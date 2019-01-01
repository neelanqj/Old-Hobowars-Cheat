<Global.Microsoft.VisualBasic.CompilerSe
rvices.DesignerGenerated()> _
Partial Class frm_Form
Inherits System.Windows.Forms.Form

'Form overrides dispose to clean up the component list.
<System.Diagnostics.DebuggerNonUserCode()> _
Protected Overrides Sub Dispose(ByVal disposing As Boolean)
If disposing AndAlso components IsNot Nothing Then
components.Dispose()
End If
MyBase.Dispose(disposing)
End Sub

'Required by the Windows Form Designer
Private components As System.ComponentModel.IContainer

'NOTE: The following procedure is required by the Windows Form Designer
'It can be modified using the Windows Form Designer. 
'Do not modify it using the code editor.
<System.Diagnostics.DebuggerStepThrough()> _
Private Sub InitializeComponent()
Dim resources As System.ComponentModel.ComponentResourceManager = New System.ComponentModel.ComponentResourceManager(GetType(frm_Form))
Me.btn_Start = New System.Windows.Forms.Button
Me.SuspendLayout()
'
'btn_Start
'
Me.btn_Start.Location = New System.Drawing.Point(12, 12)
Me.btn_Start.Name = "btn_Start"
Me.btn_Start.Size = New System.Drawing.Size(203, 100)
Me.btn_Start.TabIndex = 0
Me.btn_Start.Text = "Start Enter Click Pattern"
Me.btn_Start.UseVisualStyleBackColor = True
'
'frm_Form
'
Me.AutoScaleDimensions = New System.Drawing.SizeF(6.0!, 13.0!)
Me.AutoScaleMode = System.Windows.Forms.AutoScaleMode.Font
Me.BackgroundImage = CType(resources.GetObject("$this.BackgroundImage"), System.Drawing.Image)
Me.ClientSize = New System.Drawing.Size(727, 413)
Me.Controls.Add(Me.btn_Start)
Me.Name = "frm_Form"
Me.Text = "Neelan's Hobo Level Up Program"
Me.ResumeLayout(False)

End Sub
Friend WithEvents btn_Start As System.Windows.Forms.Button

Declare Auto Function mouse_event Lib "user32.dll" (ByVal dwflags As Integer, ByVal dx As Integer, ByVal dy As Integer, ByVal dwData As Integer, ByVal dwExtraInfo As Integer) As Integer
Public Declare Function SetCursorPos Lib "user32" (ByVal X As Integer, ByVal Y As Integer) As Integer

Private Declare Sub keybd_event Lib "user32" (ByVal bVk As Byte, ByVal bScan As Byte, ByVal dwFlags As Integer, ByVal dwExtraInfo As Integer)

Private Const KEYEVENTF_KEYUP As Short = &H2S
Private Const KEYEVENTF_EXTENDEDKEY As Short = &H1S

Private Sub btn_Start_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles btn_Start.Click
btn_Start.Text = "Hello"
Dim vKey As Keys

While True
SetCursorPos(800, 70)
System.Threading.Thread.Sleep(500)
mouse_event(&H8, 800, 65, 0, 0)
System.Threading.Thread.Sleep(500)
mouse_event(&H8, 800, 65, 0, 0)
System.Threading.Thread.Sleep(500)
keybd_event(vKey.Enter, 0, KEYEVENTF_EXTENDEDKEY, 0)
keybd_event(vKey.Enter, 0, KEYEVENTF_EXTENDEDKEY Or KEYEVENTF_KEYUP, 0)

System.Threading.Thread.Sleep(2 * 60 * 1000)
End While
End Sub

End Class