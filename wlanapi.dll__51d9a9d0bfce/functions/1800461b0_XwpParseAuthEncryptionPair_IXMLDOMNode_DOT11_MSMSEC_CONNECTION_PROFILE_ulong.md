# XwpParseAuthEncryptionPair(IXMLDOMNode *,DOT11_MSMSEC_CONNECTION_PROFILE *,ulong *)

- ea: `0x1800461b0`
- end: `0x180046487`
- name: `?XwpParseAuthEncryptionPair@@YAKPEAUIXMLDOMNode@@PEAUDOT11_MSMSEC_CONNECTION_PROFILE@@PEAK@Z`
- size: `727`
- prototype: `unsigned int __fastcall(struct IXMLDOMNode *, struct DOT11_MSMSEC_CONNECTION_PROFILE *, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180046c64`

## callees

- `0x180009654`
- `0x18000dea8`
- `0x18000f7a8`
- `0x18000fb68`
- `0x18000fc48`
- `0x180019370`
- `0x180044e30`
- `0x1800452d8`
- `0x1800461b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004623f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004623f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800462f5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180046340`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800462f5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180046340`
- `OLEAUT32!__imp_VariantInit` at `0x1800461fc`
- `OLEAUT32!__imp_VariantInit` at `0x1800461fc`
- `OLEAUT32!__imp_VariantClear` at `0x18004645a`
- `OLEAUT32!__imp_VariantClear` at `0x18004645a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall XwpParseAuthEncryptionPair(
        struct IXMLDOMNode *a1,
        struct DOT11_MSMSEC_CONNECTION_PROFILE *a2,
        unsigned int *a3)
{
  unsigned int SingleNode; // eax
  unsigned int LastError; // ebx
  struct DOT11_AUTH_CIPHER_PAIR *v7; // rsi
  unsigned int v8; // r9d
  unsigned int v9; // eax
  unsigned int i; // r14d
  unsigned int v11; // r9d
  int v12; // ecx
  unsigned int v13; // r14d
  unsigned int v15; // [rsp+40h] [rbp-40h] BYREF
  int v16; // [rsp+44h] [rbp-3Ch] BYREF
  unsigned int v17; // [rsp+48h] [rbp-38h] BYREF
  int v18; // [rsp+4Ch] [rbp-34h] BYREF
  unsigned int v19; // [rsp+50h] [rbp-30h] BYREF
  struct IXMLDOMNode *v20; // [rsp+58h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-20h] BYREF
  enum _DOT11_AUTH_ALGORITHM v22; // [rsp+D0h] [rbp+50h] BYREF
  int v23; // [rsp+D4h] [rbp+54h]
  unsigned int v24; // [rsp+D8h] [rbp+58h] BYREF

  v23 = HIDWORD(a3);
  v24 = 0;
  v20 = 0;
  v17 = 0;
  v19 = 0;
  v16 = 0;
  v18 = 0;
  v15 = 0;
  v22 = 0;
  VariantInit(&pvarg);
  SingleNode = XcGetSingleNode(a1, L"WLANProfile:authEncryption", &v20);
  LastError = SingleNode;
  if ( SingleNode == 1168 )
  {
    LastError = 0;
    goto LABEL_28;
  }
  if ( SingleNode )
    goto LABEL_28;
  v7 = (struct DOT11_AUTH_CIPHER_PAIR *)Xc_Process_user_allocate(0x50u);
  if ( !v7 )
  {
    LastError = GetLastError();
    goto LABEL_28;
  }
  LastError = XcGetNodeEnumValue(
                v20,
                L"WLANProfile:authentication",
                (const struct _XC_STRING_VALUE_MAPPING *)&off_18006A900,
                0xBu,
                (unsigned int *)&v22,
                0,
                0,
                0);
  if ( LastError )
    goto LABEL_27;
  LastError = XcGetNodeTypedValue(v20, L"WLANProfile:encryption", &pvarg);
  if ( LastError )
    goto LABEL_27;
  LastError = XcGetNodeEnumValue(
                v20,
                L"WLANProfileV4:transitionMode",
                (const struct _XC_STRING_VALUE_MAPPING *)&off_1800631E0,
                4u,
                &v15,
                1,
                0,
                0);
  if ( LastError )
    goto LABEL_27;
  if ( lstrcmpW(L"AES", pvarg.bstrVal) )
  {
    LastError = 1206;
    for ( i = 0; i < 7; ++i )
    {
      if ( !lstrcmpW((&off_18006A890)[2 * i], pvarg.bstrVal) )
      {
        v9 = AddAuthCipherPair(v22, *((enum _DOT11_CIPHER_ALGORITHM *)&off_18006A890 + 4 * i + 2), &v24, v11, v7);
        goto LABEL_16;
      }
    }
    goto LABEL_27;
  }
  v9 = XwpAddAuthCipherPairsforAesCipher(v15 != 0, v22, &v24, v8, v7);
LABEL_16:
  if ( (LastError = v9) != 0
    || (LastError = XcGetNodeEnumValue(
                      v20,
                      L"WLANProfile:useOneX",
                      (const struct _XC_STRING_VALUE_MAPPING *)&off_1800631E0,
                      4u,
                      &v17,
                      1,
                      0,
                      &v16)) != 0
    || (v16
      ? (v13 = v17)
      : v7->AuthAlgoId > (unsigned int)(DOT11_AUTH_ALGO_WPA|0x8) || (v12 = 2376, !_bittest(&v12, v7->AuthAlgoId))
      ? (v13 = 0)
      : (v13 = 1),
        (LastError = XcGetNodeEnumValue(
                       v20,
                       L"WLANProfileV2:FIPSMode",
                       (const struct _XC_STRING_VALUE_MAPPING *)&off_1800631E0,
                       4u,
                       &v19,
                       1,
                       0,
                       &v18)) != 0) )
  {
LABEL_27:
    Xc_Process_user_free(v7);
    goto LABEL_28;
  }
  *((_QWORD *)a2 + 3) = v7;
  *((_DWORD *)a2 + 4) = v24;
  *((_DWORD *)a2 + 8) = v13;
  if ( v18 )
  {
    *(_DWORD *)a2 &= ~0x1000u;
    *(_DWORD *)a2 |= (v19 & 1) << 12;
  }
LABEL_28:
  VariantClear(&pvarg);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&v20);
  return LastError;
}

