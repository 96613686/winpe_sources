# I_DeleteFile(VCARD_DATA const *,ushort const *,ushort const *)

- ea: `0x18002af40`
- end: `0x18002b0ad`
- name: `?I_DeleteFile@@YAKPEBUVCARD_DATA@@PEBG1@Z`
- size: `365`
- prototype: `__int64 __fastcall(const struct VCARD_DATA *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000f53c`
- `0x180012074`
- `0x1800163e8`
- `0x1800167f4`
- `0x180016880`

## callees

- `0x180001ec0`
- `0x18000bc48`
- `0x18000c198`
- `0x18000d368`
- `0x180015384`
- `0x180015638`
- `0x18002a2d8`
- `0x18002a8bc`
- `0x18002a92c`
- `0x18002af40`
- `0x1800348a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b020`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b020`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002b00e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002b00e`

## string_xrefs

- `0x18002af79`: `I_DeleteFile`
- `0x18002b04f`: `Unable to delete file`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall I_DeleteFile(const struct VCARD_DATA *a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  const WCHAR *v6; // rax
  __int64 v7; // rcx
  DWORD LastError; // ebx
  DWORD v10; // [rsp+30h] [rbp-19h] BYREF
  int v11; // [rsp+34h] [rbp-15h] BYREF
  _QWORD *v12; // [rsp+38h] [rbp-11h] BYREF
  _QWORD v13[3]; // [rsp+40h] [rbp-9h] BYREF
  _BYTE v14[32]; // [rsp+58h] [rbp+Fh] BYREF
  char v15[16]; // [rsp+78h] [rbp+2Fh] BYREF

  v10 = 0;
  v11 = 0;
  strcpy(v15, "I_DeleteFile");
  v13[0] = v15;
  v13[1] = &v11;
  v13[2] = &v10;
  lambda_e1db783c5a09ea3dde9cccd5fe7df81d_::operator()(v13);
  v11 = 1;
  v12 = v13;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(v14);
  I_ComposeFilePath(a1, a2, a3, v14);
  v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v14);
  if ( DeleteFileW(v6) )
    goto LABEL_12;
  WppTraceIndent(v7, 2);
  LastError = GetLastError();
  v10 = LastError;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_sDs(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      40,
      (unsigned int)&WPP_07138201f8c239aeb1d90374442b236d_Traceguids,
      (_DWORD)WPP_pszIndent,
      LastError,
      (__int64)"Unable to delete file");
LABEL_12:
    LastError = v10;
  }
  std::wstring::_Tidy_deallocate(v14);
  WppTraceUnwinder__lambda_e1db783c5a09ea3dde9cccd5fe7df81d____::_WppTraceUnwinder__lambda_e1db783c5a09ea3dde9cccd5fe7df81d____(&v12);
  return LastError;
}

