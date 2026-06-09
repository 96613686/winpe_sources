# CallerIdentity::_EnsureRuntimeBrokerPID(void)

- ea: `0x1800636c8`
- end: `0x180063796`
- name: `?_EnsureRuntimeBrokerPID@CallerIdentity@@YAXXZ`
- size: `206`
- prototype: `void __fastcall(CallerIdentity *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180063520`

## callees

- `0x1800636c8`
- `0x1800772c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006371d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006371d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800636f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800636f0`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18006376a`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18006376a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006375c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006375c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180063737`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180063737`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180063713`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180063713`

## string_xrefs

- `0x180063730`: `%SystemRoot%\System32\RuntimeBroker.exe`

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
    if ( QueryFullProcessImageNameW(CurrentProcess, 0, ExeName, dwSize) )
    {
      if ( ExpandEnvironmentStringsW(L"%SystemRoot%\\System32\\RuntimeBroker.exe", Dst, 0x104u) )
      {
        if ( CompareStringOrdinal(ExeName, -1, Dst, -1, 1) == 2 )
          CallerIdentity::g_dwRuntimeBrokerProcessId = GetProcessId(CurrentProcess);
      }
    }
    else
    {
      GetLastError();
    }
    CallerIdentity::g_fRuntimeBrokerProcessIdInitialize = 1;
  }
}

```

## disassembly

```asm
0x1800636c8  push    rbx
0x1800636ca  sub     rsp, 470h
0x1800636d1  mov     rax, cs:__security_cookie
0x1800636d8  xor     rax, rsp
0x1800636db  mov     [rsp+478h+var_18], rax
0x1800636e3  cmp     cs:?g_fRuntimeBrokerProcessIdInitialize@CallerIdentity@@3_NA, 0; bool CallerIdentity::g_fRuntimeBrokerProcessIdInitialize
0x1800636ea  jnz     loc_18006377D
0x1800636f0  call    cs:__imp_GetCurrentProcess
0x1800636f6  lea     r9, [rsp+478h+dwSize]; lpdwSize
0x1800636fb  mov     [rsp+478h+dwSize], 104h
0x180063703  mov     rcx, rax; hProcess
0x180063706  lea     r8, [rsp+478h+ExeName]; lpExeName
0x18006370e  xor     edx, edx; dwFlags
0x180063710  mov     rbx, rax
0x180063713  call    cs:__imp_QueryFullProcessImageNameW
0x180063719  test    eax, eax
0x18006371b  jnz     short loc_180063725
0x18006371d  call    cs:__imp_GetLastError
0x180063723  jmp     short loc_180063776
0x180063725  mov     r8d, 104h; nSize
0x18006372b  lea     rdx, [rsp+478h+Dst]; lpDst
0x180063730  lea     rcx, aSystemrootSyst_1; "%SystemRoot%\\System32\\RuntimeBroker.e"...
0x180063737  call    cs:__imp_ExpandEnvironmentStringsW
0x18006373d  test    eax, eax
0x18006373f  jz      short loc_180063776
0x180063741  or      edx, 0FFFFFFFFh; cchCount1
0x180063744  mov     [rsp+478h+bIgnoreCase], 1; bIgnoreCase
0x18006374c  mov     r9d, edx; cchCount2
0x18006374f  lea     r8, [rsp+478h+Dst]; lpString2
0x180063754  lea     rcx, [rsp+478h+ExeName]; lpString1
0x18006375c  call    cs:__imp_CompareStringOrdinal
0x180063762  cmp     eax, 2
0x180063765  jnz     short loc_180063776
0x180063767  mov     rcx, rbx; Process
0x18006376a  call    cs:__imp_GetProcessId
0x180063770  mov     cs:?g_dwRuntimeBrokerProcessId@CallerIdentity@@3KA, eax; ulong CallerIdentity::g_dwRuntimeBrokerProcessId
0x180063776  mov     cs:?g_fRuntimeBrokerProcessIdInitialize@CallerIdentity@@3_NA, 1; bool CallerIdentity::g_fRuntimeBrokerProcessIdInitialize
0x18006377d  mov     rcx, [rsp+478h+var_18]
0x180063785  xor     rcx, rsp; StackCookie
0x180063788  call    __security_check_cookie
0x18006378d  add     rsp, 470h
0x180063794  pop     rbx
0x180063795  retn
```
