# MultipleResponseInteraction::InitializeChoice(IXMLDOMNode *,MultipleResponseInteraction::_CHOICE *)

- ea: `0x180022ce0`
- end: `0x18002300e`
- name: `?InitializeChoice@MultipleResponseInteraction@@MEAAJPEAUIXMLDOMNode@@PEAU_CHOICE@1@@Z`
- size: `814`
- prototype: `__int64 __fastcall(struct Settings **this, struct IXMLDOMNode *, struct MultipleResponseInteraction::_CHOICE *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callees

- `0x180003b2c`
- `0x18000615c`
- `0x180022ce0`
- `0x180026fa0`
- `0x180028038`
- `0x1800286a4`
- `0x1800290bc`
- `0x18002a010`

## string_xrefs

- `0x180022f1a`: `ExtensionPoint`

## pseudocode

```c
__int64 __fastcall MultipleResponseInteraction::InitializeChoice(
        struct Settings **this,
        struct IXMLDOMNode *a2,
        struct MultipleResponseInteraction::_CHOICE *a3)
{
  struct IXMLDOMNode *v3; // rsi
  __int128 *v4; // r13
  struct IXMLDOMNodeList *v5; // r14
  int v8; // r8d
  int v9; // r9d
  int ChildNodes; // eax
  unsigned int v11; // ebx
  int v12; // r9d
  int v13; // r8d
  int v14; // eax
  int v15; // r8d
  int v16; // eax
  int v17; // eax
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v21; // [rsp+20h] [rbp-30h] BYREF
  __int128 v22; // [rsp+30h] [rbp-20h]
  __int128 v23; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v24; // [rsp+90h] [rbp+40h] BYREF
  struct IXMLDOMNode *v25; // [rsp+98h] [rbp+48h] BYREF
  struct IXMLDOMNodeList *v26; // [rsp+A8h] [rbp+58h] BYREF

  v3 = 0;
  v4 = &v21;
  v25 = 0;
  v5 = 0;
  v24 = 0;
  v26 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  if ( !a2 )
  {
    v8 = 231;
LABEL_3:
    v9 = -2147024809;
LABEL_44:
    v11 = v9;
    goto LABEL_45;
  }
  if ( !a3 )
  {
    v8 = 232;
    goto LABEL_3;
  }
  ChildNodes = SdpXmlGetChildNodes(0, a2, &v26, &v24);
  v11 = ChildNodes;
  if ( ChildNodes < 0 )
  {
    v12 = ChildNodes;
    v13 = 237;
LABEL_8:
    SdpDebugTrace(1u, L"MultipleResponseInteraction::InitializeChoice", v13, v12);
    v5 = v26;
    goto LABEL_46;
  }
  if ( v24 != 3 )
  {
    v12 = -2147024809;
    v13 = 241;
    v11 = -2147024809;
    goto LABEL_8;
  }
  v5 = v26;
  v14 = SdpXmlNextNode(v26, &v25);
  v11 = v14;
  if ( v14 < 0 )
  {
    v15 = 250;
LABEL_13:
    SdpDebugTrace(1u, L"MultipleResponseInteraction::InitializeChoice", v15, v14);
    v3 = v25;
    goto LABEL_46;
  }
  v3 = v25;
  v16 = SdpXmlCheckNode(v25, L"DisplayInformation");
  v11 = v16;
  if ( v16 >= 0 )
  {
    if ( v16 == 1 || !v3 )
    {
      v8 = 251;
    }
    else
    {
      v17 = SdpParseDisplayInformation(v3, (struct _SDIAG_DISPINFO *)&v21);
      v11 = v17;
      if ( v17 < 0 )
      {
        v8 = 254;
LABEL_20:
        v9 = v17;
        goto LABEL_45;
      }
      v17 = SdpLocalizeDisplayInformation(this[1], (struct _SDIAG_DISPINFO *)&v21, 0);
      v11 = v17;
      if ( v17 < 0 )
      {
        v8 = 259;
        goto LABEL_20;
      }
      ((void (__fastcall *)(struct IXMLDOMNode *))v3->lpVtbl->Release)(v3);
      v25 = 0;
      v14 = SdpXmlNextNode(v5, &v25);
      v11 = v14;
      if ( v14 < 0 )
      {
        v15 = 267;
        goto LABEL_13;
      }
      v3 = v25;
      v17 = SdpXmlCheckNode(v25, L"Value");
      v11 = v17;
      if ( v17 < 0 )
      {
        v8 = 268;
        goto LABEL_20;
      }
      if ( v17 == 1 || !v3 )
      {
        v8 = 268;
      }
      else
      {
        v17 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int128 *))v3->lpVtbl->get_text)(v3, &v23);
        v11 = v17;
        if ( v17 < 0 )
        {
          v8 = 271;
          goto LABEL_20;
        }
        ((void (__fastcall *)(struct IXMLDOMNode *))v3->lpVtbl->Release)(v3);
        v25 = 0;
        v14 = SdpXmlNextNode(v5, &v25);
        v11 = v14;
        if ( v14 < 0 )
        {
          v15 = 279;
          goto LABEL_13;
        }
        v3 = v25;
        v17 = SdpXmlCheckNode(v25, L"ExtensionPoint");
        v11 = v17;
        if ( v17 < 0 )
        {
          v8 = 280;
          goto LABEL_20;
        }
        if ( v17 != 1 && v3 )
        {
          v17 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64, char *))v3->lpVtbl->cloneNode)(
                  v3,
                  0xFFFFFFFFLL,
                  (char *)&v23 + 8);
          v11 = v17;
          if ( v17 >= 0 )
          {
            v4 = 0;
            v18 = v22;
            *(_OWORD *)a3 = v21;
            v19 = v23;
            *((_OWORD *)a3 + 1) = v18;
            *((_OWORD *)a3 + 2) = v19;
            goto LABEL_46;
          }
          v8 = 283;
          goto LABEL_20;
        }
        v8 = 280;
      }
    }
    v9 = -2147467259;
    goto LABEL_44;
  }
  v9 = v16;
  v8 = 251;
