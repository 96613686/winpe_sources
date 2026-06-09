# RemapProfile

- ea: `0x180014e30`
- end: `0x180014f95`
- name: `RemapProfile`
- size: `357`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800033e0`
- `0x18000e640`
- `0x18000efe0`
- `0x180013030`
- `0x180013494`
- `0x18001371c`
- `0x180014348`
- `0x180014440`
- `0x180014e30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180014eb4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180014eb4`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180014edd`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180014edd`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180014ed1`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180014ed1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RemapProfile(int a1, const WCHAR *a2, const WCHAR *a3)
{
  HANDLE CurrentProcess; // rax
  const unsigned __int16 *CommandLineW; // rbx
  int v5; // ebx
  DWORD dwSize; // [rsp+20h] [rbp-E0h] BYREF
  LPCWCH lpString1; // [rsp+28h] [rbp-D8h] BYREF
  const WCHAR *v9; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v10[3]; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v11[42]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR ExeName[264]; // [rsp+1A0h] [rbp+A0h] BYREF
  int v13; // [rsp+3D0h] [rbp+2D0h] BYREF

  v13 = a1;
  v9 = a2;
  lpString1 = a3;
  if ( !a2 || !a3 )
    return 2147942487LL;
  if ( IsServiceSid(a2) || IsServiceSid(lpString1) )
    return 2147942405LL;
  memset_0(ExeName, 0, 0x20Au);
  dwSize = 261;
  CurrentProcess = GetCurrentProcess();
  QueryFullProcessImageNameW(CurrentProcess, 0, ExeName, &dwSize);
  CommandLineW = GetCommandLineW();
  wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v11);
  v11[0] = &UserenvTelemetry::WINAPIRemapProfile::`vftable';
  UserenvTelemetry::WINAPIRemapProfile::StartActivity(
    (UserenvTelemetry::WINAPIRemapProfile *)v11,
    ExeName,
    CommandLineW);
  v10[0] = &v13;
  v10[1] = &v9;
  v10[2] = &lpString1;
  v5 = InvokeUserProfileRPC__lambda_c85f50188a6ad7c456372eb6afbcdebb_(v10);
  if ( v5 >= 0 )
  {
    wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v11);
    v5 = 0;
  }
  UserenvTelemetry::WINAPIRemapProfile::~WINAPIRemapProfile((UserenvTelemetry::WINAPIRemapProfile *)v11);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180014e30  mov     [rsp-8+arg_18], rbx
0x180014e35  mov     [rsp-8+arg_0], ecx
0x180014e39  push    rbp
0x180014e3a  lea     rbp, [rsp-2C0h]
0x180014e42  sub     rsp, 3C0h
0x180014e49  mov     rax, cs:__security_cookie
0x180014e50  xor     rax, rsp
0x180014e53  mov     [rbp+2C0h+var_10], rax
0x180014e5a  mov     [rsp+3C0h+var_390], rdx
0x180014e5f  mov     [rsp+3C0h+lpString1], r8
0x180014e64  test    rdx, rdx
0x180014e67  jz      loc_180014F6F
0x180014e6d  test    r8, r8
0x180014e70  jz      loc_180014F6F
0x180014e76  mov     rcx, rdx; lpString1
0x180014e79  call    ?IsServiceSid@@YAHPEBG@Z; IsServiceSid(ushort const *)
0x180014e7e  test    eax, eax
0x180014e80  jnz     loc_180014F68
0x180014e86  mov     rcx, [rsp+3C0h+lpString1]; lpString1
0x180014e8b  call    ?IsServiceSid@@YAHPEBG@Z; IsServiceSid(ushort const *)
0x180014e90  test    eax, eax
0x180014e92  jnz     loc_180014F68
0x180014e98  xor     edx, edx; Val
0x180014e9a  mov     r8d, 20Ah; Size
0x180014ea0  lea     rcx, [rbp+2C0h+ExeName]; void *
0x180014ea7  call    memset_0
0x180014eac  mov     [rsp+3C0h+dwSize], 105h
0x180014eb4  call    cs:__imp_GetCurrentProcess
0x180014ebb  nop     dword ptr [rax+rax+00h]
0x180014ec0  mov     rcx, rax; hProcess
0x180014ec3  lea     r9, [rsp+3C0h+dwSize]; lpdwSize
0x180014ec8  lea     r8, [rbp+2C0h+ExeName]; lpExeName
0x180014ecf  xor     edx, edx; dwFlags
0x180014ed1  call    cs:__imp_QueryFullProcessImageNameW
0x180014ed8  nop     dword ptr [rax+rax+00h]
0x180014edd  call    cs:__imp_GetCommandLineW
0x180014ee4  nop     dword ptr [rax+rax+00h]
0x180014ee9  mov     rbx, rax
0x180014eec  lea     rdx, aWinapiremappro; "WINAPIRemapProfile"
0x180014ef3  lea     rcx, [rsp+3C0h+var_370]; struct wil::details::IFailureCallback *
0x180014ef8  call    ??0?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180014efd  lea     rax, ??_7WINAPIRemapProfile@UserenvTelemetry@@6B@; const UserenvTelemetry::WINAPIRemapProfile::`vftable'
0x180014f04  mov     [rsp+3C0h+var_370], rax
0x180014f09  mov     r8, rbx; unsigned __int16 *
0x180014f0c  lea     rdx, [rbp+2C0h+ExeName]; unsigned __int16 *
0x180014f13  lea     rcx, [rsp+3C0h+var_370]; this
0x180014f18  call    ?StartActivity@WINAPIRemapProfile@UserenvTelemetry@@QEAAXPEBG0@Z; UserenvTelemetry::WINAPIRemapProfile::StartActivity(ushort const *,ushort const *)
0x180014f1d  nop
0x180014f1e  lea     rax, [rbp+2C0h+arg_0]
0x180014f25  mov     [rsp+3C0h+var_388], rax
0x180014f2a  lea     rax, [rsp+3C0h+var_390]
0x180014f2f  mov     [rsp+3C0h+var_380], rax
0x180014f34  lea     rax, [rsp+3C0h+lpString1]
0x180014f39  mov     [rsp+3C0h+var_378], rax
0x180014f3e  lea     rcx, [rsp+3C0h+var_388]
0x180014f43  call    InvokeUserProfileRPC__lambda_c85f50188a6ad7c456372eb6afbcdebb___; InvokeUserProfileRPC__lambda_c85f50188a6ad7c456372eb6afbcdebb_
0x180014f48  mov     ebx, eax
0x180014f4a  test    eax, eax
0x180014f4c  js      short loc_180014F5A
0x180014f4e  lea     rcx, [rsp+3C0h+var_370]
0x180014f53  call    ?Stop@?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180014f58  xor     ebx, ebx
0x180014f5a  lea     rcx, [rsp+3C0h+var_370]; this
0x180014f5f  call    ??1WINAPIRemapProfile@UserenvTelemetry@@QEAA@XZ; UserenvTelemetry::WINAPIRemapProfile::~WINAPIRemapProfile(void)
0x180014f64  mov     eax, ebx
0x180014f66  jmp     short loc_180014F74
0x180014f68  mov     eax, 80070005h
0x180014f6d  jmp     short loc_180014F74
0x180014f6f  mov     eax, 80070057h
0x180014f74  mov     rcx, [rbp+2C0h+var_10]
0x180014f7b  xor     rcx, rsp; StackCookie
0x180014f7e  call    __security_check_cookie
0x180014f83  mov     rbx, [rsp+3C0h+arg_18]
0x180014f8b  add     rsp, 3C0h
0x180014f92  pop     rbp
0x180014f93  retn
```
