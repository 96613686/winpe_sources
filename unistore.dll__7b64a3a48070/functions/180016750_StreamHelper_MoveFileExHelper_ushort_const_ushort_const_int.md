# StreamHelper::MoveFileExHelper(ushort const *,ushort const *,int)

- ea: `0x180016750`
- end: `0x180016a45`
- name: `?MoveFileExHelper@StreamHelper@@KAJPEBG0H@Z`
- size: `757`
- prototype: `__int64 __fastcall(LPCWSTR lpExistingFileName, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180016608`

## callees

- `0x180016750`
- `0x18001784c`
- `0x18002995c`
- `0x1800396c8`
- `0x180039898`
- `0x1800721ec`
- `0x180072eec`
- `0x1800c50f0`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18001680e`
- `msvcrt!wcsrchr` at `0x18001680e`
- `msvcrt!_wcsicmp` at `0x180016787`
- `msvcrt!_wcsicmp` at `0x180016787`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800167b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001685c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800168fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800169b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800167b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001685c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800168fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800169b7`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180016852`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180016852`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180016967`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180016967`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800167a6`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800168f2`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180016926`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180016a2d`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800167a6`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800168f2`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180016926`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180016a2d`

## pseudocode

```c
__int64 __fastcall StreamHelper::MoveFileExHelper(LPCWSTR lpExistingFileName, const unsigned __int16 *a2, int a3)
{
  int v6; // esi
  DWORD LastError; // eax
  int v8; // eax
  __int64 v9; // r8
  unsigned int v10; // edi
  wchar_t *v12; // rcx
  __int64 v13; // r8
  unsigned int v14; // ebx
  __int64 v15; // r9
  signed int v16; // eax
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v19; // rcx
  void *v20; // rax
  signed int v21; // eax
  HANDLE FileW; // rbx
  signed int v23; // eax
  void *v24; // rax
  _QWORD v25[2]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR TempFileName[264]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t Str[264]; // [rsp+270h] [rbp+170h] BYREF

  if ( !_wcsicmp(lpExistingFileName, a2) )
    return 0;
  v6 = a3 != 0 ? 2 : 0;
  if ( MoveFileExW(lpExistingFileName, a2, v6 + 1) )
    return 0;
  LastError = GetLastError();
  if ( LastError - 2 > 1 && LastError != 17 )
  {
    v8 = StringCchCopyW(Str, 0x104u, a2);
    v10 = v8;
    if ( v8 < 0 )
    {
      Log_UnistoreHREvent_17((unsigned int)v8, 1, v9, 973);
      return v10;
    }
    v12 = wcsrchr(Str, 0x5Cu);
    if ( !v12 )
    {
      v14 = -2147024809;
      v15 = 974;
LABEL_9:
      Log_UnistoreHREvent_17(v14, 0, v13, v15);
      return v14;
    }
    *v12 = 0;
    if ( !GetTempFileNameW(Str, L"OLD", 0, TempFileName) )
    {
      v16 = GetLastError();
      v14 = v16;
      if ( v16 )
      {
        if ( v16 <= 0 )
          goto LABEL_16;
      }
      else
      {
        LOWORD(v14) = 1803;
      }
      v14 = (unsigned __int16)v14 | 0x80070000;
LABEL_16:
      Log_UnistoreHREvent_17(v14, 0, v17, 988);
      if ( !v14 )
        Log_AssertionEvent_1(v19, v18, 988);
      return v14;
    }
    if ( (Microsoft_Windows_UserDataAccess_UnifiedStoreEnableBits & 0x20) != 0 )
    {
      v20 = _t_address();
      EtwTraceMessage(&ETWMESSAGE, v20, a2, -2, TempFileName, -2, 0, -1);
    }
    if ( !MoveFileExW(a2, TempFileName, 1u) )
    {
      v21 = GetLastError();
      v14 = v21;
      if ( v21 > 0 )
        v14 = (unsigned __int16)v21 | 0x80070000;
      v15 = 993;
      goto LABEL_9;
    }
    if ( MoveFileExW(lpExistingFileName, a2, v6 + 1) )
    {
      v25[0] = 0;
      FileW = CreateFileW(TempFileName, 0x40000000u, 7u, 0, 3u, 0x4000000u, 0);
      if ( FileW )
      {
        tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(v25);
        v25[0] = FileW;
      }
      tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(v25);
    }
    else
    {
      v23 = GetLastError();
      if ( v23 > 0 )
        v23 = (unsigned __int16)v23 | 0x80070000;
      LODWORD(v25[0]) = v23;
      if ( (Microsoft_Windows_UserDataAccess_UnifiedStoreEnableBits & 0x20) != 0 )
      {
        v24 = _t_address();
        EtwTraceMessage(&ETWMESSAGE, v24, lpExistingFileName, -2, a2, -2, v25, 4, 0, -1);
      }
      MoveFileExW(TempFileName, a2, 1u);
    }
    return 0;
  }
  return (unsigned __int16)LastError | 0x80070000;
}

```

## disassembly

