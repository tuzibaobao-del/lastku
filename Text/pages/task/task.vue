<%@page contentType="text/html;charset=UTF-8"%>
<%@include file="/taglibs.jsp"%>
<%pageContext.setAttribute("currentHeader", "cangku");%>
<%pageContext.setAttribute("currentMenu", "cangku");%>
<!doctype html>
<html lang="en">
	<head>
		<%@include file="/common/meta.jsp"%>
		<title>
			<spring:message code="dev.car-info.list.title" text="会计科目维护" />
		</title>
		<%@include file="/common/s3.jsp"%>
		<script type="text/javascript">
			ROOT_URL = '${tenantPrefix}';
			/* var taskOperation = new TaskOperation(); */
		</script>
		<script type="text/javascript" src="${tenantPrefix}/eahsoft/js/jquery-form.js"></script>
		<script type="text/javascript">
			var config = {
				id: 'wuzi-infoGrid',
				pageNo: $ {
					page.pageNo
				},
				pageSize: $ {
					page.pageSize
				},
				totalCount: $ {
					page.totalCount
				},
				resultSize: $ {
					page.resultSize
				},
				pageCount: $ {
					page.pageCount
				},
				orderBy: '${page.orderBy == null ? "" : page.orderBy}',
				asc: $ {
					page.asc
				},
				params: {
					'hsdw_dm': '${data.hsdw_dm}',
					'zcnd': '${data.zcnd}',
					'rkdid': '${param.rkdid}'
				},
				selectedItemClass: 'selectedItem',
				gridFormId: 'wuzi-infoGridForm',
				exportUrl: 'car-info-export.do'
			};

			var table;
			$(function() {
				table = new Table(config);
				table.configPagination('.m-pagination');
				table.configPageInfo('.m-page-info');
				table.configPageSize('.m-page-size');
			});
		</script>
		<script language="javascript" type="text/javascript">
			window.onload = function() {
				//设置年份的选择 
				var myDate = new Date();
				var startYear = myDate.getFullYear() - 5; //起始年份 
				var endYear = myDate.getFullYear() + 5; //结束年份 
				var obj = document.getElementById('myYear')
				for (var i = startYear; i <= endYear; i++) {
					obj.options.add(new Option(i, i));
				}
				var obj1 = document.getElementById('myMonth')
				for (var i = 1; i <= 12; i++) {
					obj1.options.add(new Option(i, i));
				}
				$("#myYear").val("${data.zcnd}");
				$("#myMonth").val("${data.zcnd}");
				$("#zckm").val("${data.zckm}");
				$("#dwmc").val("${data.dwmc}");
			}
		</script>
		<script type="text/javascript">
			function del() {
				var id = new Array();
				var i = 0;
				$($(".a-check")).each(function() {
					if ($(this).is(':checked')) {
						id[i] = $(this).val();
						i++;
					}
				});
				$.ajax({
					url: "${tenantPrefix}/yhrjz2/kjkm_del.do?id=" + id,
					type: "post",
					dataType: "json",
					success: function(data) {
						window.location.reload();
					}
				});
			}
		</script>
		<script type="text/javascript">
			//ajax 方式上传文件操作
			$(document).ready(function() {
				$('#btn').click(function() {
					$("#drnd").val($("#myYear").val());
					$("#drnd").val($("#myMonth").val());
					if (checkData()) {
						$('#form1').ajaxSubmit({
							//url:'uploadExcel/ajaxUpload.do',
							url: "${tenantPrefix}" + "/yhrjz2/excelimportwages.do",
							dataType: 'text',
							success: resutlMsg,
							error: errorMsg
						});

						function resutlMsg(msg) {
							alert(msg);
							$("#upfile").val("");
							window.location.reload();
						}

						function errorMsg() {
							alert("导入excel出错！");
						}
					}
				});
			});

			//JS校验form表单信息
			function checkData() {
				var fileDir = $("#upfile").val();
				var suffix = fileDir.substr(fileDir.lastIndexOf("."));
				if ("" == fileDir) {
					alert("选择需要导入的Excel文件！");
					return false;
				}
				if (".xls" != suffix && ".xlsx" != suffix) {
					alert("选择Excel格式的文件导入！");
					return false;
				}
				return true;
			}
		</script>
	</head>
	<body>
		<%@include file="/header/bpm-workspace3.jsp"%>
		<div class="row-fluid">
			<%@include file="/menu/cangku-info.jsp"%>
			<!-- start of main -->
			<section id="m-main" class="col-md-10" style="padding-top: 65px;">
				<div class="panel panel-default">
					<div class="panel-heading">
						<i class="glyphicon glyphicon-list"></i>
						查询
						<div class="pull-right ctrl">
							<a class="btn btn-default btn-xs">
								<i id="car-infoSearchIcon" class="glyphicon glyphicon-chevron-up"></i>
							</a>
						</div>
					</div>
					<div class="panel-body">
						<form name="wzdm-chaxun-infoForm" method="post" action="kjkmwh.do" class="form-inline">
							<label for="ruku-mx-info_name">核算单位:</label>
							<input type="text" id="ruku-mx-info_name" name="hsdw" value="${data.hsdw}" class="form-control">
							<label for="ruku-mx-info_xinghao">使用年度:</label>
							<select id="myYear" name="zcnd" class="form-control">
							</select>
							<label for="ruku-mx-info_xinghao">月份:</label>
							<select id="myMonth" name="zcnd" class="form-control">
							</select>
							<button class="btn btn-default a-search" onclick="document.wzdm-chaxun-infoForm.submit()">查询</button>
							&nbsp;
							<jsp:include page="/content/form/form-back.jsp"></jsp:include>

						</form>
					</div>
				</div>
				<div style="margin-bottom: 20px;" class="grid-top-bar">
					<!--  <div class="pull-left btn-group" role="group">
					<button class="btn btn-default a-insert" onclick="location.href='setkjkm.do'">新建</button>
				</div>-->
					<div class="pull-left btn-group" role="group">
						<button class="btn btn-default a-remove" onclick="del();">删除</button>
					</div>
					<form method="POST" enctype="multipart/form-data" id="form1" action="uploadExcel/upload.do">
						<input id="drnd" type="hidden" name="drnd" value="">
						<input id="dmonth" type="hidden" name="dmonth" value="">
						<table>
							<tr>
								<td>上传文件:</td>
								<td>
									<input id="upfile" type="file" name="upfile">
								</td>
								<td>
									<input type="button" value="导入" id="btn" name="btn">
								</td>
							</tr>
						</table>
					</form>

					<div class="clearfix"></div>
				</div>
				<form id="wuzi-infoGridForm" name="wuzi-infoGridForm" method='post' action="kjkm_del.do" class="m-form-blank"
				 enctype="multipart/form-data">
					<div class="panel panel-default">
						<div class="panel-heading">
							<i class="glyphicon glyphicon-list"></i>
							<spring:message code="scope-info.scope-info.list.title" text="列表" />
						</div>
						<table id="wuzi-infoGrid" class="table table-hover">
							<thead>
								<tr>
									<th width="80" class="table-check">
										<input type="checkbox" name="checkAll" onchange="toggleSelectedItems(this.checked)" />
									</th>
									<th class="" name="kmdm">录入人</th>
									<th class="" name="xz">填报时间</th>
									<th class="" name="synd">年度</th>
									<th class="" name="synd">核算单位名称</th>
								</tr>
							</thead>
							<tbody>
								<c:forEach items="${page.result}" var="item">
									<tr>
										<td class="text-center">
											<input type="checkbox" class="selectedItem a-check" name="selectedItem" value="${item.ID}">
										</td>
										<td>${item.USERNAME}</td>
										<td>${item.LRRQ}</td>
										<td>${item.GZND}</td>
										<td>${item.HSDWMC}</td>
									</tr>
								</c:forEach>
							</tbody>
						</table>
					</div>
				</form>
				<div class="grid-bottom-bar">
					<div class="m-page-info pull-left">共100条记录 显示1到10条记录</div>
					<div class="btn-group m-pagination pull-right">
						<button class="btn btn-default">&lt;</button>
						<button class="btn btn-default">1</button>
						<button class="btn btn-default">&gt;</button>
					</div>
					<div class="pull-left">
						每页显示
						<select class="m-page-size form-control" style="display: inline; width: auto;">
							<option value="10">10</option>
							<option value="20">20</option>
							<option value="50">50</option>
						</select>
						条
					</div>
					<div class="clearfix"></div>
				</div>
				<div class="m-spacer"></div>
			</section>
			<!-- end of main -->
		</div>
	</body>
</html>
