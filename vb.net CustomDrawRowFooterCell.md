"vb.net
"Luego de agrupar los registros en el view.

Private Sub dtg_pedidos_por_anio_int_CustomDrawRowFooterCell(sender As Object, e As FooterCellCustomDrawEventArgs) Handles dtg_pedidos_por_anio_int.CustomDrawRowFooterCell
        Dim level As Integer = Me.dtg_pedidos_por_anio_int.GetRowLevel(e.RowHandle)
        Dim valor As Double = 0
        Dim pedidosAceptados As Integer = 0
        Dim LicitacionesAgrupados As Integer = 0

        If level = 1 Or level = 0 Then
            Dim adj As cls_Pedidos_anio_interempresas = CType(Me.dtg_pedidos_por_anio_int.GetRow(e.RowHandle), cls_Pedidos_anio_interempresas)
            Dim adjs As List(Of cls_Pedidos_anio_interempresas) = CType(Me.dtg_pedidos_por_anio_int.DataSource, List(Of cls_Pedidos_anio_interempresas))

            If adj Is Nothing Then
                Return
            End If
            Select Case e.Info.Column.FieldName
                Case "porcentaje1"
                    For Each r As cls_Pedidos_anio_interempresas In adjs
                        If adj.supervisor.Gerente.Nombre.ToUpper = r.supervisor.Gerente.Nombre.ToUpper Then
                            If r.mes1 > 0 Then
                                pedidosAceptados += r.pedidosAceptados1
                                LicitacionesAgrupados += r.licitacionesAgrupados1

                            End If
                        End If
                    Next
                    If pedidosAceptados <> 0 And LicitacionesAgrupados <> 0 Then
                        If pedidosAceptados = 0 Then
                            valor = 0
                        Else
                            valor = pedidosAceptados / LicitacionesAgrupados
                        End If
                    End If
                    e.Info.DisplayText = Format$(valor, "0%")
                    Dim app As New DevExpress.Utils.AppearanceObject
                    app.TextOptions.HAlignment = DevExpress.Utils.HorzAlignment.Center
                    e.Info.SetAppearance(app)
                Case "porcentaje2"
                    For Each r As cls_Pedidos_anio_interempresas In adjs
                        If adj.supervisor.Gerente.Nombre.ToUpper = r.supervisor.Gerente.Nombre.ToUpper Then
                            If r.mes2 > 0 Then
                                pedidosAceptados += r.pedidosAceptados2
                                LicitacionesAgrupados += r.licitacionesAgrupados2

                            End If
                        End If
                    Next
                    If pedidosAceptados <> 0 And LicitacionesAgrupados <> 0 Then
                        If pedidosAceptados = 0 Then
                            valor = 0
                        Else
                            valor = pedidosAceptados / LicitacionesAgrupados
                        End If
                    End If
                    e.Info.DisplayText = Format$(valor, "0%")
                    Dim app As New DevExpress.Utils.AppearanceObject
                    app.TextOptions.HAlignment = DevExpress.Utils.HorzAlignment.Center
                    e.Info.SetAppearance(app)
                Case "porcentaje3"
                    For Each r As cls_Pedidos_anio_interempresas In adjs
                        If adj.supervisor.Gerente.Nombre.ToUpper = r.supervisor.Gerente.Nombre.ToUpper Then
                            If r.mes3 > 0 Then
                                pedidosAceptados += r.pedidosAceptados3
                                LicitacionesAgrupados += r.licitacionesAgrupados3

                            End If
                        End If
                    Next
                    If pedidosAceptados <> 0 And LicitacionesAgrupados <> 0 Then
                        If pedidosAceptados = 0 Then
                            valor = 0
                        Else
                            valor = pedidosAceptados / LicitacionesAgrupados
                        End If
                    End If
                    e.Info.DisplayText = Format$(valor, "0%")
                    Dim app As New DevExpress.Utils.AppearanceObject
                    app.TextOptions.HAlignment = DevExpress.Utils.HorzAlignment.Center
                    e.Info.SetAppearance(app)

                Case "porcentaje4"
                    For Each r As cls_Pedidos_anio_interempresas In adjs
                        If adj.supervisor.Gerente.Nombre.ToUpper = r.supervisor.Gerente.Nombre.ToUpper Then
                            If r.mes4 > 0 Then
                                pedidosAceptados += r.pedidosAceptados4
                                LicitacionesAgrupados += r.licitacionesAgrupados4

                            End If
                        End If
                    Next
                    If pedidosAceptados <> 0 And LicitacionesAgrupados <> 0 Then
                        If pedidosAceptados = 0 Then
                            valor = 0
                        Else
                            valor = pedidosAceptados / LicitacionesAgrupados
                        End If
                    End If
                    e.Info.DisplayText = Format$(valor, "0%")
                    Dim app As New DevExpress.Utils.AppearanceObject
                    app.TextOptions.HAlignment = DevExpress.Utils.HorzAlignment.Center
                    e.Info.SetAppearance(app)

                Case "porcentaje5"
                    For Each r As cls_Pedidos_anio_interempresas In adjs
                        If adj.supervisor.Gerente.Nombre.ToUpper = r.supervisor.Gerente.Nombre.ToUpper Then
                            If r.mes5 > 0 Then
                                pedidosAceptados += r.pedidosAceptados5
                                LicitacionesAgrupados += r.licitacionesAgrupados5

                            End If
                        End If
                    Next
                    If pedidosAceptados <> 0 And LicitacionesAgrupados <> 0 Then
                        If pedidosAceptados = 0 Then
                            valor = 0
                        Else
                            valor = pedidosAceptados / LicitacionesAgrupados
                        End If
                    End If
                    e.Info.DisplayText = Format$(valor, "0%")
                    Dim app As New DevExpress.Utils.AppearanceObject
                    app.TextOptions.HAlignment = DevExpress.Utils.HorzAlignment.Center
                    e.Info.SetAppearance(app)

                Case "porcentaje6"
                    For Each r As cls_Pedidos_anio_interempresas In adjs
                        If adj.supervisor.Gerente.Nombre.ToUpper = r.supervisor.Gerente.Nombre.ToUpper Then
                            If r.mes6 > 0 Then
                                pedidosAceptados += r.pedidosAceptados6
                                LicitacionesAgrupados += r.licitacionesAgrupados6

                            End If
                        End If
                    Next
                    If pedidosAceptados <> 0 And LicitacionesAgrupados <> 0 Then
                        If pedidosAceptados = 0 Then
                            valor = 0
                        Else
                            valor = pedidosAceptados / LicitacionesAgrupados
                        End If
                    End If
                    e.Info.DisplayText = Format$(valor, "0%")
                    Dim app As New DevExpress.Utils.AppearanceObject
                    app.TextOptions.HAlignment = DevExpress.Utils.HorzAlignment.Center
                    e.Info.SetAppearance(app)

                Case "porcentaje7"
                    For Each r As cls_Pedidos_anio_interempresas In adjs
                        If adj.supervisor.Gerente.Nombre.ToUpper = r.supervisor.Gerente.Nombre.ToUpper Then
                            If r.mes7 > 0 Then
                                pedidosAceptados += r.pedidosAceptados7
                                LicitacionesAgrupados += r.licitacionesAgrupados7

                            End If
                        End If
                    Next
                    If pedidosAceptados <> 0 And LicitacionesAgrupados <> 0 Then
                        If pedidosAceptados = 0 Then
                            valor = 0
                        Else
                            valor = pedidosAceptados / LicitacionesAgrupados
                        End If
                    End If
                    e.Info.DisplayText = Format$(valor, "0%")
                    Dim app As New DevExpress.Utils.AppearanceObject
                    app.TextOptions.HAlignment = DevExpress.Utils.HorzAlignment.Center
                    e.Info.SetAppearance(app)

                Case "porcentaje8"
                    For Each r As cls_Pedidos_anio_interempresas In adjs
                        If adj.supervisor.Gerente.Nombre.ToUpper = r.supervisor.Gerente.Nombre.ToUpper Then
                            If r.mes8 > 0 Then
                                pedidosAceptados += r.pedidosAceptados8
                                LicitacionesAgrupados += r.licitacionesAgrupados8

                            End If
                        End If
                    Next
                    If pedidosAceptados <> 0 And LicitacionesAgrupados <> 0 Then
                        If pedidosAceptados = 0 Then
                            valor = 0
                        Else
                            valor = pedidosAceptados / LicitacionesAgrupados
                        End If
                    End If
                    e.Info.DisplayText = Format$(valor, "0%")
                    Dim app As New DevExpress.Utils.AppearanceObject
                    app.TextOptions.HAlignment = DevExpress.Utils.HorzAlignment.Center
                    e.Info.SetAppearance(app)

                Case "porcentaje9"
                    For Each r As cls_Pedidos_anio_interempresas In adjs
                        If adj.supervisor.Gerente.Nombre.ToUpper = r.supervisor.Gerente.Nombre.ToUpper Then
                            If r.mes9 > 0 Then
                                pedidosAceptados += r.pedidosAceptados9
                                LicitacionesAgrupados += r.licitacionesAgrupados9

                            End If
                        End If
                    Next
                    If pedidosAceptados <> 0 And LicitacionesAgrupados <> 0 Then
                        If pedidosAceptados = 0 Then
                            valor = 0
                        Else
                            valor = pedidosAceptados / LicitacionesAgrupados
                        End If
                    End If
                    e.Info.DisplayText = Format$(valor, "0%")
                    Dim app As New DevExpress.Utils.AppearanceObject
                    app.TextOptions.HAlignment = DevExpress.Utils.HorzAlignment.Center
                    e.Info.SetAppearance(app)

                Case "porcentaje10"
                    For Each r As cls_Pedidos_anio_interempresas In adjs
                        If adj.supervisor.Gerente.Nombre.ToUpper = r.supervisor.Gerente.Nombre.ToUpper Then
                            If r.mes10 > 0 Then
                                pedidosAceptados += r.pedidosAceptados10
                                LicitacionesAgrupados += r.licitacionesAgrupados10

                            End If
                        End If
                    Next
                    If pedidosAceptados <> 0 And LicitacionesAgrupados <> 0 Then
                        If pedidosAceptados = 0 Then
                            valor = 0
                        Else
                            valor = pedidosAceptados / LicitacionesAgrupados
                        End If
                    End If
                    e.Info.DisplayText = Format$(valor, "0%")
                    Dim app As New DevExpress.Utils.AppearanceObject
                    app.TextOptions.HAlignment = DevExpress.Utils.HorzAlignment.Center
                    e.Info.SetAppearance(app)

                Case "porcentaje11"
                    For Each r As cls_Pedidos_anio_interempresas In adjs
                        If adj.supervisor.Gerente.Nombre.ToUpper = r.supervisor.Gerente.Nombre.ToUpper Then
                            If r.mes11 > 0 Then
                                pedidosAceptados += r.pedidosAceptados11
                                LicitacionesAgrupados += r.licitacionesAgrupados11

                            End If
                        End If
                    Next
                    If pedidosAceptados <> 0 And LicitacionesAgrupados <> 0 Then
                        If pedidosAceptados = 0 Then
                            valor = 0
                        Else
                            valor = pedidosAceptados / LicitacionesAgrupados
                        End If
                    End If
                    e.Info.DisplayText = Format$(valor, "0%")
                    Dim app As New DevExpress.Utils.AppearanceObject
                    app.TextOptions.HAlignment = DevExpress.Utils.HorzAlignment.Center
                    e.Info.SetAppearance(app)

                Case "porcentaje12"
                    For Each r As cls_Pedidos_anio_interempresas In adjs
                        If adj.supervisor.Gerente.Nombre.ToUpper = r.supervisor.Gerente.Nombre.ToUpper Then
                            If r.mes12 > 0 Then
                                pedidosAceptados += r.pedidosAceptados12
                                LicitacionesAgrupados += r.licitacionesAgrupados12

                            End If
                        End If
                    Next
                    If pedidosAceptados <> 0 And LicitacionesAgrupados <> 0 Then
                        If pedidosAceptados = 0 Then
                            valor = 0
                        Else
                            valor = pedidosAceptados / LicitacionesAgrupados
                        End If
                    End If
                    e.Info.DisplayText = Format$(valor, "0%")
                    Dim app As New DevExpress.Utils.AppearanceObject
                    app.TextOptions.HAlignment = DevExpress.Utils.HorzAlignment.Center
                    e.Info.SetAppearance(app)

                Case "porcentaje_tt"
                    For Each r As cls_Pedidos_anio_interempresas In adjs
                        If adj.supervisor.Gerente.Nombre.ToUpper = r.supervisor.Gerente.Nombre.ToUpper Then
                            pedidosAceptados += r.pedidosAceptados_tt
                            LicitacionesAgrupados += r.licitacionesAgrupados_tt
                        End If
                    Next
                    If pedidosAceptados <> 0 And LicitacionesAgrupados <> 0 Then
                        If pedidosAceptados = 0 Then
                            valor = 0
                        Else
                            valor = pedidosAceptados / LicitacionesAgrupados
                        End If
                    End If
                    e.Info.DisplayText = Format$(valor, "0%")
                    Dim app As New DevExpress.Utils.AppearanceObject
                    app.TextOptions.HAlignment = DevExpress.Utils.HorzAlignment.Center
                    e.Info.SetAppearance(app)
            End Select
        End If
    End Sub
