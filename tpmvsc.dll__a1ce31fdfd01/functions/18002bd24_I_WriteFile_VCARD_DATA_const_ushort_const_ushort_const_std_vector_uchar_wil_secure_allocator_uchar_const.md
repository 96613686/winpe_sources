# I_WriteFile(VCARD_DATA const *,ushort const *,ushort const *,std::vector<uchar,wil::secure_allocator<uchar>> const &)

- ea: `0x18002bd24`
- end: `0x18002c00b`
- name: `?I_WriteFile@@YAKPEBUVCARD_DATA@@PEBG1AEBV?$vector@EU?$secure_allocator@E@wil@@@std@@@Z`
- size: `743`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002c014`

## callees

- `0x180001ec0`
- `0x18000bc48`
- `0x18000c198`
- `0x18000d368`
- `0x180015384`
- `0x180015638`
- `0x1800258f4`
- `0x18002a268`
- `0x18002a6fc`
- `0x18002a92c`
- `0x18002bd24`
- `0x18002c1c0`
- `0x1800348a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002be3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bed5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002be3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bed5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002be24`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002be24`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002bec4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002bec4`
- `ntdll!NtFlushBuffersFileEx` at `0x18002bf83`
- `ntdll!NtFlushBuffersFileEx` at `0x18002bf83`

## string_xrefs

- `0x18002bd5f`: `I_WriteFile`
- `0x18002be77`: `Unable to open file for write`
- `0x18002bf10`: `Unable to write file`
- `0x18002bf5e`: `Unable to write the whole file`

## pseudocode

```c
__int64 __fastcall I_WriteFile(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rdx
  __int64 v9; // rcx
  const WCHAR *v10; // rax
  HANDLE FileW; // rax
  __int64 v12; // rcx
  HANDLE v13; // rbx
  DWORD LastError; // ebx
  _QWORD *v15; // rcx
  int v16; // edx
  const char *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rcx
  char v22; // bl
  int v23; // edx
  int v24; // r8d
  int v25; // r9d
  int v27; // [rsp+40h] [rbp-49h] BYREF
  int v28; // [rsp+44h] [rbp-45h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+48h] [rbp-41h] BYREF
  HANDLE v30; // [rsp+50h] [rbp-39h] BYREF
  _QWORD *v31; // [rsp+58h] [rbp-31h] BYREF
  __int128 v32; // [rsp+60h] [rbp-29h] BYREF
  _QWORD v33[3]; // [rsp+70h] [rbp-19h] BYREF
  _BYTE v34[32]; // [rsp+88h] [rbp-1h] BYREF
  char v35[16]; // [rsp+A8h] [rbp+1Fh] BYREF

  v27 = 0;
  v28 = 0;
  strcpy(v35, "I_WriteFile");
  v33[0] = v35;
  v33[1] = &v28;
  v33[2] = &v27;
  lambda_8a5043b22fa4b4ebf43c18b0f904c462_::operator()(v33);
  v28 = 1;
  v31 = v33;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, v8);
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, v8);
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, v8);
  if ( *(_QWORD *)(a4 + 8) - *(_QWORD *)a4 > 0x100000u )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, v8);
  std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(v34);
  I_ComposeFilePath(a1, a2, a3, (__int64)v34);
  v10 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v34);
  FileW = CreateFileW(v10, 0x40000000u, 0, 0, 2u, 6u, 0);
  v13 = FileW;
  v30 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    WppTraceIndent(v12, 2);
    LastError = GetLastError();
    v27 = LastError;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = 35;
      v17 = "Unable to open file for write";
LABEL_14:
      WPP_SF_sDs(
        v15[2],
        v16,
        (unsigned int)&WPP_07138201f8c239aeb1d90374442b236d_Traceguids,
        (_DWORD)WPP_pszIndent,
        LastError,
        (__int64)v17);
