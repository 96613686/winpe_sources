# CallerIdentity::_EnsureRuntimeBrokerPID(void)

- ea: `0x1800d9530`
- end: `0x1800d95ff`
- name: `?_EnsureRuntimeBrokerPID@CallerIdentity@@YAXXZ`
- size: `207`
- prototype: `void __fastcall(CallerIdentity *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800d9100`

## callees

- `0x1800b7570`
- `0x1800d9530`
- `0x1800de450`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800d95d3`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800d95d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800d9558`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800d9558`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800d95c5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800d95c5`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800d95a0`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800d95a0`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800d957b`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800d957b`

## string_xrefs

- `0x1800d9599`: `%SystemRoot%\System32\RuntimeBroker.exe`

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
0x1800d9530  push    rbx
0x1800d9532  sub     rsp, 470h
0x1800d9539  mov     rax, cs:__security_cookie
0x1800d9540  xor     rax, rsp
0x1800d9543  mov     [rsp+478h+var_18], rax
0x1800d954b  cmp     cs:?g_fRuntimeBrokerProcessIdInitialize@CallerIdentity@@3_NA, 0; bool CallerIdentity::g_fRuntimeBrokerProcessIdInitialize
0x1800d9552  jnz     loc_1800D95E6
0x1800d9558  call    cs:__imp_GetCurrentProcess
0x1800d955e  lea     r9, [rsp+478h+dwSize]; lpdwSize
0x1800d9563  mov     [rsp+478h+dwSize], 104h
0x1800d956b  mov     rcx, rax; hProcess
0x1800d956e  lea     r8, [rsp+478h+ExeName]; lpExeName
0x1800d9576  xor     edx, edx; dwFlags
0x1800d9578  mov     rbx, rax
0x1800d957b  call    cs:__imp_QueryFullProcessImageNameW
0x1800d9581  test    eax, eax
0x1800d9583  jnz     short loc_1800D958E
0x1800d9585  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800d958a  test    eax, eax
0x1800d958c  js      short loc_1800D95DF
0x1800d958e  mov     r8d, 104h; nSize
0x1800d9594  lea     rdx, [rsp+478h+Dst]; lpDst
0x1800d9599  lea     rcx, aSystemrootSyst; "%SystemRoot%\\System32\\RuntimeBroker.e"...
0x1800d95a0  call    cs:__imp_ExpandEnvironmentStringsW
0x1800d95a6  test    eax, eax
0x1800d95a8  jz      short loc_1800D95DF
0x1800d95aa  or      edx, 0FFFFFFFFh; cchCount1
0x1800d95ad  mov     [rsp+478h+bIgnoreCase], 1; bIgnoreCase
0x1800d95b5  mov     r9d, edx; cchCount2
0x1800d95b8  lea     r8, [rsp+478h+Dst]; lpString2
0x1800d95bd  lea     rcx, [rsp+478h+ExeName]; lpString1
0x1800d95c5  call    cs:__imp_CompareStringOrdinal
0x1800d95cb  cmp     eax, 2
0x1800d95ce  jnz     short loc_1800D95DF
0x1800d95d0  mov     rcx, rbx; Process
0x1800d95d3  call    cs:__imp_GetProcessId
0x1800d95d9  mov     cs:?g_dwRuntimeBrokerProcessId@CallerIdentity@@3KA, eax; ulong CallerIdentity::g_dwRuntimeBrokerProcessId
0x1800d95df  mov     cs:?g_fRuntimeBrokerProcessIdInitialize@CallerIdentity@@3_NA, 1; bool CallerIdentity::g_fRuntimeBrokerProcessIdInitialize
0x1800d95e6  mov     rcx, [rsp+478h+var_18]
0x1800d95ee  xor     rcx, rsp; StackCookie
0x1800d95f1  call    __security_check_cookie
0x1800d95f6  add     rsp, 470h
0x1800d95fd  pop     rbx
0x1800d95fe  retn
```
