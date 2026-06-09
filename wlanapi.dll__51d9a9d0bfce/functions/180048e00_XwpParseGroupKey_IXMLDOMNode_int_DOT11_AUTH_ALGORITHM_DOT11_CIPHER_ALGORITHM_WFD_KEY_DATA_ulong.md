# XwpParseGroupKey(IXMLDOMNode *,int,_DOT11_AUTH_ALGORITHM,_DOT11_CIPHER_ALGORITHM,_WFD_KEY_DATA *,ulong *)

- ea: `0x180048e00`
- end: `0x1800490cb`
- name: `?XwpParseGroupKey@@YAKPEAUIXMLDOMNode@@HW4_DOT11_AUTH_ALGORITHM@@W4_DOT11_CIPHER_ALGORITHM@@PEAU_WFD_KEY_DATA@@PEAK@Z`
- size: `715`
- prototype: `unsigned int __usercall@<eax>(struct IXMLDOMNode *@<rcx>, int@<edx>, enum _DOT11_AUTH_ALGORITHM@<r8d>, enum _DOT11_CIPHER_ALGORITHM@<r9d>, struct _WFD_KEY_DATA *, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180049530`

## callees

- `0x180009654`
- `0x18000f7a8`
- `0x18000fb68`
- `0x18000fc48`
- `0x18000fed0`
- `0x180019370`
- `0x18003abf0`
- `0x180048e00`
- `0x18006013c`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180048e3a`
- `OLEAUT32!__imp_VariantInit` at `0x180048e3a`
- `OLEAUT32!__imp_VariantClear` at `0x1800490a8`
- `OLEAUT32!__imp_VariantClear` at `0x1800490a8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall XwpParseGroupKey(
        struct IXMLDOMNode *a1,
        int a2,
        enum _DOT11_AUTH_ALGORITHM a3,
        unsigned int a4,
        struct _WFD_KEY_DATA *a5,
        unsigned int *a6)
{
  unsigned int *v9; // rdi
  const unsigned __int16 *v10; // rdx
  unsigned int SingleNode; // ebx
  struct _WFD_KEY_DATA *v12; // r14
  const unsigned __int16 *v13; // rdx
  const unsigned __int16 *v14; // rdx
  unsigned int v15; // r15d
  unsigned int v16; // r12d
  const unsigned __int16 *v17; // rdx
  unsigned int NodeTypedValue; // eax
  unsigned __int64 v19; // rsi
  unsigned int v20; // eax
  unsigned int v21; // eax
  char v22; // di
  unsigned int NodeHexBinaryValue; // eax
  int v25; // [rsp+40h] [rbp-40h] BYREF
  unsigned int v26; // [rsp+44h] [rbp-3Ch] BYREF
  unsigned int v27; // [rsp+48h] [rbp-38h] BYREF
  struct IXMLDOMNode *v28; // [rsp+50h] [rbp-30h] BYREF
  void *Src; // [rsp+58h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-20h] BYREF
  size_t Size; // [rsp+C8h] [rbp+48h] BYREF
  enum _DOT11_AUTH_ALGORITHM v32; // [rsp+D0h] [rbp+50h]

  v32 = a3;
  v26 = 0;
  v27 = 0;
  v25 = 0;
  VariantInit(&pvarg);
  LODWORD(Size) = 0;
  Src = 0;
  v28 = 0;
  v9 = a6;
  if ( a6 )
    *a6 = 0;
  v10 = L"WFDLegacyProfile:groupKey";
  if ( !a2 )
    v10 = L"WFDProfile:groupKey";
  SingleNode = XcGetSingleNode(a1, v10, &v28);
  if ( !SingleNode )
  {
    v12 = a5;
    *((_BYTE *)a5 + 8) = 0;
    v13 = L"WFDLegacyProfile:keyType";
    if ( !a2 )
      v13 = L"WFDProfile:keyType";
    SingleNode = XcGetNodeEnumValue(
                   v28,
                   v13,
                   (const struct _XC_STRING_VALUE_MAPPING *)&off_18006AC30,
                   2u,
                   &v26,
                   0,
                   0,
                   0);
    if ( !SingleNode )
    {
      v14 = L"WFDLegacyProfile:protected";
      if ( !a2 )
        v14 = L"WFDProfile:protected";
      SingleNode = XcGetNodeEnumValue(
                     v28,
                     v14,
                     (const struct _XC_STRING_VALUE_MAPPING *)&off_1800631E0,
                     4u,
                     &v27,
                     0,
                     0,
                     0);
      if ( !SingleNode )
      {
        v15 = v26;
        v16 = v27;
        v17 = L"WFDLegacyProfile:keyMaterial";
        if ( v27 )
        {
          if ( !a2 )
            v17 = L"WFDProfile:keyMaterial";
          NodeHexBinaryValue = XcGetNodeHexBinaryValue(v28, v17, (unsigned __int8 **)&Src, (unsigned int *)&Size);
          SingleNode = NodeHexBinaryValue;
          if ( NodeHexBinaryValue == 1206 )
          {
            if ( v9 )
              *v9 = 262167;
            goto LABEL_41;
          }
          if ( NodeHexBinaryValue )
          {
LABEL_41:
            if ( Src )
              Xc_Process_user_free(Src);
            goto LABEL_43;
          }
          v22 = Size;
          if ( (unsigned int)Size > 0x40 )
          {
            SingleNode = 1206;
            goto LABEL_41;
          }
          memcpy_0((char *)v12 + 9, Src, (unsigned int)Size);
        }
        else
        {
          if ( !a2 )
            v17 = L"WFDProfile:keyMaterial";
          NodeTypedValue = XcGetNodeTypedValue(v28, v17, &pvarg);
          SingleNode = NodeTypedValue;
          if ( NodeTypedValue == 1168 )
            goto LABEL_20;
          if ( NodeTypedValue )
            goto LABEL_43;
          v19 = -1;
          do
            ++v19;
          while ( *(_WORD *)(pvarg.llVal + 2 * v19) );
          if ( v19 > 0xFFFFFFFF )
            goto LABEL_20;
          v20 = ConvertPassPhraseKeyStringToBuffer(
                  pvarg.llVal,
                  (unsigned int)v19,
                  (unsigned int)v32,
                  a4,
                  0,
                  &Size,
                  &v25,
                  v9);
          SingleNode = v20;
          if ( v20 == 11 )
            goto LABEL_20;
          if ( v20 == 234 )
          {
            if ( v25 != v15 )
            {
              SingleNode = 1206;
              if ( v9 )
                *v9 = 262168;
              goto LABEL_43;
            }
          }
          else if ( v20 )
          {
            goto LABEL_43;
          }
          if ( (unsigned int)Size > 0x40
            || (v21 = ConvertPassPhraseKeyStringToBuffer(
                        pvarg.llVal,
                        (unsigned int)v19,
                        (unsigned int)v32,
                        a4,
                        (char *)v12 + 9,
                        &Size,
                        &v25,
                        v9),
                SingleNode = v21,
                v21 == 11) )
          {
LABEL_20:
            SingleNode = 1206;
            goto LABEL_43;
          }
          if ( v21 )
            goto LABEL_43;
          v22 = Size;
        }
        *(_DWORD *)v12 = v15;
        *((_DWORD *)v12 + 1) = v16;
        *((_BYTE *)v12 + 8) = v22;
        goto LABEL_41;
      }
    }
  }
LABEL_43:
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&v28);
  VariantClear(&pvarg);
  return SingleNode;
}

