# XwpParseSharedKey(IXMLDOMNode *,DOT11_MSMSEC_CONNECTION_PROFILE *,ulong *)

- ea: `0x18000d660`
- end: `0x18000da01`
- name: `?XwpParseSharedKey@@YAKPEAUIXMLDOMNode@@PEAUDOT11_MSMSEC_CONNECTION_PROFILE@@PEAK@Z`
- size: `929`
- prototype: `unsigned int __fastcall(struct IXMLDOMNode *, struct DOT11_MSMSEC_CONNECTION_PROFILE *, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180046c64`

## callees

- `0x18000d660`
- `0x18000dea8`
- `0x18000f7a8`
- `0x18000fb68`
- `0x18000fc48`
- `0x18000fed0`
- `0x180018e1c`
- `0x180019370`
- `0x18003abf0`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d906`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d906`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000d7c4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000d7c4`
- `OLEAUT32!__imp_VariantInit` at `0x18000d69b`
- `OLEAUT32!__imp_VariantInit` at `0x18000d715`
- `OLEAUT32!__imp_VariantInit` at `0x18000d69b`
- `OLEAUT32!__imp_VariantInit` at `0x18000d715`
- `OLEAUT32!__imp_VariantClear` at `0x18000d7ed`
- `OLEAUT32!__imp_VariantClear` at `0x18000d993`
- `OLEAUT32!__imp_VariantClear` at `0x18000d7ed`
- `OLEAUT32!__imp_VariantClear` at `0x18000d993`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall XwpParseSharedKey(
        struct IXMLDOMNode *a1,
        struct DOT11_MSMSEC_CONNECTION_PROFILE *a2,
        unsigned int *a3)
{
  unsigned int v6; // r15d
  unsigned int NodeEnumValue; // ebx
  unsigned __int8 *v8; // rsi
  unsigned int SingleNode; // eax
  struct IXMLDOMNode *v10; // rbx
  int v11; // eax
  int v12; // edi
  char v13; // r13
  unsigned int NodeTypedValue; // eax
  unsigned __int64 v15; // r15
  unsigned int v16; // eax
  unsigned __int8 *v17; // rax
  unsigned int v18; // eax
  unsigned int NodeHexBinaryValue; // eax
  struct IXMLDOMNode *v21; // [rsp+40h] [rbp-29h] BYREF
  unsigned __int8 *v22; // [rsp+48h] [rbp-21h] BYREF
  struct IXMLDOMNode *v23; // [rsp+50h] [rbp-19h] BYREF
  unsigned int *v24; // [rsp+58h] [rbp-11h]
  VARIANTARG v25; // [rsp+60h] [rbp-9h] BYREF
  VARIANTARG pvarg; // [rsp+78h] [rbp+Fh] BYREF
  SIZE_T dwBytes; // [rsp+D8h] [rbp+6Fh] BYREF
  int v28; // [rsp+E0h] [rbp+77h] BYREF
  unsigned int v29; // [rsp+E8h] [rbp+7Fh] BYREF

  v6 = 0;
  NodeEnumValue = 0;
  v21 = 0;
  v29 = 0;
  v28 = 0;
  VariantInit(&pvarg);
  LODWORD(dwBytes) = 0;
  v8 = 0;
  v22 = 0;
  if ( a3 )
    *a3 = 0;
  *((_DWORD *)a2 + 16) = 0;
  *((_QWORD *)a2 + 9) = 0;
  v24 = (unsigned int *)*((_QWORD *)a2 + 3);
  if ( (unsigned int)AuthCipher1xRequiresKeyMaterial(*v24, v24[1], *((unsigned int *)a2 + 8)) )
  {
    SingleNode = XcGetSingleNode(a1, L"WLANProfile:sharedKey", &v21);
    NodeEnumValue = SingleNode;
    if ( SingleNode == 1168 )
    {
      NodeEnumValue = 0;
      goto LABEL_53;
    }
    if ( !SingleNode )
    {
      v10 = v21;
      VariantInit(&v25);
      v23 = 0;
      NodeEnumValue = XcGetSingleNode(v10, L"WLANProfile:keyType", &v23);
      if ( !NodeEnumValue )
      {
        v11 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, VARIANTARG *))v23->lpVtbl->get_nodeTypedValue)(v23, &v25);
        if ( v11 < 0 )
        {
          NodeEnumValue = (unsigned __int16)v11;
          if ( (v11 & 0x1FFF0000) != 0x70000 )
            NodeEnumValue = v11;
        }
        else if ( v25.vt != 8 || !v25.llVal )
        {
          NodeEnumValue = 1168;
        }
      }
      if ( v23 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v23->lpVtbl->Release)(v23);
      if ( NodeEnumValue == 1168 )
      {
        NodeEnumValue = 1206;
      }
      else if ( !NodeEnumValue )
      {
        NodeEnumValue = 1206;
        while ( 1 )
        {
          v12 = 0;
          if ( v6 >= 2 )
            break;
          if ( !lstrcmpW((&off_180063130)[2 * v6], v25.bstrVal) )
          {
            v12 = *((_DWORD *)&off_180063130 + 4 * v6 + 2);
            NodeEnumValue = 0;
            break;
          }
          ++v6;
        }
LABEL_25:
        VariantClear(&v25);
        if ( NodeEnumValue )
          goto LABEL_51;
        NodeEnumValue = XcGetNodeEnumValue(
                          v21,
                          L"WLANProfile:protected",
                          (const struct _XC_STRING_VALUE_MAPPING *)&off_1800631E0,
                          4u,
                          &v29,
                          0,
                          0,
                          0);
        if ( NodeEnumValue )
          goto LABEL_53;
        v13 = v29;
        if ( v29 )
        {
          NodeHexBinaryValue = XcGetNodeHexBinaryValue(v21, L"WLANProfile:keyMaterial", &v22, (unsigned int *)&dwBytes);
          NodeEnumValue = NodeHexBinaryValue;
          if ( NodeHexBinaryValue == 1206 )
          {
            if ( a3 )
              *a3 = 262167;
          }
          else if ( !NodeHexBinaryValue )
          {
            v8 = v22;
            goto LABEL_58;
          }
          v8 = v22;
        }
        else
        {
          NodeTypedValue = XcGetNodeTypedValue(v21, L"WLANProfile:keyMaterial", &pvarg);
          NodeEnumValue = NodeTypedValue;
          if ( NodeTypedValue == 1168 )
            goto LABEL_33;
          if ( NodeTypedValue )
            goto LABEL_53;
          v15 = -1;
          do
            ++v15;
          while ( *(_WORD *)(pvarg.llVal + 2 * v15) );
          if ( v15 > 0xFFFFFFFF
            || (v16 = ConvertPassPhraseKeyStringToBuffer(
                        pvarg.llVal,
                        (unsigned int)v15,
                        *v24,
                        v24[1],
                        0,
                        &dwBytes,
                        &v28,
                        a3),
                NodeEnumValue = v16,
                v16 == 11) )
          {
LABEL_33:
            NodeEnumValue = 1206;
            goto LABEL_53;
          }
          if ( v16 == 234 )
          {
            if ( v28 != v12 )
            {
              NodeEnumValue = 1206;
              if ( a3 )
                *a3 = 262168;
              goto LABEL_53;
            }
          }
          else if ( v16 )
          {
            goto LABEL_53;
          }
          v17 = (unsigned __int8 *)Xc_Process_user_allocate((unsigned int)dwBytes);
          v8 = v17;
          if ( !v17 )
          {
            NodeEnumValue = GetLastError();
            if ( !NodeEnumValue )
              goto LABEL_53;
            goto LABEL_51;
          }
          v18 = ConvertPassPhraseKeyStringToBuffer(
                  pvarg.llVal,
                  (unsigned int)v15,
                  *v24,
                  v24[1],
                  v17,
                  &dwBytes,
                  &v28,
                  a3);
          NodeEnumValue = v18;
          if ( v18 == 11 )
          {
            NodeEnumValue = 1206;
            goto LABEL_51;
          }
          if ( !v18 )
          {
LABEL_58:
            *(_DWORD *)a2 = v13 & 1 | (*(_DWORD *)a2 & 0xFFFFFFFD ^ (2 * (v12 & 1))) & 0xFFFFFFFE;
            *((_DWORD *)a2 + 16) = dwBytes;
            *((_QWORD *)a2 + 9) = v8;
            goto LABEL_53;
          }
        }
LABEL_51:
        if ( v8 )
          Xc_Process_user_free(v8);
        goto LABEL_53;
      }
      v12 = 0;
      goto LABEL_25;
    }
  }
LABEL_53:
  VariantClear(&pvarg);
  if ( v21 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
  return NodeEnumValue;
}

```

