
Devexpress vb.net impresos
Asignar en los grupos del reporte porcentajes, de manera personalizada o manual. 
Nota: observar los metodos que se refieren a despues de impreso el reporte. es decir despues que coloca los valores en los campos sumados el sistema toma los datos con el AfterPrint, y los pone en estado disponible por medio de una variable  para el metodo SummaryGetResult los tome y calcule el porcentaje. abajo dos 

Breve explicación.
tenemos el(os) campo que sum los grupos
tenemos el(os) campo que calculara el porcentaje

El AfterPrint de los campos que suman los agrupados en el código obtienen el dato por medio de una variable
El SummaryGetResult del campo que va calcular por medio de las variables el porcentaje, establece el valor del calculo. es importante que no se puede colocar el formato {0%} en las propiedades del campo ya que altera el porcentaje habría que concatenar el resultado del calculo despues de redondear con la cadena % para que se muestre en el resultado.

vb.net/grilla/ cuadro de control

Dim agrupados_m10 As Integer = 0 : Dim pedidosAcept_m10 As Integer = 0
    Dim agrupados_m10_1 As Integer = 0 : Dim pedidosAcept_m10_1 As Integer = 0

    Dim agrupados_m11 As Integer = 0 : Dim pedidosAcept_m11 As Integer = 0
    Dim agrupados_m11_1 As Integer = 0 : Dim pedidosAcept_m11_1 As Integer = 0

    Dim agrupados_m12 As Integer = 0 : Dim pedidosAcept_m12 As Integer = 0
    Dim agrupados_m12_1 As Integer = 0 : Dim pedidosAcept_m12_1 As Integer = 0

    Dim agrupados_mtt As Integer = 0 : Dim pedidosAcept_mtt As Integer = 0
    '   Dim agrupados_mtt_1 As Integer = 0 : Dim pedidosAcept_mtt_1 As Integer = 0

    Dim pedidosAcept_mtt_0_1 As Integer = 0 : Dim agrupados_0_1 As Integer = 0
    Dim pedidosAcept_mtt_1_1 As Integer = 0 : Dim agrupados_mtt_1_1 As Integer = 0

    Dim pedidosAcept_mtt_0_2 As Integer = 0 : Dim agrupados_0_2 As Integer = 0
    Dim pedidosAcept_mtt_1_2 As Integer = 0 : Dim agrupados_mtt_1_2 As Integer = 0

    Dim pedidosAcept_0_mtt As Integer = 0 : Dim agrupados_0_mtt As Integer = 0
    Dim pedidosAcept_1_mtt As Integer = 0 : Dim agrupados_1_mtt As Integer = 0

    Dim agrupados_m9 As Integer = 0 : Dim pedidosAcept_m9 As Integer = 0
    Dim pedidosAcept_m9_1 As Integer = 0 : Dim agrupados_m9_1 As Integer = 0

    Dim agrupados_0_3 As Integer = 0 : Dim pedidosAcept_0_3 As Integer = 0
    Dim pedidosAcept_1_3 As Integer = 0 : Dim agrupados_1_3 As Integer = 0

    Dim agrupados_0_4 As Integer = 0 : Dim pedidosAcept_0_4 As Integer = 0
    Dim pedidosAcept_1_4 As Integer = 0 : Dim agrupados_1_4 As Integer = 0

    Dim agrupados_0_5 As Integer = 0 : Dim pedidosAcept_0_5 As Integer = 0
    Dim pedidosAcept_1_5 As Integer = 0 : Dim agrupados_1_5 As Integer = 0

    Dim agrupados_0_6 As Integer = 0 : Dim pedidosAcept_0_6 As Integer = 0
    Dim pedidosAcept_1_6 As Integer = 0 : Dim agrupados_1_6 As Integer = 0

    Dim agrupados_0_7 As Integer = 0 : Dim pedidosAcept_0_7 As Integer = 0
    Dim pedidosAcept_1_7 As Integer = 0 : Dim agrupados_1_7 As Integer = 0

    Dim agrupados_0_8 As Integer = 0 : Dim pedidosAcept_0_8 As Integer = 0
    Dim pedidosAcept_1_8 As Integer = 0 : Dim agrupados_1_8 As Integer = 0

    
