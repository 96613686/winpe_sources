# XwpParseGroupID(IXMLDOMNode *,int,_WFD_GROUP_ID *,ulong *)

- ea: `0x180048bcc`
- end: `0x180048dfa`
- name: `?XwpParseGroupID@@YAKPEAUIXMLDOMNode@@HPEAU_WFD_GROUP_ID@@PEAK@Z`
- size: `558`
- prototype: `unsigned int __fastcall(struct IXMLDOMNode *, int, struct _WFD_GROUP_ID *, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800488ec`

## callees

- `0x180009654`
- `0x18000fc48`
- `0x18000fe30`
- `0x180012b40`
- `0x180019a20`
- `0x18004871c`
- `0x180048800`
- `0x180048bcc`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180048c1d`
- `OLEAUT32!__imp_VariantInit` at `0x180048c28`
- `OLEAUT32!__imp_VariantInit` at `0x180048c1d`
- `OLEAUT32!__imp_VariantInit` at `0x180048c28`
- `OLEAUT32!__imp_VariantClear` at `0x180048ccf`
- `OLEAUT32!__imp_VariantClear` at `0x180048d60`
- `OLEAUT32!__imp_VariantClear` at `0x180048d98`
- `OLEAUT32!__imp_VariantClear` at `0x180048da3`
- `OLEAUT32!__imp_VariantClear` at `0x180048ccf`
- `OLEAUT32!__imp_VariantClear` at `0x180048d60`
- `OLEAUT32!__imp_VariantClear` at `0x180048d98`
- `OLEAUT32!__imp_VariantClear` at `0x180048da3`

## string_xrefs

- `0x180048cfc`: `WFDLegacyProfile:SSID`
- `0x180048cf5`: `WFDProfile:SSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall XwpParseGroupID(struct IXMLDOMNode *a1, int a2, struct _WFD_GROUP_ID *a3, unsigned int *a4)
{
  __int128 v8; // xmm6
  int v9; // r13d
  __int128 v10; // xmm7
  int v11; // r12d
  const unsigned __int16 *v12; // rdx
  unsigned int FirstNode; // eax
  unsigned int v14; // ebx
  const unsigned __int16 *v15; // rdx
  unsigned int NodeTypedValue; // eax
  const unsigned __int16 *v17; // rdx
  unsigned int v18; // eax
  const WCHAR *bstrVal; // rbx
  int v20; // eax
  struct IXMLDOMNode *v22; // [rsp+28h] [rbp-79h] BYREF
  __int64 v23; // [rsp+30h] [rbp-71h] BYREF
  __int64 v24; // [rsp+38h] [rbp-69h] BYREF
  VARIANTARG v25; // [rsp+40h] [rbp-61h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-49h] BYREF
  __int128 v27; // [rsp+70h] [rbp-31h]
  __int128 v28; // [rsp+80h] [rbp-21h]
  int v29; // [rsp+90h] [rbp-11h]
  unsigned __int8 v30[4]; // [rsp+98h] [rbp-9h] BYREF
  __int16 v31; // [rsp+9Ch] [rbp-5h]

  v22 = 0;
  v24 = 0;
  v23 = 0;
  VariantInit(&pvarg);
  VariantInit(&v25);
  v8 = 0;
  v9 = 0;
  v27 = 0;
  v10 = 0;
  v28 = 0;
  v29 = 0;
  v11 = 0;
  *(_DWORD *)v30 = 0;
  v31 = 0;
  if ( a4 )
    *a4 = 0;
  v12 = L"WFDLegacyProfile:groupID";
  if ( !a2 )
    v12 = L"WFDProfile:groupID";
  FirstNode = XcGetFirstNode(a1, v12, &v22);
  v14 = FirstNode;
  if ( FirstNode == 1168 )
  {
    v14 = 1206;
    goto LABEL_28;
  }
  if ( FirstNode )
    goto LABEL_28;
  v15 = L"WFDLegacyProfile:deviceAddress";
  if ( !a2 )
    v15 = L"WFDProfile:deviceAddress";
  NodeTypedValue = XcGetNodeTypedValue(v22, v15, &v25);
  v14 = NodeTypedValue;
  if ( NodeTypedValue )
  {
    if ( NodeTypedValue != 1206 && NodeTypedValue != 1168 )
      goto LABEL_28;
    v14 = 1206;
    if ( a4 )
      goto LABEL_28;
  }
  else
  {
    WFDStringToDeviceAddress(v25.bstrVal, v30);
    VariantClear(&v25);
    v11 = *(_DWORD *)v30;
  }
  v17 = L"WFDLegacyProfile:SSID";
  if ( !a2 )
    v17 = L"WFDProfile:SSID";
  v18 = XcGetNodeTypedValue(v22, v17, &pvarg);
  v14 = v18;
  if ( !v18 )
  {
    bstrVal = pvarg.bstrVal;
    if ( !pvarg.llVal
      || WFDValidateSSID(pvarg.bstrVal, a2 == 0)
      || (v20 = WlanStringToUtf8Ssid(bstrVal), v9 = v29, v10 = v28, v8 = v27, v20) )
    {
      v14 = 1206;
    }
    else
    {
      v14 = 0;
    }
    VariantClear(&pvarg);
    goto LABEL_27;
  }
  if ( v18 == 1206 || v18 == 1168 )
  {
    v14 = 1206;
    if ( !a4 )
    {
LABEL_27:
      *(_DWORD *)a3->DeviceAddress = v11;
      *(_WORD *)&a3->DeviceAddress[4] = v31;
      *(_OWORD *)&a3->GroupSSID.uSSIDLength = v8;
      *(_OWORD *)&a3->GroupSSID.ucSSID[12] = v10;
      *(_DWORD *)&a3->GroupSSID.ucSSID[28] = v9;
    }
  }
LABEL_28:
  VariantClear(&v25);
  VariantClear(&pvarg);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v23);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v24);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v22);
  return v14;
}

