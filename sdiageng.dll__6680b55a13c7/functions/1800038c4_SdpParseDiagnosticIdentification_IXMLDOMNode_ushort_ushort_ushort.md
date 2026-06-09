# SdpParseDiagnosticIdentification(IXMLDOMNode *,ushort * *,ushort * *,ushort * *)

- ea: `0x1800038c4`
- end: `0x180003b24`
- name: `?SdpParseDiagnosticIdentification@@YAJPEAUIXMLDOMNode@@PEAPEAG11@Z`
- size: `608`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180016630`

## callees

- `0x1800038c4`
- `0x180026fa0`
- `0x1800286a4`
- `0x1800290bc`
- `0x18002a010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180003ad5`
- `OLEAUT32!__imp_SysFreeString` at `0x180003aec`
- `OLEAUT32!__imp_SysFreeString` at `0x180003b03`
- `OLEAUT32!__imp_SysFreeString` at `0x180003ad5`
- `OLEAUT32!__imp_SysFreeString` at `0x180003aec`
- `OLEAUT32!__imp_SysFreeString` at `0x180003b03`

## pseudocode

```c
__int64 __fastcall SdpParseDiagnosticIdentification(
        struct IXMLDOMNode *a1,
        unsigned __int16 **a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4)
{
  struct IXMLDOMNode *v4; // rdi
  unsigned int v9; // r8d
  int v10; // r9d
  unsigned int v11; // ebx
  int v12; // eax
  int ChildNodes; // eax
  struct IXMLDOMNodeList *v14; // rsi
  unsigned int v15; // r8d
  int v16; // r9d
  int v17; // eax
  unsigned int v18; // r8d
  struct IXMLDOMNode *v20; // [rsp+20h] [rbp-30h] BYREF
  BSTR bstrString; // [rsp+28h] [rbp-28h] BYREF
  BSTR v22; // [rsp+30h] [rbp-20h] BYREF
  BSTR v23; // [rsp+38h] [rbp-18h] BYREF
  struct IXMLDOMNodeList *v24; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v25; // [rsp+80h] [rbp+30h] BYREF

  v4 = 0;
  v24 = 0;
  v20 = 0;
  v25 = 0;
  v22 = 0;
  bstrString = 0;
  v23 = 0;
  if ( !a1 )
  {
    v9 = 59;
LABEL_3:
    v10 = -2147024809;
    v11 = -2147024809;
LABEL_4:
    SdpDebugTrace(1u, L"SdpParseDiagnosticIdentification", v9, v10);
    goto LABEL_31;
  }
  if ( !a2 )
  {
    v9 = 60;
    goto LABEL_3;
  }
  if ( !a4 )
  {
    v9 = 61;
    goto LABEL_3;
  }
  v12 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))a1->lpVtbl->get_xml)(a1, &bstrString);
  v11 = v12;
  if ( v12 < 0 )
  {
    v10 = v12;
    v9 = 64;
    goto LABEL_4;
  }
  ChildNodes = SdpXmlGetChildNodes(0, a1, &v24, &v25);
  v14 = v24;
  v11 = ChildNodes;
  if ( ChildNodes >= 0 )
  {
    if ( v25 < 2 )
    {
      v16 = -2147024809;
      v15 = 71;
      v11 = -2147024809;
      goto LABEL_14;
    }
    v17 = SdpXmlNextNode(v24, &v20);
    v11 = v17;
    if ( v17 >= 0 )
    {
      v4 = v20;
      ChildNodes = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))v20->lpVtbl->get_text)(v20, &v22);
      v11 = ChildNodes;
      if ( ChildNodes < 0 )
      {
        v15 = 82;
        goto LABEL_13;
      }
      ((void (__fastcall *)(struct IXMLDOMNode *))v4->lpVtbl->Release)(v4);
      v20 = 0;
      v17 = SdpXmlNextNode(v14, &v20);
      v11 = v17;
      if ( v17 >= 0 )
      {
        v4 = v20;
        ChildNodes = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))v20->lpVtbl->get_text)(v20, &v23);
        v11 = ChildNodes;
        if ( ChildNodes >= 0 )
        {
          *a2 = v22;
          *a4 = bstrString;
          *a3 = v23;
          v22 = 0;
          bstrString = 0;
          v23 = 0;
          goto LABEL_27;
        }
        v15 = 94;
        goto LABEL_13;
      }
      v18 = 91;
    }
    else
    {
      v18 = 79;
    }
    SdpDebugTrace(1u, L"SdpParseDiagnosticIdentification", v18, v17);
    v4 = v20;
    goto LABEL_27;
  }
  v15 = 67;
