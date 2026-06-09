# Rootcause::BuildResultXml(Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *,IXMLDOMDocument2 * *)

- ea: `0x18001955c`
- end: `0x1800199be`
- name: `?BuildResultXml@Rootcause@@AEAAJPEAU_SDIAG_ROOTCAUSE_INSTANCE@1@PEAPEAUIXMLDOMDocument2@@@Z`
- size: `1122`
- prototype: `__int64 __fastcall(Rootcause *__hidden this, struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *, struct IXMLDOMDocument2 **)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x1800181a4`
- `0x18001b4d4`

## callees

- `0x1800012a4`
- `0x180002280`
- `0x180002d20`
- `0x18000312c`
- `0x180005ad0`
- `0x1800192ac`
- `0x18001955c`
- `0x18001b070`
- `0x180026fa0`
- `0x180027aa0`
- `0x180027ea4`
- `0x1800280f8`
- `0x18002827c`
- `0x1800288b8`
- `0x18002a010`

## string_xrefs

- `0x1800195b1`: `Rootcause::BuildResultXml`
- `0x1800195f3`: `Rootcause::BuildResultXml`
- `0x180019755`: `Rootcause::BuildResultXml`
- `0x180019805`: `Rootcause::BuildResultXml`
- `0x180019892`: `Rootcause::BuildResultXml`
- `0x1800195d4`: `<?xml version="1.0" encoding="utf-8"?><Rootcause/>`

## pseudocode

