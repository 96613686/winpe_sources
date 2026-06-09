# Script::ParseScriptXml(IXMLDOMNode *)

- ea: `0x18001dc28`
- end: `0x18001e18c`
- name: `?ParseScriptXml@Script@@AEAAJPEAUIXMLDOMNode@@@Z`
- size: `1380`
- prototype: `__int64 __fastcall(Script *__hidden this, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18001db84`

## callees

- `0x1800012a4`
- `0x1800020f8`
- `0x180003814`
- `0x1800040e8`
- `0x18001dc28`
- `0x18001e808`
- `0x18001ec38`
- `0x180026fa0`
- `0x18002758c`
- `0x180028038`
- `0x1800286a4`
- `0x1800290bc`
- `0x18002a010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001e045`
- `KERNEL32!GetLastError` at `0x18001e045`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e148`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e15b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e148`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e15b`

## string_xrefs

- `0x18001e0a8`: `ExtensionPoint`
- `0x18001dc72`: `Script::ParseScriptXml`
- `0x18001dd06`: `Script::ParseScriptXml`
- `0x18001dfdc`: `Script::ParseScriptXml`
- `0x18001e10a`: `Script::ParseScriptXml`

## pseudocode

```c
__int64 __fastcall Script::ParseScriptXml(Script *this, struct IXMLDOMNode *a2)
{
  struct IXMLDOMNode *v3; // rsi
  unsigned __int16 *v4; // r15
  signed int v5; // ebx
  int ChildNodes; // eax
  struct IXMLDOMNodeList *v7; // r12
  int v8; // r8d
  int v9; // r9d
  int v10; // eax
  int v11; // r8d
  int IsSubDirectory; // eax
  int PackagePath; // eax
  signed int LastError; // eax
  BSTR bstrString; // [rsp+20h] [rbp-20h] BYREF
  BSTR v17; // [rsp+28h] [rbp-18h] BYREF
  unsigned __int16 *v18; // [rsp+30h] [rbp-10h] BYREF
  struct IXMLDOMNodeList *v19; // [rsp+38h] [rbp-8h] BYREF
  unsigned int v20; // [rsp+88h] [rbp+48h] BYREF
  int v21; // [rsp+90h] [rbp+50h] BYREF
  struct IXMLDOMNode *v22; // [rsp+98h] [rbp+58h] BYREF

  v19 = 0;
  v3 = 0;
  v22 = 0;
  v4 = 0;
  bstrString = 0;
  v20 = 0;
  v18 = 0;
  v17 = 0;
  v21 = 0;
  if ( !a2 )
  {
    v5 = -2147024809;
    SdpDebugTrace(1u, L"Script::ParseScriptXml", 412, -2147024809);
    goto LABEL_87;
  }
  ChildNodes = SdpXmlGetChildNodes(0, a2, &v19, &v20);
  v7 = v19;
  v5 = ChildNodes;
  if ( ChildNodes < 0 )
  {
    v8 = 415;
LABEL_5:
    v9 = ChildNodes;
LABEL_82:
    SdpDebugTrace(1u, L"Script::ParseScriptXml", v8, v9);
    goto LABEL_83;
  }
  if ( v20 )
  {
    if ( v20 < 6 )
    {
      v9 = -2147024809;
      v8 = 428;
LABEL_81:
      v5 = v9;
      goto LABEL_82;
    }
    v10 = SdpXmlNextNode(v19, &v22);
    v5 = v10;
    if ( v10 < 0 )
    {
      v11 = 436;
LABEL_12:
      SdpDebugTrace(1u, L"Script::ParseScriptXml", v11, v10);
      v3 = v22;
      goto LABEL_83;
    }
    v3 = v22;
    ChildNodes = SdpXmlCheckNode(v22, L"Parameters");
    v5 = ChildNodes;
    if ( ChildNodes < 0 )
    {
      v8 = 437;
      goto LABEL_5;
    }
    if ( ChildNodes == 1 || !v3 )
    {
      v8 = 437;
    }
    else
    {
      IsSubDirectory = SdpParseParameters(v3, (Script *)((char *)this + 24));
      v5 = IsSubDirectory;
      if ( IsSubDirectory < 0 )
      {
        v8 = 441;
LABEL_19:
        v9 = IsSubDirectory;
        goto LABEL_82;
      }
      ((void (__fastcall *)(struct IXMLDOMNode *))v3->lpVtbl->Release)(v3);
      v22 = 0;
      v10 = SdpXmlNextNode(v7, &v22);
      v5 = v10;
      if ( v10 < 0 )
      {
        v11 = 449;
        goto LABEL_12;
      }
      v3 = v22;
      IsSubDirectory = SdpXmlCheckNode(v22, L"ProcessArchitecture");
      v5 = IsSubDirectory;
      if ( IsSubDirectory < 0 )
      {
        v8 = 450;
        goto LABEL_19;
      }
      if ( IsSubDirectory == 1 || !v3 )
      {
        v8 = 450;
      }
      else
      {
        IsSubDirectory = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))v3->lpVtbl->get_text)(v3, &v17);
        v5 = IsSubDirectory;
        if ( IsSubDirectory < 0 )
        {
          v8 = 453;
          goto LABEL_19;
        }
        IsSubDirectory = Settings::set_RequiredArchitecture(*(Settings **)this, v17);
        v5 = IsSubDirectory;
        if ( IsSubDirectory < 0 )
        {
          v8 = 456;
          goto LABEL_19;
        }
        ((void (__fastcall *)(struct IXMLDOMNode *))v3->lpVtbl->Release)(v3);
        v22 = 0;
        v10 = SdpXmlNextNode(v7, &v22);
        v5 = v10;
        if ( v10 < 0 )
        {
          v11 = 468;
          goto LABEL_12;
        }
        v3 = v22;
        IsSubDirectory = SdpXmlCheckNode(v22, L"RequiresElevation");
        v5 = IsSubDirectory;
        if ( IsSubDirectory < 0 )
        {
          v8 = 469;
          goto LABEL_19;
        }
        if ( IsSubDirectory == 1 || !v3 )
        {
          v8 = 469;
        }
        else
        {
          IsSubDirectory = SdpParseBooleanNode(v3, (int *)this + 4);
          v5 = IsSubDirectory;
          if ( IsSubDirectory < 0 )
          {
            v8 = 472;
            goto LABEL_19;
          }
          ((void (__fastcall *)(struct IXMLDOMNode *))v3->lpVtbl->Release)(v3);
          v22 = 0;
          v10 = SdpXmlNextNode(v7, &v22);
          v5 = v10;
          if ( v10 < 0 )
          {
            v11 = 480;
            goto LABEL_12;
          }
          v3 = v22;
          IsSubDirectory = SdpXmlCheckNode(v22, L"RequiresInteractivity");
          v5 = IsSubDirectory;
          if ( IsSubDirectory < 0 )
          {
            v8 = 481;
            goto LABEL_19;
          }
          if ( IsSubDirectory == 1 || !v3 )
          {
            v8 = 481;
          }
          else
          {
            IsSubDirectory = SdpParseBooleanNode(v3, (int *)this + 10);
            v5 = IsSubDirectory;
            if ( IsSubDirectory < 0 )
            {
              v8 = 484;
              goto LABEL_19;
            }
            ((void (__fastcall *)(struct IXMLDOMNode *))v3->lpVtbl->Release)(v3);
            v22 = 0;
            v10 = SdpXmlNextNode(v7, &v22);
            v5 = v10;
            if ( v10 < 0 )
            {
              v11 = 492;
              goto LABEL_12;
            }
            v3 = v22;
            IsSubDirectory = SdpXmlCheckNode(v22, L"FileName");
            v5 = IsSubDirectory;
            if ( IsSubDirectory < 0 )
            {
              v8 = 493;
              goto LABEL_19;
            }
            if ( IsSubDirectory == 1 || !v3 )
            {
              v8 = 493;
            }
            else
            {
              IsSubDirectory = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))v3->lpVtbl->get_text)(
                                 v3,
                                 &bstrString);
              v5 = IsSubDirectory;
              if ( IsSubDirectory < 0 )
              {
                v8 = 496;
                goto LABEL_19;
              }
              if ( !*(_QWORD *)this )
              {
                v5 = -2147467261;
                v8 = 498;
                v9 = -2147467261;
                goto LABEL_82;
              }
              PackagePath = Settings::get_PackagePath(*(Settings **)this, &v18);
              v5 = PackagePath;
              if ( PackagePath < 0 )
              {
                SdpDebugTrace(1u, L"Script::ParseScriptXml", 501, PackagePath);
                v4 = v18;
                goto LABEL_83;
              }
              v4 = v18;
              IsSubDirectory = SdpBuildPath(v18, bstrString, (unsigned __int16 **)this + 1);
              v5 = IsSubDirectory;
              if ( IsSubDirectory < 0 )
              {
                v8 = 504;
                goto LABEL_19;
              }
              IsSubDirectory = SdpIsSubDirectory(v4, *((const unsigned __int16 **)this + 1), &v21);
              v5 = IsSubDirectory;
              if ( IsSubDirectory < 0 )
              {
                v8 = 511;
                goto LABEL_19;
              }
              if ( !v21 )
              {
                LastError = GetLastError();
                v5 = LastError;
                if ( LastError > 0 )
                  v5 = (unsigned __int16)LastError | 0x80070000;
                v8 = 512;
                if ( v5 >= 0 )
                  v5 = -2147467259;
                v9 = v5;
                goto LABEL_82;
              }
              ((void (__fastcall *)(struct IXMLDOMNode *))v3->lpVtbl->Release)(v3);
              v22 = 0;
              v10 = SdpXmlNextNode(v7, &v22);
              v5 = v10;
              if ( v10 < 0 )
              {
                v11 = 520;
                goto LABEL_12;
              }
              v3 = v22;
              IsSubDirectory = SdpXmlCheckNode(v22, L"ExtensionPoint");
              v5 = IsSubDirectory;
              if ( IsSubDirectory < 0 )
              {
                v8 = 521;
                goto LABEL_19;
              }
              if ( IsSubDirectory != 1 && v3 )
                goto LABEL_83;
              v8 = 521;
            }
          }
        }
      }
    }
    v9 = -2147467259;
    goto LABEL_81;
  }
  v5 = 1;
