# CIASXMLConverter::ConvertEAPBlobs(ushort const *,ushort const *)

- ea: `0x180047628`
- end: `0x18004779d`
- name: `?ConvertEAPBlobs@CIASXMLConverter@@SAJPEBG0@Z`
- size: `373`
- prototype: `static int(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003d140`

## callees

- `0x180024cac`
- `0x18002cd00`
- `0x18002f240`
- `0x180042a80`
- `0x1800475b8`
- `0x180047604`
- `0x180047628`
- `0x180047c10`
- `0x18004bfc8`
- `0x18004d4c8`

## string_xrefs

- `0x18004768d`: `ConvertEAPBlobs(), failed to load ias.xml: %!hresult!`
- `0x180047702`: `ConvertEAPBlobs(), failed to convert EAP blobs in ias.xml: %!hresult!`
- `0x18004776e`: `ConvertEAPBlobs(), failed to save xml text on disk: %!hresult!`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CIASXMLConverter::ConvertEAPBlobs(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        __int64 a3)
{
  int v4; // ebx
  int v5; // edx
  struct IUnknown *v6; // rbx
  _BYTE v8[40]; // [rsp+30h] [rbp-28h] BYREF
  __int64 v9; // [rsp+60h] [rbp+8h] BYREF

  v9 = 0;
  if ( !a1 )
  {
    v4 = -2147024809;
    goto LABEL_20;
  }
  v4 = CIASMigrationHelper::LoadXMLFromFile(&v9, a1, a3);
  if ( v4 >= 0 )
  {
    v4 = CIASMigrationHelper::ConvertEAPConfigurationNodes(&v9);
    if ( v4 >= 0 )
    {
      v6 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v9);
      _variant_t::_variant_t((_variant_t *)v8, a2);
      v4 = MSXML2::IXMLDOMDocument::save(v6, (const struct _variant_t *)v8);
      _variant_t::~_variant_t((_variant_t *)v8);
      if ( v4 >= 0 )
      {
        v4 = 0;
        goto LABEL_20;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WppDbgPrint("ConvertEAPBlobs(), failed to save xml text on disk: %!hresult!");
        v5 = 17;
        goto LABEL_8;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WppDbgPrint("ConvertEAPBlobs(), failed to convert EAP blobs in ias.xml: %!hresult!");
      v5 = 16;
      goto LABEL_8;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WppDbgPrint("ConvertEAPBlobs(), failed to load ias.xml: %!hresult!");
    v5 = 15;
LABEL_8:
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      (unsigned int)&WPP_a89d8cb01d6b390d91c3212b6347ecab_Traceguids,
      (unsigned int)"NPSDS",
      v4);
  }
LABEL_20:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v9);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180047628  mov     [rsp+arg_8], rbx
0x18004762d  push    rdi
0x18004762e  sub     rsp, 50h
0x180047632  mov     rdi, rdx
0x180047635  mov     [rsp+58h+arg_0], 0
0x18004763e  test    rcx, rcx
0x180047641  jnz     short loc_18004764D
0x180047643  mov     ebx, 80070057h
0x180047648  jmp     loc_180047786
0x18004764d  mov     rdx, rcx
0x180047650  lea     rcx, [rsp+58h+arg_0]
0x180047655  call    ?LoadXMLFromFile@CIASMigrationHelper@@SAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@PEBG@Z; CIASMigrationHelper::LoadXMLFromFile(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,ushort const *)
0x18004765a  mov     ebx, eax
0x18004765c  test    eax, eax
0x18004765e  jns     short loc_1800476C5
0x180047660  lea     rax, WPP_GLOBAL_Control
0x180047667  mov     rcx, cs:WPP_GLOBAL_Control
0x18004766e  cmp     rcx, rax
0x180047671  jz      loc_180047786
0x180047677  cmp     byte ptr [rcx+19h], 2
0x18004767b  jb      loc_180047786
0x180047681  test    byte ptr [rcx+1Ch], 10h
0x180047685  jz      loc_180047786
0x18004768b  mov     edx, ebx
0x18004768d  lea     rcx, aConverteapblob_2; "ConvertEAPBlobs(), failed to load ias.x"...
0x180047694  call    WppDbgPrint
0x180047699  mov     edx, 0Fh
0x18004769e  mov     [rsp+58h+var_38], ebx
0x1800476a2  lea     r9, aNpsds; "NPSDS"
0x1800476a9  lea     r8, WPP_a89d8cb01d6b390d91c3212b6347ecab_Traceguids
0x1800476b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800476b7  mov     rcx, [rcx+10h]
0x1800476bb  call    WPP_SF_sd
0x1800476c0  jmp     loc_180047786
0x1800476c5  lea     rcx, [rsp+58h+arg_0]
0x1800476ca  call    ?ConvertEAPConfigurationNodes@CIASMigrationHelper@@SAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z; CIASMigrationHelper::ConvertEAPConfigurationNodes(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &)
0x1800476cf  mov     ebx, eax
0x1800476d1  test    eax, eax
0x1800476d3  jns     short loc_180047715
0x1800476d5  lea     rax, WPP_GLOBAL_Control
0x1800476dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800476e3  cmp     rcx, rax
0x1800476e6  jz      loc_180047786
0x1800476ec  cmp     byte ptr [rcx+19h], 2
0x1800476f0  jb      loc_180047786
0x1800476f6  test    byte ptr [rcx+1Ch], 10h
0x1800476fa  jz      loc_180047786
0x180047700  mov     edx, ebx
0x180047702  lea     rcx, aConverteapblob_1; "ConvertEAPBlobs(), failed to convert EA"...
0x180047709  call    WppDbgPrint
0x18004770e  mov     edx, 10h
0x180047713  jmp     short loc_18004769E
0x180047715  lea     rcx, [rsp+58h+arg_0]
0x18004771a  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004771f  mov     rbx, rax
0x180047722  mov     rdx, rdi; unsigned __int16 *
0x180047725  lea     rcx, [rsp+58h+var_28]; this
0x18004772a  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x18004772f  nop
0x180047730  lea     rdx, [rsp+58h+var_28]; struct _variant_t *
0x180047735  mov     rcx, rbx; this
0x180047738  call    ?save@IXMLDOMDocument@MSXML2@@QEAAJAEBV_variant_t@@@Z; MSXML2::IXMLDOMDocument::save(_variant_t const &)
0x18004773d  mov     ebx, eax
0x18004773f  lea     rcx, [rsp+58h+var_28]; this
0x180047744  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180047749  test    ebx, ebx
0x18004774b  jns     short loc_180047784
0x18004774d  lea     rax, WPP_GLOBAL_Control
0x180047754  mov     rcx, cs:WPP_GLOBAL_Control
0x18004775b  cmp     rcx, rax
0x18004775e  jz      short loc_180047786
0x180047760  cmp     byte ptr [rcx+19h], 2
0x180047764  jb      short loc_180047786
0x180047766  test    byte ptr [rcx+1Ch], 10h
0x18004776a  jz      short loc_180047786
0x18004776c  mov     edx, ebx
0x18004776e  lea     rcx, aConverteapblob; "ConvertEAPBlobs(), failed to save xml t"...
0x180047775  call    WppDbgPrint
0x18004777a  mov     edx, 11h
0x18004777f  jmp     loc_18004769E
0x180047784  xor     ebx, ebx
0x180047786  lea     rcx, [rsp+58h+arg_0]
0x18004778b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180047790  mov     eax, ebx
0x180047792  mov     rbx, [rsp+58h+arg_8]
0x180047797  add     rsp, 50h
0x18004779b  pop     rdi
0x18004779c  retn
```
