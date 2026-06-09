# CPackagedComCatalog::GetClassInfoW(ulong,IUserToken *,_GUID const &,_GUID const &,void * *,void *)

- ea: `0x18005ca90`
- end: `0x18005ce80`
- name: `?GetClassInfoW@CPackagedComCatalog@@UEAAJKPEAUIUserToken@@AEBU_GUID@@1PEAPEAXPEAX@Z`
- size: `1008`
- prototype: `__int64 __usercall@<rax>(CPackagedComCatalog *__hidden this@<rcx>, unsigned int@<edx>, struct IUserToken *@<r8>, const struct _GUID *@<r9>, const struct _GUID *, void **, void *)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003064`
- `0x180005c40`
- `0x18000d4c4`
- `0x18002ba28`
- `0x18002f91c`
- `0x18004778c`
- `0x18005ca90`
- `0x18005ce88`
- `0x18005ced0`
- `0x18005cf64`
- `0x18008d028`
- `0x18008e98c`
- `0x18010b010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005cb7a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005cb7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cb84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ccde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cd17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ce49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cb84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ccde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cd17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ce49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005cd2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005cd2e`
- `combase!__imp_RoGetRegistrationStoreContext` at `0x18005cc21`
- `combase!__imp_RoGetRegistrationStoreContext` at `0x18005cc21`

## string_xrefs

- `0x18005cb59`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18005cd4e`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18005cd8a`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18005cdd8`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18005cdfa`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18005ce28`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`

## pseudocode