#Region "mes 01"
    Private Sub lic_agrupa_1_g0_AfterPrint(sender As Object, e As EventArgs) Handles lic_agrupa_1_g0.AfterPrint
        If lic_agrupa_1_g0.Text <> "" Then
            agrupados_0_1 = CInt(lic_agrupa_1_g0.Text)
        End If
    End Sub
    Private Sub pedAceptados_0_1_AfterPrint(sender As Object, e As EventArgs) Handles pedAceptados_0_1.AfterPrint
        If pedAceptados_0_1.Text <> "" Then
            pedidosAcept_mtt_0_1 = CInt(pedAceptados_0_1.Text)
        End If
    End Sub

    Private Sub t_porc_1_g0_SummaryGetResult(sender As Object, e As SummaryGetResultEventArgs) Handles t_porc_1_g0.SummaryGetResult
        If pedidosAcept_mtt_0_1 <> 0 And agrupados_0_1 <> 0 Then
            e.Result = CStr(CInt(Math.Round(((pedidosAcept_mtt_0_1 / agrupados_0_1) * 100), 0))) & "%"
        Else
            e.Result = CStr(0) & "%"
        End If
        e.Handled = True
        Dim f As String = XrLabel39.Text
    End Sub
    ' ----- grupo level  1--------------
    Private Sub lic_agrupa_1_g1_AfterPrint(sender As Object, e As EventArgs) Handles lic_agrupa_1_g1.AfterPrint
        If lic_agrupa_1_g1.Text <> "" Then
            agrupados_mtt_1_1 = CInt(lic_agrupa_1_g1.Text)
        End If
    End Sub

    Private Sub pedAceptados_1_1_AfterPrint(sender As Object, e As EventArgs) Handles pedAceptados_1_1.AfterPrint
        If pedAceptados_1_1.Text <> "" Then
            pedidosAcept_mtt_1_1 = CInt(pedAceptados_1_1.Text)
        End If
    End Sub

    Private Sub t_porc_1_g1_SummaryGetResult(sender As Object, e As SummaryGetResultEventArgs) Handles t_porc_1_g1.SummaryGetResult
        If pedidosAcept_mtt_1_1 <> 0 And agrupados_mtt_1_1 <> 0 Then
            e.Result = CStr(CInt(Math.Round(((pedidosAcept_mtt_1_1 / agrupados_mtt_1_1) * 100), 0))) & "%"
        Else
            e.Result = CStr(0) & "%"
        End If
        e.Handled = True
    End Sub
#End Region

#Region "mes 02"

    Private Sub pedAceptados_0_2_AfterPrint(sender As Object, e As EventArgs) Handles pedAceptados_0_2.AfterPrint
        If pedAceptados_0_2.Text <> "" Then
            pedidosAcept_mtt_0_2 = CInt(pedAceptados_0_2.Text)
        End If
    End Sub
    Private Sub lic_agrupa_2_g0_AfterPrint(sender As Object, e As EventArgs) Handles lic_agrupa_2_g0.AfterPrint
        If lic_agrupa_2_g0.Text <> "" Then
            agrupados_0_2 = CInt(lic_agrupa_2_g0.Text)
        End If
    End Sub
    Private Sub t_porc_2_g0_SummaryGetResult(sender As Object, e As SummaryGetResultEventArgs) Handles t_porc_2_g0.SummaryGetResult
        If pedidosAcept_mtt_0_2 <> 0 And agrupados_0_2 <> 0 Then
            e.Result = CStr(CInt(Math.Round(((pedidosAcept_mtt_0_2 / agrupados_0_2) * 100), 0))) & "%"
        Else
            e.Result = CStr(0) & "%"
        End If
        e.Handled = True
    End Sub
    ' --------------------------------------
    Private Sub pedAceptados_1_2_AfterPrint(sender As Object, e As EventArgs) Handles pedAceptados_1_2.AfterPrint
        If pedAceptados_1_2.Text <> "" Then
            pedidosAcept_mtt_1_2 = CInt(pedAceptados_1_2.Text)
        End If
    End Sub
    Private Sub lic_agrupa_2_g1_AfterPrint(sender As Object, e As EventArgs) Handles lic_agrupa_2_g1.AfterPrint
        If lic_agrupa_2_g1.Text <> "" Then
            agrupados_mtt_1_2 = CInt(lic_agrupa_2_g1.Text)
        End If
    End Sub
    Private Sub t_porc_2_g1_SummaryGetResult(sender As Object, e As SummaryGetResultEventArgs) Handles t_porc_2_g1.SummaryGetResult
        If pedidosAcept_mtt_1_2 <> 0 And agrupados_mtt_1_2 <> 0 Then
            e.Result = CStr(CInt(Math.Round(((pedidosAcept_mtt_1_2 / agrupados_mtt_1_2) * 100), 0))) & "%"
        Else
            e.Result = CStr(0) & "%"
        End If
        e.Handled = True
    End Sub
