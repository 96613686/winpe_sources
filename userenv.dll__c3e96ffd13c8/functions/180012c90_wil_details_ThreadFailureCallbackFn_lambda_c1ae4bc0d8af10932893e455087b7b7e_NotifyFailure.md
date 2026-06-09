# wil::details::ThreadFailureCallbackFn__lambda_c1ae4bc0d8af10932893e455087b7b7e___::NotifyFailure

- ea: `0x180012c90`
- end: `0x180012d1c`
- name: `wil::details::ThreadFailureCallbackFn__lambda_c1ae4bc0d8af10932893e455087b7b7e___::NotifyFailure`
- size: `140`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000d9b0`
- `0x18000e330`
- `0x1800121bc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180012cc8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180012cc8`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180012ce3`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180012ce3`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180012cdd`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180012cdd`

## pseudocode

```c
char __fastcall wil::details::ThreadFailureCallbackFn__lambda_c1ae4bc0d8af10932893e455087b7b7e___::NotifyFailure(
        __int64 a1,
        __int64 a2)
{
  HANDLE CurrentProcess; // rax
  DWORD dwSize; // [rsp+20h] [rbp-238h] BYREF
  LPWSTR CommandLineW; // [rsp+28h] [rbp-230h] BYREF
  WCHAR ExeName[264]; // [rsp+30h] [rbp-228h] BYREF

  memset_0(ExeName, 0, 0x20Au);
  dwSize = 261;
  CurrentProcess = GetCurrentProcess();
  QueryFullProcessImageNameW(CurrentProcess, 0, ExeName, &dwSize);
  CommandLineW = GetCommandLineW();
  UserenvTelemetry::WINAPIUnloadUserProfileFailure<unsigned short (&)[261],unsigned short *,long const &>(
    ExeName,
    &CommandLineW,
    a2 + 8);
  return 0;
}

```

## disassembly

```asm
0x180012c90  push    rbx
0x180012c92  sub     rsp, 250h
0x180012c99  mov     rax, cs:__security_cookie
0x180012ca0  xor     rax, rsp
0x180012ca3  mov     [rsp+258h+var_18], rax
0x180012cab  mov     rbx, rdx
0x180012cae  lea     rcx, [rsp+258h+ExeName]; void *
0x180012cb3  xor     edx, edx; Val
0x180012cb5  mov     r8d, 20Ah; Size
0x180012cbb  call    memset_0
0x180012cc0  mov     [rsp+258h+dwSize], 105h
0x180012cc8  call    cs:__imp_GetCurrentProcess
0x180012cce  lea     r9, [rsp+258h+dwSize]; lpdwSize
0x180012cd3  xor     edx, edx; dwFlags
0x180012cd5  mov     rcx, rax; hProcess
0x180012cd8  lea     r8, [rsp+258h+ExeName]; lpExeName
0x180012cdd  call    cs:__imp_QueryFullProcessImageNameW
0x180012ce3  call    cs:__imp_GetCommandLineW
0x180012ce9  lea     r8, [rbx+8]
0x180012ced  mov     [rsp+258h+var_230], rax
0x180012cf2  lea     rdx, [rsp+258h+var_230]
0x180012cf7  lea     rcx, [rsp+258h+ExeName]
0x180012cfc  call    ??$WINAPIUnloadUserProfileFailure@AEAY0BAF@GPEAGAEBJ@UserenvTelemetry@@SAXAEAY0BAF@G$$QEAPEAGAEBJPEBD@Z; UserenvTelemetry::WINAPIUnloadUserProfileFailure<ushort (&)[261],ushort *,long const &>(ushort (&)[261],ushort * &&,long const &,char const *)
0x180012d01  xor     al, al
0x180012d03  mov     rcx, [rsp+258h+var_18]
0x180012d0b  xor     rcx, rsp; StackCookie
0x180012d0e  call    __security_check_cookie
0x180012d13  add     rsp, 250h
0x180012d1a  pop     rbx
0x180012d1b  retn
```