```

## disassembly

```asm
0x180048e00  mov     [rsp-38h+arg_0], rbx
0x180048e05  mov     [rsp-38h+arg_10], r8d
0x180048e0a  push    rbp
0x180048e0b  push    rsi
0x180048e0c  push    rdi
0x180048e0d  push    r12
0x180048e0f  push    r13
0x180048e11  push    r14
0x180048e13  push    r15
0x180048e15  mov     rbp, rsp
0x180048e18  sub     rsp, 80h
0x180048e1f  mov     r13d, r9d
0x180048e22  mov     esi, edx
0x180048e24  mov     rbx, rcx
0x180048e27  xor     r15d, r15d
0x180048e2a  mov     [rbp+var_3C], r15d
0x180048e2e  mov     [rbp+var_38], r15d
0x180048e32  mov     [rbp+var_40], r15d
0x180048e36  lea     rcx, [rbp+pvarg]; pvarg
0x180048e3a  call    cs:__imp_VariantInit
0x180048e40  nop
0x180048e41  mov     dword ptr [rbp+Size], r15d
0x180048e45  mov     [rbp+Src], r15
0x180048e49  mov     [rbp+var_30], r15
0x180048e4d  mov     rdi, [rbp+arg_28]
0x180048e51  test    rdi, rdi
0x180048e54  jz      short loc_180048E59
0x180048e56  mov     [rdi], r15d
0x180048e59  lea     rax, aWfdprofileGrou_0; "WFDProfile:groupKey"
0x180048e60  lea     rdx, aWfdlegacyprofi_2; "WFDLegacyProfile:groupKey"
0x180048e67  test    esi, esi
0x180048e69  cmovz   rdx, rax; unsigned __int16 *
0x180048e6d  lea     r8, [rbp+var_30]; struct IXMLDOMNode **
0x180048e71  mov     rcx, rbx; struct IXMLDOMNode *
0x180048e74  call    ?XcGetSingleNode@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; XcGetSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x180048e79  mov     ebx, eax
0x180048e7b  test    eax, eax
0x180048e7d  jnz     loc_18004909A
0x180048e83  mov     r14, [rbp+arg_20]
0x180048e87  mov     [r14+8], r15b
0x180048e8b  lea     rax, aWfdprofileKeyt; "WFDProfile:keyType"
0x180048e92  lea     rdx, aWfdlegacyprofi_9; "WFDLegacyProfile:keyType"
0x180048e99  test    esi, esi
0x180048e9b  cmovz   rdx, rax; unsigned __int16 *
0x180048e9f  mov     [rsp+80h+var_48], r15; int *
0x180048ea4  mov     [rsp+80h+var_50], r15d; unsigned int
0x180048ea9  mov     [rsp+80h+var_58], r15d; int
0x180048eae  lea     rax, [rbp+var_3C]
0x180048eb2  mov     [rsp+80h+var_60], rax; unsigned int *
0x180048eb7  lea     r9d, [rbx+2]; unsigned int
0x180048ebb  lea     r8, off_18006AC30; struct _XC_STRING_VALUE_MAPPING *
0x180048ec2  mov     rcx, [rbp+var_30]; struct IXMLDOMNode *
0x180048ec6  call    ?XcGetNodeEnumValue@@YAKPEAUIXMLDOMNode@@PEBGPEBU_XC_STRING_VALUE_MAPPING@@KPEAKHKPEAH@Z; XcGetNodeEnumValue(IXMLDOMNode *,ushort const *,_XC_STRING_VALUE_MAPPING const *,ulong,ulong *,int,ulong,int *)
0x180048ecb  mov     ebx, eax
0x180048ecd  test    eax, eax
0x180048ecf  jnz     loc_18004909A
0x180048ed5  lea     rax, aWfdprofileProt; "WFDProfile:protected"
0x180048edc  lea     rdx, aWfdlegacyprofi_8; "WFDLegacyProfile:protected"
0x180048ee3  test    esi, esi
0x180048ee5  cmovz   rdx, rax; unsigned __int16 *
0x180048ee9  mov     [rsp+80h+var_48], r15; int *
0x180048eee  mov     [rsp+80h+var_50], r15d; unsigned int
0x180048ef3  mov     [rsp+80h+var_58], r15d; int
0x180048ef8  lea     rax, [rbp+var_38]
0x180048efc  mov     [rsp+80h+var_60], rax; unsigned int *
0x180048f01  lea     r9d, [rbx+4]; unsigned int
0x180048f05  lea     r8, off_1800631E0; struct _XC_STRING_VALUE_MAPPING *
0x180048f0c  mov     rcx, [rbp+var_30]; struct IXMLDOMNode *
0x180048f10  call    ?XcGetNodeEnumValue@@YAKPEAUIXMLDOMNode@@PEBGPEBU_XC_STRING_VALUE_MAPPING@@KPEAKHKPEAH@Z; XcGetNodeEnumValue(IXMLDOMNode *,ushort const *,_XC_STRING_VALUE_MAPPING const *,ulong,ulong *,int,ulong,int *)
0x180048f15  mov     ebx, eax
0x180048f17  test    eax, eax
0x180048f19  jnz     loc_18004909A
0x180048f1f  mov     r15d, [rbp+var_3C]
0x180048f23  mov     r12d, [rbp+var_38]
0x180048f27  lea     rax, aWfdprofileKeym; "WFDProfile:keyMaterial"
0x180048f2e  lea     rdx, aWfdlegacyprofi_3; "WFDLegacyProfile:keyMaterial"
0x180048f35  mov     rcx, [rbp+var_30]; struct IXMLDOMNode *
0x180048f39  test    r12d, r12d
0x180048f3c  jnz     loc_180049034
0x180048f42  test    esi, esi
0x180048f44  cmovz   rdx, rax; unsigned __int16 *
0x180048f48  lea     r8, [rbp+pvarg]; struct tagVARIANT *
0x180048f4c  call    ?XcGetNodeTypedValue@@YAKPEAUIXMLDOMNode@@PEBGPEAUtagVARIANT@@@Z; XcGetNodeTypedValue(IXMLDOMNode *,ushort const *,tagVARIANT *)
0x180048f51  mov     ebx, eax
0x180048f53  cmp     eax, 490h
0x180048f58  jz      short loc_180048F7F
0x180048f5a  xor     edx, edx
0x180048f5c  test    eax, eax
0x180048f5e  jnz     loc_18004909A
0x180048f64  mov     rcx, qword ptr [rbp+pvarg+8]
0x180048f68  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180048f6c  inc     rsi
0x180048f6f  cmp     [rcx+rsi*2], dx
0x180048f73  jnz     short loc_180048F6C
0x180048f75  mov     eax, 0FFFFFFFFh
0x180048f7a  cmp     rsi, rax
0x180048f7d  jbe     short loc_180048F89
0x180048f7f  mov     ebx, 4B6h
0x180048f84  jmp     loc_18004909A
0x180048f89  mov     [rsp+80h+var_48], rdi
0x180048f8e  lea     rax, [rbp+var_40]
0x180048f92  mov     qword ptr [rsp+80h+var_50], rax
0x180048f97  lea     rax, [rbp+Size]
0x180048f9b  mov     qword ptr [rsp+80h+var_58], rax
0x180048fa0  mov     [rsp+80h+var_60], rdx
0x180048fa5  mov     r9d, r13d
0x180048fa8  mov     r8d, [rbp+arg_10]
0x180048fac  mov     edx, esi
0x180048fae  call    ConvertPassPhraseKeyStringToBuffer
0x180048fb3  mov     ebx, eax
0x180048fb5  cmp     eax, 0Bh
0x180048fb8  jz      short loc_180048F7F
0x180048fba  cmp     eax, 0EAh
0x180048fbf  jnz     short loc_180048FE0
0x180048fc1  cmp     [rbp+var_40], r15d
0x180048fc5  jz      short loc_180048FE8
0x180048fc7  mov     ebx, 4B6h
0x180048fcc  test    rdi, rdi
0x180048fcf  jz      loc_18004909A
0x180048fd5  mov     dword ptr [rdi], 40018h
0x180048fdb  jmp     loc_18004909A
0x180048fe0  test    eax, eax
0x180048fe2  jnz     loc_18004909A
0x180048fe8  cmp     dword ptr [rbp+Size], 40h ; '@'
0x180048fec  ja      short loc_180048F7F
0x180048fee  lea     rax, [r14+9]
0x180048ff2  mov     [rsp+80h+var_48], rdi
0x180048ff7  lea     rcx, [rbp+var_40]
0x180048ffb  mov     qword ptr [rsp+80h+var_50], rcx
0x180049000  lea     rcx, [rbp+Size]
0x180049004  mov     qword ptr [rsp+80h+var_58], rcx
0x180049009  mov     [rsp+80h+var_60], rax
0x18004900e  mov     r9d, r13d
0x180049011  mov     r8d, [rbp+arg_10]
0x180049015  mov     edx, esi
0x180049017  mov     rcx, qword ptr [rbp+pvarg+8]
0x18004901b  call    ConvertPassPhraseKeyStringToBuffer
0x180049020  mov     ebx, eax
0x180049022  cmp     eax, 0Bh
0x180049025  jz      loc_180048F7F
0x18004902b  test    eax, eax
0x18004902d  jnz     short loc_18004909A
0x18004902f  mov     edi, dword ptr [rbp+Size]
0x180049032  jmp     short loc_180049080
0x180049034  test    esi, esi
0x180049036  cmovz   rdx, rax; unsigned __int16 *
0x18004903a  lea     r9, [rbp+Size]; unsigned int *
0x18004903e  lea     r8, [rbp+Src]; unsigned __int8 **
0x180049042  call    ?XcGetNodeHexBinaryValue@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAEPEAK@Z; XcGetNodeHexBinaryValue(IXMLDOMNode *,ushort const *,uchar * *,ulong *)
0x180049047  mov     ebx, eax
0x180049049  cmp     eax, 4B6h
0x18004904e  jnz     short loc_18004905D
0x180049050  test    rdi, rdi
0x180049053  jz      short loc_18004908B
0x180049055  mov     dword ptr [rdi], 40017h
0x18004905b  jmp     short loc_18004908B
0x18004905d  test    eax, eax
0x18004905f  jnz     short loc_18004908B
0x180049061  mov     edi, dword ptr [rbp+Size]
0x180049064  cmp     edi, 40h ; '@'
0x180049067  jbe     short loc_180049070
0x180049069  mov     ebx, 4B6h
0x18004906e  jmp     short loc_18004908B
0x180049070  mov     r8, rdi; Size
0x180049073  lea     rcx, [r14+9]; void *
0x180049077  mov     rdx, [rbp+Src]; Src
0x18004907b  call    memcpy_0
0x180049080  mov     [r14], r15d
0x180049083  mov     [r14+4], r12d
0x180049087  mov     [r14+8], dil
0x18004908b  mov     rcx, [rbp+Src]; lpMem
0x18004908f  test    rcx, rcx
0x180049092  jz      short loc_18004909A
0x180049094  call    ?Xc_Process_user_free@@YAXPEAX@Z; Xc_Process_user_free(void *)
0x180049099  nop
0x18004909a  lea     rcx, [rbp+var_30]
0x18004909e  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x1800490a3  nop
0x1800490a4  lea     rcx, [rbp+pvarg]; pvarg
0x1800490a8  call    cs:__imp_VariantClear
0x1800490ae  mov     eax, ebx
0x1800490b0  mov     rbx, [rsp+80h+arg_0]
0x1800490b8  add     rsp, 80h
0x1800490bf  pop     r15
0x1800490c1  pop     r14
0x1800490c3  pop     r13
0x1800490c5  pop     r12
0x1800490c7  pop     rdi
0x1800490c8  pop     rsi
0x1800490c9  pop     rbp
0x1800490ca  retn
```
