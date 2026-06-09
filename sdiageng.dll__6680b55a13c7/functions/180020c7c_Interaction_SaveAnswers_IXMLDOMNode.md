# Interaction::SaveAnswers(IXMLDOMNode *)

- ea: `0x180020c7c`
- end: `0x180020f0e`
- name: `?SaveAnswers@Interaction@@IEAAJPEAUIXMLDOMNode@@@Z`
- size: `658`
- prototype: `__int64 __fastcall(Interaction *__hidden this, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180020648`

## callees

- `0x180020c7c`
- `0x180026fa0`
- `0x180028038`
- `0x1800286a4`
- `0x1800290bc`
- `0x18002a010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180020ef8`
- `OLEAUT32!__imp_SysFreeString` at `0x180020ef8`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180020ec1`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180020ec1`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180020d40`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180020d40`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180020eab`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180020eab`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180020d1b`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180020d1b`

## pseudocode

```c
__int64 __fastcall Interaction::SaveAnswers(Interaction *this, struct IXMLDOMNode *a2)
{
  struct IXMLDOMNode *v2; // rsi
  struct IXMLDOMNodeList *v3; // r15
  SAFEARRAY *v4; // r14
  unsigned int v5; // ebx
  int v6; // r8d
  int v7; // r9d
  HRESULT ChildNodes; // eax
  int v9; // r8d
  int v10; // r9d
  SAFEARRAY *Vector; // rax
  __int64 v12; // r12
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  struct IXMLDOMNode *v19; // [rsp+20h] [rbp-28h] BYREF
  void *ppvData; // [rsp+28h] [rbp-20h] BYREF
  BSTR bstrString[3]; // [rsp+30h] [rbp-18h] BYREF
  ULONG cElements; // [rsp+88h] [rbp+40h] BYREF
  int v24; // [rsp+90h] [rbp+48h] BYREF
  struct IXMLDOMNodeList *v25; // [rsp+98h] [rbp+50h] BYREF

  v2 = 0;
  v3 = 0;
  v4 = 0;
  v25 = 0;
  v19 = 0;
  bstrString[0] = 0;
  ppvData = 0;
  cElements = 0;
  v24 = 0;
  if ( !a2 )
  {
    v5 = -2147024809;
    v6 = 976;
    v7 = -2147024809;
LABEL_3:
    SdpDebugTrace(1u, L"Interaction::SaveAnswers", v6, v7);
    goto LABEL_32;
  }
  ChildNodes = SdpXmlGetChildNodes(0, a2, &v25, &cElements);
  v5 = ChildNodes;
  if ( ChildNodes < 0 )
  {
    v9 = 979;
LABEL_6:
    v10 = ChildNodes;
LABEL_7:
    SdpDebugTrace(1u, L"Interaction::SaveAnswers", v9, v10);
    v3 = v25;
    goto LABEL_32;
  }
  Vector = SafeArrayCreateVector(8u, 0, cElements);
  v4 = Vector;
  if ( !Vector )
  {
    v5 = -2147024882;
    v9 = 982;
    v10 = -2147024882;
    goto LABEL_7;
  }
  ChildNodes = SafeArrayAccessData(Vector, &ppvData);
  v5 = ChildNodes;
  if ( ChildNodes < 0 )
  {
    v9 = 985;
    goto LABEL_6;
  }
  v3 = v25;
  v12 = 0;
  if ( cElements )
  {
    while ( 1 )
    {
      if ( v2 )
      {
        ((void (__fastcall *)(struct IXMLDOMNode *))v2->lpVtbl->Release)(v2);
        v19 = 0;
      }
      v13 = SdpXmlNextNode(v3, &v19);
      v5 = v13;
      if ( v13 < 0 )
        break;
      v2 = v19;
      v14 = SdpXmlCheckNode(v19, L"Value");
      v5 = v14;
      if ( v14 < 0 )
      {
        v7 = v14;
        goto LABEL_26;
      }
      if ( v14 == 1 || !v2 )
      {
        v5 = -2147467259;
        v7 = -2147467259;
LABEL_26:
        v6 = 992;
        goto LABEL_3;
      }
      v15 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))v2->lpVtbl->get_text)(v2, bstrString);
      v5 = v15;
      if ( v15 < 0 )
      {
        v7 = v15;
        v6 = 995;
        goto LABEL_3;
      }
      *((BSTR *)ppvData + v12) = bstrString[0];
      v12 = (unsigned int)(v12 + 1);
      bstrString[0] = 0;
      if ( (unsigned int)v12 >= cElements )
        goto LABEL_21;
    }
    SdpDebugTrace(1u, L"Interaction::SaveAnswers", 991, v13);
    v2 = v19;
  }
  else
  {
LABEL_21:
    v16 = (*(__int64 (__fastcall **)(Interaction *, int *))(*(_QWORD *)this + 8LL))(this, &v24);
    v5 = v16;
    if ( v16 < 0 )
    {
      v7 = v16;
      v6 = 1003;
      goto LABEL_3;
    }
    if ( !v24 )
    {
      v17 = (*(__int64 (__fastcall **)(Interaction *, SAFEARRAY *))(*(_QWORD *)this + 48LL))(this, v4);
      v5 = v17;
      if ( v17 < 0 )
      {
        v7 = v17;
        v6 = 1007;
        goto LABEL_3;
      }
    }
    *((_QWORD *)this + 10) = v4;
    v4 = 0;
  }
LABEL_32:
  if ( ppvData )
  {
    SafeArrayUnaccessData(v4);
    ppvData = 0;
  }
  if ( v4 )
    SafeArrayDestroy(v4);
  if ( v3 )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v3->lpVtbl->Release)(v3);
  if ( v2 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v2->lpVtbl->Release)(v2);
  if ( bstrString[0] )
    SysFreeString(bstrString[0]);
  return v5;
}

```

