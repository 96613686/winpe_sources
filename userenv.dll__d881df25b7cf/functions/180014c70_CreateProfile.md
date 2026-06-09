# CreateProfile

- ea: `0x180014c70`
- end: `0x180014de7`
- name: `CreateProfile`
- size: `375`
- prototype: `HRESULT __stdcall(LPCWSTR pszUserSid, LPCWSTR pszUserName, LPWSTR pszProfilePath, DWORD cchProfilePath)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800033e0`
- `0x18000e640`
- `0x18000efe0`
- `0x180012f10`
- `0x180013494`
- `0x1800136c4`
- `0x180014158`
- `0x180014440`
- `0x180014c70`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180014d06`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180014d06`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180014d2f`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180014d2f`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180014d23`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180014d23`

## string_xrefs

- `0x180014d3e`: `WINAPICreateProfile`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall CreateProfile(LPCWSTR pszUserSid, LPCWSTR pszUserName, LPWSTR pszProfilePath, DWORD cchProfilePath)
{
  HANDLE CurrentProcess; // rax
  const unsigned __int16 *CommandLineW; // rbx
  HRESULT v7; // ebx
  DWORD dwSize[2]; // [rsp+28h] [rbp-E0h] BYREF
  LPCWSTR v9; // [rsp+30h] [rbp-D8h] BYREF
  _QWORD v10[4]; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD v11[42]; // [rsp+58h] [rbp-B0h] BYREF
  WCHAR ExeName[264]; // [rsp+1A8h] [rbp+A0h] BYREF
  LPCWSTR v13; // [rsp+3F0h] [rbp+2E8h] BYREF
  LPWSTR v14; // [rsp+3F8h] [rbp+2F0h] BYREF
  DWORD v15; // [rsp+400h] [rbp+2F8h] BYREF

  v15 = cchProfilePath;
  v14 = pszProfilePath;
  v13 = pszUserName;
  v9 = pszUserSid;
  if ( !pszUserSid )
    return -2147024809;
  if ( IsServiceSid(pszUserSid) )
    return -2147024891;
  if ( !v13 || !v14 || !v15 )
    return -2147024809;
  memset_0(ExeName, 0, 0x20Au);
  dwSize[0] = 261;
  CurrentProcess = GetCurrentProcess();
  QueryFullProcessImageNameW(CurrentProcess, 0, ExeName, dwSize);
  CommandLineW = GetCommandLineW();
  wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v11);
  v11[0] = &UserenvTelemetry::WINAPICreateProfile::`vftable';
  UserenvTelemetry::WINAPICreateProfile::StartActivity(
    (UserenvTelemetry::WINAPICreateProfile *)v11,
    ExeName,
    CommandLineW);
  v10[0] = &v9;
  v10[1] = &v13;
  v10[2] = &v14;
  v10[3] = &v15;
  v7 = InvokeUserProfileRPC__lambda_34c279a10b2d290b68eee06320d75c21_(v10);
  if ( v7 >= 0 )
  {
    wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v11);
    v7 = 0;
  }
  UserenvTelemetry::WINAPICreateProfile::~WINAPICreateProfile((UserenvTelemetry::WINAPICreateProfile *)v11);
  return v7;
}

```

## disassembly