```c
__int64 __fastcall CPackagedComCatalog::GetClassInfoW(
        CPackagedComCatalog *this,
        unsigned int a2,
        struct IUserToken *a3,
        struct _GUID *a4,
        const struct _GUID *a5,
        void **a6)
{
  struct _GUID *v6; // rsi
  bool v10; // dl
  __int64 v11; // rcx
  int v12; // eax
  unsigned int PackageFullName; // ebx
  enum tagCLSCTX RequestedClassContext; // r13d
  __int64 v15; // rdx
  void (*v16)(void); // rax
  int v18; // eax
  int RegistrationStoreContext; // eax
  BOOL IsUserHiveOk; // ecx
  int v21; // eax
  char v22; // cl
  unsigned int ClassInfoWorker; // eax
  __int64 v24; // rcx
  void (*v25)(void); // rax
  const WCHAR *v26; // rsi
  unsigned __int64 v27; // rbx
  HRESULT v28; // eax
  __int64 v29; // rcx
  int v30; // [rsp+20h] [rbp-91h]
  int v31; // [rsp+80h] [rbp-31h] BYREF
  HSTRING string; // [rsp+88h] [rbp-29h] BYREF
  struct IUserTokenInternal *v33; // [rsp+90h] [rbp-21h] BYREF
  int v34[2]; // [rsp+98h] [rbp-19h] BYREF
  LPVOID lpMem; // [rsp+A0h] [rbp-11h] BYREF
  _QWORD v36[9]; // [rsp+A8h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+47h]

  v6 = a4;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v11);
    PackageFullName = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8A8,
      (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
      (const char *)0x8000FFFFLL,
      v30);
    return PackageFullName;
  }
  v33 = 0;
  *a6 = 0;
  if ( a3 )
  {
    v12 = (**(__int64 (__fastcall ***)(struct IUserToken *, GUID *, struct IUserTokenInternal **))a3)(
            a3,
            &GUID_000001fc_0000_0000_cfff_123045660046,
            &v33);
    PackageFullName = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8B1,
        (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
        (const char *)(unsigned int)v12,
        v30);
      if ( !v33 )
        return PackageFullName;
      v16 = *(void (**)(void))(*(_QWORD *)v33 + 16LL);
      goto LABEL_14;
    }
  }
  RequestedClassContext = CPackagedComCatalog::GetRequestedClassContext(a2, v10);
  if ( RequestedClassContext )
  {
    v36[0] = 0;
    if ( a3 )
    {
      v18 = (*(__int64 (__fastcall **)(struct IUserToken *, _QWORD *))(*(_QWORD *)a3 + 48LL))(a3, v36);
      PackageFullName = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8BD,
          (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
          (const char *)(unsigned int)v18,
          v30);
        goto LABEL_49;
      }
    }
    string = 0;
    if ( !*((_BYTE *)this + 56) )
    {
LABEL_21:
      *(_QWORD *)v34 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v34);
      RegistrationStoreContext = RoGetRegistrationStoreContext(1, v36[0], 0, &GUID_3d36d086_c789_44cc_9d8c_cb3b5f8eeada);
      PackageFullName = RegistrationStoreContext;
      if ( RegistrationStoreContext >= 0 )
      {
        IsUserHiveOk = CPackagedComCatalog::IsUserHiveOk(this);
        v31 = IsUserHiveOk;
        if ( a3 )
        {
          v21 = (*(__int64 (__fastcall **)(struct IUserToken *, int *))(*(_QWORD *)a3 + 88LL))(a3, &v31);
          PackageFullName = v21;
          if ( v21 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x8D5,
              (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
              (const char *)(unsigned int)v21,
              (int)v34);
            v29 = *(_QWORD *)v34;
            if ( !*(_QWORD *)v34 )
              goto LABEL_30;
            *(_QWORD *)v34 = 0;
            v25 = *(void (**)(void))(*(_QWORD *)v29 + 16LL);
            goto LABEL_29;
          }
          IsUserHiveOk = v31;
        }
        if ( !IsUserHiveOk )
        {
          if ( (a2 & 0x200) == 0 )
          {
            v22 = 0;
            goto LABEL_27;
          }
          v31 = 1;
        }
        v22 = 1;
LABEL_27:
        ClassInfoWorker = CPackagedComCatalog::GetClassInfoWorker(
                            RequestedClassContext,
                            v33,
                            *(__int64 *)v34,
                            (const struct OpaqueString *)&string,
                            1,
                            v6,
                            v22,
                            (__int64)a5,
                            a6,
                            0,
                            0,
                            0,
                            0,
                            0,
                            0);
        v24 = *(_QWORD *)v34;
        PackageFullName = ClassInfoWorker;
        if ( !*(_QWORD *)v34 )
        {
LABEL_30:
          WindowsDeleteString(string);
          string = 0;
LABEL_12:
          if ( !v33 )
            return PackageFullName;
          v16 = *(void (**)(void))(*(_QWORD *)v33 + 16LL);
LABEL_14:
          v16();
          return PackageFullName;
        }
        *(_QWORD *)v34 = 0;
        v25 = *(void (**)(void))(*(_QWORD *)v24 + 16LL);
LABEL_29:
        v25();
        goto LABEL_30;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8D0,
        (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
        (const char *)(unsigned int)RegistrationStoreContext,
        (int)v34);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v34);
      WindowsDeleteString(string);
      string = 0;
LABEL_49:
      wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v33);
      return PackageFullName;
    }
    lpMem = 0;
    PackageFullName = GetPackageFullName(v33, &lpMem);
    if ( (PackageFullName & 0x80000000) != 0 )
    {
      v15 = 2247;
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
        (const char *)PackageFullName,
        v30);
      if ( lpMem )
        HeapFree(g_hHeap, 0, lpMem);
      WindowsDeleteString(string);
      string = 0;
      goto LABEL_12;
    }
    v26 = (const WCHAR *)lpMem;
    if ( lpMem )
    {
      v27 = -1;
      do
        ++v27;
      while ( *((_WORD *)lpMem + v27) );
      if ( v27 > 0xFFFFFFFF )
      {
        PackageFullName = -2147024362;
        goto LABEL_37;
      }
      WindowsDeleteString(string);
      string = 0;
      v28 = WindowsCreateString(v26, v27, &string);
    }
    else
    {
      v28 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&string, &Class, 0);
    }
    PackageFullName = v28;
LABEL_37:
    if ( (PackageFullName & 0x80000000) != 0 )
    {
      v15 = 2248;
      goto LABEL_9;
    }
    utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(&lpMem);
    v6 = a4;
    goto LABEL_21;
  }
  if ( v33 )
    (*(void (__fastcall **)(struct IUserTokenInternal *))(*(_QWORD *)v33 + 16LL))(v33);
  return 2147746132LL;
}

```

