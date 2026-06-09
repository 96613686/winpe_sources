# CallerIdentity::_EnsureRuntimeBrokerPID(void)

- ea: `0x18002ff68`
- end: `0x180030056`
- name: `?_EnsureRuntimeBrokerPID@CallerIdentity@@YAXXZ`
- size: `238`
- prototype: `void __fastcall(CallerIdentity *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800e04f0`

## callees

- `0x18002ff68`
- `0x18003d244`
- `0x180054130`

## import_xrefs

- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18002ffb9`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18002ffb9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003000f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003000f`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180030023`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180030023`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002ff90`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002ff90`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002ffe4`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002ffe4`

## string_xrefs

- `0x18002ffdd`: `%SystemRoot%\System32\RuntimeBroker.exe`

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
0x18002ff68  push    rbx
0x18002ff6a  sub     rsp, 470h
0x18002ff71  mov     rax, cs:__security_cookie
0x18002ff78  xor     rax, rsp
0x18002ff7b  mov     [rsp+478h+var_18], rax
0x18002ff83  cmp     cs:?g_fRuntimeBrokerProcessIdInitialize@CallerIdentity@@3_NA, 0; bool CallerIdentity::g_fRuntimeBrokerProcessIdInitialize
0x18002ff8a  jnz     loc_18003003C
0x18002ff90  call    cs:__imp_GetCurrentProcess
0x18002ff97  nop     dword ptr [rax+rax+00h]
0x18002ff9c  lea     r9, [rsp+478h+dwSize]; lpdwSize
0x18002ffa1  mov     [rsp+478h+dwSize], 104h
0x18002ffa9  mov     rcx, rax; hProcess
0x18002ffac  lea     r8, [rsp+478h+ExeName]; lpExeName
0x18002ffb4  xor     edx, edx; dwFlags
0x18002ffb6  mov     rbx, rax
0x18002ffb9  call    cs:__imp_QueryFullProcessImageNameW
0x18002ffc0  nop     dword ptr [rax+rax+00h]
0x18002ffc5  test    eax, eax
0x18002ffc7  jnz     short loc_18002FFD2
0x18002ffc9  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002ffce  test    eax, eax
0x18002ffd0  js      short loc_180030035
0x18002ffd2  mov     r8d, 104h; nSize
0x18002ffd8  lea     rdx, [rsp+478h+Dst]; lpDst
0x18002ffdd  lea     rcx, aSystemrootSyst_1; "%SystemRoot%\\System32\\RuntimeBroker.e"...
0x18002ffe4  call    cs:__imp_ExpandEnvironmentStringsW
0x18002ffeb  nop     dword ptr [rax+rax+00h]
0x18002fff0  test    eax, eax
0x18002fff2  jz      short loc_180030035
0x18002fff4  or      edx, 0FFFFFFFFh; cchCount1
0x18002fff7  mov     [rsp+478h+bIgnoreCase], 1; bIgnoreCase
0x18002ffff  mov     r9d, edx; cchCount2
0x180030002  lea     r8, [rsp+478h+Dst]; lpString2
0x180030007  lea     rcx, [rsp+478h+ExeName]; lpString1
0x18003000f  call    cs:__imp_CompareStringOrdinal
0x180030016  nop     dword ptr [rax+rax+00h]
0x18003001b  cmp     eax, 2
0x18003001e  jnz     short loc_180030035
0x180030020  mov     rcx, rbx; Process
0x180030023  call    cs:__imp_GetProcessId
0x18003002a  nop     dword ptr [rax+rax+00h]
0x18003002f  mov     cs:?g_dwRuntimeBrokerProcessId@CallerIdentity@@3KA, eax; ulong CallerIdentity::g_dwRuntimeBrokerProcessId
0x180030035  mov     cs:?g_fRuntimeBrokerProcessIdInitialize@CallerIdentity@@3_NA, 1; bool CallerIdentity::g_fRuntimeBrokerProcessIdInitialize
0x18003003c  mov     rcx, [rsp+478h+var_18]
0x180030044  xor     rcx, rsp; StackCookie
0x180030047  call    __security_check_cookie
0x18003004c  add     rsp, 470h
0x180030053  pop     rbx
0x180030054  retn
```
