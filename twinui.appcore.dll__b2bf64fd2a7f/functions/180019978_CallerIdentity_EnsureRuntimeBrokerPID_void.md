# CallerIdentity::_EnsureRuntimeBrokerPID(void)

- ea: `0x180019978`
- end: `0x180019a47`
- name: `?_EnsureRuntimeBrokerPID@CallerIdentity@@YAXXZ`
- size: `207`
- prototype: `void __fastcall(CallerIdentity *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018cc0`

## callees

- `0x180019978`
- `0x1800299c8`
- `0x18002b1b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800199a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800199a0`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180019a1b`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180019a1b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180019a0d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180019a0d`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800199c3`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800199c3`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800199e8`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800199e8`

## string_xrefs

- `0x1800199e1`: `%SystemRoot%\System32\RuntimeBroker.exe`

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
0x180019978  push    rbx
0x18001997a  sub     rsp, 470h
0x180019981  mov     rax, cs:__security_cookie
0x180019988  xor     rax, rsp
0x18001998b  mov     [rsp+478h+var_18], rax
0x180019993  cmp     cs:?g_fRuntimeBrokerProcessIdInitialize@CallerIdentity@@3_NA, 0; bool CallerIdentity::g_fRuntimeBrokerProcessIdInitialize
0x18001999a  jnz     loc_180019A2E
0x1800199a0  call    cs:__imp_GetCurrentProcess
0x1800199a6  lea     r9, [rsp+478h+dwSize]; lpdwSize
0x1800199ab  mov     [rsp+478h+dwSize], 104h
0x1800199b3  mov     rcx, rax; hProcess
0x1800199b6  lea     r8, [rsp+478h+ExeName]; lpExeName
0x1800199be  xor     edx, edx; dwFlags
0x1800199c0  mov     rbx, rax
0x1800199c3  call    cs:__imp_QueryFullProcessImageNameW
0x1800199c9  test    eax, eax
0x1800199cb  jnz     short loc_1800199D6
0x1800199cd  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800199d2  test    eax, eax
0x1800199d4  js      short loc_180019A27
0x1800199d6  mov     r8d, 104h; nSize
0x1800199dc  lea     rdx, [rsp+478h+Dst]; lpDst
0x1800199e1  lea     rcx, Src; "%SystemRoot%\\System32\\RuntimeBroker.e"...
0x1800199e8  call    cs:__imp_ExpandEnvironmentStringsW
0x1800199ee  test    eax, eax
0x1800199f0  jz      short loc_180019A27
0x1800199f2  or      edx, 0FFFFFFFFh; cchCount1
0x1800199f5  mov     [rsp+478h+bIgnoreCase], 1; bIgnoreCase
0x1800199fd  mov     r9d, edx; cchCount2
0x180019a00  lea     r8, [rsp+478h+Dst]; lpString2
0x180019a05  lea     rcx, [rsp+478h+ExeName]; lpString1
0x180019a0d  call    cs:__imp_CompareStringOrdinal
0x180019a13  cmp     eax, 2
0x180019a16  jnz     short loc_180019A27
0x180019a18  mov     rcx, rbx; Process
0x180019a1b  call    cs:__imp_GetProcessId
0x180019a21  mov     cs:?g_dwRuntimeBrokerProcessId@CallerIdentity@@3KA, eax; ulong CallerIdentity::g_dwRuntimeBrokerProcessId
0x180019a27  mov     cs:?g_fRuntimeBrokerProcessIdInitialize@CallerIdentity@@3_NA, 1; bool CallerIdentity::g_fRuntimeBrokerProcessIdInitialize
0x180019a2e  mov     rcx, [rsp+478h+var_18]
0x180019a36  xor     rcx, rsp; StackCookie
0x180019a39  call    __security_check_cookie
0x180019a3e  add     rsp, 470h
0x180019a45  pop     rbx
0x180019a46  retn
```
