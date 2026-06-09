# CIASXMLConverter::ConvertIasXMLToCurrentVersion(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x1800477a4`
- end: `0x180047a57`
- name: `?ConvertIasXMLToCurrentVersion@CIASXMLConverter@@SAJPEBG00000@Z`
- size: `691`
- prototype: `static int(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003cee8`
- `0x18003d140`

## callees

- `0x180024cac`
- `0x18002cd00`
- `0x18002f240`
- `0x180042a80`
- `0x1800475b8`
- `0x180047604`
- `0x1800477a4`
- `0x180047c10`
- `0x18004c16c`
- `0x18004d4c8`
- `0x18004d900`

## string_xrefs

- `0x18004788b`: `iasdatastore.dll`
- `0x1800478dc`: `iasmigplugin.dll`
- `0x180047830`: `ConvertIasXMLToCurrentVersion(), failed to load ias.xml: %!hresult!`
- `0x1800478c2`: `ConvertIasXMLToCurrentVersion(), failed to load the reference ias.xml: %!hresult!`
- `0x18004791f`: `ConvertIasXMLToCurrentVersion(), failed to load iasmig.xml: %!hresult!`
- `0x180047979`: `ConvertIasXMLToCurrentVersion(), failed to convert ias.xml to current version: %!hresult!`
- `0x1800479f0`: `ConvertIasXMLToCurrentVersion(), failed to save xml text on disk: %!hresult!`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CIASXMLConverter::ConvertIasXMLToCurrentVersion(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6)
{
  int v8; // ebx
  int v9; // edx
  struct IUnknown *v11; // rbx
  _BYTE v12[32]; // [rsp+30h] [rbp-20h] BYREF
  __int64 v13; // [rsp+70h] [rbp+20h] BYREF
  __int64 v14; // [rsp+80h] [rbp+30h] BYREF

  v14 = 0;
  a5 = 0;
  v13 = 0;
  if ( a1 && a2 && a4 && a6 )
  {
    v8 = CIASMigrationHelper::LoadXMLFromFile(&v14, a1, a3);
    if ( v8 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      {
        goto LABEL_11;
      }
      WppDbgPrint("ConvertIasXMLToCurrentVersion(), failed to load ias.xml: %!hresult!");
      v9 = 10;
LABEL_10:
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v9,
        (unsigned int)&WPP_a89d8cb01d6b390d91c3212b6347ecab_Traceguids,
        (unsigned int)"NPSDS",
        v8);
LABEL_11:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v13);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&a5);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v14);
      return (unsigned int)v8;
    }
    v8 = CIASMigrationHelper::LoadXMLFromResources(&a5, L"iasdatastore.dll", a4);
    if ( v8 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      {
        goto LABEL_11;
      }
      WppDbgPrint("ConvertIasXMLToCurrentVersion(), failed to load the reference ias.xml: %!hresult!");
      v9 = 11;
      goto LABEL_10;
    }
    v8 = CIASMigrationHelper::LoadXMLFromResources(&v13, L"iasmigplugin.dll", a6);
    if ( v8 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      {
        goto LABEL_11;
      }
      WppDbgPrint("ConvertIasXMLToCurrentVersion(), failed to load iasmig.xml: %!hresult!");
      v9 = 12;
      goto LABEL_10;
    }
    v8 = CIASMigrationHelper::ConvertIasXMLToCurrentVersion(&v14, &a5, &v13);
    if ( v8 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      {
        goto LABEL_11;
      }
      WppDbgPrint("ConvertIasXMLToCurrentVersion(), failed to convert ias.xml to current version: %!hresult!");
      v9 = 13;
      goto LABEL_10;
    }
    v11 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v14);
    _variant_t::_variant_t((_variant_t *)v12, a2);
    v8 = MSXML2::IXMLDOMDocument::save(v11, (const struct _variant_t *)v12);
    _variant_t::~_variant_t((_variant_t *)v12);
    if ( v8 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      {
        goto LABEL_11;
      }
      WppDbgPrint("ConvertIasXMLToCurrentVersion(), failed to save xml text on disk: %!hresult!");
      v9 = 14;
      goto LABEL_10;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v13);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&a5);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v14);
    return 0;
  }
  else
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v13);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&a5);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v14);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800477a4  mov     [rsp-18h+arg_8], rbx
0x1800477a9  mov     [rsp-18h+arg_10], r8
0x1800477ae  push    rbp
0x1800477af  push    rsi
0x1800477b0  push    r14
0x1800477b2  mov     rbp, rsp
0x1800477b5  sub     rsp, 50h
0x1800477b9  mov     rsi, r9
0x1800477bc  mov     r14, rdx
0x1800477bf  mov     [rbp+arg_10], 0
0x1800477c7  mov     [rbp+arg_20], 0
0x1800477cf  mov     [rbp+arg_0], 0
0x1800477d7  test    rcx, rcx
0x1800477da  jz      loc_180047A27
0x1800477e0  test    rdx, rdx
0x1800477e3  jz      loc_180047A27
0x1800477e9  test    r9, r9
0x1800477ec  jz      loc_180047A27
0x1800477f2  cmp     [rbp+arg_28], 0
0x1800477f7  jz      loc_180047A27
0x1800477fd  mov     rdx, rcx
0x180047800  lea     rcx, [rbp+arg_10]
0x180047804  call    ?LoadXMLFromFile@CIASMigrationHelper@@SAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@PEBG@Z; CIASMigrationHelper::LoadXMLFromFile(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,ushort const *)
0x180047809  mov     ebx, eax
0x18004780b  test    eax, eax
0x18004780d  jns     short loc_180047888
0x18004780f  lea     rcx, WPP_GLOBAL_Control
0x180047816  mov     rdx, cs:WPP_GLOBAL_Control
0x18004781d  cmp     rdx, rcx
0x180047820  jz      short loc_180047864
0x180047822  cmp     byte ptr [rdx+19h], 2
0x180047826  jb      short loc_180047864
0x180047828  test    byte ptr [rdx+1Ch], 10h
0x18004782c  jz      short loc_180047864
0x18004782e  mov     edx, eax
0x180047830  lea     rcx, aConvertiasxmlt_3; "ConvertIasXMLToCurrentVersion(), failed"...
0x180047837  call    WppDbgPrint
0x18004783c  mov     edx, 0Ah
0x180047841  mov     [rsp+50h+var_30], ebx
0x180047845  lea     r9, aNpsds; "NPSDS"
0x18004784c  lea     r8, WPP_a89d8cb01d6b390d91c3212b6347ecab_Traceguids
0x180047853  mov     rcx, cs:WPP_GLOBAL_Control
0x18004785a  mov     rcx, [rcx+10h]
0x18004785e  call    WPP_SF_sd
0x180047863  nop
0x180047864  lea     rcx, [rbp+arg_0]
0x180047868  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004786d  nop
0x18004786e  lea     rcx, [rbp+arg_20]
0x180047872  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180047877  nop
0x180047878  lea     rcx, [rbp+arg_10]
0x18004787c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180047881  mov     eax, ebx
0x180047883  jmp     loc_180047A49
0x180047888  mov     r8, rsi
0x18004788b  lea     rdx, aIasdatastoreDl; "iasdatastore.dll"
0x180047892  lea     rcx, [rbp+arg_20]
0x180047896  call    ?LoadXMLFromResources@CIASMigrationHelper@@SAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@PEBG1@Z; CIASMigrationHelper::LoadXMLFromResources(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,ushort const *,ushort const *)
0x18004789b  mov     ebx, eax
0x18004789d  test    eax, eax
0x18004789f  jns     short loc_1800478D8
0x1800478a1  lea     rcx, WPP_GLOBAL_Control
0x1800478a8  mov     rdx, cs:WPP_GLOBAL_Control
0x1800478af  cmp     rdx, rcx
0x1800478b2  jz      short loc_180047864
0x1800478b4  cmp     byte ptr [rdx+19h], 2
0x1800478b8  jb      short loc_180047864
0x1800478ba  test    byte ptr [rdx+1Ch], 10h
0x1800478be  jz      short loc_180047864
0x1800478c0  mov     edx, eax
0x1800478c2  lea     rcx, aConvertiasxmlt; "ConvertIasXMLToCurrentVersion(), failed"...
0x1800478c9  call    WppDbgPrint
0x1800478ce  mov     edx, 0Bh
0x1800478d3  jmp     loc_180047841
0x1800478d8  mov     r8, [rbp+arg_28]
0x1800478dc  lea     rdx, aIasmigpluginDl; "iasmigplugin.dll"
0x1800478e3  lea     rcx, [rbp+arg_0]
0x1800478e7  call    ?LoadXMLFromResources@CIASMigrationHelper@@SAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@PEBG1@Z; CIASMigrationHelper::LoadXMLFromResources(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,ushort const *,ushort const *)
0x1800478ec  mov     ebx, eax
0x1800478ee  test    eax, eax
0x1800478f0  jns     short loc_180047935
0x1800478f2  lea     rcx, WPP_GLOBAL_Control
0x1800478f9  mov     rdx, cs:WPP_GLOBAL_Control
0x180047900  cmp     rdx, rcx
0x180047903  jz      loc_180047864
0x180047909  cmp     byte ptr [rdx+19h], 2
0x18004790d  jb      loc_180047864
0x180047913  test    byte ptr [rdx+1Ch], 10h
0x180047917  jz      loc_180047864
0x18004791d  mov     edx, eax
0x18004791f  lea     rcx, aConvertiasxmlt_2; "ConvertIasXMLToCurrentVersion(), failed"...
0x180047926  call    WppDbgPrint
0x18004792b  mov     edx, 0Ch
0x180047930  jmp     loc_180047841
0x180047935  lea     r8, [rbp+arg_0]
0x180047939  lea     rdx, [rbp+arg_20]
0x18004793d  lea     rcx, [rbp+arg_10]
0x180047941  call    ?ConvertIasXMLToCurrentVersion@CIASMigrationHelper@@SAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@00@Z; CIASMigrationHelper::ConvertIasXMLToCurrentVersion(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &)
0x180047946  mov     ebx, eax
0x180047948  test    eax, eax
0x18004794a  jns     short loc_18004798F
0x18004794c  lea     rcx, WPP_GLOBAL_Control
0x180047953  mov     rdx, cs:WPP_GLOBAL_Control
0x18004795a  cmp     rdx, rcx
0x18004795d  jz      loc_180047864
0x180047963  cmp     byte ptr [rdx+19h], 2
0x180047967  jb      loc_180047864
0x18004796d  test    byte ptr [rdx+1Ch], 10h
0x180047971  jz      loc_180047864
0x180047977  mov     edx, eax
0x180047979  lea     rcx, aConvertiasxmlt_0; "ConvertIasXMLToCurrentVersion(), failed"...
0x180047980  call    WppDbgPrint
0x180047985  mov     edx, 0Dh
0x18004798a  jmp     loc_180047841
0x18004798f  lea     rcx, [rbp+arg_10]
0x180047993  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x180047998  mov     rbx, rax
0x18004799b  mov     rdx, r14; unsigned __int16 *
0x18004799e  lea     rcx, [rbp+var_20]; this
0x1800479a2  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x1800479a7  nop
0x1800479a8  lea     rdx, [rbp+var_20]; struct _variant_t *
0x1800479ac  mov     rcx, rbx; this
0x1800479af  call    ?save@IXMLDOMDocument@MSXML2@@QEAAJAEBV_variant_t@@@Z; MSXML2::IXMLDOMDocument::save(_variant_t const &)
0x1800479b4  mov     ebx, eax
0x1800479b6  lea     rcx, [rbp+var_20]; this
0x1800479ba  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800479bf  test    ebx, ebx
0x1800479c1  jns     short loc_180047A06
0x1800479c3  lea     rcx, WPP_GLOBAL_Control
0x1800479ca  mov     rdx, cs:WPP_GLOBAL_Control
0x1800479d1  cmp     rdx, rcx
0x1800479d4  jz      loc_180047864
0x1800479da  cmp     byte ptr [rdx+19h], 2
0x1800479de  jb      loc_180047864
0x1800479e4  test    byte ptr [rdx+1Ch], 10h
0x1800479e8  jz      loc_180047864
0x1800479ee  mov     edx, ebx
0x1800479f0  lea     rcx, aConvertiasxmlt_1; "ConvertIasXMLToCurrentVersion(), failed"...
0x1800479f7  call    WppDbgPrint
0x1800479fc  mov     edx, 0Eh
0x180047a01  jmp     loc_180047841
0x180047a06  lea     rcx, [rbp+arg_0]
0x180047a0a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180047a0f  nop
0x180047a10  lea     rcx, [rbp+arg_20]
0x180047a14  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180047a19  nop
0x180047a1a  lea     rcx, [rbp+arg_10]
0x180047a1e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180047a23  xor     eax, eax
0x180047a25  jmp     short loc_180047A49
0x180047a27  lea     rcx, [rbp+arg_0]
0x180047a2b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180047a30  nop
0x180047a31  lea     rcx, [rbp+arg_20]
0x180047a35  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180047a3a  nop
0x180047a3b  lea     rcx, [rbp+arg_10]
0x180047a3f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180047a44  mov     eax, 80070057h
0x180047a49  mov     rbx, [rsp+50h+arg_8]
0x180047a4e  add     rsp, 50h
0x180047a52  pop     r14
0x180047a54  pop     rsi
0x180047a55  pop     rbp
0x180047a56  retn
```