```

## disassembly

```asm
0x18002af40  mov     [rsp-8+arg_18], rbx
0x18002af45  push    rbp
0x18002af46  push    rsi
0x18002af47  push    rdi
0x18002af48  lea     rbp, [rsp-47h]
0x18002af4d  sub     rsp, 90h
0x18002af54  mov     rax, cs:__security_cookie
0x18002af5b  xor     rax, rsp
0x18002af5e  mov     [rbp+57h+var_18], rax
0x18002af62  mov     rdi, r8
0x18002af65  mov     rbx, rdx
0x18002af68  mov     rsi, rcx
0x18002af6b  mov     [rbp+57h+var_70], 0
0x18002af72  mov     [rbp+57h+var_6C], 0
0x18002af79  movsd   xmm0, qword ptr cs:aIDeletefile; "I_DeleteFile"
0x18002af81  movsd   qword ptr [rbp+57h+var_28], xmm0
0x18002af86  mov     eax, dword ptr cs:aIDeletefile+8; "File"
0x18002af8c  mov     dword ptr [rbp+57h+var_28+8], eax
0x18002af8f  mov     al, byte ptr cs:aIDeletefile+0Ch; ""
0x18002af95  mov     [rbp+57h+var_28+0Ch], al
0x18002af98  lea     rax, [rbp+57h+var_28]
0x18002af9c  mov     [rbp+57h+var_60], rax
0x18002afa0  lea     rax, [rbp+57h+var_6C]
0x18002afa4  mov     [rbp+57h+var_58], rax
0x18002afa8  lea     rax, [rbp+57h+var_70]
0x18002afac  mov     [rbp+57h+var_50], rax
0x18002afb0  lea     rcx, [rbp+57h+var_60]
0x18002afb4  call    _lambda_e1db783c5a09ea3dde9cccd5fe7df81d___operator__
0x18002afb9  mov     [rbp+57h+var_6C], 1
0x18002afc0  lea     rax, [rbp+57h+var_60]
0x18002afc4  mov     [rbp+57h+var_68], rax
0x18002afc8  test    rsi, rsi
0x18002afcb  jnz     short loc_18002AFD2
0x18002afcd  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002afd2  test    rbx, rbx
0x18002afd5  jnz     short loc_18002AFDC
0x18002afd7  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002afdc  test    rdi, rdi
0x18002afdf  jnz     short loc_18002AFE6
0x18002afe1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002afe6  lea     rcx, [rbp+57h+var_48]
0x18002afea  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x18002afef  nop
0x18002aff0  lea     r9, [rbp+57h+var_48]
0x18002aff4  mov     r8, rdi
0x18002aff7  mov     rdx, rbx
0x18002affa  mov     rcx, rsi
0x18002affd  call    I_ComposeFilePath
0x18002b002  lea     rcx, [rbp+57h+var_48]
0x18002b006  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002b00b  mov     rcx, rax; lpFileName
0x18002b00e  call    cs:__imp_DeleteFileW
0x18002b014  test    eax, eax
0x18002b016  jnz     short loc_18002B076
0x18002b018  lea     edx, [rax+2]
0x18002b01b  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002b020  call    cs:__imp_GetLastError
0x18002b026  mov     ebx, eax
0x18002b028  mov     [rbp+57h+var_70], eax
0x18002b02b  lea     rax, WPP_GLOBAL_Control
0x18002b032  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b039  cmp     rcx, rax
0x18002b03c  jz      short loc_18002B079
0x18002b03e  test    byte ptr [rcx+1Ch], 1
0x18002b042  jz      short loc_18002B079
0x18002b044  cmp     byte ptr [rcx+19h], 2
0x18002b048  jb      short loc_18002B079
0x18002b04a  mov     edx, 28h ; '('
0x18002b04f  lea     rax, aUnableToDelete_0; "Unable to delete file"
0x18002b056  mov     [rsp+0A0h+var_78], rax
0x18002b05b  mov     [rsp+0A0h+var_80], ebx
0x18002b05f  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002b066  lea     r8, WPP_07138201f8c239aeb1d90374442b236d_Traceguids
0x18002b06d  mov     rcx, [rcx+10h]
0x18002b071  call    WPP_SF_sDs
0x18002b076  mov     ebx, [rbp+57h+var_70]
0x18002b079  lea     rcx, [rbp+57h+var_48]
0x18002b07d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002b082  nop
0x18002b083  lea     rcx, [rbp+57h+var_68]
0x18002b087  call    WppTraceUnwinder__lambda_e1db783c5a09ea3dde9cccd5fe7df81d_______WppTraceUnwinder__lambda_e1db783c5a09ea3dde9cccd5fe7df81d____
0x18002b08c  mov     eax, ebx
0x18002b08e  mov     rcx, [rbp+57h+var_18]
0x18002b092  xor     rcx, rsp; StackCookie
0x18002b095  call    __security_check_cookie
0x18002b09a  mov     rbx, [rsp+0A0h+arg_18]
0x18002b0a2  add     rsp, 90h
0x18002b0a9  pop     rdi
0x18002b0aa  pop     rsi
0x18002b0ab  pop     rbp
0x18002b0ac  retn
```
