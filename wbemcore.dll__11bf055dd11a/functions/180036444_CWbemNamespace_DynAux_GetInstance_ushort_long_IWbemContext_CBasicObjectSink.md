# CWbemNamespace::DynAux_GetInstance(ushort *,long,IWbemContext *,CBasicObjectSink *)

- ea: `0x180036444`
- end: `0x180036a94`
- name: `?DynAux_GetInstance@CWbemNamespace@@QEAAJPEAGJPEAUIWbemContext@@PEAVCBasicObjectSink@@@Z`
- size: `1616`
- prototype: `int(CWbemNamespace *__hidden this, unsigned __int16 *, int, struct IWbemContext *, struct CBasicObjectSink *)`
- caller_count: `1`
- callee_count: `22`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18003ad40`

## callees

- `0x18000b140`
- `0x18001307c`
- `0x1800159fc`
- `0x180027324`
- `0x180028be8`
- `0x180028c10`
- `0x180036444`
- `0x180036a9c`
- `0x1800370c0`
- `0x1800371b8`
- `0x180037af4`
- `0x180037bf8`
- `0x180037ebc`
- `0x18003cfe0`
- `0x18003d050`
- `0x18005edf4`
- `0x18005fd50`
- `0x18005fe8c`
- `0x18008ae80`
- `0x18008d608`
- `0x18009c6e4`
- `0x1800da010`

## import_xrefs

- `wbemcomn!??0WString@@QEAA@PEBG@Z` at `0x180036674`
- `wbemcomn!??0WString@@QEAA@PEBG@Z` at `0x180036674`
- `wbemcomn!??1WString@@QEAA@XZ` at `0x180036705`
- `wbemcomn!??1WString@@QEAA@XZ` at `0x1800367b6`
- `wbemcomn!??1WString@@QEAA@XZ` at `0x18003696b`
- `wbemcomn!??1WString@@QEAA@XZ` at `0x180036705`
- `wbemcomn!??1WString@@QEAA@XZ` at `0x1800367b6`
- `wbemcomn!??1WString@@QEAA@XZ` at `0x18003696b`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x18003669b`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x18003669b`
- `wbemcomn!??0WString@@QEAA@XZ` at `0x180036568`
- `wbemcomn!??0WString@@QEAA@XZ` at `0x180036568`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003661a`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003661a`
- `wbemcomn!??0CCritSec@@QEAA@XZ` at `0x180036663`
- `wbemcomn!??0CCritSec@@QEAA@XZ` at `0x180036663`
- `wbemcomn!GetMemLogObject` at `0x18003686a`
- `wbemcomn!GetMemLogObject` at `0x1800368ed`
- `wbemcomn!GetMemLogObject` at `0x18003699f`
- `wbemcomn!GetMemLogObject` at `0x1800369dd`
- `wbemcomn!GetMemLogObject` at `0x180036a2e`
- `wbemcomn!GetMemLogObject` at `0x18003686a`
- `wbemcomn!GetMemLogObject` at `0x1800368ed`
- `wbemcomn!GetMemLogObject` at `0x18003699f`
- `wbemcomn!GetMemLogObject` at `0x1800369dd`
- `wbemcomn!GetMemLogObject` at `0x180036a2e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036877`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800368fa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800369ac`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800369ea`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036a3e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036877`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800368fa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800369ac`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800369ea`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036a3e`
- `OLEAUT32!__imp_SysAllocString` at `0x180036503`
- `OLEAUT32!__imp_SysAllocString` at `0x180036503`
- `OLEAUT32!__imp_SysFreeString` at `0x18003672c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800367dd`
- `OLEAUT32!__imp_SysFreeString` at `0x18003672c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800367dd`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall CWbemNamespace::DynAux_GetInstance(
        CWbemNamespace *this,
        unsigned __int16 *a2,
        unsigned int a3,
        struct IWbemContext *a4,
        struct CBasicObjectSink *a5)
{
  int v8; // eax
  const OLECHAR **v9; // r15
  unsigned int v10; // edi
  OLECHAR *v11; // rax
  OLECHAR *v12; // rsi
  int ObjectByPath; // eax
  struct IWbemClassObject *v14; // rbx
  struct CWbemInstance *v15; // rdi
  CCombiningSink *v16; // rax
  unsigned int v17; // edx
  struct CBasicObjectSink *v18; // rdi
  const unsigned __int16 *v19; // rax
  unsigned int v20; // edx
  CMemoryLog *v22; // rax
  CMemoryLog *v23; // rax
  CMemoryLog *v24; // rax
  unsigned int v25; // edx
  CMemoryLog *v26; // rax
  CMemoryLog *MemLogObject; // rax
  int v28[2]; // [rsp+38h] [rbp-91h] BYREF
  struct IWbemClassObject *v29; // [rsp+40h] [rbp-89h] BYREF
  struct ParsedObjectPath *v30; // [rsp+48h] [rbp-81h] BYREF
  _BYTE v31[8]; // [rsp+50h] [rbp-79h] BYREF
  struct CDynasty *v32; // [rsp+58h] [rbp-71h] BYREF
  struct IWbemClassObject *v33; // [rsp+60h] [rbp-69h] BYREF
  OLECHAR *v34; // [rsp+68h] [rbp-61h] BYREF
  struct IWbemClassObject **v35; // [rsp+70h] [rbp-59h] BYREF
  CCombiningSink *v36; // [rsp+78h] [rbp-51h]
  _QWORD v37[3]; // [rsp+80h] [rbp-49h] BYREF
  char v38; // [rsp+98h] [rbp-31h]
  __int64 v39; // [rsp+A0h] [rbp-29h] BYREF
  int v40; // [rsp+A8h] [rbp-21h]
  __int64 v41; // [rsp+B0h] [rbp-19h]
  __int128 v42; // [rsp+B8h] [rbp-11h]
  int v43; // [rsp+C8h] [rbp-1h]
  __int64 *v44; // [rsp+D0h] [rbp+7h]
  struct ParsedObjectPath *v45; // [rsp+D8h] [rbp+Fh]

  v30 = 0;
  v43 = 1;
  v40 = 0;
  v41 = 0;
  v39 = 0;
  v42 = 0;
  v8 = CObjectPathParser::Parse((CObjectPathParser *)&v39, a2, &v30);
  v44 = &v39;
  v9 = (const OLECHAR **)v30;
  v45 = v30;
  if ( v8 || !(unsigned int)ParsedObjectPath::IsInstance(v30) )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217350);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 342, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749946LL);
    }
    v10 = CBasicObjectSink::Return(a5, -2147217350, 0);
    goto LABEL_34;
  }
  v10 = -2147217407;
  v28[0] = -2147217407;
  v29 = 0;
  v35 = &v29;
  v37[0] = a5;
  v37[1] = v28;
  v37[2] = &v29;
  v38 = 0;
  v11 = SysAllocString(v9[3]);
  v12 = v11;
  if ( !v11 )
  {
    v10 = -2147217402;
    v28[0] = -2147217402;
    goto LABEL_31;
  }
  v34 = v11;
  v33 = 0;
  ObjectByPath = CWbemNamespace::Exec_GetObjectByPath(this, v11, a3 & 0x20000, a4, &v33, 0);
  v28[0] = ObjectByPath;
  if ( ObjectByPath < 0 )
  {
    if ( ObjectByPath == -2147217406 )
    {
      v10 = -2147217392;
    }
    else
    {
      v22 = GetMemLogObject();
      CMemoryLog::Write(v22, v28[0]);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          343,
          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
          (unsigned int)v28[0]);
      }
    }
    v28[0] = v10;
    goto LABEL_30;
  }
  v14 = v33;
  v30 = (struct ParsedObjectPath *)v33;
  v15 = (struct CWbemInstance *)v33;
  WString::WString((WString *)v31);
  v28[0] = NormalizeObjectPath((struct ParsedObjectPath *)v9, (struct WString *)v31, v15);
  if ( v28[0] < 0 )
  {
    v23 = GetMemLogObject();
    CMemoryLog::Write(v23, v28[0]);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        344,
        WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
        (unsigned int)v28[0]);
    }
    v10 = v28[0];
    goto LABEL_55;
  }
  if ( !(*(unsigned int (__fastcall **)(struct CWbemInstance *))(*(_QWORD *)v15 + 1032LL))(v15) )
  {
    v10 = -2147217392;
    v28[0] = -2147217392;
LABEL_27:
    WString::~WString((WString *)v31);
    if ( v14 )
      ((void (__fastcall *)(struct IWbemClassObject *))v14->lpVtbl->Release)(v14);
    v30 = 0;
LABEL_30:
    SysFreeString(v12);
LABEL_31:
    Sink_Return((struct IWbemObjectSink *)a5, v28, &v29);
    if ( v29 )
      ((void (__fastcall *)(struct IWbemClassObject *))v29->lpVtbl->Release)(v29);
    v29 = 0;
    goto LABEL_34;
  }
  std::unique_ptr<IUnknown * [0]>::unique_ptr<IUnknown * [0]>(&v32);
  v28[0] = CWbemNamespace::DynAux_BuildClassHierarchy((struct IWmiDbSession **)this, v12, a3, a4, &v32, &v29);
  if ( v28[0] < 0 )
  {
    v24 = GetMemLogObject();
    CMemoryLog::Write(v24, v28[0]);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        345,
        WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
        (unsigned int)v28[0]);
    }
    v10 = v28[0];
    std::unique_ptr<CDynasty>::~unique_ptr<CDynasty>(&v32, v25);
LABEL_55:
    WString::~WString((WString *)v31);
    CReleaseMe::release((CReleaseMe *)&v30);
    CSysFreeMe::~CSysFreeMe(&v34);
    OnDeleteIf3<IWbemObjectSink *,long &,IWbemClassObject * &,void (*)(IWbemObjectSink *,long &,IWbemClassObject * &),&void Sink_Return(IWbemObjectSink *,long &,IWbemClassObject * &)>::~OnDeleteIf3<IWbemObjectSink *,long &,IWbemClassObject * &,void (*)(IWbemObjectSink *,long &,IWbemClassObject * &),&void Sink_Return(IWbemObjectSink *,long &,IWbemClassObject * &)>(v37);
    CReleaseMeRef<IWbemClassObject *>::release(&v35);
LABEL_34:
    CObjectPathParser::Free((CObjectPathParser *)&v39, (struct ParsedObjectPath *)v9);
    goto LABEL_24;
  }
  if ( v29 )
    ((void (__fastcall *)(struct IWbemClassObject *))v29->lpVtbl->Release)(v29);
  v29 = 0;
  if ( (a3 & 0x200) == 0 )
  {
    v28[0] = -2147217402;
    v16 = (CCombiningSink *)CWin32DefaultArena::WbemMemAlloc(0xA8u);
    v18 = v16;
    v36 = v16;
    if ( v16 )
    {
      CCombiningSink::CCombiningSink(v16, a5, 0x80041002);
      *(_QWORD *)v18 = &CSingleMergingSink::`vftable'{for `IWbemObjectSinkEx'};
      *((_QWORD *)v18 + 1) = &CInternalMerger::COwnSink::`vftable'{for `CDestination'};
      *((_QWORD *)v18 + 14) = 0;
      CCritSec::CCritSec((struct CBasicObjectSink *)((char *)v18 + 120));
      WString::WString((struct CBasicObjectSink *)((char *)v18 + 160), v12);
    }
    else
    {
      v18 = 0;
    }
    if ( v18 )
    {
      (*(void (__fastcall **)(struct CBasicObjectSink *))(*(_QWORD *)v18 + 8LL))(v18);
      v36 = v18;
      v19 = (const unsigned __int16 *)WString::operator unsigned short *(v31);
      CWbemNamespace::DynAux_AskRecursively(this, v32, a3, v19, a4, v18);
      (*(void (__fastcall **)(struct CBasicObjectSink *))(*(_QWORD *)v18 + 16LL))(v18);
      v36 = 0;
      goto LABEL_15;
    }
    v10 = v28[0];
    if ( v28[0] < 0 )
    {
      v26 = GetMemLogObject();
      CMemoryLog::Write(v26, v28[0]);
      v10 = v28[0];
    }
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 346, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v10);
      v10 = v28[0];
    }
    std::unique_ptr<CDynasty>::~unique_ptr<CDynasty>(&v32, v17);
    goto LABEL_27;
  }
  CWbemNamespace::DynAux_GetSingleInstance(this, (struct CWbemClass *)v33, a3, a2, a4, a5);
