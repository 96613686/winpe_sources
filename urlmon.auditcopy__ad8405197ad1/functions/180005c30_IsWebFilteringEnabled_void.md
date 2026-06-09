# IsWebFilteringEnabled(void)

- ea: `0x180005c30`
- end: `0x180005f3e`
- name: `?IsWebFilteringEnabled@@YA_NXZ`
- size: `782`
- prototype: `char(void)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180006564`
- `0x18000713c`

## callees

- `0x1800052d8`
- `0x180005c30`
- `0x1800162d4`
- `0x18001db50`
- `0x18002fee0`
- `0x18008ad14`

## import_xrefs

- `iertutil!__imp_?GetUserSid@@YAKPEAXPEAPEAX@Z` at `0x180005cc8`
- `iertutil!__imp_?GetUserSid@@YAKPEAXPEAPEAX@Z` at `0x180005cc8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005f12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005f12`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005de4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005ebc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005de4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005ebc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005ef3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005ef3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180005c8d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180005c8d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180005ca5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180005ca5`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180005c70`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180005c70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e27`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005e07`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005e17`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005e07`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005e17`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180005ce8`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180005ce8`

## pseudocode

```c
char IsWebFilteringEnabled(void)
{
  HANDLE CurrentProcess; // rax
  signed int v2; // ebx
  LPWSTR v3; // rdx
  LPWSTR v4; // rax
  __int64 v5; // rcx
  __int64 v6; // rdi
  unsigned __int64 v7; // rsi
  void *v8; // rdi
  unsigned __int64 v9; // rsi
  const WCHAR *v10; // rdx
  PSID Sid; // [rsp+30h] [rbp-10h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-8h] BYREF
  int Data; // [rsp+70h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+40h] BYREF
  LPWSTR StringSid; // [rsp+88h] [rbp+48h] BYREF

  if ( !byte_18016B6DB )
  {
    InitOnceExecuteOnce(&stru_18016BB00, (PINIT_ONCE_FN)InitOnceDeviceFamily, 0, 0);
    if ( byte_18016AF34 && !IsOs_PhoneNT() )
      goto LABEL_20;
    TokenHandle = 0;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      goto LABEL_20;
    v2 = 0;
    Sid = 0;
    if ( GetUserSid(TokenHandle, &Sid) )
    {
LABEL_19:
      CloseHandle(TokenHandle);
      if ( v2 < 0 )
        return byte_18016B6DA;
LABEL_20:
      byte_18016B6DB = 1;
      return byte_18016B6DA;
    }
    StringSid = 0;
    if ( !ConvertSidToStringSidW(Sid, &StringSid) )
    {
LABEL_18:
      LocalFree(Sid);
      goto LABEL_19;
    }
    v3 = StringSid;
    if ( !StringSid )
    {
      v2 = -2147024809;
      goto LABEL_17;
    }
    v4 = StringSid;
    v5 = 0x7FFFFFFF;
    do
    {
      if ( !*v4 )
        break;
      ++v4;
      --v5;
    }
    while ( v5 );
    v2 = v5 == 0 ? 0x80070057 : 0;
    v6 = (0x7FFFFFFF - v5) & -(__int64)(v5 != 0);
    if ( !v5 )
      goto LABEL_17;
    hKey = 0;
    Data = 0;
    cbData = 4;
    if ( IsOs_Win8OrGreater() )
    {
      v7 = v6 + 72;
      v8 = operator new(saturated_mul(v6 + 73, 2u));
      if ( !v8
        || (v2 = StringCchPrintfW(
                   (unsigned __int16 *)v8,
                   v7,
                   L"%s%s%s",
                   L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Parental Controls\\users\\",
                   StringSid,
                   L"\\Web"),
            v2 < 0)
        || RegOpenKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)v8, 0, 0x101u, &hKey) )
      {
LABEL_16:
        operator delete(v8);
        v3 = StringSid;
LABEL_17:
        LocalFree(v3);
        goto LABEL_18;
      }
      v10 = L"Filter On";
    }
    else
    {
      v9 = v6 + 67;
      v8 = operator new(saturated_mul(v6 + 68, 2u));
      if ( !v8 )
        goto LABEL_16;
      v2 = StringCchPrintfW(
             (unsigned __int16 *)v8,
             v9,
             L"%s%s",
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Parental Controls\\users\\",
             StringSid);
      if ( v2 < 0 || RegOpenKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)v8, 0, 0x101u, &hKey) )
        goto LABEL_16;
      v10 = L"Parental Controls On";
    }
    if ( !RegQueryValueExW(hKey, v10, 0, 0, (LPBYTE)&Data, &cbData) )
      byte_18016B6DA = Data != 0;
    RegCloseKey(hKey);
    goto LABEL_16;
  }
  return byte_18016B6DA;
}