LABEL_13:
  v16 = ChildNodes;
LABEL_14:
  SdpDebugTrace(1u, L"SdpParseDiagnosticIdentification", v15, v16);
LABEL_27:
  if ( v14 )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v14->lpVtbl->Release)(v14);
  if ( v4 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v4->lpVtbl->Release)(v4);
LABEL_31:
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v22 )
  {
    SysFreeString(v22);
    v22 = 0;
  }
  if ( v23 )
    SysFreeString(v23);
  return v11;
}

```

## disassembly

```asm
0x1800038c4  mov     [rsp-28h+arg_8], rbx
0x1800038c9  mov     [rsp-28h+arg_10], rsi
0x1800038ce  push    rbp
0x1800038cf  push    rdi
0x1800038d0  push    r12
0x1800038d2  push    r14
0x1800038d4  push    r15
0x1800038d6  mov     rbp, rsp
0x1800038d9  sub     rsp, 50h
0x1800038dd  xor     edi, edi
0x1800038df  mov     [rbp+var_10], 0
0x1800038e7  mov     [rbp+var_30], rdi
0x1800038eb  mov     r14, r9
0x1800038ee  mov     [rbp+arg_0], edi
0x1800038f1  mov     r12, r8
0x1800038f4  mov     [rbp+var_20], rdi
0x1800038f8  mov     r15, rdx
0x1800038fb  mov     [rbp+bstrString], rdi
0x1800038ff  mov     rsi, rcx
0x180003902  mov     [rbp+var_18], rdi
0x180003906  test    rcx, rcx
0x180003909  jnz     short loc_18000392E
0x18000390b  lea     r8d, [rcx+3Bh]; int
0x18000390f  mov     r9d, 80070057h; int
0x180003915  mov     ebx, r9d
0x180003918  lea     rdx, aSdpparsediagno; "SdpParseDiagnosticIdentification"
0x18000391f  mov     ecx, 1; Level
0x180003924  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180003929  jmp     loc_180003ACC
0x18000392e  test    r15, r15
0x180003931  jnz     short loc_180003939
0x180003933  lea     r8d, [r15+3Ch]
0x180003937  jmp     short loc_18000390F
0x180003939  test    r14, r14
0x18000393c  jnz     short loc_180003944
0x18000393e  lea     r8d, [r14+3Dh]
0x180003942  jmp     short loc_18000390F
0x180003944  mov     rax, [rcx]
0x180003947  lea     rdx, [rbp+bstrString]
0x18000394b  mov     rax, [rax+110h]
0x180003952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003957  mov     ebx, eax
0x180003959  test    eax, eax
0x18000395b  jns     short loc_180003968
0x18000395d  mov     r9d, eax
0x180003960  mov     r8d, 40h ; '@'
0x180003966  jmp     short loc_180003918
0x180003968  lea     r9, [rbp+arg_0]; unsigned int *
0x18000396c  mov     rdx, rsi; struct IXMLDOMNode *
0x18000396f  lea     r8, [rbp+var_10]; struct IXMLDOMNodeList **
0x180003973  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x180003975  call    ?SdpXmlGetChildNodes@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@PEAK@Z; SdpXmlGetChildNodes(IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *,ulong *)
0x18000397a  mov     rsi, [rbp+var_10]
0x18000397e  mov     ebx, eax
0x180003980  test    eax, eax
0x180003982  jns     short loc_1800039A3
0x180003984  mov     r8d, 43h ; 'C'; int
0x18000398a  mov     r9d, eax; int
0x18000398d  lea     rdx, aSdpparsediagno; "SdpParseDiagnosticIdentification"
0x180003994  mov     ecx, 1; Level
0x180003999  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000399e  jmp     loc_180003AA4
0x1800039a3  cmp     [rbp+arg_0], 2
0x1800039a7  jnb     short loc_1800039BA
0x1800039a9  mov     r9d, 80070057h
0x1800039af  mov     r8d, 47h ; 'G'
0x1800039b5  mov     ebx, r9d
0x1800039b8  jmp     short loc_18000398D
0x1800039ba  lea     rdx, [rbp+var_30]; struct IXMLDOMNode **
0x1800039be  mov     rcx, rsi; struct IXMLDOMNodeList *
0x1800039c1  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x1800039c6  mov     ebx, eax
0x1800039c8  test    eax, eax
0x1800039ca  jns     short loc_1800039EF
0x1800039cc  mov     r8d, 4Fh ; 'O'; int
0x1800039d2  mov     r9d, eax; int
0x1800039d5  lea     rdx, aSdpparsediagno; "SdpParseDiagnosticIdentification"
0x1800039dc  mov     ecx, 1; Level
0x1800039e1  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800039e6  mov     rdi, [rbp+var_30]
0x1800039ea  jmp     loc_180003AA4
0x1800039ef  mov     rdi, [rbp+var_30]
0x1800039f3  lea     rdx, [rbp+var_20]
0x1800039f7  mov     rcx, rdi
0x1800039fa  mov     rax, [rdi]
0x1800039fd  mov     rax, [rax+0D0h]
0x180003a04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a09  mov     ebx, eax
0x180003a0b  test    eax, eax
0x180003a0d  jns     short loc_180003A1A
0x180003a0f  mov     r8d, 52h ; 'R'
0x180003a15  jmp     loc_18000398A
0x180003a1a  mov     rax, [rdi]
0x180003a1d  mov     rcx, rdi
0x180003a20  mov     rax, [rax+10h]
0x180003a24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a29  lea     rdx, [rbp+var_30]; struct IXMLDOMNode **
0x180003a2d  mov     [rbp+var_30], 0
0x180003a35  mov     rcx, rsi; struct IXMLDOMNodeList *
0x180003a38  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x180003a3d  mov     ebx, eax
0x180003a3f  test    eax, eax
0x180003a41  jns     short loc_180003A4B
0x180003a43  mov     r8d, 5Bh ; '['
0x180003a49  jmp     short loc_1800039D2
0x180003a4b  mov     rdi, [rbp+var_30]
0x180003a4f  lea     rdx, [rbp+var_18]
0x180003a53  mov     rcx, rdi
0x180003a56  mov     rax, [rdi]
0x180003a59  mov     rax, [rax+0D0h]
0x180003a60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a65  mov     ebx, eax
0x180003a67  test    eax, eax
0x180003a69  jns     short loc_180003A76
0x180003a6b  mov     r8d, 5Eh ; '^'
0x180003a71  jmp     loc_18000398A
0x180003a76  mov     rax, [rbp+var_20]
0x180003a7a  mov     [r15], rax
0x180003a7d  mov     rax, [rbp+bstrString]
0x180003a81  mov     [r14], rax
0x180003a84  mov     rax, [rbp+var_18]
0x180003a88  mov     [r12], rax
0x180003a8c  mov     [rbp+var_20], 0
0x180003a94  mov     [rbp+bstrString], 0
0x180003a9c  mov     [rbp+var_18], 0
0x180003aa4  test    rsi, rsi
0x180003aa7  jz      short loc_180003AB8
0x180003aa9  mov     rax, [rsi]
0x180003aac  mov     rcx, rsi
0x180003aaf  mov     rax, [rax+10h]
0x180003ab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ab8  test    rdi, rdi
0x180003abb  jz      short loc_180003ACC
0x180003abd  mov     rax, [rdi]
0x180003ac0  mov     rcx, rdi
0x180003ac3  mov     rax, [rax+10h]
0x180003ac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003acc  mov     rcx, [rbp+bstrString]; bstrString
0x180003ad0  test    rcx, rcx
0x180003ad3  jz      short loc_180003AE3
0x180003ad5  call    cs:__imp_SysFreeString
0x180003adb  mov     [rbp+bstrString], 0
0x180003ae3  mov     rcx, [rbp+var_20]; bstrString
0x180003ae7  test    rcx, rcx
0x180003aea  jz      short loc_180003AFA
0x180003aec  call    cs:__imp_SysFreeString
0x180003af2  mov     [rbp+var_20], 0
0x180003afa  mov     rcx, [rbp+var_18]; bstrString
0x180003afe  test    rcx, rcx
0x180003b01  jz      short loc_180003B09
0x180003b03  call    cs:__imp_SysFreeString
0x180003b09  lea     r11, [rsp+50h+var_s0]
0x180003b0e  mov     eax, ebx
0x180003b10  mov     rbx, [r11+38h]
0x180003b14  mov     rsi, [r11+40h]
0x180003b18  mov     rsp, r11
0x180003b1b  pop     r15
0x180003b1d  pop     r14
0x180003b1f  pop     r12
0x180003b21  pop     rdi
0x180003b22  pop     rbp
0x180003b23  retn
```