#End Region

#Region "mes 9"
    Private Sub XrLabel248_AfterPrint(sender As Object, e As EventArgs) Handles pedAcep_g0_m9.AfterPrint
        If pedAcep_g0_m9.Text <> "" Then
            pedidosAcept_m9 = CInt(pedAcep_g0_m9.Text)
        End If
        Dim f As String = XrLabel39.Text : Dim G As String = XrLabel55.Text
        If f = "EDUARDO MUÑIZ" Then
            Beep()
        End If
    End Sub
    Private Sub XrLabel56_AfterPrint(sender As Object, e As EventArgs) Handles agrupa_g0_m9.AfterPrint
        If agrupa_g0_m9.Text <> "" Then
            agrupados_m9 = CInt(agrupa_g0_m9.Text)
        End If
    End Sub
    Private Sub t_porc_9_g0_SummaryGetResult(sender As Object, e As SummaryGetResultEventArgs) Handles t_porc_9_g0.SummaryGetResult
        If pedidosAcept_m9 <> 0 And agrupados_m9 <> 0 Then
            e.Result = CStr(CInt(Math.Round(((pedidosAcept_m9 / agrupados_m9) * 100), 0))) & "%"
        Else
            e.Result = CStr(0) & "%"
        End If
        e.Handled = True
    End Sub
    '------------------
    Private Sub agrupa_1_9_AfterPrint(sender As Object, e As EventArgs) Handles agrupa_1_9.AfterPrint
        If agrupa_1_9.Text <> "" Then
            agrupados_m9_1 = CInt(agrupa_1_9.Text)
        End If
        Dim f As String = XrLabel39.Text : Dim G As String = XrLabel55.Text
        If f = "EDUARDO MUÑIZ" Then
            Beep()
        End If
    End Sub
    Private Sub pedidoAcep_1_9_AfterPrint(sender As Object, e As EventArgs) Handles pedidoAcep_1_9.AfterPrint
        If pedidoAcep_1_9.Text <> "" Then
            pedidosAcept_m9_1 = CInt(pedidoAcep_1_9.Text)
        End If
    End Sub
    Private Sub t_porc_9_g1_SummaryGetResult(sender As Object, e As SummaryGetResultEventArgs) Handles t_porc_9_g1.SummaryGetResult
        If pedidosAcept_m9_1 <> 0 And agrupados_m9_1 <> 0 Then
            e.Result = CStr(CInt(Math.Round(((pedidosAcept_m9_1 / agrupados_m9_1) * 100), 0))) & "%"
        Else
            e.Result = CStr(0) & "%"
        End If
        e.Handled = True
    End Sub
#End Region

#Region "mes 10"
    Private Sub pedAcep_g0_m10_AfterPrint(sender As Object, e As EventArgs) Handles pedAcep_g0_m10.AfterPrint
        If pedAcep_g0_m10.Text <> "" Then
            pedidosAcept_m10 = CInt(pedAcep_g0_m10.Text)
        End If
    End Sub

    Private Sub agrupa_g0_10_AfterPrint(sender As Object, e As EventArgs) Handles agrupa_g0_10.AfterPrint
        If agrupa_g0_10.Text <> "" Then
            agrupados_m10 = CInt(agrupa_g0_10.Text)
        End If
    End Sub

    Private Sub t_porc_10_g0_SummaryGetResult(sender As Object, e As SummaryGetResultEventArgs) Handles t_porc_10_g0.SummaryGetResult
        If pedidosAcept_m10 <> 0 And agrupados_m10 <> 0 Then
            e.Result = CStr(CInt(Math.Round(((pedidosAcept_m10 / agrupados_m10) * 100), 0))) & "%"
        Else
            e.Result = CStr(0) & "%"
        End If
        e.Handled = True
    End Sub

    Private Sub pedAcep_g1_10_AfterPrint(sender As Object, e As EventArgs) Handles pedAcep_g1_10.AfterPrint

        If pedAcep_g1_10.Text <> "" Then
            pedidosAcept_m10_1 = CInt(pedAcep_g1_10.Text)
        End If
    End Sub

    Private Sub agrupa_g1_10_AfterPrint(sender As Object, e As EventArgs) Handles agrupa_g1_10.AfterPrint

        If agrupa_g1_10.Text <> "" Then
            agrupados_m10_1 = CInt(agrupa_g1_10.Text)
        End If
    End Sub
    Private Sub t_porc10_g1_SummaryGetResult(sender As Object, e As SummaryGetResultEventArgs) Handles t_porc10_g1.SummaryGetResult
        If pedidosAcept_m10_1 <> 0 And agrupados_m10_1 <> 0 Then
            e.Result = CStr(CInt(Math.Round(((pedidosAcept_m10_1 / agrupados_m10_1) * 100), 0))) & "%"
        Else
            e.Result = CStr(0) & "%"
        End If
        e.Handled = True
    End Sub
