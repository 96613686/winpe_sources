# _lambda_c1ae4bc0d8af10932893e455087b7b7e_::operator()

- ea: `0x1800138dc`
- end: `0x18001397b`
- name: `_lambda_c1ae4bc0d8af10932893e455087b7b7e_::operator()`
- size: `159`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180013d50`

## callees

- `0x18000e640`
- `0x18000efe0`
- `0x18001318c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180013914`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180013914`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18001393b`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18001393b`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18001392f`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18001392f`

## pseudocode

```c
char __fastcall lambda_c1ae4bc0d8af10932893e455087b7b7e_::operator()(__int64 a1, __int64 a2)
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
0x1800138dc  push    rbx
0x1800138de  sub     rsp, 250h
0x1800138e5  mov     rax, cs:__security_cookie
0x1800138ec  xor     rax, rsp
0x1800138ef  mov     [rsp+258h+var_18], rax
0x1800138f7  mov     rbx, rdx
0x1800138fa  lea     rcx, [rsp+258h+ExeName]; void *
0x1800138ff  xor     edx, edx; Val
0x180013901  mov     r8d, 20Ah; Size
0x180013907  call    memset_0
0x18001390c  mov     [rsp+258h+dwSize], 105h
0x180013914  call    cs:__imp_GetCurrentProcess
0x18001391b  nop     dword ptr [rax+rax+00h]
0x180013920  lea     r9, [rsp+258h+dwSize]; lpdwSize
0x180013925  xor     edx, edx; dwFlags
0x180013927  mov     rcx, rax; hProcess
0x18001392a  lea     r8, [rsp+258h+ExeName]; lpExeName
0x18001392f  call    cs:__imp_QueryFullProcessImageNameW
0x180013936  nop     dword ptr [rax+rax+00h]
0x18001393b  call    cs:__imp_GetCommandLineW
0x180013942  nop     dword ptr [rax+rax+00h]
0x180013947  lea     r8, [rbx+8]
0x18001394b  mov     [rsp+258h+var_230], rax
0x180013950  lea     rdx, [rsp+258h+var_230]
0x180013955  lea     rcx, [rsp+258h+ExeName]
0x18001395a  call    ??$WINAPIUnloadUserProfileFailure@AEAY0BAF@GPEAGAEBJ@UserenvTelemetry@@SAXAEAY0BAF@G$$QEAPEAGAEBJPEBD@Z; UserenvTelemetry::WINAPIUnloadUserProfileFailure<ushort (&)[261],ushort *,long const &>(ushort (&)[261],ushort * &&,long const &,char const *)
0x18001395f  xor     al, al
0x180013961  mov     rcx, [rsp+258h+var_18]
0x180013969  xor     rcx, rsp; StackCookie
0x18001396c  call    __security_check_cookie
0x180013971  add     rsp, 250h
0x180013978  pop     rbx
0x180013979  retn
```
