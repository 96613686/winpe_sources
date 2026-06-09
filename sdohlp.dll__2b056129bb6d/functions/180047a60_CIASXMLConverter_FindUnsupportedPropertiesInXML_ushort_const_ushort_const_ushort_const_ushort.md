# CIASXMLConverter::FindUnsupportedPropertiesInXML(ushort const *,ushort const *,ushort const *,ushort * *)

- ea: `0x180047a60`
- end: `0x180047c07`
- name: `?FindUnsupportedPropertiesInXML@CIASXMLConverter@@SAJPEBG00PEAPEAG@Z`
- size: `423`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003d140`

## callees

- `0x180024cac`
- `0x18002cd00`
- `0x180042a80`
- `0x180047a60`
- `0x180047c64`
- `0x18004cdf4`
- `0x18004d4c8`
- `0x18004d900`

## string_xrefs

- `0x180047b28`: `iasmigplugin.dll`
- `0x180047b69`: `iasmigplugin.dll`
- `0x180047b21`: `IDR_NAPPROPSMIG_XML_RES_XML`
- `0x180047b62`: `IDR_NAPPROPSMIG_XML_RES_XML`
- `0x180047ad3`: `FindUnsupportedPropertiesInXML(), failed to load ias.xml: %!hresult!`
- `0x180047b70`: `FindUnsupportedPropertiesInXML(), failed to load iasnapidentify.xml  DLL=%S RES=%S: %!hresult!`
- `0x180047bdc`: `FindUnsupportedPropertiesInXML(), failed to get NAP parameters from ias.xml: %!hresult!`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CIASXMLConverter::FindUnsupportedPropertiesInXML(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  int UnsupportedPropertiesInXML; // ebx
  int v6; // edx
  __int64 v8; // rcx
  const unsigned __int16 *v9; // [rsp+58h] [rbp+18h] BYREF
  const unsigned __int16 *v10; // [rsp+60h] [rbp+20h] BYREF

  v10 = a3;
  v9 = a2;
  if ( a1 && a4 )
  {
    v9 = 0;
    v10 = 0;
    UnsupportedPropertiesInXML = CIASMigrationHelper::LoadXMLFromFile(&v9, a1, a3);
    if ( UnsupportedPropertiesInXML >= 0 )
    {
      UnsupportedPropertiesInXML = CIASMigrationHelper::LoadXMLFromResources(
                                     &v10,
                                     L"iasmigplugin.dll",
                                     L"IDR_NAPPROPSMIG_XML_RES_XML");
      if ( UnsupportedPropertiesInXML < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          WppDbgPrint("FindUnsupportedPropertiesInXML(), failed to load iasnapidentify.xml  DLL=%S RES=%S: %!hresult!");
          WPP_SF_sSSd(*((_QWORD *)WPP_GLOBAL_Control + 2));
        }
        goto LABEL_9;
      }
      UnsupportedPropertiesInXML = CIASMigrationHelper::FindUnsupportedPropertiesInXML(v8, &v9, &v10, a4);
      if ( UnsupportedPropertiesInXML >= 0
        || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      {
LABEL_9:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v10);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v9);
        return (unsigned int)UnsupportedPropertiesInXML;
      }
      WppDbgPrint("FindUnsupportedPropertiesInXML(), failed to get NAP parameters from ias.xml: %!hresult!");
      v6 = 20;
    }
    else
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      {
        goto LABEL_9;
      }
      WppDbgPrint("FindUnsupportedPropertiesInXML(), failed to load ias.xml: %!hresult!");
      v6 = 18;
    }
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v6,
      (unsigned int)&WPP_a89d8cb01d6b390d91c3212b6347ecab_Traceguids,
      (unsigned int)"NPSDS",
      UnsupportedPropertiesInXML);
    goto LABEL_9;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180047a60  mov     rax, rsp
0x180047a63  mov     [rax+8], rbx
0x180047a67  mov     [rax+20h], rdi
0x180047a6b  mov     [rax+18h], r8
0x180047a6f  mov     [rax+10h], rdx
0x180047a73  push    rbp
0x180047a74  mov     rbp, rsp
0x180047a77  sub     rsp, 40h
0x180047a7b  mov     rdi, r9
0x180047a7e  test    rcx, rcx
0x180047a81  jz      loc_180047BF2
0x180047a87  test    r9, r9
0x180047a8a  jz      loc_180047BF2
0x180047a90  mov     [rbp+arg_8], 0
0x180047a98  mov     [rbp+arg_10], 0
0x180047aa0  mov     rdx, rcx
0x180047aa3  lea     rcx, [rbp+arg_8]
0x180047aa7  call    ?LoadXMLFromFile@CIASMigrationHelper@@SAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@PEBG@Z; CIASMigrationHelper::LoadXMLFromFile(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,ushort const *)
0x180047aac  mov     ebx, eax
0x180047aae  test    eax, eax
0x180047ab0  jns     short loc_180047B21
0x180047ab2  lea     rcx, WPP_GLOBAL_Control
0x180047ab9  mov     rdx, cs:WPP_GLOBAL_Control
0x180047ac0  cmp     rdx, rcx
0x180047ac3  jz      short loc_180047B07
0x180047ac5  cmp     byte ptr [rdx+19h], 2
0x180047ac9  jb      short loc_180047B07
0x180047acb  test    byte ptr [rdx+1Ch], 10h
0x180047acf  jz      short loc_180047B07
0x180047ad1  mov     edx, eax
0x180047ad3  lea     rcx, aFindunsupporte; "FindUnsupportedPropertiesInXML(), faile"...
0x180047ada  call    WppDbgPrint
0x180047adf  mov     edx, 12h
0x180047ae4  mov     [rsp+40h+var_20], ebx
0x180047ae8  lea     r9, aNpsds; "NPSDS"
0x180047aef  lea     r8, WPP_a89d8cb01d6b390d91c3212b6347ecab_Traceguids
0x180047af6  mov     rcx, cs:WPP_GLOBAL_Control
0x180047afd  mov     rcx, [rcx+10h]
0x180047b01  call    WPP_SF_sd
0x180047b06  nop
0x180047b07  lea     rcx, [rbp+arg_10]
0x180047b0b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180047b10  nop
0x180047b11  lea     rcx, [rbp+arg_8]
0x180047b15  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180047b1a  mov     eax, ebx
0x180047b1c  jmp     loc_180047BF7
0x180047b21  lea     r8, aIdrNappropsmig; "IDR_NAPPROPSMIG_XML_RES_XML"
0x180047b28  lea     rdx, aIasmigpluginDl; "iasmigplugin.dll"
0x180047b2f  lea     rcx, [rbp+arg_10]
0x180047b33  call    ?LoadXMLFromResources@CIASMigrationHelper@@SAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@PEBG1@Z; CIASMigrationHelper::LoadXMLFromResources(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,ushort const *,ushort const *)
0x180047b38  mov     ebx, eax
0x180047b3a  test    eax, eax
0x180047b3c  jns     short loc_180047B95
0x180047b3e  lea     rcx, WPP_GLOBAL_Control
0x180047b45  mov     r9, cs:WPP_GLOBAL_Control
0x180047b4c  cmp     r9, rcx
0x180047b4f  jz      short loc_180047B07
0x180047b51  cmp     byte ptr [r9+19h], 2
0x180047b56  jb      short loc_180047B07
0x180047b58  test    byte ptr [r9+1Ch], 10h
0x180047b5d  jz      short loc_180047B07
0x180047b5f  mov     r9d, eax
0x180047b62  lea     r8, aIdrNappropsmig; "IDR_NAPPROPSMIG_XML_RES_XML"
0x180047b69  lea     rdx, aIasmigpluginDl; "iasmigplugin.dll"
0x180047b70  lea     rcx, aFindunsupporte_0; "FindUnsupportedPropertiesInXML(), faile"...
0x180047b77  call    WppDbgPrint
0x180047b7c  mov     [rsp+40h+var_10], ebx
0x180047b80  mov     rcx, cs:WPP_GLOBAL_Control
0x180047b87  mov     rcx, [rcx+10h]
0x180047b8b  call    WPP_SF_sSSd
0x180047b90  jmp     loc_180047B07
0x180047b95  mov     r9, rdi
0x180047b98  lea     r8, [rbp+arg_10]
0x180047b9c  lea     rdx, [rbp+arg_8]
0x180047ba0  call    ?FindUnsupportedPropertiesInXML@CIASMigrationHelper@@SAJPEBGAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@1PEAPEAG@Z; CIASMigrationHelper::FindUnsupportedPropertiesInXML(ushort const *,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,ushort * *)
0x180047ba5  mov     ebx, eax
0x180047ba7  test    eax, eax
0x180047ba9  jns     loc_180047B07
0x180047baf  lea     rcx, WPP_GLOBAL_Control
0x180047bb6  mov     rax, cs:WPP_GLOBAL_Control
0x180047bbd  cmp     rax, rcx
0x180047bc0  jz      loc_180047B07
0x180047bc6  cmp     byte ptr [rax+19h], 2
0x180047bca  jb      loc_180047B07
0x180047bd0  test    byte ptr [rax+1Ch], 10h
0x180047bd4  jz      loc_180047B07
0x180047bda  mov     edx, ebx
0x180047bdc  lea     rcx, aFindunsupporte_1; "FindUnsupportedPropertiesInXML(), faile"...
0x180047be3  call    WppDbgPrint
0x180047be8  mov     edx, 14h
0x180047bed  jmp     loc_180047AE4
0x180047bf2  mov     eax, 80070057h
0x180047bf7  mov     rbx, [rsp+40h+arg_0]
0x180047bfc  mov     rdi, [rsp+40h+arg_18]
0x180047c01  add     rsp, 40h
0x180047c05  pop     rbp
0x180047c06  retn
```
