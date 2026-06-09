# DeleteProfileInternal(ushort const *,ushort const *,ushort const *)

- ea: `0x180009f74`
- end: `0x18000a0f2`
- name: `?DeleteProfileInternal@@YAJPEBG00@Z`
- size: `382`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180009f40`

## callees

- `0x1800033e0`
- `0x180007f80`
- `0x180009f74`
- `0x18000db08`
- `0x18000e640`
- `0x18000efe0`
- `0x180012fa0`
- `0x180013494`
- `0x1800136f0`
- `0x180014250`
- `0x180014440`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a007`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a007`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18000a030`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18000a030`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18000a024`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18000a024`

## string_xrefs

- `0x18000a09f`: `onecore\ds\security\gina\profile\userenv\dll\profrpc.cpp`
- `0x18000a03f`: `WINAPIDeleteProfile`

## pseudocode

```c
__int64 __fastcall DeleteProfileInternal(const unsigned __int16 *a1, unsigned __int16 *a2, const unsigned __int16 *a3)
{
  HANDLE CurrentProcess; // rax
  const unsigned __int16 *CommandLineW; // rbx
  int v7; // eax
  unsigned int v8; // ebx
  DWORD dwSize; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int16 *v10; // [rsp+28h] [rbp-D8h] BYREF
  const unsigned __int16 *v11; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v12[3]; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v13[42]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR ExeName[264]; // [rsp+1A0h] [rbp+A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3C8h] [rbp+2C8h]

  v11 = a1;
  v10 = a2;
  if ( !a1 )
    return 2147942487LL;
  if ( (unsigned int)IsServiceSid(a1) )
    return 2147942405LL;
  if ( v10 && (int)StringCchLengthW(v10, 0x104u, 0) < 0 || a3 )
    return 2147942487LL;
  memset_0(ExeName, 0, 0x20Au);
  dwSize = 261;
  CurrentProcess = GetCurrentProcess();
  QueryFullProcessImageNameW(CurrentProcess, 0, ExeName, &dwSize);
  CommandLineW = GetCommandLineW();
  wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v13);
  v13[0] = &UserenvTelemetry::WINAPIDeleteProfile::`vftable';
  UserenvTelemetry::WINAPIDeleteProfile::StartActivity(
    (UserenvTelemetry::WINAPIDeleteProfile *)v13,
    ExeName,
    CommandLineW);
  v12[0] = &v11;
  v12[1] = &v10;
  v7 = InvokeUserProfileRPC__lambda_c3e8d726eb567336769114f33ed11b9b_(v12);
  v8 = v7;
  if ( v7 >= 0 )
  {
    wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v13);
    v8 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x195,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\dll\\profrpc.cpp",
      (const char *)(unsigned int)v7,
      dwSize);
  }
  UserenvTelemetry::WINAPIDeleteProfile::~WINAPIDeleteProfile((UserenvTelemetry::WINAPIDeleteProfile *)v13);
  return v8;
}

```

## disassembly

