# Interaction::CreateInteractionsFromXml(Settings *,IXMLDOMNode *,IXMLDOMDocument2 *,Interaction * * *,ulong *)

- ea: `0x18001fc10`
- end: `0x180020214`
- name: `?CreateInteractionsFromXml@Interaction@@SAJPEAVSettings@@PEAUIXMLDOMNode@@PEAUIXMLDOMDocument2@@PEAPEAPEAV1@PEAK@Z`
- size: `1540`
- prototype: `__int64 __fastcall(struct Settings *, struct IXMLDOMNode *, struct IXMLDOMDocument2 *, struct Interaction ***, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x180016630`

## callees

- `0x1800012a4`
- `0x1800012b0`
- `0x18001f010`
- `0x18001fc10`
- `0x180026fa0`
- `0x180028038`
- `0x1800286a4`
- `0x1800290bc`
- `0x180029882`
- `0x18002a010`

## string_xrefs

- `0x18001fc7e`: `Interaction::CreateInteractionsFromXml`
- `0x18001fcd9`: `Interaction::CreateInteractionsFromXml`
- `0x18001fd29`: `Interaction::CreateInteractionsFromXml`
- `0x18001fd8f`: `Interaction::CreateInteractionsFromXml`
- `0x18001fe8a`: `Interaction::CreateInteractionsFromXml`
- `0x18001ff12`: `Interaction::CreateInteractionsFromXml`
- `0x18002005b`: `Interaction::CreateInteractionsFromXml`
- `0x18002011c`: `Interaction::CreateInteractionsFromXml`

## pseudocode