LABEL_31:
      LastError = v27;
    }
  }
  else
  {
    NumberOfBytesWritten = 0;
    if ( WriteFile(FileW, *(LPCVOID *)a4, *(_DWORD *)(a4 + 8) - *(_DWORD *)a4, &NumberOfBytesWritten, 0) )
    {
      v19 = *(_QWORD *)(a4 + 8) - *(_QWORD *)a4;
      if ( v19 == NumberOfBytesWritten )
      {
        v32 = 0;
        v20 = NtFlushBuffersFileEx(v13, 2, 0, 0, &v32);
        v22 = v20;
        if ( v20 < 0 || (int)v32 < 0 )
        {
          WppTraceIndent(v21, 2);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            WPP_SF_sdd(*((_QWORD *)WPP_GLOBAL_Control + 2), v23, v24, v25, v22, v32);
          }
        }
        goto LABEL_31;
      }
      WppTraceIndent(v19, 2);
      LastError = 29;
      v27 = 29;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v16 = 37;
        v17 = "Unable to write the whole file";
        goto LABEL_14;
      }
    }
    else
    {
      WppTraceIndent(v18, 2);
      LastError = GetLastError();
      v27 = LastError;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v16 = 36;
        v17 = "Unable to write file";
        goto LABEL_14;
      }
    }
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v30);
  std::wstring::_Tidy_deallocate(v34);
  WppTraceUnwinder__lambda_8a5043b22fa4b4ebf43c18b0f904c462____::_WppTraceUnwinder__lambda_8a5043b22fa4b4ebf43c18b0f904c462____(&v31);
  return LastError;
}

