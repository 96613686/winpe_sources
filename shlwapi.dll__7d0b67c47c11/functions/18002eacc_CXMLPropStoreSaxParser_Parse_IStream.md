# CXMLPropStoreSaxParser::Parse(IStream *)

- ea: `0x18002eacc`
- end: `0x18002ee34`
- name: `?Parse@CXMLPropStoreSaxParser@@QEAAJPEAUIStream@@@Z`
- size: `872`
- prototype: `__int64 __fastcall(CXMLPropStoreSaxParser *__hidden this, struct IStream *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002e6f0`

## callees

- `0x18000b430`
- `0x180012550`
- `0x180012964`
- `0x180013066`
- `0x180023940`
- `0x18002eacc`
- `0x180030a4c`
- `0x180031454`
- `0x180031fac`
- `0x180032a8c`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x18002ede7`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x18002ede7`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x18002ebd6`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x18002ec11`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x18002ebd6`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x18002ec11`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002ec71`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002ec71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ebad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ebad`

## pseudocode

```c
__int64 __fastcall CXMLPropStoreSaxParser::Parse(
        CXMLPropStoreSaxParser *this,
        int (__fastcall ***a2)(struct IStream *, GUID *, __int64 *))
{
  int (__fastcall **v2)(struct IStream *, GUID *, __int64 *); // rax
  int (__fastcall *v5)(struct IStream *, GUID *, __int64 *); // rbx
  __int64 v6; // rsi
  void (__fastcall *v7)(__int64, char *); // rdi
  unsigned __int64 v8; // rax
  WCHAR *v9; // rax
  WCHAR *v10; // rbx
  void *v11; // rcx
  WCHAR *v12; // rdi
  HRESULT SchemaCollection; // ebx
  _WORD *v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  const WCHAR *v17; // rdx
  __int128 v19; // [rsp+30h] [rbp-79h] BYREF
  __int64 v20; // [rsp+40h] [rbp-69h]
  ULONG pcchLanguagesBuffer[4]; // [rsp+50h] [rbp-59h] BYREF
  LPVOID pv[10]; // [rsp+60h] [rbp-49h] BYREF
  LPVOID ppv; // [rsp+B0h] [rbp+7h] BYREF
  ULONG pulNumLanguages[2]; // [rsp+B8h] [rbp+Fh] BYREF
  __int64 v25; // [rsp+C0h] [rbp+17h] BYREF

  v2 = *a2;
  v25 = 0;
  v5 = *v2;
  Microsoft::WRL::ComPtr<IPropertyDescription>::InternalRelease(&v25);
  if ( v5((struct IStream *)a2, &GUID_52958b02_bcca_41cf_a447_d24f460b24e9, &v25) < 0 )
  {
    if ( !*((_BYTE *)this + 125) )
      goto LABEL_14;
    memset_0(pv, 0, sizeof(pv));
    if ( (*a2)[12]((struct IStream *)a2, (GUID *)pv, 0) >= 0 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
        (char *)this + 88,
        pv[0],
        -1);
      CoTaskMemFree(pv[0]);
    }
  }
  else
  {
    v6 = v25;
    v7 = *(void (__fastcall **)(__int64, char *))(*(_QWORD *)v25 + 24LL);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 88);
    *((_QWORD *)this + 12) = -1;
    *((_QWORD *)this + 13) = -1;
    v7(v6, (char *)this + 88);
  }
  if ( *((_BYTE *)this + 125) )
  {
    pulNumLanguages[0] = 0;
    pcchLanguagesBuffer[0] = 0;
    if ( GetThreadPreferredUILanguages(0x44u, pulNumLanguages, 0, pcchLanguagesBuffer) )
    {
      v8 = 2LL * pcchLanguagesBuffer[0];
      if ( !is_mul_ok(pcchLanguagesBuffer[0], 2u) )
        v8 = -1;
      v9 = (WCHAR *)operator new[](v8, (const struct std::nothrow_t *)&std::nothrow);
      v10 = v9;
      if ( v9 && GetThreadPreferredUILanguages(0x44u, pulNumLanguages, v9, pcchLanguagesBuffer) )
      {
        v11 = (void *)*((_QWORD *)this + 19);
        v12 = v10;
        v10 = 0;
        *((_QWORD *)this + 19) = 0;
        operator delete(v11);
        *((_QWORD *)this + 19) = v12;
      }
      operator delete(v10);
    }
  }
LABEL_14:
  ppv = 0;
  Microsoft::WRL::ComPtr<IPropertyDescription>::InternalRelease(&ppv);
  SchemaCollection = CoCreateInstance(&CLSID_SAXXMLReader60, 0, 1u, &GUID_a4f96ed0_f829_476e_81c0_cdc7bd2a0802, &ppv);
  if ( SchemaCollection < 0 )
    goto LABEL_29;
  SchemaCollection = (*(__int64 (__fastcall **)(LPVOID, CXMLPropStoreSaxParser *))(*(_QWORD *)ppv + 80LL))(ppv, this);
  if ( SchemaCollection >= 0 )
  {
    SchemaCollection = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 112LL))(
                         ppv,
                         ((unsigned __int64)this + 8) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64));
    if ( SchemaCollection >= 0 )
    {
      v14 = (_WORD *)*((_QWORD *)this + 5);
      if ( v14 && *v14 )
      {
        *(_QWORD *)pulNumLanguages = 0;
        Microsoft::WRL::ComPtr<IPropertyDescription>::InternalRelease(pulNumLanguages);
        SchemaCollection = CXMLPropStoreSaxParser::_CreateSchemaCollection(
                             this,
                             (struct IStream *)a2,
                             (struct IXMLDOMSchemaCollection **)pulNumLanguages);
        if ( SchemaCollection >= 0 )
        {
          SchemaCollection = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int64))(*(_QWORD *)ppv + 32LL))(
                               ppv,
                               L"schema-validation",
                               0xFFFFFFFFLL);
          if ( SchemaCollection >= 0 )
          {
            *(_QWORD *)&v19 = 0;
            *((_QWORD *)&v19 + 1) = *(_QWORD *)pulNumLanguages;
            v15 = *(_QWORD *)ppv;
            LOWORD(v19) = 13;
            v20 = 0;
            SchemaCollection = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int128 *))(v15 + 48))(
                                 ppv,
                                 L"schemas",
                                 &v19);
          }
        }
        Microsoft::WRL::ComPtr<IPropertyDescription>::InternalRelease(pulNumLanguages);
      }
      if ( SchemaCollection >= 0 )
      {
        v19 = 0;
        v20 = 0;
        v16 = *(_QWORD *)ppv;
        LOWORD(v19) = 13;
        *((_QWORD *)&v19 + 1) = a2;
        SchemaCollection = (*(__int64 (__fastcall **)(LPVOID, __int128 *))(v16 + 152))(ppv, &v19);
      }
    }
  }
  (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 112LL))(ppv, 0);
  (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 80LL))(ppv, 0);
  if ( *((_BYTE *)this + 124) )
  {
    v17 = (const WCHAR *)*((_QWORD *)this + 19);
    if ( v17 )
      SetThreadPreferredUILanguages(4u, v17, 0);
  }
  if ( SchemaCollection < 0 )
LABEL_29:
    CXMLPropStoreSaxParser::_TerminateParsing(this);
  Microsoft::WRL::ComPtr<IPropertyDescription>::InternalRelease(&ppv);
  Microsoft::WRL::ComPtr<IPropertyDescription>::InternalRelease(&v25);
  return (unsigned int)SchemaCollection;
}

```