```c
__int64 __fastcall Interaction::CreateInteractionsFromXml(
        struct Settings *a1,
        struct IXMLDOMNode *a2,
        struct IXMLDOMDocument2 *a3,
        struct Interaction ***a4,
        unsigned int *a5)
{
  struct Interaction **v5; // r13
  struct IXMLDOMNode *v6; // r14
  int v7; // r8d
  int v8; // ebx
  int ChildNodes; // eax
  int v10; // r9d
  int v11; // r8d
  struct IXMLDOMNodeList *v12; // rsi
  int v13; // eax
  int v14; // r8d
  struct IXMLDOMNode *v15; // r15
  int v16; // eax
  int v17; // r8d
  struct IXMLDOMNode *v18; // r15
  struct IXMLDOMNode *v19; // r12
  struct IXMLDOMNode *v20; // r15
  int v21; // eax
  int v22; // eax
  int v23; // r8d
  unsigned int v24; // esi
  unsigned int v25; // esi
  unsigned int v26; // esi
  unsigned int v27; // esi
  struct Interaction **v28; // rax
  int v29; // r8d
  __int64 v30; // r15
  int v31; // r12d
  struct Interaction *v32; // rcx
  unsigned int v34; // [rsp+58h] [rbp-21h] BYREF
  unsigned int v35; // [rsp+5Ch] [rbp-1Dh] BYREF
  struct IXMLDOMNodeList *v36; // [rsp+60h] [rbp-19h] BYREF
  struct IXMLDOMNode *v37; // [rsp+68h] [rbp-11h] BYREF
  struct IXMLDOMNode *v38; // [rsp+70h] [rbp-9h] BYREF
  struct IXMLDOMNode *v39; // [rsp+78h] [rbp-1h] BYREF
  struct IXMLDOMNode *v40; // [rsp+80h] [rbp+7h] BYREF
  struct IXMLDOMNode *v41; // [rsp+88h] [rbp+Fh] BYREF

  v34 = 0;
  v5 = 0;
  v39 = 0;
  v37 = 0;
  v6 = 0;
  v40 = 0;
  v41 = 0;
  v38 = 0;
  v36 = 0;
  v35 = 0;
  if ( !a1 )
  {
    v7 = 76;
LABEL_3:
    v8 = -2147024809;
    SdpDebugTrace(1u, L"Interaction::CreateInteractionsFromXml", v7, -2147024809);
    return (unsigned int)v8;
  }
  if ( !a2 )
  {
    v7 = 77;
    goto LABEL_3;
  }
  if ( !a4 )
  {
    v7 = 78;
    goto LABEL_3;
  }
  if ( !a5 )
  {
    v7 = 79;
    goto LABEL_3;
  }
  ChildNodes = SdpXmlGetChildNodes(0, a2, &v36, &v35);
  v8 = ChildNodes;
  if ( ChildNodes >= 0 )
  {
    if ( v35 < 5 )
    {
      v10 = -2147024809;
      v11 = 89;
      v8 = -2147024809;
      goto LABEL_12;
    }
    v12 = v36;
    v13 = SdpXmlNextNode(v36, &v39);
    v8 = v13;
    if ( v13 < 0 )
    {
      v14 = 97;
LABEL_17:
      SdpDebugTrace(1u, L"Interaction::CreateInteractionsFromXml", v14, v13);
LABEL_89:
      if ( v39 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v39->lpVtbl->Release)(v39);
      if ( v5 )
        (*((void (__fastcall **)(struct Interaction **))*v5 + 2))(v5);
      if ( v40 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v40->lpVtbl->Release)(v40);
      if ( v41 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v41->lpVtbl->Release)(v41);
      if ( v6 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v6->lpVtbl->Release)(v6);
      goto LABEL_99;
    }
    v15 = v39;
    v13 = SdpXmlCheckNode(v39, L"SingleResponseInteractions");
    v8 = v13;
    if ( v13 < 0 )
    {
      v14 = 98;
      goto LABEL_17;
    }
    if ( v13 == 1 || !v15 )
    {
      v8 = -2147467259;
      v29 = 98;
    }
    else
    {
      v16 = SdpXmlNextNode(v12, &v37);
      v8 = v16;
      if ( v16 < 0 )
      {
        v17 = 101;
LABEL_24:
        SdpDebugTrace(1u, L"Interaction::CreateInteractionsFromXml", v17, v16);
LABEL_88:
        v5 = (struct Interaction **)v37;
        goto LABEL_89;
      }
      v18 = v37;
      v16 = SdpXmlCheckNode(v37, L"MultipleResponseInteractions");
      v8 = v16;
      if ( v16 < 0 )
      {
LABEL_26:
        v17 = 102;
        goto LABEL_24;
      }
      if ( v16 == 1 || !v18 )
      {
        v16 = -2147467259;
        v8 = -2147467259;
        goto LABEL_26;
      }
      v16 = SdpXmlNextNode(v12, &v40);
      v8 = v16;
      if ( v16 < 0 )
      {
        v17 = 105;
        goto LABEL_24;
      }
      v19 = v40;
      v16 = SdpXmlCheckNode(v40, L"TextInteractions");
      v8 = v16;
      if ( v16 < 0 )
      {
LABEL_32:
        v17 = 106;
        goto LABEL_24;
      }
      if ( v16 == 1 || !v19 )
      {
        v16 = -2147467259;
        v8 = -2147467259;
        goto LABEL_32;
      }
      v16 = SdpXmlNextNode(v12, &v41);
      v8 = v16;
      if ( v16 < 0 )
      {
        v17 = 109;
        goto LABEL_24;
      }
      v20 = v41;
      v16 = SdpXmlCheckNode(v41, L"PauseInteractions");
      v8 = v16;
      if ( v16 < 0 )
      {
LABEL_38:
        v17 = 110;
        goto LABEL_24;
      }
      if ( v16 == 1 || !v20 )
      {
        v16 = -2147467259;
        v8 = -2147467259;
        goto LABEL_38;
      }
      v21 = SdpXmlNextNode(v12, &v38);
      v8 = v21;
      if ( v21 < 0 )
      {
        SdpDebugTrace(1u, L"Interaction::CreateInteractionsFromXml", 113, v21);
LABEL_87:
        v6 = v38;
        goto LABEL_88;
      }
      v6 = v38;
      v16 = SdpXmlCheckNode(v38, L"LaunchUIInteractions");
      v8 = v16;
      if ( v16 < 0 )
      {
LABEL_44:
        v17 = 114;
        goto LABEL_24;
      }
      if ( v16 == 1 || !v6 )
      {
        v16 = -2147467259;
        v8 = -2147467259;
        goto LABEL_44;
      }
      if ( v12 )
      {
        ((void (__fastcall *)(struct IXMLDOMNodeList *))v12->lpVtbl->Release)(v12);
        v36 = 0;
      }
      v22 = SdpXmlGetChildNodes(0, v39, &v36, &v34);
      v8 = v22;
      if ( v22 < 0 )
      {
        v23 = 122;
LABEL_51:
        SdpDebugTrace(1u, L"Interaction::CreateInteractionsFromXml", v23, v22);
        v12 = v36;
        goto LABEL_88;
      }
      v24 = v34;
      if ( v36 )
      {
        ((void (__fastcall *)(struct IXMLDOMNodeList *))v36->lpVtbl->Release)(v36);
        v36 = 0;
      }
      v22 = SdpXmlGetChildNodes(0, v37, &v36, &v34);
      v8 = v22;
      if ( v22 < 0 )
      {
        v23 = 127;
        goto LABEL_51;
      }
      v25 = v34 + v24;
      if ( v36 )
      {
        ((void (__fastcall *)(struct IXMLDOMNodeList *))v36->lpVtbl->Release)(v36);
        v36 = 0;
      }
      v22 = SdpXmlGetChildNodes(0, v19, &v36, &v34);
      v8 = v22;
      if ( v22 < 0 )
      {
        v23 = 132;
        goto LABEL_51;
      }
      v26 = v34 + v25;
      if ( v36 )
      {
        ((void (__fastcall *)(struct IXMLDOMNodeList *))v36->lpVtbl->Release)(v36);
        v36 = 0;
      }
      v22 = SdpXmlGetChildNodes(0, v20, &v36, &v34);
      v8 = v22;
      if ( v22 < 0 )
      {
        v23 = 137;
        goto LABEL_51;
      }
      v27 = v34 + v26;
      if ( v36 )
      {
        ((void (__fastcall *)(struct IXMLDOMNodeList *))v36->lpVtbl->Release)(v36);
        v36 = 0;
      }
      v22 = SdpXmlGetChildNodes(0, v6, &v36, &v34);
      v8 = v22;
      if ( v22 < 0 )
      {
        v23 = 142;
        goto LABEL_51;
      }
      v6 = (struct IXMLDOMNode *)(v27 + v34);
      if ( !(v27 + v34) )
        goto LABEL_74;
      v28 = (struct Interaction **)operator new[](saturated_mul((unsigned int)v6, 8u));
      v5 = v28;
      if ( !v28 )
      {
        v8 = -2147024882;
        SdpDebugTrace(1u, L"Interaction::CreateInteractionsFromXml", 152, -2147024882);
LABEL_71:
        v12 = v36;
        goto LABEL_87;
      }
      memset_0(v28, 0, 8LL * (_QWORD)v6);
      v8 = Interaction::BuildInteractionArray(a1, a3, v39, v37, v19, v20, v38, v5, (unsigned int)v6);
      if ( v8 >= 0 )
      {
LABEL_74:
        *a4 = v5;
        *a5 = (unsigned int)v6;
        goto LABEL_71;
      }
      v12 = v36;
      v29 = 164;
    }
    SdpDebugTrace(1u, L"Interaction::CreateInteractionsFromXml", v29, v8);
    if ( v5 )
    {
      if ( (_DWORD)v6 )
      {
        v30 = 0;
        v31 = 0;
        do
        {
          v32 = v5[v30];
          if ( v32 )
          {
            (**(void (__fastcall ***)(struct Interaction *, __int64))v32)(v32, 1);
            v5[v31] = 0;
          }
          v30 = (unsigned int)(v30 + 1);
          v31 = v30;
        }
        while ( (unsigned int)v30 < (unsigned int)v6 );
      }
      operator delete(v5);
    }
    goto LABEL_87;
  }
  v10 = ChildNodes;
  v11 = 85;
LABEL_12:
  SdpDebugTrace(1u, L"Interaction::CreateInteractionsFromXml", v11, v10);
  v12 = v36;
LABEL_99:
  if ( v12 )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v12->lpVtbl->Release)(v12);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001fc10  mov     rax, rsp
0x18001fc13  mov     [rax+10h], rbx
0x18001fc17  mov     [rax+20h], r9
0x18001fc1b  mov     [rax+18h], r8
0x18001fc1f  mov     [rax+8], rcx
0x18001fc23  push    rbp
0x18001fc24  push    rsi
0x18001fc25  push    rdi
0x18001fc26  push    r12
0x18001fc28  push    r13
0x18001fc2a  push    r14
0x18001fc2c  push    r15
0x18001fc2e  lea     rbp, [rax-57h]
0x18001fc32  sub     rsp, 90h
0x18001fc39  xor     r12d, r12d
0x18001fc3c  mov     [rbp+4Fh+var_70], 0
0x18001fc43  xor     r13d, r13d
0x18001fc46  mov     [rbp+4Fh+var_50], 0
0x18001fc4e  xor     r15d, r15d
0x18001fc51  mov     [rbp+4Fh+var_60], r13
0x18001fc55  xor     r14d, r14d
0x18001fc58  mov     [rbp+4Fh+var_48], r12
0x18001fc5c  mov     [rbp+4Fh+var_40], r15
0x18001fc60  mov     rax, r9
0x18001fc63  mov     [rbp+4Fh+var_58], r14
0x18001fc67  mov     [rbp+4Fh+var_68], r12
0x18001fc6b  mov     [rbp+4Fh+var_6C], r12d
0x18001fc6f  test    rcx, rcx
0x18001fc72  jnz     short loc_18001FC97
0x18001fc74  lea     r8d, [r13+4Ch]; int
0x18001fc78  mov     r9d, 80070057h; int
0x18001fc7e  lea     rdx, aInteractionCre; "Interaction::CreateInteractionsFromXml"
0x18001fc85  mov     ecx, 1; Level
0x18001fc8a  mov     ebx, r9d
0x18001fc8d  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001fc92  jmp     loc_1800201F7
0x18001fc97  test    rdx, rdx
0x18001fc9a  jnz     short loc_18001FCA2
0x18001fc9c  lea     r8d, [rdx+4Dh]
0x18001fca0  jmp     short loc_18001FC78
0x18001fca2  test    rax, rax
0x18001fca5  jnz     short loc_18001FCAD
0x18001fca7  lea     r8d, [rax+4Eh]
0x18001fcab  jmp     short loc_18001FC78
0x18001fcad  cmp     [rbp+4Fh+arg_20], r12
0x18001fcb1  jnz     short loc_18001FCBB
0x18001fcb3  mov     r8d, 4Fh ; 'O'
0x18001fcb9  jmp     short loc_18001FC78
0x18001fcbb  lea     r9, [rbp+4Fh+var_6C]; unsigned int *
0x18001fcbf  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x18001fcc1  lea     r8, [rbp+4Fh+var_68]; struct IXMLDOMNodeList **
0x18001fcc5  call    ?SdpXmlGetChildNodes@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@PEAK@Z; SdpXmlGetChildNodes(IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *,ulong *)
0x18001fcca  mov     ebx, eax
0x18001fccc  test    eax, eax
0x18001fcce  jns     short loc_18001FCF3
0x18001fcd0  mov     r9d, eax; int
0x18001fcd3  mov     r8d, 55h ; 'U'; int
0x18001fcd9  lea     rdx, aInteractionCre; "Interaction::CreateInteractionsFromXml"
0x18001fce0  mov     ecx, 1; Level
0x18001fce5  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001fcea  mov     rsi, [rbp+4Fh+var_68]
0x18001fcee  jmp     loc_1800201E3
0x18001fcf3  cmp     [rbp+4Fh+var_6C], 5
0x18001fcf7  jnb     short loc_18001FD0A
0x18001fcf9  mov     r9d, 80070057h
0x18001fcff  mov     r8d, 59h ; 'Y'
0x18001fd05  mov     ebx, r9d
0x18001fd08  jmp     short loc_18001FCD9
0x18001fd0a  mov     rsi, [rbp+4Fh+var_68]
0x18001fd0e  lea     rdx, [rbp+4Fh+var_50]; struct IXMLDOMNode **
0x18001fd12  mov     rcx, rsi; struct IXMLDOMNodeList *
0x18001fd15  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x18001fd1a  mov     ebx, eax
0x18001fd1c  test    eax, eax
0x18001fd1e  jns     short loc_18001FD3F
0x18001fd20  mov     r8d, 61h ; 'a'; int
0x18001fd26  mov     r9d, eax; int
0x18001fd29  lea     rdx, aInteractionCre; "Interaction::CreateInteractionsFromXml"
0x18001fd30  mov     ecx, 1; Level
0x18001fd35  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001fd3a  jmp     loc_18002017B
0x18001fd3f  mov     r15, [rbp+4Fh+var_50]
0x18001fd43  lea     rdx, aSingleresponse_0; "SingleResponseInteractions"
0x18001fd4a  mov     rcx, r15; struct IXMLDOMNode *
0x18001fd4d  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x18001fd52  mov     ebx, eax
0x18001fd54  test    eax, eax
0x18001fd56  jns     short loc_18001FD60
0x18001fd58  mov     r8d, 62h ; 'b'
0x18001fd5e  jmp     short loc_18001FD26
0x18001fd60  mov     edi, 1
0x18001fd65  cmp     eax, edi
0x18001fd67  jz      loc_180020111
0x18001fd6d  test    r15, r15
0x18001fd70  jz      loc_180020111
0x18001fd76  lea     rdx, [rbp+4Fh+var_60]; struct IXMLDOMNode **
0x18001fd7a  mov     rcx, rsi; struct IXMLDOMNodeList *
0x18001fd7d  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x18001fd82  mov     ebx, eax
0x18001fd84  test    eax, eax
0x18001fd86  jns     short loc_18001FDA2
0x18001fd88  lea     r8d, [rdi+64h]; int
0x18001fd8c  mov     r9d, eax; int
0x18001fd8f  lea     rdx, aInteractionCre; "Interaction::CreateInteractionsFromXml"
0x18001fd96  mov     ecx, edi; Level
0x18001fd98  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001fd9d  jmp     loc_180020177
0x18001fda2  mov     r15, [rbp+4Fh+var_60]
0x18001fda6  lea     rdx, aMultiplerespon_3; "MultipleResponseInteractions"
0x18001fdad  mov     rcx, r15; struct IXMLDOMNode *
0x18001fdb0  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x18001fdb5  mov     ebx, eax
0x18001fdb7  test    eax, eax
0x18001fdb9  jns     short loc_18001FDC3
0x18001fdbb  mov     r8d, 66h ; 'f'
0x18001fdc1  jmp     short loc_18001FD8C
0x18001fdc3  cmp     eax, edi
0x18001fdc5  jz      loc_180020105
0x18001fdcb  test    r15, r15
0x18001fdce  jz      loc_180020105
0x18001fdd4  lea     rdx, [rbp+4Fh+var_48]; struct IXMLDOMNode **
0x18001fdd8  mov     rcx, rsi; struct IXMLDOMNodeList *
0x18001fddb  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x18001fde0  mov     ebx, eax
0x18001fde2  test    eax, eax
0x18001fde4  jns     short loc_18001FDEE
0x18001fde6  mov     r8d, 69h ; 'i'
0x18001fdec  jmp     short loc_18001FD8C
0x18001fdee  mov     r12, [rbp+4Fh+var_48]
0x18001fdf2  lea     rdx, aTextinteractio_0; "TextInteractions"
0x18001fdf9  mov     rcx, r12; struct IXMLDOMNode *
0x18001fdfc  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x18001fe01  mov     ebx, eax
0x18001fe03  test    eax, eax
0x18001fe05  jns     short loc_18001FE12
0x18001fe07  mov     r8d, 6Ah ; 'j'
0x18001fe0d  jmp     loc_18001FD8C
0x18001fe12  cmp     eax, edi
0x18001fe14  jz      loc_1800200F9
0x18001fe1a  test    r12, r12
0x18001fe1d  jz      loc_1800200F9
0x18001fe23  lea     rdx, [rbp+4Fh+var_40]; struct IXMLDOMNode **
0x18001fe27  mov     rcx, rsi; struct IXMLDOMNodeList *
0x18001fe2a  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x18001fe2f  mov     ebx, eax
0x18001fe31  test    eax, eax
0x18001fe33  jns     short loc_18001FE40
0x18001fe35  mov     r8d, 6Dh ; 'm'
0x18001fe3b  jmp     loc_18001FD8C
0x18001fe40  mov     r15, [rbp+4Fh+var_40]
0x18001fe44  lea     rdx, aPauseinteracti_1; "PauseInteractions"
0x18001fe4b  mov     rcx, r15; struct IXMLDOMNode *
0x18001fe4e  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x18001fe53  mov     ebx, eax
0x18001fe55  test    eax, eax
0x18001fe57  jns     short loc_18001FE64
0x18001fe59  mov     r8d, 6Eh ; 'n'
0x18001fe5f  jmp     loc_18001FD8C
0x18001fe64  cmp     eax, edi
0x18001fe66  jz      loc_1800200ED
0x18001fe6c  test    r15, r15
0x18001fe6f  jz      loc_1800200ED
0x18001fe75  lea     rdx, [rbp+4Fh+var_58]; struct IXMLDOMNode **
0x18001fe79  mov     rcx, rsi; struct IXMLDOMNodeList *
0x18001fe7c  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x18001fe81  mov     ebx, eax
0x18001fe83  test    eax, eax
0x18001fe85  jns     short loc_18001FEA3
0x18001fe87  mov     r9d, eax; int
0x18001fe8a  lea     rdx, aInteractionCre; "Interaction::CreateInteractionsFromXml"
0x18001fe91  mov     r8d, 71h ; 'q'; int
0x18001fe97  mov     ecx, edi; Level
0x18001fe99  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001fe9e  jmp     loc_180020173
0x18001fea3  mov     r14, [rbp+4Fh+var_58]
0x18001fea7  lea     rdx, aLaunchuiintera_0; "LaunchUIInteractions"
0x18001feae  mov     rcx, r14; struct IXMLDOMNode *
0x18001feb1  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x18001feb6  mov     ebx, eax
0x18001feb8  test    eax, eax
0x18001feba  jns     short loc_18001FEC7
0x18001febc  mov     r8d, 72h ; 'r'
0x18001fec2  jmp     loc_18001FD8C
0x18001fec7  cmp     eax, edi
0x18001fec9  jz      loc_1800200E1
0x18001fecf  test    r14, r14
0x18001fed2  jz      loc_1800200E1
0x18001fed8  test    rsi, rsi
0x18001fedb  jz      short loc_18001FEF0
0x18001fedd  mov     rax, [rsi]
0x18001fee0  mov     rcx, rsi
0x18001fee3  mov     rax, [rax+10h]
0x18001fee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001feec  mov     [rbp+4Fh+var_68], r13
0x18001fef0  mov     rdx, [rbp+4Fh+var_50]; struct IXMLDOMNode *
0x18001fef4  lea     r9, [rbp+4Fh+var_70]; unsigned int *
0x18001fef8  lea     r8, [rbp+4Fh+var_68]; struct IXMLDOMNodeList **
0x18001fefc  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x18001fefe  call    ?SdpXmlGetChildNodes@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@PEAK@Z; SdpXmlGetChildNodes(IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *,ulong *)
0x18001ff03  mov     ebx, eax
0x18001ff05  test    eax, eax
0x18001ff07  jns     short loc_18001FF29
0x18001ff09  mov     r8d, 7Ah ; 'z'; int
0x18001ff0f  mov     r9d, eax; int
0x18001ff12  lea     rdx, aInteractionCre; "Interaction::CreateInteractionsFromXml"
0x18001ff19  mov     ecx, edi; Level
0x18001ff1b  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001ff20  mov     rsi, [rbp+4Fh+var_68]
0x18001ff24  jmp     loc_180020177
0x18001ff29  mov     rcx, [rbp+4Fh+var_68]
0x18001ff2d  mov     esi, [rbp+4Fh+var_70]
0x18001ff30  test    rcx, rcx
0x18001ff33  jz      short loc_18001FF45
0x18001ff35  mov     rax, [rcx]
0x18001ff38  mov     rax, [rax+10h]
0x18001ff3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff41  mov     [rbp+4Fh+var_68], r13
0x18001ff45  mov     rdx, [rbp+4Fh+var_60]; struct IXMLDOMNode *
0x18001ff49  lea     r9, [rbp+4Fh+var_70]; unsigned int *
0x18001ff4d  lea     r8, [rbp+4Fh+var_68]; struct IXMLDOMNodeList **
0x18001ff51  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x18001ff53  call    ?SdpXmlGetChildNodes@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@PEAK@Z; SdpXmlGetChildNodes(IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *,ulong *)
0x18001ff58  mov     ebx, eax
0x18001ff5a  test    eax, eax
0x18001ff5c  jns     short loc_18001FF66
0x18001ff5e  mov     r8d, 7Fh
0x18001ff64  jmp     short loc_18001FF0F
0x18001ff66  add     esi, [rbp+4Fh+var_70]
0x18001ff69  mov     rcx, [rbp+4Fh+var_68]
0x18001ff6d  test    rcx, rcx
0x18001ff70  jz      short loc_18001FF82
0x18001ff72  mov     rax, [rcx]
0x18001ff75  mov     rax, [rax+10h]
0x18001ff79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff7e  mov     [rbp+4Fh+var_68], r13
0x18001ff82  lea     r9, [rbp+4Fh+var_70]; unsigned int *
0x18001ff86  mov     rdx, r12; struct IXMLDOMNode *
0x18001ff89  lea     r8, [rbp+4Fh+var_68]; struct IXMLDOMNodeList **
0x18001ff8d  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x18001ff8f  call    ?SdpXmlGetChildNodes@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@PEAK@Z; SdpXmlGetChildNodes(IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *,ulong *)
0x18001ff94  mov     ebx, eax
0x18001ff96  test    eax, eax
0x18001ff98  jns     short loc_18001FFA5
0x18001ff9a  mov     r8d, 84h
0x18001ffa0  jmp     loc_18001FF0F
0x18001ffa5  add     esi, [rbp+4Fh+var_70]
0x18001ffa8  mov     rcx, [rbp+4Fh+var_68]
0x18001ffac  test    rcx, rcx
0x18001ffaf  jz      short loc_18001FFC1
0x18001ffb1  mov     rax, [rcx]
0x18001ffb4  mov     rax, [rax+10h]
0x18001ffb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ffbd  mov     [rbp+4Fh+var_68], r13
0x18001ffc1  lea     r9, [rbp+4Fh+var_70]; unsigned int *
0x18001ffc5  mov     rdx, r15; struct IXMLDOMNode *
0x18001ffc8  lea     r8, [rbp+4Fh+var_68]; struct IXMLDOMNodeList **
0x18001ffcc  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x18001ffce  call    ?SdpXmlGetChildNodes@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@PEAK@Z; SdpXmlGetChildNodes(IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *,ulong *)
0x18001ffd3  mov     ebx, eax
0x18001ffd5  test    eax, eax
0x18001ffd7  jns     short loc_18001FFE4
0x18001ffd9  mov     r8d, 89h
0x18001ffdf  jmp     loc_18001FF0F
0x18001ffe4  add     esi, [rbp+4Fh+var_70]
0x18001ffe7  mov     rcx, [rbp+4Fh+var_68]
0x18001ffeb  test    rcx, rcx
0x18001ffee  jz      short loc_180020000
0x18001fff0  mov     rax, [rcx]
0x18001fff3  mov     rax, [rax+10h]
0x18001fff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fffc  mov     [rbp+4Fh+var_68], r13
0x180020000  lea     r9, [rbp+4Fh+var_70]; unsigned int *
0x180020004  mov     rdx, r14; struct IXMLDOMNode *
0x180020007  lea     r8, [rbp+4Fh+var_68]; struct IXMLDOMNodeList **
0x18002000b  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x18002000d  call    ?SdpXmlGetChildNodes@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@PEAK@Z; SdpXmlGetChildNodes(IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *,ulong *)
0x180020012  mov     ebx, eax
0x180020014  test    eax, eax
0x180020016  jns     short loc_180020023
0x180020018  mov     r8d, 8Eh
0x18002001e  jmp     loc_18001FF0F
0x180020023  mov     r14d, [rbp+4Fh+var_70]
0x180020027  add     r14d, esi
0x18002002a  jz      loc_1800200D1
0x180020030  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180020037  mov     ebx, r14d
0x18002003a  mov     eax, 8
0x18002003f  mul     rbx
0x180020042  cmovb   rax, rcx
0x180020046  mov     rcx, rax; unsigned __int64
0x180020049  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002004e  mov     r13, rax
0x180020051  test    rax, rax
0x180020054  jnz     short loc_18002007B
0x180020056  mov     ebx, 8007000Eh
0x18002005b  lea     rdx, aInteractionCre; "Interaction::CreateInteractionsFromXml"
0x180020062  mov     r9d, ebx; int
0x180020065  mov     r8d, 98h; int
0x18002006b  mov     ecx, edi; Level
0x18002006d  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
  ... truncated ...
```
