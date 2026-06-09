# Resolver::BuildResultXml(int,ushort const *,IXMLDOMDocument2 * *)

- ea: `0x18001c224`
- end: `0x18001c5a4`
- name: `?BuildResultXml@Resolver@@AEAAJHPEBGPEAPEAUIXMLDOMDocument2@@@Z`
- size: `896`
- prototype: `__int64 __fastcall(Resolver *this, int, const unsigned __int16 *, struct IXMLDOMDocument2 **)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config`

## callers

- `0x1800192ac`

## callees

- `0x1800012a4`
- `0x180002280`
- `0x180002d20`
- `0x18001c224`
- `0x18001dac4`
- `0x180026fa0`
- `0x180027aa0`
- `0x180027ea4`
- `0x1800280f8`
- `0x18002827c`
- `0x1800288b8`
- `0x18002a010`

## string_xrefs

- `0x18001c276`: `Resolver::BuildResultXml`
- `0x18001c2b7`: `Resolver::BuildResultXml`
- `0x18001c30b`: `Resolver::BuildResultXml`
- `0x18001c387`: `Resolver::BuildResultXml`
- `0x18001c442`: `Resolver::BuildResultXml`
- `0x18001c298`: `<?xml version="1.0" encoding="utf-8"?><Resolution/>`
- `0x18001c42d`: `<?xml version="1.0" encoding="utf-8"?><Script/>`

## pseudocode

