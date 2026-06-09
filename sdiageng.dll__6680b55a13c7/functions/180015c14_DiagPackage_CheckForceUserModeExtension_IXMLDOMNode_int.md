# DiagPackage::CheckForceUserModeExtension(IXMLDOMNode *,int *)

- ea: `0x180015c14`
- end: `0x180015e2a`
- name: `?CheckForceUserModeExtension@DiagPackage@@AEAAJPEAUIXMLDOMNode@@PEAH@Z`
- size: `534`
- prototype: `__int64 __fastcall(DiagPackage *__hidden this, struct IXMLDOMNode *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180016630`

## callees

- `0x180015c14`
- `0x180026fa0`
- `0x1800286a4`
- `0x1800290bc`
- `0x18002a010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180015d97`
- `msvcrt!_wcsicmp` at `0x180015dc8`
- `msvcrt!_wcsicmp` at `0x180015d97`
- `msvcrt!_wcsicmp` at `0x180015dc8`
- `OLEAUT32!__imp_SysFreeString` at `0x180015cba`
- `OLEAUT32!__imp_SysFreeString` at `0x180015cd1`
- `OLEAUT32!__imp_SysFreeString` at `0x180015d4b`
- `OLEAUT32!__imp_SysFreeString` at `0x180015cba`
- `OLEAUT32!__imp_SysFreeString` at `0x180015cd1`
- `OLEAUT32!__imp_SysFreeString` at `0x180015d4b`

## string_xrefs

- `0x180015c5a`: `DiagPackage::CheckForceUserModeExtension`
- `0x180015c96`: `DiagPackage::CheckForceUserModeExtension`
- `0x180015e0a`: `DiagPackage::CheckForceUserModeExtension`

## pseudocode

```c
__int64 __fastcall DiagPackage::CheckForceUserModeExtension(DiagPackage *this, struct IXMLDOMNode *a2, int *a3)
{
  struct IXMLDOMNodeList *v3; // rsi
  struct IXMLDOMNode *v4; // rdi
  int v6; // r8d
  int v7; // r9d
  unsigned int v8; // ebx
  int ChildNodes; // eax
  int v11; // r14d
  int v12; // eax
  int v13; // eax
  int v14; // eax
  struct IXMLDOMNodeList *v15; // [rsp+20h] [rbp-10h] BYREF
  BSTR String1; // [rsp+28h] [rbp-8h] BYREF
  unsigned int v17; // [rsp+60h] [rbp+30h] BYREF
  int v18; // [rsp+64h] [rbp+34h]
  BSTR bstrString; // [rsp+68h] [rbp+38h] BYREF
  struct IXMLDOMNode *v20; // [rsp+78h] [rbp+48h] BYREF

  v18 = HIDWORD(this);
  v3 = 0;
  v4 = 0;
  v15 = 0;
  v20 = 0;
  v17 = 0;
  bstrString = 0;
  String1 = 0;
  if ( !a2 )
  {
    v6 = 1411;
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v6 = 1412;
LABEL_3:
    v7 = -2147024809;
    v8 = -2147024809;
LABEL_4:
    SdpDebugTrace(1u, L"DiagPackage::CheckForceUserModeExtension", v6, v7);
    goto LABEL_10;
  }
  ChildNodes = SdpXmlGetChildNodes(0, a2, &v15, &v17);
  v8 = ChildNodes;
  if ( ChildNodes < 0 )
  {
    SdpDebugTrace(1u, L"DiagPackage::CheckForceUserModeExtension", 1415, ChildNodes);
LABEL_9:
    v3 = v15;
    goto LABEL_10;
  }
  v11 = 0;
  if ( !v17 )
    goto LABEL_9;
  v3 = v15;
  while ( 1 )
  {
    if ( v4 )
    {
      ((void (__fastcall *)(struct IXMLDOMNode *))v4->lpVtbl->Release)(v4);
      v20 = 0;
    }
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
    v12 = SdpXmlNextNode(v3, &v20);
    v8 = v12;
    if ( v12 < 0 )
      break;
    v4 = v20;
    v13 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))v20->lpVtbl->get_nodeName)(v20, &bstrString);
    v8 = v13;
    if ( v13 < 0 )
    {
      v7 = v13;
      v6 = 1426;
      goto LABEL_4;
    }
    if ( !_wcsicmp(bstrString, L"ForceUsermode") )
    {
      v14 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))v4->lpVtbl->get_text)(v4, &String1);
      v8 = v14;
      if ( v14 < 0 )
      {
        v7 = v14;
        v6 = 1433;
        goto LABEL_4;
      }
      *a3 = _wcsicmp(String1, L"TRUE") == 0;
    }
    if ( ++v11 >= v17 )
      goto LABEL_10;
  }
  SdpDebugTrace(1u, L"DiagPackage::CheckForceUserModeExtension", 1423, v12);
  v4 = v20;
LABEL_10:
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( String1 )
  {
    SysFreeString(String1);
    String1 = 0;
  }
  if ( v3 )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v3->lpVtbl->Release)(v3);
  if ( v4 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v4->lpVtbl->Release)(v4);
  return v8;
}

```