## disassembly

```asm
0x18002eacc  mov     [rsp-8+arg_10], rbx
0x18002ead1  push    rbp
0x18002ead2  push    rsi
0x18002ead3  push    rdi
0x18002ead4  push    r12
0x18002ead6  push    r13
0x18002ead8  push    r14
0x18002eada  push    r15
0x18002eadc  lea     rbp, [rsp-27h]
0x18002eae1  sub     rsp, 0D0h
0x18002eae8  mov     rax, cs:__security_cookie
0x18002eaef  xor     rax, rsp
0x18002eaf2  mov     [rbp+57h+var_38], rax
0x18002eaf6  mov     rax, [rdx]
0x18002eaf9  mov     r14, rcx
0x18002eafc  xor     r13d, r13d
0x18002eaff  lea     rcx, [rbp+57h+var_40]
0x18002eb03  mov     r12, rdx
0x18002eb06  mov     [rbp+57h+var_40], r13
0x18002eb0a  mov     rbx, [rax]
0x18002eb0d  call    ?InternalRelease@?$ComPtr@UIPropertyDescription@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPropertyDescription>::InternalRelease(void)
0x18002eb12  lea     r8, [rbp+57h+var_40]
0x18002eb16  mov     rcx, r12
0x18002eb19  lea     rdx, _GUID_52958b02_bcca_41cf_a447_d24f460b24e9
0x18002eb20  mov     rax, rbx
0x18002eb23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eb28  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002eb2c  test    eax, eax
0x18002eb2e  js      short loc_18002EB65
0x18002eb30  mov     rsi, [rbp+57h+var_40]
0x18002eb34  lea     rcx, [r14+58h]
0x18002eb38  mov     rax, [rsi]
0x18002eb3b  mov     rdi, [rax+18h]
0x18002eb3f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002eb44  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002eb48  lea     rdx, [r14+58h]
0x18002eb4c  mov     [r14+60h], rax
0x18002eb50  mov     rcx, rsi
0x18002eb53  mov     [r14+68h], rax
0x18002eb57  mov     rax, rdi
0x18002eb5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eb5f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002eb63  jmp     short loc_18002EBB3
0x18002eb65  cmp     [r14+7Dh], r13b
0x18002eb69  jz      loc_18002EC47
0x18002eb6f  xor     edx, edx; Val
0x18002eb71  lea     rcx, [rbp+57h+pv]; void *
0x18002eb75  lea     r8d, [rdx+50h]; Size
0x18002eb79  call    memset_0
0x18002eb7e  mov     rax, [r12]
0x18002eb82  lea     rdx, [rbp+57h+pv]
0x18002eb86  xor     r8d, r8d
0x18002eb89  mov     rcx, r12
0x18002eb8c  mov     rax, [rax+60h]
0x18002eb90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eb95  test    eax, eax
0x18002eb97  js      short loc_18002EBB3
0x18002eb99  mov     rdx, [rbp+57h+pv]
0x18002eb9d  lea     rcx, [r14+58h]
0x18002eba1  mov     r8, rdi
0x18002eba4  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18002eba9  mov     rcx, [rbp+57h+pv]; pv
0x18002ebad  call    cs:__imp_CoTaskMemFree
0x18002ebb3  cmp     [r14+7Dh], r13b
0x18002ebb7  jz      loc_18002EC47
0x18002ebbd  xor     r8d, r8d; pwszLanguagesBuffer
0x18002ebc0  mov     [rbp+57h+pulNumLanguages], r13d
0x18002ebc4  lea     r9, [rbp+57h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x18002ebc8  mov     [rbp+57h+pcchLanguagesBuffer], r13d
0x18002ebcc  lea     rdx, [rbp+57h+pulNumLanguages]; pulNumLanguages
0x18002ebd0  lea     esi, [r8+44h]
0x18002ebd4  mov     ecx, esi; dwFlags
0x18002ebd6  call    cs:__imp_GetThreadPreferredUILanguages
0x18002ebdc  test    eax, eax
0x18002ebde  jz      short loc_18002EC47
0x18002ebe0  mov     ecx, [rbp+57h+pcchLanguagesBuffer]
0x18002ebe3  lea     eax, [rsi-42h]
0x18002ebe6  mul     rcx
0x18002ebe9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002ebf0  cmovb   rax, rdi
0x18002ebf4  mov     rcx, rax; unsigned __int64
0x18002ebf7  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002ebfc  mov     rbx, rax
0x18002ebff  test    rax, rax
0x18002ec02  jz      short loc_18002EC3F
0x18002ec04  lea     r9, [rbp+57h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x18002ec08  mov     r8, rax; pwszLanguagesBuffer
0x18002ec0b  lea     rdx, [rbp+57h+pulNumLanguages]; pulNumLanguages
0x18002ec0f  mov     ecx, esi; dwFlags
0x18002ec11  call    cs:__imp_GetThreadPreferredUILanguages
0x18002ec17  test    eax, eax
0x18002ec19  jz      short loc_18002EC3F
0x18002ec1b  mov     rcx, [r14+98h]; lpMem
0x18002ec22  mov     rdi, rbx
0x18002ec25  mov     rbx, r13
0x18002ec28  mov     [r14+98h], r13
0x18002ec2f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002ec34  mov     [r14+98h], rdi
0x18002ec3b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002ec3f  mov     rcx, rbx; lpMem
0x18002ec42  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002ec47  lea     rcx, [rbp+57h+var_50]
0x18002ec4b  mov     [rbp+57h+var_50], r13
0x18002ec4f  call    ?InternalRelease@?$ComPtr@UIPropertyDescription@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPropertyDescription>::InternalRelease(void)
0x18002ec54  xor     edx, edx; pUnkOuter
0x18002ec56  lea     rax, [rbp+57h+var_50]
0x18002ec5a  lea     r9, _GUID_a4f96ed0_f829_476e_81c0_cdc7bd2a0802; riid
0x18002ec61  mov     [rsp+100h+ppv], rax; ppv
0x18002ec66  lea     rcx, CLSID_SAXXMLReader60; rclsid
0x18002ec6d  lea     r8d, [rdx+1]; dwClsContext
0x18002ec71  call    cs:__imp_CoCreateInstance
0x18002ec77  mov     ebx, eax
0x18002ec79  test    eax, eax
0x18002ec7b  js      loc_18002EDF1
0x18002ec81  mov     rcx, [rbp+57h+var_50]
0x18002ec85  mov     rdx, r14
0x18002ec88  mov     rax, [rcx]
0x18002ec8b  mov     rax, [rax+50h]
0x18002ec8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec94  mov     ebx, eax
0x18002ec96  test    eax, eax
0x18002ec98  js      loc_18002EDAA
0x18002ec9e  mov     r9, [rbp+57h+var_50]
0x18002eca2  lea     rcx, [r14+8]
0x18002eca6  mov     rax, r14
0x18002eca9  neg     rax
0x18002ecac  mov     r8, [r9]
0x18002ecaf  sbb     rdx, rdx
0x18002ecb2  and     rdx, rcx
0x18002ecb5  mov     rcx, r9
0x18002ecb8  mov     rax, [r8+70h]
0x18002ecbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ecc1  mov     ebx, eax
0x18002ecc3  test    eax, eax
0x18002ecc5  js      loc_18002EDAA
0x18002eccb  mov     rax, [r14+28h]
0x18002eccf  mov     esi, 0Dh
0x18002ecd4  test    rax, rax
0x18002ecd7  jz      loc_18002ED70
0x18002ecdd  cmp     [rax], r13w
0x18002ece1  jz      loc_18002ED70
0x18002ece7  lea     rcx, [rbp+57h+pulNumLanguages]
0x18002eceb  mov     qword ptr [rbp+57h+pulNumLanguages], r13
0x18002ecef  call    ?InternalRelease@?$ComPtr@UIPropertyDescription@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPropertyDescription>::InternalRelease(void)
0x18002ecf4  lea     r8, [rbp+57h+pulNumLanguages]; struct IXMLDOMSchemaCollection **
0x18002ecf8  mov     rdx, r12; struct IStream *
0x18002ecfb  mov     rcx, r14; this
0x18002ecfe  call    ?_CreateSchemaCollection@CXMLPropStoreSaxParser@@AEAAJPEAUIStream@@PEAPEAUIXMLDOMSchemaCollection@@@Z; CXMLPropStoreSaxParser::_CreateSchemaCollection(IStream *,IXMLDOMSchemaCollection * *)
0x18002ed03  mov     ebx, eax
0x18002ed05  test    eax, eax
0x18002ed07  js      short loc_18002ED67
0x18002ed09  mov     rcx, [rbp+57h+var_50]
0x18002ed0d  lea     rdx, aSchemaValidati; "schema-validation"
0x18002ed14  mov     r8d, edi
0x18002ed17  mov     rax, [rcx]
0x18002ed1a  mov     rax, [rax+20h]
0x18002ed1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed23  mov     ebx, eax
0x18002ed25  test    eax, eax
0x18002ed27  js      short loc_18002ED67
0x18002ed29  mov     rcx, [rbp+57h+var_50]
0x18002ed2d  lea     r8, [rbp+57h+var_D0]
0x18002ed31  mov     rax, qword ptr [rbp+57h+pulNumLanguages]
0x18002ed35  xorps   xmm0, xmm0
0x18002ed38  movups  [rbp+57h+var_D0], xmm0
0x18002ed3c  mov     qword ptr [rbp+57h+var_D0+8], rax
0x18002ed40  xor     edx, edx
0x18002ed42  mov     rax, [rcx]
0x18002ed45  mov     word ptr [rbp+57h+var_D0], si
0x18002ed49  movups  xmm0, [rbp+57h+var_D0]
0x18002ed4d  mov     [rbp+57h+var_C0], rdx
0x18002ed51  lea     rdx, aSchemas; "schemas"
0x18002ed58  mov     rax, [rax+30h]
0x18002ed5c  movaps  [rbp+57h+var_D0], xmm0
0x18002ed60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed65  mov     ebx, eax
0x18002ed67  lea     rcx, [rbp+57h+pulNumLanguages]
0x18002ed6b  call    ?InternalRelease@?$ComPtr@UIPropertyDescription@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPropertyDescription>::InternalRelease(void)
0x18002ed70  test    ebx, ebx
0x18002ed72  js      short loc_18002EDAA
0x18002ed74  mov     rcx, [rbp+57h+var_50]
0x18002ed78  lea     rdx, [rbp+57h+var_D0]
0x18002ed7c  xor     eax, eax
0x18002ed7e  xorps   xmm0, xmm0
0x18002ed81  movups  [rbp+57h+var_D0], xmm0
0x18002ed85  mov     [rbp+57h+var_C0], rax
0x18002ed89  mov     rax, [rcx]
0x18002ed8c  mov     word ptr [rbp+57h+var_D0], si
0x18002ed90  mov     qword ptr [rbp+57h+var_D0+8], r12
0x18002ed94  movups  xmm0, [rbp+57h+var_D0]
0x18002ed98  mov     rax, [rax+98h]
0x18002ed9f  movaps  [rbp+57h+var_D0], xmm0
0x18002eda3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eda8  mov     ebx, eax
0x18002edaa  mov     rcx, [rbp+57h+var_50]
0x18002edae  xor     edx, edx
0x18002edb0  mov     rax, [rcx]
0x18002edb3  mov     rax, [rax+70h]
0x18002edb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002edbc  mov     rcx, [rbp+57h+var_50]
0x18002edc0  xor     edx, edx
0x18002edc2  mov     rax, [rcx]
0x18002edc5  mov     rax, [rax+50h]
0x18002edc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002edce  cmp     [r14+7Ch], r13b
0x18002edd2  jz      short loc_18002EDED
0x18002edd4  mov     rdx, [r14+98h]; pwszLanguagesBuffer
0x18002eddb  test    rdx, rdx
0x18002edde  jz      short loc_18002EDED
0x18002ede0  xor     r8d, r8d; pulNumLanguages
0x18002ede3  lea     ecx, [r8+4]; dwFlags
0x18002ede7  call    cs:__imp_SetThreadPreferredUILanguages
0x18002eded  test    ebx, ebx
0x18002edef  jns     short loc_18002EDF9
0x18002edf1  mov     rcx, r14; this
0x18002edf4  call    ?_TerminateParsing@CXMLPropStoreSaxParser@@AEAAXXZ; CXMLPropStoreSaxParser::_TerminateParsing(void)
0x18002edf9  lea     rcx, [rbp+57h+var_50]
0x18002edfd  call    ?InternalRelease@?$ComPtr@UIPropertyDescription@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPropertyDescription>::InternalRelease(void)
0x18002ee02  lea     rcx, [rbp+57h+var_40]
0x18002ee06  call    ?InternalRelease@?$ComPtr@UIPropertyDescription@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPropertyDescription>::InternalRelease(void)
0x18002ee0b  mov     eax, ebx
0x18002ee0d  mov     rcx, [rbp+57h+var_38]
0x18002ee11  xor     rcx, rsp; StackCookie
0x18002ee14  call    __security_check_cookie
0x18002ee19  mov     rbx, [rsp+100h+arg_10]
0x18002ee21  add     rsp, 0D0h
0x18002ee28  pop     r15
0x18002ee2a  pop     r14
0x18002ee2c  pop     r13
0x18002ee2e  pop     r12
0x18002ee30  pop     rdi
0x18002ee31  pop     rsi
0x18002ee32  pop     rbp
0x18002ee33  retn
```
