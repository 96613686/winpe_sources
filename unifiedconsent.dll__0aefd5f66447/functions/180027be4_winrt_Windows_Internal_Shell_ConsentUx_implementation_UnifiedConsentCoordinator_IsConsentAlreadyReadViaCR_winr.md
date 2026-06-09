# winrt::Windows::Internal::Shell::ConsentUx::implementation::UnifiedConsentCoordinator::IsConsentAlreadyReadViaCR(winrt::hstring,bool &)

- ea: `0x180027be4`
- end: `0x180027f3c`
- name: `?IsConsentAlreadyReadViaCR@UnifiedConsentCoordinator@implementation@ConsentUx@Shell@Internal@Windows@winrt@@AEAA_NUhstring@7@AEA_N@Z`
- size: `856`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002aae0`

## callees

- `0x1800034f7`
- `0x1800035ab`
- `0x18000ebfc`
- `0x18000f44c`
- `0x180018290`
- `0x1800237d0`
- `0x180027be4`
- `0x1800293b4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180027e3c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180027e4b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180027e5a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180027ead`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180027f2a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180027f35`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180027e3c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180027e4b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180027e5a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180027ead`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180027f2a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180027f35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027db6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027db6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027dc9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027dc9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027c97`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027e00`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027c97`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027e00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027dc1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027e72`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027ee2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027dc1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027e72`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027ee2`

## string_xrefs

- `0x180027c28`: `triggeredCRRead`
- `0x180027c49`: `Consent is already read via CR.`
- `0x180027c58`: `Ensuring values in registry.`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
char __fastcall winrt::Windows::Internal::Shell::ConsentUx::implementation::UnifiedConsentCoordinator::IsConsentAlreadyReadViaCR(
        HKEY a1,
        volatile signed __int32 **a2,
        _BYTE *a3)
{
  const WCHAR *v5; // r14
  const unsigned __int16 *v6; // rdx
  const WCHAR *v7; // rdx
  unsigned int v8; // edx
  volatile signed __int32 *v9; // r15
  unsigned int v10; // edx
  volatile signed __int32 *v11; // rbx
  __int64 v12; // rax
  void *v13; // r12
  int v14; // eax
  HANDLE ProcessHeap; // rax
  int v16; // eax
  HANDLE v17; // rax
  int v18; // eax
  HANDLE v19; // rax
  HKEY v20; // r15
  DWORD LastError; // ebx
  volatile signed __int32 *v22; // rbx
  int v23; // eax
  HANDLE v24; // rax
  volatile signed __int32 *v25; // rbx
  int v26; // edi
  HANDLE v27; // rax
  int v29; // eax
  HANDLE v30; // rax
  volatile signed __int32 *v31; // rbx
  int v32; // edi
  HANDLE v33; // rax
  volatile signed __int32 *v34; // [rsp+30h] [rbp-20h] BYREF
  volatile signed __int32 *v35; // [rsp+38h] [rbp-18h] BYREF
  LPVOID v36[2]; // [rsp+40h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+90h] [rbp+40h] BYREF
  volatile signed __int32 **v38; // [rsp+98h] [rbp+48h]
  LPVOID lpMem; // [rsp+A8h] [rbp+58h] BYREF

  v38 = a2;
  HIDWORD(hKey) = HIDWORD(a1);
  LODWORD(hKey) = 0;
  v5 = &Name;
  if ( *a2 )
    v6 = (const unsigned __int16 *)*((_QWORD *)*a2 + 2);
  else
    v6 = &Name;
  if ( (int)SHRegGetBOOL(a1, v6, L"triggeredCRRead", (int *)&hKey) >= 0 && (_DWORD)hKey )
  {
    UnifiedConsentLogging::TraceLoggingInfo("Consent is already read via CR.");
    *a3 = 1;
    UnifiedConsentLogging::TraceLoggingInfo("Ensuring values in registry.");
    hKey = 0;
    if ( *a2 )
      v7 = (const WCHAR *)*((_QWORD *)*a2 + 2);
    else
      v7 = &Name;
    if ( !RegOpenKeyExW(HKEY_CURRENT_USER, v7, 0, 8u, &hKey) )
    {
      UnifiedConsentLogging::TraceLoggingInfo("Obtained account key.");
      v9 = (volatile signed __int32 *)winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x19, v8);
      memcpy_s((void *const)(v9 + 7), 0x32u, L"WINDOWSACCOUNTSYNCCONSENT", 0x32u);
      v35 = v9;
      v11 = (volatile signed __int32 *)winrt::impl::precreate_hstring_on_heap((winrt::impl *)1, v10);
      memcpy_s((void *const)(v11 + 7), 2u, L"\\", 2u);
      v34 = v11;
      v12 = winrt::operator+(&lpMem, a2, &v34);
      winrt::operator+(v36, v12, &v35);
      v13 = lpMem;
      if ( lpMem )
      {
        v14 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
        if ( v14 )
        {
          if ( v14 < 0 )
            abort();
        }
        else
        {
          ProcessHeap = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(ProcessHeap, 0, v13);
        }
        lpMem = 0;
      }
      if ( v11 )
      {
        v16 = _InterlockedDecrement(v11 + 6);
        if ( v16 )
        {
          if ( v16 < 0 )
            abort();
        }
        else
        {
          v17 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v17, 0, (LPVOID)v11);
        }
      }
      if ( v9 )
      {
        v18 = _InterlockedDecrement(v9 + 6);
        if ( v18 )
        {
          if ( v18 < 0 )
            abort();
        }
        else
        {
          v19 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v19, 0, (LPVOID)v9);
        }
      }
      v20 = hKey;
      if ( hKey )
      {
        LastError = GetLastError();
        RegCloseKey(v20);
        SetLastError(LastError);
      }
      hKey = 0;
      v22 = (volatile signed __int32 *)v36[0];
      if ( v36[0] )
        v5 = (const WCHAR *)*((_QWORD *)v36[0] + 2);
      if ( !RegOpenKeyExW(HKEY_CURRENT_USER, v5, 0, 1u, &hKey) )
      {
        if ( !v22 )
        {
LABEL_35:
          if ( hKey )
            RegCloseKey(hKey);
          v25 = *a2;
          if ( *a2 )
          {
            v26 = _InterlockedDecrement(v25 + 6);
            if ( v26 )
            {
              if ( v26 < 0 )
                abort();
            }
            else
            {
              v27 = WINRT_IMPL_GetProcessHeap();
              WINRT_IMPL_HeapFree(v27, 0, (LPVOID)v25);
            }
            *a2 = 0;
          }
          return 1;
        }
        v23 = _InterlockedDecrement(v22 + 6);
        if ( !v23 )
        {
          v24 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v24, 0, (LPVOID)v22);
          goto LABEL_35;
        }
        if ( v23 >= 0 )
          goto LABEL_35;
LABEL_55:
        abort();
      }
      if ( v22 )
      {
        v29 = _InterlockedDecrement(v22 + 6);
        if ( v29 )
        {
          if ( v29 < 0 )
            goto LABEL_55;
        }
        else
        {
          v30 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v30, 0, (LPVOID)v22);
        }
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  v31 = *a2;
  if ( *a2 )
  {
    v32 = _InterlockedDecrement(v31 + 6);
    if ( v32 )
    {
      if ( v32 < 0 )
        abort();
    }
    else
    {
      v33 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v33, 0, (LPVOID)v31);
    }
    *a2 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180027be4  mov     [rsp-38h+arg_8], rdx
0x180027be9  mov     [rsp-38h+hKey], rcx
0x180027bee  push    rbp
0x180027bef  push    rbx
0x180027bf0  push    rsi
0x180027bf1  push    rdi
0x180027bf2  push    r12
0x180027bf4  push    r14
0x180027bf6  push    r15
0x180027bf8  mov     rbp, rsp
0x180027bfb  sub     rsp, 50h
0x180027bff  mov     rbx, r8
0x180027c02  mov     rsi, rdx
0x180027c05  mov     dword ptr [rbp+hKey], 0
0x180027c0c  mov     rax, [rdx]
0x180027c0f  lea     r14, Name
0x180027c16  test    rax, rax
0x180027c19  jz      short loc_180027C21
0x180027c1b  mov     rdx, [rax+10h]
0x180027c1f  jmp     short loc_180027C24
0x180027c21  mov     rdx, r14; unsigned __int16 *
0x180027c24  lea     r9, [rbp+hKey]; int *
0x180027c28  lea     r8, aTriggeredcrrea; "triggeredCRRead"
0x180027c2f  call    ?SHRegGetBOOL@@YAJPEAUHKEY__@@PEBG1PEAH@Z; SHRegGetBOOL(HKEY__ *,ushort const *,ushort const *,int *)
0x180027c34  or      edi, 0FFFFFFFFh
0x180027c37  test    eax, eax
0x180027c39  js      loc_180027EE9
0x180027c3f  cmp     dword ptr [rbp+hKey], 0
0x180027c43  jz      loc_180027EE9
0x180027c49  lea     rcx, aConsentIsAlrea; "Consent is already read via CR."
0x180027c50  call    ?TraceLoggingInfo@UnifiedConsentLogging@@SAXPEBDZZ; UnifiedConsentLogging::TraceLoggingInfo(char const *,...)
0x180027c55  mov     byte ptr [rbx], 1
0x180027c58  lea     rcx, aEnsuringValues; "Ensuring values in registry."
0x180027c5f  call    ?TraceLoggingInfo@UnifiedConsentLogging@@SAXPEBDZZ; UnifiedConsentLogging::TraceLoggingInfo(char const *,...)
0x180027c64  nop
0x180027c65  mov     [rbp+hKey], 0
0x180027c6d  mov     rax, [rsi]
0x180027c70  test    rax, rax
0x180027c73  jz      short loc_180027C7B
0x180027c75  mov     rdx, [rax+10h]
0x180027c79  jmp     short loc_180027C7E
0x180027c7b  mov     rdx, r14; lpSubKey
0x180027c7e  lea     rax, [rbp+hKey]
0x180027c82  mov     [rsp+50h+phkResult], rax; phkResult
0x180027c87  mov     r9d, 8; samDesired
0x180027c8d  xor     r8d, r8d; ulOptions
0x180027c90  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180027c97  call    cs:__imp_RegOpenKeyExW
0x180027c9d  test    eax, eax
0x180027c9f  jnz     loc_180027ED9
0x180027ca5  lea     rcx, aObtainedAccoun; "Obtained account key."
0x180027cac  call    ?TraceLoggingInfo@UnifiedConsentLogging@@SAXPEBDZZ; UnifiedConsentLogging::TraceLoggingInfo(char const *,...)
0x180027cb1  mov     ecx, 19h; this
0x180027cb6  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180027cbb  mov     r15, rax
0x180027cbe  lea     rcx, [rax+1Ch]; Destination
0x180027cc2  mov     edx, 32h ; '2'; DestinationSize
0x180027cc7  mov     r9d, edx; SourceSize
0x180027cca  lea     r8, aWindowsaccount_0; "WINDOWSACCOUNTSYNCCONSENT"
0x180027cd1  call    memcpy_s
0x180027cd6  mov     [rbp+var_18], r15
0x180027cda  mov     ecx, 1; this
0x180027cdf  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180027ce4  mov     rbx, rax
0x180027ce7  lea     rcx, [rax+1Ch]; Destination
0x180027ceb  mov     edx, 2; DestinationSize
0x180027cf0  mov     r9d, edx; SourceSize
0x180027cf3  lea     r8, asc_180082840; "\\"
0x180027cfa  call    memcpy_s
0x180027cff  mov     [rbp+var_20], rbx
0x180027d03  lea     r8, [rbp+var_20]
0x180027d07  mov     rdx, rsi
0x180027d0a  lea     rcx, [rbp+lpMem]
0x180027d0e  call    ??Hwinrt@@YA?AUhstring@0@AEBU10@0@Z; winrt::operator+(winrt::hstring const &,winrt::hstring const &)
0x180027d13  nop
0x180027d14  lea     r8, [rbp+var_18]
0x180027d18  mov     rdx, rax
0x180027d1b  lea     rcx, [rbp+var_10]
0x180027d1f  call    ??Hwinrt@@YA?AUhstring@0@AEBU10@0@Z; winrt::operator+(winrt::hstring const &,winrt::hstring const &)
0x180027d24  nop
0x180027d25  mov     r12, [rbp+lpMem]
0x180027d29  test    r12, r12
0x180027d2c  jz      short loc_180027D5B
0x180027d2e  mov     eax, edi
0x180027d30  lock xadd [r12+18h], eax
0x180027d37  sub     eax, 1
0x180027d3a  jnz     loc_180027E34
0x180027d40  nop
0x180027d41  call    WINRT_IMPL_GetProcessHeap
0x180027d46  mov     rcx, rax; hHeap
0x180027d49  mov     r8, r12; lpMem
0x180027d4c  xor     edx, edx; dwFlags
0x180027d4e  call    WINRT_IMPL_HeapFree
0x180027d53  mov     [rbp+lpMem], 0
0x180027d5b  test    rbx, rbx
0x180027d5e  jz      short loc_180027D84
0x180027d60  mov     eax, edi
0x180027d62  lock xadd [rbx+18h], eax
0x180027d67  sub     eax, 1
0x180027d6a  jnz     loc_180027E43
0x180027d70  nop
0x180027d71  call    WINRT_IMPL_GetProcessHeap
0x180027d76  mov     rcx, rax; hHeap
0x180027d79  mov     r8, rbx; lpMem
0x180027d7c  xor     edx, edx; dwFlags
0x180027d7e  call    WINRT_IMPL_HeapFree
0x180027d83  nop
0x180027d84  test    r15, r15
0x180027d87  jz      short loc_180027DAD
0x180027d89  mov     eax, edi
0x180027d8b  lock xadd [r15+18h], eax
0x180027d91  sub     eax, 1
0x180027d94  jnz     loc_180027E52
0x180027d9a  nop
0x180027d9b  call    WINRT_IMPL_GetProcessHeap
0x180027da0  mov     rcx, rax; hHeap
0x180027da3  mov     r8, r15; lpMem
0x180027da6  xor     edx, edx; dwFlags
0x180027da8  call    WINRT_IMPL_HeapFree
0x180027dad  mov     r15, [rbp+hKey]
0x180027db1  test    r15, r15
0x180027db4  jz      short loc_180027DCF
0x180027db6  call    cs:__imp_GetLastError
0x180027dbc  mov     ebx, eax
0x180027dbe  mov     rcx, r15; hKey
0x180027dc1  call    cs:__imp_RegCloseKey
0x180027dc7  mov     ecx, ebx; dwErrCode
0x180027dc9  call    cs:__imp_SetLastError
0x180027dcf  mov     [rbp+hKey], 0
0x180027dd7  mov     rbx, [rbp+var_10]
0x180027ddb  test    rbx, rbx
0x180027dde  jz      short loc_180027DE4
0x180027de0  mov     r14, [rbx+10h]
0x180027de4  lea     rax, [rbp+hKey]
0x180027de8  mov     [rsp+50h+phkResult], rax; phkResult
0x180027ded  mov     r9d, 1; samDesired
0x180027df3  xor     r8d, r8d; ulOptions
0x180027df6  mov     rdx, r14; lpSubKey
0x180027df9  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180027e00  call    cs:__imp_RegOpenKeyExW
0x180027e06  test    eax, eax
0x180027e08  jnz     loc_180027EB4
0x180027e0e  test    rbx, rbx
0x180027e11  jz      short loc_180027E69
0x180027e13  mov     eax, edi
0x180027e15  lock xadd [rbx+18h], eax
0x180027e1a  sub     eax, 1
0x180027e1d  jnz     short loc_180027E61
0x180027e1f  nop
0x180027e20  call    WINRT_IMPL_GetProcessHeap
0x180027e25  mov     rcx, rax; hHeap
0x180027e28  mov     r8, rbx; lpMem
0x180027e2b  xor     edx, edx; dwFlags
0x180027e2d  call    WINRT_IMPL_HeapFree
0x180027e32  jmp     short loc_180027E69
0x180027e34  test    eax, eax
0x180027e36  jns     loc_180027D53
0x180027e3c  call    cs:__imp_abort
0x180027e43  test    eax, eax
0x180027e45  jns     loc_180027D84
0x180027e4b  call    cs:__imp_abort
0x180027e52  test    eax, eax
0x180027e54  jns     loc_180027DAD
0x180027e5a  call    cs:__imp_abort
0x180027e61  test    eax, eax
0x180027e63  js      loc_180027F2A
0x180027e69  mov     rcx, [rbp+hKey]; hKey
0x180027e6d  test    rcx, rcx
0x180027e70  jz      short loc_180027E79
0x180027e72  call    cs:__imp_RegCloseKey
0x180027e78  nop
0x180027e79  mov     rbx, [rsi]
0x180027e7c  test    rbx, rbx
0x180027e7f  jz      short loc_180027EA5
0x180027e81  lock xadd [rbx+18h], edi
0x180027e86  sub     edi, 1
0x180027e89  jnz     short loc_180027EA9
0x180027e8b  nop
0x180027e8c  call    WINRT_IMPL_GetProcessHeap
0x180027e91  mov     rcx, rax; hHeap
0x180027e94  mov     r8, rbx; lpMem
0x180027e97  xor     edx, edx; dwFlags
0x180027e99  call    WINRT_IMPL_HeapFree
0x180027e9e  mov     qword ptr [rsi], 0
0x180027ea5  mov     al, 1
0x180027ea7  jmp     short loc_180027F17
0x180027ea9  test    edi, edi
0x180027eab  jns     short loc_180027E9E
0x180027ead  call    cs:__imp_abort
0x180027eb4  test    rbx, rbx
0x180027eb7  jz      short loc_180027ED9
0x180027eb9  mov     eax, edi
0x180027ebb  lock xadd [rbx+18h], eax
0x180027ec0  sub     eax, 1
0x180027ec3  jnz     short loc_180027F26
0x180027ec5  nop
0x180027ec6  call    WINRT_IMPL_GetProcessHeap
0x180027ecb  mov     rcx, rax; hHeap
0x180027ece  mov     r8, rbx; lpMem
0x180027ed1  xor     edx, edx; dwFlags
0x180027ed3  call    WINRT_IMPL_HeapFree
0x180027ed8  nop
0x180027ed9  mov     rcx, [rbp+hKey]; hKey
0x180027edd  test    rcx, rcx
0x180027ee0  jz      short loc_180027EE9
0x180027ee2  call    cs:__imp_RegCloseKey
0x180027ee8  nop
0x180027ee9  mov     rbx, [rsi]
0x180027eec  test    rbx, rbx
0x180027eef  jz      short loc_180027F15
0x180027ef1  lock xadd [rbx+18h], edi
0x180027ef6  sub     edi, 1
0x180027ef9  jnz     short loc_180027F31
0x180027efb  nop
0x180027efc  call    WINRT_IMPL_GetProcessHeap
0x180027f01  mov     rcx, rax; hHeap
0x180027f04  mov     r8, rbx; lpMem
0x180027f07  xor     edx, edx; dwFlags
0x180027f09  call    WINRT_IMPL_HeapFree
0x180027f0e  mov     qword ptr [rsi], 0
0x180027f15  xor     al, al
0x180027f17  add     rsp, 50h
0x180027f1b  pop     r15
0x180027f1d  pop     r14
0x180027f1f  pop     r12
0x180027f21  pop     rdi
0x180027f22  pop     rsi
0x180027f23  pop     rbx
0x180027f24  pop     rbp
0x180027f25  retn
0x180027f26  test    eax, eax
0x180027f28  jns     short loc_180027ED9
0x180027f2a  call    cs:__imp_abort
0x180027f31  test    edi, edi
0x180027f33  jns     short loc_180027F0E
0x180027f35  call    cs:__imp_abort
```
