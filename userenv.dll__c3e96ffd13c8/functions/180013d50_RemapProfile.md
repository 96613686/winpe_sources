# RemapProfile

- ea: `0x180013d50`
- end: `0x180013ea2`
- name: `RemapProfile`
- size: `338`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003380`
- `0x18000d9b0`
- `0x18000e330`
- `0x180012064`
- `0x1800124b0`
- `0x180012720`
- `0x1800132a0`
- `0x180013394`
- `0x180013d50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180013dd4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180013dd4`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180013df1`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180013df1`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180013deb`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180013deb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RemapProfile(int a1, const WCHAR *a2, const WCHAR *a3)
{
  HANDLE CurrentProcess; // rax
  const size_t *CommandLineW; // rbx
  int v5; // ebx
  DWORD dwSize; // [rsp+20h] [rbp-E0h] BYREF
  LPCWCH lpString1; // [rsp+28h] [rbp-D8h] BYREF
  const WCHAR *v9; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v10[3]; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v11[42]; // [rsp+50h] [rbp-B0h] BYREF
  size_t ExeName[66]; // [rsp+1A0h] [rbp+A0h] BYREF
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
  QueryFullProcessImageNameW(CurrentProcess, 0, (LPWSTR)ExeName, &dwSize);
  CommandLineW = (const size_t *)GetCommandLineW();
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
0x180013d50  mov     [rsp-8+arg_18], rbx
0x180013d55  mov     [rsp-8+arg_0], ecx
0x180013d59  push    rbp
0x180013d5a  lea     rbp, [rsp-2C0h]
0x180013d62  sub     rsp, 3C0h
0x180013d69  mov     rax, cs:__security_cookie
0x180013d70  xor     rax, rsp
0x180013d73  mov     [rbp+2C0h+var_10], rax
0x180013d7a  mov     [rsp+3C0h+var_390], rdx
0x180013d7f  mov     [rsp+3C0h+lpString1], r8
0x180013d84  test    rdx, rdx
0x180013d87  jz      loc_180013E7D
0x180013d8d  test    r8, r8
0x180013d90  jz      loc_180013E7D
0x180013d96  mov     rcx, rdx; lpString1
0x180013d99  call    ?IsServiceSid@@YAHPEBG@Z; IsServiceSid(ushort const *)
0x180013d9e  test    eax, eax
0x180013da0  jnz     loc_180013E76
0x180013da6  mov     rcx, [rsp+3C0h+lpString1]; lpString1
0x180013dab  call    ?IsServiceSid@@YAHPEBG@Z; IsServiceSid(ushort const *)
0x180013db0  test    eax, eax
0x180013db2  jnz     loc_180013E76
0x180013db8  xor     edx, edx; Val
0x180013dba  mov     r8d, 20Ah; Size
0x180013dc0  lea     rcx, [rbp+2C0h+ExeName]; void *
0x180013dc7  call    memset_0
0x180013dcc  mov     [rsp+3C0h+dwSize], 105h
0x180013dd4  call    cs:__imp_GetCurrentProcess
0x180013dda  mov     rcx, rax; hProcess
0x180013ddd  lea     r9, [rsp+3C0h+dwSize]; lpdwSize
0x180013de2  lea     r8, [rbp+2C0h+ExeName]; lpExeName
0x180013de9  xor     edx, edx; dwFlags
0x180013deb  call    cs:__imp_QueryFullProcessImageNameW
0x180013df1  call    cs:__imp_GetCommandLineW
0x180013df7  mov     rbx, rax
0x180013dfa  lea     rdx, aWinapiremappro; "WINAPIRemapProfile"
0x180013e01  lea     rcx, [rsp+3C0h+var_370]; struct wil::details::IFailureCallback *
0x180013e06  call    ??0?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180013e0b  lea     rax, ??_7WINAPIRemapProfile@UserenvTelemetry@@6B@; const UserenvTelemetry::WINAPIRemapProfile::`vftable'
0x180013e12  mov     [rsp+3C0h+var_370], rax
0x180013e17  mov     r8, rbx; unsigned __int16 *
0x180013e1a  lea     rdx, [rbp+2C0h+ExeName]; unsigned __int16 *
0x180013e21  lea     rcx, [rsp+3C0h+var_370]; this
0x180013e26  call    ?StartActivity@WINAPIRemapProfile@UserenvTelemetry@@QEAAXPEBG0@Z; UserenvTelemetry::WINAPIRemapProfile::StartActivity(ushort const *,ushort const *)
0x180013e2b  nop
0x180013e2c  lea     rax, [rbp+2C0h+arg_0]
0x180013e33  mov     [rsp+3C0h+var_388], rax
0x180013e38  lea     rax, [rsp+3C0h+var_390]
0x180013e3d  mov     [rsp+3C0h+var_380], rax
0x180013e42  lea     rax, [rsp+3C0h+lpString1]
0x180013e47  mov     [rsp+3C0h+var_378], rax
0x180013e4c  lea     rcx, [rsp+3C0h+var_388]
0x180013e51  call    InvokeUserProfileRPC__lambda_c85f50188a6ad7c456372eb6afbcdebb___; InvokeUserProfileRPC__lambda_c85f50188a6ad7c456372eb6afbcdebb_
0x180013e56  mov     ebx, eax
0x180013e58  test    eax, eax
0x180013e5a  js      short loc_180013E68
0x180013e5c  lea     rcx, [rsp+3C0h+var_370]
0x180013e61  call    ?Stop@?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180013e66  xor     ebx, ebx
0x180013e68  lea     rcx, [rsp+3C0h+var_370]; this
0x180013e6d  call    ??1WINAPIRemapProfile@UserenvTelemetry@@QEAA@XZ; UserenvTelemetry::WINAPIRemapProfile::~WINAPIRemapProfile(void)
0x180013e72  mov     eax, ebx
0x180013e74  jmp     short loc_180013E82
0x180013e76  mov     eax, 80070005h
0x180013e7b  jmp     short loc_180013E82
0x180013e7d  mov     eax, 80070057h
0x180013e82  mov     rcx, [rbp+2C0h+var_10]
0x180013e89  xor     rcx, rsp; StackCookie
0x180013e8c  call    __security_check_cookie
0x180013e91  mov     rbx, [rsp+3C0h+arg_18]
0x180013e99  add     rsp, 3C0h
0x180013ea0  pop     rbp
0x180013ea1  retn
```
