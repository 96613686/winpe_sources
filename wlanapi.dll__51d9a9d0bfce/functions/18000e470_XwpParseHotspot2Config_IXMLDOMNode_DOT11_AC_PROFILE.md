# XwpParseHotspot2Config(IXMLDOMNode *,_DOT11_AC_PROFILE *)

- ea: `0x18000e470`
- end: `0x18000e9da`
- name: `?XwpParseHotspot2Config@@YAKPEAUIXMLDOMNode@@PEAU_DOT11_AC_PROFILE@@@Z`
- size: `1386`
- prototype: `unsigned int __fastcall(struct IXMLDOMNode *, struct _DOT11_AC_PROFILE *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000dafc`

## callees

- `0x180009654`
- `0x18000dea8`
- `0x18000e470`
- `0x18000fc48`
- `0x18000fd24`
- `0x18000fe30`
- `0x180011bf8`
- `0x180019370`
- `0x18001a598`
- `0x180044cd4`
- `0x18004e964`
- `0x18004ed20`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e523`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e5c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e6e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e832`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e523`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e5c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e6e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e832`
- `OLEAUT32!__imp_VariantInit` at `0x18000e4c2`
- `OLEAUT32!__imp_VariantInit` at `0x18000e5ec`
- `OLEAUT32!__imp_VariantInit` at `0x18000e70e`
- `OLEAUT32!__imp_VariantInit` at `0x18000e916`
- `OLEAUT32!__imp_VariantInit` at `0x18000e4c2`
- `OLEAUT32!__imp_VariantInit` at `0x18000e5ec`
- `OLEAUT32!__imp_VariantInit` at `0x18000e70e`
- `OLEAUT32!__imp_VariantInit` at `0x18000e916`
- `OLEAUT32!__imp_VariantClear` at `0x18000e544`
- `OLEAUT32!__imp_VariantClear` at `0x18000e652`
- `OLEAUT32!__imp_VariantClear` at `0x18000e65d`
- `OLEAUT32!__imp_VariantClear` at `0x18000e79d`
- `OLEAUT32!__imp_VariantClear` at `0x18000e7a8`
- `OLEAUT32!__imp_VariantClear` at `0x18000e843`
- `OLEAUT32!__imp_VariantClear` at `0x18000e9c2`
- `OLEAUT32!__imp_VariantClear` at `0x18000e544`
- `OLEAUT32!__imp_VariantClear` at `0x18000e652`
- `OLEAUT32!__imp_VariantClear` at `0x18000e65d`
- `OLEAUT32!__imp_VariantClear` at `0x18000e79d`
- `OLEAUT32!__imp_VariantClear` at `0x18000e7a8`
- `OLEAUT32!__imp_VariantClear` at `0x18000e843`
- `OLEAUT32!__imp_VariantClear` at `0x18000e9c2`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall XwpParseHotspot2Config(struct IXMLDOMNode *a1, struct _DOT11_AC_PROFILE *a2)
{
  struct IXMLDOMNodeList *i; // rbx
  struct IXMLDOMNodeList *j; // rsi
  struct IXMLDOMNodeList *k; // rdi
  DWORD FirstNode; // r14d
  void *v8; // rax
  int v9; // eax
  int v10; // r12d
  int *v11; // rcx
  int v12; // r14d
  __int64 v13; // r8
  __int64 v14; // rdx
  int v15; // eax
  int v16; // r12d
  int *v17; // rcx
  int v18; // r14d
  __int64 v19; // r8
  __int64 v20; // rdx
  int v21; // eax
  int v22; // r13d
  int *v23; // rcx
  int v25; // r12d
  unsigned int v26; // ecx
  struct IXMLDOMNode *v27; // [rsp+20h] [rbp-79h] BYREF
  int v28[2]; // [rsp+28h] [rbp-71h] BYREF
  VARIANTARG v29; // [rsp+30h] [rbp-69h] BYREF
  struct IXMLDOMNodeList *v30; // [rsp+48h] [rbp-51h] BYREF
  struct IXMLDOMNodeList *v31; // [rsp+50h] [rbp-49h] BYREF
  struct IXMLDOMNodeList *v32; // [rsp+58h] [rbp-41h] BYREF
  struct IXMLDOMNode *v33; // [rsp+60h] [rbp-39h] BYREF
  struct IXMLDOMNode *v34; // [rsp+68h] [rbp-31h] BYREF
  struct IXMLDOMNode *v35; // [rsp+70h] [rbp-29h] BYREF
  VARIANTARG pvarg; // [rsp+78h] [rbp-21h] BYREF
  __int64 v37; // [rsp+90h] [rbp-9h]
  struct tagVARIANT v38; // [rsp+A0h] [rbp+7h] BYREF
  rsize_t SourceSize; // [rsp+110h] [rbp+77h] BYREF
  void *Source; // [rsp+118h] [rbp+7Fh] BYREF

  v27 = 0;
  v37 = 0;
  v35 = 0;
  v34 = 0;
  v33 = 0;
  i = 0;
  v30 = 0;
  j = 0;
  v31 = 0;
  k = 0;
  v32 = 0;
  VariantInit(&pvarg);
  LODWORD(SourceSize) = 0;
  LODWORD(Source) = 0;
  v28[0] = 0;
  FirstNode = XcGetFirstNode(a1, L"WLANProfile:Hotspot2", &v27);
  if ( !FirstNode )
  {
    FirstNode = XcGetNodeTypedValue(v27, L"WLANProfile:DomainName", &pvarg);
    if ( !FirstNode )
    {
      v8 = Xc_Process_user_allocate(0x20u);
      *((_QWORD *)a2 + 7) = v8;
      if ( !v8 )
      {
        FirstNode = GetLastError();
        goto LABEL_42;
      }
      FirstNode = WcDuplicateString(pvarg.bstrVal);
      VariantClear(&pvarg);
      if ( !FirstNode )
      {
        if ( !XcGetFirstNode(v27, L"WLANProfile:NAIRealm", &v35) )
        {
          if ( XcGetNodes(v35, L"WLANProfile:name", &v30, (int *)&SourceSize) )
          {
            i = v30;
          }
          else
          {
            v9 = 1;
            v10 = SourceSize;
            if ( (int)SourceSize > 0 )
              v9 = SourceSize;
            *(_QWORD *)(*((_QWORD *)a2 + 7) + 24LL) = Xc_Process_user_allocate(((__int64)v9 << 9) + 8);
            v11 = *(int **)(*((_QWORD *)a2 + 7) + 24LL);
            if ( !v11 )
            {
              FirstNode = GetLastError();
              i = v30;
              goto LABEL_42;
            }
            *v11 = v10;
            v12 = 0;
            for ( i = v30; v12 < v10; ++v12 )
            {
              VariantInit(&v29);
              if ( !XcGetItemNodeTypedValue(i, v12, &v29) )
              {
                v13 = -1;
                do
                  ++v13;
                while ( *(_WORD *)(v29.llVal + 2 * v13) );
                v14 = (__int64)v12 << 9;
                *(_WORD *)(*(_QWORD *)(*((_QWORD *)a2 + 7) + 24LL) + v14 + 8) = v13;
                o_wmemcpy_s_0(
                  (wchar_t *)(v14 + *(_QWORD *)(*((_QWORD *)a2 + 7) + 24LL) + 10LL),
                  0xFEu,
                  v29.bstrVal,
                  (unsigned __int16)v13);
              }
              VariantClear(&v29);
              VariantClear(&v29);
            }
          }
        }
        if ( !XcGetFirstNode(v27, L"WLANProfile:Network3GPP", &v34) )
        {
          if ( XcGetNodes(v34, L"WLANProfile:PLMNID", &v31, (int *)&Source) )
          {
            j = v31;
          }
          else
          {
            v15 = 1;
            v16 = (int)Source;
            if ( (int)Source > 0 )
              v15 = (int)Source;
            *(_QWORD *)(*((_QWORD *)a2 + 7) + 16LL) = Xc_Process_user_allocate(14LL * v15 + 8);
            v17 = *(int **)(*((_QWORD *)a2 + 7) + 16LL);
            if ( !v17 )
            {
              FirstNode = GetLastError();
              j = v31;
              goto LABEL_42;
            }
            *v17 = v16;
            v18 = 0;
            for ( j = v31; v18 < v16; ++v18 )
            {
              VariantInit(&v29);
              if ( !XcGetItemNodeTypedValue(j, v18, &v29) )
              {
                v19 = -1;
                do
                  ++v19;
                while ( *(_WORD *)(v29.llVal + 2 * v19) );
                v20 = 14LL * v18;
                *(_WORD *)(*(_QWORD *)(*((_QWORD *)a2 + 7) + 16LL) + v20 + 8) = v19;
                SourceSize = (unsigned __int16)v19;
                if ( !o_wmemcpy_s_0(
                        (wchar_t *)(v20 + *(_QWORD *)(*((_QWORD *)a2 + 7) + 16LL) + 10LL),
                        5u,
                        v29.bstrVal,
                        (unsigned __int16)v19) )
                  *(_WORD *)(*(_QWORD *)(*((_QWORD *)a2 + 7) + 16LL) + 2 * (SourceSize + 7LL * v18) + 10) = 0;
              }
              VariantClear(&v29);
              VariantClear(&v29);
            }
          }
        }
        FirstNode = XcGetFirstNode(v27, L"WLANProfile:RoamingConsortium", &v33);
        if ( !FirstNode )
        {
          FirstNode = XcGetNodes(v33, L"WLANProfile:OUI", &v32, v28);
          if ( FirstNode )
          {
LABEL_41:
            k = v32;
            goto LABEL_42;
          }
          v21 = 1;
          v22 = v28[0];
          if ( v28[0] > 0 )
            v21 = v28[0];
          *(_QWORD *)(*((_QWORD *)a2 + 7) + 8LL) = Xc_Process_user_allocate(8LL * v21 + 8);
          v23 = *(int **)(*((_QWORD *)a2 + 7) + 8LL);
          if ( !v23 )
          {
            FirstNode = GetLastError();
            goto LABEL_41;
          }
          *v23 = v22;
          v25 = 0;
          for ( k = v32; v25 < v22; ++v25 )
          {
            VariantInit(&v29);
            *(_QWORD *)v28 = 0;
            Source = 0;
            LODWORD(SourceSize) = 0;
            FirstNode = XcGetItemNodeTypedValue(k, v25, &v29);
            if ( !FirstNode )
            {
              v38 = v29;
              FirstNode = XcGetVarHexBinaryValue(&v38, (unsigned __int8 **)&Source, (unsigned int *)&SourceSize);
              if ( !FirstNode )
              {
                v26 = SourceSize;
                if ( (unsigned int)SourceSize <= 5 )
                {
                  *(_WORD *)(*(_QWORD *)(*((_QWORD *)a2 + 7) + 8LL) + 8LL * v25 + 8) = SourceSize;
                  memcpy_s_0(
                    (void *const)(*(_QWORD *)(*((_QWORD *)a2 + 7) + 8LL) + 10LL + 8LL * v25),
                    FirstNode + 5,
                    Source,
                    v26);
                }
              }
              if ( Source )
                Xc_Process_user_free(Source);
            }
            ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)v28);
            VariantClear(&v29);
          }
        }
      }
    }
  }