```c
__int64 __fastcall Resolver::BuildResultXml(
        Resolver *this,
        int a2,
        const unsigned __int16 *a3,
        struct IXMLDOMDocument2 **a4)
{
  struct IXMLDOMDocument2 *v6; // r12
  struct IXMLDOMDocument2 *v7; // rsi
  unsigned __int16 *v8; // r15
  int v9; // ebx
  int RootNode; // eax
  struct IXMLDOMDocument2 *v11; // rdi
  int v12; // r8d
  int v13; // r9d
  const unsigned __int16 *v14; // rdx
  int v15; // eax
  int v16; // r8d
  int v17; // eax
  const unsigned __int16 *v18; // r9
  int v19; // eax
  Script *v20; // rcx
  int v21; // r8d
  unsigned __int16 *v23; // [rsp+30h] [rbp-30h] BYREF
  struct IXMLDOMElement *v24; // [rsp+38h] [rbp-28h] BYREF
  struct IXMLDOMDocument2 *v25; // [rsp+40h] [rbp-20h] BYREF
  struct IXMLDOMDocument2 *v26; // [rsp+48h] [rbp-18h] BYREF
  struct IXMLDOMElement *v27; // [rsp+50h] [rbp-10h] BYREF
  struct IXMLDOMDocument2 *v28; // [rsp+58h] [rbp-8h] BYREF

  v28 = 0;
  v6 = 0;
  v27 = 0;
  v7 = 0;
  v24 = 0;
  v8 = 0;
  v25 = 0;
  v26 = 0;
  v23 = 0;
  if ( !a4 )
  {
    v9 = -2147024809;
    SdpDebugTrace(1u, L"Resolver::BuildResultXml", 520, -2147024809);
    return (unsigned int)v9;
  }
  RootNode = SdpXmlCreate((OLECHAR *)L"<?xml version=\"1.0\" encoding=\"utf-8\"?><Resolution/>", &v28);
  v11 = v28;
  v9 = RootNode;
  if ( RootNode >= 0 )
  {
    RootNode = SdpXmlGetRootNode(v28, &v27);
    v9 = RootNode;
    if ( RootNode < 0 )
    {
      v12 = 526;
      goto LABEL_5;
    }
    v14 = (const unsigned __int16 *)*((_QWORD *)this + 2);
    if ( a3 )
    {
      v15 = SdpCatId(a3, v14, &v23);
      v9 = v15;
      if ( v15 < 0 )
      {
        v16 = 534;
LABEL_12:
        SdpDebugTrace(1u, L"Resolver::BuildResultXml", v16, v15);
        v8 = v23;
        goto LABEL_40;
      }
    }
    else
    {
      v15 = SdpStrCpy(&v23, v14);
      v9 = v15;
      if ( v15 < 0 )
      {
        v16 = 538;
        goto LABEL_12;
      }
    }
    v8 = v23;
    RootNode = SdpXmlCreateNode(v11, 0, L"ID", v23, &v24);
    v9 = RootNode;
    if ( RootNode < 0 )
    {
      v12 = 542;
      goto LABEL_5;
    }
    v17 = SdpBuildDisplayInformationXml((Resolver *)((char *)this + 32), a2, &v25);
    v9 = v17;
    if ( v17 < 0 )
    {
      SdpDebugTrace(1u, L"Resolver::BuildResultXml", 552, v17);
      v6 = v25;
      goto LABEL_40;
    }
    v6 = v25;
    RootNode = SdpXmlAppend(v11, 0, v25);
    v9 = RootNode;
    if ( RootNode < 0 )
    {
      v12 = 555;
      goto LABEL_5;
    }
    if ( v24 )
    {
      ((void (__fastcall *)(struct IXMLDOMElement *))v24->lpVtbl->Release)(v24);
      v24 = 0;
    }
    v18 = (const unsigned __int16 *)*((_QWORD *)this + 8);
    if ( !v18 )
    {
      v9 = -2147467261;
      v12 = 563;
      v13 = -2147467261;
      goto LABEL_6;
    }
    RootNode = SdpXmlCreateNode(v11, 0, L"RequiresConsent", v18, &v24);
    v9 = RootNode;
    if ( RootNode < 0 )
    {
      v12 = 569;
      goto LABEL_5;
    }
    v19 = SdpXmlCreate((OLECHAR *)L"<?xml version=\"1.0\" encoding=\"utf-8\"?><Script/>", &v26);
    v9 = v19;
    if ( v19 < 0 )
    {
      SdpDebugTrace(1u, L"Resolver::BuildResultXml", 576, v19);
      v7 = v26;
      goto LABEL_40;
    }
    v20 = (Script *)*((_QWORD *)this + 1);
    v7 = v26;
    if ( v20 )
    {
      if ( !v26 )
      {
        v9 = -2147024809;
        v21 = 291;
LABEL_34:
        SdpDebugTrace(1u, L"Script::Describe", v21, v9);
        v13 = v9;
        v12 = 580;
        goto LABEL_6;
      }
      v9 = Script::BuildResultXml(v20, v26);
      if ( v9 < 0 )
      {
        v21 = 294;
        goto LABEL_34;
      }
    }
    RootNode = SdpXmlAppend(v11, 0, v7);
    v9 = RootNode;
    if ( RootNode >= 0 )
    {
      RootNode = ((__int64 (__fastcall *)(struct IXMLDOMElement *, _QWORD, _QWORD))v27->lpVtbl->appendChild)(
                   v27,
                   *((_QWORD *)this + 3),
                   0);
      v9 = RootNode;
      if ( RootNode >= 0 )
      {
        *a4 = v11;
        ((void (__fastcall *)(struct IXMLDOMDocument2 *))v11->lpVtbl->AddRef)(v11);
        goto LABEL_40;
      }
      v12 = 591;
    }
    else
    {
      v12 = 584;
    }
    goto LABEL_5;
  }
  v12 = 523;
LABEL_5:
  v13 = RootNode;
LABEL_6:
  SdpDebugTrace(1u, L"Resolver::BuildResultXml", v12, v13);
LABEL_40:
  if ( v11 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v11->lpVtbl->Release)(v11);
  if ( v27 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v27->lpVtbl->Release)(v27);
  if ( v24 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v24->lpVtbl->Release)(v24);
  if ( v6 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v6->lpVtbl->Release)(v6);
  if ( v7 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v7->lpVtbl->Release)(v7);
  if ( v8 )
    operator delete(v8);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001c224  mov     [rsp-38h+arg_0], rbx
0x18001c229  mov     [rsp-38h+arg_18], r9
0x18001c22e  mov     [rsp-38h+arg_8], edx
0x18001c232  push    rbp
0x18001c233  push    rsi
0x18001c234  push    rdi
0x18001c235  push    r12
0x18001c237  push    r13
0x18001c239  push    r14
0x18001c23b  push    r15
0x18001c23d  mov     rbp, rsp
0x18001c240  sub     rsp, 60h
0x18001c244  mov     r14, rcx
0x18001c247  mov     r13, r8
0x18001c24a  xor     ecx, ecx
0x18001c24c  mov     [rbp+var_8], rcx
0x18001c250  mov     r12d, ecx
0x18001c253  mov     [rbp+var_10], rcx
0x18001c257  mov     esi, ecx
0x18001c259  mov     [rbp+var_28], rcx
0x18001c25d  mov     r15d, ecx
0x18001c260  mov     [rbp+var_20], rcx
0x18001c264  mov     [rbp+var_18], rcx
0x18001c268  mov     [rbp+var_30], rcx
0x18001c26c  test    r9, r9
0x18001c26f  jnz     short loc_18001C294
0x18001c271  mov     ebx, 80070057h
0x18001c276  lea     rdx, aResolverBuildr; "Resolver::BuildResultXml"
0x18001c27d  mov     r9d, ebx; int
0x18001c280  lea     ecx, [r15+1]; Level
0x18001c284  mov     r8d, 208h; int
0x18001c28a  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001c28f  jmp     loc_18001C58A
0x18001c294  lea     rdx, [rbp+var_8]; struct IXMLDOMDocument2 **
0x18001c298  lea     rcx, aXmlVersion10En_19; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x18001c29f  call    ?SdpXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; SdpXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x18001c2a4  mov     rdi, [rbp+var_8]
0x18001c2a8  mov     ebx, eax
0x18001c2aa  test    eax, eax
0x18001c2ac  jns     short loc_18001C2CD
0x18001c2ae  mov     r8d, 20Bh; int
0x18001c2b4  mov     r9d, eax; int
0x18001c2b7  lea     rdx, aResolverBuildr; "Resolver::BuildResultXml"
0x18001c2be  mov     ecx, 1; Level
0x18001c2c3  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001c2c8  jmp     loc_18001C516
0x18001c2cd  lea     rdx, [rbp+var_10]; struct IXMLDOMElement **
0x18001c2d1  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x18001c2d4  call    ?SdpXmlGetRootNode@@YAJPEAUIXMLDOMDocument2@@PEAPEAUIXMLDOMElement@@@Z; SdpXmlGetRootNode(IXMLDOMDocument2 *,IXMLDOMElement * *)
0x18001c2d9  mov     ebx, eax
0x18001c2db  test    eax, eax
0x18001c2dd  jns     short loc_18001C2E7
0x18001c2df  mov     r8d, 20Eh
0x18001c2e5  jmp     short loc_18001C2B4
0x18001c2e7  mov     rdx, [r14+10h]; unsigned __int16 *
0x18001c2eb  test    r13, r13
0x18001c2ee  jz      short loc_18001C325
0x18001c2f0  lea     r8, [rbp+var_30]; unsigned __int16 **
0x18001c2f4  mov     rcx, r13; unsigned __int16 *
0x18001c2f7  call    ?SdpCatId@@YAJPEBG0PEAPEAG@Z; SdpCatId(ushort const *,ushort const *,ushort * *)
0x18001c2fc  mov     ebx, eax
0x18001c2fe  test    eax, eax
0x18001c300  jns     short loc_18001C33C
0x18001c302  mov     r8d, 216h; int
0x18001c308  mov     r9d, eax; int
0x18001c30b  lea     rdx, aResolverBuildr; "Resolver::BuildResultXml"
0x18001c312  mov     ecx, 1; Level
0x18001c317  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001c31c  mov     r15, [rbp+var_30]
0x18001c320  jmp     loc_18001C516
0x18001c325  lea     rcx, [rbp+var_30]; unsigned __int16 **
0x18001c329  call    ?SdpStrCpy@@YAJPEAPEAGPEBG@Z; SdpStrCpy(ushort * *,ushort const *)
0x18001c32e  mov     ebx, eax
0x18001c330  test    eax, eax
0x18001c332  jns     short loc_18001C33C
0x18001c334  mov     r8d, 21Ah
0x18001c33a  jmp     short loc_18001C308
0x18001c33c  mov     r15, [rbp+var_30]
0x18001c340  lea     rax, [rbp+var_28]
0x18001c344  mov     r9, r15; unsigned __int16 *
0x18001c347  mov     [rsp+60h+var_40], rax; struct IXMLDOMElement **
0x18001c34c  lea     r8, aId; "ID"
0x18001c353  xor     edx, edx; struct IXMLDOMElement *
0x18001c355  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x18001c358  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001c35d  mov     ebx, eax
0x18001c35f  test    eax, eax
0x18001c361  jns     short loc_18001C36E
0x18001c363  mov     r8d, 21Eh
0x18001c369  jmp     loc_18001C2B4
0x18001c36e  mov     edx, [rbp+arg_8]; int
0x18001c371  lea     rcx, [r14+20h]; struct _SDIAG_DISPINFO *
0x18001c375  lea     r8, [rbp+var_20]; struct IXMLDOMDocument2 **
0x18001c379  call    ?SdpBuildDisplayInformationXml@@YAJPEAU_SDIAG_DISPINFO@@HPEAPEAUIXMLDOMDocument2@@@Z; SdpBuildDisplayInformationXml(_SDIAG_DISPINFO *,int,IXMLDOMDocument2 * *)
0x18001c37e  mov     ebx, eax
0x18001c380  test    eax, eax
0x18001c382  jns     short loc_18001C3A7
0x18001c384  mov     r9d, eax; int
0x18001c387  lea     rdx, aResolverBuildr; "Resolver::BuildResultXml"
0x18001c38e  mov     r8d, 228h; int
0x18001c394  mov     ecx, 1; Level
0x18001c399  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001c39e  mov     r12, [rbp+var_20]
0x18001c3a2  jmp     loc_18001C516
0x18001c3a7  mov     r12, [rbp+var_20]
0x18001c3ab  xor     edx, edx; struct IXMLDOMElement *
0x18001c3ad  mov     r8, r12; struct IXMLDOMDocument2 *
0x18001c3b0  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x18001c3b3  call    ?SdpXmlAppend@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@0@Z; SdpXmlAppend(IXMLDOMDocument2 *,IXMLDOMElement *,IXMLDOMDocument2 *)
0x18001c3b8  mov     ebx, eax
0x18001c3ba  test    eax, eax
0x18001c3bc  jns     short loc_18001C3C9
0x18001c3be  mov     r8d, 22Bh
0x18001c3c4  jmp     loc_18001C2B4
0x18001c3c9  mov     rcx, [rbp+var_28]
0x18001c3cd  test    rcx, rcx
0x18001c3d0  jz      short loc_18001C3E2
0x18001c3d2  mov     rax, [rcx]
0x18001c3d5  mov     rax, [rax+10h]
0x18001c3d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c3de  mov     [rbp+var_28], rsi
0x18001c3e2  mov     r9, [r14+40h]; unsigned __int16 *
0x18001c3e6  test    r9, r9
0x18001c3e9  jnz     short loc_18001C3FE
0x18001c3eb  mov     ebx, 80004003h
0x18001c3f0  mov     r8d, 233h
0x18001c3f6  mov     r9d, ebx
0x18001c3f9  jmp     loc_18001C2B7
0x18001c3fe  lea     rax, [rbp+var_28]
0x18001c402  xor     edx, edx; struct IXMLDOMElement *
0x18001c404  lea     r8, aRequiresconsen; "RequiresConsent"
0x18001c40b  mov     [rsp+60h+var_40], rax; struct IXMLDOMElement **
0x18001c410  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x18001c413  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001c418  mov     ebx, eax
0x18001c41a  test    eax, eax
0x18001c41c  jns     short loc_18001C429
0x18001c41e  mov     r8d, 239h
0x18001c424  jmp     loc_18001C2B4
0x18001c429  lea     rdx, [rbp+var_18]; struct IXMLDOMDocument2 **
0x18001c42d  lea     rcx, aXmlVersion10En_17; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x18001c434  call    ?SdpXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; SdpXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x18001c439  mov     ebx, eax
0x18001c43b  test    eax, eax
0x18001c43d  jns     short loc_18001C462
0x18001c43f  mov     r9d, eax; int
0x18001c442  lea     rdx, aResolverBuildr; "Resolver::BuildResultXml"
0x18001c449  mov     r8d, 240h; int
0x18001c44f  mov     ecx, 1; Level
0x18001c454  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001c459  mov     rsi, [rbp+var_18]
0x18001c45d  jmp     loc_18001C516
0x18001c462  mov     rcx, [r14+8]; this
0x18001c466  mov     rsi, [rbp+var_18]
0x18001c46a  test    rcx, rcx
0x18001c46d  jz      short loc_18001C4B7
0x18001c46f  test    rsi, rsi
0x18001c472  jnz     short loc_18001C481
0x18001c474  mov     ebx, 80070057h
0x18001c479  mov     r8d, 123h
0x18001c47f  jmp     short loc_18001C495
0x18001c481  mov     rdx, rsi; struct IXMLDOMDocument2 *
0x18001c484  call    ?BuildResultXml@Script@@AEAAJPEAUIXMLDOMDocument2@@@Z; Script::BuildResultXml(IXMLDOMDocument2 *)
0x18001c489  mov     ebx, eax
0x18001c48b  test    eax, eax
0x18001c48d  jns     short loc_18001C4B7
0x18001c48f  mov     r8d, 126h; int
0x18001c495  lea     rdx, aScriptDescribe; "Script::Describe"
0x18001c49c  mov     r9d, ebx; int
0x18001c49f  mov     ecx, 1; Level
0x18001c4a4  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001c4a9  mov     r9d, ebx
0x18001c4ac  mov     r8d, 244h
0x18001c4b2  jmp     loc_18001C2B7
0x18001c4b7  mov     r8, rsi; struct IXMLDOMDocument2 *
0x18001c4ba  xor     edx, edx; struct IXMLDOMElement *
0x18001c4bc  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x18001c4bf  call    ?SdpXmlAppend@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@0@Z; SdpXmlAppend(IXMLDOMDocument2 *,IXMLDOMElement *,IXMLDOMDocument2 *)
0x18001c4c4  mov     ebx, eax
0x18001c4c6  test    eax, eax
0x18001c4c8  jns     short loc_18001C4D5
0x18001c4ca  mov     r8d, 248h
0x18001c4d0  jmp     loc_18001C2B4
0x18001c4d5  mov     rcx, [rbp+var_10]
0x18001c4d9  xor     r8d, r8d
0x18001c4dc  mov     rdx, [r14+18h]
0x18001c4e0  mov     rax, [rcx]
0x18001c4e3  mov     rax, [rax+0A8h]
0x18001c4ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c4ef  mov     ebx, eax
0x18001c4f1  test    eax, eax
0x18001c4f3  jns     short loc_18001C500
0x18001c4f5  mov     r8d, 24Fh
0x18001c4fb  jmp     loc_18001C2B4
0x18001c500  mov     rax, [rbp+arg_18]
0x18001c504  mov     rcx, rdi
0x18001c507  mov     [rax], rdi
0x18001c50a  mov     rax, [rdi]
0x18001c50d  mov     rax, [rax+8]
0x18001c511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c516  test    rdi, rdi
0x18001c519  jz      short loc_18001C52A
0x18001c51b  mov     rax, [rdi]
0x18001c51e  mov     rcx, rdi
0x18001c521  mov     rax, [rax+10h]
0x18001c525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c52a  mov     rcx, [rbp+var_10]
0x18001c52e  test    rcx, rcx
0x18001c531  jz      short loc_18001C53F
0x18001c533  mov     rax, [rcx]
0x18001c536  mov     rax, [rax+10h]
0x18001c53a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c53f  mov     rcx, [rbp+var_28]
0x18001c543  test    rcx, rcx
0x18001c546  jz      short loc_18001C554
0x18001c548  mov     rax, [rcx]
0x18001c54b  mov     rax, [rax+10h]
0x18001c54f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c554  test    r12, r12
0x18001c557  jz      short loc_18001C569
0x18001c559  mov     rax, [r12]
0x18001c55d  mov     rcx, r12
0x18001c560  mov     rax, [rax+10h]
0x18001c564  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c569  test    rsi, rsi
0x18001c56c  jz      short loc_18001C57D
0x18001c56e  mov     rax, [rsi]
0x18001c571  mov     rcx, rsi
0x18001c574  mov     rax, [rax+10h]
0x18001c578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c57d  test    r15, r15
0x18001c580  jz      short loc_18001C58A
0x18001c582  mov     rcx, r15; Block
0x18001c585  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001c58a  mov     eax, ebx
0x18001c58c  mov     rbx, [rsp+60h+arg_0]
0x18001c594  add     rsp, 60h
0x18001c598  pop     r15
0x18001c59a  pop     r14
0x18001c59c  pop     r13
0x18001c59e  pop     r12
0x18001c5a0  pop     rdi
0x18001c5a1  pop     rsi
0x18001c5a2  pop     rbp
0x18001c5a3  retn
```
