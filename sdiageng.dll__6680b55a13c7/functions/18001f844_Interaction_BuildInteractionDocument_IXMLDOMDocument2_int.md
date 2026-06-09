# Interaction::BuildInteractionDocument(IXMLDOMDocument2 * *,int)

- ea: `0x18001f844`
- end: `0x18001fc07`
- name: `?BuildInteractionDocument@Interaction@@IEAAJPEAPEAUIXMLDOMDocument2@@H@Z`
- size: `963`
- prototype: `__int64 __fastcall(Interaction *this, struct IXMLDOMDocument2 **, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017c90`
- `0x180020314`

## callees

- `0x180002d20`
- `0x18000312c`
- `0x18001f844`
- `0x180026fa0`
- `0x180027ea4`
- `0x18002827c`
- `0x1800288b8`
- `0x18002a010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001fa5b`
- `OLEAUT32!__imp_SysAllocString` at `0x18001fa5b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001fbe7`
- `OLEAUT32!__imp_SysFreeString` at `0x18001fbe7`

## pseudocode

```c
__int64 __fastcall Interaction::BuildInteractionDocument(Interaction *this, struct IXMLDOMDocument2 **a2, int a3)
{
  struct IXMLDOMElement *v3; // rdi
  struct IXMLDOMDocument2 *v4; // r13
  struct IXMLDOMDocument2 *v5; // r12
  OLECHAR *v6; // r15
  int v9; // ebx
  int v10; // r8d
  int v11; // r9d
  int v12; // eax
  int RootNode; // eax
  int v14; // eax
  int v15; // r8d
  int v16; // r9d
  int v17; // eax
  int v18; // eax
  int v19; // eax
  __int64 v20; // rax
  int v21; // r8d
  const OLECHAR *v22; // rcx
  BSTR v23; // rax
  OLECHAR *v24; // rsi
  int v25; // eax
  int v26; // r8d
  int v27; // eax
  struct IXMLDOMDocument2 *v28; // rcx
  struct IXMLDOMElement *v30; // [rsp+30h] [rbp-20h] BYREF
  struct IXMLDOMDocument2 *v31; // [rsp+38h] [rbp-18h] BYREF
  struct IXMLDOMDocument2 *v32; // [rsp+40h] [rbp-10h] BYREF
  struct IXMLDOMElement *v33; // [rsp+48h] [rbp-8h] BYREF
  struct IXMLDOMDocument2 *v36; // [rsp+A8h] [rbp+58h] BYREF

  v3 = 0;
  v31 = 0;
  v4 = 0;
  v33 = 0;
  v5 = 0;
  v30 = 0;
  v6 = 0;
  v36 = 0;
  v32 = 0;
  if ( !a2 )
  {
    v9 = -2147024809;
    v10 = 693;
    v11 = -2147024809;
LABEL_3:
    SdpDebugTrace(1u, L"Interaction::BuildInteractionDocument", v10, v11);
    goto LABEL_40;
  }
  v12 = (*(__int64 (__fastcall **)(Interaction *, struct IXMLDOMDocument2 **))(*(_QWORD *)this + 32LL))(this, &v31);
  v9 = v12;
  if ( v12 < 0 )
  {
    v11 = v12;
    v10 = 700;
    goto LABEL_3;
  }
  RootNode = SdpXmlGetRootNode(v31, &v33);
  v9 = RootNode;
  if ( RootNode < 0 )
  {
    v11 = RootNode;
    v10 = 703;
    goto LABEL_3;
  }
  v14 = SdpXmlCreateNode(v31, 0, L"ID", 0, &v30);
  v9 = v14;
  if ( v14 < 0 )
  {
    v15 = 710;
LABEL_10:
    v16 = v14;
LABEL_11:
    SdpDebugTrace(1u, L"Interaction::BuildInteractionDocument", v15, v16);
    v3 = v30;
    goto LABEL_40;
  }
  if ( !*((_QWORD *)this + 2) )
  {
    v9 = -2147467261;
    v15 = 712;
    v16 = -2147467261;
    goto LABEL_11;
  }
  v3 = v30;
  v17 = ((__int64 (__fastcall *)(struct IXMLDOMElement *))v30->lpVtbl->put_text)(v30);
  v9 = v17;
  if ( v17 < 0 )
  {
    v11 = v17;
    v10 = 714;
    goto LABEL_3;
  }
  v18 = SdpBuildDisplayInformationXml((Interaction *)((char *)this + 24), a3, &v36);
  v9 = v18;
  if ( v18 < 0 )
  {
    SdpDebugTrace(1u, L"Interaction::BuildInteractionDocument", 724, v18);
    v4 = v36;
    goto LABEL_40;
  }
  v4 = v36;
  v19 = SdpXmlAppend(v31, 0, v36);
  v9 = v19;
  if ( v19 < 0 )
  {
    v11 = v19;
    v10 = 727;
    goto LABEL_3;
  }
  ((void (__fastcall *)(struct IXMLDOMElement *))v3->lpVtbl->Release)(v3);
  v30 = 0;
  v14 = SdpXmlCreateNode(v31, 0, L"Dynamic", 0, &v30);
  v9 = v14;
  if ( v14 < 0 )
  {
    v15 = 735;
    goto LABEL_10;
  }
  v20 = *(_QWORD *)this;
  LODWORD(v36) = 0;
  v9 = (*(__int64 (__fastcall **)(Interaction *, struct IXMLDOMDocument2 **))(v20 + 8))(this, &v36);
  if ( v9 < 0 )
  {
    v21 = 790;
LABEL_28:
    SdpDebugTrace(1u, L"Interaction::BuildDynamicString", v21, v9);
    v16 = v9;
    v15 = 738;
    goto LABEL_11;
  }
  v22 = L"true";
  if ( !(_DWORD)v36 )
    v22 = L"false";
  v23 = SysAllocString(v22);
  v24 = v23;
  if ( !v23 )
  {
    v9 = -2147024882;
    v21 = 798;
    goto LABEL_28;
  }
  v3 = v30;
  v25 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, BSTR))v30->lpVtbl->put_text)(v30, v23);
  v9 = v25;
  if ( v25 >= 0 )
  {
    v27 = SdpBuildParameterXml((Interaction *)((char *)this + 64), a3, &v32);
    v9 = v27;
    if ( v27 < 0 )
    {
      SdpDebugTrace(1u, L"Interaction::BuildInteractionDocument", 748, v27);
      v5 = v32;
      goto LABEL_39;
    }
    v5 = v32;
    v25 = SdpXmlAppend(v31, 0, v32);
    v9 = v25;
    if ( v25 >= 0 )
    {
      v25 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, _QWORD, _QWORD))v33->lpVtbl->appendChild)(
              v33,
              *((_QWORD *)this + 7),
              0);
      v9 = v25;
      if ( v25 >= 0 )
      {
        v28 = v31;
        *a2 = v31;
        ((void (__fastcall *)(struct IXMLDOMDocument2 *))v28->lpVtbl->AddRef)(v28);
        goto LABEL_39;
      }
      v26 = 758;
    }
    else
    {
      v26 = 751;
    }
  }
  else
  {
    v26 = 741;
  }
  SdpDebugTrace(1u, L"Interaction::BuildInteractionDocument", v26, v25);
LABEL_39:
  v6 = v24;
LABEL_40:
  if ( v31 )
  {
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v31->lpVtbl->Release)(v31);
    v31 = 0;
  }
  if ( v33 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v33->lpVtbl->Release)(v33);
  if ( v3 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v3->lpVtbl->Release)(v3);
  if ( v4 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v4->lpVtbl->Release)(v4);
  if ( v5 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v5->lpVtbl->Release)(v5);
  if ( v6 )
    SysFreeString(v6);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001f844  mov     [rsp-38h+arg_0], rbx
0x18001f849  mov     [rsp-38h+arg_10], r8d
0x18001f84e  mov     [rsp-38h+arg_8], rdx
0x18001f853  push    rbp
0x18001f854  push    rsi
0x18001f855  push    rdi
0x18001f856  push    r12
0x18001f858  push    r13
0x18001f85a  push    r14
0x18001f85c  push    r15
0x18001f85e  mov     rbp, rsp
0x18001f861  sub     rsp, 50h
0x18001f865  xor     edi, edi
0x18001f867  mov     [rbp+var_18], 0
0x18001f86f  xor     r13d, r13d
0x18001f872  mov     [rbp+var_8], 0
0x18001f87a  xor     r12d, r12d
0x18001f87d  mov     [rbp+var_20], rdi
0x18001f881  xor     r15d, r15d
0x18001f884  mov     [rbp+arg_18], r13
0x18001f888  mov     [rbp+var_10], r12
0x18001f88c  mov     esi, r8d
0x18001f88f  mov     r14, rcx
0x18001f892  test    rdx, rdx
0x18001f895  jnz     short loc_18001F8BB
0x18001f897  mov     ebx, 80070057h
0x18001f89c  mov     r8d, 2B5h; int
0x18001f8a2  mov     r9d, ebx; int
0x18001f8a5  lea     rdx, aInteractionBui; "Interaction::BuildInteractionDocument"
0x18001f8ac  mov     ecx, 1; Level
0x18001f8b1  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001f8b6  jmp     loc_18001FB6F
0x18001f8bb  mov     rax, [rcx]
0x18001f8be  lea     rdx, [rbp+var_18]
0x18001f8c2  mov     rax, [rax+20h]
0x18001f8c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f8cb  mov     ebx, eax
0x18001f8cd  test    eax, eax
0x18001f8cf  jns     short loc_18001F8DC
0x18001f8d1  mov     r9d, eax
0x18001f8d4  mov     r8d, 2BCh
0x18001f8da  jmp     short loc_18001F8A5
0x18001f8dc  mov     rcx, [rbp+var_18]; struct IXMLDOMDocument2 *
0x18001f8e0  lea     rdx, [rbp+var_8]; struct IXMLDOMElement **
0x18001f8e4  call    ?SdpXmlGetRootNode@@YAJPEAUIXMLDOMDocument2@@PEAPEAUIXMLDOMElement@@@Z; SdpXmlGetRootNode(IXMLDOMDocument2 *,IXMLDOMElement * *)
0x18001f8e9  mov     ebx, eax
0x18001f8eb  test    eax, eax
0x18001f8ed  jns     short loc_18001F8FA
0x18001f8ef  mov     r9d, eax
0x18001f8f2  mov     r8d, 2BFh
0x18001f8f8  jmp     short loc_18001F8A5
0x18001f8fa  mov     rcx, [rbp+var_18]; struct IXMLDOMDocument2 *
0x18001f8fe  lea     rax, [rbp+var_20]
0x18001f902  xor     r9d, r9d; unsigned __int16 *
0x18001f905  mov     [rsp+50h+var_30], rax; struct IXMLDOMElement **
0x18001f90a  lea     r8, aId; "ID"
0x18001f911  xor     edx, edx; struct IXMLDOMElement *
0x18001f913  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001f918  mov     ebx, eax
0x18001f91a  test    eax, eax
0x18001f91c  jns     short loc_18001F941
0x18001f91e  mov     r8d, 2C6h; int
0x18001f924  mov     r9d, eax; int
0x18001f927  lea     rdx, aInteractionBui; "Interaction::BuildInteractionDocument"
0x18001f92e  mov     ecx, 1; Level
0x18001f933  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001f938  mov     rdi, [rbp+var_20]
0x18001f93c  jmp     loc_18001FB6F
0x18001f941  mov     rdx, [r14+10h]
0x18001f945  test    rdx, rdx
0x18001f948  jnz     short loc_18001F95A
0x18001f94a  mov     ebx, 80004003h
0x18001f94f  mov     r8d, 2C8h
0x18001f955  mov     r9d, ebx
0x18001f958  jmp     short loc_18001F927
0x18001f95a  mov     rdi, [rbp+var_20]
0x18001f95e  mov     rcx, rdi
0x18001f961  mov     rax, [rdi]
0x18001f964  mov     rax, [rax+0D8h]
0x18001f96b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f970  mov     ebx, eax
0x18001f972  test    eax, eax
0x18001f974  jns     short loc_18001F984
0x18001f976  mov     r9d, eax
0x18001f979  mov     r8d, 2CAh
0x18001f97f  jmp     loc_18001F8A5
0x18001f984  lea     rcx, [r14+18h]; struct _SDIAG_DISPINFO *
0x18001f988  mov     edx, esi; int
0x18001f98a  lea     r8, [rbp+arg_18]; struct IXMLDOMDocument2 **
0x18001f98e  call    ?SdpBuildDisplayInformationXml@@YAJPEAU_SDIAG_DISPINFO@@HPEAPEAUIXMLDOMDocument2@@@Z; SdpBuildDisplayInformationXml(_SDIAG_DISPINFO *,int,IXMLDOMDocument2 * *)
0x18001f993  xor     esi, esi
0x18001f995  mov     ebx, eax
0x18001f997  test    eax, eax
0x18001f999  jns     short loc_18001F9BC
0x18001f99b  mov     r9d, eax; int
0x18001f99e  lea     rdx, aInteractionBui; "Interaction::BuildInteractionDocument"
0x18001f9a5  mov     r8d, 2D4h; int
0x18001f9ab  lea     ecx, [rsi+1]; Level
0x18001f9ae  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001f9b3  mov     r13, [rbp+arg_18]
0x18001f9b7  jmp     loc_18001FB6F
0x18001f9bc  mov     r13, [rbp+arg_18]
0x18001f9c0  xor     edx, edx; struct IXMLDOMElement *
0x18001f9c2  mov     rcx, [rbp+var_18]; struct IXMLDOMDocument2 *
0x18001f9c6  mov     r8, r13; struct IXMLDOMDocument2 *
0x18001f9c9  call    ?SdpXmlAppend@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@0@Z; SdpXmlAppend(IXMLDOMDocument2 *,IXMLDOMElement *,IXMLDOMDocument2 *)
0x18001f9ce  mov     ebx, eax
0x18001f9d0  test    eax, eax
0x18001f9d2  jns     short loc_18001F9E2
0x18001f9d4  mov     r9d, eax
0x18001f9d7  mov     r8d, 2D7h
0x18001f9dd  jmp     loc_18001F8A5
0x18001f9e2  mov     rax, [rdi]
0x18001f9e5  mov     rcx, rdi
0x18001f9e8  mov     rax, [rax+10h]
0x18001f9ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f9f1  mov     rcx, [rbp+var_18]; struct IXMLDOMDocument2 *
0x18001f9f5  lea     rax, [rbp+var_20]
0x18001f9f9  xor     r9d, r9d; unsigned __int16 *
0x18001f9fc  mov     [rsp+50h+var_30], rax; struct IXMLDOMElement **
0x18001fa01  lea     r8, aDynamic; "Dynamic"
0x18001fa08  mov     [rbp+var_20], rsi
0x18001fa0c  xor     edx, edx; struct IXMLDOMElement *
0x18001fa0e  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001fa13  mov     ebx, eax
0x18001fa15  test    eax, eax
0x18001fa17  jns     short loc_18001FA24
0x18001fa19  mov     r8d, 2DFh
0x18001fa1f  jmp     loc_18001F924
0x18001fa24  mov     rax, [r14]
0x18001fa27  lea     rdx, [rbp+arg_18]
0x18001fa2b  mov     rcx, r14
0x18001fa2e  mov     dword ptr [rbp+arg_18], esi
0x18001fa31  mov     rax, [rax+8]
0x18001fa35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fa3a  mov     ebx, eax
0x18001fa3c  test    eax, eax
0x18001fa3e  jns     short loc_18001FA48
0x18001fa40  mov     r8d, 316h
0x18001fa46  jmp     short loc_18001FA74
0x18001fa48  lea     rcx, aTrue; "true"
0x18001fa4f  cmp     dword ptr [rbp+arg_18], esi
0x18001fa52  jnz     short loc_18001FA5B
0x18001fa54  lea     rcx, aFalse; "false"
0x18001fa5b  call    cs:__imp_SysAllocString
0x18001fa61  mov     rsi, rax
0x18001fa64  test    rax, rax
0x18001fa67  jnz     short loc_18001FA96
0x18001fa69  mov     ebx, 8007000Eh
0x18001fa6e  mov     r8d, 31Eh; int
0x18001fa74  mov     r9d, ebx; int
0x18001fa77  lea     rdx, aInteractionBui_0; "Interaction::BuildDynamicString"
0x18001fa7e  mov     ecx, 1; Level
0x18001fa83  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001fa88  mov     r9d, ebx
0x18001fa8b  mov     r8d, 2E2h
0x18001fa91  jmp     loc_18001F927
0x18001fa96  mov     rdi, [rbp+var_20]
0x18001fa9a  mov     rdx, rsi
0x18001fa9d  mov     rcx, rdi
0x18001faa0  mov     rax, [rdi]
0x18001faa3  mov     rax, [rax+0D8h]
0x18001faaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001faaf  mov     ebx, eax
0x18001fab1  test    eax, eax
0x18001fab3  jns     short loc_18001FAD4
0x18001fab5  mov     r8d, 2E5h; int
0x18001fabb  mov     r9d, eax; int
0x18001fabe  lea     rdx, aInteractionBui; "Interaction::BuildInteractionDocument"
0x18001fac5  mov     ecx, 1; Level
0x18001faca  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001facf  jmp     loc_18001FB6C
0x18001fad4  mov     edx, [rbp+arg_10]; int
0x18001fad7  lea     rcx, [r14+40h]; struct _SDIAG_PARAMSET *
0x18001fadb  lea     r8, [rbp+var_10]; struct IXMLDOMDocument2 **
0x18001fadf  call    ?SdpBuildParameterXml@@YAJPEAU_SDIAG_PARAMSET@@HPEAPEAUIXMLDOMDocument2@@@Z; SdpBuildParameterXml(_SDIAG_PARAMSET *,int,IXMLDOMDocument2 * *)
0x18001fae4  mov     ebx, eax
0x18001fae6  test    eax, eax
0x18001fae8  jns     short loc_18001FB0A
0x18001faea  mov     r9d, eax; int
0x18001faed  lea     rdx, aInteractionBui; "Interaction::BuildInteractionDocument"
0x18001faf4  mov     r8d, 2ECh; int
0x18001fafa  mov     ecx, 1; Level
0x18001faff  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001fb04  mov     r12, [rbp+var_10]
0x18001fb08  jmp     short loc_18001FB6C
0x18001fb0a  mov     r12, [rbp+var_10]
0x18001fb0e  xor     edx, edx; struct IXMLDOMElement *
0x18001fb10  mov     rcx, [rbp+var_18]; struct IXMLDOMDocument2 *
0x18001fb14  mov     r8, r12; struct IXMLDOMDocument2 *
0x18001fb17  call    ?SdpXmlAppend@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@0@Z; SdpXmlAppend(IXMLDOMDocument2 *,IXMLDOMElement *,IXMLDOMDocument2 *)
0x18001fb1c  mov     ebx, eax
0x18001fb1e  test    eax, eax
0x18001fb20  jns     short loc_18001FB2A
0x18001fb22  mov     r8d, 2EFh
0x18001fb28  jmp     short loc_18001FABB
0x18001fb2a  mov     rcx, [rbp+var_8]
0x18001fb2e  xor     r8d, r8d
0x18001fb31  mov     rdx, [r14+38h]
0x18001fb35  mov     rax, [rcx]
0x18001fb38  mov     rax, [rax+0A8h]
0x18001fb3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb44  mov     ebx, eax
0x18001fb46  test    eax, eax
0x18001fb48  jns     short loc_18001FB55
0x18001fb4a  mov     r8d, 2F6h
0x18001fb50  jmp     loc_18001FABB
0x18001fb55  mov     rcx, [rbp+var_18]
0x18001fb59  mov     rax, [rbp+arg_8]
0x18001fb5d  mov     [rax], rcx
0x18001fb60  mov     rax, [rcx]
0x18001fb63  mov     rax, [rax+8]
0x18001fb67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb6c  mov     r15, rsi
0x18001fb6f  mov     rcx, [rbp+var_18]
0x18001fb73  test    rcx, rcx
0x18001fb76  jz      short loc_18001FB8C
0x18001fb78  mov     rax, [rcx]
0x18001fb7b  mov     rax, [rax+10h]
0x18001fb7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb84  mov     [rbp+var_18], 0
0x18001fb8c  mov     rcx, [rbp+var_8]
0x18001fb90  test    rcx, rcx
0x18001fb93  jz      short loc_18001FBA1
0x18001fb95  mov     rax, [rcx]
0x18001fb98  mov     rax, [rax+10h]
0x18001fb9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fba1  test    rdi, rdi
0x18001fba4  jz      short loc_18001FBB5
0x18001fba6  mov     rax, [rdi]
0x18001fba9  mov     rcx, rdi
0x18001fbac  mov     rax, [rax+10h]
0x18001fbb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fbb5  test    r13, r13
0x18001fbb8  jz      short loc_18001FBCA
0x18001fbba  mov     rax, [r13+0]
0x18001fbbe  mov     rcx, r13
0x18001fbc1  mov     rax, [rax+10h]
0x18001fbc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fbca  test    r12, r12
0x18001fbcd  jz      short loc_18001FBDF
0x18001fbcf  mov     rax, [r12]
0x18001fbd3  mov     rcx, r12
0x18001fbd6  mov     rax, [rax+10h]
0x18001fbda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fbdf  test    r15, r15
0x18001fbe2  jz      short loc_18001FBED
0x18001fbe4  mov     rcx, r15; bstrString
0x18001fbe7  call    cs:__imp_SysFreeString
0x18001fbed  mov     eax, ebx
0x18001fbef  mov     rbx, [rsp+50h+arg_0]
0x18001fbf7  add     rsp, 50h
0x18001fbfb  pop     r15
0x18001fbfd  pop     r14
0x18001fbff  pop     r13
0x18001fc01  pop     r12
0x18001fc03  pop     rdi
0x18001fc04  pop     rsi
0x18001fc05  pop     rbp
0x18001fc06  retn
```