```c
__int64 __fastcall Rootcause::BuildResultXml(
        Rootcause *this,
        struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *a2,
        struct IXMLDOMDocument2 **a3)
{
  struct IXMLDOMDocument2 *v3; // r12
  struct IXMLDOMDocument2 *v4; // r13
  struct IXMLDOMDocument2 *v5; // r15
  unsigned int v8; // ebx
  int RootNode; // eax
  struct IXMLDOMDocument2 *v10; // rsi
  int v11; // r8d
  int v12; // r9d
  const unsigned __int16 *v13; // rdx
  __int64 v14; // rcx
  unsigned __int16 *v15; // rax
  bool v16; // zf
  wchar_t *v17; // rax
  struct _SDIAG_DISPINFO *v18; // rax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // r8d
  void *Block; // [rsp+30h] [rbp-30h] BYREF
  struct IXMLDOMDocument2 *v25; // [rsp+38h] [rbp-28h] BYREF
  struct IXMLDOMDocument2 *v26; // [rsp+40h] [rbp-20h] BYREF
  struct IXMLDOMElement *v27; // [rsp+48h] [rbp-18h] BYREF
  struct IXMLDOMDocument2 *v28; // [rsp+50h] [rbp-10h] BYREF
  unsigned __int16 *v29; // [rsp+58h] [rbp-8h] BYREF
  struct IXMLDOMDocument2 *v31; // [rsp+B8h] [rbp+58h] BYREF

  v3 = 0;
  v28 = 0;
  v4 = 0;
  v26 = 0;
  v5 = 0;
  v25 = 0;
  v31 = 0;
  v27 = 0;
  Block = 0;
  v29 = 0;
  if ( !a3 )
  {
    v8 = -2147024809;
    SdpDebugTrace(1u, L"Rootcause::BuildResultXml", 1274, -2147024809);
    goto LABEL_60;
  }
  RootNode = SdpXmlCreate((OLECHAR *)L"<?xml version=\"1.0\" encoding=\"utf-8\"?><Rootcause/>", &v28);
  v10 = v28;
  v8 = RootNode;
  if ( RootNode >= 0 )
  {
    RootNode = SdpXmlGetRootNode(v28, &v27);
    v8 = RootNode;
    if ( RootNode < 0 )
    {
      v11 = 1280;
      goto LABEL_5;
    }
    if ( !*((_QWORD *)this + 5) )
    {
      v12 = -2147467261;
      v11 = 1282;
      v8 = -2147467261;
      goto LABEL_6;
    }
    if ( a2 )
    {
      v13 = (const unsigned __int16 *)*((_QWORD *)a2 + 2);
      if ( !v13 )
      {
        v12 = -2147467261;
        v11 = 1285;
        v8 = -2147467261;
        goto LABEL_6;
      }
      RootNode = SdpCatId(*((const unsigned __int16 **)this + 5), v13, (unsigned __int16 **)&Block);
      v8 = RootNode;
      if ( RootNode < 0 )
      {
        v11 = 1288;
        goto LABEL_5;
      }
      RootNode = Rootcause::StatusToString(v14, *((unsigned int *)a2 + 6), &v29);
      v8 = RootNode;
      if ( RootNode < 0 )
      {
        v11 = 1291;
        goto LABEL_5;
      }
      v15 = v29;
    }
    else
    {
      RootNode = SdpStrCpy((unsigned __int16 **)&Block, *((const unsigned __int16 **)this + 5));
      v8 = RootNode;
      if ( RootNode < 0 )
      {
        v11 = 1295;
        goto LABEL_5;
      }
      v15 = L"Not Checked";
    }
    v16 = *((_QWORD *)this + 3) == 0;
    v29 = v15;
    v17 = (wchar_t *)L"true";
    if ( v16 )
      v17 = (wchar_t *)L"false";
    v28 = (struct IXMLDOMDocument2 *)v17;
    RootNode = SdpXmlCreateNode(v10, 0, L"ID", (const unsigned __int16 *)Block, 0);
    v8 = RootNode;
    if ( RootNode < 0 )
    {
      v11 = 1311;
      goto LABEL_5;
    }
    v18 = (Rootcause *)((char *)this + 56);
    if ( a2 )
    {
      RootNode = SdpUpdateParamSet(*((SAFEARRAY **)a2 + 4), *((SAFEARRAY **)a2 + 5), (Rootcause *)((char *)this + 72));
      v8 = RootNode;
      if ( RootNode < 0 )
      {
        v11 = 1321;
        goto LABEL_5;
      }
      v18 = (Rootcause *)((char *)this + 56);
    }
    v19 = SdpBuildDisplayInformationXml(v18, a2 == 0, &v25);
    v8 = v19;
    if ( v19 < 0 )
    {
      SdpDebugTrace(1u, L"Rootcause::BuildResultXml", 1327, v19);
      v4 = v25;
      goto LABEL_56;
    }
    v4 = v25;
    RootNode = SdpXmlAppend(v10, 0, v25);
    v8 = RootNode;
    if ( RootNode < 0 )
    {
      v11 = 1330;
      goto LABEL_5;
    }
    RootNode = SdpXmlCreateNode(v10, 0, L"Status", v29, 0);
    v8 = RootNode;
    if ( RootNode < 0 )
    {
      v11 = 1337;
      goto LABEL_5;
    }
    RootNode = SdpXmlCreateNode(v10, 0, L"Verifiable", (const unsigned __int16 *)v28, 0);
    v8 = RootNode;
    if ( RootNode < 0 )
    {
      v11 = 1344;
      goto LABEL_5;
    }
    v20 = Rootcause::BuildResultResolutionsXml(this, (struct tagSAFEARRAY **)a2, &v26);
    v8 = v20;
    if ( v20 < 0 )
    {
      SdpDebugTrace(1u, L"Rootcause::BuildResultXml", 1351, v20);
      v3 = v26;
      goto LABEL_56;
    }
    v3 = v26;
    RootNode = SdpXmlAppend(v10, 0, v26);
    v8 = RootNode;
    if ( RootNode < 0 )
    {
      v11 = 1354;
      goto LABEL_5;
    }
    if ( a2 && *((_DWORD *)a2 + 6) == 2 )
    {
      RootNode = SdpUpdateParamSet(*((SAFEARRAY **)a2 + 4), *((SAFEARRAY **)a2 + 5), (Rootcause *)((char *)this + 88));
      v8 = RootNode;
      if ( RootNode < 0 )
      {
        v11 = 1364;
        goto LABEL_5;
      }
      v21 = SdpBuildParameterXml((Rootcause *)((char *)this + 88), 0, &v31);
      v8 = v21;
      if ( v21 < 0 )
      {
        v22 = 1367;
LABEL_48:
        SdpDebugTrace(1u, L"Rootcause::BuildResultXml", v22, v21);
        v5 = v31;
        goto LABEL_56;
      }
    }
    else
    {
      v21 = SdpBuildParameterXml((Rootcause *)((char *)this + 88), 1, &v31);
      v8 = v21;
      if ( v21 < 0 )
      {
        v22 = 1370;
        goto LABEL_48;
      }
    }
    v5 = v31;
    RootNode = SdpXmlAppend(v10, 0, v31);
    v8 = RootNode;
    if ( RootNode >= 0 )
    {
      RootNode = ((__int64 (__fastcall *)(struct IXMLDOMElement *, _QWORD, _QWORD))v27->lpVtbl->appendChild)(
                   v27,
                   *((_QWORD *)this + 6),
                   0);
      v8 = RootNode;
      if ( RootNode >= 0 )
      {
        *a3 = v10;
        ((void (__fastcall *)(struct IXMLDOMDocument2 *))v10->lpVtbl->AddRef)(v10);
        goto LABEL_56;
      }
      v11 = 1381;
    }
    else
    {
      v11 = 1374;
    }
    goto LABEL_5;
  }
  v11 = 1277;
LABEL_5:
  v12 = RootNode;
LABEL_6:
  SdpDebugTrace(1u, L"Rootcause::BuildResultXml", v11, v12);
LABEL_56:
  if ( v10 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v10->lpVtbl->Release)(v10);
  if ( v3 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v3->lpVtbl->Release)(v3);
LABEL_60:
  if ( v4 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v4->lpVtbl->Release)(v4);
  if ( v5 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v5->lpVtbl->Release)(v5);
  if ( v27 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v27->lpVtbl->Release)(v27);
  if ( Block )
    operator delete(Block);
  return v8;
}

```

