# CNotification::SchdpUpdateParameter(IXMLDOMNode *,long)

- ea: `0x180003e10`
- end: `0x1800040ac`
- name: `?SchdpUpdateParameter@CNotification@@AEAAJPEAUIXMLDOMNode@@J@Z`
- size: `668`
- prototype: `__int64 __fastcall(CNotification *__hidden this, struct IXMLDOMNode *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x1800040b4`

## callees

- `0x180003e10`
- `0x18000b13c`
- `0x18000b234`
- `0x18000b498`
- `0x18000b884`
- `0x18000d010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180004050`
- `OLEAUT32!__imp_SysFreeString` at `0x18000406a`
- `OLEAUT32!__imp_SysFreeString` at `0x180004084`
- `OLEAUT32!__imp_SysFreeString` at `0x180004050`
- `OLEAUT32!__imp_SysFreeString` at `0x18000406a`
- `OLEAUT32!__imp_SysFreeString` at `0x180004084`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180003f23`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180003f23`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180003fda`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180003fda`

## string_xrefs

- `0x180003e8f`: `CNotification::SchdpUpdateParameter`
- `0x180004013`: `CNotification::SchdpUpdateParameter`

## pseudocode

```c
__int64 __fastcall CNotification::SchdpUpdateParameter(struct IXMLDOMDocument2 *this, struct IXMLDOMNode *a2, int a3)
{
  struct IXMLDOMNode *v3; // rsi
  int ChildNodes; // eax
  struct IXMLDOMNodeList *v7; // r14
  unsigned int v8; // ebx
  int v9; // r9d
  int v10; // r8d
  int v11; // eax
  int v12; // r8d
  int v13; // eax
  HRESULT Element; // eax
  SAFEARRAY *lpVtbl; // rcx
  int v16; // eax
  SAFEARRAY *v17; // rcx
  struct IXMLDOMNode *v19; // [rsp+20h] [rbp-30h] BYREF
  LONG rgIndices; // [rsp+28h] [rbp-28h] BYREF
  int v21; // [rsp+2Ch] [rbp-24h]
  BSTR v22; // [rsp+30h] [rbp-20h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-18h] BYREF
  struct IXMLDOMNodeList *v24; // [rsp+40h] [rbp-10h] BYREF
  BSTR pv; // [rsp+48h] [rbp-8h] BYREF
  unsigned int v26; // [rsp+98h] [rbp+48h] BYREF

  v26 = 0;
  v24 = 0;
  v3 = 0;
  bstrString = 0;
  v22 = 0;
  pv = 0;
  v19 = 0;
  ChildNodes = SdpXmlGetChildNodes(this, a2, &v24, &v26);
  v7 = v24;
  v8 = ChildNodes;
  if ( ChildNodes >= 0 )
  {
    v11 = SdpXmlNextNode(v24, &v19);
    v8 = v11;
    if ( v11 < 0 )
    {
      v12 = 431;
LABEL_5:
      SdpDebugTrace(1u, L"CNotification::SchdpUpdateParameter", v12, v11);
      v3 = v19;
      goto LABEL_30;
    }
    v3 = v19;
    v13 = SdpXmlCheckNode(v19, L"Name");
    v8 = v13;
    if ( v13 < 0 )
    {
      v9 = v13;
LABEL_28:
      v10 = 432;
      goto LABEL_29;
    }
    if ( v13 == 1 || !v3 )
    {
      v9 = -2147467259;
      v8 = -2147467259;
      goto LABEL_28;
    }
    Element = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))v3->lpVtbl->get_text)(v3, &bstrString);
    v8 = Element;
    if ( Element >= 0 )
    {
      lpVtbl = (SAFEARRAY *)this[3].lpVtbl;
      rgIndices = 0;
      v21 = a3;
      Element = SafeArrayGetElement(lpVtbl, &rgIndices, &pv);
      v8 = Element;
      if ( Element >= 0 )
      {
        ((void (__fastcall *)(struct IXMLDOMNode *))v3->lpVtbl->Release)(v3);
        v19 = 0;
        v11 = SdpXmlNextNode(v7, &v19);
        v8 = v11;
        if ( v11 < 0 )
        {
          v12 = 447;
          goto LABEL_5;
        }
        v3 = v19;
        v16 = SdpXmlCheckNode(v19, L"Value");
        v8 = v16;
        if ( v16 >= 0 )
        {
          if ( v16 != 1 && v3 )
          {
            Element = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))v3->lpVtbl->get_text)(v3, &v22);
            v8 = Element;
            if ( Element >= 0 )
            {
              v17 = (SAFEARRAY *)this[3].lpVtbl;
              rgIndices = 1;
              v21 = a3;
              Element = SafeArrayPutElement(v17, &rgIndices, v22);
              v8 = Element;
              if ( Element >= 0 )
                goto LABEL_30;
              v10 = 457;
            }
            else
            {
              v10 = 451;
            }
            goto LABEL_12;
          }
          v9 = -2147467259;
          v8 = -2147467259;
        }
        else
        {
          v9 = v16;
        }
        v10 = 448;
        goto LABEL_29;
      }
      v10 = 441;
    }
    else
    {
      v10 = 435;
    }
LABEL_12:
    v9 = Element;
    goto LABEL_29;
  }
  v9 = ChildNodes;
  v10 = 427;
LABEL_29:
  SdpDebugTrace(1u, L"CNotification::SchdpUpdateParameter", v10, v9);
LABEL_30:
  if ( v7 )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v7->lpVtbl->Release)(v7);
  if ( v3 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v3->lpVtbl->Release)(v3);
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
  if ( pv )
    SysFreeString(pv);
  return v8;
}

```