```asm
0x180009f74  mov     [rsp-8+arg_10], rbx
0x180009f79  push    rbp
0x180009f7a  lea     rbp, [rsp-2C0h]
0x180009f82  sub     rsp, 3C0h
0x180009f89  mov     rax, cs:__security_cookie
0x180009f90  xor     rax, rsp
0x180009f93  mov     [rbp+2C0h+var_10], rax
0x180009f9a  mov     rbx, r8
0x180009f9d  mov     [rsp+3C0h+var_390], rcx
0x180009fa2  mov     [rsp+3C0h+var_398], rdx
0x180009fa7  test    rcx, rcx
0x180009faa  jz      loc_18000A0CC
0x180009fb0  call    ?IsServiceSid@@YAHPEBG@Z; IsServiceSid(ushort const *)
0x180009fb5  test    eax, eax
0x180009fb7  jz      short loc_180009FC3
0x180009fb9  mov     eax, 80070005h
0x180009fbe  jmp     loc_18000A0D1
0x180009fc3  mov     rcx, [rsp+3C0h+var_398]; unsigned __int16 *
0x180009fc8  test    rcx, rcx
0x180009fcb  jz      short loc_180009FE2
0x180009fcd  xor     r8d, r8d; unsigned __int64 *
0x180009fd0  mov     edx, 104h; unsigned __int64
0x180009fd5  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180009fda  test    eax, eax
0x180009fdc  js      loc_18000A0CC
0x180009fe2  test    rbx, rbx
0x180009fe5  jnz     loc_18000A0CC
0x180009feb  xor     edx, edx; Val
0x180009fed  mov     r8d, 20Ah; Size
0x180009ff3  lea     rcx, [rbp+2C0h+ExeName]; void *
0x180009ffa  call    memset_0
0x180009fff  mov     [rsp+3C0h+dwSize], 105h; int
0x18000a007  call    cs:__imp_GetCurrentProcess
0x18000a00e  nop     dword ptr [rax+rax+00h]
0x18000a013  mov     rcx, rax; hProcess
0x18000a016  lea     r9, [rsp+3C0h+dwSize]; lpdwSize
0x18000a01b  lea     r8, [rbp+2C0h+ExeName]; lpExeName
0x18000a022  xor     edx, edx; dwFlags
0x18000a024  call    cs:__imp_QueryFullProcessImageNameW
0x18000a02b  nop     dword ptr [rax+rax+00h]
0x18000a030  call    cs:__imp_GetCommandLineW
0x18000a037  nop     dword ptr [rax+rax+00h]
0x18000a03c  mov     rbx, rax
0x18000a03f  lea     rdx, aWinapideletepr; "WINAPIDeleteProfile"
0x18000a046  lea     rcx, [rsp+3C0h+var_370]; struct wil::details::IFailureCallback *
0x18000a04b  call    ??0?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000a050  lea     rax, ??_7WINAPIDeleteProfile@UserenvTelemetry@@6B@; const UserenvTelemetry::WINAPIDeleteProfile::`vftable'
0x18000a057  mov     [rsp+3C0h+var_370], rax
0x18000a05c  mov     r8, rbx; unsigned __int16 *
0x18000a05f  lea     rdx, [rbp+2C0h+ExeName]; unsigned __int16 *
0x18000a066  lea     rcx, [rsp+3C0h+var_370]; this
0x18000a06b  call    ?StartActivity@WINAPIDeleteProfile@UserenvTelemetry@@QEAAXPEBG0@Z; UserenvTelemetry::WINAPIDeleteProfile::StartActivity(ushort const *,ushort const *)
0x18000a070  nop
0x18000a071  lea     rax, [rsp+3C0h+var_390]
0x18000a076  mov     [rsp+3C0h+var_388], rax
0x18000a07b  lea     rax, [rsp+3C0h+var_398]
0x18000a080  mov     [rsp+3C0h+var_380], rax
0x18000a085  lea     rcx, [rsp+3C0h+var_388]
0x18000a08a  call    InvokeUserProfileRPC__lambda_c3e8d726eb567336769114f33ed11b9b___; InvokeUserProfileRPC__lambda_c3e8d726eb567336769114f33ed11b9b_
0x18000a08f  mov     ebx, eax
0x18000a091  test    eax, eax
0x18000a093  jns     short loc_18000A0B2
0x18000a095  mov     rcx, [rbp+2C8h]; this
0x18000a09c  mov     r9d, eax; char *
0x18000a09f  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\u"...
0x18000a0a6  mov     edx, 195h; void *
0x18000a0ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a0b0  jmp     short loc_18000A0BE
0x18000a0b2  lea     rcx, [rsp+3C0h+var_370]
0x18000a0b7  call    ?Stop@?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000a0bc  xor     ebx, ebx
0x18000a0be  lea     rcx, [rsp+3C0h+var_370]; this
0x18000a0c3  call    ??1WINAPIDeleteProfile@UserenvTelemetry@@QEAA@XZ; UserenvTelemetry::WINAPIDeleteProfile::~WINAPIDeleteProfile(void)
0x18000a0c8  mov     eax, ebx
0x18000a0ca  jmp     short loc_18000A0D1
0x18000a0cc  mov     eax, 80070057h
0x18000a0d1  mov     rcx, [rbp+2C0h+var_10]
0x18000a0d8  xor     rcx, rsp; StackCookie
0x18000a0db  call    __security_check_cookie
0x18000a0e0  mov     rbx, [rsp+3C0h+arg_10]
0x18000a0e8  add     rsp, 3C0h
0x18000a0ef  pop     rbp
0x18000a0f0  retn
```