## disassembly

```asm
0x18000d660  mov     [rsp-8+arg_0], rbx
0x18000d665  push    rbp
0x18000d666  push    rsi
0x18000d667  push    rdi
0x18000d668  push    r12
0x18000d66a  push    r13
0x18000d66c  push    r14
0x18000d66e  push    r15
0x18000d670  lea     rbp, [rsp-27h]
0x18000d675  sub     rsp, 90h
0x18000d67c  mov     r14, r8
0x18000d67f  mov     r12, rdx
0x18000d682  mov     rdi, rcx
0x18000d685  xor     r15d, r15d
0x18000d688  mov     ebx, r15d
0x18000d68b  mov     [rbp+57h+var_80], r15
0x18000d68f  mov     [rbp+57h+arg_18], r15d
0x18000d693  mov     [rbp+57h+arg_10], r15d
0x18000d697  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18000d69b  call    cs:__imp_VariantInit
0x18000d6a1  nop
0x18000d6a2  mov     dword ptr [rbp+57h+dwBytes], r15d
0x18000d6a6  mov     esi, r15d
0x18000d6a9  mov     [rbp+57h+var_78], r15
0x18000d6ad  test    r14, r14
0x18000d6b0  jz      short loc_18000D6B5
0x18000d6b2  mov     [r14], r15d
0x18000d6b5  mov     [r12+40h], r15d
0x18000d6ba  mov     [r12+48h], r15
0x18000d6bf  mov     rax, [r12+18h]
0x18000d6c4  mov     [rbp+57h+var_68], rax
0x18000d6c8  mov     r8d, [r12+20h]
0x18000d6cd  mov     edx, [rax+4]
0x18000d6d0  mov     ecx, [rax]
0x18000d6d2  call    AuthCipher1xRequiresKeyMaterial
0x18000d6d7  test    eax, eax
0x18000d6d9  jz      loc_18000D98F
0x18000d6df  lea     r8, [rbp+57h+var_80]; struct IXMLDOMNode **
0x18000d6e3  lea     rdx, aWlanprofileSha; "WLANProfile:sharedKey"
0x18000d6ea  mov     rcx, rdi; struct IXMLDOMNode *
0x18000d6ed  call    ?XcGetSingleNode@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; XcGetSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18000d6f2  mov     ebx, eax
0x18000d6f4  mov     edi, 490h
0x18000d6f9  cmp     eax, edi
0x18000d6fb  jnz     short loc_18000D705
0x18000d6fd  mov     ebx, r15d
0x18000d700  jmp     loc_18000D98F
0x18000d705  test    eax, eax
0x18000d707  jnz     loc_18000D98F
0x18000d70d  mov     rbx, [rbp+57h+var_80]
0x18000d711  lea     rcx, [rbp+57h+var_60]; pvarg
0x18000d715  call    cs:__imp_VariantInit
0x18000d71b  mov     [rbp+57h+var_70], r15
0x18000d71f  lea     r8, [rbp+57h+var_70]; struct IXMLDOMNode **
0x18000d723  lea     rdx, aWlanprofileKey_1; "WLANProfile:keyType"
0x18000d72a  mov     rcx, rbx; struct IXMLDOMNode *
0x18000d72d  call    ?XcGetSingleNode@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; XcGetSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18000d732  mov     ebx, eax
0x18000d734  test    eax, eax
0x18000d736  jnz     short loc_18000D777
0x18000d738  mov     rcx, [rbp+57h+var_70]
0x18000d73c  mov     rax, [rcx]
0x18000d73f  lea     rdx, [rbp+57h+var_60]
0x18000d743  mov     rax, [rax+0F0h]
0x18000d74a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d74f  mov     ecx, eax
0x18000d751  test    eax, eax
0x18000d753  js      short loc_18000D766
0x18000d755  cmp     word ptr [rbp+57h+var_60], 8
0x18000d75a  jnz     short loc_18000D762
0x18000d75c  cmp     qword ptr [rbp+57h+var_60+8], r15
0x18000d760  jnz     short loc_18000D777
0x18000d762  mov     ebx, edi
0x18000d764  jmp     short loc_18000D777
0x18000d766  and     eax, 1FFF0000h
0x18000d76b  cmp     eax, 70000h
0x18000d770  movzx   ebx, cx
0x18000d773  jz      short loc_18000D777
0x18000d775  mov     ebx, ecx
0x18000d777  mov     rcx, [rbp+57h+var_70]
0x18000d77b  test    rcx, rcx
0x18000d77e  jz      short loc_18000D78D
0x18000d780  mov     rax, [rcx]
0x18000d783  mov     rax, [rax+10h]
0x18000d787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d78c  nop
0x18000d78d  mov     eax, 4B6h
0x18000d792  cmp     ebx, edi
0x18000d794  jnz     short loc_18000D79D
0x18000d796  mov     ebx, eax
0x18000d798  mov     edi, r15d
0x18000d79b  jmp     short loc_18000D7E9
0x18000d79d  test    ebx, ebx
0x18000d79f  jnz     short loc_18000D798
0x18000d7a1  mov     ebx, eax
0x18000d7a3  lea     rax, off_180063130; "networkKey"
0x18000d7aa  xor     r13d, r13d
0x18000d7ad  mov     edi, r13d
0x18000d7b0  cmp     r15d, 2
0x18000d7b4  jnb     short loc_18000D7E6
0x18000d7b6  mov     edi, r15d
0x18000d7b9  add     rdi, rdi
0x18000d7bc  mov     rdx, qword ptr [rbp+57h+var_60+8]; lpString2
0x18000d7c0  mov     rcx, [rax+rdi*8]; lpString1
0x18000d7c4  call    cs:__imp_lstrcmpW
0x18000d7ca  test    eax, eax
0x18000d7cc  lea     rax, off_180063130; "networkKey"
0x18000d7d3  jz      short loc_18000D7DA
0x18000d7d5  inc     r15d
0x18000d7d8  jmp     short loc_18000D7AD
0x18000d7da  mov     edi, [rax+rdi*8+8]
0x18000d7de  xor     r15d, r15d
0x18000d7e1  mov     ebx, r15d
0x18000d7e4  jmp     short loc_18000D7E9
0x18000d7e6  xor     r15d, r15d
0x18000d7e9  lea     rcx, [rbp+57h+var_60]; pvarg
0x18000d7ed  call    cs:__imp_VariantClear
0x18000d7f3  test    ebx, ebx
0x18000d7f5  jnz     loc_18000D981
0x18000d7fb  mov     [rsp+0C0h+var_88], r15; int *
0x18000d800  mov     [rsp+0C0h+var_90], r15d; unsigned int
0x18000d805  mov     [rsp+0C0h+var_98], r15d; int
0x18000d80a  lea     rax, [rbp+57h+arg_18]
0x18000d80e  mov     [rsp+0C0h+var_A0], rax; unsigned int *
0x18000d813  lea     r9d, [rbx+4]; unsigned int
0x18000d817  lea     r8, off_1800631E0; struct _XC_STRING_VALUE_MAPPING *
0x18000d81e  lea     rdx, aWlanprofilePro; "WLANProfile:protected"
0x18000d825  mov     rcx, [rbp+57h+var_80]; struct IXMLDOMNode *
0x18000d829  call    ?XcGetNodeEnumValue@@YAKPEAUIXMLDOMNode@@PEBGPEBU_XC_STRING_VALUE_MAPPING@@KPEAKHKPEAH@Z; XcGetNodeEnumValue(IXMLDOMNode *,ushort const *,_XC_STRING_VALUE_MAPPING const *,ulong,ulong *,int,ulong,int *)
0x18000d82e  mov     ebx, eax
0x18000d830  test    eax, eax
0x18000d832  jnz     loc_18000D98F
0x18000d838  mov     r13d, [rbp+57h+arg_18]
0x18000d83c  lea     rdx, aWlanprofileKey_0; "WLANProfile:keyMaterial"
0x18000d843  mov     rcx, [rbp+57h+var_80]; struct IXMLDOMNode *
0x18000d847  test    r13d, r13d
0x18000d84a  jnz     loc_18000D95B
0x18000d850  lea     r8, [rbp+57h+pvarg]; struct tagVARIANT *
0x18000d854  call    ?XcGetNodeTypedValue@@YAKPEAUIXMLDOMNode@@PEBGPEAUtagVARIANT@@@Z; XcGetNodeTypedValue(IXMLDOMNode *,ushort const *,tagVARIANT *)
0x18000d859  mov     ebx, eax
0x18000d85b  cmp     eax, 490h
0x18000d860  jz      short loc_18000D888
0x18000d862  test    eax, eax
0x18000d864  jnz     loc_18000D98F
0x18000d86a  mov     rcx, qword ptr [rbp+57h+pvarg+8]
0x18000d86e  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000d872  xor     esi, esi
0x18000d874  inc     r15
0x18000d877  cmp     [rcx+r15*2], si
0x18000d87c  jnz     short loc_18000D874
0x18000d87e  mov     eax, 0FFFFFFFFh
0x18000d883  cmp     r15, rax
0x18000d886  jbe     short loc_18000D892
0x18000d888  mov     ebx, 4B6h
0x18000d88d  jmp     loc_18000D98F
0x18000d892  mov     [rsp+0C0h+var_88], r14
0x18000d897  lea     rax, [rbp+57h+arg_10]
0x18000d89b  mov     qword ptr [rsp+0C0h+var_90], rax
0x18000d8a0  lea     rax, [rbp+57h+dwBytes]
0x18000d8a4  mov     qword ptr [rsp+0C0h+var_98], rax
0x18000d8a9  mov     [rsp+0C0h+var_A0], rsi
0x18000d8ae  mov     r8, [rbp+57h+var_68]
0x18000d8b2  mov     r9d, [r8+4]
0x18000d8b6  mov     r8d, [r8]
0x18000d8b9  mov     edx, r15d
0x18000d8bc  call    ConvertPassPhraseKeyStringToBuffer
0x18000d8c1  mov     ebx, eax
0x18000d8c3  cmp     eax, 0Bh
0x18000d8c6  jz      short loc_18000D888
0x18000d8c8  cmp     eax, 0EAh
0x18000d8cd  jnz     short loc_18000D8EE
0x18000d8cf  cmp     [rbp+57h+arg_10], edi
0x18000d8d2  jz      short loc_18000D8F6
0x18000d8d4  mov     ebx, 4B6h
0x18000d8d9  test    r14, r14
0x18000d8dc  jz      loc_18000D98F
0x18000d8e2  mov     dword ptr [r14], 40018h
0x18000d8e9  jmp     loc_18000D98F
0x18000d8ee  test    eax, eax
0x18000d8f0  jnz     loc_18000D98F
0x18000d8f6  mov     ecx, dword ptr [rbp+57h+dwBytes]; dwBytes
0x18000d8f9  call    ?Xc_Process_user_allocate@@YAPEAX_K@Z; Xc_Process_user_allocate(unsigned __int64)
0x18000d8fe  mov     rsi, rax
0x18000d901  test    rax, rax
0x18000d904  jnz     short loc_18000D914
0x18000d906  call    cs:__imp_GetLastError
0x18000d90c  mov     ebx, eax
0x18000d90e  test    eax, eax
0x18000d910  jnz     short loc_18000D981
0x18000d912  jmp     short loc_18000D98F
0x18000d914  mov     [rsp+0C0h+var_88], r14
0x18000d919  lea     rax, [rbp+57h+arg_10]
0x18000d91d  mov     qword ptr [rsp+0C0h+var_90], rax
0x18000d922  lea     rax, [rbp+57h+dwBytes]
0x18000d926  mov     qword ptr [rsp+0C0h+var_98], rax
0x18000d92b  mov     [rsp+0C0h+var_A0], rsi
0x18000d930  mov     rax, [rbp+57h+var_68]
0x18000d934  mov     r9d, [rax+4]
0x18000d938  mov     r8d, [rax]
0x18000d93b  mov     edx, r15d
0x18000d93e  mov     rcx, qword ptr [rbp+57h+pvarg+8]
0x18000d942  call    ConvertPassPhraseKeyStringToBuffer
0x18000d947  mov     ebx, eax
0x18000d949  cmp     eax, 0Bh
0x18000d94c  jnz     short loc_18000D955
0x18000d94e  mov     ebx, 4B6h
0x18000d953  jmp     short loc_18000D981
0x18000d955  test    eax, eax
0x18000d957  jnz     short loc_18000D981
0x18000d959  jmp     short loc_18000D9D5
0x18000d95b  lea     r9, [rbp+57h+dwBytes]; unsigned int *
0x18000d95f  lea     r8, [rbp+57h+var_78]; unsigned __int8 **
0x18000d963  call    ?XcGetNodeHexBinaryValue@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAEPEAK@Z; XcGetNodeHexBinaryValue(IXMLDOMNode *,ushort const *,uchar * *,ulong *)
0x18000d968  mov     ebx, eax
0x18000d96a  cmp     eax, 4B6h
0x18000d96f  jnz     short loc_18000D9CD
0x18000d971  test    r14, r14
0x18000d974  jz      short loc_18000D97D
0x18000d976  mov     dword ptr [r14], 40017h
0x18000d97d  mov     rsi, [rbp+57h+var_78]
0x18000d981  test    rsi, rsi
0x18000d984  jz      short loc_18000D98F
0x18000d986  mov     rcx, rsi; lpMem
0x18000d989  call    ?Xc_Process_user_free@@YAXPEAX@Z; Xc_Process_user_free(void *)
0x18000d98e  nop
0x18000d98f  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18000d993  call    cs:__imp_VariantClear
0x18000d999  nop
0x18000d99a  mov     rcx, [rbp+57h+var_80]
0x18000d99e  test    rcx, rcx
0x18000d9a1  jz      short loc_18000D9B0
0x18000d9a3  mov     rax, [rcx]
0x18000d9a6  mov     rax, [rax+10h]
0x18000d9aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9af  nop
0x18000d9b0  mov     eax, ebx
0x18000d9b2  mov     rbx, [rsp+0C0h+arg_0]
0x18000d9ba  add     rsp, 90h
0x18000d9c1  pop     r15
0x18000d9c3  pop     r14
0x18000d9c5  pop     r13
0x18000d9c7  pop     r12
0x18000d9c9  pop     rdi
0x18000d9ca  pop     rsi
0x18000d9cb  pop     rbp
0x18000d9cc  retn
0x18000d9cd  test    eax, eax
0x18000d9cf  jnz     short loc_18000D97D
0x18000d9d1  mov     rsi, [rbp+57h+var_78]
0x18000d9d5  mov     eax, [r12]
0x18000d9d9  and     edi, 1
0x18000d9dc  add     edi, edi
0x18000d9de  and     eax, 0FFFFFFFDh
0x18000d9e1  xor     edi, eax
0x18000d9e3  and     edi, 0FFFFFFFEh
0x18000d9e6  and     r13d, 1
0x18000d9ea  or      edi, r13d
0x18000d9ed  mov     [r12], edi
0x18000d9f1  mov     eax, dword ptr [rbp+57h+dwBytes]
0x18000d9f4  mov     [r12+40h], eax
0x18000d9f9  mov     [r12+48h], rsi
0x18000d9fe  jmp     short loc_18000D98F
```