## disassembly

```asm
0x180003e10  mov     [rsp-28h+arg_0], rbx
0x180003e15  mov     [rsp-28h+arg_8], rsi
0x180003e1a  push    rbp
0x180003e1b  push    rdi
0x180003e1c  push    r13
0x180003e1e  push    r14
0x180003e20  push    r15
0x180003e22  mov     rbp, rsp
0x180003e25  sub     rsp, 50h
0x180003e29  and     [rbp+arg_18], 0
0x180003e2d  lea     r9, [rbp+arg_18]; unsigned int *
0x180003e31  and     [rbp+var_10], 0
0x180003e36  xor     esi, esi
0x180003e38  and     [rbp+bstrString], rsi
0x180003e3c  mov     r15d, r8d
0x180003e3f  and     [rbp+var_20], rsi
0x180003e43  lea     r8, [rbp+var_10]; struct IXMLDOMNodeList **
0x180003e47  and     [rbp+pv], rsi
0x180003e4b  mov     r13, rcx
0x180003e4e  mov     [rbp+var_30], rsi
0x180003e52  call    ?SdpXmlGetChildNodes@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@PEAK@Z; SdpXmlGetChildNodes(IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *,ulong *)
0x180003e57  mov     r14, [rbp+var_10]
0x180003e5b  mov     ebx, eax
0x180003e5d  test    eax, eax
0x180003e5f  jns     short loc_180003E72
0x180003e61  mov     r9d, eax
0x180003e64  lea     ecx, [rsi+1]
0x180003e67  mov     r8d, 1ABh
0x180003e6d  jmp     loc_180004013
0x180003e72  lea     rdx, [rbp+var_30]; struct IXMLDOMNode **
0x180003e76  mov     rcx, r14; struct IXMLDOMNodeList *
0x180003e79  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x180003e7e  mov     ebx, eax
0x180003e80  test    eax, eax
0x180003e82  jns     short loc_180003EA7
0x180003e84  mov     r8d, 1AFh; int
0x180003e8a  mov     ecx, 1; Level
0x180003e8f  lea     rdx, aCnotificationS_5; "CNotification::SchdpUpdateParameter"
0x180003e96  mov     r9d, eax; int
0x180003e99  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180003e9e  mov     rsi, [rbp+var_30]
0x180003ea2  jmp     loc_18000401F
0x180003ea7  mov     rsi, [rbp+var_30]
0x180003eab  lea     rdx, aName; "Name"
0x180003eb2  mov     rcx, rsi; struct IXMLDOMNode *
0x180003eb5  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x180003eba  mov     ebx, eax
0x180003ebc  test    eax, eax
0x180003ebe  jns     short loc_180003ECD
0x180003ec0  mov     r9d, eax
0x180003ec3  mov     ecx, 1
0x180003ec8  jmp     loc_18000400D
0x180003ecd  mov     edi, 1
0x180003ed2  cmp     eax, edi
0x180003ed4  jz      loc_180004002
0x180003eda  test    rsi, rsi
0x180003edd  jz      loc_180004002
0x180003ee3  mov     rax, [rsi]
0x180003ee6  lea     rdx, [rbp+bstrString]
0x180003eea  mov     rcx, rsi
0x180003eed  mov     rax, [rax+0D0h]
0x180003ef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ef9  mov     ebx, eax
0x180003efb  test    eax, eax
0x180003efd  jns     short loc_180003F0F
0x180003eff  mov     r8d, 1B3h
0x180003f05  mov     r9d, eax
0x180003f08  mov     ecx, edi
0x180003f0a  jmp     loc_180004013
0x180003f0f  mov     rcx, [r13+18h]; psa
0x180003f13  lea     r8, [rbp+pv]; pv
0x180003f17  and     [rbp+rgIndices], 0
0x180003f1b  lea     rdx, [rbp+rgIndices]; rgIndices
0x180003f1f  mov     [rbp+var_24], r15d
0x180003f23  call    cs:__imp_SafeArrayGetElement
0x180003f2a  nop     dword ptr [rax+rax+00h]
0x180003f2f  mov     ebx, eax
0x180003f31  test    eax, eax
0x180003f33  jns     short loc_180003F3D
0x180003f35  mov     r8d, 1B9h
0x180003f3b  jmp     short loc_180003F05
0x180003f3d  mov     rax, [rsi]
0x180003f40  mov     rcx, rsi
0x180003f43  mov     rax, [rax+10h]
0x180003f47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f4c  and     [rbp+var_30], 0
0x180003f51  lea     rdx, [rbp+var_30]; struct IXMLDOMNode **
0x180003f55  mov     rcx, r14; struct IXMLDOMNodeList *
0x180003f58  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x180003f5d  mov     ebx, eax
0x180003f5f  test    eax, eax
0x180003f61  jns     short loc_180003F70
0x180003f63  mov     r8d, 1BFh
0x180003f69  mov     ecx, edi
0x180003f6b  jmp     loc_180003E8F
0x180003f70  mov     rsi, [rbp+var_30]
0x180003f74  lea     rdx, aValue; "Value"
0x180003f7b  mov     rcx, rsi; struct IXMLDOMNode *
0x180003f7e  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x180003f83  mov     ebx, eax
0x180003f85  test    eax, eax
0x180003f87  jns     short loc_180003F97
0x180003f89  mov     r9d, eax
0x180003f8c  mov     r8d, 1C0h
0x180003f92  jmp     loc_180003F08
0x180003f97  cmp     eax, edi
0x180003f99  jz      short loc_180003FF7
0x180003f9b  test    rsi, rsi
0x180003f9e  jz      short loc_180003FF7
0x180003fa0  mov     rax, [rsi]
0x180003fa3  lea     rdx, [rbp+var_20]
0x180003fa7  mov     rcx, rsi
0x180003faa  mov     rax, [rax+0D0h]
0x180003fb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fb6  mov     ebx, eax
0x180003fb8  test    eax, eax
0x180003fba  jns     short loc_180003FC7
0x180003fbc  mov     r8d, 1C3h
0x180003fc2  jmp     loc_180003F05
0x180003fc7  mov     r8, [rbp+var_20]; pv
0x180003fcb  lea     rdx, [rbp+rgIndices]; rgIndices
0x180003fcf  mov     rcx, [r13+18h]; psa
0x180003fd3  mov     [rbp+rgIndices], edi
0x180003fd6  mov     [rbp+var_24], r15d
0x180003fda  call    cs:__imp_SafeArrayPutElement
0x180003fe1  nop     dword ptr [rax+rax+00h]
0x180003fe6  mov     ebx, eax
0x180003fe8  test    eax, eax
0x180003fea  jns     short loc_18000401F
0x180003fec  mov     r8d, 1C9h
0x180003ff2  jmp     loc_180003F05
0x180003ff7  mov     r9d, 80004005h
0x180003ffd  mov     ebx, r9d
0x180004000  jmp     short loc_180003F8C
0x180004002  mov     r9d, 80004005h; int
0x180004008  mov     ecx, edi; Level
0x18000400a  mov     ebx, r9d
0x18000400d  mov     r8d, 1B0h; int
0x180004013  lea     rdx, aCnotificationS_5; "CNotification::SchdpUpdateParameter"
0x18000401a  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000401f  test    r14, r14
0x180004022  jz      short loc_180004033
0x180004024  mov     rax, [r14]
0x180004027  mov     rcx, r14
0x18000402a  mov     rax, [rax+10h]
0x18000402e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004033  test    rsi, rsi
0x180004036  jz      short loc_180004047
0x180004038  mov     rax, [rsi]
0x18000403b  mov     rcx, rsi
0x18000403e  mov     rax, [rax+10h]
0x180004042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004047  mov     rcx, [rbp+bstrString]; bstrString
0x18000404b  test    rcx, rcx
0x18000404e  jz      short loc_180004061
0x180004050  call    cs:__imp_SysFreeString
0x180004057  nop     dword ptr [rax+rax+00h]
0x18000405c  and     [rbp+bstrString], 0
0x180004061  mov     rcx, [rbp+var_20]; bstrString
0x180004065  test    rcx, rcx
0x180004068  jz      short loc_18000407B
0x18000406a  call    cs:__imp_SysFreeString
0x180004071  nop     dword ptr [rax+rax+00h]
0x180004076  and     [rbp+var_20], 0
0x18000407b  mov     rcx, [rbp+pv]; bstrString
0x18000407f  test    rcx, rcx
0x180004082  jz      short loc_180004090
0x180004084  call    cs:__imp_SysFreeString
0x18000408b  nop     dword ptr [rax+rax+00h]
0x180004090  lea     r11, [rsp+50h+var_s0]
0x180004095  mov     eax, ebx
0x180004097  mov     rbx, [r11+30h]
0x18000409b  mov     rsi, [r11+38h]
0x18000409f  mov     rsp, r11
0x1800040a2  pop     r15
0x1800040a4  pop     r14
0x1800040a6  pop     r13
0x1800040a8  pop     rdi
0x1800040a9  pop     rbp
0x1800040aa  retn
```
