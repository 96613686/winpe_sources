# I_DeleteDir(VCARD_DATA const *,ushort const *)

- ea: `0x18002adec`
- end: `0x18002af3a`
- name: `?I_DeleteDir@@YAKPEBUVCARD_DATA@@PEBG@Z`
- size: `334`
- prototype: `__int64 __fastcall(const struct VCARD_DATA *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800163e8`
- `0x18001676c`

## callees

- `0x180001ec0`
- `0x18000bc48`
- `0x18000c198`
- `0x18000d368`
- `0x180015384`
- `0x180015638`
- `0x18002a1f8`
- `0x18002a550`
- `0x18002a92c`
- `0x18002adec`
- `0x1800348a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aeaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aeaf`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18002ae9d`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18002ae9d`

## string_xrefs

- `0x18002ae1d`: `I_DeleteDir`
- `0x18002aede`: `Unable to remove directory`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall I_DeleteDir(const struct VCARD_DATA *a1, const unsigned __int16 *a2)
{
  __int64 v3; // rdx
  __int64 v4; // rcx
  const WCHAR *v5; // rax
  __int64 v6; // rcx
  DWORD LastError; // ebx
  DWORD v9; // [rsp+30h] [rbp-9h] BYREF
  int v10; // [rsp+34h] [rbp-5h] BYREF
  _QWORD *v11; // [rsp+38h] [rbp-1h] BYREF
  _QWORD v12[3]; // [rsp+40h] [rbp+7h] BYREF
  _BYTE v13[32]; // [rsp+58h] [rbp+1Fh] BYREF
  char v14[16]; // [rsp+78h] [rbp+3Fh] BYREF

  v9 = 0;
  v10 = 0;
  strcpy(v14, "I_DeleteDir");
  v12[0] = v14;
  v12[1] = &v10;
  v12[2] = &v9;
  lambda_6f6cdd6a82523c215c6d5fa5617e370d_::operator()(v12, a2);
  v10 = 1;
  v11 = v12;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v4, v3);
  std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>((__int64)v13);
  I_ComposeFilePath((__int64)a1, (__int64)L"blobs\\", (__int64)&qword_18003BA28, (__int64)v13);
  v5 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  if ( RemoveDirectoryW(v5) )
    goto LABEL_8;
  WppTraceIndent(v6, 2);
  LastError = GetLastError();
  v9 = LastError;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_sDs(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      27,
      (unsigned int)&WPP_07138201f8c239aeb1d90374442b236d_Traceguids,
      (_DWORD)WPP_pszIndent,
      LastError,
      (__int64)"Unable to remove directory");
LABEL_8:
    LastError = v9;
  }
  std::wstring::_Tidy_deallocate((__int64)v13);
  WppTraceUnwinder__lambda_6f6cdd6a82523c215c6d5fa5617e370d____::_WppTraceUnwinder__lambda_6f6cdd6a82523c215c6d5fa5617e370d____(&v11);
  return LastError;
}

```

## disassembly

```asm
0x18002adec  mov     [rsp-8+arg_8], rbx
0x18002adf1  push    rbp
0x18002adf2  lea     rbp, [rsp-57h]
0x18002adf7  sub     rsp, 90h
0x18002adfe  mov     rax, cs:__security_cookie
0x18002ae05  xor     rax, rsp
0x18002ae08  mov     [rbp+57h+var_8], rax
0x18002ae0c  mov     rbx, rcx
0x18002ae0f  mov     [rbp+57h+var_60], 0
0x18002ae16  mov     [rbp+57h+var_5C], 0
0x18002ae1d  movsd   xmm0, qword ptr cs:aIDeletedir; "I_DeleteDir"
0x18002ae25  movsd   qword ptr [rbp+57h+var_18], xmm0
0x18002ae2a  mov     eax, dword ptr cs:aIDeletedir+8; "Dir"
0x18002ae30  mov     dword ptr [rbp+57h+var_18+8], eax
0x18002ae33  lea     rax, [rbp+57h+var_18]
0x18002ae37  mov     [rbp+57h+var_50], rax
0x18002ae3b  lea     rax, [rbp+57h+var_5C]
0x18002ae3f  mov     [rbp+57h+var_48], rax
0x18002ae43  lea     rax, [rbp+57h+var_60]
0x18002ae47  mov     [rbp+57h+var_40], rax
0x18002ae4b  lea     rcx, [rbp+57h+var_50]
0x18002ae4f  call    _lambda_6f6cdd6a82523c215c6d5fa5617e370d___operator__
0x18002ae54  mov     [rbp+57h+var_5C], 1
0x18002ae5b  lea     rax, [rbp+57h+var_50]
0x18002ae5f  mov     [rbp+57h+var_58], rax
0x18002ae63  test    rbx, rbx
0x18002ae66  jnz     short loc_18002AE6D
0x18002ae68  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002ae6d  lea     rcx, [rbp+57h+var_38]
0x18002ae71  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x18002ae76  nop
0x18002ae77  lea     r9, [rbp+57h+var_38]
0x18002ae7b  lea     r8, qword_18003BA28
0x18002ae82  lea     rdx, aBlobs; "blobs\\"
0x18002ae89  mov     rcx, rbx
0x18002ae8c  call    I_ComposeFilePath
0x18002ae91  lea     rcx, [rbp+57h+var_38]
0x18002ae95  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002ae9a  mov     rcx, rax; lpPathName
0x18002ae9d  call    cs:__imp_RemoveDirectoryW
0x18002aea3  test    eax, eax
0x18002aea5  jnz     short loc_18002AF05
0x18002aea7  lea     edx, [rax+2]
0x18002aeaa  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002aeaf  call    cs:__imp_GetLastError
0x18002aeb5  mov     ebx, eax
0x18002aeb7  mov     [rbp+57h+var_60], eax
0x18002aeba  lea     rax, WPP_GLOBAL_Control
0x18002aec1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aec8  cmp     rcx, rax
0x18002aecb  jz      short loc_18002AF08
0x18002aecd  test    byte ptr [rcx+1Ch], 1
0x18002aed1  jz      short loc_18002AF08
0x18002aed3  cmp     byte ptr [rcx+19h], 2
0x18002aed7  jb      short loc_18002AF08
0x18002aed9  mov     edx, 1Bh
0x18002aede  lea     rax, aUnableToRemove; "Unable to remove directory"
0x18002aee5  mov     [rsp+90h+var_68], rax
0x18002aeea  mov     [rsp+90h+var_70], ebx
0x18002aeee  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002aef5  lea     r8, WPP_07138201f8c239aeb1d90374442b236d_Traceguids
0x18002aefc  mov     rcx, [rcx+10h]
0x18002af00  call    WPP_SF_sDs
0x18002af05  mov     ebx, [rbp+57h+var_60]
0x18002af08  lea     rcx, [rbp+57h+var_38]
0x18002af0c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002af11  nop
0x18002af12  lea     rcx, [rbp+57h+var_58]
0x18002af16  call    WppTraceUnwinder__lambda_6f6cdd6a82523c215c6d5fa5617e370d_______WppTraceUnwinder__lambda_6f6cdd6a82523c215c6d5fa5617e370d____
0x18002af1b  mov     eax, ebx
0x18002af1d  mov     rcx, [rbp+57h+var_8]
0x18002af21  xor     rcx, rsp; StackCookie
0x18002af24  call    __security_check_cookie
0x18002af29  mov     rbx, [rsp+90h+arg_8]
0x18002af31  add     rsp, 90h
0x18002af38  pop     rbp
0x18002af39  retn
```