## disassembly

```asm
0x18001955c  mov     [rsp-38h+arg_0], rbx
0x180019561  mov     [rsp-38h+arg_10], r8
0x180019566  push    rbp
0x180019567  push    rsi
0x180019568  push    rdi
0x180019569  push    r12
0x18001956b  push    r13
0x18001956d  push    r14
0x18001956f  push    r15
0x180019571  mov     rbp, rsp
0x180019574  sub     rsp, 60h
0x180019578  xor     r12d, r12d
0x18001957b  mov     [rbp+var_10], 0
0x180019583  xor     r13d, r13d
0x180019586  mov     [rbp+var_20], r12
0x18001958a  xor     r15d, r15d
0x18001958d  mov     [rbp+var_28], r13
0x180019591  mov     [rbp+arg_18], r15
0x180019595  mov     rdi, rdx
0x180019598  mov     [rbp+var_18], r12
0x18001959c  mov     r14, rcx
0x18001959f  mov     [rbp+Block], r12
0x1800195a3  mov     [rbp+var_8], r12
0x1800195a7  test    r8, r8
0x1800195aa  jnz     short loc_1800195D0
0x1800195ac  mov     ebx, 80070057h
0x1800195b1  lea     rdx, aRootcauseBuild_1; "Rootcause::BuildResultXml"
0x1800195b8  mov     r9d, ebx; int
0x1800195bb  lea     ecx, [r12+1]; Level
0x1800195c0  mov     r8d, 4FAh; int
0x1800195c6  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800195cb  jmp     loc_180019958
0x1800195d0  lea     rdx, [rbp+var_10]; struct IXMLDOMDocument2 **
0x1800195d4  lea     rcx, aXmlVersion10En_9; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x1800195db  call    ?SdpXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; SdpXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x1800195e0  mov     rsi, [rbp+var_10]
0x1800195e4  mov     ebx, eax
0x1800195e6  test    eax, eax
0x1800195e8  jns     short loc_180019609
0x1800195ea  mov     r8d, 4FDh; int
0x1800195f0  mov     r9d, eax; int
0x1800195f3  lea     rdx, aRootcauseBuild_1; "Rootcause::BuildResultXml"
0x1800195fa  mov     ecx, 1; Level
0x1800195ff  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180019604  jmp     loc_18001992F
0x180019609  lea     rdx, [rbp+var_18]; struct IXMLDOMElement **
0x18001960d  mov     rcx, rsi; struct IXMLDOMDocument2 *
0x180019610  call    ?SdpXmlGetRootNode@@YAJPEAUIXMLDOMDocument2@@PEAPEAUIXMLDOMElement@@@Z; SdpXmlGetRootNode(IXMLDOMDocument2 *,IXMLDOMElement * *)
0x180019615  mov     ebx, eax
0x180019617  test    eax, eax
0x180019619  jns     short loc_180019623
0x18001961b  mov     r8d, 500h
0x180019621  jmp     short loc_1800195F0
0x180019623  mov     rax, [r14+28h]
0x180019627  test    rax, rax
0x18001962a  jnz     short loc_18001963D
0x18001962c  mov     r9d, 80004003h
0x180019632  mov     r8d, 502h
0x180019638  mov     ebx, r9d
0x18001963b  jmp     short loc_1800195F3
0x18001963d  test    rdi, rdi
0x180019640  jz      short loc_18001969C
0x180019642  mov     rdx, [rdi+10h]; unsigned __int16 *
0x180019646  test    rdx, rdx
0x180019649  jnz     short loc_18001965C
0x18001964b  mov     r9d, 80004003h
0x180019651  mov     r8d, 505h
0x180019657  mov     ebx, r9d
0x18001965a  jmp     short loc_1800195F3
0x18001965c  lea     r8, [rbp+Block]; unsigned __int16 **
0x180019660  mov     rcx, rax; unsigned __int16 *
0x180019663  call    ?SdpCatId@@YAJPEBG0PEAPEAG@Z; SdpCatId(ushort const *,ushort const *,ushort * *)
0x180019668  mov     ebx, eax
0x18001966a  test    eax, eax
0x18001966c  jns     short loc_180019679
0x18001966e  mov     r8d, 508h
0x180019674  jmp     loc_1800195F0
0x180019679  mov     edx, [rdi+18h]
0x18001967c  lea     r8, [rbp+var_8]
0x180019680  call    ?StatusToString@Rootcause@@AEAAJW4SDIAG_ROOTCAUSE_STATUS@1@PEAPEAG@Z; Rootcause::StatusToString(Rootcause::SDIAG_ROOTCAUSE_STATUS,ushort * *)
0x180019685  mov     ebx, eax
0x180019687  test    eax, eax
0x180019689  jns     short loc_180019696
0x18001968b  mov     r8d, 50Bh
0x180019691  jmp     loc_1800195F0
0x180019696  mov     rax, [rbp+var_8]
0x18001969a  jmp     short loc_1800196C0
0x18001969c  mov     rdx, rax; unsigned __int16 *
0x18001969f  lea     rcx, [rbp+Block]; unsigned __int16 **
0x1800196a3  call    ?SdpStrCpy@@YAJPEAPEAGPEBG@Z; SdpStrCpy(ushort * *,ushort const *)
0x1800196a8  mov     ebx, eax
0x1800196aa  test    eax, eax
0x1800196ac  jns     short loc_1800196B9
0x1800196ae  mov     r8d, 50Fh
0x1800196b4  jmp     loc_1800195F0
0x1800196b9  lea     rax, aNotChecked; "Not Checked"
0x1800196c0  cmp     [r14+18h], r12
0x1800196c4  lea     rcx, aFalse; "false"
0x1800196cb  mov     r9, [rbp+Block]; unsigned __int16 *
0x1800196cf  lea     r8, aId; "ID"
0x1800196d6  mov     [rbp+var_8], rax
0x1800196da  lea     rax, aTrue; "true"
0x1800196e1  cmovz   rax, rcx
0x1800196e5  mov     [rsp+60h+var_40], r12; struct IXMLDOMElement **
0x1800196ea  xor     edx, edx; struct IXMLDOMElement *
0x1800196ec  mov     [rbp+var_10], rax
0x1800196f0  mov     rcx, rsi; struct IXMLDOMDocument2 *
0x1800196f3  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x1800196f8  mov     ebx, eax
0x1800196fa  test    eax, eax
0x1800196fc  jns     short loc_180019709
0x1800196fe  mov     r8d, 51Fh
0x180019704  jmp     loc_1800195F0
0x180019709  lea     rax, [r14+38h]
0x18001970d  test    rdi, rdi
0x180019710  jz      short loc_180019738
0x180019712  mov     rdx, [rdi+28h]; SAFEARRAY *
0x180019716  lea     r8, [rax+10h]; struct _SDIAG_PARAMSET *
0x18001971a  mov     rcx, [rdi+20h]; psa
0x18001971e  call    ?SdpUpdateParamSet@@YAJPEAUtagSAFEARRAY@@0PEAU_SDIAG_PARAMSET@@@Z; SdpUpdateParamSet(tagSAFEARRAY *,tagSAFEARRAY *,_SDIAG_PARAMSET *)
0x180019723  mov     ebx, eax
0x180019725  test    eax, eax
0x180019727  jns     short loc_180019734
0x180019729  mov     r8d, 529h
0x18001972f  jmp     loc_1800195F0
0x180019734  lea     rax, [r14+38h]
0x180019738  xor     edx, edx
0x18001973a  lea     r8, [rbp+var_28]; struct IXMLDOMDocument2 **
0x18001973e  test    rdi, rdi
0x180019741  mov     rcx, rax; struct _SDIAG_DISPINFO *
0x180019744  setz    dl; int
0x180019747  call    ?SdpBuildDisplayInformationXml@@YAJPEAU_SDIAG_DISPINFO@@HPEAPEAUIXMLDOMDocument2@@@Z; SdpBuildDisplayInformationXml(_SDIAG_DISPINFO *,int,IXMLDOMDocument2 * *)
0x18001974c  mov     ebx, eax
0x18001974e  test    eax, eax
0x180019750  jns     short loc_180019775
0x180019752  mov     r9d, eax; int
0x180019755  lea     rdx, aRootcauseBuild_1; "Rootcause::BuildResultXml"
0x18001975c  mov     r8d, 52Fh; int
0x180019762  mov     ecx, 1; Level
0x180019767  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001976c  mov     r13, [rbp+var_28]
0x180019770  jmp     loc_18001992F
0x180019775  mov     r13, [rbp+var_28]
0x180019779  xor     edx, edx; struct IXMLDOMElement *
0x18001977b  mov     r8, r13; struct IXMLDOMDocument2 *
0x18001977e  mov     rcx, rsi; struct IXMLDOMDocument2 *
0x180019781  call    ?SdpXmlAppend@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@0@Z; SdpXmlAppend(IXMLDOMDocument2 *,IXMLDOMElement *,IXMLDOMDocument2 *)
0x180019786  mov     ebx, eax
0x180019788  test    eax, eax
0x18001978a  jns     short loc_180019797
0x18001978c  mov     r8d, 532h
0x180019792  jmp     loc_1800195F0
0x180019797  mov     r9, [rbp+var_8]; unsigned __int16 *
0x18001979b  lea     r8, aStatus; "Status"
0x1800197a2  xor     edx, edx; struct IXMLDOMElement *
0x1800197a4  mov     [rsp+60h+var_40], r12; struct IXMLDOMElement **
0x1800197a9  mov     rcx, rsi; struct IXMLDOMDocument2 *
0x1800197ac  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x1800197b1  mov     ebx, eax
0x1800197b3  test    eax, eax
0x1800197b5  jns     short loc_1800197C2
0x1800197b7  mov     r8d, 539h
0x1800197bd  jmp     loc_1800195F0
0x1800197c2  mov     r9, [rbp+var_10]; unsigned __int16 *
0x1800197c6  lea     r8, aVerifiable; "Verifiable"
0x1800197cd  xor     edx, edx; struct IXMLDOMElement *
0x1800197cf  mov     [rsp+60h+var_40], r12; struct IXMLDOMElement **
0x1800197d4  mov     rcx, rsi; struct IXMLDOMDocument2 *
0x1800197d7  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x1800197dc  mov     ebx, eax
0x1800197de  test    eax, eax
0x1800197e0  jns     short loc_1800197ED
0x1800197e2  mov     r8d, 540h
0x1800197e8  jmp     loc_1800195F0
0x1800197ed  lea     r8, [rbp+var_20]; struct IXMLDOMDocument2 **
0x1800197f1  mov     rdx, rdi; struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *
0x1800197f4  mov     rcx, r14; this
0x1800197f7  call    ?BuildResultResolutionsXml@Rootcause@@AEAAJPEAU_SDIAG_ROOTCAUSE_INSTANCE@1@PEAPEAUIXMLDOMDocument2@@@Z; Rootcause::BuildResultResolutionsXml(Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *,IXMLDOMDocument2 * *)
0x1800197fc  mov     ebx, eax
0x1800197fe  test    eax, eax
0x180019800  jns     short loc_180019825
0x180019802  mov     r9d, eax; int
0x180019805  lea     rdx, aRootcauseBuild_1; "Rootcause::BuildResultXml"
0x18001980c  mov     r8d, 547h; int
0x180019812  mov     ecx, 1; Level
0x180019817  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001981c  mov     r12, [rbp+var_20]
0x180019820  jmp     loc_18001992F
0x180019825  mov     r12, [rbp+var_20]
0x180019829  xor     edx, edx; struct IXMLDOMElement *
0x18001982b  mov     r8, r12; struct IXMLDOMDocument2 *
0x18001982e  mov     rcx, rsi; struct IXMLDOMDocument2 *
0x180019831  call    ?SdpXmlAppend@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@0@Z; SdpXmlAppend(IXMLDOMDocument2 *,IXMLDOMElement *,IXMLDOMDocument2 *)
0x180019836  mov     ebx, eax
0x180019838  test    eax, eax
0x18001983a  jns     short loc_180019847
0x18001983c  mov     r8d, 54Ah
0x180019842  jmp     loc_1800195F0
0x180019847  test    rdi, rdi
0x18001984a  jz      short loc_1800198AC
0x18001984c  cmp     dword ptr [rdi+18h], 2
0x180019850  jnz     short loc_1800198AC
0x180019852  mov     rdx, [rdi+28h]; SAFEARRAY *
0x180019856  lea     r8, [r14+58h]; struct _SDIAG_PARAMSET *
0x18001985a  mov     rcx, [rdi+20h]; psa
0x18001985e  call    ?SdpUpdateParamSet@@YAJPEAUtagSAFEARRAY@@0PEAU_SDIAG_PARAMSET@@@Z; SdpUpdateParamSet(tagSAFEARRAY *,tagSAFEARRAY *,_SDIAG_PARAMSET *)
0x180019863  mov     ebx, eax
0x180019865  test    eax, eax
0x180019867  jns     short loc_180019874
0x180019869  mov     r8d, 554h
0x18001986f  jmp     loc_1800195F0
0x180019874  lea     r8, [rbp+arg_18]; struct IXMLDOMDocument2 **
0x180019878  xor     edx, edx; int
0x18001987a  lea     rcx, [r14+58h]; struct _SDIAG_PARAMSET *
0x18001987e  call    ?SdpBuildParameterXml@@YAJPEAU_SDIAG_PARAMSET@@HPEAPEAUIXMLDOMDocument2@@@Z; SdpBuildParameterXml(_SDIAG_PARAMSET *,int,IXMLDOMDocument2 * *)
0x180019883  mov     ebx, eax
0x180019885  test    eax, eax
0x180019887  jns     short loc_1800198CC
0x180019889  mov     r8d, 557h; int
0x18001988f  mov     r9d, eax; int
0x180019892  lea     rdx, aRootcauseBuild_1; "Rootcause::BuildResultXml"
0x180019899  mov     ecx, 1; Level
0x18001989e  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800198a3  mov     r15, [rbp+arg_18]
0x1800198a7  jmp     loc_18001992F
0x1800198ac  lea     rcx, [r14+58h]; struct _SDIAG_PARAMSET *
0x1800198b0  mov     edx, 1; int
0x1800198b5  lea     r8, [rbp+arg_18]; struct IXMLDOMDocument2 **
0x1800198b9  call    ?SdpBuildParameterXml@@YAJPEAU_SDIAG_PARAMSET@@HPEAPEAUIXMLDOMDocument2@@@Z; SdpBuildParameterXml(_SDIAG_PARAMSET *,int,IXMLDOMDocument2 * *)
0x1800198be  mov     ebx, eax
0x1800198c0  test    eax, eax
0x1800198c2  jns     short loc_1800198CC
0x1800198c4  mov     r8d, 55Ah
0x1800198ca  jmp     short loc_18001988F
0x1800198cc  mov     r15, [rbp+arg_18]
0x1800198d0  xor     edx, edx; struct IXMLDOMElement *
0x1800198d2  mov     r8, r15; struct IXMLDOMDocument2 *
0x1800198d5  mov     rcx, rsi; struct IXMLDOMDocument2 *
0x1800198d8  call    ?SdpXmlAppend@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@0@Z; SdpXmlAppend(IXMLDOMDocument2 *,IXMLDOMElement *,IXMLDOMDocument2 *)
0x1800198dd  mov     ebx, eax
0x1800198df  test    eax, eax
0x1800198e1  jns     short loc_1800198EE
0x1800198e3  mov     r8d, 55Eh
0x1800198e9  jmp     loc_1800195F0
0x1800198ee  mov     rcx, [rbp+var_18]
0x1800198f2  xor     r8d, r8d
0x1800198f5  mov     rdx, [r14+30h]
0x1800198f9  mov     rax, [rcx]
0x1800198fc  mov     rax, [rax+0A8h]
0x180019903  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019908  mov     ebx, eax
0x18001990a  test    eax, eax
0x18001990c  jns     short loc_180019919
0x18001990e  mov     r8d, 565h
0x180019914  jmp     loc_1800195F0
0x180019919  mov     rax, [rbp+arg_10]
0x18001991d  mov     rcx, rsi
0x180019920  mov     [rax], rsi
0x180019923  mov     rax, [rsi]
0x180019926  mov     rax, [rax+8]
0x18001992a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001992f  test    rsi, rsi
0x180019932  jz      short loc_180019943
0x180019934  mov     rax, [rsi]
0x180019937  mov     rcx, rsi
0x18001993a  mov     rax, [rax+10h]
0x18001993e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019943  test    r12, r12
0x180019946  jz      short loc_180019958
0x180019948  mov     rax, [r12]
0x18001994c  mov     rcx, r12
0x18001994f  mov     rax, [rax+10h]
0x180019953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019958  test    r13, r13
0x18001995b  jz      short loc_18001996D
0x18001995d  mov     rax, [r13+0]
0x180019961  mov     rcx, r13
0x180019964  mov     rax, [rax+10h]
0x180019968  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001996d  test    r15, r15
0x180019970  jz      short loc_180019981
0x180019972  mov     rax, [r15]
0x180019975  mov     rcx, r15
0x180019978  mov     rax, [rax+10h]
0x18001997c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019981  mov     rcx, [rbp+var_18]
0x180019985  test    rcx, rcx
0x180019988  jz      short loc_180019996
0x18001998a  mov     rax, [rcx]
0x18001998d  mov     rax, [rax+10h]
0x180019991  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019996  mov     rcx, [rbp+Block]; Block
0x18001999a  test    rcx, rcx
0x18001999d  jz      short loc_1800199A4
0x18001999f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800199a4  mov     eax, ebx
0x1800199a6  mov     rbx, [rsp+60h+arg_0]
0x1800199ae  add     rsp, 60h
0x1800199b2  pop     r15
0x1800199b4  pop     r14
  ... truncated ...
```