#End Region

#Region "mes 11"
    Private Sub pedAcep_g0_m11_AfterPrint(sender As Object, e As EventArgs) Handles pedAcep_g0_m11.AfterPrint
        If pedAcep_g0_m11.Text <> "" Then
            pedidosAcept_m11 = CInt(pedAcep_g0_m11.Text)
        End If
    End Sub
    Private Sub agrupa_g0_m11_AfterPrint(sender As Object, e As EventArgs) Handles agrupa_g0_m11.AfterPrint
        If agrupa_g0_m11.Text <> "" Then
            agrupados_m11 = CInt(agrupa_g0_m11.Text)
        End If
    End Sub
    Private Sub t_porc_11_g0_SummaryGetResult(sender As Object, e As SummaryGetResultEventArgs) Handles t_porc_11_g0.SummaryGetResult
        If pedidosAcept_m11 <> 0 And agrupados_m11 <> 0 Then
            e.Result = CStr(CInt(Math.Round(((pedidosAcept_m11 / agrupados_m11) * 100), 0))) & "%"
        Else
            e.Result = CStr(0) & "%"
        End If
        e.Handled = True
    End Sub
    '---------------
    Private Sub pedAcep_g1_m11_AfterPrint(sender As Object, e As EventArgs) Handles pedAcep_g1_m11.AfterPrint
        If pedAcep_g1_m11.Text <> "" Then
            pedidosAcept_m11_1 = CInt(pedAcep_g1_m11.Text)
        End If
    End Sub
    Private Sub agrupa_g1_m11_AfterPrint(sender As Object, e As EventArgs) Handles agrupa_g1_m11.AfterPrint
        If agrupa_g1_m11.Text <> "" Then
            agrupados_m11_1 = CInt(agrupa_g1_m11.Text)
        End If
    End Sub
    Private Sub t_porc_11_g1_SummaryGetResult(sender As Object, e As SummaryGetResultEventArgs) Handles t_porc_11_g1.SummaryGetResult
        If pedidosAcept_m11 <> 0 And agrupados_m11 <> 0 Then
            e.Result = CStr(CInt(Math.Round(((pedidosAcept_m11 / agrupados_m11) * 100), 0))) & "%"
        Else
            e.Result = CStr(0) & "%"
        End If
        e.Handled = True
    End Sub
#End Region