LABEL_45:
  SdpDebugTrace(1u, L"MultipleResponseInteraction::InitializeChoice", v8, v9);
LABEL_46:
  (*((void (__fastcall **)(struct Settings **, __int128 *))*this + 9))(this, v4);
  if ( v5 )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v5->lpVtbl->Release)(v5);
  if ( v3 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v3->lpVtbl->Release)(v3);
  return v11;
}

```

## disassembly

```asm
0x180022ce0  mov     [rsp-38h+arg_10], rbx
0x180022ce5  push    rbp
0x180022ce6  push    rsi
0x180022ce7  push    rdi
0x180022ce8  push    r12
0x180022cea  push    r13
0x180022cec  push    r14
0x180022cee  push    r15
0x180022cf0  mov     rbp, rsp
0x180022cf3  sub     rsp, 50h
0x180022cf7  xor     esi, esi
0x180022cf9  lea     r13, [rbp+var_30]
0x180022cfd  xorps   xmm0, xmm0
0x180022d00  mov     [rbp+arg_8], rsi
0x180022d04  xor     r14d, r14d
0x180022d07  mov     [rbp+arg_0], esi
0x180022d0a  mov     [rbp+arg_18], r14
0x180022d0e  mov     r15, r8
0x180022d11  mov     r12, rcx
0x180022d14  movups  [rbp+var_30], xmm0
0x180022d18  movups  [rbp+var_20], xmm0
0x180022d1c  movups  [rbp+var_10], xmm0
0x180022d20  test    rdx, rdx
0x180022d23  jnz     short loc_180022D3B
0x180022d25  mov     r8d, 0E7h
0x180022d2b  mov     r9d, 80070057h
0x180022d31  mov     ecx, 1
0x180022d36  jmp     loc_180022FAA
0x180022d3b  test    r15, r15
0x180022d3e  jnz     short loc_180022D48
0x180022d40  mov     r8d, 0E8h
0x180022d46  jmp     short loc_180022D2B
0x180022d48  lea     r9, [rbp+arg_0]; unsigned int *
0x180022d4c  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x180022d4e  lea     r8, [rbp+arg_18]; struct IXMLDOMNodeList **
0x180022d52  call    ?SdpXmlGetChildNodes@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@PEAK@Z; SdpXmlGetChildNodes(IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *,ulong *)
0x180022d57  mov     ebx, eax
0x180022d59  test    eax, eax
0x180022d5b  jns     short loc_180022D80
0x180022d5d  mov     r9d, eax; int
0x180022d60  mov     r8d, 0EDh; int
0x180022d66  lea     rdx, aMultiplerespon_10; "MultipleResponseInteraction::Initialize"...
0x180022d6d  mov     ecx, 1; Level
0x180022d72  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180022d77  mov     r14, [rbp+arg_18]
0x180022d7b  jmp     loc_180022FB9
0x180022d80  cmp     [rbp+arg_0], 3
0x180022d84  jz      short loc_180022D97
0x180022d86  mov     r9d, 80070057h
0x180022d8c  mov     r8d, 0F1h
0x180022d92  mov     ebx, r9d
0x180022d95  jmp     short loc_180022D66
0x180022d97  mov     r14, [rbp+arg_18]
0x180022d9b  lea     rdx, [rbp+arg_8]; struct IXMLDOMNode **
0x180022d9f  mov     rcx, r14; struct IXMLDOMNodeList *
0x180022da2  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x180022da7  mov     ebx, eax
0x180022da9  test    eax, eax
0x180022dab  jns     short loc_180022DD0
0x180022dad  mov     r8d, 0FAh; int
0x180022db3  mov     ecx, 1; Level
0x180022db8  mov     r9d, eax; int
0x180022dbb  lea     rdx, aMultiplerespon_10; "MultipleResponseInteraction::Initialize"...
0x180022dc2  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180022dc7  mov     rsi, [rbp+arg_8]
0x180022dcb  jmp     loc_180022FB9
0x180022dd0  mov     rsi, [rbp+arg_8]
0x180022dd4  lea     rdx, aDisplayinforma; "DisplayInformation"
0x180022ddb  mov     rcx, rsi; struct IXMLDOMNode *
0x180022dde  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x180022de3  mov     ebx, eax
0x180022de5  test    eax, eax
0x180022de7  jns     short loc_180022DFC
0x180022de9  mov     r9d, eax
0x180022dec  mov     r8d, 0FBh
0x180022df2  mov     ecx, 1
0x180022df7  jmp     loc_180022FAD
0x180022dfc  mov     edi, 1
0x180022e01  cmp     eax, edi
0x180022e03  jz      loc_180022F9C
0x180022e09  test    rsi, rsi
0x180022e0c  jz      loc_180022F9C
0x180022e12  lea     rdx, [rbp+var_30]; struct _SDIAG_DISPINFO *
0x180022e16  mov     rcx, rsi; struct IXMLDOMNode *
0x180022e19  call    ?SdpParseDisplayInformation@@YAJPEAUIXMLDOMNode@@PEAU_SDIAG_DISPINFO@@@Z; SdpParseDisplayInformation(IXMLDOMNode *,_SDIAG_DISPINFO *)
0x180022e1e  mov     ebx, eax
0x180022e20  test    eax, eax
0x180022e22  jns     short loc_180022E34
0x180022e24  mov     r8d, 0FEh
0x180022e2a  mov     r9d, eax
0x180022e2d  mov     ecx, edi
0x180022e2f  jmp     loc_180022FAD
0x180022e34  mov     rcx, [r12+8]; struct Settings *
0x180022e39  lea     rdx, [rbp+var_30]; struct _SDIAG_DISPINFO *
0x180022e3d  xor     r8d, r8d; int
0x180022e40  call    ?SdpLocalizeDisplayInformation@@YAJPEAVSettings@@PEAU_SDIAG_DISPINFO@@H@Z; SdpLocalizeDisplayInformation(Settings *,_SDIAG_DISPINFO *,int)
0x180022e45  mov     ebx, eax
0x180022e47  test    eax, eax
0x180022e49  jns     short loc_180022E53
0x180022e4b  mov     r8d, 103h
0x180022e51  jmp     short loc_180022E2A
0x180022e53  mov     rax, [rsi]
0x180022e56  mov     rcx, rsi
0x180022e59  mov     rax, [rax+10h]
0x180022e5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e62  lea     rdx, [rbp+arg_8]; struct IXMLDOMNode **
0x180022e66  mov     [rbp+arg_8], 0
0x180022e6e  mov     rcx, r14; struct IXMLDOMNodeList *
0x180022e71  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x180022e76  mov     ebx, eax
0x180022e78  test    eax, eax
0x180022e7a  jns     short loc_180022E89
0x180022e7c  mov     r8d, 10Bh
0x180022e82  mov     ecx, edi
0x180022e84  jmp     loc_180022DB8
0x180022e89  mov     rsi, [rbp+arg_8]
0x180022e8d  lea     rdx, aValue; "Value"
0x180022e94  mov     rcx, rsi; struct IXMLDOMNode *
0x180022e97  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x180022e9c  mov     ebx, eax
0x180022e9e  test    eax, eax
0x180022ea0  jns     short loc_180022EAA
0x180022ea2  mov     r8d, 10Ch
0x180022ea8  jmp     short loc_180022E2A
0x180022eaa  cmp     eax, edi
0x180022eac  jz      loc_180022F94
0x180022eb2  test    rsi, rsi
0x180022eb5  jz      loc_180022F94
0x180022ebb  mov     rax, [rsi]
0x180022ebe  lea     rdx, [rbp+var_10]
0x180022ec2  mov     rcx, rsi
0x180022ec5  mov     rax, [rax+0D0h]
0x180022ecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ed1  mov     ebx, eax
0x180022ed3  test    eax, eax
0x180022ed5  jns     short loc_180022EE2
0x180022ed7  mov     r8d, 10Fh
0x180022edd  jmp     loc_180022E2A
0x180022ee2  mov     rax, [rsi]
0x180022ee5  mov     rcx, rsi
0x180022ee8  mov     rax, [rax+10h]
0x180022eec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ef1  lea     rdx, [rbp+arg_8]; struct IXMLDOMNode **
0x180022ef5  mov     [rbp+arg_8], 0
0x180022efd  mov     rcx, r14; struct IXMLDOMNodeList *
0x180022f00  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x180022f05  mov     ebx, eax
0x180022f07  test    eax, eax
0x180022f09  jns     short loc_180022F16
0x180022f0b  mov     r8d, 117h
0x180022f11  jmp     loc_180022E82
0x180022f16  mov     rsi, [rbp+arg_8]
0x180022f1a  lea     rdx, aExtensionpoint_0; "ExtensionPoint"
0x180022f21  mov     rcx, rsi; struct IXMLDOMNode *
0x180022f24  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x180022f29  mov     ebx, eax
0x180022f2b  test    eax, eax
0x180022f2d  jns     short loc_180022F3A
0x180022f2f  mov     r8d, 118h
0x180022f35  jmp     loc_180022E2A
0x180022f3a  cmp     eax, edi
0x180022f3c  jz      short loc_180022F8C
0x180022f3e  test    rsi, rsi
0x180022f41  jz      short loc_180022F8C
0x180022f43  mov     rax, [rsi]
0x180022f46  lea     r8, [rbp+var_10+8]
0x180022f4a  or      edx, 0FFFFFFFFh
0x180022f4d  mov     rcx, rsi
0x180022f50  mov     rax, [rax+0C0h]
0x180022f57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f5c  mov     ebx, eax
0x180022f5e  test    eax, eax
0x180022f60  jns     short loc_180022F6D
0x180022f62  mov     r8d, 11Bh
0x180022f68  jmp     loc_180022E2A
0x180022f6d  movups  xmm0, [rbp+var_30]
0x180022f71  xor     r13d, r13d
0x180022f74  movups  xmm1, [rbp+var_20]
0x180022f78  movups  xmmword ptr [r15], xmm0
0x180022f7c  movups  xmm0, [rbp+var_10]
0x180022f80  movups  xmmword ptr [r15+10h], xmm1
0x180022f85  movups  xmmword ptr [r15+20h], xmm0
0x180022f8a  jmp     short loc_180022FB9
0x180022f8c  mov     r8d, 118h
0x180022f92  jmp     short loc_180022FA2
0x180022f94  mov     r8d, 10Ch
0x180022f9a  jmp     short loc_180022FA2
0x180022f9c  mov     r8d, 0FBh; int
0x180022fa2  mov     r9d, 80004005h; int
0x180022fa8  mov     ecx, edi; Level
0x180022faa  mov     ebx, r9d
0x180022fad  lea     rdx, aMultiplerespon_10; "MultipleResponseInteraction::Initialize"...
0x180022fb4  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180022fb9  mov     rax, [r12]
0x180022fbd  mov     rdx, r13
0x180022fc0  mov     rcx, r12
0x180022fc3  mov     rax, [rax+48h]
0x180022fc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022fcc  test    r14, r14
0x180022fcf  jz      short loc_180022FE0
0x180022fd1  mov     rax, [r14]
0x180022fd4  mov     rcx, r14
0x180022fd7  mov     rax, [rax+10h]
0x180022fdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022fe0  test    rsi, rsi
0x180022fe3  jz      short loc_180022FF4
0x180022fe5  mov     rax, [rsi]
0x180022fe8  mov     rcx, rsi
0x180022feb  mov     rax, [rax+10h]
0x180022fef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ff4  mov     eax, ebx
0x180022ff6  mov     rbx, [rsp+50h+arg_10]
0x180022ffe  add     rsp, 50h
0x180023002  pop     r15
0x180023004  pop     r14
0x180023006  pop     r13
0x180023008  pop     r12
0x18002300a  pop     rdi
0x18002300b  pop     rsi
0x18002300c  pop     rbp
0x18002300d  retn
```