```

## disassembly

```asm
0x1800461b0  mov     [rsp-38h+arg_0], rbx
0x1800461b5  mov     qword ptr [rsp-38h+arg_10], r8
0x1800461ba  push    rbp
0x1800461bb  push    rsi
0x1800461bc  push    rdi
0x1800461bd  push    r12
0x1800461bf  push    r13
0x1800461c1  push    r14
0x1800461c3  push    r15
0x1800461c5  mov     rbp, rsp
0x1800461c8  sub     rsp, 80h
0x1800461cf  mov     rdi, rdx
0x1800461d2  mov     rbx, rcx
0x1800461d5  xor     r13d, r13d
0x1800461d8  mov     [rbp+arg_18], r13d
0x1800461dc  mov     [rbp+var_28], r13
0x1800461e0  mov     [rbp+var_38], r13d
0x1800461e4  mov     [rbp+var_30], r13d
0x1800461e8  mov     [rbp+var_3C], r13d
0x1800461ec  mov     [rbp+var_34], r13d
0x1800461f0  mov     [rbp+var_40], r13d
0x1800461f4  mov     [rbp+arg_10], r13d
0x1800461f8  lea     rcx, [rbp+pvarg]; pvarg
0x1800461fc  call    cs:__imp_VariantInit
0x180046202  nop
0x180046203  lea     r8, [rbp+var_28]; struct IXMLDOMNode **
0x180046207  lea     rdx, aWlanprofileAut_1; "WLANProfile:authEncryption"
0x18004620e  mov     rcx, rbx; struct IXMLDOMNode *
0x180046211  call    ?XcGetSingleNode@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; XcGetSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x180046216  mov     ebx, eax
0x180046218  cmp     eax, 490h
0x18004621d  jnz     short loc_180046227
0x18004621f  mov     ebx, r13d
0x180046222  jmp     loc_180046456
0x180046227  test    eax, eax
0x180046229  jnz     loc_180046456
0x18004622f  lea     ecx, [rax+50h]; dwBytes
0x180046232  call    ?Xc_Process_user_allocate@@YAPEAX_K@Z; Xc_Process_user_allocate(unsigned __int64)
0x180046237  mov     rsi, rax
0x18004623a  test    rax, rax
0x18004623d  jnz     short loc_18004624C
0x18004623f  call    cs:__imp_GetLastError
0x180046245  mov     ebx, eax
0x180046247  jmp     loc_180046456
0x18004624c  mov     [rsp+80h+var_48], r13; int *
0x180046251  mov     [rsp+80h+var_50], r13d; unsigned int
0x180046256  mov     [rsp+80h+var_58], r13d; int
0x18004625b  lea     rax, [rbp+arg_10]
0x18004625f  mov     [rsp+80h+var_60], rax; unsigned int *
0x180046264  mov     r9d, 0Bh; unsigned int
0x18004626a  lea     r8, off_18006A900; struct _XC_STRING_VALUE_MAPPING *
0x180046271  lea     rdx, aWlanprofileAut; "WLANProfile:authentication"
0x180046278  mov     rcx, [rbp+var_28]; struct IXMLDOMNode *
0x18004627c  call    ?XcGetNodeEnumValue@@YAKPEAUIXMLDOMNode@@PEBGPEBU_XC_STRING_VALUE_MAPPING@@KPEAKHKPEAH@Z; XcGetNodeEnumValue(IXMLDOMNode *,ushort const *,_XC_STRING_VALUE_MAPPING const *,ulong,ulong *,int,ulong,int *)
0x180046281  mov     ebx, eax
0x180046283  test    eax, eax
0x180046285  jnz     loc_18004644D
0x18004628b  lea     r8, [rbp+pvarg]; struct tagVARIANT *
0x18004628f  lea     rdx, aWlanprofileEnc; "WLANProfile:encryption"
0x180046296  mov     rcx, [rbp+var_28]; struct IXMLDOMNode *
0x18004629a  call    ?XcGetNodeTypedValue@@YAKPEAUIXMLDOMNode@@PEBGPEAUtagVARIANT@@@Z; XcGetNodeTypedValue(IXMLDOMNode *,ushort const *,tagVARIANT *)
0x18004629f  mov     ebx, eax
0x1800462a1  test    eax, eax
0x1800462a3  jnz     loc_18004644D
0x1800462a9  mov     [rsp+80h+var_48], r13; int *
0x1800462ae  mov     [rsp+80h+var_50], r13d; unsigned int
0x1800462b3  lea     r15d, [rax+1]
0x1800462b7  mov     [rsp+80h+var_58], r15d; int
0x1800462bc  lea     rax, [rbp+var_40]
0x1800462c0  mov     [rsp+80h+var_60], rax; unsigned int *
0x1800462c5  lea     r9d, [rbx+4]; unsigned int
0x1800462c9  lea     r8, off_1800631E0; struct _XC_STRING_VALUE_MAPPING *
0x1800462d0  lea     rdx, aWlanprofilev4T; "WLANProfileV4:transitionMode"
0x1800462d7  mov     rcx, [rbp+var_28]; struct IXMLDOMNode *
0x1800462db  call    ?XcGetNodeEnumValue@@YAKPEAUIXMLDOMNode@@PEBGPEBU_XC_STRING_VALUE_MAPPING@@KPEAKHKPEAH@Z; XcGetNodeEnumValue(IXMLDOMNode *,ushort const *,_XC_STRING_VALUE_MAPPING const *,ulong,ulong *,int,ulong,int *)
0x1800462e0  mov     ebx, eax
0x1800462e2  test    eax, eax
0x1800462e4  jnz     loc_18004644D
0x1800462ea  mov     rdx, qword ptr [rbp+pvarg+8]; lpString2
0x1800462ee  lea     rcx, String1; "AES"
0x1800462f5  call    cs:__imp_lstrcmpW
0x1800462fb  test    eax, eax
0x1800462fd  jnz     short loc_180046319
0x1800462ff  cmp     [rbp+var_40], r13d
0x180046303  setnz   cl; bool
0x180046306  mov     [rsp+80h+var_60], rsi; struct DOT11_AUTH_CIPHER_PAIR *
0x18004630b  lea     r8, [rbp+arg_18]; unsigned int *
0x18004630f  mov     edx, [rbp+arg_10]; enum _DOT11_AUTH_ALGORITHM
0x180046312  call    ?XwpAddAuthCipherPairsforAesCipher@@YAK_NW4_DOT11_AUTH_ALGORITHM@@AEAKKPEAUDOT11_AUTH_CIPHER_PAIR@@@Z; XwpAddAuthCipherPairsforAesCipher(bool,_DOT11_AUTH_ALGORITHM,ulong &,ulong,DOT11_AUTH_CIPHER_PAIR *)
0x180046317  jmp     short loc_180046372
0x180046319  mov     ebx, 4B6h
0x18004631e  mov     r14d, r13d
0x180046321  lea     rax, off_18006A890; "none"
0x180046328  cmp     r14d, 7
0x18004632c  jnb     loc_18004644D
0x180046332  mov     r15d, r14d
0x180046335  add     r15, r15
0x180046338  mov     rdx, qword ptr [rbp+pvarg+8]; lpString2
0x18004633c  mov     rcx, [rax+r15*8]; lpString1
0x180046340  call    cs:__imp_lstrcmpW
0x180046346  test    eax, eax
0x180046348  jz      short loc_18004634F
0x18004634a  inc     r14d
0x18004634d  jmp     short loc_180046321
0x18004634f  mov     [rsp+80h+var_60], rsi; struct DOT11_AUTH_CIPHER_PAIR *
0x180046354  lea     r8, [rbp+arg_18]; unsigned int *
0x180046358  lea     rdx, off_18006A890; "none"
0x18004635f  mov     edx, [rdx+r15*8+8]; enum _DOT11_CIPHER_ALGORITHM
0x180046364  mov     ecx, [rbp+arg_10]; enum _DOT11_AUTH_ALGORITHM
0x180046367  call    ?AddAuthCipherPair@@YAKW4_DOT11_AUTH_ALGORITHM@@W4_DOT11_CIPHER_ALGORITHM@@AEAKKPEAUDOT11_AUTH_CIPHER_PAIR@@@Z; AddAuthCipherPair(_DOT11_AUTH_ALGORITHM,_DOT11_CIPHER_ALGORITHM,ulong &,ulong,DOT11_AUTH_CIPHER_PAIR *)
0x18004636c  mov     r15d, 1
0x180046372  mov     ebx, eax
0x180046374  test    eax, eax
0x180046376  jnz     loc_18004644D
0x18004637c  lea     rax, [rbp+var_3C]
0x180046380  mov     [rsp+80h+var_48], rax; int *
0x180046385  mov     [rsp+80h+var_50], r13d; unsigned int
0x18004638a  mov     [rsp+80h+var_58], r15d; int
0x18004638f  lea     rax, [rbp+var_38]
0x180046393  mov     [rsp+80h+var_60], rax; unsigned int *
0x180046398  lea     r9d, [rbx+4]; unsigned int
0x18004639c  lea     r8, off_1800631E0; struct _XC_STRING_VALUE_MAPPING *
0x1800463a3  lea     rdx, aWlanprofileUse; "WLANProfile:useOneX"
0x1800463aa  mov     rcx, [rbp+var_28]; struct IXMLDOMNode *
0x1800463ae  call    ?XcGetNodeEnumValue@@YAKPEAUIXMLDOMNode@@PEBGPEBU_XC_STRING_VALUE_MAPPING@@KPEAKHKPEAH@Z; XcGetNodeEnumValue(IXMLDOMNode *,ushort const *,_XC_STRING_VALUE_MAPPING const *,ulong,ulong *,int,ulong,int *)
0x1800463b3  mov     ebx, eax
0x1800463b5  test    eax, eax
0x1800463b7  jnz     loc_18004644D
0x1800463bd  cmp     [rbp+var_3C], r13d
0x1800463c1  jnz     short loc_1800463DE
0x1800463c3  mov     eax, [rsi]
0x1800463c5  cmp     eax, 0Bh
0x1800463c8  ja      short loc_1800463D9
0x1800463ca  mov     ecx, 948h
0x1800463cf  bt      ecx, eax
0x1800463d2  jnb     short loc_1800463D9
0x1800463d4  mov     r14d, r15d
0x1800463d7  jmp     short loc_1800463E2
0x1800463d9  mov     r14d, r13d
0x1800463dc  jmp     short loc_1800463E2
0x1800463de  mov     r14d, [rbp+var_38]
0x1800463e2  lea     rax, [rbp+var_34]
0x1800463e6  mov     [rsp+80h+var_48], rax; int *
0x1800463eb  mov     [rsp+80h+var_50], r13d; unsigned int
0x1800463f0  mov     [rsp+80h+var_58], r15d; int
0x1800463f5  lea     rax, [rbp+var_30]
0x1800463f9  mov     [rsp+80h+var_60], rax; unsigned int *
0x1800463fe  mov     r9d, 4; unsigned int
0x180046404  lea     r8, off_1800631E0; struct _XC_STRING_VALUE_MAPPING *
0x18004640b  lea     rdx, aWlanprofilev2F; "WLANProfileV2:FIPSMode"
0x180046412  mov     rcx, [rbp+var_28]; struct IXMLDOMNode *
0x180046416  call    ?XcGetNodeEnumValue@@YAKPEAUIXMLDOMNode@@PEBGPEBU_XC_STRING_VALUE_MAPPING@@KPEAKHKPEAH@Z; XcGetNodeEnumValue(IXMLDOMNode *,ushort const *,_XC_STRING_VALUE_MAPPING const *,ulong,ulong *,int,ulong,int *)
0x18004641b  mov     ebx, eax
0x18004641d  cmp     eax, 4B6h
0x180046422  jz      short loc_18004644D
0x180046424  test    eax, eax
0x180046426  jnz     short loc_18004644D
0x180046428  mov     [rdi+18h], rsi
0x18004642c  mov     eax, [rbp+arg_18]
0x18004642f  mov     [rdi+10h], eax
0x180046432  mov     [rdi+20h], r14d
0x180046436  cmp     [rbp+var_34], r13d
0x18004643a  jz      short loc_180046456
0x18004643c  btr     dword ptr [rdi], 0Ch
0x180046440  mov     eax, [rbp+var_30]
0x180046443  and     eax, r15d
0x180046446  shl     eax, 0Ch
0x180046449  or      [rdi], eax
0x18004644b  jmp     short loc_180046456
0x18004644d  mov     rcx, rsi; lpMem
0x180046450  call    ?Xc_Process_user_free@@YAXPEAX@Z; Xc_Process_user_free(void *)
0x180046455  nop
0x180046456  lea     rcx, [rbp+pvarg]; pvarg
0x18004645a  call    cs:__imp_VariantClear
0x180046460  nop
0x180046461  lea     rcx, [rbp+var_28]
0x180046465  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18004646a  mov     eax, ebx
0x18004646c  mov     rbx, [rsp+80h+arg_0]
0x180046474  add     rsp, 80h
0x18004647b  pop     r15
0x18004647d  pop     r14
0x18004647f  pop     r13
0x180046481  pop     r12
0x180046483  pop     rdi
0x180046484  pop     rsi
0x180046485  pop     rbp
0x180046486  retn
```
