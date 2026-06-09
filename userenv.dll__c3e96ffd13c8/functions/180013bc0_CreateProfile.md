# CreateProfile

- ea: `0x180013bc0`
- end: `0x180013d24`
- name: `CreateProfile`
- size: `356`
- prototype: `HRESULT __stdcall(LPCWSTR pszUserSid, LPCWSTR pszUserName, LPWSTR pszProfilePath, DWORD cchProfilePath)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003380`
- `0x18000d9b0`
- `0x18000e330`
- `0x180011f4c`
- `0x1800124b0`
- `0x1800126c8`
- `0x1800130b8`
- `0x180013394`
- `0x180013bc0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180013c56`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180013c56`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180013c73`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180013c73`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180013c6d`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180013c6d`

## string_xrefs

- `0x180013c7c`: `WINAPICreateProfile`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall CreateProfile(LPCWSTR pszUserSid, LPCWSTR pszUserName, LPWSTR pszProfilePath, DWORD cchProfilePath)
{
  HANDLE CurrentProcess; // rax
  const size_t *CommandLineW; // rbx
  HRESULT v7; // ebx
  DWORD dwSize[2]; // [rsp+28h] [rbp-E0h] BYREF
  LPCWSTR v9; // [rsp+30h] [rbp-D8h] BYREF
  _QWORD v10[4]; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD v11[42]; // [rsp+58h] [rbp-B0h] BYREF
  size_t ExeName[66]; // [rsp+1A8h] [rbp+A0h] BYREF
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
  QueryFullProcessImageNameW(CurrentProcess, 0, (LPWSTR)ExeName, dwSize);
  CommandLineW = (const size_t *)GetCommandLineW();
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
0x180013bc0  mov     rax, rsp
0x180013bc3  mov     [rax+20h], r9d
0x180013bc7  mov     [rax+18h], r8
0x180013bcb  mov     [rax+10h], rdx
0x180013bcf  push    rbp
0x180013bd0  push    rbx
0x180013bd1  lea     rbp, [rax-2D8h]
0x180013bd8  sub     rsp, 3C8h
0x180013bdf  mov     rax, cs:__security_cookie
0x180013be6  xor     rax, rsp
0x180013be9  mov     [rbp+2D0h+var_20], rax
0x180013bf0  mov     [rsp+3D0h+var_3A8], rcx
0x180013bf5  test    rcx, rcx
0x180013bf8  jz      loc_180013D06
0x180013bfe  call    ?IsServiceSid@@YAHPEBG@Z; IsServiceSid(ushort const *)
0x180013c03  test    eax, eax
0x180013c05  jz      short loc_180013C11
0x180013c07  mov     eax, 80070005h
0x180013c0c  jmp     loc_180013D0B
0x180013c11  cmp     [rbp+2D0h+arg_8], 0
0x180013c19  jz      loc_180013D06
0x180013c1f  cmp     [rbp+2D0h+arg_10], 0
0x180013c27  jz      loc_180013D06
0x180013c2d  cmp     [rbp+2D0h+arg_18], 0
0x180013c34  jz      loc_180013D06
0x180013c3a  xor     edx, edx; Val
0x180013c3c  mov     r8d, 20Ah; Size
0x180013c42  lea     rcx, [rbp+2D0h+ExeName]; void *
0x180013c49  call    memset_0
0x180013c4e  mov     [rsp+3D0h+dwSize], 105h
0x180013c56  call    cs:__imp_GetCurrentProcess
0x180013c5c  mov     rcx, rax; hProcess
0x180013c5f  lea     r9, [rsp+3D0h+dwSize]; lpdwSize
0x180013c64  lea     r8, [rbp+2D0h+ExeName]; lpExeName
0x180013c6b  xor     edx, edx; dwFlags
0x180013c6d  call    cs:__imp_QueryFullProcessImageNameW
0x180013c73  call    cs:__imp_GetCommandLineW
0x180013c79  mov     rbx, rax
0x180013c7c  lea     rdx, aWinapicreatepr; "WINAPICreateProfile"
0x180013c83  lea     rcx, [rsp+3D0h+var_380]; struct wil::details::IFailureCallback *
0x180013c88  call    ??0?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180013c8d  lea     rax, ??_7WINAPICreateProfile@UserenvTelemetry@@6B@; const UserenvTelemetry::WINAPICreateProfile::`vftable'
0x180013c94  mov     [rsp+3D0h+var_380], rax
0x180013c99  mov     r8, rbx; unsigned __int16 *
0x180013c9c  lea     rdx, [rbp+2D0h+ExeName]; unsigned __int16 *
0x180013ca3  lea     rcx, [rsp+3D0h+var_380]; this
0x180013ca8  call    ?StartActivity@WINAPICreateProfile@UserenvTelemetry@@QEAAXPEBG0@Z; UserenvTelemetry::WINAPICreateProfile::StartActivity(ushort const *,ushort const *)
0x180013cad  nop
0x180013cae  lea     rax, [rsp+3D0h+var_3A8]
0x180013cb3  mov     [rsp+3D0h+var_3A0], rax
0x180013cb8  lea     rax, [rbp+2D0h+arg_8]
0x180013cbf  mov     [rsp+3D0h+var_398], rax
0x180013cc4  lea     rax, [rbp+2D0h+arg_10]
0x180013ccb  mov     [rsp+3D0h+var_390], rax
0x180013cd0  lea     rax, [rbp+2D0h+arg_18]
0x180013cd7  mov     [rsp+3D0h+var_388], rax
0x180013cdc  lea     rcx, [rsp+3D0h+var_3A0]
0x180013ce1  call    InvokeUserProfileRPC__lambda_34c279a10b2d290b68eee06320d75c21___; InvokeUserProfileRPC__lambda_34c279a10b2d290b68eee06320d75c21_
0x180013ce6  mov     ebx, eax
0x180013ce8  test    eax, eax
0x180013cea  js      short loc_180013CF8
0x180013cec  lea     rcx, [rsp+3D0h+var_380]
0x180013cf1  call    ?Stop@?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180013cf6  xor     ebx, ebx
0x180013cf8  lea     rcx, [rsp+3D0h+var_380]; this
0x180013cfd  call    ??1WINAPICreateProfile@UserenvTelemetry@@QEAA@XZ; UserenvTelemetry::WINAPICreateProfile::~WINAPICreateProfile(void)
0x180013d02  mov     eax, ebx
0x180013d04  jmp     short loc_180013D0B
0x180013d06  mov     eax, 80070057h
0x180013d0b  mov     rcx, [rbp+2D0h+var_20]
0x180013d12  xor     rcx, rsp; StackCookie
0x180013d15  call    __security_check_cookie
0x180013d1a  add     rsp, 3C8h
0x180013d21  pop     rbx
0x180013d22  pop     rbp
0x180013d23  retn
```
