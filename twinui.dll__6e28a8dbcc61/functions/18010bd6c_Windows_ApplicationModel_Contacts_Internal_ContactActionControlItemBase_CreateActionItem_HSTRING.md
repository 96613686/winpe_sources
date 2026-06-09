# Windows::ApplicationModel::Contacts::Internal::ContactActionControlItemBase::_CreateActionItem(HSTRING__ *)

- ea: `0x18010bd6c`
- end: `0x18010c07c`
- name: `?_CreateActionItem@ContactActionControlItemBase@Internal@Contacts@ApplicationModel@Windows@@IEAAXPEAUHSTRING__@@@Z`
- size: `784`
- prototype: `void __fastcall(Windows::ApplicationModel::Contacts::Internal::ContactActionControlItemBase *__hidden this, HSTRING)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801cc43c`
- `0x1801d0a68`

## callees

- `0x180008a74`
- `0x180008acc`
- `0x18000b7e8`
- `0x180011884`
- `0x18001dec8`
- `0x180027ee4`
- `0x18006d698`
- `0x18010bd6c`
- `0x18010c084`
- `0x180158790`
- `0x1801cd69c`
- `0x1801cf660`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18010bddc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18010bef3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18010bddc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18010bef3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010be87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010c047`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010be87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010c047`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010bda2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010beb3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010bf17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010bf53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010bf62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010bf85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010bda2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010beb3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010bf17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010bf53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010bf62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010bf85`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18010bfec`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18010bfec`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::ApplicationModel::Contacts::Internal::ContactActionControlItemBase::_CreateActionItem(
        Windows::ApplicationModel::Contacts::Internal::ContactActionControlItemBase *this,
        HSTRING a2)
{
  AgileGitPtr *v3; // r12
  const WCHAR *StringRawBuffer; // rdi
  bool v5; // cl
  unsigned int v6; // ebx
  int v7; // eax
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // r8
  int (__fastcall ***v11)(_QWORD, GUID *, __int64 *); // rdi
  int (__fastcall *v12)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v13; // rdi
  int (__fastcall *v14)(__int64, HSTRING *); // rbx
  const WCHAR *v15; // rax
  char v16; // r13
  unsigned __int64 i; // r15
  const unsigned __int16 *v18; // rsi
  const unsigned __int16 *v19; // rdi
  const unsigned __int16 *v20; // rbx
  HSTRING v21; // r8
  int v22; // eax
  const unsigned __int16 *v23; // rax
  struct IShellItem *v24; // rbx
  __int64 v25; // rcx
  struct IShellItem *v26; // [rsp+30h] [rbp-39h] BYREF
  HSTRING string; // [rsp+38h] [rbp-31h] BYREF
  __int64 v28; // [rsp+40h] [rbp-29h] BYREF
  __int64 v29; // [rsp+48h] [rbp-21h] BYREF
  __int64 v30; // [rsp+50h] [rbp-19h] BYREF
  const WCHAR *v31; // [rsp+58h] [rbp-11h]
  unsigned __int16 *v32[12]; // [rsp+60h] [rbp-9h] BYREF
  UINT32 length; // [rsp+D0h] [rbp+67h] BYREF
  HSTRING v34; // [rsp+D8h] [rbp+6Fh]
  __int64 v35; // [rsp+E0h] [rbp+77h] BYREF
  struct IShellItem *v36; // [rsp+E8h] [rbp+7Fh] BYREF

  v34 = a2;
  v3 = (Windows::ApplicationModel::Contacts::Internal::ContactActionControlItemBase *)((char *)this + 72);
  if ( *((_QWORD *)this + 9) )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 12), 0);
    v5 = 0;
    v6 = 0;
    while ( !v5 )
    {
      v7 = CompareStringOrdinal(StringRawBuffer, -1, off_1803E1760[v6++], -1, 1);
      v5 = v7 == 2;
      if ( v6 >= 2 )
      {
        if ( v7 != 2 )
        {
          v26 = 0;
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v26);
          if ( (int)AgileGitPtr::CopyLocal(v3, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, (void **)&v26) >= 0 )
          {
            v29 = 0;
            v8 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IImmersiveMonitor>>(&v29);
            if ( (int)HiddenProperties_GetPropStoreFromItem(v9, v26, v10, v8) < 0 )
            {
              v28 = 0;
              v11 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 8);
              v12 = **v11;
              Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v28);
              if ( v12(v11, &GUID_811233d1_3151_4e14_83da_ad47404c0b41, &v28) >= 0 )
              {
                string = 0;
                v13 = v28;
                v14 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v28 + 72LL);
                WindowsDeleteString(0);
                string = 0;
                if ( v14(v13, &string) >= 0 )
                {
                  length = 0;
                  v15 = WindowsGetStringRawBuffer(*((HSTRING *)this + 12), &length);
                  v31 = v15;
                  v16 = 0;
                  for ( i = 0; i < 6; ++i )
                  {
                    if ( v16 )
                      break;
                    if ( CompareStringOrdinal(v15, length, (&off_1803E1770)[2 * i], -1, 1) == 2 )
                    {
                      v16 = 1;
                      memset(v32, 0, 24);
                      WindowsGetStringRawBuffer(*((HSTRING *)this + 14), 0);
                      if ( (int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeResMessage(
                                  v32,
                                  &_ImageBase,
                                  (unsigned int)dword_1803E177C[4 * i]) >= 0 )
                      {
                        v36 = 0;
                        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v36);
                        v18 = v32[0];
                        v19 = WindowsGetStringRawBuffer(string, 0);
                        v20 = WindowsGetStringRawBuffer(v34, 0);
                        v22 = Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                                *((Microsoft::WRL::Wrappers::Details **)this + 13),
                                0,
                                v21);
                        v23 = WindowsGetStringRawBuffer(*(HSTRING *)((char *)this + (v22 != 0 ? 8 : 0) + 96), 0);
                        if ( (int)CreateShellItemWithActionInformation(v26, v23, v20, v19, v18, &v36) >= 0 )
                        {
                          wil::details::FeatureImpl<__WilFeatureTraits_Feature_KeepWin8SearchPane>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_KeepWin8SearchPane>::GetImpl'::`2'::impl);
                          StoreItemInHistory(v36);
                          v24 = v36;
                          v35 = 0;
                          if ( v36 )
                          {
                            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
                            RoGetAgileReference(0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, v24, &v35);
                          }
                          v25 = v35;
                          v35 = 0;
                          v30 = *(_QWORD *)v3;
                          *(_QWORD *)v3 = v25;
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
                        }
                        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v36);
                      }
                      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v32);
                    }
                    else
                    {
                      v16 = 0;
                    }
                    v15 = v31;
                  }
                }
                WindowsDeleteString(string);
              }
              Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v28);
            }
            Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v29);
          }
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v26);
        }
        return;
      }
    }
  }
}