```asm
0x180014c70  mov     rax, rsp
0x180014c73  mov     [rax+20h], r9d
0x180014c77  mov     [rax+18h], r8
0x180014c7b  mov     [rax+10h], rdx
0x180014c7f  push    rbp
0x180014c80  push    rbx
0x180014c81  lea     rbp, [rax-2D8h]
0x180014c88  sub     rsp, 3C8h
0x180014c8f  mov     rax, cs:__security_cookie
0x180014c96  xor     rax, rsp
0x180014c99  mov     [rbp+2D0h+var_20], rax
0x180014ca0  mov     [rsp+3D0h+var_3A8], rcx
0x180014ca5  test    rcx, rcx
0x180014ca8  jz      loc_180014DC8
0x180014cae  call    ?IsServiceSid@@YAHPEBG@Z; IsServiceSid(ushort const *)
0x180014cb3  test    eax, eax
0x180014cb5  jz      short loc_180014CC1
0x180014cb7  mov     eax, 80070005h
0x180014cbc  jmp     loc_180014DCD
0x180014cc1  cmp     [rbp+2D0h+arg_8], 0
0x180014cc9  jz      loc_180014DC8
0x180014ccf  cmp     [rbp+2D0h+arg_10], 0
0x180014cd7  jz      loc_180014DC8
0x180014cdd  cmp     [rbp+2D0h+arg_18], 0
0x180014ce4  jz      loc_180014DC8
0x180014cea  xor     edx, edx; Val
0x180014cec  mov     r8d, 20Ah; Size
0x180014cf2  lea     rcx, [rbp+2D0h+ExeName]; void *
0x180014cf9  call    memset_0
0x180014cfe  mov     [rsp+3D0h+dwSize], 105h
0x180014d06  call    cs:__imp_GetCurrentProcess
0x180014d0d  nop     dword ptr [rax+rax+00h]
0x180014d12  mov     rcx, rax; hProcess
0x180014d15  lea     r9, [rsp+3D0h+dwSize]; lpdwSize
0x180014d1a  lea     r8, [rbp+2D0h+ExeName]; lpExeName
0x180014d21  xor     edx, edx; dwFlags
0x180014d23  call    cs:__imp_QueryFullProcessImageNameW
0x180014d2a  nop     dword ptr [rax+rax+00h]
0x180014d2f  call    cs:__imp_GetCommandLineW
0x180014d36  nop     dword ptr [rax+rax+00h]
0x180014d3b  mov     rbx, rax
0x180014d3e  lea     rdx, aWinapicreatepr; "WINAPICreateProfile"
0x180014d45  lea     rcx, [rsp+3D0h+var_380]; struct wil::details::IFailureCallback *
0x180014d4a  call    ??0?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180014d4f  lea     rax, ??_7WINAPICreateProfile@UserenvTelemetry@@6B@; const UserenvTelemetry::WINAPICreateProfile::`vftable'
0x180014d56  mov     [rsp+3D0h+var_380], rax
0x180014d5b  mov     r8, rbx; unsigned __int16 *
0x180014d5e  lea     rdx, [rbp+2D0h+ExeName]; unsigned __int16 *
0x180014d65  lea     rcx, [rsp+3D0h+var_380]; this
0x180014d6a  call    ?StartActivity@WINAPICreateProfile@UserenvTelemetry@@QEAAXPEBG0@Z; UserenvTelemetry::WINAPICreateProfile::StartActivity(ushort const *,ushort const *)
0x180014d6f  nop
0x180014d70  lea     rax, [rsp+3D0h+var_3A8]
0x180014d75  mov     [rsp+3D0h+var_3A0], rax
0x180014d7a  lea     rax, [rbp+2D0h+arg_8]
0x180014d81  mov     [rsp+3D0h+var_398], rax
0x180014d86  lea     rax, [rbp+2D0h+arg_10]
0x180014d8d  mov     [rsp+3D0h+var_390], rax
0x180014d92  lea     rax, [rbp+2D0h+arg_18]
0x180014d99  mov     [rsp+3D0h+var_388], rax
0x180014d9e  lea     rcx, [rsp+3D0h+var_3A0]
0x180014da3  call    InvokeUserProfileRPC__lambda_34c279a10b2d290b68eee06320d75c21___; InvokeUserProfileRPC__lambda_34c279a10b2d290b68eee06320d75c21_
0x180014da8  mov     ebx, eax
0x180014daa  test    eax, eax
0x180014dac  js      short loc_180014DBA
0x180014dae  lea     rcx, [rsp+3D0h+var_380]
0x180014db3  call    ?Stop@?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180014db8  xor     ebx, ebx
0x180014dba  lea     rcx, [rsp+3D0h+var_380]; this
0x180014dbf  call    ??1WINAPICreateProfile@UserenvTelemetry@@QEAA@XZ; UserenvTelemetry::WINAPICreateProfile::~WINAPICreateProfile(void)
0x180014dc4  mov     eax, ebx
0x180014dc6  jmp     short loc_180014DCD
0x180014dc8  mov     eax, 80070057h
0x180014dcd  mov     rcx, [rbp+2D0h+var_20]
0x180014dd4  xor     rcx, rsp; StackCookie
0x180014dd7  call    __security_check_cookie
0x180014ddc  add     rsp, 3C8h
0x180014de3  pop     rbx
0x180014de4  pop     rbp
0x180014de5  retn
```
