# I_CreateDir(VCARD_DATA const *,ushort const *)

- ea: `0x18002aa64`
- end: `0x18002ac4b`
- name: `?I_CreateDir@@YAKPEBUVCARD_DATA@@PEBG@Z`
- size: `487`
- prototype: `__int64 __fastcall(const struct VCARD_DATA *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180016954`

## callees

- `0x180001ec0`
- `0x18000bc48`
- `0x18000c198`
- `0x18000d368`
- `0x180015384`
- `0x180015638`
- `0x18002a230`
- `0x18002a61c`
- `0x18002a92c`
- `0x18002aa64`
- `0x1800348a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ab21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ab63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ab21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ab63`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18002ab4d`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18002ab4d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002ab17`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002ab17`

## string_xrefs

- `0x18002aa95`: `I_CreateDir`
- `0x18002abec`: `Unable to create directory`
- `0x18002ab90`: `Unable to set directory attributes`

## pseudocode

```c
__int64 __fastcall I_CreateDir(const struct VCARD_DATA *a1, const unsigned __int16 *a2)
{
  __int64 v3; // rdx
  __int64 v4; // rcx
  const WCHAR *v5; // rax
  __int64 v6; // rcx
  const WCHAR *v7; // rax
  __int64 v8; // rcx
  DWORD v9; // eax
  DWORD v10; // ebx
  DWORD LastError; // [rsp+30h] [rbp-9h] BYREF
  int v13; // [rsp+34h] [rbp-5h] BYREF
  _QWORD *v14; // [rsp+38h] [rbp-1h] BYREF
  _QWORD v15[3]; // [rsp+40h] [rbp+7h] BYREF
  _BYTE v16[32]; // [rsp+58h] [rbp+1Fh] BYREF
  char v17[16]; // [rsp+78h] [rbp+3Fh] BYREF

  LastError = 0;
  v13 = 0;
  strcpy(v17, "I_CreateDir");
  v15[0] = v17;
  v15[1] = &v13;
  v15[2] = &LastError;
  lambda_749e96c62404d74b8c0198df70f538c1_::operator()(v15, a2);
  v13 = 1;
  v14 = v15;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v4, v3);
  std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>((__int64)v16);
  I_ComposeFilePath((__int64)a1, (__int64)L"blobs\\", (__int64)&qword_18003BA28, (__int64)v16);
  v5 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  if ( !CreateDirectoryW(v5, 0) )
  {
    LastError = GetLastError();
    if ( LastError != 183 )
    {
      WppTraceIndent(v6, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sDs(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          24,
          (unsigned int)&WPP_07138201f8c239aeb1d90374442b236d_Traceguids,
          (_DWORD)WPP_pszIndent,
          LastError,
          (__int64)"Unable to create directory");
      }
      goto LABEL_16;
    }
    LastError = 0;
  }
  v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  if ( SetFileAttributesW(v7, 6u) )
  {
LABEL_16:
    v10 = LastError;
    goto LABEL_17;
  }
  WppTraceIndent(v8, 2);
  v9 = GetLastError();
  LastError = v9;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_sDs(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      25,
      (unsigned int)&WPP_07138201f8c239aeb1d90374442b236d_Traceguids,
      (_DWORD)WPP_pszIndent,
      v9,
      (__int64)"Unable to set directory attributes");
    v9 = LastError;
  }
  v10 = v9;
LABEL_17:
  std::wstring::_Tidy_deallocate((__int64)v16);
  WppTraceUnwinder__lambda_749e96c62404d74b8c0198df70f538c1____::_WppTraceUnwinder__lambda_749e96c62404d74b8c0198df70f538c1____(&v14);
  return v10;
}