```

## disassembly

```asm
0x18010bd6c  mov     [rsp-8+arg_8], rdx
0x18010bd71  push    rbp
0x18010bd72  push    rbx
0x18010bd73  push    rsi
0x18010bd74  push    rdi
0x18010bd75  push    r12
0x18010bd77  push    r13
0x18010bd79  push    r14
0x18010bd7b  push    r15
0x18010bd7d  lea     rbp, [rsp-1Fh]
0x18010bd82  sub     rsp, 88h
0x18010bd89  mov     r14, rcx
0x18010bd8c  lea     r12, [rcx+48h]
0x18010bd90  xor     esi, esi
0x18010bd92  cmp     [r12], rsi
0x18010bd96  jz      loc_18010C068
0x18010bd9c  xor     edx, edx; length
0x18010bd9e  mov     rcx, [rcx+60h]; string
0x18010bda2  call    cs:__imp_WindowsGetStringRawBuffer
0x18010bda8  mov     rdi, rax
0x18010bdab  mov     cl, sil
0x18010bdae  mov     ebx, esi
0x18010bdb0  lea     rax, __ImageBase
0x18010bdb7  test    cl, cl
0x18010bdb9  jnz     loc_18010C068
0x18010bdbf  movsxd  r8, ebx
0x18010bdc2  mov     [rsp+0C0h+bIgnoreCase], 1; bIgnoreCase
0x18010bdca  or      r9d, 0FFFFFFFFh; cchCount2
0x18010bdce  mov     r8, ds:rva off_1803E1760[rax+r8*8]; lpString2
0x18010bdd6  or      edx, r9d; cchCount1
0x18010bdd9  mov     rcx, rdi; lpString1
0x18010bddc  call    cs:__imp_CompareStringOrdinal
0x18010bde2  inc     ebx
0x18010bde4  cmp     eax, 2
0x18010bde7  setz    cl
0x18010bdea  cmp     ebx, 2
0x18010bded  jb      short loc_18010BDB0
0x18010bdef  cmp     eax, 2
0x18010bdf2  jz      loc_18010C068
0x18010bdf8  mov     [rbp+57h+var_90], rsi
0x18010bdfc  lea     rcx, [rbp+57h+var_90]
0x18010be00  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18010be05  lea     r8, [rbp+57h+var_90]; void **
0x18010be09  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; struct _GUID *
0x18010be10  mov     rcx, r12; this
0x18010be13  call    ?CopyLocal@AgileGitPtr@@QEBAJAEBU_GUID@@PEAPEAX@Z; AgileGitPtr::CopyLocal(_GUID const &,void * *)
0x18010be18  test    eax, eax
0x18010be1a  js      loc_18010C05F
0x18010be20  mov     [rbp+57h+var_78], rsi
0x18010be24  lea     rcx, [rbp+57h+var_78]
0x18010be28  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIImmersiveMonitor@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIImmersiveMonitor@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IImmersiveMonitor>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IImmersiveMonitor>>)
0x18010be2d  mov     r9, rax
0x18010be30  mov     rdx, [rbp+57h+var_90]
0x18010be34  call    ?HiddenProperties_GetPropStoreFromItem@@YAJW4IDLHID@@PEAUIShellItem@@AEBU_GUID@@PEAPEAX@Z; HiddenProperties_GetPropStoreFromItem(IDLHID,IShellItem *,_GUID const &,void * *)
0x18010be39  test    eax, eax
0x18010be3b  jns     loc_18010C056
0x18010be41  mov     [rbp+57h+var_80], rsi
0x18010be45  mov     rdi, [r14+40h]
0x18010be49  mov     rax, [rdi]
0x18010be4c  mov     rbx, [rax]
0x18010be4f  lea     rcx, [rbp+57h+var_80]
0x18010be53  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18010be58  lea     r8, [rbp+57h+var_80]
0x18010be5c  lea     rdx, _GUID_811233d1_3151_4e14_83da_ad47404c0b41
0x18010be63  mov     rcx, rdi
0x18010be66  mov     rax, rbx
0x18010be69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010be6e  test    eax, eax
0x18010be70  js      loc_18010C04D
0x18010be76  mov     [rbp+57h+string], rsi
0x18010be7a  mov     rdi, [rbp+57h+var_80]
0x18010be7e  mov     rax, [rdi]
0x18010be81  mov     rbx, [rax+48h]
0x18010be85  xor     ecx, ecx; string
0x18010be87  call    cs:__imp_WindowsDeleteString
0x18010be8d  mov     [rbp+57h+string], rsi
0x18010be91  lea     rdx, [rbp+57h+string]
0x18010be95  mov     rcx, rdi
0x18010be98  mov     rax, rbx
0x18010be9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010bea0  test    eax, eax
0x18010bea2  js      loc_18010C043
0x18010bea8  mov     [rbp+57h+length], esi
0x18010beab  lea     rdx, [rbp+57h+length]; length
0x18010beaf  mov     rcx, [r14+60h]; string
0x18010beb3  call    cs:__imp_WindowsGetStringRawBuffer
0x18010beb9  mov     [rbp+57h+var_68], rax
0x18010bebd  mov     r13b, sil
0x18010bec0  mov     r15, rsi
0x18010bec3  test    r13b, r13b
0x18010bec6  jnz     loc_18010C043
0x18010becc  mov     rbx, r15
0x18010becf  add     rbx, rbx
0x18010bed2  mov     [rsp+0C0h+bIgnoreCase], 1; bIgnoreCase
0x18010beda  or      r9d, 0FFFFFFFFh; cchCount2
0x18010bede  lea     rdi, __ImageBase
0x18010bee5  mov     r8, ds:rva off_1803E1770[rdi+rbx*8]; lpString2
0x18010beed  mov     edx, [rbp+57h+length]; cchCount1
0x18010bef0  mov     rcx, rax; lpString1
0x18010bef3  call    cs:__imp_CompareStringOrdinal
0x18010bef9  cmp     eax, 2
0x18010befc  jnz     loc_18010C02F
0x18010bf02  mov     r13b, 1
0x18010bf05  mov     [rbp+57h+var_60], rsi
0x18010bf09  mov     [rbp+57h+var_58], rsi
0x18010bf0d  mov     [rbp+57h+var_50], rsi
0x18010bf11  xor     edx, edx; length
0x18010bf13  mov     rcx, [r14+70h]; string
0x18010bf17  call    cs:__imp_WindowsGetStringRawBuffer
0x18010bf1d  mov     r9, rax
0x18010bf20  mov     r8d, ds:rva dword_1803E177C[rdi+rbx*8]
0x18010bf28  mov     rdx, rdi
0x18010bf2b  lea     rcx, [rbp+57h+var_60]
0x18010bf2f  call    ?InitializeResMessage@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@HZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeResMessage(HINSTANCE__ *,int,...)
0x18010bf34  test    eax, eax
0x18010bf36  js      loc_18010C024
0x18010bf3c  mov     [rbp+57h+arg_18], rsi
0x18010bf40  lea     rcx, [rbp+57h+arg_18]
0x18010bf44  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18010bf49  mov     rsi, [rbp+57h+var_60]
0x18010bf4d  xor     edx, edx; length
0x18010bf4f  mov     rcx, [rbp+57h+string]; string
0x18010bf53  call    cs:__imp_WindowsGetStringRawBuffer
0x18010bf59  mov     rdi, rax
0x18010bf5c  xor     edx, edx; length
0x18010bf5e  mov     rcx, [rbp+57h+arg_8]; string
0x18010bf62  call    cs:__imp_WindowsGetStringRawBuffer
0x18010bf68  mov     rbx, rax
0x18010bf6b  xor     edx, edx; HSTRING
0x18010bf6d  mov     rcx, [r14+68h]; this
0x18010bf71  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18010bf76  neg     eax
0x18010bf78  sbb     rcx, rcx
0x18010bf7b  and     ecx, 8
0x18010bf7e  xor     edx, edx; length
0x18010bf80  mov     rcx, [rcx+r14+60h]; string
0x18010bf85  call    cs:__imp_WindowsGetStringRawBuffer
0x18010bf8b  lea     rcx, [rbp+57h+arg_18]
0x18010bf8f  mov     [rsp+0C0h+var_98], rcx; struct IShellItem **
0x18010bf94  mov     qword ptr [rsp+0C0h+bIgnoreCase], rsi; unsigned __int16 *
0x18010bf99  mov     r9, rdi; unsigned __int16 *
0x18010bf9c  mov     r8, rbx; unsigned __int16 *
0x18010bf9f  mov     rdx, rax; unsigned __int16 *
0x18010bfa2  mov     rcx, [rbp+57h+var_90]; struct IShellItem *
0x18010bfa6  call    ?CreateShellItemWithActionInformation@@YAJPEAUIShellItem@@PEBG111PEAPEAU1@@Z; CreateShellItemWithActionInformation(IShellItem *,ushort const *,ushort const *,ushort const *,ushort const *,IShellItem * *)
0x18010bfab  xor     esi, esi
0x18010bfad  test    eax, eax
0x18010bfaf  js      short loc_18010C01B
0x18010bfb1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_KeepWin8SearchPane@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_KeepWin8SearchPane@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_KeepWin8SearchPane> `wil::Feature<__WilFeatureTraits_Feature_KeepWin8SearchPane>::GetImpl(void)'::`2'::impl
0x18010bfb8  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_KeepWin8SearchPane@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_KeepWin8SearchPane>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x18010bfbd  mov     rcx, [rbp+57h+arg_18]; struct IShellItem *
0x18010bfc1  call    ?StoreItemInHistory@@YAJPEAUIShellItem@@@Z; StoreItemInHistory(IShellItem *)
0x18010bfc6  mov     rbx, [rbp+57h+arg_18]
0x18010bfca  mov     [rbp+57h+arg_10], rsi
0x18010bfce  test    rbx, rbx
0x18010bfd1  jz      short loc_18010BFF3
0x18010bfd3  lea     rcx, [rbp+57h+arg_10]
0x18010bfd7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010bfdc  lea     r9, [rbp+57h+arg_10]
0x18010bfe0  mov     r8, rbx
0x18010bfe3  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x18010bfea  xor     ecx, ecx
0x18010bfec  call    cs:__imp_RoGetAgileReference
0x18010bff2  nop
0x18010bff3  mov     rcx, [rbp+57h+arg_10]
0x18010bff7  mov     [rbp+57h+arg_10], rsi
0x18010bffb  mov     rax, [r12]
0x18010bfff  mov     [rbp+57h+var_70], rax
0x18010c003  mov     [r12], rcx
0x18010c007  lea     rcx, [rbp+57h+var_70]
0x18010c00b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010c010  nop
0x18010c011  lea     rcx, [rbp+57h+arg_10]
0x18010c015  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010c01a  nop
0x18010c01b  lea     rcx, [rbp+57h+arg_18]
0x18010c01f  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18010c024  lea     rcx, [rbp+57h+var_60]
0x18010c028  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18010c02d  jmp     short loc_18010C032
0x18010c02f  mov     r13b, sil
0x18010c032  inc     r15
0x18010c035  cmp     r15, 6
0x18010c039  mov     rax, [rbp+57h+var_68]
0x18010c03d  jb      loc_18010BEC3
0x18010c043  mov     rcx, [rbp+57h+string]; string
0x18010c047  call    cs:__imp_WindowsDeleteString
0x18010c04d  lea     rcx, [rbp+57h+var_80]
0x18010c051  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18010c056  lea     rcx, [rbp+57h+var_78]
0x18010c05a  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18010c05f  lea     rcx, [rbp+57h+var_90]
0x18010c063  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18010c068  add     rsp, 88h
0x18010c06f  pop     r15
0x18010c071  pop     r14
0x18010c073  pop     r13
0x18010c075  pop     r12
0x18010c077  pop     rdi
0x18010c078  pop     rsi
0x18010c079  pop     rbx
0x18010c07a  pop     rbp
0x18010c07b  retn
```