```

## disassembly

```asm
0x180005c30  push    rbp
0x180005c32  push    rbx
0x180005c33  push    rsi
0x180005c34  push    rdi
0x180005c35  push    r14
0x180005c37  mov     rbp, rsp
0x180005c3a  sub     rsp, 40h
0x180005c3e  xor     r14d, r14d
0x180005c41  cmp     cs:byte_18016B6DB, r14b
0x180005c48  jz      short loc_180005C5C
0x180005c4a  mov     al, cs:byte_18016B6DA
0x180005c50  add     rsp, 40h
0x180005c54  pop     r14
0x180005c56  pop     rdi
0x180005c57  pop     rsi
0x180005c58  pop     rbx
0x180005c59  pop     rbp
0x180005c5a  retn
0x180005c5c  xor     r9d, r9d; Context
0x180005c5f  lea     rdx, ?InitOnceDeviceFamily@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180005c66  xor     r8d, r8d; Parameter
0x180005c69  lea     rcx, stru_18016BB00; InitOnce
0x180005c70  call    cs:__imp_InitOnceExecuteOnce
0x180005c77  nop     dword ptr [rax+rax+00h]
0x180005c7c  cmp     cs:byte_18016AF34, r14b
0x180005c83  jnz     loc_180005F23
0x180005c89  mov     [rbp+TokenHandle], r14
0x180005c8d  call    cs:__imp_GetCurrentProcess
0x180005c94  nop     dword ptr [rax+rax+00h]
0x180005c99  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180005c9d  mov     edx, 8; DesiredAccess
0x180005ca2  mov     rcx, rax; ProcessHandle
0x180005ca5  call    cs:__imp_OpenProcessToken
0x180005cac  nop     dword ptr [rax+rax+00h]
0x180005cb1  test    eax, eax
0x180005cb3  jz      loc_180005E3B
0x180005cb9  mov     rcx, [rbp+TokenHandle]
0x180005cbd  lea     rdx, [rbp+Sid]
0x180005cc1  mov     ebx, r14d
0x180005cc4  mov     [rbp+Sid], r14
0x180005cc8  call    cs:__imp_?GetUserSid@@YAKPEAXPEAPEAX@Z; GetUserSid(void *,void * *)
0x180005ccf  nop     dword ptr [rax+rax+00h]
0x180005cd4  test    eax, eax
0x180005cd6  jnz     loc_180005E23
0x180005cdc  mov     rcx, [rbp+Sid]; Sid
0x180005ce0  lea     rdx, [rbp+StringSid]; StringSid
0x180005ce4  mov     [rbp+StringSid], r14
0x180005ce8  call    cs:__imp_ConvertSidToStringSidW
0x180005cef  nop     dword ptr [rax+rax+00h]
0x180005cf4  test    eax, eax
0x180005cf6  jz      loc_180005E13
0x180005cfc  mov     rdx, [rbp+StringSid]
0x180005d00  test    rdx, rdx
0x180005d03  jz      loc_180005E47
0x180005d09  mov     r8d, 7FFFFFFFh
0x180005d0f  mov     rax, rdx
0x180005d12  mov     ecx, r8d
0x180005d15  cmp     [rax], r14w
0x180005d19  jz      short loc_180005D25
0x180005d1b  add     rax, 2
0x180005d1f  sub     rcx, 1
0x180005d23  jnz     short loc_180005D15
0x180005d25  mov     rax, rcx
0x180005d28  neg     rax
0x180005d2b  mov     rax, rcx
0x180005d2e  sbb     ebx, ebx
0x180005d30  sub     r8, rcx
0x180005d33  not     ebx
0x180005d35  and     ebx, 80070057h
0x180005d3b  neg     rax
0x180005d3e  sbb     rdi, rdi
0x180005d41  and     rdi, r8
0x180005d44  test    rcx, rcx
0x180005d47  jz      loc_180005E04
0x180005d4d  mov     [rbp+hKey], r14
0x180005d51  mov     [rbp+Data], r14d
0x180005d55  mov     [rbp+cbData], 4
0x180005d5c  call    ?IsOs_Win8OrGreater@@YA_NXZ; IsOs_Win8OrGreater(void)
0x180005d61  test    al, al
0x180005d63  mov     eax, 2
0x180005d68  jz      loc_180005E4E
0x180005d6e  lea     rsi, [rdi+48h]
0x180005d72  lea     rcx, [rsi+1]
0x180005d76  mul     rcx
0x180005d79  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180005d80  cmovb   rax, rcx
0x180005d84  mov     rcx, rax; Size
0x180005d87  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005d8c  mov     rdi, rax
0x180005d8f  test    rax, rax
0x180005d92  jz      short loc_180005DF8
0x180005d94  mov     rcx, [rbp+StringSid]
0x180005d98  lea     rax, aWeb; "\\Web"
0x180005d9f  mov     [rsp+40h+lpcbData], rax
0x180005da4  lea     r9, aSoftwareMicros_104; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180005dab  mov     [rsp+40h+phkResult], rcx
0x180005db0  lea     r8, aSSS; "%s%s%s"
0x180005db7  mov     rcx, rdi; unsigned __int16 *
0x180005dba  mov     rdx, rsi; unsigned __int64
0x180005dbd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005dc2  mov     ebx, eax
0x180005dc4  test    eax, eax
0x180005dc6  js      short loc_180005DF8
0x180005dc8  lea     rax, [rbp+hKey]
0x180005dcc  mov     r9d, 101h; samDesired
0x180005dd2  xor     r8d, r8d; ulOptions
0x180005dd5  mov     [rsp+40h+phkResult], rax; phkResult
0x180005dda  mov     rdx, rdi; lpSubKey
0x180005ddd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180005de4  call    cs:__imp_RegOpenKeyExW
0x180005deb  nop     dword ptr [rax+rax+00h]
0x180005df0  test    eax, eax
0x180005df2  jz      loc_180005F35
0x180005df8  mov     rcx, rdi; void *
0x180005dfb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005e00  mov     rdx, [rbp+StringSid]
0x180005e04  mov     rcx, rdx; hMem
0x180005e07  call    cs:__imp_LocalFree
0x180005e0e  nop     dword ptr [rax+rax+00h]
0x180005e13  mov     rcx, [rbp+Sid]; hMem
0x180005e17  call    cs:__imp_LocalFree
0x180005e1e  nop     dword ptr [rax+rax+00h]
0x180005e23  mov     rcx, [rbp+TokenHandle]; hObject
0x180005e27  call    cs:__imp_CloseHandle
0x180005e2e  nop     dword ptr [rax+rax+00h]
0x180005e33  test    ebx, ebx
0x180005e35  js      loc_180005C4A
0x180005e3b  mov     cs:byte_18016B6DB, 1
0x180005e42  jmp     loc_180005C4A
0x180005e47  mov     ebx, 80070057h
0x180005e4c  jmp     short loc_180005E04
0x180005e4e  lea     rsi, [rdi+43h]
0x180005e52  lea     rcx, [rsi+1]
0x180005e56  mul     rcx
0x180005e59  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180005e60  cmovb   rax, rcx
0x180005e64  mov     rcx, rax; Size
0x180005e67  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005e6c  mov     rdi, rax
0x180005e6f  test    rax, rax
0x180005e72  jz      short loc_180005DF8
0x180005e74  mov     rax, [rbp+StringSid]
0x180005e78  lea     r9, aSoftwareMicros_104; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180005e7f  lea     r8, aSS_3; "%s%s"
0x180005e86  mov     [rsp+40h+phkResult], rax
0x180005e8b  mov     rdx, rsi; unsigned __int64
0x180005e8e  mov     rcx, rdi; unsigned __int16 *
0x180005e91  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005e96  mov     ebx, eax
0x180005e98  test    eax, eax
0x180005e9a  js      loc_180005DF8
0x180005ea0  lea     rax, [rbp+hKey]
0x180005ea4  mov     r9d, 101h; samDesired
0x180005eaa  xor     r8d, r8d; ulOptions
0x180005ead  mov     [rsp+40h+phkResult], rax; phkResult
0x180005eb2  mov     rdx, rdi; lpSubKey
0x180005eb5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180005ebc  call    cs:__imp_RegOpenKeyExW
0x180005ec3  nop     dword ptr [rax+rax+00h]
0x180005ec8  test    eax, eax
0x180005eca  jnz     loc_180005DF8
0x180005ed0  lea     rdx, aParentalContro; "Parental Controls On"
0x180005ed7  mov     rcx, [rbp+hKey]; hKey
0x180005edb  lea     rax, [rbp+cbData]
0x180005edf  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180005ee4  xor     r9d, r9d; lpType
0x180005ee7  lea     rax, [rbp+Data]
0x180005eeb  xor     r8d, r8d; lpReserved
0x180005eee  mov     [rsp+40h+phkResult], rax; lpData
0x180005ef3  call    cs:__imp_RegQueryValueExW
0x180005efa  nop     dword ptr [rax+rax+00h]
0x180005eff  test    eax, eax
0x180005f01  jnz     short loc_180005F0E
0x180005f03  cmp     [rbp+Data], r14d
0x180005f07  setnz   cs:byte_18016B6DA
0x180005f0e  mov     rcx, [rbp+hKey]; hKey
0x180005f12  call    cs:__imp_RegCloseKey
0x180005f19  nop     dword ptr [rax+rax+00h]
0x180005f1e  jmp     loc_180005DF8
0x180005f23  call    ?IsOs_PhoneNT@@YA_NXZ; IsOs_PhoneNT(void)
0x180005f28  test    al, al
0x180005f2a  jz      loc_180005E3B
0x180005f30  jmp     loc_180005C89
0x180005f35  lea     rdx, aFilterOn; "Filter On"
0x180005f3c  jmp     short loc_180005ED7
```