```

## disassembly

```asm
0x18002aa64  mov     [rsp-8+arg_8], rbx
0x18002aa69  push    rbp
0x18002aa6a  lea     rbp, [rsp-57h]
0x18002aa6f  sub     rsp, 90h
0x18002aa76  mov     rax, cs:__security_cookie
0x18002aa7d  xor     rax, rsp
0x18002aa80  mov     [rbp+57h+var_8], rax
0x18002aa84  mov     rbx, rcx
0x18002aa87  mov     [rbp+57h+var_60], 0
0x18002aa8e  mov     [rbp+57h+var_5C], 0
0x18002aa95  movsd   xmm0, qword ptr cs:aICreatedir; "I_CreateDir"
0x18002aa9d  movsd   qword ptr [rbp+57h+var_18], xmm0
0x18002aaa2  mov     eax, dword ptr cs:aICreatedir+8; "Dir"
0x18002aaa8  mov     dword ptr [rbp+57h+var_18+8], eax
0x18002aaab  lea     rax, [rbp+57h+var_18]
0x18002aaaf  mov     [rbp+57h+var_50], rax
0x18002aab3  lea     rax, [rbp+57h+var_5C]
0x18002aab7  mov     [rbp+57h+var_48], rax
0x18002aabb  lea     rax, [rbp+57h+var_60]
0x18002aabf  mov     [rbp+57h+var_40], rax
0x18002aac3  lea     rcx, [rbp+57h+var_50]
0x18002aac7  call    _lambda_749e96c62404d74b8c0198df70f538c1___operator__
0x18002aacc  mov     [rbp+57h+var_5C], 1
0x18002aad3  lea     rax, [rbp+57h+var_50]
0x18002aad7  mov     [rbp+57h+var_58], rax
0x18002aadb  test    rbx, rbx
0x18002aade  jnz     short loc_18002AAE5
0x18002aae0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002aae5  lea     rcx, [rbp+57h+var_38]
0x18002aae9  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x18002aaee  nop
0x18002aaef  lea     r9, [rbp+57h+var_38]
0x18002aaf3  lea     r8, qword_18003BA28
0x18002aafa  lea     rdx, aBlobs; "blobs\\"
0x18002ab01  mov     rcx, rbx
0x18002ab04  call    I_ComposeFilePath
0x18002ab09  lea     rcx, [rbp+57h+var_38]
0x18002ab0d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002ab12  mov     rcx, rax; lpPathName
0x18002ab15  xor     edx, edx; lpSecurityAttributes
0x18002ab17  call    cs:__imp_CreateDirectoryW
0x18002ab1d  test    eax, eax
0x18002ab1f  jnz     short loc_18002AB3C
0x18002ab21  call    cs:__imp_GetLastError
0x18002ab27  mov     [rbp+57h+var_60], eax
0x18002ab2a  cmp     eax, 0B7h
0x18002ab2f  jnz     loc_18002ABBE
0x18002ab35  mov     [rbp+57h+var_60], 0
0x18002ab3c  lea     rcx, [rbp+57h+var_38]
0x18002ab40  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002ab45  mov     rcx, rax; lpFileName
0x18002ab48  mov     edx, 6; dwFileAttributes
0x18002ab4d  call    cs:__imp_SetFileAttributesW
0x18002ab53  test    eax, eax
0x18002ab55  jnz     loc_18002AC16
0x18002ab5b  lea     edx, [rax+2]
0x18002ab5e  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002ab63  call    cs:__imp_GetLastError
0x18002ab69  mov     [rbp+57h+var_60], eax
0x18002ab6c  lea     rdx, WPP_GLOBAL_Control
0x18002ab73  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ab7a  cmp     rcx, rdx
0x18002ab7d  jz      short loc_18002ABBA
0x18002ab7f  test    byte ptr [rcx+1Ch], 1
0x18002ab83  jz      short loc_18002ABBA
0x18002ab85  cmp     byte ptr [rcx+19h], 2
0x18002ab89  jb      short loc_18002ABBA
0x18002ab8b  mov     edx, 19h
0x18002ab90  lea     r8, aUnableToSetDir; "Unable to set directory attributes"
0x18002ab97  mov     [rsp+90h+var_68], r8
0x18002ab9c  mov     [rsp+90h+var_70], eax
0x18002aba0  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002aba7  lea     r8, WPP_07138201f8c239aeb1d90374442b236d_Traceguids
0x18002abae  mov     rcx, [rcx+10h]
0x18002abb2  call    WPP_SF_sDs
0x18002abb7  mov     eax, [rbp+57h+var_60]
0x18002abba  mov     ebx, eax
0x18002abbc  jmp     short loc_18002AC19
0x18002abbe  mov     edx, 2
0x18002abc3  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002abc8  lea     rdx, WPP_GLOBAL_Control
0x18002abcf  mov     rcx, cs:WPP_GLOBAL_Control
0x18002abd6  cmp     rcx, rdx
0x18002abd9  jz      short loc_18002AC16
0x18002abdb  test    byte ptr [rcx+1Ch], 1
0x18002abdf  jz      short loc_18002AC16
0x18002abe1  cmp     byte ptr [rcx+19h], 2
0x18002abe5  jb      short loc_18002AC16
0x18002abe7  mov     edx, 18h
0x18002abec  lea     rax, aUnableToCreate_12; "Unable to create directory"
0x18002abf3  mov     [rsp+90h+var_68], rax
0x18002abf8  mov     eax, [rbp+57h+var_60]
0x18002abfb  mov     [rsp+90h+var_70], eax
0x18002abff  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002ac06  lea     r8, WPP_07138201f8c239aeb1d90374442b236d_Traceguids
0x18002ac0d  mov     rcx, [rcx+10h]
0x18002ac11  call    WPP_SF_sDs
0x18002ac16  mov     ebx, [rbp+57h+var_60]
0x18002ac19  lea     rcx, [rbp+57h+var_38]
0x18002ac1d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ac22  nop
0x18002ac23  lea     rcx, [rbp+57h+var_58]
0x18002ac27  call    WppTraceUnwinder__lambda_749e96c62404d74b8c0198df70f538c1_______WppTraceUnwinder__lambda_749e96c62404d74b8c0198df70f538c1____
0x18002ac2c  mov     eax, ebx
0x18002ac2e  mov     rcx, [rbp+57h+var_8]
0x18002ac32  xor     rcx, rsp; StackCookie
0x18002ac35  call    __security_check_cookie
0x18002ac3a  mov     rbx, [rsp+90h+arg_8]
0x18002ac42  add     rsp, 90h
0x18002ac49  pop     rbp
0x18002ac4a  retn
```
