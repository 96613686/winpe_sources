# XwpParseLegacyKey(IXMLDOMNode *,int,_DOT11_AUTH_ALGORITHM,_DOT11_CIPHER_ALGORITHM,_WFD_KEY_DATA *,ulong *)

- ea: `0x1800490d4`
- end: `0x1800493a6`
- name: `?XwpParseLegacyKey@@YAKPEAUIXMLDOMNode@@HW4_DOT11_AUTH_ALGORITHM@@W4_DOT11_CIPHER_ALGORITHM@@PEAU_WFD_KEY_DATA@@PEAK@Z`
- size: `722`
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
- `0x1800490d4`
- `0x18006013c`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18004910e`
- `OLEAUT32!__imp_VariantInit` at `0x18004910e`
- `OLEAUT32!__imp_VariantClear` at `0x180049383`
- `OLEAUT32!__imp_VariantClear` at `0x180049383`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall XwpParseLegacyKey(
        struct IXMLDOMNode *a1,
        int a2,
        enum _DOT11_AUTH_ALGORITHM a3,
        unsigned int a4,
        struct _WFD_KEY_DATA *a5,
        unsigned int *a6)
{
  unsigned int *v9; // rdi
  const unsigned __int16 *v10; // rdx
  unsigned int NodeEnumValue; // ebx
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
  v10 = L"WFDLegacyProfile:legacyKey";
  if ( !a2 )
    v10 = L"WFDProfile:legacyKey";
  if ( (unsigned int)XcGetSingleNode(a1, v10, &v28) == 1168 )
  {
    NodeEnumValue = 0;
    goto LABEL_44;
  }
  v12 = a5;
  *((_BYTE *)a5 + 8) = 0;
  v13 = L"WFDLegacyProfile:keyType";
  if ( !a2 )
    v13 = L"WFDProfile:keyType";
  NodeEnumValue = XcGetNodeEnumValue(
                    v28,
                    v13,
                    (const struct _XC_STRING_VALUE_MAPPING *)&off_18006AC20,
                    1u,
                    &v26,
                    0,
                    0,
                    0);
  if ( !NodeEnumValue )
  {
    v14 = L"WFDLegacyProfile:protected";
    if ( !a2 )
      v14 = L"WFDProfile:protected";
    NodeEnumValue = XcGetNodeEnumValue(
                      v28,
                      v14,
                      (const struct _XC_STRING_VALUE_MAPPING *)&off_1800631E0,
                      4u,
                      &v27,
                      0,
                      0,
                      0);
    if ( !NodeEnumValue )
    {
      v15 = v26;
      v16 = v27;
      v17 = L"WFDLegacyProfile:keyMaterial";
      if ( v27 )
      {
        if ( !a2 )
          v17 = L"WFDProfile:keyMaterial";
        NodeHexBinaryValue = XcGetNodeHexBinaryValue(v28, v17, (unsigned __int8 **)&Src, (unsigned int *)&Size);
        NodeEnumValue = NodeHexBinaryValue;
        if ( NodeHexBinaryValue == 1206 )
        {
          if ( v9 )
            *v9 = 262167;
          goto LABEL_42;
        }
        if ( NodeHexBinaryValue )
        {
LABEL_42:
          if ( Src )
            Xc_Process_user_free(Src);
          goto LABEL_44;
        }
        v22 = Size;
        if ( (unsigned int)Size > 0x40 )
        {
          NodeEnumValue = 1206;
          goto LABEL_42;
        }
        memcpy_0((char *)v12 + 9, Src, (unsigned int)Size);
      }
      else
      {
        if ( !a2 )
          v17 = L"WFDProfile:keyMaterial";
        NodeTypedValue = XcGetNodeTypedValue(v28, v17, &pvarg);
        NodeEnumValue = NodeTypedValue;
        if ( NodeTypedValue == 1168 )
          goto LABEL_21;
        if ( NodeTypedValue )
          goto LABEL_44;
        v19 = -1;
        do
          ++v19;
        while ( *(_WORD *)(pvarg.llVal + 2 * v19) );
        if ( v19 > 0xFFFFFFFF )
          goto LABEL_21;
        v20 = ConvertPassPhraseKeyStringToBuffer(
                pvarg.llVal,
                (unsigned int)v19,
                (unsigned int)v32,
                a4,
                0,
                &Size,
                &v25,
                v9);
        NodeEnumValue = v20;
        if ( v20 == 11 )
          goto LABEL_21;
        if ( v20 == 234 )
        {
          if ( v25 != v15 )
          {
            NodeEnumValue = 1206;
            if ( v9 )
              *v9 = 262168;
            goto LABEL_44;
          }
        }
        else if ( v20 )
        {
          goto LABEL_44;
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
              NodeEnumValue = v21,
              v21 == 11) )
        {
LABEL_21:
          NodeEnumValue = 1206;
          goto LABEL_44;
        }
        if ( v21 )
          goto LABEL_44;
        v22 = Size;
      }
      *(_DWORD *)v12 = v15;
      *((_DWORD *)v12 + 1) = v16;
      *((_BYTE *)v12 + 8) = v22;
      goto LABEL_42;
    }
  }
LABEL_44:
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&v28);
  VariantClear(&pvarg);
  return NodeEnumValue;
}

```

