# _lambda_7f6ac0bf7f2f21dfe02fc8cbc8cb9efd_::operator()

- ea: `0x180012820`
- end: `0x1800128c5`
- name: `_lambda_7f6ac0bf7f2f21dfe02fc8cbc8cb9efd_::operator()`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180012c80`

## callees

- `0x18000d9b0`
- `0x18000e330`
- `0x1800120f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001285f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001285f`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18001287a`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18001287a`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180012874`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180012874`

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
0x180012820  mov     [rsp+arg_10], rbx
0x180012825  push    rdi
0x180012826  sub     rsp, 260h
0x18001282d  mov     rax, cs:__security_cookie
0x180012834  xor     rax, rsp
0x180012837  mov     [rsp+268h+var_18], rax
0x18001283f  mov     rdi, rdx
0x180012842  mov     rbx, rcx
0x180012845  xor     edx, edx; Val
0x180012847  lea     rcx, [rsp+268h+ExeName]; void *
0x18001284c  mov     r8d, 20Ah; Size
0x180012852  call    memset_0
0x180012857  mov     [rsp+268h+dwSize], 105h
0x18001285f  call    cs:__imp_GetCurrentProcess
0x180012865  lea     r9, [rsp+268h+dwSize]; lpdwSize
0x18001286a  xor     edx, edx; dwFlags
0x18001286c  mov     rcx, rax; hProcess
0x18001286f  lea     r8, [rsp+268h+ExeName]; lpExeName
0x180012874  call    cs:__imp_QueryFullProcessImageNameW
0x18001287a  call    cs:__imp_GetCommandLineW
0x180012880  mov     [rsp+268h+var_230], rax
0x180012885  lea     r9, [rdi+8]
0x180012889  mov     rax, [rbx]
0x18001288c  lea     r8, [rsp+268h+var_230]
0x180012891  lea     rdx, [rsp+268h+ExeName]
0x180012896  mov     rcx, [rax]
0x180012899  add     rcx, 4
0x18001289d  call    ??$WINAPILoadUserProfileFailure@AEAKAEAY0BAF@GPEAGAEBJ@UserenvTelemetry@@SAXAEAKAEAY0BAF@G$$QEAPEAGAEBJPEBD@Z; UserenvTelemetry::WINAPILoadUserProfileFailure<ulong &,ushort (&)[261],ushort *,long const &>(ulong &,ushort (&)[261],ushort * &&,long const &,char const *)
0x1800128a2  xor     al, al
0x1800128a4  mov     rcx, [rsp+268h+var_18]
0x1800128ac  xor     rcx, rsp; StackCookie
0x1800128af  call    __security_check_cookie
0x1800128b4  mov     rbx, [rsp+268h+arg_10]
0x1800128bc  add     rsp, 260h
0x1800128c3  pop     rdi
0x1800128c4  retn
```
