# SdpBuildDisplayInformationXml(_SDIAG_DISPINFO *,int,IXMLDOMDocument2 * *)

- ea: `0x180002d20`
- end: `0x180003124`
- name: `?SdpBuildDisplayInformationXml@@YAJPEAU_SDIAG_DISPINFO@@HPEAPEAUIXMLDOMDocument2@@@Z`
- size: `1028`
- prototype: `__int64 __fastcall(struct _SDIAG_DISPINFO *, int, struct IXMLDOMDocument2 **)`
- caller_count: `5`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x180017b94`
- `0x18001955c`
- `0x18001c224`
- `0x18001f844`
- `0x180022570`

## callees

- `0x1800012a4`
- `0x180002d20`
- `0x18000571c`
- `0x180026fa0`
- `0x180028038`
- `0x1800280f8`
- `0x1800286a4`
- `0x1800290bc`
- `0x18002a010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180002ec3`
- `OLEAUT32!__imp_SysAllocString` at `0x180002fe6`
- `OLEAUT32!__imp_SysAllocString` at `0x180002ec3`
- `OLEAUT32!__imp_SysAllocString` at `0x180002fe6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800030f9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000310b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800030f9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000310b`

## string_xrefs

- `0x180002d74`: `SdpBuildDisplayInformationXml`
- `0x180002de7`: `SdpBuildDisplayInformationXml`
- `0x180002e28`: `SdpBuildDisplayInformationXml`
- `0x180002e9f`: `SdpBuildDisplayInformationXml`
- `0x180002fc2`: `SdpBuildDisplayInformationXml`
- `0x18000308a`: `SdpBuildDisplayInformationXml`
- `0x180002da2`: `<?xml version="1.0" encoding="utf-8"?><DisplayInformation><Name></Name><Description></Description></DisplayInformation>`

## pseudocode

```c
__int64 __fastcall SdpBuildDisplayInformationXml(struct _SDIAG_DISPINFO *a1, int a2, struct IXMLDOMDocument2 **a3)
{
  struct IXMLDOMNodeList *v4; // r15
  struct IXMLDOMNode *v5; // rsi
  OLECHAR *v6; // r13
  OLECHAR *v7; // r12
  int v8; // r8d
  unsigned int v9; // ebx
  int v10; // eax
  int v11; // r9d
  int v12; // r8d
  int ChildNodes; // eax
  int v14; // eax
  int v15; // r8d
  int v16; // eax
  const unsigned __int16 *v17; // rdx
  int v18; // eax
  OLECHAR *v19; // rax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  const unsigned __int16 *v23; // rdx
  int v24; // eax
  OLECHAR *v25; // rax
  int v26; // eax
  int v27; // eax
  struct IXMLDOMDocument2 *v28; // rcx
  struct IXMLDOMDocument2 *v30; // [rsp+20h] [rbp-38h] BYREF
  struct IXMLDOMNodeList *v31; // [rsp+28h] [rbp-30h] BYREF
  OLECHAR *psz; // [rsp+30h] [rbp-28h] BYREF
  OLECHAR *v33; // [rsp+38h] [rbp-20h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-18h]
  BSTR v35; // [rsp+48h] [rbp-10h]
  unsigned int v36; // [rsp+A0h] [rbp+48h] BYREF
  int v37; // [rsp+A8h] [rbp+50h]
  struct IXMLDOMDocument2 **v38; // [rsp+B0h] [rbp+58h]
  struct IXMLDOMNode *v39; // [rsp+B8h] [rbp+60h] BYREF

  v38 = a3;
  v37 = a2;
  v30 = 0;
  v31 = 0;
  v4 = 0;
  v39 = 0;
  v5 = 0;
  psz = 0;
  v6 = 0;
  v33 = 0;
  v7 = 0;
  if ( !a1 )
  {
    v8 = 534;
LABEL_3:
    v9 = -2147024809;
    SdpDebugTrace(1u, L"SdpBuildDisplayInformationXml", v8, -2147024809);
    return v9;
  }
  if ( !a3 )
  {
    v8 = 535;
    goto LABEL_3;
  }
  bstrString = 0;
  v35 = 0;
  v10 = SdpXmlCreate(
          (OLECHAR *)L"<?xml version=\"1.0\" encoding=\"utf-8\"?><DisplayInformation><Name></Name><Description></Descripti"
                      "on></DisplayInformation>",
          &v30);
  v9 = v10;
  if ( v10 < 0 )
  {
    v11 = v10;
    v12 = 538;
LABEL_47:
    SdpDebugTrace(1u, L"SdpBuildDisplayInformationXml", v12, v11);
    goto LABEL_48;
  }
  ChildNodes = SdpXmlGetChildNodes(v30, 0, &v31, &v36);
  v9 = ChildNodes;
  if ( ChildNodes >= 0 )
  {
    v4 = v31;
    v14 = SdpXmlNextNode(v31, &v39);
    v9 = v14;
    if ( v14 < 0 )
    {
      v15 = 548;
LABEL_12:
      SdpDebugTrace(1u, L"SdpBuildDisplayInformationXml", v15, v14);
      v5 = v39;
      goto LABEL_48;
    }
    v5 = v39;
    v16 = SdpXmlCheckNode(v39, L"Name");
    v9 = v16;
    if ( v16 < 0 )
    {
      v11 = v16;
LABEL_46:
      v12 = 549;
      goto LABEL_47;
    }
    if ( v16 == 1 || !v5 )
    {
      v11 = -2147467259;
      v9 = -2147467259;
      goto LABEL_46;
    }
    v17 = *(const unsigned __int16 **)a1;
    if ( v37 )
    {
      v21 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, const unsigned __int16 *))v5->lpVtbl->put_text)(v5, v17);
      v9 = v21;
      if ( v21 < 0 )
      {
        v11 = v21;
        v12 = 565;
        goto LABEL_47;
      }
    }
    else
    {
      v18 = SdpSubstituteParamSet(&psz, v17, (struct _SDIAG_DISPINFO *)((char *)a1 + 16));
      v9 = v18;
      if ( v18 < 0 )
      {
        SdpDebugTrace(1u, L"SdpBuildDisplayInformationXml", 555, v18);
        v6 = psz;
        goto LABEL_48;
      }
      v6 = psz;
      v19 = SysAllocString(psz);
      bstrString = v19;
      if ( !v19 )
      {
        v12 = 558;
LABEL_22:
        v11 = -2147024882;
        v9 = -2147024882;
        goto LABEL_47;
      }
      v20 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, OLECHAR *))v5->lpVtbl->put_text)(v5, v19);
      v9 = v20;
      if ( v20 < 0 )
      {
        v11 = v20;
        v12 = 561;
        goto LABEL_47;
      }
    }
    ((void (__fastcall *)(struct IXMLDOMNode *))v5->lpVtbl->Release)(v5);
    v39 = 0;
    v14 = SdpXmlNextNode(v4, &v39);
    v9 = v14;
    if ( v14 < 0 )
    {
      v15 = 574;
      goto LABEL_12;
    }
    v5 = v39;
    v22 = SdpXmlCheckNode(v39, L"Description");
    v9 = v22;
    if ( v22 >= 0 )
    {
      if ( v22 != 1 && v5 )
      {
        v23 = (const unsigned __int16 *)*((_QWORD *)a1 + 1);
        if ( v37 )
        {
          v27 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, const unsigned __int16 *))v5->lpVtbl->put_text)(v5, v23);
          v9 = v27;
          if ( v27 < 0 )
          {
            v11 = v27;
            v12 = 591;
            goto LABEL_47;
          }
        }
        else
        {
          v24 = SdpSubstituteParamSet(&v33, v23, (struct _SDIAG_DISPINFO *)((char *)a1 + 16));
          v9 = v24;
          if ( v24 < 0 )
          {
            SdpDebugTrace(1u, L"SdpBuildDisplayInformationXml", 581, v24);
            v7 = v33;
            goto LABEL_48;
          }
          v7 = v33;
          v25 = SysAllocString(v33);
          v35 = v25;
          if ( !v25 )
          {
            v12 = 584;
            goto LABEL_22;
          }
          v26 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, OLECHAR *))v5->lpVtbl->put_text)(v5, v25);
          v9 = v26;
          if ( v26 < 0 )
          {
            v11 = v26;
            v12 = 587;
            goto LABEL_47;
          }
        }
        v28 = v30;
        *v38 = v30;
        ((void (__fastcall *)(struct IXMLDOMDocument2 *))v28->lpVtbl->AddRef)(v28);
        goto LABEL_48;
      }
      v11 = -2147467259;
      v9 = -2147467259;
    }
    else
    {
      v11 = v22;
    }
    v12 = 575;
    goto LABEL_47;
  }
  SdpDebugTrace(1u, L"SdpBuildDisplayInformationXml", 541, ChildNodes);
  v4 = v31;
