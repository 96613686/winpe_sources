# CPickerInvoker::_CreatePickerController(HWND__ *,IPickerController * *)

- ea: `0x1800124e0`
- end: `0x18001277f`
- name: `?_CreatePickerController@CPickerInvoker@@IEAAJPEAUHWND__@@PEAPEAUIPickerController@@@Z`
- size: `671`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, HWND, struct IPickerController **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18005c578`

## callees

- `0x1800030b0`
- `0x180003d24`
- `0x1800124e0`
- `0x18001cc38`
- `0x18002e489`
- `0x18005c32c`
- `0x18005c488`
- `0x18005c5fc`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001250d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001250d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012752`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012752`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012580`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012649`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012697`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800126c4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012580`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012649`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012697`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800126c4`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180012720`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180012720`

## pseudocode

```c
__int64 __fastcall CPickerInvoker::_CreatePickerController(RTL_SRWLOCK *this, HWND a2, struct IPickerController **a3)
{
  RTL_SRWLOCK *v6; // rbx
  HRESULT AgileReference; // edi
  GUID *v8; // rdx
  __int64 v9; // rcx
  unsigned int v10; // r8d
  __int64 v11; // rdx
  HRESULT v12; // eax
  HRESULT v13; // eax
  PVOID Ptr; // rcx
  LPVOID v15; // rcx
  int ppv; // [rsp+20h] [rbp-58h]
  int ppva; // [rsp+20h] [rbp-58h]
  _BYTE v19[56]; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  int v21; // [rsp+80h] [rbp+8h] BYREF
  __int16 v22; // [rsp+84h] [rbp+Ch]
  LPVOID v23; // [rsp+90h] [rbp+18h] BYREF
  RTL_SRWLOCK *v24; // [rsp+98h] [rbp+20h]

  *a3 = 0;
  v6 = this + 7;
  v24 = this + 7;
  AcquireSRWLockExclusive(this + 7);
  if ( LOBYTE(this[8].Ptr) )
  {
    AgileReference = -2147023673;
  }
  else
  {
    v23 = 0;
    v8 = &CLSID_PickerControllerInProcServer;
    if ( !HIDWORD(this[8].Ptr) )
      v8 = &CLSID_PickerControllerLocalServer;
    if ( !memcmp_0(&CLSID_PickerControllerLocalServer, v8, 0x10u) )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
      AgileReference = CoCreateInstance(
                         &CLSID_PickerControllerLocalServer,
                         0,
                         4u,
                         &GUID_0ed2ab50_c827_4cea_adc9_2d55083b8e67,
                         &v23);
    }
    else
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
      v10 = *(_DWORD *)Feature_RedirectFilePicker__descriptor;
      if ( (*(_DWORD *)Feature_RedirectFilePicker__descriptor & 4) == 0 )
        v10 = *(_DWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_RedirectFilePicker>::GetCachedFeatureEnabledState(
                           v9,
                           v19);
      v21 = 0;
      v22 = 3;
      wil::details::ReportUsageToService(qword_1800B3960, 9837567, (v10 >> 10) & 1, (v10 >> 11) & 1, &v21, 1, 3);
      v21 = 0;
      if ( (int)Windows::Internal::Shell::Holographic::GetWindowDisplayContext(a2, v11, &v21) >= 0 && v21 == 1 )
      {
        v12 = CoCreateInstance(
                &GUID_6a30ad66_de02_407c_8ea3_b1c03e1faa87,
                0,
                1u,
                &GUID_0ed2ab50_c827_4cea_adc9_2d55083b8e67,
                &v23);
        AgileReference = v12;
        if ( v12 < 0 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x19,
            (unsigned int)"onecoreuap\\internal\\shell\\inc\\PickerHelper.h",
            (const char *)(unsigned int)v12,
            ppv);
      }
      else if ( CoCreateInstance(
                  &CLSID_PickerControllerInProcServer,
                  0,
                  1u,
                  &GUID_0ed2ab50_c827_4cea_adc9_2d55083b8e67,
                  &v23) >= 0 )
      {
        AgileReference = 0;
      }
      else
      {
        v13 = CoCreateInstance(
                &GUID_6a30ad66_de02_407c_8ea3_b1c03e1faa87,
                0,
                1u,
                &GUID_0ed2ab50_c827_4cea_adc9_2d55083b8e67,
                &v23);
        AgileReference = v13;
        if ( v13 < 0 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x20,
            (unsigned int)"onecoreuap\\internal\\shell\\inc\\PickerHelper.h",
            (const char *)(unsigned int)v13,
            ppva);
      }
    }
    if ( AgileReference >= 0 )
    {
      Ptr = this[6].Ptr;
      this[6].Ptr = 0;
      if ( Ptr )
        (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
      AgileReference = RoGetAgileReference(0, &GUID_0ed2ab50_c827_4cea_adc9_2d55083b8e67, v23, &this[6]);
    }
    v15 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v15 + 16LL))(v15);
    }
  }
  if ( v6 )
    ReleaseSRWLockExclusive(v6);
  if ( AgileReference < 0 )
    return (unsigned int)AgileReference;
  else
    return CPickerInvoker::_GetPickerController((CPickerInvoker *)this, a3);
}

```