## disassembly

```asm
0x180020c7c  mov     [rsp-30h+arg_0], rcx
0x180020c81  push    rbp
0x180020c82  push    rbx
0x180020c83  push    rsi
0x180020c84  push    r12
0x180020c86  push    r14
0x180020c88  push    r15
0x180020c8a  mov     rbp, rsp
0x180020c8d  sub     rsp, 48h
0x180020c91  xor     esi, esi
0x180020c93  xor     r15d, r15d
0x180020c96  xor     r14d, r14d
0x180020c99  mov     [rbp+arg_18], r15
0x180020c9d  mov     [rbp+var_28], rsi
0x180020ca1  mov     [rbp+bstrString], rsi
0x180020ca5  mov     [rbp+ppvData], rsi
0x180020ca9  mov     [rbp+cElements], esi
0x180020cac  mov     [rbp+arg_10], esi
0x180020caf  test    rdx, rdx
0x180020cb2  jnz     short loc_180020CD8
0x180020cb4  mov     ebx, 80070057h
0x180020cb9  mov     r8d, 3D0h; int
0x180020cbf  mov     r9d, ebx; int
0x180020cc2  lea     rdx, aInteractionSav; "Interaction::SaveAnswers"
0x180020cc9  mov     ecx, 1; Level
0x180020cce  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180020cd3  jmp     loc_180020EA1
0x180020cd8  lea     r9, [rbp+cElements]; unsigned int *
0x180020cdc  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x180020cde  lea     r8, [rbp+arg_18]; struct IXMLDOMNodeList **
0x180020ce2  call    ?SdpXmlGetChildNodes@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@PEAK@Z; SdpXmlGetChildNodes(IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *,ulong *)
0x180020ce7  mov     ebx, eax
0x180020ce9  test    eax, eax
0x180020ceb  jns     short loc_180020D10
0x180020ced  mov     r8d, 3D3h; int
0x180020cf3  mov     r9d, eax; int
0x180020cf6  lea     rdx, aInteractionSav; "Interaction::SaveAnswers"
0x180020cfd  mov     ecx, 1; Level
0x180020d02  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180020d07  mov     r15, [rbp+arg_18]
0x180020d0b  jmp     loc_180020EA1
0x180020d10  mov     r8d, [rbp+cElements]; cElements
0x180020d14  mov     ecx, 8; vt
0x180020d19  xor     edx, edx; lLbound
0x180020d1b  call    cs:__imp_SafeArrayCreateVector
0x180020d21  mov     r14, rax
0x180020d24  test    rax, rax
0x180020d27  jnz     short loc_180020D39
0x180020d29  mov     ebx, 8007000Eh
0x180020d2e  mov     r8d, 3D6h
0x180020d34  mov     r9d, ebx
0x180020d37  jmp     short loc_180020CF6
0x180020d39  lea     rdx, [rbp+ppvData]; ppvData
0x180020d3d  mov     rcx, r14; psa
0x180020d40  call    cs:__imp_SafeArrayAccessData
0x180020d46  mov     ebx, eax
0x180020d48  test    eax, eax
0x180020d4a  jns     short loc_180020D54
0x180020d4c  mov     r8d, 3D9h
0x180020d52  jmp     short loc_180020CF3
0x180020d54  mov     r15, [rbp+arg_18]
0x180020d58  xor     r12d, r12d
0x180020d5b  cmp     [rbp+cElements], esi
0x180020d5e  jbe     loc_180020DFA
0x180020d64  test    rsi, rsi
0x180020d67  jz      short loc_180020D80
0x180020d69  mov     rax, [rsi]
0x180020d6c  mov     rcx, rsi
0x180020d6f  mov     rax, [rax+10h]
0x180020d73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d78  mov     [rbp+var_28], 0
0x180020d80  lea     rdx, [rbp+var_28]; struct IXMLDOMNode **
0x180020d84  mov     rcx, r15; struct IXMLDOMNodeList *
0x180020d87  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x180020d8c  mov     ebx, eax
0x180020d8e  test    eax, eax
0x180020d90  js      loc_180020E4C
0x180020d96  mov     rsi, [rbp+var_28]
0x180020d9a  lea     rdx, aValue; "Value"
0x180020da1  mov     rcx, rsi; struct IXMLDOMNode *
0x180020da4  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x180020da9  mov     ebx, eax
0x180020dab  test    eax, eax
0x180020dad  js      loc_180020E3E
0x180020db3  cmp     eax, 1
0x180020db6  jz      short loc_180020E34
0x180020db8  test    rsi, rsi
0x180020dbb  jz      short loc_180020E34
0x180020dbd  mov     rax, [rsi]
0x180020dc0  lea     rdx, [rbp+bstrString]
0x180020dc4  mov     rcx, rsi
0x180020dc7  mov     rax, [rax+0D0h]
0x180020dce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020dd3  mov     ebx, eax
0x180020dd5  test    eax, eax
0x180020dd7  js      short loc_180020E26
0x180020dd9  mov     rax, [rbp+bstrString]
0x180020ddd  mov     rcx, [rbp+ppvData]
0x180020de1  mov     [rcx+r12*8], rax
0x180020de5  inc     r12d
0x180020de8  mov     [rbp+bstrString], 0
0x180020df0  cmp     r12d, [rbp+cElements]
0x180020df4  jb      loc_180020D64
0x180020dfa  mov     r12, [rbp+arg_0]
0x180020dfe  lea     rdx, [rbp+arg_10]
0x180020e02  mov     rcx, r12
0x180020e05  mov     rax, [r12]
0x180020e09  mov     rax, [rax+8]
0x180020e0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e12  mov     ebx, eax
0x180020e14  test    eax, eax
0x180020e16  jns     short loc_180020E6C
0x180020e18  mov     r9d, eax
0x180020e1b  mov     r8d, 3EBh
0x180020e21  jmp     loc_180020CC2
0x180020e26  mov     r9d, eax
0x180020e29  mov     r8d, 3E3h
0x180020e2f  jmp     loc_180020CC2
0x180020e34  mov     ebx, 80004005h
0x180020e39  mov     r9d, ebx
0x180020e3c  jmp     short loc_180020E41
0x180020e3e  mov     r9d, eax
0x180020e41  mov     r8d, 3E0h
0x180020e47  jmp     loc_180020CC2
0x180020e4c  mov     r9d, eax; int
0x180020e4f  lea     rdx, aInteractionSav; "Interaction::SaveAnswers"
0x180020e56  mov     r8d, 3DFh; int
0x180020e5c  mov     ecx, 1; Level
0x180020e61  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180020e66  mov     rsi, [rbp+var_28]
0x180020e6a  jmp     short loc_180020EA1
0x180020e6c  cmp     [rbp+arg_10], 0
0x180020e70  jnz     short loc_180020E99
0x180020e72  mov     rax, [r12]
0x180020e76  mov     rdx, r14
0x180020e79  mov     rcx, r12
0x180020e7c  mov     rax, [rax+30h]
0x180020e80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e85  mov     ebx, eax
0x180020e87  test    eax, eax
0x180020e89  jns     short loc_180020E99
0x180020e8b  mov     r9d, eax
0x180020e8e  mov     r8d, 3EFh
0x180020e94  jmp     loc_180020CC2
0x180020e99  mov     [r12+50h], r14
0x180020e9e  xor     r14d, r14d
0x180020ea1  cmp     [rbp+ppvData], 0
0x180020ea6  jz      short loc_180020EB9
0x180020ea8  mov     rcx, r14; psa
0x180020eab  call    cs:__imp_SafeArrayUnaccessData
0x180020eb1  mov     [rbp+ppvData], 0
0x180020eb9  test    r14, r14
0x180020ebc  jz      short loc_180020EC7
0x180020ebe  mov     rcx, r14; psa
0x180020ec1  call    cs:__imp_SafeArrayDestroy
0x180020ec7  test    r15, r15
0x180020eca  jz      short loc_180020EDB
0x180020ecc  mov     rax, [r15]
0x180020ecf  mov     rcx, r15
0x180020ed2  mov     rax, [rax+10h]
0x180020ed6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020edb  test    rsi, rsi
0x180020ede  jz      short loc_180020EEF
0x180020ee0  mov     rax, [rsi]
0x180020ee3  mov     rcx, rsi
0x180020ee6  mov     rax, [rax+10h]
0x180020eea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020eef  mov     rcx, [rbp+bstrString]; bstrString
0x180020ef3  test    rcx, rcx
0x180020ef6  jz      short loc_180020EFE
0x180020ef8  call    cs:__imp_SysFreeString
0x180020efe  mov     eax, ebx
0x180020f00  add     rsp, 48h
0x180020f04  pop     r15
0x180020f06  pop     r14
0x180020f08  pop     r12
0x180020f0a  pop     rsi
0x180020f0b  pop     rbx
0x180020f0c  pop     rbp
0x180020f0d  retn
```