```

## disassembly

```asm
0x180048bcc  mov     rax, rsp
0x180048bcf  mov     [rax+10h], rbx
0x180048bd3  push    rbp
0x180048bd4  push    rsi
0x180048bd5  push    rdi
0x180048bd6  push    r12
0x180048bd8  push    r13
0x180048bda  push    r14
0x180048bdc  push    r15
0x180048bde  lea     rbp, [rax-5Fh]
0x180048be2  sub     rsp, 0C0h
0x180048be9  movaps  xmmword ptr [rax-48h], xmm6
0x180048bed  movaps  xmmword ptr [rax-58h], xmm7
0x180048bf1  mov     rax, cs:__security_cookie
0x180048bf8  xor     rax, rsp
0x180048bfb  mov     [rbp+57h+var_58], rax
0x180048bff  mov     rsi, r9
0x180048c02  mov     r14, r8
0x180048c05  mov     r15d, edx
0x180048c08  mov     rbx, rcx
0x180048c0b  xor     edi, edi
0x180048c0d  mov     [rbp+57h+var_D0], rdi
0x180048c11  mov     [rbp+57h+var_C0], rdi
0x180048c15  mov     [rbp+57h+var_C8], rdi
0x180048c19  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180048c1d  call    cs:__imp_VariantInit
0x180048c23  nop
0x180048c24  lea     rcx, [rbp+57h+var_B8]; pvarg
0x180048c28  call    cs:__imp_VariantInit
0x180048c2e  nop
0x180048c2f  xorps   xmm6, xmm6
0x180048c32  xor     r13d, r13d
0x180048c35  movups  [rbp+57h+var_88], xmm6
0x180048c39  xorps   xmm7, xmm7
0x180048c3c  movups  [rbp+57h+var_78], xmm7
0x180048c40  mov     [rbp+57h+var_68], r13d
0x180048c44  xor     r12d, r12d
0x180048c47  mov     dword ptr [rbp+57h+var_60], r12d
0x180048c4b  mov     [rbp+57h+var_5C], r12w
0x180048c50  test    rsi, rsi
0x180048c53  jz      short loc_180048C57
0x180048c55  mov     [rsi], edi
0x180048c57  lea     rax, aWfdprofileGrou_1; "WFDProfile:groupID"
0x180048c5e  lea     rdx, aWfdlegacyprofi_11; "WFDLegacyProfile:groupID"
0x180048c65  test    r15d, r15d
0x180048c68  cmovz   rdx, rax; unsigned __int16 *
0x180048c6c  lea     r8, [rbp+57h+var_D0]; struct IXMLDOMNode **
0x180048c70  mov     rcx, rbx; struct IXMLDOMNode *
0x180048c73  call    ?XcGetFirstNode@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; XcGetFirstNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x180048c78  mov     ebx, eax
0x180048c7a  cmp     eax, 490h
0x180048c7f  jnz     short loc_180048C89
0x180048c81  lea     ebx, [rax+26h]
0x180048c84  jmp     loc_180048D94
0x180048c89  test    eax, eax
0x180048c8b  jnz     loc_180048D94
0x180048c91  lea     rax, aWfdprofileDevi; "WFDProfile:deviceAddress"
0x180048c98  lea     rdx, aWfdlegacyprofi_5; "WFDLegacyProfile:deviceAddress"
0x180048c9f  test    r15d, r15d
0x180048ca2  cmovz   rdx, rax; unsigned __int16 *
0x180048ca6  lea     r8, [rbp+57h+var_B8]; struct tagVARIANT *
0x180048caa  mov     rcx, [rbp+57h+var_D0]; struct IXMLDOMNode *
0x180048cae  call    ?XcGetNodeTypedValue@@YAKPEAUIXMLDOMNode@@PEBGPEAUtagVARIANT@@@Z; XcGetNodeTypedValue(IXMLDOMNode *,ushort const *,tagVARIANT *)
0x180048cb3  mov     ebx, eax
0x180048cb5  mov     edi, 4B6h
0x180048cba  test    eax, eax
0x180048cbc  jnz     short loc_180048CDB
0x180048cbe  lea     rdx, [rbp+57h+var_60]; unsigned __int8 *
0x180048cc2  mov     rcx, qword ptr [rbp+57h+var_B8+8]; unsigned __int16 *
0x180048cc6  call    ?WFDStringToDeviceAddress@@YAKPEAGQEAE@Z; WFDStringToDeviceAddress(ushort *,uchar * const)
0x180048ccb  lea     rcx, [rbp+57h+var_B8]; pvarg
0x180048ccf  call    cs:__imp_VariantClear
0x180048cd5  mov     r12d, dword ptr [rbp+57h+var_60]
0x180048cd9  jmp     short loc_180048CF5
0x180048cdb  cmp     eax, edi
0x180048cdd  jz      short loc_180048CEA
0x180048cdf  cmp     eax, 490h
0x180048ce4  jnz     loc_180048D94
0x180048cea  mov     ebx, edi
0x180048cec  test    rsi, rsi
0x180048cef  jnz     loc_180048D94
0x180048cf5  lea     rax, aWfdprofileSsid; "WFDProfile:SSID"
0x180048cfc  lea     rdx, aWfdlegacyprofi_14; "WFDLegacyProfile:SSID"
0x180048d03  test    r15d, r15d
0x180048d06  cmovz   rdx, rax; unsigned __int16 *
0x180048d0a  lea     r8, [rbp+57h+pvarg]; struct tagVARIANT *
0x180048d0e  mov     rcx, [rbp+57h+var_D0]; struct IXMLDOMNode *
0x180048d12  call    ?XcGetNodeTypedValue@@YAKPEAUIXMLDOMNode@@PEBGPEAUtagVARIANT@@@Z; XcGetNodeTypedValue(IXMLDOMNode *,ushort const *,tagVARIANT *)
0x180048d17  mov     ebx, eax
0x180048d19  test    eax, eax
0x180048d1b  jnz     short loc_180048D68
0x180048d1d  xor     edx, edx
0x180048d1f  test    r15d, r15d
0x180048d22  setz    dl; int
0x180048d25  mov     rbx, qword ptr [rbp+57h+pvarg+8]
0x180048d29  test    rbx, rbx
0x180048d2c  jz      short loc_180048D5A
0x180048d2e  mov     rcx, rbx; String2
0x180048d31  call    ?WFDValidateSSID@@YAKPEAGH@Z; WFDValidateSSID(ushort *,int)
0x180048d36  test    eax, eax
0x180048d38  jnz     short loc_180048D5A
0x180048d3a  lea     rdx, [rbp+57h+var_88]
0x180048d3e  mov     rcx, rbx; lpWideCharStr
0x180048d41  call    WlanStringToUtf8Ssid
0x180048d46  mov     r13d, [rbp+57h+var_68]
0x180048d4a  movups  xmm7, [rbp+57h+var_78]
0x180048d4e  movups  xmm6, [rbp+57h+var_88]
0x180048d52  test    eax, eax
0x180048d54  jnz     short loc_180048D5A
0x180048d56  xor     ebx, ebx
0x180048d58  jmp     short loc_180048D5C
0x180048d5a  mov     ebx, edi
0x180048d5c  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180048d60  call    cs:__imp_VariantClear
0x180048d66  jmp     short loc_180048D7A
0x180048d68  cmp     eax, edi
0x180048d6a  jz      short loc_180048D73
0x180048d6c  cmp     eax, 490h
0x180048d71  jnz     short loc_180048D94
0x180048d73  mov     ebx, edi
0x180048d75  test    rsi, rsi
0x180048d78  jnz     short loc_180048D94
0x180048d7a  mov     [r14], r12d
0x180048d7d  movzx   eax, [rbp+57h+var_5C]
0x180048d81  mov     [r14+4], ax
0x180048d86  movups  xmmword ptr [r14+8], xmm6
0x180048d8b  movups  xmmword ptr [r14+18h], xmm7
0x180048d90  mov     [r14+28h], r13d
0x180048d94  lea     rcx, [rbp+57h+var_B8]; pvarg
0x180048d98  call    cs:__imp_VariantClear
0x180048d9e  nop
0x180048d9f  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180048da3  call    cs:__imp_VariantClear
0x180048da9  nop
0x180048daa  lea     rcx, [rbp+57h+var_C8]
0x180048dae  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180048db3  nop
0x180048db4  lea     rcx, [rbp+57h+var_C0]
0x180048db8  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180048dbd  nop
0x180048dbe  lea     rcx, [rbp+57h+var_D0]
0x180048dc2  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180048dc7  mov     eax, ebx
0x180048dc9  mov     rcx, [rbp+57h+var_58]
0x180048dcd  xor     rcx, rsp; StackCookie
0x180048dd0  call    __security_check_cookie
0x180048dd5  lea     r11, [rsp+0F0h+var_30]
0x180048ddd  mov     rbx, [r11+48h]
0x180048de1  movaps  xmm6, xmmword ptr [r11-10h]
0x180048de6  movaps  xmm7, xmmword ptr [r11-20h]
0x180048deb  mov     rsp, r11
0x180048dee  pop     r15
0x180048df0  pop     r14
0x180048df2  pop     r13
0x180048df4  pop     r12
0x180048df6  pop     rdi
0x180048df7  pop     rsi
0x180048df8  pop     rbp
0x180048df9  retn
```