```asm
0x180016750  mov     [rsp-8+arg_10], rbx
0x180016755  mov     [rsp-8+arg_18], rsi
0x18001675a  push    rbp
0x18001675b  push    rdi
0x18001675c  push    r14
0x18001675e  lea     rbp, [rsp-390h]
0x180016766  sub     rsp, 490h
0x18001676d  mov     rax, cs:__security_cookie
0x180016774  xor     rax, rsp
0x180016777  mov     [rbp+3A0h+var_20], rax
0x18001677e  mov     edi, r8d
0x180016781  mov     rbx, rdx
0x180016784  mov     r14, rcx
0x180016787  call    cs:__imp__wcsicmp
0x18001678d  test    eax, eax
0x18001678f  jz      loc_18001698E
0x180016795  neg     edi
0x180016797  mov     rdx, rbx; lpNewFileName
0x18001679a  mov     rcx, r14; lpExistingFileName
0x18001679d  sbb     esi, esi
0x18001679f  and     esi, 2
0x1800167a2  lea     r8d, [rsi+1]; dwFlags
0x1800167a6  call    cs:__imp_MoveFileExW
0x1800167ac  test    eax, eax
0x1800167ae  jnz     loc_18001698E
0x1800167b4  call    cs:__imp_GetLastError
0x1800167ba  lea     ecx, [rax-2]
0x1800167bd  cmp     ecx, 1
0x1800167c0  jbe     loc_180016A38
0x1800167c6  cmp     eax, 11h
0x1800167c9  jz      loc_180016A38
0x1800167cf  mov     r8, rbx; unsigned __int16 *
0x1800167d2  lea     rcx, [rbp+3A0h+Str]; unsigned __int16 *
0x1800167d9  mov     edx, 104h; unsigned __int64
0x1800167de  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800167e3  mov     edi, eax
0x1800167e5  test    eax, eax
0x1800167e7  jns     short loc_180016802
0x1800167e9  mov     edx, 1
0x1800167ee  mov     r9d, 3CDh
0x1800167f4  mov     ecx, eax
0x1800167f6  call    Log_UnistoreHREvent_17
0x1800167fb  mov     eax, edi
0x1800167fd  jmp     loc_180016990
0x180016802  mov     edx, 5Ch ; '\'; Ch
0x180016807  lea     rcx, [rbp+3A0h+Str]; Str
0x18001680e  call    cs:__imp_wcsrchr
0x180016814  mov     rcx, rax
0x180016817  test    rax, rax
0x18001681a  jnz     short loc_180016837
0x18001681c  mov     ebx, 80070057h
0x180016821  mov     r9d, 3CEh
0x180016827  xor     edx, edx
0x180016829  mov     ecx, ebx
0x18001682b  call    Log_UnistoreHREvent_17
0x180016830  mov     eax, ebx
0x180016832  jmp     loc_180016990
0x180016837  xor     eax, eax
0x180016839  lea     r9, [rsp+4A0h+TempFileName]; lpTempFileName
0x18001683e  mov     [rcx], ax
0x180016841  lea     rdx, ?c_wszTemporaryFilePrefix@@3QBGB; "OLD"
0x180016848  lea     rcx, [rbp+3A0h+Str]; lpPathName
0x18001684f  xor     r8d, r8d; uUnique
0x180016852  call    cs:__imp_GetTempFileNameW
0x180016858  test    eax, eax
0x18001685a  jnz     short loc_180016899
0x18001685c  call    cs:__imp_GetLastError
0x180016862  mov     ebx, eax
0x180016864  test    eax, eax
0x180016866  jnz     short loc_18001686F
0x180016868  mov     ebx, 70Bh
0x18001686d  jmp     short loc_180016871
0x18001686f  jle     short loc_18001687A
0x180016871  movzx   ebx, bx
0x180016874  or      ebx, 80070000h
0x18001687a  mov     edi, 3DCh
0x18001687f  xor     edx, edx
0x180016881  mov     r9d, edi
0x180016884  mov     ecx, ebx
0x180016886  call    Log_UnistoreHREvent_17
0x18001688b  test    ebx, ebx
0x18001688d  jnz     short loc_180016830
0x18001688f  mov     r8d, edi
0x180016892  call    Log_AssertionEvent_1
0x180016897  jmp     short loc_180016830
0x180016899  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UnifiedStoreEnableBits, 20h
0x1800168a0  mov     rdi, 0FFFFFFFFFFFFFFFEh
0x1800168a7  jz      short loc_1800168E4
0x1800168a9  call    ?_t_address@@YAPEAXXZ; _t_address(void)
0x1800168ae  mov     [rsp+4A0h+var_468], 0FFFFFFFFFFFFFFFFh
0x1800168b7  lea     rcx, _ETWMESSAGE; EventDescriptor
0x1800168be  mov     rdx, rax; void *
0x1800168c1  mov     [rsp+4A0h+hTemplateFile], 0
0x1800168ca  lea     rax, [rsp+4A0h+TempFileName]
0x1800168cf  mov     qword ptr [rsp+4A0h+dwFlagsAndAttributes], rdi
0x1800168d4  mov     r9, rdi
0x1800168d7  mov     qword ptr [rsp+4A0h+dwCreationDisposition], rax
0x1800168dc  mov     r8, rbx
0x1800168df  call    ?EtwTraceMessage@@YAXPEBU_EVENT_DESCRIPTOR@@PEAXZZ; EtwTraceMessage(_EVENT_DESCRIPTOR const *,void *,...)
0x1800168e4  mov     r8d, 1; dwFlags
0x1800168ea  lea     rdx, [rsp+4A0h+TempFileName]; lpNewFileName
0x1800168ef  mov     rcx, rbx; lpExistingFileName
0x1800168f2  call    cs:__imp_MoveFileExW
0x1800168f8  test    eax, eax
0x1800168fa  jnz     short loc_18001691C
0x1800168fc  call    cs:__imp_GetLastError
0x180016902  mov     ebx, eax
0x180016904  test    eax, eax
0x180016906  jle     short loc_180016911
0x180016908  movzx   ebx, ax
0x18001690b  or      ebx, 80070000h
0x180016911  mov     r9d, 3E1h
0x180016917  jmp     loc_180016827
0x18001691c  lea     r8d, [rsi+1]; dwFlags
0x180016920  mov     rdx, rbx; lpNewFileName
0x180016923  mov     rcx, r14; lpExistingFileName
0x180016926  call    cs:__imp_MoveFileExW
0x18001692c  test    eax, eax
0x18001692e  jz      loc_1800169B7
0x180016934  xor     r9d, r9d; lpSecurityAttributes
0x180016937  mov     [rsp+4A0h+hTemplateFile], 0; hTemplateFile
0x180016940  mov     [rsp+4A0h+dwFlagsAndAttributes], 4000000h; dwFlagsAndAttributes
0x180016948  lea     rcx, [rsp+4A0h+TempFileName]; lpFileName
0x18001694d  mov     edx, 40000000h; dwDesiredAccess
0x180016952  mov     [rsp+4A0h+var_450], 0
0x18001695b  mov     [rsp+4A0h+dwCreationDisposition], 3; dwCreationDisposition
0x180016963  lea     r8d, [r9+7]; dwShareMode
0x180016967  call    cs:__imp_CreateFileW
0x18001696d  mov     rbx, rax
0x180016970  test    rax, rax
0x180016973  jz      short loc_180016984
0x180016975  lea     rcx, [rsp+4A0h+var_450]
0x18001697a  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x18001697f  mov     [rsp+4A0h+var_450], rbx
0x180016984  lea     rcx, [rsp+4A0h+var_450]
0x180016989  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x18001698e  xor     eax, eax
0x180016990  mov     rcx, [rbp+3A0h+var_20]
0x180016997  xor     rcx, rsp; StackCookie
0x18001699a  call    __security_check_cookie
0x18001699f  lea     r11, [rsp+4A0h+var_10]
0x1800169a7  mov     rbx, [r11+30h]
0x1800169ab  mov     rsi, [r11+38h]
0x1800169af  mov     rsp, r11
0x1800169b2  pop     r14
0x1800169b4  pop     rdi
0x1800169b5  pop     rbp
0x1800169b6  retn
0x1800169b7  call    cs:__imp_GetLastError
0x1800169bd  test    eax, eax
0x1800169bf  jle     short loc_1800169C9
0x1800169c1  movzx   eax, ax
0x1800169c4  or      eax, 80070000h
0x1800169c9  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UnifiedStoreEnableBits, 20h
0x1800169d0  mov     dword ptr [rsp+4A0h+var_450], eax
0x1800169d4  jz      short loc_180016A1F
0x1800169d6  call    ?_t_address@@YAPEAXXZ; _t_address(void)
0x1800169db  mov     [rsp+4A0h+var_458], 0FFFFFFFFFFFFFFFFh
0x1800169e4  lea     rcx, _ETWMESSAGE; EventDescriptor
0x1800169eb  mov     [rsp+4A0h+var_460], 0
0x1800169f4  mov     rdx, rax; void *
0x1800169f7  mov     [rsp+4A0h+var_468], 4
0x180016a00  lea     rax, [rsp+4A0h+var_450]
0x180016a05  mov     [rsp+4A0h+hTemplateFile], rax
0x180016a0a  mov     r9, rdi
0x180016a0d  mov     qword ptr [rsp+4A0h+dwFlagsAndAttributes], rdi
0x180016a12  mov     r8, r14
0x180016a15  mov     qword ptr [rsp+4A0h+dwCreationDisposition], rbx
0x180016a1a  call    ?EtwTraceMessage@@YAXPEBU_EVENT_DESCRIPTOR@@PEAXZZ; EtwTraceMessage(_EVENT_DESCRIPTOR const *,void *,...)
0x180016a1f  mov     r8d, 1; dwFlags
0x180016a25  lea     rcx, [rsp+4A0h+TempFileName]; lpExistingFileName
0x180016a2a  mov     rdx, rbx; lpNewFileName
0x180016a2d  call    cs:__imp_MoveFileExW
0x180016a33  jmp     loc_18001698E
0x180016a38  movzx   eax, ax
0x180016a3b  or      eax, 80070000h
0x180016a40  jmp     loc_180016990
```