#Region "mes 12"
    Private Sub pedAcep_g0_m12_AfterPrint(sender As Object, e As EventArgs) Handles pedAcep_g0_m12.AfterPrint
        If pedAcep_g0_m12.Text <> "" Then
            pedidosAcept_m12 = CInt(pedAcep_g0_m12.Text)
        End If
    End Sub
    Private Sub agrupa_g0_m12_AfterPrint(sender As Object, e As EventArgs) Handles agrupa_g0_m12.AfterPrint
        If agrupa_g0_m12.Text <> "" Then
            agrupados_m12 = CInt(agrupa_g0_m12.Text)
        End If
    End Sub
    Private Sub t_porc12_g0_SummaryGetResult(sender As Object, e As SummaryGetResultEventArgs) Handles t_porc12_g0.SummaryGetResult
        If pedidosAcept_m12 <> 0 And agrupados_m12 <> 0 Then
            e.Result = CStr(CInt(Math.Round(((pedidosAcept_m12 / agrupados_m12) * 100), 0))) & "%"
        Else
            e.Result = CStr(0) & "%"
        End If
        e.Handled = True
    End Sub
    '--------------------------------------------------------
    Private Sub pedAcep_g1_m12_AfterPrint(sender As Object, e As EventArgs) Handles pedAcep_g1_m12.AfterPrint
        If pedAcep_g1_m12.Text <> "" Then
            pedidosAcept_m12_1 = CInt(pedAcep_g1_m12.Text)
        End If
    End Sub
    Private Sub agrupa_g1_m12_AfterPrint(sender As Object, e As EventArgs) Handles agrupa_g1_m12.AfterPrint
        If agrupa_g1_m12.Text <> "" Then
            agrupados_m12_1 = CInt(agrupa_g1_m12.Text)
        End If
    End Sub
    Private Sub t_porc_12_g1_SummaryGetResult(sender As Object, e As SummaryGetResultEventArgs) Handles t_porc_12_g1.SummaryGetResult
        If pedidosAcept_m12_1 <> 0 And agrupados_m12_1 <> 0 Then
            e.Result = CStr(CInt(Math.Round(((pedidosAcept_m12_1 / agrupados_m12_1) * 100), 0))) & "%"
        Else
            e.Result = CStr(0) & "%"
        End If
        e.Handled = True
    End Sub
#End Region

#Region "mes tt"
    Private Sub pedAcep_g0_tt_AfterPrint(sender As Object, e As EventArgs) Handles pedAcep_g0_tt.AfterPrint
        If pedAcep_g0_tt.Text <> "" Then
            pedidosAcept_0_mtt = CInt(pedAcep_g0_tt.Text)
        End If
    End Sub
    Private Sub agrupa_g0_tt_AfterPrint(sender As Object, e As EventArgs) Handles agrupa_g0_tt.AfterPrint
        If agrupa_g0_tt.Text <> "" Then
            agrupados_0_mtt = CInt(agrupa_g0_tt.Text)
        End If
    End Sub
    Private Sub t_porc_tt_g0_SummaryGetResult(sender As Object, e As SummaryGetResultEventArgs) Handles t_porc_tt_g0.SummaryGetResult
        If pedidosAcept_0_mtt <> 0 And agrupados_mtt <> 0 Then
            e.Result = CStr(CInt(Math.Round(((pedidosAcept_0_mtt / agrupados_0_mtt) * 100), 0))) & "%"
        Else
            e.Result = CStr(0) & "%"
        End If
        e.Handled = True
    End Sub

    ' ---------------------------------------------
    Private Sub pedAcep_g1_mtt_AfterPrint(sender As Object, e As EventArgs) Handles pedAcep_g1_mtt.AfterPrint
        If pedAcep_g1_mtt.Text <> "" Then
            pedidosAcept_1_mtt = CInt(pedAcep_g1_mtt.Text)
        End If
    End Sub
    Private Sub agrupa_g1_tt_AfterPrint(sender As Object, e As EventArgs) Handles agrupa_g1_tt.AfterPrint
        If agrupa_g1_tt.Text <> "" Then
            agrupados_1_mtt = CInt(agrupa_g1_tt.Text)
        End If
    End Sub

    Private Sub t_porc_tt_g1_SummaryGetResult(sender As Object, e As SummaryGetResultEventArgs) Handles t_porc_tt_g1.SummaryGetResult
        If pedidosAcept_1_mtt <> 0 And agrupados_1_mtt <> 0 Then
            e.Result = CStr(CInt(Math.Round(((pedidosAcept_1_mtt / agrupados_1_mtt) * 100), 0))) & "%"
        Else
            e.Result = CStr(0) & "%"
        End If
        e.Handled = True
    End Sub
#End Region

