# Windows::Internal::UI::StartScreen::JumpListBrokered::RuntimeClassInitialize(void)

- ea: `0x1800a022c`
- end: `0x1800a0453`
- name: `?RuntimeClassInitialize@JumpListBrokered@StartScreen@UI@Internal@Windows@@QEAAJXZ`
- size: `551`
- prototype: `__int64 __fastcall(Windows::Internal::UI::StartScreen::JumpListBrokered *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800a0134`

## callees

- `0x180008acc`
- `0x18003c5e4`
- `0x1800542a8`
- `0x180078490`
- `0x1800a022c`
- `0x1800a9328`
- `0x1800c4760`
- `0x1800fec3c`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a03a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a03a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a02aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a02ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a0303`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a0313`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a032c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a043e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a02aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a02ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a0303`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a0313`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a032c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a043e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a035d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a035d`

## string_xrefs

- `0x1800a028f`: `shell\twinui\jumplist\broker\jumplistbrokered.cpp`
- `0x1800a02e9`: `shell\twinui\jumplist\broker\jumplistbrokered.cpp`
- `0x1800a036e`: `shell\twinui\jumplist\broker\jumplistbrokered.cpp`
- `0x1800a0408`: `shell\twinui\jumplist\broker\jumplistbrokered.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Internal::UI::StartScreen::JumpListBrokered::RuntimeClassInitialize(HSTRING *this)
{
  unsigned __int16 **v2; // rdx
  int CallingProcessAppId; // eax
  unsigned __int16 **v4; // r8
  int PackageFullNameFromAppId; // eax
  HRESULT JumpList; // ebx
  void *v8; // rbx
  int v9; // eax
  unsigned int v10; // edi
  __int64 v11; // rdx
  LPVOID v12; // rdi
  __int64 (__fastcall *v13)(LPVOID, _QWORD, CallerIdentity **, _QWORD); // rbx
  DWORD CurrentProcessId; // eax
  __int64 v15; // rdx
  int ppv; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  CallerIdentity *v18; // [rsp+68h] [rbp+28h] BYREF
  LPVOID pv; // [rsp+70h] [rbp+30h] BYREF

  v18 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v18,
    0);
  CallingProcessAppId = CallerIdentity::GetCallingProcessAppId((CallerIdentity *)&v18, v2);
  pv = 0;
  if ( CallingProcessAppId < 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pv);
    JumpList = CoCreateInstance(
                 &CLSID_StartMenuCacheAndAppResolver,
                 0,
                 3u,
                 &GUID_de25675a_72de_44b4_9373_05170450c140,
                 &pv);
    if ( JumpList >= 0 )
    {
      v12 = pv;
      v13 = *(__int64 (__fastcall **)(LPVOID, _QWORD, CallerIdentity **, _QWORD))(*(_QWORD *)pv + 48LL);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v18,
        0);
      CurrentProcessId = GetCurrentProcessId();
      ppv = 0;
      JumpList = v13(v12, CurrentProcessId, &v18, 0);
      if ( JumpList >= 0 )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pv);
        goto LABEL_22;
      }
      v11 = 96;
    }
    else
    {
      v11 = 95;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"shell\\twinui\\jumplist\\broker\\jumplistbrokered.cpp",
      (const char *)(unsigned int)JumpList,
      ppv);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pv);
LABEL_5:
    if ( v18 )
      CoTaskMemFree(v18);
    return (unsigned int)JumpList;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pv,
    0);
  PackageFullNameFromAppId = CallerIdentity::GetPackageFullNameFromAppId(v18, (const unsigned __int16 *)&pv, v4);
  JumpList = PackageFullNameFromAppId;
  if ( PackageFullNameFromAppId < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x57,
      (unsigned int)"shell\\twinui\\jumplist\\broker\\jumplistbrokered.cpp",
      (const char *)(unsigned int)PackageFullNameFromAppId,
      ppv);
    if ( pv )
      CoTaskMemFree(pv);
    goto LABEL_5;
  }
  v8 = pv;
  v9 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(this + 9);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x58,
      (unsigned int)"shell\\twinui\\jumplist\\broker\\jumplistbrokered.cpp",
      (const char *)(unsigned int)v9,
      ppv);
    if ( v8 )
      CoTaskMemFree(v8);
    if ( v18 )
      CoTaskMemFree(v18);
    return v10;
  }
  if ( v8 )
    CoTaskMemFree(v8);