LABEL_42:
  VariantClear(&pvarg);
  if ( k )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))k->lpVtbl->Release)(k);
  if ( j )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))j->lpVtbl->Release)(j);
  if ( i )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))i->lpVtbl->Release)(i);
  if ( v33 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v33->lpVtbl->Release)(v33);
  if ( v34 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v34->lpVtbl->Release)(v34);
  if ( v35 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v35->lpVtbl->Release)(v35);
  if ( v27 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v27->lpVtbl->Release)(v27);
  return FirstNode;
}

```

## disassembly

```asm
0x18000e470  mov     [rsp-8+arg_0], rbx
0x18000e475  push    rbp
0x18000e476  push    rsi
0x18000e477  push    rdi
0x18000e478  push    r12
0x18000e47a  push    r13
0x18000e47c  push    r14
0x18000e47e  push    r15
0x18000e480  lea     rbp, [rsp-27h]
0x18000e485  sub     rsp, 0C0h
0x18000e48c  mov     r15, rdx
0x18000e48f  mov     r14, rcx
0x18000e492  xor     r13d, r13d
0x18000e495  mov     [rbp+57h+var_D0], r13
0x18000e499  mov     [rbp+57h+var_60], r13
0x18000e49d  mov     [rbp+57h+var_80], r13
0x18000e4a1  mov     [rbp+57h+var_88], r13
0x18000e4a5  mov     [rbp+57h+var_90], r13
0x18000e4a9  mov     ebx, r13d
0x18000e4ac  mov     [rbp+57h+var_A8], rbx
0x18000e4b0  mov     esi, r13d
0x18000e4b3  mov     [rbp+57h+var_A0], r13
0x18000e4b7  mov     edi, r13d
0x18000e4ba  mov     [rbp+57h+var_98], r13
0x18000e4be  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18000e4c2  call    cs:__imp_VariantInit
0x18000e4c8  nop
0x18000e4c9  mov     dword ptr [rbp+57h+SourceSize], r13d
0x18000e4cd  mov     dword ptr [rbp+57h+Source], r13d
0x18000e4d1  mov     [rbp+57h+var_C8], r13d
0x18000e4d5  lea     r8, [rbp+57h+var_D0]; struct IXMLDOMNode **
0x18000e4d9  lea     rdx, aWlanprofileHot; "WLANProfile:Hotspot2"
0x18000e4e0  mov     rcx, r14; struct IXMLDOMNode *
0x18000e4e3  call    ?XcGetFirstNode@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; XcGetFirstNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18000e4e8  mov     r14d, eax
0x18000e4eb  test    eax, eax
0x18000e4ed  jnz     loc_18000E83F
0x18000e4f3  lea     r8, [rbp+57h+pvarg]; struct tagVARIANT *
0x18000e4f7  lea     rdx, aWlanprofileDom; "WLANProfile:DomainName"
0x18000e4fe  mov     rcx, [rbp+57h+var_D0]; struct IXMLDOMNode *
0x18000e502  call    ?XcGetNodeTypedValue@@YAKPEAUIXMLDOMNode@@PEBGPEAUtagVARIANT@@@Z; XcGetNodeTypedValue(IXMLDOMNode *,ushort const *,tagVARIANT *)
0x18000e507  mov     r14d, eax
0x18000e50a  test    eax, eax
0x18000e50c  jnz     loc_18000E83F
0x18000e512  lea     ecx, [rax+20h]; dwBytes
0x18000e515  call    ?Xc_Process_user_allocate@@YAPEAX_K@Z; Xc_Process_user_allocate(unsigned __int64)
0x18000e51a  mov     [r15+38h], rax
0x18000e51e  test    rax, rax
0x18000e521  jnz     short loc_18000E531
0x18000e523  call    cs:__imp_GetLastError
0x18000e529  mov     r14d, eax
0x18000e52c  jmp     loc_18000E83F
0x18000e531  mov     rdx, rax
0x18000e534  mov     rcx, qword ptr [rbp+57h+pvarg+8]; Src
0x18000e538  call    WcDuplicateString
0x18000e53d  mov     r14d, eax
0x18000e540  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18000e544  call    cs:__imp_VariantClear
0x18000e54a  test    r14d, r14d
0x18000e54d  jnz     loc_18000E83F
0x18000e553  lea     r8, [rbp+57h+var_80]; struct IXMLDOMNode **
0x18000e557  lea     rdx, aWlanprofileNai; "WLANProfile:NAIRealm"
0x18000e55e  mov     rcx, [rbp+57h+var_D0]; struct IXMLDOMNode *
0x18000e562  call    ?XcGetFirstNode@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; XcGetFirstNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18000e567  test    eax, eax
0x18000e569  jnz     loc_18000E675
0x18000e56f  lea     r9, [rbp+57h+SourceSize]; int *
0x18000e573  lea     r8, [rbp+57h+var_A8]; struct IXMLDOMNodeList **
0x18000e577  lea     rdx, aWlanprofileNam; "WLANProfile:name"
0x18000e57e  mov     rcx, [rbp+57h+var_80]; struct IXMLDOMNode *
0x18000e582  call    ?XcGetNodes@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAUIXMLDOMNodeList@@PEAJ@Z; XcGetNodes(IXMLDOMNode *,ushort const *,IXMLDOMNodeList * *,long *)
0x18000e587  test    eax, eax
0x18000e589  jnz     loc_18000E671
0x18000e58f  lea     eax, [r14+1]
0x18000e593  mov     r12d, dword ptr [rbp+57h+SourceSize]
0x18000e597  test    r12d, r12d
0x18000e59a  cmovg   eax, r12d
0x18000e59e  movsxd  rcx, eax
0x18000e5a1  shl     rcx, 9
0x18000e5a5  add     rcx, 8; dwBytes
0x18000e5a9  call    ?Xc_Process_user_allocate@@YAPEAX_K@Z; Xc_Process_user_allocate(unsigned __int64)
0x18000e5ae  mov     rcx, [r15+38h]
0x18000e5b2  mov     [rcx+18h], rax
0x18000e5b6  mov     rax, [r15+38h]
0x18000e5ba  mov     rcx, [rax+18h]
0x18000e5be  test    rcx, rcx
0x18000e5c1  jnz     short loc_18000E5D5
0x18000e5c3  call    cs:__imp_GetLastError
0x18000e5c9  mov     r14d, eax
0x18000e5cc  mov     rbx, [rbp+57h+var_A8]
0x18000e5d0  jmp     loc_18000E83F
0x18000e5d5  mov     [rcx], r12d
0x18000e5d8  mov     r14d, r13d
0x18000e5db  mov     rbx, [rbp+57h+var_A8]
0x18000e5df  test    r12d, r12d
0x18000e5e2  jle     loc_18000E675
0x18000e5e8  lea     rcx, [rbp+57h+var_C0]; pvarg
0x18000e5ec  call    cs:__imp_VariantInit
0x18000e5f2  nop
0x18000e5f3  lea     r8, [rbp+57h+var_C0]; struct tagVARIANT *
0x18000e5f7  mov     edx, r14d; int
0x18000e5fa  mov     rcx, rbx; struct IXMLDOMNodeList *
0x18000e5fd  call    ?XcGetItemNodeTypedValue@@YAKPEAUIXMLDOMNodeList@@JPEAUtagVARIANT@@@Z; XcGetItemNodeTypedValue(IXMLDOMNodeList *,long,tagVARIANT *)
0x18000e602  test    eax, eax
0x18000e604  jnz     short loc_18000E64E
0x18000e606  mov     rax, qword ptr [rbp+57h+var_C0+8]
0x18000e60a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000e60e  inc     r8
0x18000e611  cmp     [rax+r8*2], r13w
0x18000e616  jnz     short loc_18000E60E
0x18000e618  movsxd  rdx, r14d
0x18000e61b  shl     rdx, 9
0x18000e61f  mov     rax, [r15+38h]
0x18000e623  mov     rcx, [rax+18h]
0x18000e627  mov     [rcx+rdx+8], r8w
0x18000e62d  movzx   r9d, r8w; N
0x18000e631  mov     rax, [r15+38h]
0x18000e635  mov     rcx, [rax+18h]
0x18000e639  add     rcx, 0Ah
0x18000e63d  add     rcx, rdx; S1
0x18000e640  mov     r8, qword ptr [rbp+57h+var_C0+8]; S2
0x18000e644  mov     edx, 0FEh; N1
0x18000e649  call    _o_wmemcpy_s_0
0x18000e64e  lea     rcx, [rbp+57h+var_C0]; pvarg
0x18000e652  call    cs:__imp_VariantClear
0x18000e658  nop
0x18000e659  lea     rcx, [rbp+57h+var_C0]; pvarg
0x18000e65d  call    cs:__imp_VariantClear
0x18000e663  inc     r14d
0x18000e666  cmp     r14d, r12d
0x18000e669  jl      loc_18000E5E8
0x18000e66f  jmp     short loc_18000E675
0x18000e671  mov     rbx, [rbp+57h+var_A8]
0x18000e675  lea     r8, [rbp+57h+var_88]; struct IXMLDOMNode **
0x18000e679  lea     rdx, aWlanprofileNet; "WLANProfile:Network3GPP"
0x18000e680  mov     rcx, [rbp+57h+var_D0]; struct IXMLDOMNode *
0x18000e684  call    ?XcGetFirstNode@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; XcGetFirstNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18000e689  test    eax, eax
0x18000e68b  jnz     loc_18000E7C0
0x18000e691  lea     r9, [rbp+57h+Source]; int *
0x18000e695  lea     r8, [rbp+57h+var_A0]; struct IXMLDOMNodeList **
0x18000e699  lea     rdx, aWlanprofilePlm; "WLANProfile:PLMNID"
0x18000e6a0  mov     rcx, [rbp+57h+var_88]; struct IXMLDOMNode *
0x18000e6a4  call    ?XcGetNodes@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAUIXMLDOMNodeList@@PEAJ@Z; XcGetNodes(IXMLDOMNode *,ushort const *,IXMLDOMNodeList * *,long *)
0x18000e6a9  test    eax, eax
0x18000e6ab  jnz     loc_18000E7BC
0x18000e6b1  mov     eax, 1
0x18000e6b6  mov     r12d, dword ptr [rbp+57h+Source]
0x18000e6ba  test    r12d, r12d
0x18000e6bd  cmovg   eax, r12d
0x18000e6c1  cdqe
0x18000e6c3  imul    rcx, rax, 0Eh
0x18000e6c7  add     rcx, 8; dwBytes
0x18000e6cb  call    ?Xc_Process_user_allocate@@YAPEAX_K@Z; Xc_Process_user_allocate(unsigned __int64)
0x18000e6d0  mov     rcx, [r15+38h]
0x18000e6d4  mov     [rcx+10h], rax
0x18000e6d8  mov     rax, [r15+38h]
0x18000e6dc  mov     rcx, [rax+10h]
0x18000e6e0  test    rcx, rcx
0x18000e6e3  jnz     short loc_18000E6F7
0x18000e6e5  call    cs:__imp_GetLastError
0x18000e6eb  mov     r14d, eax
0x18000e6ee  mov     rsi, [rbp+57h+var_A0]
0x18000e6f2  jmp     loc_18000E83F
0x18000e6f7  mov     [rcx], r12d
0x18000e6fa  mov     r14d, r13d
0x18000e6fd  mov     rsi, [rbp+57h+var_A0]
0x18000e701  test    r12d, r12d
0x18000e704  jle     loc_18000E7C0
0x18000e70a  lea     rcx, [rbp+57h+var_C0]; pvarg
0x18000e70e  call    cs:__imp_VariantInit
0x18000e714  nop
0x18000e715  lea     r8, [rbp+57h+var_C0]; struct tagVARIANT *
0x18000e719  mov     edx, r14d; int
0x18000e71c  mov     rcx, rsi; struct IXMLDOMNodeList *
0x18000e71f  call    ?XcGetItemNodeTypedValue@@YAKPEAUIXMLDOMNodeList@@JPEAUtagVARIANT@@@Z; XcGetItemNodeTypedValue(IXMLDOMNodeList *,long,tagVARIANT *)
0x18000e724  test    eax, eax
0x18000e726  jnz     short loc_18000E799
0x18000e728  mov     rax, qword ptr [rbp+57h+var_C0+8]
0x18000e72c  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000e730  inc     r8
0x18000e733  cmp     [rax+r8*2], r13w
0x18000e738  jnz     short loc_18000E730
0x18000e73a  movsxd  r13, r14d
0x18000e73d  imul    rdx, r13, 0Eh
0x18000e741  mov     rax, [r15+38h]
0x18000e745  mov     rcx, [rax+10h]
0x18000e749  mov     [rcx+rdx+8], r8w
0x18000e74f  movzx   r8d, r8w
0x18000e753  mov     [rbp+57h+SourceSize], r8
0x18000e757  mov     rax, [r15+38h]
0x18000e75b  mov     rcx, [rax+10h]
0x18000e75f  add     rcx, 0Ah
0x18000e763  add     rcx, rdx; S1
0x18000e766  mov     r9d, r8d; N
0x18000e769  mov     r8, qword ptr [rbp+57h+var_C0+8]; S2
0x18000e76d  mov     edx, 5; N1
0x18000e772  call    _o_wmemcpy_s_0
0x18000e777  test    eax, eax
0x18000e779  jnz     short loc_18000E796
0x18000e77b  imul    rdx, r13, 7
0x18000e77f  add     rdx, [rbp+57h+SourceSize]
0x18000e783  mov     rax, [r15+38h]
0x18000e787  mov     rcx, [rax+10h]
0x18000e78b  xor     r13d, r13d
0x18000e78e  mov     [rcx+rdx*2+0Ah], r13w
0x18000e794  jmp     short loc_18000E799
0x18000e796  xor     r13d, r13d
0x18000e799  lea     rcx, [rbp+57h+var_C0]; pvarg
0x18000e79d  call    cs:__imp_VariantClear
0x18000e7a3  nop
0x18000e7a4  lea     rcx, [rbp+57h+var_C0]; pvarg
0x18000e7a8  call    cs:__imp_VariantClear
0x18000e7ae  inc     r14d
0x18000e7b1  cmp     r14d, r12d
0x18000e7b4  jl      loc_18000E70A
0x18000e7ba  jmp     short loc_18000E7C0
0x18000e7bc  mov     rsi, [rbp+57h+var_A0]
0x18000e7c0  lea     r8, [rbp+57h+var_90]; struct IXMLDOMNode **
0x18000e7c4  lea     rdx, aWlanprofileRoa; "WLANProfile:RoamingConsortium"
0x18000e7cb  mov     rcx, [rbp+57h+var_D0]; struct IXMLDOMNode *
0x18000e7cf  call    ?XcGetFirstNode@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; XcGetFirstNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18000e7d4  mov     r14d, eax
0x18000e7d7  test    eax, eax
0x18000e7d9  jnz     short loc_18000E83F
0x18000e7db  lea     r9, [rbp+57h+var_C8]; int *
0x18000e7df  lea     r8, [rbp+57h+var_98]; struct IXMLDOMNodeList **
0x18000e7e3  lea     rdx, aWlanprofileOui; "WLANProfile:OUI"
0x18000e7ea  mov     rcx, [rbp+57h+var_90]; struct IXMLDOMNode *
0x18000e7ee  call    ?XcGetNodes@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAUIXMLDOMNodeList@@PEAJ@Z; XcGetNodes(IXMLDOMNode *,ushort const *,IXMLDOMNodeList * *,long *)
0x18000e7f3  mov     r14d, eax
0x18000e7f6  test    eax, eax
0x18000e7f8  jnz     short loc_18000E83B
0x18000e7fa  lea     eax, [r14+1]
0x18000e7fe  mov     r13d, [rbp+57h+var_C8]
0x18000e802  test    r13d, r13d
0x18000e805  cmovg   eax, r13d
0x18000e809  movsxd  rcx, eax
0x18000e80c  lea     rcx, ds:8[rcx*8]; dwBytes
0x18000e814  call    ?Xc_Process_user_allocate@@YAPEAX_K@Z; Xc_Process_user_allocate(unsigned __int64)
0x18000e819  mov     rcx, [r15+38h]
0x18000e81d  mov     [rcx+8], rax
0x18000e821  mov     rax, [r15+38h]
0x18000e825  mov     rcx, [rax+8]
0x18000e829  test    rcx, rcx
0x18000e82c  jnz     loc_18000E8FF
0x18000e832  call    cs:__imp_GetLastError
0x18000e838  mov     r14d, eax
0x18000e83b  mov     rdi, [rbp+57h+var_98]
0x18000e83f  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18000e843  call    cs:__imp_VariantClear
0x18000e849  nop
0x18000e84a  test    rdi, rdi
0x18000e84d  jz      short loc_18000E85F
0x18000e84f  mov     rax, [rdi]
0x18000e852  mov     rcx, rdi
0x18000e855  mov     rax, [rax+10h]
0x18000e859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e85e  nop
0x18000e85f  test    rsi, rsi
0x18000e862  jz      short loc_18000E874
0x18000e864  mov     rax, [rsi]
0x18000e867  mov     rcx, rsi
0x18000e86a  mov     rax, [rax+10h]
0x18000e86e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e873  nop
0x18000e874  test    rbx, rbx
0x18000e877  jz      short loc_18000E889
0x18000e879  mov     rax, [rbx]
0x18000e87c  mov     rcx, rbx
0x18000e87f  mov     rax, [rax+10h]
0x18000e883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e888  nop
0x18000e889  mov     rcx, [rbp+57h+var_90]
0x18000e88d  test    rcx, rcx
0x18000e890  jz      short loc_18000E89F
0x18000e892  mov     rax, [rcx]
0x18000e895  mov     rax, [rax+10h]
0x18000e899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e89e  nop
0x18000e89f  mov     rcx, [rbp+57h+var_88]
0x18000e8a3  test    rcx, rcx
0x18000e8a6  jz      short loc_18000E8B5
0x18000e8a8  mov     rax, [rcx]
0x18000e8ab  mov     rax, [rax+10h]
0x18000e8af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8b4  nop
0x18000e8b5  mov     rcx, [rbp+57h+var_80]
0x18000e8b9  test    rcx, rcx
0x18000e8bc  jz      short loc_18000E8CB
0x18000e8be  mov     rax, [rcx]
0x18000e8c1  mov     rax, [rax+10h]
0x18000e8c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8ca  nop
0x18000e8cb  mov     rcx, [rbp+57h+var_D0]
0x18000e8cf  test    rcx, rcx
0x18000e8d2  jz      short loc_18000E8E1
0x18000e8d4  mov     rax, [rcx]
0x18000e8d7  mov     rax, [rax+10h]
0x18000e8db  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