LABEL_15:
  v38 = 1;
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 347, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 0);
  }
  std::unique_ptr<CDynasty>::~unique_ptr<CDynasty>(&v32, v20);
  WString::~WString((WString *)v31);
  if ( v14 )
    ((void (__fastcall *)(struct IWbemClassObject *))v14->lpVtbl->Release)(v14);
  v30 = 0;
  SysFreeString(v12);
  if ( v29 )
    ((void (__fastcall *)(struct IWbemClassObject *))v29->lpVtbl->Release)(v29);
  v29 = 0;
  if ( v9 )
    ParsedObjectPath::`scalar deleting destructor'((ParsedObjectPath *)v9);
  v10 = 0;
LABEL_24:
  CObjectPathParser::Empty((CObjectPathParser *)&v39);
  return v10;
}

```

## disassembly

```asm
0x180036444  mov     rax, rsp
0x180036447  mov     [rax+18h], rbx
0x18003644b  mov     [rax+10h], rdx
0x18003644f  mov     [rax+8], rcx
0x180036453  push    rbp
0x180036454  push    rsi
0x180036455  push    rdi
0x180036456  push    r12
0x180036458  push    r13
0x18003645a  push    r14
0x18003645c  push    r15
0x18003645e  lea     rbp, [rax-57h]
0x180036462  sub     rsp, 0E0h
0x180036469  mov     r13, r9
0x18003646c  mov     r12d, r8d
0x18003646f  mov     rbx, rcx
0x180036472  xor     esi, esi
0x180036474  mov     [rsp+110h+var_D0], rsi
0x180036479  mov     [rbp+4Fh+var_50], 1
0x180036480  mov     [rbp+4Fh+var_70], esi
0x180036483  mov     [rbp+4Fh+var_68], rsi
0x180036487  mov     [rbp+4Fh+var_78], rsi
0x18003648b  xorps   xmm0, xmm0
0x18003648e  movdqu  [rbp+4Fh+var_60], xmm0
0x180036493  lea     r8, [rsp+110h+var_D0]; struct ParsedObjectPath **
0x180036498  lea     rcx, [rbp+4Fh+var_78]; this
0x18003649c  call    ?Parse@CObjectPathParser@@QEAAHPEBGPEAPEAUParsedObjectPath@@@Z; CObjectPathParser::Parse(ushort const *,ParsedObjectPath * *)
0x1800364a1  lea     rcx, [rbp+4Fh+var_78]
0x1800364a5  mov     [rbp+4Fh+var_48], rcx
0x1800364a9  mov     r15, [rsp+110h+var_D0]
0x1800364ae  mov     [rbp+4Fh+var_40], r15
0x1800364b2  test    eax, eax
0x1800364b4  jnz     loc_180036A2E
0x1800364ba  mov     rcx, r15; this
0x1800364bd  call    ?IsInstance@ParsedObjectPath@@QEAAHXZ; ParsedObjectPath::IsInstance(void)
0x1800364c2  test    eax, eax
0x1800364c4  jz      loc_180036A2E
0x1800364ca  mov     edi, 80041001h
0x1800364cf  mov     [rsp+110h+var_E0], edi
0x1800364d3  mov     [rsp+110h+var_D8], rsi
0x1800364d8  lea     rax, [rsp+110h+var_D8]
0x1800364dd  mov     [rbp+4Fh+var_A8], rax
0x1800364e1  mov     r14, [rbp+4Fh+arg_20]
0x1800364e5  mov     [rbp+4Fh+var_98], r14
0x1800364e9  lea     rax, [rsp+110h+var_E0]
0x1800364ee  mov     [rbp+4Fh+var_90], rax
0x1800364f2  lea     rax, [rsp+110h+var_D8]
0x1800364f7  mov     [rbp+4Fh+var_88], rax
0x1800364fb  mov     [rbp+4Fh+var_80], sil
0x1800364ff  mov     rcx, [r15+18h]; psz
0x180036503  call    cs:__imp_SysAllocString
0x180036509  mov     rsi, rax
0x18003650c  test    rax, rax
0x18003650f  jz      loc_180036827
0x180036515  mov     [rbp+4Fh+var_B0], rax
0x180036519  mov     [rbp+4Fh+var_B8], 0
0x180036521  mov     r8d, r12d
0x180036524  and     r8d, 20000h; int
0x18003652b  mov     [rsp+110h+var_E8], 0; struct IWbemClassObject **
0x180036534  lea     rax, [rbp+4Fh+var_B8]
0x180036538  mov     [rsp+110h+var_F0], rax; struct IWbemClassObject **
0x18003653d  mov     r9, r13; struct IWbemContext *
0x180036540  mov     rdx, rsi; unsigned __int16 *
0x180036543  mov     rcx, rbx; this
0x180036546  call    ?Exec_GetObjectByPath@CWbemNamespace@@QEAAJPEBGJPEAUIWbemContext@@PEAPEAUIWbemClassObject@@2@Z; CWbemNamespace::Exec_GetObjectByPath(ushort const *,long,IWbemContext *,IWbemClassObject * *,IWbemClassObject * *)
0x18003654b  mov     [rsp+110h+var_E0], eax
0x18003654f  test    eax, eax
0x180036551  js      loc_180036863
0x180036557  mov     rbx, [rbp+4Fh+var_B8]
0x18003655b  mov     [rsp+110h+var_D0], rbx
0x180036560  mov     rdi, [rbp+4Fh+var_B8]
0x180036564  lea     rcx, [rbp+4Fh+var_C8]
0x180036568  call    cs:__imp_??0WString@@QEAA@XZ; WString::WString(void)
0x18003656e  nop
0x18003656f  mov     r8, rdi; struct CWbemInstance *
0x180036572  lea     rdx, [rbp+4Fh+var_C8]; struct WString *
0x180036576  mov     rcx, r15; struct ParsedObjectPath *
0x180036579  call    ?NormalizeObjectPath@@YAJPEAUParsedObjectPath@@AEAVWString@@PEAVCWbemInstance@@@Z; NormalizeObjectPath(ParsedObjectPath *,WString &,CWbemInstance *)
0x18003657e  mov     [rsp+110h+var_E0], eax
0x180036582  test    eax, eax
0x180036584  js      loc_1800368ED
0x18003658a  mov     rax, [rdi]
0x18003658d  mov     rcx, rdi
0x180036590  mov     rax, [rax+408h]
0x180036597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003659c  test    eax, eax
0x18003659e  jz      loc_1800367A9
0x1800365a4  lea     rcx, [rbp+4Fh+var_C0]
0x1800365a8  call    ??0?$unique_ptr@$$BY0A@PEAUIUnknown@@U?$default_delete@$$BY0A@PEAUIUnknown@@@std@@@std@@QEAA@XZ; std::unique_ptr<IUnknown * [0]>::unique_ptr<IUnknown * [0]>(void)
0x1800365ad  nop
0x1800365ae  lea     rax, [rsp+110h+var_D8]
0x1800365b3  mov     [rsp+110h+var_E8], rax; struct IWbemClassObject **
0x1800365b8  lea     rax, [rbp+4Fh+var_C0]
0x1800365bc  mov     [rsp+110h+var_F0], rax; __int64
0x1800365c1  mov     r9, r13
0x1800365c4  mov     r8d, r12d; int
0x1800365c7  mov     rdx, rsi; unsigned __int16 *
0x1800365ca  mov     rdi, [rbp+4Fh+arg_0]
0x1800365ce  mov     rcx, rdi; this
0x1800365d1  call    ?DynAux_BuildClassHierarchy@CWbemNamespace@@QEAAJPEAGJPEAUIWbemContext@@AEAV?$unique_ptr@VCDynasty@@U?$default_delete@VCDynasty@@@std@@@std@@PEAPEAUIWbemClassObject@@@Z; CWbemNamespace::DynAux_BuildClassHierarchy(ushort *,long,IWbemContext *,std::unique_ptr<CDynasty> &,IWbemClassObject * *)
0x1800365d6  mov     [rsp+110h+var_E0], eax
0x1800365da  test    eax, eax
0x1800365dc  js      loc_18003699F
0x1800365e2  mov     rcx, [rsp+110h+var_D8]
0x1800365e7  test    rcx, rcx
0x1800365ea  jz      short loc_1800365F8
0x1800365ec  mov     rax, [rcx]
0x1800365ef  mov     rax, [rax+10h]
0x1800365f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800365f8  mov     [rsp+110h+var_D8], 0
0x180036601  bt      r12d, 9
0x180036606  jb      loc_180036787
0x18003660c  mov     edi, 80041006h
0x180036611  mov     [rsp+110h+var_E0], edi
0x180036615  mov     ecx, 0A8h
0x18003661a  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180036620  mov     rdi, rax
0x180036623  mov     [rbp+4Fh+var_A0], rax
0x180036627  test    rax, rax
0x18003662a  jz      loc_1800369D6
0x180036630  mov     r8d, 80041002h; int
0x180036636  mov     rdx, r14; struct CBasicObjectSink *
0x180036639  mov     rcx, rax; this
0x18003663c  call    ??0CCombiningSink@@QEAA@PEAVCBasicObjectSink@@J@Z; CCombiningSink::CCombiningSink(CBasicObjectSink *,long)
0x180036641  nop
0x180036642  lea     rax, ??_7CSingleMergingSink@@6BIWbemObjectSinkEx@@@; const CSingleMergingSink::`vftable'{for `IWbemObjectSinkEx'}
0x180036649  mov     [rdi], rax
0x18003664c  lea     rax, ??_7COwnSink@CInternalMerger@@6BCDestination@@@; const CInternalMerger::COwnSink::`vftable'{for `CDestination'}
0x180036653  mov     [rdi+8], rax
0x180036657  mov     qword ptr [rdi+70h], 0
0x18003665f  lea     rcx, [rdi+78h]
0x180036663  call    cs:__imp_??0CCritSec@@QEAA@XZ; CCritSec::CCritSec(void)
0x180036669  nop
0x18003666a  lea     rcx, [rdi+0A0h]
0x180036671  mov     rdx, rsi
0x180036674  call    cs:__imp_??0WString@@QEAA@PEBG@Z; WString::WString(ushort const *)
0x18003667a  nop
0x18003667b  test    rdi, rdi
0x18003667e  jz      loc_180036832
0x180036684  mov     rax, [rdi]
0x180036687  mov     rcx, rdi
0x18003668a  mov     rax, [rax+8]
0x18003668e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036693  mov     [rbp+4Fh+var_A0], rdi
0x180036697  lea     rcx, [rbp+4Fh+var_C8]
0x18003669b  call    cs:__imp_??BWString@@QEAAPEAGXZ; WString::operator ushort *(void)
0x1800366a1  mov     [rsp+110h+var_E8], rdi; struct CBasicObjectSink *
0x1800366a6  mov     [rsp+110h+var_F0], r13; struct IWbemContext *
0x1800366ab  mov     r9, rax; unsigned __int16 *
0x1800366ae  mov     r8d, r12d; int
0x1800366b1  mov     rdx, [rbp+4Fh+var_C0]; struct CDynasty *
0x1800366b5  mov     rcx, [rbp+4Fh+arg_0]; this
0x1800366b9  call    ?DynAux_AskRecursively@CWbemNamespace@@QEAAJPEAVCDynasty@@JPEBGPEAUIWbemContext@@PEAVCBasicObjectSink@@@Z; CWbemNamespace::DynAux_AskRecursively(CDynasty *,long,ushort const *,IWbemContext *,CBasicObjectSink *)
0x1800366be  nop
0x1800366bf  mov     rax, [rdi]
0x1800366c2  mov     rcx, rdi
0x1800366c5  mov     rax, [rax+10h]
0x1800366c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800366ce  mov     [rbp+4Fh+var_A0], 0
0x1800366d6  mov     [rbp+4Fh+var_80], 1
0x1800366da  lea     rax, WPP_GLOBAL_Control
0x1800366e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800366e8  cmp     rcx, rax
0x1800366eb  jz      short loc_1800366F7
0x1800366ed  test    byte ptr [rcx+1Ch], 1
0x1800366f1  jnz     loc_1800368BF
0x1800366f7  lea     rcx, [rbp+4Fh+var_C0]
0x1800366fb  call    ??1?$unique_ptr@VCDynasty@@U?$default_delete@VCDynasty@@@std@@@std@@QEAA@XZ; std::unique_ptr<CDynasty>::~unique_ptr<CDynasty>(void)
0x180036700  nop
0x180036701  lea     rcx, [rbp+4Fh+var_C8]
0x180036705  call    cs:__imp_??1WString@@QEAA@XZ; WString::~WString(void)
0x18003670b  nop
0x18003670c  test    rbx, rbx
0x18003670f  jz      short loc_180036720
0x180036711  mov     rax, [rbx]
0x180036714  mov     rcx, rbx
0x180036717  mov     rax, [rax+10h]
0x18003671b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036720  mov     [rsp+110h+var_D0], 0
0x180036729  mov     rcx, rsi; bstrString
0x18003672c  call    cs:__imp_SysFreeString
0x180036732  nop
0x180036733  mov     rcx, [rsp+110h+var_D8]
0x180036738  test    rcx, rcx
0x18003673b  jz      short loc_180036749
0x18003673d  mov     rax, [rcx]
0x180036740  mov     rax, [rax+10h]
0x180036744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036749  mov     [rsp+110h+var_D8], 0
0x180036752  test    r15, r15
0x180036755  jz      short loc_18003675F
0x180036757  mov     rcx, r15; this
0x18003675a  call    ??_GParsedObjectPath@@QEAAPEAXI@Z; ParsedObjectPath::`scalar deleting destructor'(uint)
0x18003675f  xor     edi, edi
0x180036761  lea     rcx, [rbp+4Fh+var_78]; this
0x180036765  call    ?Empty@CObjectPathParser@@AEAAXXZ; CObjectPathParser::Empty(void)
0x18003676a  mov     eax, edi
0x18003676c  mov     rbx, [rsp+110h+arg_10]
0x180036774  add     rsp, 0E0h
0x18003677b  pop     r15
0x18003677d  pop     r14
0x18003677f  pop     r13
0x180036781  pop     r12
0x180036783  pop     rdi
0x180036784  pop     rsi
0x180036785  pop     rbp
0x180036786  retn
0x180036787  mov     [rsp+110h+var_E8], r14; struct CBasicObjectSink *
0x18003678c  mov     [rsp+110h+var_F0], r13; struct IWbemContext *
0x180036791  mov     r9, [rbp+4Fh+arg_8]; unsigned __int16 *
0x180036795  mov     r8d, r12d; int
0x180036798  mov     rdx, [rbp+4Fh+var_B8]; struct CWbemClass *
0x18003679c  mov     rcx, rdi; this
0x18003679f  call    ?DynAux_GetSingleInstance@CWbemNamespace@@QEAAJPEAVCWbemClass@@JPEBGPEAUIWbemContext@@PEAVCBasicObjectSink@@@Z; CWbemNamespace::DynAux_GetSingleInstance(CWbemClass *,long,ushort const *,IWbemContext *,CBasicObjectSink *)
0x1800367a4  jmp     loc_1800366D6
0x1800367a9  mov     edi, 80041010h
0x1800367ae  mov     [rsp+110h+var_E0], edi
0x1800367b2  lea     rcx, [rbp+4Fh+var_C8]
0x1800367b6  call    cs:__imp_??1WString@@QEAA@XZ; WString::~WString(void)
0x1800367bc  nop
0x1800367bd  test    rbx, rbx
0x1800367c0  jz      short loc_1800367D1
0x1800367c2  mov     rax, [rbx]
0x1800367c5  mov     rcx, rbx
0x1800367c8  mov     rax, [rax+10h]
0x1800367cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800367d1  mov     [rsp+110h+var_D0], 0
0x1800367da  mov     rcx, rsi; bstrString
0x1800367dd  call    cs:__imp_SysFreeString
0x1800367e3  nop
0x1800367e4  lea     r8, [rsp+110h+var_D8]; struct IWbemClassObject **
0x1800367e9  lea     rdx, [rsp+110h+var_E0]; int *
0x1800367ee  mov     rcx, r14; struct IWbemObjectSink *
0x1800367f1  call    ?Sink_Return@@YAXPEAUIWbemObjectSink@@AEAJAEAPEAUIWbemClassObject@@@Z; Sink_Return(IWbemObjectSink *,long &,IWbemClassObject * &)
0x1800367f6  nop
0x1800367f7  mov     rcx, [rsp+110h+var_D8]
0x1800367fc  test    rcx, rcx
0x1800367ff  jz      short loc_18003680D
0x180036801  mov     rax, [rcx]
0x180036804  mov     rax, [rax+10h]
0x180036808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003680d  mov     [rsp+110h+var_D8], 0
0x180036816  mov     rdx, r15; struct ParsedObjectPath *
0x180036819  lea     rcx, [rbp+4Fh+var_78]; this
0x18003681d  call    ?Free@CObjectPathParser@@QEAAXPEAUParsedObjectPath@@@Z; CObjectPathParser::Free(ParsedObjectPath *)
0x180036822  jmp     loc_180036761
0x180036827  mov     edi, 80041006h
0x18003682c  mov     [rsp+110h+var_E0], edi
0x180036830  jmp     short loc_1800367E4
0x180036832  mov     edi, [rsp+110h+var_E0]
0x180036836  test    edi, edi
0x180036838  js      loc_1800369DD
0x18003683e  lea     rax, WPP_GLOBAL_Control
0x180036845  mov     rcx, cs:WPP_GLOBAL_Control
0x18003684c  cmp     rcx, rax
0x18003684f  jnz     loc_1800369F9
0x180036855  lea     rcx, [rbp+4Fh+var_C0]
0x180036859  call    ??1?$unique_ptr@VCDynasty@@U?$default_delete@VCDynasty@@@std@@@std@@QEAA@XZ; std::unique_ptr<CDynasty>::~unique_ptr<CDynasty>(void)
0x18003685e  jmp     loc_1800367B2
0x180036863  cmp     eax, 80041002h
0x180036868  jz      short loc_1800368E6
0x18003686a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180036870  mov     edx, [rsp+110h+var_E0]
0x180036874  mov     rcx, rax
0x180036877  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003687d  lea     rax, WPP_GLOBAL_Control
0x180036884  mov     rcx, cs:WPP_GLOBAL_Control
0x18003688b  cmp     rcx, rax
0x18003688e  jz      short loc_1800368B6
0x180036890  test    byte ptr [rcx+1Ch], 1
0x180036894  jz      short loc_1800368B6
0x180036896  cmp     byte ptr [rcx+19h], 2
0x18003689a  jb      short loc_1800368B6
0x18003689c  mov     edx, 157h
0x1800368a1  mov     r9d, [rsp+110h+var_E0]
0x1800368a6  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x1800368ad  mov     rcx, [rcx+10h]
0x1800368b1  call    WPP_SF_d
0x1800368b6  mov     [rsp+110h+var_E0], edi
0x1800368ba  jmp     loc_1800367DA
0x1800368bf  cmp     byte ptr [rcx+19h], 2
0x1800368c3  jb      loc_1800366F7
0x1800368c9  mov     edx, 15Bh
0x1800368ce  xor     r9d, r9d
0x1800368d1  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x1800368d8  mov     rcx, [rcx+10h]
0x1800368dc  call    WPP_SF_d
0x1800368e1  jmp     loc_1800366F7
0x1800368e6  mov     edi, 80041010h
0x1800368eb  jmp     short loc_1800368B6
0x1800368ed  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800368f3  mov     edx, [rsp+110h+var_E0]
0x1800368f7  mov     rcx, rax
0x1800368fa  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180036900  lea     rax, WPP_GLOBAL_Control
0x180036907  mov     rcx, cs:WPP_GLOBAL_Control
0x18003690e  cmp     rcx, rax
0x180036911  jz      short loc_180036939
0x180036913  test    byte ptr [rcx+1Ch], 1
0x180036917  jz      short loc_180036939
  ... truncated ...
```
