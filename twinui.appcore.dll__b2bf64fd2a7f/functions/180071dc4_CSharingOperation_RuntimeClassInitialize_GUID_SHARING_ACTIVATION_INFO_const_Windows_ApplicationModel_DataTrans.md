# CSharingOperation::RuntimeClassInitialize(_GUID,SHARING_ACTIVATION_INFO const &,Windows::ApplicationModel::DataTransfer::IDataPackage *,Windows::Foundation::Collections::IVectorView<HSTRING__ *> *,IDataTransferBroker *)

- ea: `0x180071dc4`
- end: `0x1800722d7`
- name: `?RuntimeClassInitialize@CSharingOperation@@QEAAJU_GUID@@AEBUSHARING_ACTIVATION_INFO@@PEAUIDataPackage@DataTransfer@ApplicationModel@Windows@@PEAU?$IVectorView@PEAUHSTRING__@@@Collections@Foundation@7@PEAUIDataTransferBroker@@@Z`
- size: `1299`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180070990`

## callees

- `0x180003d24`
- `0x1800040e0`
- `0x1800177a4`
- `0x18001cc38`
- `0x180026498`
- `0x180033d5c`
- `0x180063068`
- `0x180070498`
- `0x180070684`
- `0x180070828`
- `0x180071dc4`
- `0x180072534`
- `0x18007283c`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072091`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072113`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072123`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007218e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007219e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800721f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072208`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072236`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072246`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072091`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072113`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072123`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007218e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007219e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800721f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072208`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072236`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072246`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007227f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180072291`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007227f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180072291`
- `ContactActivation!DeserializeContactFromString` at `0x180072152`
- `ContactActivation!DeserializeContactFromString` at `0x180072152`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180071f1b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180071f1b`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180071ed3`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180071ed3`

## string_xrefs