LABEL_83:
  if ( v7 )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v7->lpVtbl->Release)(v7);
  if ( v3 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v3->lpVtbl->Release)(v3);
LABEL_87:
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v17 )
  {
    SysFreeString(v17);
    v17 = 0;
  }
  if ( v4 )
    operator delete(v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001dc28  mov     [rsp-38h+arg_0], rbx
0x18001dc2d  push    rbp
0x18001dc2e  push    rsi
0x18001dc2f  push    rdi
0x18001dc30  push    r12
0x18001dc32  push    r13
0x18001dc34  push    r14
0x18001dc36  push    r15
0x18001dc38  mov     rbp, rsp
0x18001dc3b  sub     rsp, 40h
0x18001dc3f  xor     r13d, r13d
0x18001dc42  mov     r14, rcx
0x18001dc45  mov     [rbp+var_8], r13
0x18001dc49  mov     esi, r13d
0x18001dc4c  mov     [rbp+arg_18], r13
0x18001dc50  mov     r15d, r13d
0x18001dc53  mov     [rbp+bstrString], r13
0x18001dc57  mov     [rbp+arg_8], r13d
0x18001dc5b  mov     [rbp+var_10], r13
0x18001dc5f  mov     [rbp+var_18], r13
0x18001dc63  mov     [rbp+arg_10], r13d
0x18001dc67  test    rdx, rdx
0x18001dc6a  jnz     short loc_18001DC90
0x18001dc6c  mov     r9d, 80070057h; int
0x18001dc72  lea     rdx, aScriptParsescr; "Script::ParseScriptXml"
0x18001dc79  mov     r8d, 19Ch; int
0x18001dc7f  lea     ecx, [r13+1]; Level
0x18001dc83  mov     ebx, r9d
0x18001dc86  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001dc8b  jmp     loc_18001E13F
0x18001dc90  lea     r9, [rbp+arg_8]; unsigned int *
0x18001dc94  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x18001dc96  lea     r8, [rbp+var_8]; struct IXMLDOMNodeList **
0x18001dc9a  call    ?SdpXmlGetChildNodes@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@PEAK@Z; SdpXmlGetChildNodes(IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *,ulong *)
0x18001dc9f  mov     r12, [rbp+var_8]
0x18001dca3  mov     ebx, eax
0x18001dca5  test    eax, eax
0x18001dca7  jns     short loc_18001DCBC
0x18001dca9  mov     r8d, 19Fh
0x18001dcaf  mov     r9d, eax
0x18001dcb2  mov     ecx, 1
0x18001dcb7  jmp     loc_18001E10A
0x18001dcbc  mov     eax, [rbp+arg_8]
0x18001dcbf  test    eax, eax
0x18001dcc1  jnz     short loc_18001DCCB
0x18001dcc3  lea     ebx, [rax+1]
0x18001dcc6  jmp     loc_18001E116
0x18001dccb  cmp     eax, 6
0x18001dcce  jnb     short loc_18001DCE6
0x18001dcd0  mov     r9d, 80070057h
0x18001dcd6  mov     r8d, 1ACh
0x18001dcdc  mov     ecx, 1
0x18001dce1  jmp     loc_18001E107
0x18001dce6  lea     rdx, [rbp+arg_18]; struct IXMLDOMNode **
0x18001dcea  mov     rcx, r12; struct IXMLDOMNodeList *
0x18001dced  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x18001dcf2  mov     ebx, eax
0x18001dcf4  test    eax, eax
0x18001dcf6  jns     short loc_18001DD1B
0x18001dcf8  mov     r8d, 1B4h; int
0x18001dcfe  mov     ecx, 1; Level
0x18001dd03  mov     r9d, eax; int
0x18001dd06  lea     rdx, aScriptParsescr; "Script::ParseScriptXml"
0x18001dd0d  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001dd12  mov     rsi, [rbp+arg_18]
0x18001dd16  jmp     loc_18001E116
0x18001dd1b  mov     rsi, [rbp+arg_18]
0x18001dd1f  lea     rdx, aParameters; "Parameters"
0x18001dd26  mov     rcx, rsi; struct IXMLDOMNode *
0x18001dd29  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x18001dd2e  mov     ebx, eax
0x18001dd30  test    eax, eax
0x18001dd32  jns     short loc_18001DD3F
0x18001dd34  mov     r8d, 1B5h
0x18001dd3a  jmp     loc_18001DCAF
0x18001dd3f  mov     edi, 1
0x18001dd44  cmp     eax, edi
0x18001dd46  jz      loc_18001E0F9
0x18001dd4c  test    rsi, rsi
0x18001dd4f  jz      loc_18001E0F9
0x18001dd55  lea     rdx, [r14+18h]; struct _SDIAG_PARAMSET *
0x18001dd59  mov     rcx, rsi; struct IXMLDOMNode *
0x18001dd5c  call    ?SdpParseParameters@@YAJPEAUIXMLDOMNode@@PEAU_SDIAG_PARAMSET@@@Z; SdpParseParameters(IXMLDOMNode *,_SDIAG_PARAMSET *)
0x18001dd61  mov     ebx, eax
0x18001dd63  test    eax, eax
0x18001dd65  jns     short loc_18001DD77
0x18001dd67  mov     r8d, 1B9h
0x18001dd6d  mov     r9d, eax
0x18001dd70  mov     ecx, edi
0x18001dd72  jmp     loc_18001E10A
0x18001dd77  mov     rax, [rsi]
0x18001dd7a  mov     rcx, rsi
0x18001dd7d  mov     rax, [rax+10h]
0x18001dd81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd86  lea     rdx, [rbp+arg_18]; struct IXMLDOMNode **
0x18001dd8a  mov     [rbp+arg_18], r13
0x18001dd8e  mov     rcx, r12; struct IXMLDOMNodeList *
0x18001dd91  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x18001dd96  mov     ebx, eax
0x18001dd98  test    eax, eax
0x18001dd9a  jns     short loc_18001DDA9
0x18001dd9c  mov     r8d, 1C1h
0x18001dda2  mov     ecx, edi
0x18001dda4  jmp     loc_18001DD03
0x18001dda9  mov     rsi, [rbp+arg_18]
0x18001ddad  lea     rdx, aProcessarchite; "ProcessArchitecture"
0x18001ddb4  mov     rcx, rsi; struct IXMLDOMNode *
0x18001ddb7  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x18001ddbc  mov     ebx, eax
0x18001ddbe  test    eax, eax
0x18001ddc0  jns     short loc_18001DDCA
0x18001ddc2  mov     r8d, 1C2h
0x18001ddc8  jmp     short loc_18001DD6D
0x18001ddca  cmp     eax, edi
0x18001ddcc  jz      loc_18001E0F1
0x18001ddd2  test    rsi, rsi
0x18001ddd5  jz      loc_18001E0F1
0x18001dddb  mov     rax, [rsi]
0x18001ddde  lea     rdx, [rbp+var_18]
0x18001dde2  mov     rcx, rsi
0x18001dde5  mov     rax, [rax+0D0h]
0x18001ddec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ddf1  mov     ebx, eax
0x18001ddf3  test    eax, eax
0x18001ddf5  jns     short loc_18001DE02
0x18001ddf7  mov     r8d, 1C5h
0x18001ddfd  jmp     loc_18001DD6D
0x18001de02  mov     rdx, [rbp+var_18]; unsigned __int16 *
0x18001de06  mov     rcx, [r14]; this
0x18001de09  call    ?set_RequiredArchitecture@Settings@@QEAAJPEAG@Z; Settings::set_RequiredArchitecture(ushort *)
0x18001de0e  mov     ebx, eax
0x18001de10  test    eax, eax
0x18001de12  jns     short loc_18001DE1F
0x18001de14  mov     r8d, 1C8h
0x18001de1a  jmp     loc_18001DD6D
0x18001de1f  mov     rax, [rsi]
0x18001de22  mov     rcx, rsi
0x18001de25  mov     rax, [rax+10h]
0x18001de29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de2e  lea     rdx, [rbp+arg_18]; struct IXMLDOMNode **
0x18001de32  mov     [rbp+arg_18], r13
0x18001de36  mov     rcx, r12; struct IXMLDOMNodeList *
0x18001de39  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x18001de3e  mov     ebx, eax
0x18001de40  test    eax, eax
0x18001de42  jns     short loc_18001DE4F
0x18001de44  mov     r8d, 1D4h
0x18001de4a  jmp     loc_18001DDA2
0x18001de4f  mov     rsi, [rbp+arg_18]
0x18001de53  lea     rdx, aRequireselevat; "RequiresElevation"
0x18001de5a  mov     rcx, rsi; struct IXMLDOMNode *
0x18001de5d  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x18001de62  mov     ebx, eax
0x18001de64  test    eax, eax
0x18001de66  jns     short loc_18001DE73
0x18001de68  mov     r8d, 1D5h
0x18001de6e  jmp     loc_18001DD6D
0x18001de73  cmp     eax, edi
0x18001de75  jz      loc_18001E0E9
0x18001de7b  test    rsi, rsi
0x18001de7e  jz      loc_18001E0E9
0x18001de84  lea     rdx, [r14+10h]; int *
0x18001de88  mov     rcx, rsi; struct IXMLDOMNode *
0x18001de8b  call    ?SdpParseBooleanNode@@YAJPEAUIXMLDOMNode@@PEAH@Z; SdpParseBooleanNode(IXMLDOMNode *,int *)
0x18001de90  mov     ebx, eax
0x18001de92  test    eax, eax
0x18001de94  jns     short loc_18001DEA1
0x18001de96  mov     r8d, 1D8h
0x18001de9c  jmp     loc_18001DD6D
0x18001dea1  mov     rax, [rsi]
0x18001dea4  mov     rcx, rsi
0x18001dea7  mov     rax, [rax+10h]
0x18001deab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001deb0  lea     rdx, [rbp+arg_18]; struct IXMLDOMNode **
0x18001deb4  mov     [rbp+arg_18], r13
0x18001deb8  mov     rcx, r12; struct IXMLDOMNodeList *
0x18001debb  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x18001dec0  mov     ebx, eax
0x18001dec2  test    eax, eax
0x18001dec4  jns     short loc_18001DED1
0x18001dec6  mov     r8d, 1E0h
0x18001decc  jmp     loc_18001DDA2
0x18001ded1  mov     rsi, [rbp+arg_18]
0x18001ded5  lea     rdx, aRequiresintera; "RequiresInteractivity"
0x18001dedc  mov     rcx, rsi; struct IXMLDOMNode *
0x18001dedf  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x18001dee4  mov     ebx, eax
0x18001dee6  test    eax, eax
0x18001dee8  jns     short loc_18001DEF5
0x18001deea  mov     r8d, 1E1h
0x18001def0  jmp     loc_18001DD6D
0x18001def5  cmp     eax, edi
0x18001def7  jz      loc_18001E0E1
0x18001defd  test    rsi, rsi
0x18001df00  jz      loc_18001E0E1
0x18001df06  lea     rdx, [r14+28h]; int *
0x18001df0a  mov     rcx, rsi; struct IXMLDOMNode *
0x18001df0d  call    ?SdpParseBooleanNode@@YAJPEAUIXMLDOMNode@@PEAH@Z; SdpParseBooleanNode(IXMLDOMNode *,int *)
0x18001df12  mov     ebx, eax
0x18001df14  test    eax, eax
0x18001df16  jns     short loc_18001DF23
0x18001df18  mov     r8d, 1E4h
0x18001df1e  jmp     loc_18001DD6D
0x18001df23  mov     rax, [rsi]
0x18001df26  mov     rcx, rsi
0x18001df29  mov     rax, [rax+10h]
0x18001df2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df32  lea     rdx, [rbp+arg_18]; struct IXMLDOMNode **
0x18001df36  mov     [rbp+arg_18], r13
0x18001df3a  mov     rcx, r12; struct IXMLDOMNodeList *
0x18001df3d  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x18001df42  mov     ebx, eax
0x18001df44  test    eax, eax
0x18001df46  jns     short loc_18001DF53
0x18001df48  mov     r8d, 1ECh
0x18001df4e  jmp     loc_18001DDA2
0x18001df53  mov     rsi, [rbp+arg_18]
0x18001df57  lea     rdx, aFilename_0; "FileName"
0x18001df5e  mov     rcx, rsi; struct IXMLDOMNode *
0x18001df61  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x18001df66  mov     ebx, eax
0x18001df68  test    eax, eax
0x18001df6a  jns     short loc_18001DF77
0x18001df6c  mov     r8d, 1EDh
0x18001df72  jmp     loc_18001DD6D
0x18001df77  cmp     eax, edi
0x18001df79  jz      loc_18001E0D9
0x18001df7f  test    rsi, rsi
0x18001df82  jz      loc_18001E0D9
0x18001df88  mov     rax, [rsi]
0x18001df8b  lea     rdx, [rbp+bstrString]
0x18001df8f  mov     rcx, rsi
0x18001df92  mov     rax, [rax+0D0h]
0x18001df99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df9e  mov     ebx, eax
0x18001dfa0  test    eax, eax
0x18001dfa2  jns     short loc_18001DFAF
0x18001dfa4  mov     r8d, 1F0h
0x18001dfaa  jmp     loc_18001DD6D
0x18001dfaf  mov     rcx, [r14]; this
0x18001dfb2  test    rcx, rcx
0x18001dfb5  jnz     short loc_18001DFCA
0x18001dfb7  mov     ebx, 80004003h
0x18001dfbc  mov     r8d, 1F2h
0x18001dfc2  mov     r9d, ebx
0x18001dfc5  jmp     loc_18001DD70
0x18001dfca  lea     rdx, [rbp+var_10]; unsigned __int16 **
0x18001dfce  call    ?get_PackagePath@Settings@@QEAAJPEAPEAG@Z; Settings::get_PackagePath(ushort * *)
0x18001dfd3  mov     ebx, eax
0x18001dfd5  test    eax, eax
0x18001dfd7  jns     short loc_18001DFF9
0x18001dfd9  mov     r9d, eax; int
0x18001dfdc  lea     rdx, aScriptParsescr; "Script::ParseScriptXml"
0x18001dfe3  mov     r8d, 1F5h; int
0x18001dfe9  mov     ecx, edi; Level
0x18001dfeb  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001dff0  mov     r15, [rbp+var_10]
0x18001dff4  jmp     loc_18001E116
0x18001dff9  mov     r15, [rbp+var_10]
0x18001dffd  lea     r8, [r14+8]; unsigned __int16 **
0x18001e001  mov     rdx, [rbp+bstrString]; unsigned __int16 *
0x18001e005  mov     rcx, r15; unsigned __int16 *
0x18001e008  call    ?SdpBuildPath@@YAJPEBG0PEAPEAG@Z; SdpBuildPath(ushort const *,ushort const *,ushort * *)
0x18001e00d  mov     ebx, eax
0x18001e00f  test    eax, eax
0x18001e011  jns     short loc_18001E01E
0x18001e013  mov     r8d, 1F8h
0x18001e019  jmp     loc_18001DD6D
0x18001e01e  mov     rdx, [r14+8]; unsigned __int16 *
0x18001e022  lea     r8, [rbp+arg_10]; int *
0x18001e026  mov     rcx, r15; unsigned __int16 *
0x18001e029  call    ?SdpIsSubDirectory@@YAJPEBG0PEAH@Z; SdpIsSubDirectory(ushort const *,ushort const *,int *)
0x18001e02e  mov     ebx, eax
0x18001e030  test    eax, eax
0x18001e032  jns     short loc_18001E03F
0x18001e034  mov     r8d, 1FFh
0x18001e03a  jmp     loc_18001DD6D
0x18001e03f  cmp     [rbp+arg_10], r13d
0x18001e043  jnz     short loc_18001E074
0x18001e045  call    cs:__imp_GetLastError
0x18001e04b  mov     ebx, eax
0x18001e04d  test    eax, eax
0x18001e04f  jle     short loc_18001E05A
0x18001e051  movzx   ebx, ax
0x18001e054  or      ebx, 80070000h
0x18001e05a  mov     r9d, 80004005h
0x18001e060  test    ebx, ebx
0x18001e062  mov     r8d, 200h
0x18001e068  cmovns  ebx, r9d
0x18001e06c  mov     r9d, ebx
0x18001e06f  jmp     loc_18001DD70
0x18001e074  mov     rax, [rsi]
0x18001e077  mov     rcx, rsi
0x18001e07a  mov     rax, [rax+10h]
0x18001e07e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e083  lea     rdx, [rbp+arg_18]; struct IXMLDOMNode **
0x18001e087  mov     [rbp+arg_18], r13
0x18001e08b  mov     rcx, r12; struct IXMLDOMNodeList *
0x18001e08e  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x18001e093  mov     ebx, eax
  ... truncated ...
```
