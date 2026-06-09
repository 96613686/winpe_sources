# SdpParseParameter(IXMLDOMNode *,_SDIAG_PARAMETER *)

- ea: `0x180003e50`
- end: `0x1800040e2`
- name: `?SdpParseParameter@@YAJPEAUIXMLDOMNode@@PEAU_SDIAG_PARAMETER@@@Z`
- size: `658`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, struct _SDIAG_PARAMETER *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800040e8`

## callees

- `0x180003e50`
- `0x180026fa0`
- `0x180028038`
- `0x1800286a4`
- `0x1800290bc`
- `0x18002a010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180004022`
- `msvcrt!_wcsicmp` at `0x180004022`
- `OLEAUT32!__imp_SysFreeString` at `0x180004035`
- `OLEAUT32!__imp_SysFreeString` at `0x1800040b7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800040ce`
- `OLEAUT32!__imp_SysFreeString` at `0x180004035`
- `OLEAUT32!__imp_SysFreeString` at `0x1800040b7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800040ce`

## pseudocode

```c
__int64 __fastcall SdpParseParameter(struct IXMLDOMNode *a1, struct _SDIAG_PARAMETER *a2)
{
  struct IXMLDOMNode *v2; // rsi
  int v4; // r8d
  unsigned int v5; // ebx
  int ChildNodes; // eax
  struct IXMLDOMNodeList *v7; // r15
  int v8; // r9d
  int v9; // r8d
  int v10; // eax
  int v11; // r8d
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  wchar_t *v17; // rcx
  BSTR bstrString; // [rsp+20h] [rbp-10h] BYREF
  struct IXMLDOMNodeList *v20; // [rsp+28h] [rbp-8h] BYREF
  unsigned int v21; // [rsp+60h] [rbp+30h] BYREF
  struct IXMLDOMNode *v22; // [rsp+70h] [rbp+40h] BYREF
  wchar_t *String1; // [rsp+78h] [rbp+48h] BYREF

  v2 = 0;
  v20 = 0;
  v22 = 0;
  v21 = 0;
  bstrString = 0;
  String1 = 0;
  if ( !a1 )
  {
    v4 = 439;
LABEL_3:
    v5 = -2147024809;
    SdpDebugTrace(1u, L"SdpParseParameter", v4, -2147024809);
    goto LABEL_40;
  }
  if ( !a2 )
  {
    v4 = 440;
    goto LABEL_3;
  }
  ChildNodes = SdpXmlGetChildNodes(0, a1, &v20, &v21);
  v7 = v20;
  v5 = ChildNodes;
  if ( ChildNodes < 0 )
  {
    v8 = ChildNodes;
    v9 = 443;
LABEL_35:
    SdpDebugTrace(1u, L"SdpParseParameter", v9, v8);
    goto LABEL_36;
  }
  if ( v21 < 2 )
  {
    v8 = -2147024809;
    v9 = 447;
LABEL_34:
    v5 = v8;
    goto LABEL_35;
  }
  v10 = SdpXmlNextNode(v20, &v22);
  v5 = v10;
  if ( v10 >= 0 )
  {
    v2 = v22;
    v12 = SdpXmlCheckNode(v22, L"Name");
    v5 = v12;
    if ( v12 < 0 )
    {
      v8 = v12;
      v9 = 456;
      goto LABEL_35;
    }
    if ( v12 == 1 || !v2 )
    {
      v9 = 456;
    }
    else
    {
      v13 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))v2->lpVtbl->get_text)(v2, &bstrString);
      v5 = v13;
      if ( v13 < 0 )
      {
        v8 = v13;
        v9 = 459;
        goto LABEL_35;
      }
      ((void (__fastcall *)(struct IXMLDOMNode *))v2->lpVtbl->Release)(v2);
      v22 = 0;
      v10 = SdpXmlNextNode(v7, &v22);
      v5 = v10;
      if ( v10 < 0 )
      {
        v11 = 467;
        goto LABEL_12;
      }
      v2 = v22;
      v14 = SdpXmlCheckNode(v22, L"DefaultValue");
      v5 = v14;
      if ( v14 < 0 )
      {
        v8 = v14;
        v9 = 468;
        goto LABEL_35;
      }
      if ( v14 != 1 && v2 )
      {
        v15 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, wchar_t **))v2->lpVtbl->get_text)(v2, &String1);
        v5 = v15;
        if ( v15 >= 0 )
        {
          v16 = _wcsicmp(String1, &word_18002DFCC);
          v17 = String1;
          if ( !v16 && String1 )
          {
            SysFreeString(String1);
            v17 = 0;
          }
          *(_QWORD *)a2 = bstrString;
          bstrString = 0;
          *((_QWORD *)a2 + 1) = v17;
          *((_QWORD *)a2 + 2) = v17;
          String1 = 0;
          goto LABEL_36;
        }
        v8 = v15;
        v9 = 471;
        goto LABEL_35;
      }
      v9 = 468;
    }
    v8 = -2147467259;
    goto LABEL_34;
  }
  v11 = 455;