- `0x1800720c5`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CSharingOperation::RuntimeClassInitialize(
        __int64 a1,
        _OWORD *a2,
        const unsigned __int16 **a3,
        __int64 a4,
        void *a5,
        __int64 a6)
{
  const struct _GUID *v9; // r13
  const unsigned __int16 *v10; // rdx
  HRESULT AgileReference; // esi
  const unsigned __int16 *v12; // rdx
  const unsigned __int16 *v13; // rdx
  __int64 (__fastcall *v14)(__int64, __int64 *); // rbx
  LPVOID v15; // rsi
  __int64 (__fastcall *v16)(LPVOID, SID *, GUID *, __int64); // rdi
  __int64 v17; // rbx
  __int64 v18; // rcx
  int v19; // ebx
  __int64 v20; // rdx
  __int64 result; // rax
  __int64 v22; // rcx
  int v23; // eax
  const char *v24; // r9
  int i; // eax
  __int64 (__fastcall *v26)(void *, _QWORD, HSTRING *); // rbx
  int v27; // eax
  int v28; // eax
  unsigned int v29; // ebx
  int v30; // eax
  unsigned int v31; // ebx
  int v32; // eax
  unsigned int v33; // ebx
  PCWSTR StringRawBuffer; // rdi
  PCWSTR v35; // rbx
  char *v36; // rax
  int v37; // edx
  int v38; // r8d
  int ppv; // [rsp+20h] [rbp-88h]
  void *v40; // [rsp+40h] [rbp-68h]
  unsigned int v41; // [rsp+48h] [rbp-60h]
  HSTRING string; // [rsp+50h] [rbp-58h] BYREF
  _BYTE v43[8]; // [rsp+58h] [rbp-50h] BYREF
  int v44; // [rsp+60h] [rbp-48h]
  HSTRING v45; // [rsp+68h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]
  LPVOID v47; // [rsp+B0h] [rbp+8h] BYREF
  __int64 v48; // [rsp+B8h] [rbp+10h] BYREF
  __int64 v49; // [rsp+C0h] [rbp+18h] BYREF

  v9 = (const struct _GUID *)(a1 + 176);
  *(_OWORD *)(a1 + 176) = *a2;
  v10 = a3[2];
  if ( !v10 )
    goto LABEL_18;
  AgileReference = Windows::Internal::String::_InitializeHelper((HSTRING *)(a1 + 152), v10);
  if ( AgileReference < 0 )
    goto LABEL_19;
  v12 = a3[4];
  if ( !v12 )
    goto LABEL_18;
  AgileReference = Windows::Internal::String::_InitializeHelper((HSTRING *)(a1 + 160), v12);
  if ( AgileReference < 0 )
    goto LABEL_19;
  v13 = a3[3];
  if ( v13 )
  {
    AgileReference = Windows::Internal::String::_InitializeHelper((HSTRING *)(a1 + 144), v13);
    if ( AgileReference >= 0 )
    {
      if ( !*a3
        || (AgileReference = Windows::Internal::String::_InitializeHelper((HSTRING *)(a1 + 168), *a3),
            AgileReference >= 0) )
      {
        v48 = 0;
        v14 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a4 + 48LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
        AgileReference = v14(a4, &v48);
        if ( AgileReference >= 0 )
        {
          wil::com_ptr_t<IAgileReference,wil::err_returncode_policy>::reset(a1 + 208);
          AgileReference = RoGetAgileReference(0, &GUID_7b840471_5900_4d85_a90b_10cb85fe3552, v48, a1 + 208);
          if ( AgileReference >= 0 )
          {
            v47 = 0;
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
            AgileReference = CoCreateInstance(
                               &GUID_6b3b8d23_fa8d_40b9_8dbd_b950333e2c52,
                               0,
                               0x404u,
                               &GUID_6d5140c1_7436_11ce_8034_00aa006009fa,
                               &v47);
            if ( AgileReference >= 0 )
            {
              v15 = v47;
              v16 = *(__int64 (__fastcall **)(LPVOID, SID *, GUID *, __int64))(*(_QWORD *)v47 + 24LL);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a1 + 192);
              AgileReference = v16(v15, &SID_RunningShareManager, &GUID_9c3b7f41_b036_42d5_8634_e7da8b1bc329, a1 + 192);
            }
            v17 = a6;
            if ( a6 && *(_QWORD *)(a1 + 200) != a6 )
            {
              v49 = a6;
              Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v49);
              v49 = *(_QWORD *)(a1 + 200);
              *(_QWORD *)(a1 + 200) = v17;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
            }
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
          }
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
      }
    }
  }
  else
  {
LABEL_18:
    AgileReference = -2147467261;
  }
