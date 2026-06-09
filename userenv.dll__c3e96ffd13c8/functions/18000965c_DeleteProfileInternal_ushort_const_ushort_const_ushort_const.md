# DeleteProfileInternal(ushort const *,ushort const *,ushort const *)

- ea: `0x18000965c`
- end: `0x1800097c7`
- name: `?DeleteProfileInternal@@YAJPEBG00@Z`
- size: `363`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180009630`

## callees

- `0x180003380`
- `0x1800072a0`
- `0x18000965c`
- `0x18000cea0`
- `0x18000d9b0`
- `0x18000e330`
- `0x180011fd8`
- `0x1800124b0`
- `0x1800126f4`
- `0x1800131ac`
- `0x180013394`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800096ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800096ef`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18000970c`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18000970c`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180009706`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180009706`

## string_xrefs

- `0x180009775`: `onecore\ds\security\gina\profile\userenv\dll\profrpc.cpp`
- `0x180009715`: `WINAPIDeleteProfile`

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
0x18000965c  mov     [rsp-8+arg_10], rbx
0x180009661  push    rbp
0x180009662  lea     rbp, [rsp-2C0h]
0x18000966a  sub     rsp, 3C0h
0x180009671  mov     rax, cs:__security_cookie
0x180009678  xor     rax, rsp
0x18000967b  mov     [rbp+2C0h+var_10], rax
0x180009682  mov     rbx, r8
0x180009685  mov     [rsp+3C0h+var_390], rcx
0x18000968a  mov     [rsp+3C0h+var_398], rdx
0x18000968f  test    rcx, rcx
0x180009692  jz      loc_1800097A2
0x180009698  call    ?IsServiceSid@@YAHPEBG@Z; IsServiceSid(ushort const *)
0x18000969d  test    eax, eax
0x18000969f  jz      short loc_1800096AB
0x1800096a1  mov     eax, 80070005h
0x1800096a6  jmp     loc_1800097A7
0x1800096ab  mov     rcx, [rsp+3C0h+var_398]; unsigned __int16 *
0x1800096b0  test    rcx, rcx
0x1800096b3  jz      short loc_1800096CA
0x1800096b5  xor     r8d, r8d; unsigned __int64 *
0x1800096b8  mov     edx, 104h; unsigned __int64
0x1800096bd  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800096c2  test    eax, eax
0x1800096c4  js      loc_1800097A2
0x1800096ca  test    rbx, rbx
0x1800096cd  jnz     loc_1800097A2
0x1800096d3  xor     edx, edx; Val
0x1800096d5  mov     r8d, 20Ah; Size
0x1800096db  lea     rcx, [rbp+2C0h+ExeName]; void *
0x1800096e2  call    memset_0
0x1800096e7  mov     [rsp+3C0h+dwSize], 105h; int
0x1800096ef  call    cs:__imp_GetCurrentProcess
0x1800096f5  mov     rcx, rax; hProcess
0x1800096f8  lea     r9, [rsp+3C0h+dwSize]; lpdwSize
0x1800096fd  lea     r8, [rbp+2C0h+ExeName]; lpExeName
0x180009704  xor     edx, edx; dwFlags
0x180009706  call    cs:__imp_QueryFullProcessImageNameW
0x18000970c  call    cs:__imp_GetCommandLineW
0x180009712  mov     rbx, rax
0x180009715  lea     rdx, aWinapideletepr; "WINAPIDeleteProfile"
0x18000971c  lea     rcx, [rsp+3C0h+var_370]; struct wil::details::IFailureCallback *
0x180009721  call    ??0?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180009726  lea     rax, ??_7WINAPIDeleteProfile@UserenvTelemetry@@6B@; const UserenvTelemetry::WINAPIDeleteProfile::`vftable'
0x18000972d  mov     [rsp+3C0h+var_370], rax
0x180009732  mov     r8, rbx; unsigned __int16 *
0x180009735  lea     rdx, [rbp+2C0h+ExeName]; unsigned __int16 *
0x18000973c  lea     rcx, [rsp+3C0h+var_370]; this
0x180009741  call    ?StartActivity@WINAPIDeleteProfile@UserenvTelemetry@@QEAAXPEBG0@Z; UserenvTelemetry::WINAPIDeleteProfile::StartActivity(ushort const *,ushort const *)
0x180009746  nop
0x180009747  lea     rax, [rsp+3C0h+var_390]
0x18000974c  mov     [rsp+3C0h+var_388], rax
0x180009751  lea     rax, [rsp+3C0h+var_398]
0x180009756  mov     [rsp+3C0h+var_380], rax
0x18000975b  lea     rcx, [rsp+3C0h+var_388]
0x180009760  call    InvokeUserProfileRPC__lambda_c3e8d726eb567336769114f33ed11b9b___; InvokeUserProfileRPC__lambda_c3e8d726eb567336769114f33ed11b9b_
0x180009765  mov     ebx, eax
0x180009767  test    eax, eax
0x180009769  jns     short loc_180009788
0x18000976b  mov     rcx, [rbp+2C8h]; this
0x180009772  mov     r9d, eax; char *
0x180009775  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\u"...
0x18000977c  mov     edx, 195h; void *
0x180009781  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009786  jmp     short loc_180009794
0x180009788  lea     rcx, [rsp+3C0h+var_370]
0x18000978d  call    ?Stop@?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180009792  xor     ebx, ebx
0x180009794  lea     rcx, [rsp+3C0h+var_370]; this
0x180009799  call    ??1WINAPIDeleteProfile@UserenvTelemetry@@QEAA@XZ; UserenvTelemetry::WINAPIDeleteProfile::~WINAPIDeleteProfile(void)
0x18000979e  mov     eax, ebx
0x1800097a0  jmp     short loc_1800097A7
0x1800097a2  mov     eax, 80070057h
0x1800097a7  mov     rcx, [rbp+2C0h+var_10]
0x1800097ae  xor     rcx, rsp; StackCookie
0x1800097b1  call    __security_check_cookie
0x1800097b6  mov     rbx, [rsp+3C0h+arg_10]
0x1800097be  add     rsp, 3C0h
0x1800097c5  pop     rbp
0x1800097c6  retn
```