LABEL_48:
  if ( v30 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v30->lpVtbl->Release)(v30);
  if ( v4 )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v4->lpVtbl->Release)(v4);
  if ( v5 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v5->lpVtbl->Release)(v5);
  if ( v6 )
    operator delete(v6);
  if ( v7 )
    operator delete(v7);
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v35 )
    SysFreeString(v35);
  return v9;
}

```

## disassembly

```asm
0x180002d20  mov     [rsp-40h+arg_10], r8
0x180002d25  mov     [rsp-40h+arg_8], edx
0x180002d29  push    rbp
0x180002d2a  push    rbx
0x180002d2b  push    rsi
0x180002d2c  push    rdi
0x180002d2d  push    r12
0x180002d2f  push    r13
0x180002d31  push    r14
0x180002d33  push    r15
0x180002d35  mov     rbp, rsp
0x180002d38  sub     rsp, 58h
0x180002d3c  xor     edi, edi
0x180002d3e  mov     rax, r8
0x180002d41  mov     [rbp+var_38], rdi
0x180002d45  mov     r14, rcx
0x180002d48  mov     [rbp+var_30], rdi
0x180002d4c  mov     r15d, edi
0x180002d4f  mov     [rbp+arg_18], rdi
0x180002d53  mov     esi, edi
0x180002d55  mov     [rbp+psz], rdi
0x180002d59  mov     r13d, edi
0x180002d5c  mov     [rbp+var_20], rdi
0x180002d60  mov     r12d, edi
0x180002d63  test    rcx, rcx
0x180002d66  jnz     short loc_180002D8D
0x180002d68  mov     r8d, 216h; int
0x180002d6e  mov     r9d, 80070057h; int
0x180002d74  lea     rdx, aSdpbuilddispla; "SdpBuildDisplayInformationXml"
0x180002d7b  mov     ecx, 1; Level
0x180002d80  mov     ebx, r9d
0x180002d83  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180002d88  jmp     loc_180003111
0x180002d8d  test    rax, rax
0x180002d90  jnz     short loc_180002D9A
0x180002d92  mov     r8d, 217h
0x180002d98  jmp     short loc_180002D6E
0x180002d9a  lea     rdx, [rbp+var_38]; struct IXMLDOMDocument2 **
0x180002d9e  mov     [rbp+bstrString], rdi
0x180002da2  lea     rcx, aXmlVersion10En_14; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x180002da9  mov     [rbp+var_10], rdi
0x180002dad  call    ?SdpXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; SdpXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x180002db2  mov     ebx, eax
0x180002db4  test    eax, eax
0x180002db6  jns     short loc_180002DCB
0x180002db8  mov     r9d, eax
0x180002dbb  mov     r8d, 21Ah
0x180002dc1  mov     ecx, 1
0x180002dc6  jmp     loc_18000308A
0x180002dcb  mov     rcx, [rbp+var_38]; struct IXMLDOMDocument2 *
0x180002dcf  lea     r9, [rbp+arg_0]; unsigned int *
0x180002dd3  lea     r8, [rbp+var_30]; struct IXMLDOMNodeList **
0x180002dd7  xor     edx, edx; struct IXMLDOMNode *
0x180002dd9  call    ?SdpXmlGetChildNodes@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@PEAK@Z; SdpXmlGetChildNodes(IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *,ulong *)
0x180002dde  mov     ebx, eax
0x180002de0  test    eax, eax
0x180002de2  jns     short loc_180002E07
0x180002de4  mov     r9d, eax; int
0x180002de7  lea     rdx, aSdpbuilddispla; "SdpBuildDisplayInformationXml"
0x180002dee  mov     r8d, 21Dh; int
0x180002df4  mov     ecx, 1; Level
0x180002df9  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180002dfe  mov     r15, [rbp+var_30]
0x180002e02  jmp     loc_180003096
0x180002e07  mov     r15, [rbp+var_30]
0x180002e0b  lea     rdx, [rbp+arg_18]; struct IXMLDOMNode **
0x180002e0f  mov     rcx, r15; struct IXMLDOMNodeList *
0x180002e12  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x180002e17  mov     ebx, eax
0x180002e19  test    eax, eax
0x180002e1b  jns     short loc_180002E40
0x180002e1d  mov     r8d, 224h; int
0x180002e23  mov     ecx, 1; Level
0x180002e28  lea     rdx, aSdpbuilddispla; "SdpBuildDisplayInformationXml"
0x180002e2f  mov     r9d, eax; int
0x180002e32  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180002e37  mov     rsi, [rbp+arg_18]
0x180002e3b  jmp     loc_180003096
0x180002e40  mov     rsi, [rbp+arg_18]
0x180002e44  lea     rdx, aName; "Name"
0x180002e4b  mov     rcx, rsi; struct IXMLDOMNode *
0x180002e4e  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x180002e53  mov     ebx, eax
0x180002e55  test    eax, eax
0x180002e57  jns     short loc_180002E66
0x180002e59  mov     r9d, eax
0x180002e5c  mov     ecx, 1
0x180002e61  jmp     loc_180003084
0x180002e66  mov     edi, 1
0x180002e6b  cmp     eax, edi
0x180002e6d  jz      loc_180003079
0x180002e73  test    rsi, rsi
0x180002e76  jz      loc_180003079
0x180002e7c  mov     rdx, [r14]; unsigned __int16 *
0x180002e7f  cmp     [rbp+arg_8], r12d
0x180002e83  jnz     loc_180002F11
0x180002e89  lea     r8, [r14+10h]; struct _SDIAG_PARAMSET *
0x180002e8d  lea     rcx, [rbp+psz]; unsigned __int16 **
0x180002e91  call    ?SdpSubstituteParamSet@@YAJPEAPEAGPEBGPEAU_SDIAG_PARAMSET@@@Z; SdpSubstituteParamSet(ushort * *,ushort const *,_SDIAG_PARAMSET *)
0x180002e96  mov     ebx, eax
0x180002e98  test    eax, eax
0x180002e9a  jns     short loc_180002EBC
0x180002e9c  mov     r9d, eax; int
0x180002e9f  lea     rdx, aSdpbuilddispla; "SdpBuildDisplayInformationXml"
0x180002ea6  mov     r8d, 22Bh; int
0x180002eac  mov     ecx, edi; Level
0x180002eae  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180002eb3  mov     r13, [rbp+psz]
0x180002eb7  jmp     loc_180003096
0x180002ebc  mov     r13, [rbp+psz]
0x180002ec0  mov     rcx, r13; psz
0x180002ec3  call    cs:__imp_SysAllocString
0x180002ec9  mov     [rbp+bstrString], rax
0x180002ecd  mov     rcx, rax
0x180002ed0  test    rax, rax
0x180002ed3  jnz     short loc_180002EEB
0x180002ed5  mov     r8d, 22Eh
0x180002edb  mov     r9d, 8007000Eh
0x180002ee1  mov     ebx, r9d
0x180002ee4  mov     ecx, edi
0x180002ee6  jmp     loc_18000308A
0x180002eeb  mov     rax, [rsi]
0x180002eee  mov     rdx, rcx
0x180002ef1  mov     rcx, rsi
0x180002ef4  mov     rax, [rax+0D8h]
0x180002efb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f00  mov     ebx, eax
0x180002f02  test    eax, eax
0x180002f04  jns     short loc_180002F34
0x180002f06  mov     r9d, eax
0x180002f09  mov     r8d, 231h
0x180002f0f  jmp     short loc_180002EE4
0x180002f11  mov     rax, [rsi]
0x180002f14  mov     rcx, rsi
0x180002f17  mov     rax, [rax+0D8h]
0x180002f1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f23  mov     ebx, eax
0x180002f25  test    eax, eax
0x180002f27  jns     short loc_180002F34
0x180002f29  mov     r9d, eax
0x180002f2c  mov     r8d, 235h
0x180002f32  jmp     short loc_180002EE4
0x180002f34  mov     rax, [rsi]
0x180002f37  mov     rcx, rsi
0x180002f3a  mov     rax, [rax+10h]
0x180002f3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f43  lea     rdx, [rbp+arg_18]; struct IXMLDOMNode **
0x180002f47  mov     [rbp+arg_18], r12
0x180002f4b  mov     rcx, r15; struct IXMLDOMNodeList *
0x180002f4e  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x180002f53  mov     ebx, eax
0x180002f55  test    eax, eax
0x180002f57  jns     short loc_180002F66
0x180002f59  mov     r8d, 23Eh
0x180002f5f  mov     ecx, edi
0x180002f61  jmp     loc_180002E28
0x180002f66  mov     rsi, [rbp+arg_18]
0x180002f6a  lea     rdx, aDescription; "Description"
0x180002f71  mov     rcx, rsi; struct IXMLDOMNode *
0x180002f74  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x180002f79  mov     ebx, eax
0x180002f7b  test    eax, eax
0x180002f7d  jns     short loc_180002F8D
0x180002f7f  mov     r9d, eax
0x180002f82  mov     r8d, 23Fh
0x180002f88  jmp     loc_180002EE4
0x180002f8d  cmp     eax, edi
0x180002f8f  jz      loc_18000306B
0x180002f95  test    rsi, rsi
0x180002f98  jz      loc_18000306B
0x180002f9e  mov     rdx, [r14+8]; unsigned __int16 *
0x180002fa2  cmp     [rbp+arg_8], r12d
0x180002fa6  jnz     loc_18000302C
0x180002fac  lea     r8, [r14+10h]; struct _SDIAG_PARAMSET *
0x180002fb0  lea     rcx, [rbp+var_20]; unsigned __int16 **
0x180002fb4  call    ?SdpSubstituteParamSet@@YAJPEAPEAGPEBGPEAU_SDIAG_PARAMSET@@@Z; SdpSubstituteParamSet(ushort * *,ushort const *,_SDIAG_PARAMSET *)
0x180002fb9  mov     ebx, eax
0x180002fbb  test    eax, eax
0x180002fbd  jns     short loc_180002FDF
0x180002fbf  mov     r9d, eax; int
0x180002fc2  lea     rdx, aSdpbuilddispla; "SdpBuildDisplayInformationXml"
0x180002fc9  mov     r8d, 245h; int
0x180002fcf  mov     ecx, edi; Level
0x180002fd1  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180002fd6  mov     r12, [rbp+var_20]
0x180002fda  jmp     loc_180003096
0x180002fdf  mov     r12, [rbp+var_20]
0x180002fe3  mov     rcx, r12; psz
0x180002fe6  call    cs:__imp_SysAllocString
0x180002fec  mov     [rbp+var_10], rax
0x180002ff0  mov     rcx, rax
0x180002ff3  test    rax, rax
0x180002ff6  jnz     short loc_180003003
0x180002ff8  mov     r8d, 248h
0x180002ffe  jmp     loc_180002EDB
0x180003003  mov     rax, [rsi]
0x180003006  mov     rdx, rcx
0x180003009  mov     rcx, rsi
0x18000300c  mov     rax, [rax+0D8h]
0x180003013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003018  mov     ebx, eax
0x18000301a  test    eax, eax
0x18000301c  jns     short loc_180003052
0x18000301e  mov     r9d, eax
0x180003021  mov     r8d, 24Bh
0x180003027  jmp     loc_180002EE4
0x18000302c  mov     rax, [rsi]
0x18000302f  mov     rcx, rsi
0x180003032  mov     rax, [rax+0D8h]
0x180003039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000303e  mov     ebx, eax
0x180003040  test    eax, eax
0x180003042  jns     short loc_180003052
0x180003044  mov     r9d, eax
0x180003047  mov     r8d, 24Fh
0x18000304d  jmp     loc_180002EE4
0x180003052  mov     rcx, [rbp+var_38]
0x180003056  mov     rax, [rbp+arg_10]
0x18000305a  mov     [rax], rcx
0x18000305d  mov     rax, [rcx]
0x180003060  mov     rax, [rax+8]
0x180003064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003069  jmp     short loc_180003096
0x18000306b  mov     r9d, 80004005h
0x180003071  mov     ebx, r9d
0x180003074  jmp     loc_180002F82
0x180003079  mov     r9d, 80004005h; int
0x18000307f  mov     ecx, edi; Level
0x180003081  mov     ebx, r9d
0x180003084  mov     r8d, 225h; int
0x18000308a  lea     rdx, aSdpbuilddispla; "SdpBuildDisplayInformationXml"
0x180003091  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180003096  mov     rcx, [rbp+var_38]
0x18000309a  test    rcx, rcx
0x18000309d  jz      short loc_1800030AB
0x18000309f  mov     rax, [rcx]
0x1800030a2  mov     rax, [rax+10h]
0x1800030a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030ab  test    r15, r15
0x1800030ae  jz      short loc_1800030BF
0x1800030b0  mov     rax, [r15]
0x1800030b3  mov     rcx, r15
0x1800030b6  mov     rax, [rax+10h]
0x1800030ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030bf  test    rsi, rsi
0x1800030c2  jz      short loc_1800030D3
0x1800030c4  mov     rax, [rsi]
0x1800030c7  mov     rcx, rsi
0x1800030ca  mov     rax, [rax+10h]
0x1800030ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030d3  test    r13, r13
0x1800030d6  jz      short loc_1800030E0
0x1800030d8  mov     rcx, r13; Block
0x1800030db  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800030e0  test    r12, r12
0x1800030e3  jz      short loc_1800030ED
0x1800030e5  mov     rcx, r12; Block
0x1800030e8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800030ed  mov     rax, [rbp+bstrString]
0x1800030f1  test    rax, rax
0x1800030f4  jz      short loc_1800030FF
0x1800030f6  mov     rcx, rax; bstrString
0x1800030f9  call    cs:__imp_SysFreeString
0x1800030ff  mov     rax, [rbp+var_10]
0x180003103  test    rax, rax
0x180003106  jz      short loc_180003111
0x180003108  mov     rcx, rax; bstrString
0x18000310b  call    cs:__imp_SysFreeString
0x180003111  mov     eax, ebx
0x180003113  add     rsp, 58h
0x180003117  pop     r15
0x180003119  pop     r14
0x18000311b  pop     r13
0x18000311d  pop     r12
0x18000311f  pop     rdi
0x180003120  pop     rsi
0x180003121  pop     rbx
0x180003122  pop     rbp
0x180003123  retn
```