## disassembly

```asm
0x180015c14  mov     [rsp-28h+arg_10], rbx
0x180015c19  mov     qword ptr [rsp-28h+arg_0], rcx
0x180015c1e  push    rbp
0x180015c1f  push    rsi
0x180015c20  push    rdi
0x180015c21  push    r12
0x180015c23  push    r14
0x180015c25  mov     rbp, rsp
0x180015c28  sub     rsp, 30h
0x180015c2c  xor     esi, esi
0x180015c2e  xor     edi, edi
0x180015c30  mov     [rbp+var_10], rsi
0x180015c34  mov     r12, r8
0x180015c37  mov     [rbp+arg_18], rdi
0x180015c3b  mov     [rbp+arg_0], esi
0x180015c3e  mov     [rbp+bstrString], rsi
0x180015c42  mov     [rbp+String1], rsi
0x180015c46  test    rdx, rdx
0x180015c49  jnz     short loc_180015C6D
0x180015c4b  mov     r8d, 583h; int
0x180015c51  mov     r9d, 80070057h; int
0x180015c57  mov     ebx, r9d
0x180015c5a  lea     rdx, aDiagpackageChe; "DiagPackage::CheckForceUserModeExtensio"...
0x180015c61  mov     ecx, 1; Level
0x180015c66  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180015c6b  jmp     short loc_180015CB1
0x180015c6d  test    r12, r12
0x180015c70  jnz     short loc_180015C7A
0x180015c72  mov     r8d, 584h
0x180015c78  jmp     short loc_180015C51
0x180015c7a  lea     r9, [rbp+arg_0]; unsigned int *
0x180015c7e  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x180015c80  lea     r8, [rbp+var_10]; struct IXMLDOMNodeList **
0x180015c84  call    ?SdpXmlGetChildNodes@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@PEAK@Z; SdpXmlGetChildNodes(IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *,ulong *)
0x180015c89  mov     ebx, eax
0x180015c8b  test    eax, eax
0x180015c8d  jns     loc_180015D1A
0x180015c93  mov     r9d, eax; int
0x180015c96  lea     rdx, aDiagpackageChe; "DiagPackage::CheckForceUserModeExtensio"...
0x180015c9d  mov     r8d, 587h; int
0x180015ca3  mov     ecx, 1; Level
0x180015ca8  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180015cad  mov     rsi, [rbp+var_10]
0x180015cb1  mov     rcx, [rbp+bstrString]; bstrString
0x180015cb5  test    rcx, rcx
0x180015cb8  jz      short loc_180015CC8
0x180015cba  call    cs:__imp_SysFreeString
0x180015cc0  mov     [rbp+bstrString], 0
0x180015cc8  mov     rcx, [rbp+String1]; bstrString
0x180015ccc  test    rcx, rcx
0x180015ccf  jz      short loc_180015CDF
0x180015cd1  call    cs:__imp_SysFreeString
0x180015cd7  mov     [rbp+String1], 0
0x180015cdf  test    rsi, rsi
0x180015ce2  jz      short loc_180015CF3
0x180015ce4  mov     rax, [rsi]
0x180015ce7  mov     rcx, rsi
0x180015cea  mov     rax, [rax+10h]
0x180015cee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015cf3  test    rdi, rdi
0x180015cf6  jz      short loc_180015D07
0x180015cf8  mov     rax, [rdi]
0x180015cfb  mov     rcx, rdi
0x180015cfe  mov     rax, [rax+10h]
0x180015d02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d07  mov     eax, ebx
0x180015d09  mov     rbx, [rsp+30h+arg_10]
0x180015d0e  add     rsp, 30h
0x180015d12  pop     r14
0x180015d14  pop     r12
0x180015d16  pop     rdi
0x180015d17  pop     rsi
0x180015d18  pop     rbp
0x180015d19  retn
0x180015d1a  xor     r14d, r14d
0x180015d1d  cmp     [rbp+arg_0], esi
0x180015d20  jbe     short loc_180015CAD
0x180015d22  mov     rsi, [rbp+var_10]
0x180015d26  test    rdi, rdi
0x180015d29  jz      short loc_180015D42
0x180015d2b  mov     rax, [rdi]
0x180015d2e  mov     rcx, rdi
0x180015d31  mov     rax, [rax+10h]
0x180015d35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d3a  mov     [rbp+arg_18], 0
0x180015d42  mov     rcx, [rbp+bstrString]; bstrString
0x180015d46  test    rcx, rcx
0x180015d49  jz      short loc_180015D59
0x180015d4b  call    cs:__imp_SysFreeString
0x180015d51  mov     [rbp+bstrString], 0
0x180015d59  lea     rdx, [rbp+arg_18]; struct IXMLDOMNode **
0x180015d5d  mov     rcx, rsi; struct IXMLDOMNodeList *
0x180015d60  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x180015d65  mov     ebx, eax
0x180015d67  test    eax, eax
0x180015d69  js      loc_180015E07
0x180015d6f  mov     rdi, [rbp+arg_18]
0x180015d73  lea     rdx, [rbp+bstrString]
0x180015d77  mov     rcx, rdi
0x180015d7a  mov     rax, [rdi]
0x180015d7d  mov     rax, [rax+38h]
0x180015d81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d86  mov     ebx, eax
0x180015d88  test    eax, eax
0x180015d8a  js      short loc_180015DF9
0x180015d8c  mov     rcx, [rbp+bstrString]; String1
0x180015d90  lea     rdx, aForceusermode; "ForceUsermode"
0x180015d97  call    cs:__imp__wcsicmp
0x180015d9d  test    eax, eax
0x180015d9f  jnz     short loc_180015DD9
0x180015da1  mov     rax, [rdi]
0x180015da4  lea     rdx, [rbp+String1]
0x180015da8  mov     rcx, rdi
0x180015dab  mov     rax, [rax+0D0h]
0x180015db2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015db7  mov     ebx, eax
0x180015db9  test    eax, eax
0x180015dbb  js      short loc_180015DEB
0x180015dbd  mov     rcx, [rbp+String1]; String1
0x180015dc1  lea     rdx, aTrue_0; "TRUE"
0x180015dc8  call    cs:__imp__wcsicmp
0x180015dce  xor     ecx, ecx
0x180015dd0  test    eax, eax
0x180015dd2  setz    cl
0x180015dd5  mov     [r12], ecx
0x180015dd9  inc     r14d
0x180015ddc  cmp     r14d, [rbp+arg_0]
0x180015de0  jb      loc_180015D26
0x180015de6  jmp     loc_180015CB1
0x180015deb  mov     r9d, eax
0x180015dee  mov     r8d, 599h
0x180015df4  jmp     loc_180015C5A
0x180015df9  mov     r9d, eax
0x180015dfc  mov     r8d, 592h
0x180015e02  jmp     loc_180015C5A
0x180015e07  mov     r9d, eax; int
0x180015e0a  lea     rdx, aDiagpackageChe; "DiagPackage::CheckForceUserModeExtensio"...
0x180015e11  mov     r8d, 58Fh; int
0x180015e17  mov     ecx, 1; Level
0x180015e1c  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180015e21  mov     rdi, [rbp+arg_18]
0x180015e25  jmp     loc_180015CB1
```