LABEL_12:
  SdpDebugTrace(1u, L"SdpParseParameter", v11, v10);
  v2 = v22;
LABEL_36:
  if ( v7 )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v7->lpVtbl->Release)(v7);
  if ( v2 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v2->lpVtbl->Release)(v2);
LABEL_40:
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( String1 )
    SysFreeString(String1);
  return v5;
}

```

## disassembly

```asm
0x180003e50  push    rbp
0x180003e52  push    rbx
0x180003e53  push    rsi
0x180003e54  push    r14
0x180003e56  push    r15
0x180003e58  mov     rbp, rsp
0x180003e5b  sub     rsp, 30h
0x180003e5f  xor     esi, esi
0x180003e61  mov     [rbp+var_8], 0
0x180003e69  mov     [rbp+arg_10], rsi
0x180003e6d  mov     r14, rdx
0x180003e70  mov     [rbp+arg_0], esi
0x180003e73  mov     [rbp+bstrString], rsi
0x180003e77  mov     [rbp+String1], rsi
0x180003e7b  test    rcx, rcx
0x180003e7e  jnz     short loc_180003EA5
0x180003e80  mov     r8d, 1B7h; int
0x180003e86  mov     r9d, 80070057h; int
0x180003e8c  lea     rdx, aSdpparseparame_0; "SdpParseParameter"
0x180003e93  mov     ecx, 1; Level
0x180003e98  mov     ebx, r9d
0x180003e9b  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180003ea0  jmp     loc_1800040AE
0x180003ea5  test    r14, r14
0x180003ea8  jnz     short loc_180003EB2
0x180003eaa  mov     r8d, 1B8h
0x180003eb0  jmp     short loc_180003E86
0x180003eb2  mov     rdx, rcx; struct IXMLDOMNode *
0x180003eb5  lea     r9, [rbp+arg_0]; unsigned int *
0x180003eb9  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x180003ebb  lea     r8, [rbp+var_8]; struct IXMLDOMNodeList **
0x180003ebf  call    ?SdpXmlGetChildNodes@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@PEAK@Z; SdpXmlGetChildNodes(IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *,ulong *)
0x180003ec4  mov     r15, [rbp+var_8]
0x180003ec8  mov     ebx, eax
0x180003eca  test    eax, eax
0x180003ecc  jns     short loc_180003EDC
0x180003ece  mov     r9d, eax
0x180003ed1  mov     r8d, 1BBh
0x180003ed7  jmp     loc_180004075
0x180003edc  cmp     [rbp+arg_0], 2
0x180003ee0  jnb     short loc_180003EF3
0x180003ee2  mov     r9d, 80070057h
0x180003ee8  mov     r8d, 1BFh
0x180003eee  jmp     loc_180004072
0x180003ef3  lea     rdx, [rbp+arg_10]; struct IXMLDOMNode **
0x180003ef7  mov     rcx, r15; struct IXMLDOMNodeList *
0x180003efa  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x180003eff  mov     ebx, eax
0x180003f01  test    eax, eax
0x180003f03  jns     short loc_180003F28
0x180003f05  mov     r8d, 1C7h; int
0x180003f0b  mov     r9d, eax; int
0x180003f0e  lea     rdx, aSdpparseparame_0; "SdpParseParameter"
0x180003f15  mov     ecx, 1; Level
0x180003f1a  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180003f1f  mov     rsi, [rbp+arg_10]
0x180003f23  jmp     loc_180004086
0x180003f28  mov     rsi, [rbp+arg_10]
0x180003f2c  lea     rdx, aName; "Name"
0x180003f33  mov     rcx, rsi; struct IXMLDOMNode *
0x180003f36  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x180003f3b  mov     ebx, eax
0x180003f3d  test    eax, eax
0x180003f3f  jns     short loc_180003F4F
0x180003f41  mov     r9d, eax
0x180003f44  mov     r8d, 1C8h
0x180003f4a  jmp     loc_180004075
0x180003f4f  cmp     eax, 1
0x180003f52  jz      loc_180004066
0x180003f58  test    rsi, rsi
0x180003f5b  jz      loc_180004066
0x180003f61  mov     rax, [rsi]
0x180003f64  lea     rdx, [rbp+bstrString]
0x180003f68  mov     rcx, rsi
0x180003f6b  mov     rax, [rax+0D0h]
0x180003f72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f77  mov     ebx, eax
0x180003f79  test    eax, eax
0x180003f7b  jns     short loc_180003F8B
0x180003f7d  mov     r9d, eax
0x180003f80  mov     r8d, 1CBh
0x180003f86  jmp     loc_180004075
0x180003f8b  mov     rax, [rsi]
0x180003f8e  mov     rcx, rsi
0x180003f91  mov     rax, [rax+10h]
0x180003f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f9a  lea     rdx, [rbp+arg_10]; struct IXMLDOMNode **
0x180003f9e  mov     [rbp+arg_10], 0
0x180003fa6  mov     rcx, r15; struct IXMLDOMNodeList *
0x180003fa9  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x180003fae  mov     ebx, eax
0x180003fb0  test    eax, eax
0x180003fb2  jns     short loc_180003FBF
0x180003fb4  mov     r8d, 1D3h
0x180003fba  jmp     loc_180003F0B
0x180003fbf  mov     rsi, [rbp+arg_10]
0x180003fc3  lea     rdx, aDefaultvalue; "DefaultValue"
0x180003fca  mov     rcx, rsi; struct IXMLDOMNode *
0x180003fcd  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x180003fd2  mov     ebx, eax
0x180003fd4  test    eax, eax
0x180003fd6  jns     short loc_180003FE6
0x180003fd8  mov     r9d, eax
0x180003fdb  mov     r8d, 1D4h
0x180003fe1  jmp     loc_180004075
0x180003fe6  cmp     eax, 1
0x180003fe9  jz      short loc_18000405E
0x180003feb  test    rsi, rsi
0x180003fee  jz      short loc_18000405E
0x180003ff0  mov     rax, [rsi]
0x180003ff3  lea     rdx, [rbp+String1]
0x180003ff7  mov     rcx, rsi
0x180003ffa  mov     rax, [rax+0D0h]
0x180004001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004006  mov     ebx, eax
0x180004008  test    eax, eax
0x18000400a  jns     short loc_180004017
0x18000400c  mov     r9d, eax
0x18000400f  mov     r8d, 1D7h
0x180004015  jmp     short loc_180004075
0x180004017  mov     rcx, [rbp+String1]; String1
0x18000401b  lea     rdx, word_18002DFCC; String2
0x180004022  call    cs:__imp__wcsicmp
0x180004028  mov     rcx, [rbp+String1]; bstrString
0x18000402c  test    eax, eax
0x18000402e  jnz     short loc_18000403D
0x180004030  test    rcx, rcx
0x180004033  jz      short loc_18000403D
0x180004035  call    cs:__imp_SysFreeString
0x18000403b  xor     ecx, ecx
0x18000403d  mov     rax, [rbp+bstrString]
0x180004041  mov     [r14], rax
0x180004044  mov     [rbp+bstrString], 0
0x18000404c  mov     [r14+8], rcx
0x180004050  mov     [r14+10h], rcx
0x180004054  mov     [rbp+String1], 0
0x18000405c  jmp     short loc_180004086
0x18000405e  mov     r8d, 1D4h
0x180004064  jmp     short loc_18000406C
0x180004066  mov     r8d, 1C8h; int
0x18000406c  mov     r9d, 80004005h; int
0x180004072  mov     ebx, r9d
0x180004075  lea     rdx, aSdpparseparame_0; "SdpParseParameter"
0x18000407c  mov     ecx, 1; Level
0x180004081  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180004086  test    r15, r15
0x180004089  jz      short loc_18000409A
0x18000408b  mov     rax, [r15]
0x18000408e  mov     rcx, r15
0x180004091  mov     rax, [rax+10h]
0x180004095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000409a  test    rsi, rsi
0x18000409d  jz      short loc_1800040AE
0x18000409f  mov     rax, [rsi]
0x1800040a2  mov     rcx, rsi
0x1800040a5  mov     rax, [rax+10h]
0x1800040a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040ae  mov     rcx, [rbp+bstrString]; bstrString
0x1800040b2  test    rcx, rcx
0x1800040b5  jz      short loc_1800040C5
0x1800040b7  call    cs:__imp_SysFreeString
0x1800040bd  mov     [rbp+bstrString], 0
0x1800040c5  mov     rcx, [rbp+String1]; bstrString
0x1800040c9  test    rcx, rcx
0x1800040cc  jz      short loc_1800040D4
0x1800040ce  call    cs:__imp_SysFreeString
0x1800040d4  mov     eax, ebx
0x1800040d6  add     rsp, 30h
0x1800040da  pop     r15
0x1800040dc  pop     r14
0x1800040de  pop     rsi
0x1800040df  pop     rbx
0x1800040e0  pop     rbp
0x1800040e1  retn
```