#Region "MES 03"
    ' pedidos aceptados g0
    Private Sub XrLabel159_AfterPrint(sender As Object, e As EventArgs) Handles XrLabel159.AfterPrint
        If XrLabel159.Text <> "" Then
            pedidosAcept_0_3 = CInt(XrLabel159.Text)
        End If
    End Sub
    'agrupados g0
    Private Sub XrLabel123_AfterPrint(sender As Object, e As EventArgs) Handles XrLabel123.AfterPrint
        If XrLabel123.Text <> "" Then
            agrupados_0_3 = CInt(XrLabel123.Text)
        End If
    End Sub
    'porcentaje g0
    Private Sub XrLabel160_SummaryGetResult(sender As Object, e As SummaryGetResultEventArgs) Handles XrLabel160.SummaryGetResult
        If pedidosAcept_0_3 <> 0 And agrupados_0_3 <> 0 Then
            e.Result = CStr(CInt(Math.Round(((pedidosAcept_0_3 / agrupados_0_3) * 100), 0))) & "%"
        Else
            e.Result = CStr(0) & "%"
        End If
        e.Handled = True

    End Sub
    '-------------------------------------------------------------------------------------------------------
    ' pedidos aceptados g1
    Private Sub XrLabel187_AfterPrint(sender As Object, e As EventArgs) Handles XrLabel187.AfterPrint
        If XrLabel187.Text <> "" Then
            pedidosAcept_1_3 = CInt(XrLabel187.Text)
        End If
    End Sub

    'agrupados g1
    Private Sub XrLabel124_AfterPrint(sender As Object, e As EventArgs) Handles XrLabel124.AfterPrint
        If XrLabel124.Text <> "" Then
            agrupados_1_3 = CInt(XrLabel124.Text)
        End If
    End Sub

    'porcentaje g1
    Private Sub XrLabel188_SummaryGetResult(sender As Object, e As SummaryGetResultEventArgs) Handles XrLabel188.SummaryGetResult
        If pedidosAcept_1_3 <> 0 And agrupados_1_3 <> 0 Then
            e.Result = CStr(CInt(Math.Round(((pedidosAcept_1_3 / agrupados_1_3) * 100), 0))) & "%"
        Else
            e.Result = CStr(0) & "%"
        End If
        e.Handled = True

    End Sub

#End Region

#Region "MES 04"

    ' pedidos aceptados g0
    Private Sub XrLabel162_AfterPrint(sender As Object, e As EventArgs) Handles XrLabel162.AfterPrint
        If XrLabel162.Text <> "" Then
            pedidosAcept_0_4 = CInt(XrLabel162.Text)
        End If
    End Sub
    'agrupados g0
    Private Sub XrLabel74_AfterPrint(sender As Object, e As EventArgs) Handles XrLabel74.AfterPrint
        If XrLabel74.Text <> "" Then
            agrupados_0_4 = CInt(XrLabel74.Text)
        End If
        If agrupados_0_4 = 4 Then
            Beep()
        End If
    End Sub
    'porcentaje g0
    Private Sub XrLabel161_SummaryGetResult(sender As Object, e As SummaryGetResultEventArgs) Handles XrLabel161.SummaryGetResult

        If pedidosAcept_0_4 <> 0 And agrupados_0_4 <> 0 Then
            e.Result = CStr(CInt(Math.Round(((pedidosAcept_0_4 / agrupados_0_4) * 100), 0))) & "%"
        Else
            e.Result = CStr(0) & "%"
        End If
        e.Handled = True
        Dim f As String = XrLabel39.Text
    End Sub
    '---------------------------------------
    ' pedidos aceptados g1
    Private Sub XrLabel190_AfterPrint(sender As Object, e As EventArgs) Handles XrLabel190.AfterPrint
        If XrLabel190.Text <> "" Then
            pedidosAcept_1_4 = CInt(XrLabel190.Text)
        End If
    End Sub
    'agrupados g1
    Private Sub XrLabel76_AfterPrint(sender As Object, e As EventArgs) Handles XrLabel76.AfterPrint
        If XrLabel76.Text <> "" Then
            agrupados_1_4 = CInt(XrLabel76.Text)
        End If
    End Sub

    'porcentaje g1
    Private Sub XrLabel189_SummaryGetResult(sender As Object, e As SummaryGetResultEventArgs) Handles XrLabel189.SummaryGetResult
        If pedidosAcept_1_4 <> 0 And agrupados_1_4 <> 0 Then
            e.Result = CStr(CInt(Math.Round(((pedidosAcept_1_4 / agrupados_1_4) * 100), 0))) & "%"
        Else
            e.Result = CStr(0) & "%"
        End If
        e.Handled = True
    End Sub
#End Region