LABEL_19:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a1 + 216);
  v19 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::ApplicationModel::Contacts::Contact,Windows::Foundation::Collections::Internal::AgileVector<Windows::ApplicationModel::Contacts::Contact *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::ApplicationModel::Contacts::Contact *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::Contacts::Contact *>,0>>(
          v18,
          a1 + 216);
  if ( v19 < 0 )
  {
    v20 = 80;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecoreuap\\shell\\twinui\\sharinganddevices\\platform\\sharingtargetcallback.cpp",
      (const char *)(unsigned int)v19,
      ppv);
    return (unsigned int)v19;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a1 + 224);
  v23 = Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(
          v22,
          a1 + 224);
  v19 = v23;
  if ( v23 < 0 )
  {
    v20 = 81;
    goto LABEL_21;
  }
  try
  {
    if ( a5 )
    {
      v47 = a5;
      v40 = a5;
      v41 = 0;
      string = 0;
      wil::vector_range<Windows::Foundation::Collections::IVectorView<HSTRING__ *>,wil::err_exception_policy>::end(
        &v47,
        v43);
      for ( i = 0; i != v44; i = ++v41 )
      {
        v26 = *(__int64 (__fastcall **)(void *, _QWORD, HSTRING *))(*(_QWORD *)v40 + 48LL);
        WindowsDeleteString(string);
        string = 0;
        v27 = v26(v40, v41, &string);
        if ( v27 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1CBE,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
            (const char *)(unsigned int)v27,
            ppv);
        v28 = (*(__int64 (__fastcall **)(_QWORD, HSTRING))(**(_QWORD **)(a1 + 224) + 104LL))(
                *(_QWORD *)(a1 + 224),
                string);
        v29 = v28;
        if ( v28 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x59,
            (unsigned int)"onecoreuap\\shell\\twinui\\sharinganddevices\\platform\\sharingtargetcallback.cpp",
            (const char *)(unsigned int)v28,
            ppv);
          WindowsDeleteString(v45);
          v45 = 0;
          WindowsDeleteString(string);
          return v29;
        }
        v47 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
        v30 = DeserializeContactFromString(string, &v47);
        v31 = v30;
        if ( v30 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5C,
            (unsigned int)"onecoreuap\\shell\\twinui\\sharinganddevices\\platform\\sharingtargetcallback.cpp",
            (const char *)(unsigned int)v30,
            ppv);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
          WindowsDeleteString(v45);
          v45 = 0;
          WindowsDeleteString(string);
          return v31;
        }
        v32 = (*(__int64 (__fastcall **)(_QWORD, LPVOID))(**(_QWORD **)(a1 + 216) + 104LL))(*(_QWORD *)(a1 + 216), v47);
        v33 = v32;
        if ( v32 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5E,
            (unsigned int)"onecoreuap\\shell\\twinui\\sharinganddevices\\platform\\sharingtargetcallback.cpp",
            (const char *)(unsigned int)v32,
            ppv);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
          WindowsDeleteString(v45);
          v45 = 0;
          WindowsDeleteString(string);
          return v33;
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
      }
      WindowsDeleteString(v45);
      v45 = 0;
      WindowsDeleteString(string);
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 168), 0);
      v35 = WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 152), 0);
      v36 = GuidRepA(v9);
      WPP_SF_dsSS(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        v37,
        v38,
        AgileReference,
        (__int64)v36,
        (__int64)v35,
        (__int64)StringRawBuffer);
    }
    result = (unsigned int)AgileReference;
  }
  catch ( ... )
  {
    LODWORD(v47) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x61,
                     (unsigned int)"onecoreuap\\shell\\twinui\\sharinganddevices\\platform\\sharingtargetcallback.cpp",
                     v24);
    return (unsigned int)v47;
  }
  return result;
}