## disassembly

```asm
0x1800490d4  mov     [rsp-38h+arg_0], rbx
0x1800490d9  mov     [rsp-38h+arg_10], r8d
0x1800490de  push    rbp
0x1800490df  push    rsi
0x1800490e0  push    rdi
0x1800490e1  push    r12
0x1800490e3  push    r13
0x1800490e5  push    r14
0x1800490e7  push    r15
0x1800490e9  mov     rbp, rsp
0x1800490ec  sub     rsp, 80h
0x1800490f3  mov     r13d, r9d
0x1800490f6  mov     esi, edx
0x1800490f8  mov     rbx, rcx
0x1800490fb  xor     r15d, r15d
0x1800490fe  mov     [rbp+var_3C], r15d
0x180049102  mov     [rbp+var_38], r15d
0x180049106  mov     [rbp+var_40], r15d
0x18004910a  lea     rcx, [rbp+pvarg]; pvarg
0x18004910e  call    cs:__imp_VariantInit
0x180049114  nop
0x180049115  mov     dword ptr [rbp+Size], r15d
0x180049119  mov     [rbp+Src], r15
0x18004911d  mov     [rbp+var_30], r15
0x180049121  mov     rdi, [rbp+arg_28]
0x180049125  test    rdi, rdi
0x180049128  jz      short loc_18004912D
0x18004912a  mov     [rdi], r15d
0x18004912d  lea     rax, aWfdprofileLega; "WFDProfile:legacyKey"
0x180049134  lea     rdx, aWfdlegacyprofi_13; "WFDLegacyProfile:legacyKey"
0x18004913b  test    esi, esi
0x18004913d  cmovz   rdx, rax; unsigned __int16 *
0x180049141  lea     r8, [rbp+var_30]; struct IXMLDOMNode **
0x180049145  mov     rcx, rbx; struct IXMLDOMNode *
0x180049148  call    ?XcGetSingleNode@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; XcGetSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18004914d  cmp     eax, 490h
0x180049152  jnz     short loc_18004915C
0x180049154  mov     ebx, r15d
0x180049157  jmp     loc_180049375
0x18004915c  mov     r14, [rbp+arg_20]
0x180049160  mov     [r14+8], r15b
0x180049164  lea     rax, aWfdprofileKeyt; "WFDProfile:keyType"
0x18004916b  lea     rdx, aWfdlegacyprofi_9; "WFDLegacyProfile:keyType"
0x180049172  test    esi, esi
0x180049174  cmovz   rdx, rax; unsigned __int16 *
0x180049178  mov     [rsp+80h+var_48], r15; int *
0x18004917d  mov     [rsp+80h+var_50], r15d; unsigned int
0x180049182  mov     [rsp+80h+var_58], r15d; int
0x180049187  lea     rax, [rbp+var_3C]
0x18004918b  mov     [rsp+80h+var_60], rax; unsigned int *
0x180049190  mov     r9d, 1; unsigned int
0x180049196  lea     r8, off_18006AC20; struct _XC_STRING_VALUE_MAPPING *
0x18004919d  mov     rcx, [rbp+var_30]; struct IXMLDOMNode *
0x1800491a1  call    ?XcGetNodeEnumValue@@YAKPEAUIXMLDOMNode@@PEBGPEBU_XC_STRING_VALUE_MAPPING@@KPEAKHKPEAH@Z; XcGetNodeEnumValue(IXMLDOMNode *,ushort const *,_XC_STRING_VALUE_MAPPING const *,ulong,ulong *,int,ulong,int *)
0x1800491a6  mov     ebx, eax
0x1800491a8  test    eax, eax
0x1800491aa  jnz     loc_180049375
0x1800491b0  lea     rax, aWfdprofileProt; "WFDProfile:protected"
0x1800491b7  lea     rdx, aWfdlegacyprofi_8; "WFDLegacyProfile:protected"
0x1800491be  test    esi, esi
0x1800491c0  cmovz   rdx, rax; unsigned __int16 *
0x1800491c4  mov     [rsp+80h+var_48], r15; int *
0x1800491c9  mov     [rsp+80h+var_50], r15d; unsigned int
0x1800491ce  mov     [rsp+80h+var_58], r15d; int
0x1800491d3  lea     rax, [rbp+var_38]
0x1800491d7  mov     [rsp+80h+var_60], rax; unsigned int *
0x1800491dc  lea     r9d, [rbx+4]; unsigned int
0x1800491e0  lea     r8, off_1800631E0; struct _XC_STRING_VALUE_MAPPING *
0x1800491e7  mov     rcx, [rbp+var_30]; struct IXMLDOMNode *
0x1800491eb  call    ?XcGetNodeEnumValue@@YAKPEAUIXMLDOMNode@@PEBGPEBU_XC_STRING_VALUE_MAPPING@@KPEAKHKPEAH@Z; XcGetNodeEnumValue(IXMLDOMNode *,ushort const *,_XC_STRING_VALUE_MAPPING const *,ulong,ulong *,int,ulong,int *)
0x1800491f0  mov     ebx, eax
0x1800491f2  test    eax, eax
0x1800491f4  jnz     loc_180049375
0x1800491fa  mov     r15d, [rbp+var_3C]
0x1800491fe  mov     r12d, [rbp+var_38]
0x180049202  lea     rax, aWfdprofileKeym; "WFDProfile:keyMaterial"
0x180049209  lea     rdx, aWfdlegacyprofi_3; "WFDLegacyProfile:keyMaterial"
0x180049210  mov     rcx, [rbp+var_30]; struct IXMLDOMNode *
0x180049214  test    r12d, r12d
0x180049217  jnz     loc_18004930F
0x18004921d  test    esi, esi
0x18004921f  cmovz   rdx, rax; unsigned __int16 *
0x180049223  lea     r8, [rbp+pvarg]; struct tagVARIANT *
0x180049227  call    ?XcGetNodeTypedValue@@YAKPEAUIXMLDOMNode@@PEBGPEAUtagVARIANT@@@Z; XcGetNodeTypedValue(IXMLDOMNode *,ushort const *,tagVARIANT *)
0x18004922c  mov     ebx, eax
0x18004922e  cmp     eax, 490h
0x180049233  jz      short loc_18004925A
0x180049235  xor     edx, edx
0x180049237  test    eax, eax
0x180049239  jnz     loc_180049375
0x18004923f  mov     rcx, qword ptr [rbp+pvarg+8]
0x180049243  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180049247  inc     rsi
0x18004924a  cmp     [rcx+rsi*2], dx
0x18004924e  jnz     short loc_180049247
0x180049250  mov     eax, 0FFFFFFFFh
0x180049255  cmp     rsi, rax
0x180049258  jbe     short loc_180049264
0x18004925a  mov     ebx, 4B6h
0x18004925f  jmp     loc_180049375
0x180049264  mov     [rsp+80h+var_48], rdi
0x180049269  lea     rax, [rbp+var_40]
0x18004926d  mov     qword ptr [rsp+80h+var_50], rax
0x180049272  lea     rax, [rbp+Size]
0x180049276  mov     qword ptr [rsp+80h+var_58], rax
0x18004927b  mov     [rsp+80h+var_60], rdx
0x180049280  mov     r9d, r13d
0x180049283  mov     r8d, [rbp+arg_10]
0x180049287  mov     edx, esi
0x180049289  call    ConvertPassPhraseKeyStringToBuffer
0x18004928e  mov     ebx, eax
0x180049290  cmp     eax, 0Bh
0x180049293  jz      short loc_18004925A
0x180049295  cmp     eax, 0EAh
0x18004929a  jnz     short loc_1800492BB
0x18004929c  cmp     [rbp+var_40], r15d
0x1800492a0  jz      short loc_1800492C3
0x1800492a2  mov     ebx, 4B6h
0x1800492a7  test    rdi, rdi
0x1800492aa  jz      loc_180049375
0x1800492b0  mov     dword ptr [rdi], 40018h
0x1800492b6  jmp     loc_180049375
0x1800492bb  test    eax, eax
0x1800492bd  jnz     loc_180049375
0x1800492c3  cmp     dword ptr [rbp+Size], 40h ; '@'
0x1800492c7  ja      short loc_18004925A
0x1800492c9  lea     rax, [r14+9]
0x1800492cd  mov     [rsp+80h+var_48], rdi
0x1800492d2  lea     rcx, [rbp+var_40]
0x1800492d6  mov     qword ptr [rsp+80h+var_50], rcx
0x1800492db  lea     rcx, [rbp+Size]
0x1800492df  mov     qword ptr [rsp+80h+var_58], rcx
0x1800492e4  mov     [rsp+80h+var_60], rax
0x1800492e9  mov     r9d, r13d
0x1800492ec  mov     r8d, [rbp+arg_10]
0x1800492f0  mov     edx, esi
0x1800492f2  mov     rcx, qword ptr [rbp+pvarg+8]
0x1800492f6  call    ConvertPassPhraseKeyStringToBuffer
0x1800492fb  mov     ebx, eax
0x1800492fd  cmp     eax, 0Bh
0x180049300  jz      loc_18004925A
0x180049306  test    eax, eax
0x180049308  jnz     short loc_180049375
0x18004930a  mov     edi, dword ptr [rbp+Size]
0x18004930d  jmp     short loc_18004935B
0x18004930f  test    esi, esi
0x180049311  cmovz   rdx, rax; unsigned __int16 *
0x180049315  lea     r9, [rbp+Size]; unsigned int *
0x180049319  lea     r8, [rbp+Src]; unsigned __int8 **
0x18004931d  call    ?XcGetNodeHexBinaryValue@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAEPEAK@Z; XcGetNodeHexBinaryValue(IXMLDOMNode *,ushort const *,uchar * *,ulong *)
0x180049322  mov     ebx, eax
0x180049324  cmp     eax, 4B6h
0x180049329  jnz     short loc_180049338
0x18004932b  test    rdi, rdi
0x18004932e  jz      short loc_180049366
0x180049330  mov     dword ptr [rdi], 40017h
0x180049336  jmp     short loc_180049366
0x180049338  test    eax, eax
0x18004933a  jnz     short loc_180049366
0x18004933c  mov     edi, dword ptr [rbp+Size]
0x18004933f  cmp     edi, 40h ; '@'
0x180049342  jbe     short loc_18004934B
0x180049344  mov     ebx, 4B6h
0x180049349  jmp     short loc_180049366
0x18004934b  mov     r8, rdi; Size
0x18004934e  lea     rcx, [r14+9]; void *
0x180049352  mov     rdx, [rbp+Src]; Src
0x180049356  call    memcpy_0
0x18004935b  mov     [r14], r15d
0x18004935e  mov     [r14+4], r12d
0x180049362  mov     [r14+8], dil
0x180049366  mov     rcx, [rbp+Src]; lpMem
0x18004936a  test    rcx, rcx
0x18004936d  jz      short loc_180049375
0x18004936f  call    ?Xc_Process_user_free@@YAXPEAX@Z; Xc_Process_user_free(void *)
0x180049374  nop
0x180049375  lea     rcx, [rbp+var_30]
0x180049379  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18004937e  nop
0x18004937f  lea     rcx, [rbp+pvarg]; pvarg
0x180049383  call    cs:__imp_VariantClear
0x180049389  mov     eax, ebx
0x18004938b  mov     rbx, [rsp+80h+arg_0]
0x180049393  add     rsp, 80h
0x18004939a  pop     r15
0x18004939c  pop     r14
0x18004939e  pop     r13
0x1800493a0  pop     r12
0x1800493a2  pop     rdi
0x1800493a3  pop     rsi
0x1800493a4  pop     rbp
0x1800493a5  retn
```