LABEL_22:
  pv = v18;
  JumpList = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(this + 8);
  if ( JumpList < 0 )
  {
    v15 = 98;
LABEL_24:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"shell\\twinui\\jumplist\\broker\\jumplistbrokered.cpp",
      (const char *)(unsigned int)JumpList,
      ppv);
    goto LABEL_5;
  }
  JumpList = Windows::Internal::UI::StartScreen::JumpListBrokered::LoadJumpList((Windows::Internal::UI::StartScreen::JumpListBrokered *)this);
  if ( JumpList < 0 )
  {
    v15 = 99;
    goto LABEL_24;
  }
  if ( v18 )
    CoTaskMemFree(v18);
  return 0;
}

```

## disassembly

```asm
0x1800a022c  mov     [rsp-18h+arg_0], rbx
0x1800a0231  push    rbp
0x1800a0232  push    rsi
0x1800a0233  push    rdi
0x1800a0234  mov     rbp, rsp
0x1800a0237  sub     rsp, 40h
0x1800a023b  mov     rsi, rcx
0x1800a023e  mov     [rbp+arg_8], 0
0x1800a0246  xor     edx, edx
0x1800a0248  lea     rcx, [rbp+arg_8]
0x1800a024c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800a0251  lea     rcx, [rbp+arg_8]; this
0x1800a0255  call    ?GetCallingProcessAppId@CallerIdentity@@YAJPEAPEAG@Z; CallerIdentity::GetCallingProcessAppId(ushort * *)
0x1800a025a  mov     [rbp+pv], 0
0x1800a0262  test    eax, eax
0x1800a0264  js      loc_1800A0337
0x1800a026a  xor     edx, edx
0x1800a026c  lea     rcx, [rbp+pv]
0x1800a0270  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800a0275  lea     rdx, [rbp+pv]; unsigned __int16 *
0x1800a0279  mov     rcx, [rbp+arg_8]; this
0x1800a027d  call    ?GetPackageFullNameFromAppId@CallerIdentity@@YAJPEBGPEAPEAG@Z; CallerIdentity::GetPackageFullNameFromAppId(ushort const *,ushort * *)
0x1800a0282  mov     ebx, eax
0x1800a0284  test    eax, eax
0x1800a0286  jns     short loc_1800A02C7
0x1800a0288  mov     rcx, [rbp+18h]; this
0x1800a028c  mov     r9d, eax; char *
0x1800a028f  lea     r8, aShellTwinuiJum; "shell\\twinui\\jumplist\\broker\\jumpli"...
0x1800a0296  mov     edx, 57h ; 'W'; void *
0x1800a029b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a02a0  nop
0x1800a02a1  mov     rcx, [rbp+pv]; pv
0x1800a02a5  test    rcx, rcx
0x1800a02a8  jz      short loc_1800A02B1
0x1800a02aa  call    cs:__imp_CoTaskMemFree
0x1800a02b0  nop
0x1800a02b1  mov     rcx, [rbp+arg_8]; pv
0x1800a02b5  test    rcx, rcx
0x1800a02b8  jz      short loc_1800A02C0
0x1800a02ba  call    cs:__imp_CoTaskMemFree
0x1800a02c0  mov     eax, ebx
0x1800a02c2  jmp     loc_1800A0446
0x1800a02c7  mov     rbx, [rbp+pv]
0x1800a02cb  mov     [rbp+pv], rbx
0x1800a02cf  lea     rcx, [rsi+48h]; string
0x1800a02d3  lea     rdx, [rbp+pv]
0x1800a02d7  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x1800a02dc  mov     edi, eax
0x1800a02de  test    eax, eax
0x1800a02e0  jns     short loc_1800A0320
0x1800a02e2  mov     rcx, [rbp+18h]; this
0x1800a02e6  mov     r9d, eax; char *
0x1800a02e9  lea     r8, aShellTwinuiJum; "shell\\twinui\\jumplist\\broker\\jumpli"...
0x1800a02f0  mov     edx, 58h ; 'X'; void *
0x1800a02f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a02fa  nop
0x1800a02fb  test    rbx, rbx
0x1800a02fe  jz      short loc_1800A030A
0x1800a0300  mov     rcx, rbx; pv
0x1800a0303  call    cs:__imp_CoTaskMemFree
0x1800a0309  nop
0x1800a030a  mov     rcx, [rbp+arg_8]; pv
0x1800a030e  test    rcx, rcx
0x1800a0311  jz      short loc_1800A0319
0x1800a0313  call    cs:__imp_CoTaskMemFree
0x1800a0319  mov     eax, edi
0x1800a031b  jmp     loc_1800A0446
0x1800a0320  test    rbx, rbx
0x1800a0323  jz      loc_1800A03E8
0x1800a0329  mov     rcx, rbx; pv
0x1800a032c  call    cs:__imp_CoTaskMemFree
0x1800a0332  jmp     loc_1800A03E8
0x1800a0337  lea     rcx, [rbp+pv]
0x1800a033b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a0340  lea     rax, [rbp+pv]
0x1800a0344  mov     [rsp+40h+ppv], rax; int
0x1800a0349  lea     r9, _GUID_de25675a_72de_44b4_9373_05170450c140; riid
0x1800a0350  xor     edx, edx; pUnkOuter
0x1800a0352  lea     r8d, [rdx+3]; dwClsContext
0x1800a0356  lea     rcx, CLSID_StartMenuCacheAndAppResolver; rclsid
0x1800a035d  call    cs:__imp_CoCreateInstance
0x1800a0363  mov     ebx, eax
0x1800a0365  test    eax, eax
0x1800a0367  jns     short loc_1800A0390
0x1800a0369  mov     edx, 5Fh ; '_'; void *
0x1800a036e  lea     r8, aShellTwinuiJum; "shell\\twinui\\jumplist\\broker\\jumpli"...
0x1800a0375  mov     r9d, ebx; char *
0x1800a0378  mov     rcx, [rbp+18h]; this
0x1800a037c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0381  nop
0x1800a0382  lea     rcx, [rbp+pv]
0x1800a0386  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a038b  jmp     loc_1800A02B1
0x1800a0390  mov     rdi, [rbp+pv]
0x1800a0394  mov     rax, [rdi]
0x1800a0397  mov     rbx, [rax+30h]
0x1800a039b  xor     edx, edx
0x1800a039d  lea     rcx, [rbp+arg_8]
0x1800a03a1  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800a03a6  call    cs:__imp_GetCurrentProcessId
0x1800a03ac  mov     [rsp+40h+var_18], 0
0x1800a03b5  mov     [rsp+40h+ppv], 0; int
0x1800a03be  xor     r9d, r9d
0x1800a03c1  lea     r8, [rbp+arg_8]
0x1800a03c5  mov     edx, eax
0x1800a03c7  mov     rcx, rdi
0x1800a03ca  mov     rax, rbx
0x1800a03cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a03d2  mov     ebx, eax
0x1800a03d4  test    eax, eax
0x1800a03d6  jns     short loc_1800A03DF
0x1800a03d8  mov     edx, 60h ; '`'
0x1800a03dd  jmp     short loc_1800A036E
0x1800a03df  lea     rcx, [rbp+pv]
0x1800a03e3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a03e8  mov     rax, [rbp+arg_8]
0x1800a03ec  mov     [rbp+pv], rax
0x1800a03f0  lea     rcx, [rsi+40h]; string
0x1800a03f4  lea     rdx, [rbp+pv]
0x1800a03f8  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x1800a03fd  mov     ebx, eax
0x1800a03ff  test    eax, eax
0x1800a0401  jns     short loc_1800A0420
0x1800a0403  mov     edx, 62h ; 'b'; void *
0x1800a0408  lea     r8, aShellTwinuiJum; "shell\\twinui\\jumplist\\broker\\jumpli"...
0x1800a040f  mov     r9d, ebx; char *
0x1800a0412  mov     rcx, [rbp+18h]; this
0x1800a0416  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a041b  jmp     loc_1800A02B1
0x1800a0420  mov     rcx, rsi; this
0x1800a0423  call    ?LoadJumpList@JumpListBrokered@StartScreen@UI@Internal@Windows@@AEAAJXZ; Windows::Internal::UI::StartScreen::JumpListBrokered::LoadJumpList(void)
0x1800a0428  mov     ebx, eax
0x1800a042a  test    eax, eax
0x1800a042c  jns     short loc_1800A0435
0x1800a042e  mov     edx, 63h ; 'c'
0x1800a0433  jmp     short loc_1800A0408
0x1800a0435  mov     rcx, [rbp+arg_8]; pv
0x1800a0439  test    rcx, rcx
0x1800a043c  jz      short loc_1800A0444
0x1800a043e  call    cs:__imp_CoTaskMemFree
0x1800a0444  xor     eax, eax
0x1800a0446  mov     rbx, [rsp+40h+arg_0]
0x1800a044b  add     rsp, 40h
0x1800a044f  pop     rdi
0x1800a0450  pop     rsi
0x1800a0451  pop     rbp
0x1800a0452  retn
```