```

## disassembly

```asm
0x180071dc4  push    rbx
0x180071dc6  push    rsi
0x180071dc7  push    rdi
0x180071dc8  push    r12
0x180071dca  push    r13
0x180071dcc  push    r14
0x180071dce  push    r15
0x180071dd0  sub     rsp, 70h
0x180071dd4  mov     rdi, r9
0x180071dd7  mov     rbx, r8
0x180071dda  mov     r14, rcx
0x180071ddd  xor     r12d, r12d
0x180071de0  lea     r13, [rcx+0B0h]
0x180071de7  movaps  xmm0, xmmword ptr [rdx]
0x180071dea  movdqu  xmmword ptr [r13+0], xmm0
0x180071df0  mov     rdx, [r8+10h]; unsigned __int16 *
0x180071df4  test    rdx, rdx
0x180071df7  jz      loc_180071FCF
0x180071dfd  add     rcx, 98h; this
0x180071e04  call    ?_InitializeHelper@String@Internal@Windows@@AEAAJPEBG@Z; Windows::Internal::String::_InitializeHelper(ushort const *)
0x180071e09  mov     esi, eax
0x180071e0b  test    eax, eax
0x180071e0d  js      loc_180071FD4
0x180071e13  mov     rdx, [rbx+20h]; unsigned __int16 *
0x180071e17  test    rdx, rdx
0x180071e1a  jz      loc_180071FCF
0x180071e20  lea     rcx, [r14+0A0h]; this
0x180071e27  call    ?_InitializeHelper@String@Internal@Windows@@AEAAJPEBG@Z; Windows::Internal::String::_InitializeHelper(ushort const *)
0x180071e2c  mov     esi, eax
0x180071e2e  test    eax, eax
0x180071e30  js      loc_180071FD4
0x180071e36  mov     rdx, [rbx+18h]; unsigned __int16 *
0x180071e3a  test    rdx, rdx
0x180071e3d  jz      loc_180071FCF
0x180071e43  lea     rcx, [r14+90h]; this
0x180071e4a  call    ?_InitializeHelper@String@Internal@Windows@@AEAAJPEBG@Z; Windows::Internal::String::_InitializeHelper(ushort const *)
0x180071e4f  mov     esi, eax
0x180071e51  test    eax, eax
0x180071e53  js      loc_180071FD4
0x180071e59  mov     rdx, [rbx]; unsigned __int16 *
0x180071e5c  test    rdx, rdx
0x180071e5f  jz      short loc_180071E77
0x180071e61  lea     rcx, [r14+0A8h]; this
0x180071e68  call    ?_InitializeHelper@String@Internal@Windows@@AEAAJPEBG@Z; Windows::Internal::String::_InitializeHelper(ushort const *)
0x180071e6d  mov     esi, eax
0x180071e6f  test    eax, eax
0x180071e71  js      loc_180071FD4
0x180071e77  mov     [rsp+0A8h+arg_8], r12
0x180071e7f  mov     rax, [rdi]
0x180071e82  mov     rbx, [rax+30h]
0x180071e86  lea     rcx, [rsp+0A8h+arg_8]
0x180071e8e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180071e93  lea     rdx, [rsp+0A8h+arg_8]
0x180071e9b  mov     rcx, rdi
0x180071e9e  mov     rax, rbx
0x180071ea1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071ea6  mov     esi, eax
0x180071ea8  test    eax, eax
0x180071eaa  js      loc_180071FC0
0x180071eb0  lea     rbx, [r14+0D0h]
0x180071eb7  mov     rcx, rbx
0x180071eba  call    ?reset@?$com_ptr_t@UIAgileReference@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IAgileReference,wil::err_returncode_policy>::reset(void)
0x180071ebf  mov     r9, rbx
0x180071ec2  mov     r8, [rsp+0A8h+arg_8]
0x180071eca  lea     rdx, _GUID_7b840471_5900_4d85_a90b_10cb85fe3552
0x180071ed1  xor     ecx, ecx
0x180071ed3  call    cs:__imp_RoGetAgileReference
0x180071ed9  mov     esi, eax
0x180071edb  test    eax, eax
0x180071edd  js      loc_180071FC0
0x180071ee3  mov     [rsp+0A8h+arg_0], r12
0x180071eeb  lea     rcx, [rsp+0A8h+arg_0]
0x180071ef3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180071ef8  lea     rax, [rsp+0A8h+arg_0]
0x180071f00  mov     [rsp+0A8h+ppv], rax; ppv
0x180071f05  lea     r9, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa; riid
0x180071f0c  xor     edx, edx; pUnkOuter
0x180071f0e  mov     r8d, 404h; dwClsContext
0x180071f14  lea     rcx, _GUID_6b3b8d23_fa8d_40b9_8dbd_b950333e2c52; rclsid
0x180071f1b  call    cs:__imp_CoCreateInstance
0x180071f21  mov     esi, eax
0x180071f23  test    eax, eax
0x180071f25  js      short loc_180071F63
0x180071f27  mov     rsi, [rsp+0A8h+arg_0]
0x180071f2f  mov     rax, [rsi]
0x180071f32  mov     rdi, [rax+18h]
0x180071f36  lea     rbx, [r14+0C0h]
0x180071f3d  mov     rcx, rbx
0x180071f40  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180071f45  mov     r9, rbx
0x180071f48  lea     r8, _GUID_9c3b7f41_b036_42d5_8634_e7da8b1bc329
0x180071f4f  lea     rdx, SID_RunningShareManager
0x180071f56  mov     rcx, rsi
0x180071f59  mov     rax, rdi
0x180071f5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071f61  mov     esi, eax
0x180071f63  mov     rbx, [rsp+0A8h+arg_28]
0x180071f6b  test    rbx, rbx
0x180071f6e  jz      short loc_180071FB2
0x180071f70  cmp     [r14+0C8h], rbx
0x180071f77  jz      short loc_180071FB2
0x180071f79  mov     [rsp+0A8h+arg_10], rbx
0x180071f81  lea     rcx, [rsp+0A8h+arg_10]
0x180071f89  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180071f8e  mov     rax, [r14+0C8h]
0x180071f95  mov     [rsp+0A8h+arg_10], rax
0x180071f9d  mov     [r14+0C8h], rbx
0x180071fa4  lea     rcx, [rsp+0A8h+arg_10]
0x180071fac  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180071fb1  nop
0x180071fb2  lea     rcx, [rsp+0A8h+arg_0]
0x180071fba  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180071fbf  nop
0x180071fc0  lea     rcx, [rsp+0A8h+arg_8]
0x180071fc8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180071fcd  jmp     short loc_180071FD4
0x180071fcf  mov     esi, 80004003h
0x180071fd4  lea     r15, [r14+0D8h]
0x180071fdb  mov     rcx, r15
0x180071fde  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180071fe3  mov     rdx, r15
0x180071fe6  call    ??$CreateExternalObjectVector@VContact@Contacts@ApplicationModel@Windows@@V?$AgileVector@PEAVContact@Contacts@ApplicationModel@Windows@@U?$DefaultEqualityPredicate@PEAVContact@Contacts@ApplicationModel@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVContact@Contacts@ApplicationModel@Windows@@@6784@$0A@@Internal@Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVContact@Contacts@ApplicationModel@Windows@@U?$DefaultEqualityPredicate@PEAVContact@Contacts@ApplicationModel@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVContact@Contacts@ApplicationModel@Windows@@@6784@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::ApplicationModel::Contacts::Contact,Windows::Foundation::Collections::Internal::AgileVector<Windows::ApplicationModel::Contacts::Contact *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::ApplicationModel::Contacts::Contact *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::Contacts::Contact *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::ApplicationModel::Contacts::Contact *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::ApplicationModel::Contacts::Contact *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::Contacts::Contact *>,0> * *)
0x180071feb  mov     ebx, eax
0x180071fed  test    eax, eax
0x180071fef  jns     short loc_180072014
0x180071ff1  mov     edx, 50h ; 'P'; void *
0x180071ff6  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\twinui\\sharingandde"...
0x180071ffd  mov     r9d, ebx; char *
0x180072000  mov     rcx, [rsp+0A8h]; this
0x180072008  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007200d  mov     eax, ebx
0x18007200f  jmp     loc_1800722C6
0x180072014  lea     r12, [r14+0E0h]
0x18007201b  mov     rcx, r12
0x18007201e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180072023  mov     rdx, r12
0x180072026  call    ??$CreateExternalVector@PEAUHSTRING__@@V?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@PEAUHSTRING__@@@234@@ZPEAPEAV?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<HSTRING__ *> * *),Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0> * *)
0x18007202b  mov     ebx, eax
0x18007202d  xor     edi, edi
0x18007202f  test    eax, eax
0x180072031  jns     short loc_180072038
0x180072033  lea     edx, [rdi+51h]
0x180072036  jmp     short loc_180071FF6
0x180072038  mov     rax, [rsp+0A8h+arg_20]
0x180072040  test    rax, rax
0x180072043  jz      loc_180072257
0x180072049  mov     [rsp+0A8h+arg_0], rax
0x180072051  mov     [rsp+0A8h+var_68], rax
0x180072056  mov     [rsp+0A8h+var_60], edi
0x18007205a  mov     [rsp+0A8h+string], rdi
0x18007205f  lea     rdx, [rsp+0A8h+var_50]
0x180072064  lea     rcx, [rsp+0A8h+arg_0]
0x18007206c  call    ?end@?$vector_range@U?$IVectorView@PEAUHSTRING__@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA?AVvector_iterator@12@XZ; wil::vector_range<Windows::Foundation::Collections::IVectorView<HSTRING__ *>,wil::err_exception_policy>::end(void)
0x180072071  nop
0x180072072  mov     eax, [rsp+0A8h+var_60]
0x180072076  cmp     eax, [rsp+0A8h+var_48]
0x18007207a  jz      loc_180072231
0x180072080  mov     rdi, [rsp+0A8h+var_68]
0x180072085  mov     rax, [rdi]
0x180072088  mov     rbx, [rax+30h]
0x18007208c  mov     rcx, [rsp+0A8h+string]; string
0x180072091  call    cs:__imp_WindowsDeleteString
0x180072097  mov     [rsp+0A8h+string], 0
0x1800720a0  lea     r8, [rsp+0A8h+string]
0x1800720a5  mov     edx, [rsp+0A8h+var_60]
0x1800720a9  mov     rcx, rdi
0x1800720ac  mov     rax, rbx
0x1800720af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800720b4  mov     rcx, [rsp+0A8h]; this
0x1800720bc  xor     edi, edi
0x1800720be  test    eax, eax
0x1800720c0  jns     short loc_1800720D6
0x1800720c2  mov     r9d, eax; char *
0x1800720c5  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800720cc  mov     edx, 1CBEh; void *
0x1800720d1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800720d6  mov     rcx, [r12]
0x1800720da  mov     rax, [rcx]
0x1800720dd  mov     rdx, [rsp+0A8h+string]
0x1800720e2  mov     rax, [rax+68h]
0x1800720e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800720eb  mov     ebx, eax
0x1800720ed  test    eax, eax
0x1800720ef  jns     short loc_180072130
0x1800720f1  mov     rcx, [rsp+0A8h]; this
0x1800720f9  mov     r9d, eax; char *
0x1800720fc  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\twinui\\sharingandde"...
0x180072103  mov     edx, 59h ; 'Y'; void *
0x180072108  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007210d  nop
0x18007210e  mov     rcx, [rsp+0A8h+var_40]; string
0x180072113  call    cs:__imp_WindowsDeleteString
0x180072119  mov     [rsp+0A8h+var_40], rdi
0x18007211e  mov     rcx, [rsp+0A8h+string]; string
0x180072123  call    cs:__imp_WindowsDeleteString
0x180072129  mov     eax, ebx
0x18007212b  jmp     loc_1800722C6
0x180072130  mov     [rsp+0A8h+arg_0], rdi
0x180072138  lea     rcx, [rsp+0A8h+arg_0]
0x180072140  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180072145  lea     rdx, [rsp+0A8h+arg_0]
0x18007214d  mov     rcx, [rsp+0A8h+string]
0x180072152  call    cs:__imp_DeserializeContactFromString
0x180072158  mov     ebx, eax
0x18007215a  test    eax, eax
0x18007215c  jns     short loc_1800721AB
0x18007215e  mov     rcx, [rsp+0A8h]; this
0x180072166  mov     r9d, eax; char *
0x180072169  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\twinui\\sharingandde"...
0x180072170  mov     edx, 5Ch ; '\'; void *
0x180072175  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007217a  nop
0x18007217b  lea     rcx, [rsp+0A8h+arg_0]
0x180072183  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180072188  nop
0x180072189  mov     rcx, [rsp+0A8h+var_40]; string
0x18007218e  call    cs:__imp_WindowsDeleteString
0x180072194  mov     [rsp+0A8h+var_40], rdi
0x180072199  mov     rcx, [rsp+0A8h+string]; string
0x18007219e  call    cs:__imp_WindowsDeleteString
0x1800721a4  mov     eax, ebx
0x1800721a6  jmp     loc_1800722C6
0x1800721ab  mov     rcx, [r15]
0x1800721ae  mov     rax, [rcx]
0x1800721b1  mov     rdx, [rsp+0A8h+arg_0]
0x1800721b9  mov     rax, [rax+68h]
0x1800721bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800721c2  mov     ebx, eax
0x1800721c4  test    eax, eax
0x1800721c6  jns     short loc_180072215
0x1800721c8  mov     rcx, [rsp+0A8h]; this
0x1800721d0  mov     r9d, eax; char *
0x1800721d3  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\twinui\\sharingandde"...
0x1800721da  mov     edx, 5Eh ; '^'; void *
0x1800721df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800721e4  nop
0x1800721e5  lea     rcx, [rsp+0A8h+arg_0]
0x1800721ed  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800721f2  nop
0x1800721f3  mov     rcx, [rsp+0A8h+var_40]; string
0x1800721f8  call    cs:__imp_WindowsDeleteString
0x1800721fe  mov     [rsp+0A8h+var_40], rdi
0x180072203  mov     rcx, [rsp+0A8h+string]; string
0x180072208  call    cs:__imp_WindowsDeleteString
0x18007220e  mov     eax, ebx
0x180072210  jmp     loc_1800722C6
0x180072215  lea     rcx, [rsp+0A8h+arg_0]
0x18007221d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180072222  mov     eax, [rsp+0A8h+var_60]
0x180072226  inc     eax
0x180072228  mov     [rsp+0A8h+var_60], eax
0x18007222c  jmp     loc_180072076
0x180072231  mov     rcx, [rsp+0A8h+var_40]; string
0x180072236  call    cs:__imp_WindowsDeleteString
0x18007223c  mov     [rsp+0A8h+var_40], rdi
0x180072241  mov     rcx, [rsp+0A8h+string]; string
0x180072246  call    cs:__imp_WindowsDeleteString
0x18007224c  jmp     short loc_180072257
0x18007224e  mov     eax, dword ptr [rsp+0A8h+arg_0]
0x180072255  jmp     short loc_1800722C6
0x180072257  lea     rcx, WPP_GLOBAL_Control
0x18007225e  mov     rax, cs:WPP_GLOBAL_Control
0x180072265  cmp     rax, rcx
0x180072268  jz      short loc_1800722C4
0x18007226a  test    byte ptr [rax+44h], 1
0x18007226e  jz      short loc_1800722C4
0x180072270  cmp     byte ptr [rax+41h], 4
0x180072274  jb      short loc_1800722C4
0x180072276  xor     edx, edx; length
0x180072278  mov     rcx, [r14+0A8h]; string
0x18007227f  call    cs:__imp_WindowsGetStringRawBuffer
0x180072285  mov     rdi, rax
0x180072288  xor     edx, edx; length
0x18007228a  mov     rcx, [r14+98h]; string
0x180072291  call    cs:__imp_WindowsGetStringRawBuffer
0x180072297  mov     rbx, rax
0x18007229a  mov     rcx, r13; struct _GUID *
0x18007229d  call    ?GuidRepA@@YAPEADAEBU_GUID@@@Z; GuidRepA(_GUID const &)
0x1800722a2  mov     [rsp+0A8h+var_78], rdi
0x1800722a7  mov     [rsp+0A8h+var_80], rbx
0x1800722ac  mov     [rsp+0A8h+ppv], rax
0x1800722b1  mov     r9d, esi
0x1800722b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800722bb  mov     rcx, [rcx+38h]
0x1800722bf  call    WPP_SF_dsSS
0x1800722c4  mov     eax, esi
0x1800722c6  add     rsp, 70h
0x1800722ca  pop     r15
0x1800722cc  pop     r14
0x1800722ce  pop     r13
0x1800722d0  pop     r12
0x1800722d2  pop     rdi
0x1800722d3  pop     rsi
0x1800722d4  pop     rbx
0x1800722d5  retn
```