## disassembly

```asm
0x18005ca90  mov     [rsp-8+arg_18], r9
0x18005ca95  push    rbp
0x18005ca96  push    rbx
0x18005ca97  push    rsi
0x18005ca98  push    rdi
0x18005ca99  push    r12
0x18005ca9b  push    r13
0x18005ca9d  push    r14
0x18005ca9f  push    r15
0x18005caa1  lea     rbp, [rsp-7]
0x18005caa6  sub     rsp, 0B8h
0x18005caad  mov     rsi, r9
0x18005cab0  mov     rdi, r8
0x18005cab3  mov     r15d, edx
0x18005cab6  mov     r14, rcx
0x18005cab9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x18005cac0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x18005cac5  xor     ebx, ebx
0x18005cac7  test    al, al
0x18005cac9  jnz     loc_18005CDCF
0x18005cacf  mov     r12, [rbp+3Fh+arg_28]
0x18005cad3  mov     [rbp+3Fh+var_60], rbx
0x18005cad7  mov     [r12], rbx
0x18005cadb  test    rdi, rdi
0x18005cade  jz      short loc_18005CB05
0x18005cae0  mov     rax, [rdi]
0x18005cae3  lea     r8, [rbp+3Fh+var_60]
0x18005cae7  lea     rdx, _GUID_000001fc_0000_0000_cfff_123045660046
0x18005caee  mov     rcx, rdi
0x18005caf1  mov     rax, [rax]
0x18005caf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005caf9  mov     ebx, eax
0x18005cafb  test    eax, eax
0x18005cafd  js      loc_18005CD86
0x18005cb03  xor     ebx, ebx
0x18005cb05  mov     ecx, r15d; unsigned int
0x18005cb08  call    ?GetRequestedClassContext@CPackagedComCatalog@@CA?AW4tagCLSCTX@@K_N@Z; CPackagedComCatalog::GetRequestedClassContext(ulong,bool)
0x18005cb0d  mov     r13d, eax
0x18005cb10  test    eax, eax
0x18005cb12  jz      loc_18005CBB9
0x18005cb18  mov     [rbp+3Fh+var_48], rbx
0x18005cb1c  test    rdi, rdi
0x18005cb1f  jnz     loc_18005CBD5
0x18005cb25  mov     [rbp+3Fh+string], rbx
0x18005cb29  cmp     [r14+38h], bl
0x18005cb2d  jz      loc_18005CBF9
0x18005cb33  mov     rcx, [rbp+3Fh+var_60]
0x18005cb37  lea     rdx, [rbp+3Fh+lpMem]
0x18005cb3b  mov     [rbp+3Fh+lpMem], rbx
0x18005cb3f  call    ?GetPackageFullName@@YAJPEAUIUserTokenInternal@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?PrivMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; GetPackageFullName(IUserTokenInternal *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&PrivMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18005cb44  xor     esi, esi
0x18005cb46  mov     ebx, eax
0x18005cb48  test    eax, eax
0x18005cb4a  jns     loc_18005CCED
0x18005cb50  mov     edx, 8C7h; void *
0x18005cb55  mov     rcx, [rbp+47h]; this
0x18005cb59  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x18005cb60  mov     r9d, ebx; char *
0x18005cb63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005cb68  mov     r8, [rbp+3Fh+lpMem]; lpMem
0x18005cb6c  test    r8, r8
0x18005cb6f  jz      short loc_18005CB80
0x18005cb71  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18005cb78  xor     edx, edx; dwFlags
0x18005cb7a  call    cs:__imp_HeapFree
0x18005cb80  mov     rcx, [rbp+3Fh+string]; string
0x18005cb84  call    cs:__imp_WindowsDeleteString
0x18005cb8a  mov     [rbp+3Fh+string], rsi
0x18005cb8e  mov     rcx, [rbp+3Fh+var_60]
0x18005cb92  test    rcx, rcx
0x18005cb95  jz      short loc_18005CBA3
0x18005cb97  mov     rax, [rcx]
0x18005cb9a  mov     rax, [rax+10h]
0x18005cb9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cba3  mov     eax, ebx
0x18005cba5  add     rsp, 0B8h
0x18005cbac  pop     r15
0x18005cbae  pop     r14
0x18005cbb0  pop     r13
0x18005cbb2  pop     r12
0x18005cbb4  pop     rdi
0x18005cbb5  pop     rsi
0x18005cbb6  pop     rbx
0x18005cbb7  pop     rbp
0x18005cbb8  retn
0x18005cbb9  mov     rcx, [rbp+3Fh+var_60]
0x18005cbbd  test    rcx, rcx
0x18005cbc0  jz      short loc_18005CBCE
0x18005cbc2  mov     rax, [rcx]
0x18005cbc5  mov     rax, [rax+10h]
0x18005cbc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cbce  mov     eax, 80040154h
0x18005cbd3  jmp     short loc_18005CBA5
0x18005cbd5  mov     rax, [rdi]
0x18005cbd8  lea     rdx, [rbp+3Fh+var_48]
0x18005cbdc  mov     rcx, rdi
0x18005cbdf  mov     rax, [rax+30h]
0x18005cbe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cbe8  mov     ebx, eax
0x18005cbea  test    eax, eax
0x18005cbec  js      loc_18005CDF6
0x18005cbf2  xor     ebx, ebx
0x18005cbf4  jmp     loc_18005CB25
0x18005cbf9  lea     rcx, [rbp+3Fh+var_58]
0x18005cbfd  mov     qword ptr [rbp+3Fh+var_58], rbx
0x18005cc01  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005cc06  mov     rdx, [rbp+3Fh+var_48]
0x18005cc0a  lea     rax, [rbp+3Fh+var_58]
0x18005cc0e  xor     r8d, r8d
0x18005cc11  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x18005cc16  lea     r9, _GUID_3d36d086_c789_44cc_9d8c_cb3b5f8eeada
0x18005cc1d  lea     ecx, [r8+1]
0x18005cc21  call    cs:__imp_RoGetRegistrationStoreContext
0x18005cc27  mov     ebx, eax
0x18005cc29  test    eax, eax
0x18005cc2b  js      loc_18005CE24
0x18005cc31  mov     rcx, r14; this
0x18005cc34  call    ?IsUserHiveOk@CPackagedComCatalog@@AEBA_NXZ; CPackagedComCatalog::IsUserHiveOk(void)
0x18005cc39  xor     r14d, r14d
0x18005cc3c  movzx   ecx, al
0x18005cc3f  mov     [rbp+3Fh+var_70], ecx
0x18005cc42  test    rdi, rdi
0x18005cc45  jz      short loc_18005CC67
0x18005cc47  mov     rax, [rdi]
0x18005cc4a  lea     rdx, [rbp+3Fh+var_70]
0x18005cc4e  mov     rcx, rdi
0x18005cc51  mov     rax, [rax+58h]
0x18005cc55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cc5a  mov     ebx, eax
0x18005cc5c  test    eax, eax
0x18005cc5e  js      loc_18005CD4A
0x18005cc64  mov     ecx, [rbp+3Fh+var_70]
0x18005cc67  test    ecx, ecx
0x18005cc69  jz      loc_18005CE65
0x18005cc6f  mov     cl, 1
0x18005cc71  mov     rax, [rbp+3Fh+arg_20]
0x18005cc75  lea     r9, [rbp+3Fh+string]
0x18005cc79  mov     r8, qword ptr [rbp+3Fh+var_58]
0x18005cc7d  mov     rdx, [rbp+3Fh+var_60]
0x18005cc81  mov     [rsp+0F0h+var_80], r14
0x18005cc86  mov     [rsp+0F0h+var_88], r14d
0x18005cc8b  mov     [rsp+0F0h+var_90], r14
0x18005cc90  mov     [rsp+0F0h+var_98], r14d
0x18005cc95  mov     [rsp+0F0h+var_A0], r14
0x18005cc9a  mov     [rsp+0F0h+var_A8], r14d
0x18005cc9f  mov     [rsp+0F0h+var_B0], r12
0x18005cca4  mov     [rsp+0F0h+var_B8], rax
0x18005cca9  mov     [rsp+0F0h+var_C0], cl
0x18005ccad  mov     ecx, r13d
0x18005ccb0  mov     [rsp+0F0h+var_C8], rsi
0x18005ccb5  mov     byte ptr [rsp+0F0h+var_D0], 1
0x18005ccba  call    ?GetClassInfoWorker@CPackagedComCatalog@@CAJW4tagCLSCTX@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBVOpaqueString@@_NAEBU_GUID@@45PEAPEAXW4ComRegistrationVisibility@@PEBGIQEBQEAUHSTRING__@@I9@Z; CPackagedComCatalog::GetClassInfoWorker(tagCLSCTX,IUserTokenInternal *,IPackagedComCatalogContext *,OpaqueString const &,bool,_GUID const &,bool,_GUID const &,void * *,ComRegistrationVisibility,ushort const *,uint,HSTRING__ * const * const,uint,HSTRING__ * const * const)
0x18005ccbf  mov     rcx, qword ptr [rbp+3Fh+var_58]
0x18005ccc3  mov     ebx, eax
0x18005ccc5  test    rcx, rcx
0x18005ccc8  jz      short loc_18005CCDA
0x18005ccca  mov     qword ptr [rbp+3Fh+var_58], r14
0x18005ccce  mov     rdx, [rcx]
0x18005ccd1  mov     rax, [rdx+10h]
0x18005ccd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ccda  mov     rcx, [rbp+3Fh+string]; string
0x18005ccde  call    cs:__imp_WindowsDeleteString
0x18005cce4  mov     [rbp+3Fh+string], r14
0x18005cce8  jmp     loc_18005CB8E
0x18005cced  mov     rsi, [rbp+3Fh+lpMem]
0x18005ccf1  xor     eax, eax
0x18005ccf3  test    rsi, rsi
0x18005ccf6  jz      loc_18005CDB7
0x18005ccfc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18005cd00  inc     rbx
0x18005cd03  cmp     [rsi+rbx*2], ax
0x18005cd07  jnz     short loc_18005CD00
0x18005cd09  mov     eax, 0FFFFFFFFh
0x18005cd0e  cmp     rbx, rax
0x18005cd11  ja      short loc_18005CD7F
0x18005cd13  mov     rcx, [rbp+3Fh+string]; string
0x18005cd17  call    cs:__imp_WindowsDeleteString
0x18005cd1d  mov     edx, ebx; length
0x18005cd1f  mov     [rbp+3Fh+string], 0
0x18005cd27  lea     r8, [rbp+3Fh+string]; string
0x18005cd2b  mov     rcx, rsi; sourceString
0x18005cd2e  call    cs:__imp_WindowsCreateString
0x18005cd34  mov     ebx, eax
0x18005cd36  xor     esi, esi
0x18005cd38  test    ebx, ebx
0x18005cd3a  jns     loc_18005CE10
0x18005cd40  mov     edx, 8C8h
0x18005cd45  jmp     loc_18005CB55
0x18005cd4a  mov     rcx, [rbp+47h]; this
0x18005cd4e  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x18005cd55  mov     r9d, ebx; char *
0x18005cd58  mov     edx, 8D5h; void *
0x18005cd5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005cd62  mov     rcx, qword ptr [rbp+3Fh+var_58]
0x18005cd66  test    rcx, rcx
0x18005cd69  jz      loc_18005CCDA
0x18005cd6f  mov     qword ptr [rbp+3Fh+var_58], r14
0x18005cd73  mov     rax, [rcx]
0x18005cd76  mov     rax, [rax+10h]
0x18005cd7a  jmp     loc_18005CCD5
0x18005cd7f  mov     ebx, 80070216h
0x18005cd84  jmp     short loc_18005CD36
0x18005cd86  mov     rcx, [rbp+47h]; this
0x18005cd8a  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x18005cd91  mov     r9d, ebx; char *
0x18005cd94  mov     edx, 8B1h; void *
0x18005cd99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005cd9e  mov     rcx, [rbp+3Fh+var_60]
0x18005cda2  test    rcx, rcx
0x18005cda5  jz      loc_18005CBA3
0x18005cdab  mov     rdx, [rcx]
0x18005cdae  mov     rax, [rdx+10h]
0x18005cdb2  jmp     loc_18005CB9E
0x18005cdb7  xor     r8d, r8d; unsigned int
0x18005cdba  lea     rdx, Class; unsigned __int16 *
0x18005cdc1  lea     rcx, [rbp+3Fh+string]; this
0x18005cdc5  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18005cdca  jmp     loc_18005CD34
0x18005cdcf  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005cdd4  mov     rcx, [rbp+47h]; this
0x18005cdd8  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x18005cddf  mov     ebx, 8000FFFFh
0x18005cde4  mov     edx, 8A8h; void *
0x18005cde9  mov     r9d, ebx; char *
0x18005cdec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005cdf1  jmp     loc_18005CBA3
0x18005cdf6  mov     rcx, [rbp+47h]; this
0x18005cdfa  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x18005ce01  mov     r9d, eax; char *
0x18005ce04  mov     edx, 8BDh; void *
0x18005ce09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ce0e  jmp     short loc_18005CE57
0x18005ce10  lea     rcx, [rbp+3Fh+lpMem]
0x18005ce14  call    ??1?$_UninitializedAllocation@V?$allocator@U?$_TreeNode@PEAVCClientOxid@@@utl@@@utl@@@utl@@QEAA@XZ; utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(void)
0x18005ce19  mov     rsi, [rbp+3Fh+arg_18]
0x18005ce1d  xor     ebx, ebx
0x18005ce1f  jmp     loc_18005CBF9
0x18005ce24  mov     rcx, [rbp+47h]; this
0x18005ce28  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x18005ce2f  mov     r9d, eax; char *
0x18005ce32  mov     edx, 8D0h; void *
0x18005ce37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ce3c  lea     rcx, [rbp+3Fh+var_58]
0x18005ce40  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005ce45  mov     rcx, [rbp+3Fh+string]; string
0x18005ce49  call    cs:__imp_WindowsDeleteString
0x18005ce4f  mov     [rbp+3Fh+string], 0
0x18005ce57  lea     rcx, [rbp+3Fh+var_60]
0x18005ce5b  call    ??1?$com_ptr_t@UIComWinRTActivationProperties@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(void)
0x18005ce60  jmp     loc_18005CBA3
0x18005ce65  bt      r15d, 9
0x18005ce6a  jnb     short loc_18005CE78
0x18005ce6c  mov     [rbp+3Fh+var_70], 1
0x18005ce73  jmp     loc_18005CC6F
0x18005ce78  mov     cl, r14b
0x18005ce7b  jmp     loc_18005CC71
```