## disassembly

```asm
0x1800124e0  mov     [rsp+arg_8], rbx
0x1800124e5  push    rbp
0x1800124e6  push    rsi
0x1800124e7  push    rdi
0x1800124e8  push    r14
0x1800124ea  push    r15
0x1800124ec  sub     rsp, 50h
0x1800124f0  mov     r14, r8
0x1800124f3  mov     rdi, rdx
0x1800124f6  mov     rsi, rcx
0x1800124f9  xor     ebp, ebp
0x1800124fb  mov     [r8], rbp
0x1800124fe  lea     rbx, [rcx+38h]
0x180012502  mov     [rsp+78h+arg_18], rbx
0x18001250a  mov     rcx, rbx; SRWLock
0x18001250d  call    cs:__imp_AcquireSRWLockExclusive
0x180012513  nop
0x180012514  cmp     [rsi+40h], bpl
0x180012518  jz      short loc_180012524
0x18001251a  mov     edi, 800704C7h
0x18001251f  jmp     loc_18001274A
0x180012524  mov     [rsp+78h+arg_10], rbp
0x18001252c  lea     r15, CLSID_PickerControllerLocalServer
0x180012533  lea     rdx, CLSID_PickerControllerInProcServer
0x18001253a  cmp     dword ptr [rsi+44h], 0
0x18001253e  cmovz   rdx, r15; Buf2
0x180012542  mov     r8d, 10h; Size
0x180012548  mov     rcx, r15; Buf1
0x18001254b  call    memcmp_0
0x180012550  lea     rcx, [rsp+78h+arg_10]
0x180012558  test    eax, eax
0x18001255a  jnz     short loc_18001258D
0x18001255c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180012561  lea     rax, [rsp+78h+arg_10]
0x180012569  mov     [rsp+78h+ppv], rax; ppv
0x18001256e  lea     r9, _GUID_0ed2ab50_c827_4cea_adc9_2d55083b8e67; riid
0x180012575  xor     edx, edx; pUnkOuter
0x180012577  mov     r8d, 4; dwClsContext
0x18001257d  mov     rcx, r15; rclsid
0x180012580  call    cs:__imp_CoCreateInstance
0x180012586  mov     edi, eax
0x180012588  jmp     loc_1800126ED
0x18001258d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180012592  mov     rax, cs:Feature_RedirectFilePicker__descriptor
0x180012599  mov     r8d, [rax]
0x18001259c  test    r8b, 4
0x1800125a0  jnz     short loc_1800125AF
0x1800125a2  lea     rdx, [rsp+78h+var_38]
0x1800125a7  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_RedirectFilePicker@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RedirectFilePicker>::GetCachedFeatureEnabledState(void)
0x1800125ac  mov     r8d, [rax]
0x1800125af  mov     [rsp+78h+arg_0], ebp
0x1800125b6  mov     [rsp+78h+arg_4], 3
0x1800125c0  mov     r9d, r8d
0x1800125c3  shr     r9d, 0Bh
0x1800125c7  and     r9d, 1
0x1800125cb  shr     r8d, 0Ah
0x1800125cf  and     r8d, 1
0x1800125d3  mov     [rsp+78h+var_48], 3
0x1800125db  mov     [rsp+78h+var_50], 1
0x1800125e3  lea     rax, [rsp+78h+arg_0]
0x1800125eb  mov     [rsp+78h+ppv], rax
0x1800125f0  mov     edx, 961BFFh
0x1800125f5  lea     rcx, qword_1800B3960
0x1800125fc  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180012601  mov     [rsp+78h+arg_0], ebp
0x180012608  lea     r8, [rsp+78h+arg_0]
0x180012610  mov     rcx, rdi
0x180012613  call    ?GetWindowDisplayContext@Holographic@Shell@Internal@Windows@@YAJPEAUHWND__@@W4ContextInspectionOptions@1234@PEAW4UserDisplayContext@1234@@Z; Windows::Internal::Shell::Holographic::GetWindowDisplayContext(HWND__ *,Windows::Internal::Shell::Holographic::ContextInspectionOptions,Windows::Internal::Shell::Holographic::UserDisplayContext *)
0x180012618  test    eax, eax
0x18001261a  js      short loc_180012674
0x18001261c  cmp     [rsp+78h+arg_0], 1
0x180012624  jnz     short loc_180012674
0x180012626  lea     rax, [rsp+78h+arg_10]
0x18001262e  mov     [rsp+78h+ppv], rax; int
0x180012633  lea     r9, _GUID_0ed2ab50_c827_4cea_adc9_2d55083b8e67; riid
0x18001263a  xor     edx, edx; pUnkOuter
0x18001263c  mov     r8d, 1; dwClsContext
0x180012642  lea     rcx, _GUID_6a30ad66_de02_407c_8ea3_b1c03e1faa87; rclsid
0x180012649  call    cs:__imp_CoCreateInstance
0x18001264f  mov     edi, eax
0x180012651  test    eax, eax
0x180012653  jns     loc_1800126ED
0x180012659  mov     rcx, [rsp+78h]; this
0x18001265e  mov     r9d, eax; char *
0x180012661  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\Picke"...
0x180012668  mov     edx, 19h; void *
0x18001266d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012672  jmp     short loc_1800126ED
0x180012674  lea     rax, [rsp+78h+arg_10]
0x18001267c  mov     [rsp+78h+ppv], rax; ppv
0x180012681  lea     r9, _GUID_0ed2ab50_c827_4cea_adc9_2d55083b8e67; riid
0x180012688  xor     edx, edx; pUnkOuter
0x18001268a  mov     r8d, 1; dwClsContext
0x180012690  lea     rcx, CLSID_PickerControllerInProcServer; rclsid
0x180012697  call    cs:__imp_CoCreateInstance
0x18001269d  test    eax, eax
0x18001269f  jns     short loc_1800126EB
0x1800126a1  lea     rax, [rsp+78h+arg_10]
0x1800126a9  mov     [rsp+78h+ppv], rax; int
0x1800126ae  lea     r9, _GUID_0ed2ab50_c827_4cea_adc9_2d55083b8e67; riid
0x1800126b5  xor     edx, edx; pUnkOuter
0x1800126b7  mov     r8d, 1; dwClsContext
0x1800126bd  lea     rcx, _GUID_6a30ad66_de02_407c_8ea3_b1c03e1faa87; rclsid
0x1800126c4  call    cs:__imp_CoCreateInstance
0x1800126ca  mov     edi, eax
0x1800126cc  test    eax, eax
0x1800126ce  jns     short loc_1800126ED
0x1800126d0  mov     rcx, [rsp+78h]; this
0x1800126d5  mov     r9d, eax; char *
0x1800126d8  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\Picke"...
0x1800126df  mov     edx, 20h ; ' '; void *
0x1800126e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800126e9  jmp     short loc_1800126ED
0x1800126eb  mov     edi, ebp
0x1800126ed  test    edi, edi
0x1800126ef  js      short loc_180012728
0x1800126f1  mov     rcx, [rsi+30h]
0x1800126f5  mov     [rsi+30h], rbp
0x1800126f9  test    rcx, rcx
0x1800126fc  jz      short loc_18001270B
0x1800126fe  mov     rax, [rcx]
0x180012701  mov     rax, [rax+10h]
0x180012705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001270a  nop
0x18001270b  lea     r9, [rsi+30h]
0x18001270f  mov     r8, [rsp+78h+arg_10]
0x180012717  lea     rdx, _GUID_0ed2ab50_c827_4cea_adc9_2d55083b8e67
0x18001271e  xor     ecx, ecx
0x180012720  call    cs:__imp_RoGetAgileReference
0x180012726  mov     edi, eax
0x180012728  mov     rcx, [rsp+78h+arg_10]
0x180012730  test    rcx, rcx
0x180012733  jz      short loc_18001274A
0x180012735  mov     [rsp+78h+arg_10], rbp
0x18001273d  mov     rax, [rcx]
0x180012740  mov     rax, [rax+10h]
0x180012744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012749  nop
0x18001274a  test    rbx, rbx
0x18001274d  jz      short loc_180012758
0x18001274f  mov     rcx, rbx; SRWLock
0x180012752  call    cs:__imp_ReleaseSRWLockExclusive
0x180012758  test    edi, edi
0x18001275a  js      short loc_180012769
0x18001275c  mov     rdx, r14; struct IPickerController **
0x18001275f  mov     rcx, rsi; this
0x180012762  call    ?_GetPickerController@CPickerInvoker@@IEAAJPEAPEAUIPickerController@@@Z; CPickerInvoker::_GetPickerController(IPickerController * *)
0x180012767  jmp     short loc_18001276B
0x180012769  mov     eax, edi
0x18001276b  mov     rbx, [rsp+78h+arg_8]
0x180012773  add     rsp, 50h
0x180012777  pop     r15
0x180012779  pop     r14
0x18001277b  pop     rdi
0x18001277c  pop     rsi
0x18001277d  pop     rbp
0x18001277e  retn
```