#Region "MES 05"


    ' pedidos aceptados g0
    Private Sub XrLabel127_AfterPrint(sender As Object, e As EventArgs) Handles XrLabel127.AfterPrint
        If XrLabel127.Text <> "" Then
            pedidosAcept_0_5 = CInt(XrLabel127.Text)
        End If
    End Sub
    'agrupados g0
    Private Sub XrLabel122_AfterPrint(sender As Object, e As EventArgs) Handles XrLabel122.AfterPrint
        If XrLabel122.Text <> "" Then
            agrupados_0_5 = CInt(XrLabel122.Text)
        End If
    End Sub
    'porcentaje g0
    Private Sub XrLabel169_SummaryGetResult(sender As Object, e As SummaryGetResultEventArgs) Handles XrLabel169.SummaryGetResult
        If pedidosAcept_0_5 <> 0 And agrupados_0_5 <> 0 Then
            e.Result = CStr(CInt(Math.Round(((pedidosAcept_0_5 / agrupados_0_5) * 100), 0))) & "%"
        Else
            e.Result = CStr(0) & "%"
        End If
        e.Handled = True
    End Sub

    ' pedidos aceptados g1
    Private Sub XrLabel172_AfterPrint(sender As Object, e As EventArgs) Handles XrLabel172.AfterPrint
        If XrLabel172.Text <> "" Then
            pedidosAcept_1_5 = CInt(XrLabel172.Text)
        End If
    End Sub
   
    'agrupados g1
    Private Sub XrLabel125_AfterPrint(sender As Object, e As EventArgs) Handles XrLabel125.AfterPrint
        If XrLabel125.Text <> "" Then
            agrupados_1_5 = CInt(XrLabel125.Text)
        End If
    End Sub

    'porcentaje g1
    Private Sub XrLabel197_SummaryGetResult(sender As Object, e As SummaryGetResultEventArgs) Handles XrLabel197.SummaryGetResult
        If pedidosAcept_1_5 <> 0 And agrupados_1_5 <> 0 Then
            e.Result = CStr(CInt(Math.Round(((pedidosAcept_1_5 / agrupados_1_5) * 100), 0))) & "%"
        Else
            e.Result = CStr(0) & "%"
        End If
        e.Handled = True

    End Sub
#End Region

#Region "MES 06"

    ' pedidos aceptados g0
    Private Sub XrLabel129_AfterPrint(sender As Object, e As EventArgs) Handles XrLabel129.AfterPrint
        If XrLabel129.Text <> "" Then
            pedidosAcept_0_6 = CInt(XrLabel129.Text)
        End If
    End Sub
    'agrupados g0
    Private Sub XrLabel167_AfterPrint(sender As Object, e As EventArgs) Handles XrLabel167.AfterPrint
        If XrLabel167.Text <> "" Then
            agrupados_0_6 = CInt(XrLabel167.Text)
        End If
    End Sub
    'porcentaje g0
    Private Sub XrLabel128_SummaryGetResult(sender As Object, e As SummaryGetResultEventArgs) Handles XrLabel128.SummaryGetResult
        If pedidosAcept_0_6 <> 0 And agrupados_0_6 <> 0 Then
            e.Result = CStr(CInt(Math.Round(((pedidosAcept_0_6 / agrupados_0_6) * 100), 0))) & "%"
        Else
            e.Result = CStr(0) & "%"
        End If
        e.Handled = True

    End Sub
    '------------------------
    ' pedidos aceptados g1
    Private Sub XrLabel174_AfterPrint(sender As Object, e As EventArgs) Handles XrLabel174.AfterPrint
        If XrLabel174.Text <> "" Then
            pedidosAcept_1_6 = CInt(XrLabel174.Text)
        End If
    End Sub
    'agrupados g1
    Private Sub XrLabel168_AfterPrint(sender As Object, e As EventArgs) Handles XrLabel168.AfterPrint
        If XrLabel168.Text <> "" Then
            agrupados_1_6 = CInt(XrLabel168.Text)
        End If
    End Sub

    'porcentaje g1
    Private Sub XrLabel173_SummaryGetResult(sender As Object, e As SummaryGetResultEventArgs) Handles XrLabel173.SummaryGetResult
        If pedidosAcept_1_6 <> 0 And agrupados_1_6 <> 0 Then
            e.Result = CStr(CInt(Math.Round(((pedidosAcept_1_6 / agrupados_1_6) * 100), 0))) & "%"
        Else
            e.Result = CStr(0) & "%"
        End If
        e.Handled = True
        Dim f As String = XrLabel39.Text
    End Sub
#End Region