```

## disassembly

```asm
0x18002bd24  push    rbp
0x18002bd26  push    rbx
0x18002bd27  push    rsi
0x18002bd28  push    rdi
0x18002bd29  push    r14
0x18002bd2b  lea     rbp, [rsp-37h]
0x18002bd30  sub     rsp, 0C0h
0x18002bd37  mov     rax, cs:__security_cookie
0x18002bd3e  xor     rax, rsp
0x18002bd41  mov     [rbp+57h+var_28], rax
0x18002bd45  mov     rdi, r9
0x18002bd48  mov     rsi, r8
0x18002bd4b  mov     rbx, rdx
0x18002bd4e  mov     r14, rcx
0x18002bd51  mov     [rbp+57h+var_A0], 0
0x18002bd58  mov     [rbp+57h+var_9C], 0
0x18002bd5f  movsd   xmm0, qword ptr cs:aIWritefile; "I_WriteFile"
0x18002bd67  movsd   qword ptr [rbp+57h+var_38], xmm0
0x18002bd6c  mov     eax, dword ptr cs:aIWritefile+8; "ile"
0x18002bd72  mov     dword ptr [rbp+57h+var_38+8], eax
0x18002bd75  lea     rax, [rbp+57h+var_38]
0x18002bd79  mov     [rbp+57h+var_70], rax
0x18002bd7d  lea     rax, [rbp+57h+var_9C]
0x18002bd81  mov     [rbp+57h+var_68], rax
0x18002bd85  lea     rax, [rbp+57h+var_A0]
0x18002bd89  mov     [rbp+57h+var_60], rax
0x18002bd8d  lea     rcx, [rbp+57h+var_70]
0x18002bd91  call    _lambda_8a5043b22fa4b4ebf43c18b0f904c462___operator__
0x18002bd96  mov     [rbp+57h+var_9C], 1
0x18002bd9d  lea     rax, [rbp+57h+var_70]
0x18002bda1  mov     [rbp+57h+var_88], rax
0x18002bda5  test    r14, r14
0x18002bda8  jnz     short loc_18002BDAF
0x18002bdaa  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002bdaf  test    rbx, rbx
0x18002bdb2  jnz     short loc_18002BDB9
0x18002bdb4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002bdb9  test    rsi, rsi
0x18002bdbc  jnz     short loc_18002BDC3
0x18002bdbe  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002bdc3  mov     rax, [rdi+8]
0x18002bdc7  sub     rax, [rdi]
0x18002bdca  cmp     rax, 100000h
0x18002bdd0  jbe     short loc_18002BDD7
0x18002bdd2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002bdd7  lea     rcx, [rbp+57h+var_58]
0x18002bddb  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x18002bde0  nop
0x18002bde1  lea     r9, [rbp+57h+var_58]
0x18002bde5  mov     r8, rsi
0x18002bde8  mov     rdx, rbx
0x18002bdeb  mov     rcx, r14
0x18002bdee  call    I_ComposeFilePath
0x18002bdf3  lea     rcx, [rbp+57h+var_58]
0x18002bdf7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002bdfc  mov     rcx, rax; lpFileName
0x18002bdff  mov     [rsp+0E0h+hTemplateFile], 0; hTemplateFile
0x18002be08  mov     [rsp+0E0h+dwFlagsAndAttributes], 6; dwFlagsAndAttributes
0x18002be10  mov     esi, 2
0x18002be15  mov     [rsp+0E0h+dwCreationDisposition], esi; dwCreationDisposition
0x18002be19  xor     r9d, r9d; lpSecurityAttributes
0x18002be1c  xor     r8d, r8d; dwShareMode
0x18002be1f  mov     edx, 40000000h; dwDesiredAccess
0x18002be24  call    cs:__imp_CreateFileW
0x18002be2a  mov     rbx, rax
0x18002be2d  mov     [rbp+57h+var_90], rax
0x18002be31  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002be35  jnz     short loc_18002BEA3
0x18002be37  mov     edx, esi
0x18002be39  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002be3e  call    cs:__imp_GetLastError
0x18002be44  mov     ebx, eax
0x18002be46  mov     [rbp+57h+var_A0], eax
0x18002be49  lea     rax, WPP_GLOBAL_Control
0x18002be50  mov     rcx, cs:WPP_GLOBAL_Control
0x18002be57  cmp     rcx, rax
0x18002be5a  jz      loc_18002BFD2
0x18002be60  test    byte ptr [rcx+1Ch], 1
0x18002be64  jz      loc_18002BFD2
0x18002be6a  cmp     [rcx+19h], sil
0x18002be6e  jb      loc_18002BFD2
0x18002be74  lea     edx, [rsi+21h]
0x18002be77  lea     rax, aUnableToOpenFi; "Unable to open file for write"
0x18002be7e  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rax
0x18002be83  mov     [rsp+0E0h+dwCreationDisposition], ebx
0x18002be87  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002be8e  lea     r8, WPP_07138201f8c239aeb1d90374442b236d_Traceguids
0x18002be95  mov     rcx, [rcx+10h]
0x18002be99  call    WPP_SF_sDs
0x18002be9e  jmp     loc_18002BFCF
0x18002bea3  mov     [rbp+57h+NumberOfBytesWritten], 0
0x18002beaa  mov     r8d, [rdi+8]
0x18002beae  sub     r8d, [rdi]; nNumberOfBytesToWrite
0x18002beb1  mov     qword ptr [rsp+0E0h+dwCreationDisposition], 0; lpOverlapped
0x18002beba  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002bebe  mov     rdx, [rdi]; lpBuffer
0x18002bec1  mov     rcx, rbx; hFile
0x18002bec4  call    cs:__imp_WriteFile
0x18002beca  mov     edx, esi
0x18002becc  test    eax, eax
0x18002bece  jnz     short loc_18002BF1C
0x18002bed0  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002bed5  call    cs:__imp_GetLastError
0x18002bedb  mov     ebx, eax
0x18002bedd  mov     [rbp+57h+var_A0], eax
0x18002bee0  lea     rax, WPP_GLOBAL_Control
0x18002bee7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002beee  cmp     rcx, rax
0x18002bef1  jz      loc_18002BFD2
0x18002bef7  test    byte ptr [rcx+1Ch], 1
0x18002befb  jz      loc_18002BFD2
0x18002bf01  cmp     [rcx+19h], sil
0x18002bf05  jb      loc_18002BFD2
0x18002bf0b  mov     edx, 24h ; '$'
0x18002bf10  lea     rax, aUnableToWriteF; "Unable to write file"
0x18002bf17  jmp     loc_18002BE7E
0x18002bf1c  mov     rcx, [rdi+8]
0x18002bf20  sub     rcx, [rdi]
0x18002bf23  mov     eax, [rbp+57h+NumberOfBytesWritten]
0x18002bf26  cmp     rcx, rax
0x18002bf29  jz      short loc_18002BF6A
0x18002bf2b  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002bf30  mov     ebx, 1Dh
0x18002bf35  mov     [rbp+57h+var_A0], ebx
0x18002bf38  lea     rax, WPP_GLOBAL_Control
0x18002bf3f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bf46  cmp     rcx, rax
0x18002bf49  jz      loc_18002BFD2
0x18002bf4f  test    byte ptr [rcx+1Ch], 1
0x18002bf53  jz      short loc_18002BFD2
0x18002bf55  cmp     [rcx+19h], sil
0x18002bf59  jb      short loc_18002BFD2
0x18002bf5b  lea     edx, [rbx+8]
0x18002bf5e  lea     rax, aUnableToWriteT; "Unable to write the whole file"
0x18002bf65  jmp     loc_18002BE7E
0x18002bf6a  xorps   xmm0, xmm0
0x18002bf6d  movups  [rbp+57h+var_80], xmm0
0x18002bf71  lea     rax, [rbp+57h+var_80]
0x18002bf75  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rax
0x18002bf7a  xor     r9d, r9d
0x18002bf7d  xor     r8d, r8d
0x18002bf80  mov     rcx, rbx
0x18002bf83  call    cs:__imp_NtFlushBuffersFileEx
0x18002bf89  mov     ebx, eax
0x18002bf8b  test    eax, eax
0x18002bf8d  js      short loc_18002BF95
0x18002bf8f  cmp     dword ptr [rbp+57h+var_80], 0
0x18002bf93  jge     short loc_18002BFCF
0x18002bf95  mov     edx, esi
0x18002bf97  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002bf9c  lea     rax, WPP_GLOBAL_Control
0x18002bfa3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bfaa  cmp     rcx, rax
0x18002bfad  jz      short loc_18002BFCF
0x18002bfaf  test    byte ptr [rcx+1Ch], 1
0x18002bfb3  jz      short loc_18002BFCF
0x18002bfb5  cmp     byte ptr [rcx+19h], 3
0x18002bfb9  jb      short loc_18002BFCF
0x18002bfbb  mov     eax, dword ptr [rbp+57h+var_80]
0x18002bfbe  mov     [rsp+0E0h+dwFlagsAndAttributes], eax
0x18002bfc2  mov     [rsp+0E0h+dwCreationDisposition], ebx
0x18002bfc6  mov     rcx, [rcx+10h]
0x18002bfca  call    WPP_SF_sdd
0x18002bfcf  mov     ebx, [rbp+57h+var_A0]
0x18002bfd2  lea     rcx, [rbp+57h+var_90]
0x18002bfd6  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002bfdb  nop
0x18002bfdc  lea     rcx, [rbp+57h+var_58]
0x18002bfe0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002bfe5  nop
0x18002bfe6  lea     rcx, [rbp+57h+var_88]
0x18002bfea  call    WppTraceUnwinder__lambda_8a5043b22fa4b4ebf43c18b0f904c462_______WppTraceUnwinder__lambda_8a5043b22fa4b4ebf43c18b0f904c462____
0x18002bfef  mov     eax, ebx
0x18002bff1  mov     rcx, [rbp+57h+var_28]
0x18002bff5  xor     rcx, rsp; StackCookie
0x18002bff8  call    __security_check_cookie
0x18002bffd  add     rsp, 0C0h
0x18002c004  pop     r14
0x18002c006  pop     rdi
0x18002c007  pop     rsi
0x18002c008  pop     rbx
0x18002c009  pop     rbp
0x18002c00a  retn
```
