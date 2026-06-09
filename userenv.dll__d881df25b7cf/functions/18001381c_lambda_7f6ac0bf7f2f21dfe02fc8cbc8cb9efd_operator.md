# _lambda_7f6ac0bf7f2f21dfe02fc8cbc8cb9efd_::operator()

- ea: `0x18001381c`
- end: `0x1800138d4`
- name: `_lambda_7f6ac0bf7f2f21dfe02fc8cbc8cb9efd_::operator()`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180013d40`

## callees

- `0x18000e640`
- `0x18000efe0`
- `0x1800130c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001385b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001385b`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180013882`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180013882`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180013876`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180013876`

## pseudocode

```c
char __fastcall lambda_7f6ac0bf7f2f21dfe02fc8cbc8cb9efd_::operator()(_QWORD **a1, int a2)
{
  HANDLE CurrentProcess; // rax
  DWORD dwSize; // [rsp+30h] [rbp-238h] BYREF
  LPWSTR CommandLineW; // [rsp+38h] [rbp-230h] BYREF
  WCHAR ExeName[264]; // [rsp+40h] [rbp-228h] BYREF

  memset_0(ExeName, 0, 0x20Au);
  dwSize = 261;
  CurrentProcess = GetCurrentProcess();
  QueryFullProcessImageNameW(CurrentProcess, 0, ExeName, &dwSize);
  CommandLineW = GetCommandLineW();
  UserenvTelemetry::WINAPILoadUserProfileFailure<unsigned long &,unsigned short (&)[261],unsigned short *,long const &>(
    **a1 + 4,
    (unsigned int)ExeName,
    (unsigned int)&CommandLineW,
    a2 + 8);
  return 0;
}

```

## disassembly

```asm
0x18001381c  mov     [rsp+arg_10], rbx
0x180013821  push    rdi
0x180013822  sub     rsp, 260h
0x180013829  mov     rax, cs:__security_cookie
0x180013830  xor     rax, rsp
0x180013833  mov     [rsp+268h+var_18], rax
0x18001383b  mov     rdi, rdx
0x18001383e  mov     rbx, rcx
0x180013841  xor     edx, edx; Val
0x180013843  lea     rcx, [rsp+268h+ExeName]; void *
0x180013848  mov     r8d, 20Ah; Size
0x18001384e  call    memset_0
0x180013853  mov     [rsp+268h+dwSize], 105h
0x18001385b  call    cs:__imp_GetCurrentProcess
0x180013862  nop     dword ptr [rax+rax+00h]
0x180013867  lea     r9, [rsp+268h+dwSize]; lpdwSize
0x18001386c  xor     edx, edx; dwFlags
0x18001386e  mov     rcx, rax; hProcess
0x180013871  lea     r8, [rsp+268h+ExeName]; lpExeName
0x180013876  call    cs:__imp_QueryFullProcessImageNameW
0x18001387d  nop     dword ptr [rax+rax+00h]
0x180013882  call    cs:__imp_GetCommandLineW
0x180013889  nop     dword ptr [rax+rax+00h]
0x18001388e  mov     [rsp+268h+var_230], rax
0x180013893  lea     r9, [rdi+8]
0x180013897  mov     rax, [rbx]
0x18001389a  lea     r8, [rsp+268h+var_230]
0x18001389f  lea     rdx, [rsp+268h+ExeName]
0x1800138a4  mov     rcx, [rax]
0x1800138a7  add     rcx, 4
0x1800138ab  call    ??$WINAPILoadUserProfileFailure@AEAKAEAY0BAF@GPEAGAEBJ@UserenvTelemetry@@SAXAEAKAEAY0BAF@G$$QEAPEAGAEBJPEBD@Z; UserenvTelemetry::WINAPILoadUserProfileFailure<ulong &,ushort (&)[261],ushort *,long const &>(ulong &,ushort (&)[261],ushort * &&,long const &,char const *)
0x1800138b0  xor     al, al
0x1800138b2  mov     rcx, [rsp+268h+var_18]
0x1800138ba  xor     rcx, rsp; StackCookie
0x1800138bd  call    __security_check_cookie
0x1800138c2  mov     rbx, [rsp+268h+arg_10]
0x1800138ca  add     rsp, 260h
0x1800138d1  pop     rdi
0x1800138d2  retn
```
