# CallerIdentity::_EnsureRuntimeBrokerPID(void)

- ea: `0x180072bb0`
- end: `0x180072c7f`
- name: `?_EnsureRuntimeBrokerPID@CallerIdentity@@YAXXZ`
- size: `207`
- prototype: `void __fastcall(CallerIdentity *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180072800`

## callees

- `0x180072bb0`
- `0x1800a4d18`
- `0x1800b99f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180072bd8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180072bd8`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180072c53`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180072c53`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180072c45`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180072c45`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180072c20`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180072c20`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180072bfb`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180072bfb`

## string_xrefs

- `0x180072c19`: `%SystemRoot%\System32\RuntimeBroker.exe`

## pseudocode

```c
void __fastcall CallerIdentity::_EnsureRuntimeBrokerPID(CallerIdentity *this)
{
  HANDLE CurrentProcess; // rbx
  DWORD dwSize[4]; // [rsp+30h] [rbp-448h] BYREF
  WCHAR Dst[264]; // [rsp+40h] [rbp-438h] BYREF
  WCHAR ExeName[264]; // [rsp+250h] [rbp-228h] BYREF

  if ( !CallerIdentity::g_fRuntimeBrokerProcessIdInitialize )
  {
    dwSize[0] = 260;
    CurrentProcess = GetCurrentProcess();
    if ( QueryFullProcessImageNameW(CurrentProcess, 0, ExeName, dwSize) || (int)ResultFromKnownLastError() >= 0 )
    {
      if ( ExpandEnvironmentStringsW(L"%SystemRoot%\\System32\\RuntimeBroker.exe", Dst, 0x104u) )
      {
        if ( CompareStringOrdinal(ExeName, -1, Dst, -1, 1) == 2 )
          CallerIdentity::g_dwRuntimeBrokerProcessId = GetProcessId(CurrentProcess);
      }
    }
    CallerIdentity::g_fRuntimeBrokerProcessIdInitialize = 1;
  }
}

```

## disassembly

```asm
0x180072bb0  push    rbx
0x180072bb2  sub     rsp, 470h
0x180072bb9  mov     rax, cs:__security_cookie
0x180072bc0  xor     rax, rsp
0x180072bc3  mov     [rsp+478h+var_18], rax
0x180072bcb  cmp     cs:?g_fRuntimeBrokerProcessIdInitialize@CallerIdentity@@3_NA, 0; bool CallerIdentity::g_fRuntimeBrokerProcessIdInitialize
0x180072bd2  jnz     loc_180072C66
0x180072bd8  call    cs:__imp_GetCurrentProcess
0x180072bde  lea     r9, [rsp+478h+dwSize]; lpdwSize
0x180072be3  mov     [rsp+478h+dwSize], 104h
0x180072beb  mov     rcx, rax; hProcess
0x180072bee  lea     r8, [rsp+478h+ExeName]; lpExeName
0x180072bf6  xor     edx, edx; dwFlags
0x180072bf8  mov     rbx, rax
0x180072bfb  call    cs:__imp_QueryFullProcessImageNameW
0x180072c01  test    eax, eax
0x180072c03  jnz     short loc_180072C0E
0x180072c05  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180072c0a  test    eax, eax
0x180072c0c  js      short loc_180072C5F
0x180072c0e  mov     r8d, 104h; nSize
0x180072c14  lea     rdx, [rsp+478h+Dst]; lpDst
0x180072c19  lea     rcx, Src; "%SystemRoot%\\System32\\RuntimeBroker.e"...
0x180072c20  call    cs:__imp_ExpandEnvironmentStringsW
0x180072c26  test    eax, eax
0x180072c28  jz      short loc_180072C5F
0x180072c2a  or      edx, 0FFFFFFFFh; cchCount1
0x180072c2d  mov     [rsp+478h+bIgnoreCase], 1; bIgnoreCase
0x180072c35  mov     r9d, edx; cchCount2
0x180072c38  lea     r8, [rsp+478h+Dst]; lpString2
0x180072c3d  lea     rcx, [rsp+478h+ExeName]; lpString1
0x180072c45  call    cs:__imp_CompareStringOrdinal
0x180072c4b  cmp     eax, 2
0x180072c4e  jnz     short loc_180072C5F
0x180072c50  mov     rcx, rbx; Process
0x180072c53  call    cs:__imp_GetProcessId
0x180072c59  mov     cs:?g_dwRuntimeBrokerProcessId@CallerIdentity@@3KA, eax; ulong CallerIdentity::g_dwRuntimeBrokerProcessId
0x180072c5f  mov     cs:?g_fRuntimeBrokerProcessIdInitialize@CallerIdentity@@3_NA, 1; bool CallerIdentity::g_fRuntimeBrokerProcessIdInitialize
0x180072c66  mov     rcx, [rsp+478h+var_18]
0x180072c6e  xor     rcx, rsp; StackCookie
0x180072c71  call    __security_check_cookie
0x180072c76  add     rsp, 470h
0x180072c7d  pop     rbx
0x180072c7e  retn
```
