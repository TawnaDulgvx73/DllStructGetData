# DllStructGetData
Create a unique tmp file, optional path and prefix Func _CreateUniqueTmpFile($sPath = @TempDir, $sPreFix = '999')     Local Const $ERROR_PATH_LENGTH = 6      If StringLen($sPath) > 256 - 14 Then ;MAX_PATH - 14         Return SetError($ERROR_PATH_LENGTH)     EndIf      Local $Struct = DllStructCreate("char[256]") ; MAX_PATH     Local $StructPointer = DllStructGetPtr($Struct)      Local $aRtn = DllCall("Kernel32.dll", 'uint', 'GetTempFileName', 'str', $sPath, 'str', $sPreFix, 'uint', 0, 'ptr', $StructPointer)     If @error Then         Return SetError(@error)     EndIf      Return Create a unique tmp file, optional path and prefix Func _CreateUniqueTmpFile($sPath = @TempDir, $sPreFix = '999')     Local Const $ERROR_PATH_LENGTH = 6      If StringLen($sPath) > 256 - 14 Then ;MAX_PATH - 14         Return SetError($ERROR_PATH_LENGTH)     EndIf      Local $Struct = DllStructCreate("char[256]") ; MAX_PATH     Local $StructPointer = DllStructGetPtr($Struct)      Local $aRtn = DllCall("Kernel32.dll", 'uint', 'GetTempFileName', 'str', $sPath, 'str', $sPreFix, 'uint', 0, 'ptr', $StructPointer)     If @error Then         Return SetError(@error)     EndIf      Return DllStructGetData($Struct, 1) EndFunc   ;==>_CreateUniqueTmpFile($Struct, 1) EndFunc   ;==>_CreateUniqueTmpFile