#Region "MES 07"
    ' pedidos aceptados g0
    Private Sub XrLabel154_AfterPrint(sender As Object, e As EventArgs) Handles XrLabel154.AfterPrint
        If XrLabel154.Text <> "" Then
            pedidosAcept_0_7 = CInt(XrLabel154.Text)
        End If
    End Sub
    'agrupados g0
    Private Sub XrLabel195_AfterPrint(sender As Object, e As EventArgs) Handles XrLabel195.AfterPrint
        If XrLabel195.Text <> "" Then
            agrupados_0_7 = CInt(XrLabel195.Text)
        End If
    End Sub
    'porcentaje g0
    Private Sub XrLabel134_SummaryGetResult(sender As Object, e As SummaryGetResultEventArgs) Handles XrLabel134.SummaryGetResult
        If pedidosAcept_0_7 <> 0 And agrupados_0_7 <> 0 Then
            e.Result = CStr(CInt(Math.Round(((pedidosAcept_0_7 / agrupados_0_7) * 100), 0))) & "%"
        Else
            e.Result = CStr(0) & "%"
        End If
        e.Handled = True

    End Sub
    '------------------------
    ' pedidos aceptados g1
    Private Sub XrLabel182_AfterPrint(sender As Object, e As EventArgs) Handles XrLabel182.AfterPrint
        If XrLabel182.Text <> "" Then
            pedidosAcept_1_7 = CInt(XrLabel182.Text)
        End If
    End Sub
    'agrupados g1
    Private Sub XrLabel196_AfterPrint(sender As Object, e As EventArgs) Handles XrLabel196.AfterPrint
        If XrLabel196.Text <> "" Then
            agrupados_1_7 = CInt(XrLabel196.Text)
        End If
    End Sub
    'porcentaje g1
    Private Sub XrLabel179_SummaryGetResult(sender As Object, e As SummaryGetResultEventArgs) Handles XrLabel179.SummaryGetResult
        If pedidosAcept_1_7 <> 0 And agrupados_1_7 <> 0 Then
            e.Result = CStr(CInt(Math.Round(((pedidosAcept_1_7 / agrupados_1_7) * 100), 0))) & "%"
        Else
            e.Result = CStr(0) & "%"
        End If
        e.Handled = True

    End Sub
#End Region

#Region "MES 08"

#End Region
    ' pedidos aceptados g0
    Private Sub XrLabel170_AfterPrint(sender As Object, e As EventArgs) Handles XrLabel170.AfterPrint
        If XrLabel170.Text <> "" Then
            pedidosAcept_0_8 = CInt(XrLabel170.Text)
        End If
    End Sub
    'agrupados g0
    Private Sub XrLabel200_AfterPrint(sender As Object, e As EventArgs) Handles XrLabel200.AfterPrint
        If XrLabel200.Text <> "" Then
            agrupados_0_8 = CInt(XrLabel200.Text)
        End If
    End Sub
    'porcentaje g0
    Private Sub XrLabel138_SummaryGetResult(sender As Object, e As SummaryGetResultEventArgs) Handles XrLabel138.SummaryGetResult
        If pedidosAcept_0_8 <> 0 And agrupados_0_8 <> 0 Then
            e.Result = CStr(CInt(Math.Round(((pedidosAcept_0_8 / agrupados_0_8) * 100), 0))) & "%"
        Else
            e.Result = CStr(0) & "%"
        End If
        e.Handled = True

    End Sub
    '----------------------
    ' pedidos aceptados g1
    Private Sub XrLabel198_AfterPrint(sender As Object, e As EventArgs) Handles XrLabel198.AfterPrint
        If XrLabel198.Text <> "" Then
            pedidosAcept_1_8 = CInt(XrLabel198.Text)
        End If
    End Sub
    'agrupados g1
    Private Sub XrLabel201_AfterPrint(sender As Object, e As EventArgs) Handles XrLabel201.AfterPrint
        If XrLabel201.Text <> "" Then
            agrupados_1_8 = CInt(XrLabel201.Text)
        End If
    End Sub
    'porcentaje g1
    Private Sub XrLabel180_SummaryGetResult(sender As Object, e As SummaryGetResultEventArgs) Handles XrLabel180.SummaryGetResult
        If pedidosAcept_1_8 <> 0 And agrupados_1_8 <> 0 Then
            e.Result = CStr(CInt(Math.Round(((pedidosAcept_1_8 / agrupados_1_8) * 100), 0))) & "%"
        Else
            e.Result = CStr(0) & "%"
        End If
        e.Handled = True
        Dim f As String = XrLabel39.Text
    End Sub

    
