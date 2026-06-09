# CAssocQuery::Execute(CWbemNamespace *,ushort *,IWbemContext *,CBasicObjectSink *)

- ea: `0x180015d24`
- end: `0x180016245`
- name: `?Execute@CAssocQuery@@QEAAJPEAVCWbemNamespace@@PEAGPEAUIWbemContext@@PEAVCBasicObjectSink@@@Z`
- size: `1313`
- prototype: `int(CAssocQuery *__hidden this, struct CWbemNamespace *, unsigned __int16 *, struct IWbemContext *, struct CBasicObjectSink *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18003a030`

## callees

- `0x18000b140`
- `0x1800159fc`
- `0x180015d24`
- `0x18001624c`
- `0x180016dc0`
- `0x180017484`
- `0x18001d230`
- `0x18003d050`
- `0x18005fd50`
- `0x18005fe8c`
- `0x180085e20`
- `0x1800da010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180015d4a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180015d4a`
- `wbemcomn!GetMemLogObject` at `0x180015f52`
- `wbemcomn!GetMemLogObject` at `0x180015ff8`
- `wbemcomn!GetMemLogObject` at `0x180016065`
- `wbemcomn!GetMemLogObject` at `0x1800160dd`
- `wbemcomn!GetMemLogObject` at `0x180016130`
- `wbemcomn!GetMemLogObject` at `0x180015f52`
- `wbemcomn!GetMemLogObject` at `0x180015ff8`
- `wbemcomn!GetMemLogObject` at `0x180016065`
- `wbemcomn!GetMemLogObject` at `0x1800160dd`
- `wbemcomn!GetMemLogObject` at `0x180016130`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180015f63`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180016008`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180016075`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800160ed`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180016140`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180015f63`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180016008`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180016075`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800160ed`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180016140`
- `OLEAUT32!__imp_VariantInit` at `0x180015e5c`
- `OLEAUT32!__imp_VariantInit` at `0x180015e5c`
- `OLEAUT32!__imp_VariantClear` at `0x180015f15`
- `OLEAUT32!__imp_VariantClear` at `0x180015f8c`
- `OLEAUT32!__imp_VariantClear` at `0x1800161c3`
- `OLEAUT32!__imp_VariantClear` at `0x18001621f`
- `OLEAUT32!__imp_VariantClear` at `0x180015f15`
- `OLEAUT32!__imp_VariantClear` at `0x180015f8c`
- `OLEAUT32!__imp_VariantClear` at `0x1800161c3`
- `OLEAUT32!__imp_VariantClear` at `0x18001621f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CAssocQuery::Execute(
        CAssocQuery *this,
        struct CWbemNamespace *a2,
        unsigned __int16 *a3,
        struct IWbemContext *a4,
        struct IWbemObjectSink *a5)
{
  struct IWbemObjectSink *v9; // r14
  struct IWbemContext **v10; // rdi
  struct IWbemClassObject **v11; // rdi
  bool v12; // al
  CMemoryLog *v14; // rax
  unsigned int v15; // edi
  CMemoryLog *v16; // rax
  CClientCnt *v17; // rcx
  unsigned int v18; // ebx
  CMemoryLog *MemLogObject; // rax
  __int64 v20; // rdx
  CWbemNamespace *v21; // rcx
  CMemoryLog *v22; // rax
  CClientCnt *v23; // rcx
  __int64 v24; // rdx
  CMemoryLog *v25; // rax
  struct IWbemClassObject **v26; // [rsp+40h] [rbp-68h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-60h] BYREF
  _QWORD v28[3]; // [rsp+60h] [rbp-48h] BYREF
  char v29; // [rsp+78h] [rbp-30h]
  int KeysCtx; // [rsp+B0h] [rbp+8h] BYREF
  struct IWbemClassObject *v31; // [rsp+B8h] [rbp+10h] BYREF

  *((_DWORD *)this + 70) = GetTickCount();
  *((_QWORD *)this + 94) = a2;
  _InterlockedIncrement((volatile signed __int32 *)a2 + 6);
  KeysCtx = -2147217407;
  v31 = 0;
  v26 = &v31;
  v9 = a5;
  v28[0] = a5;
  v28[1] = &KeysCtx;
  v28[2] = &v31;
  v29 = 0;
  KeysCtx = CAssocQueryParser::Parse((CAssocQuery *)((char *)this + 16), a3);
  if ( KeysCtx < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, KeysCtx);
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v20 = 10;
LABEL_32:
      WPP_SF_d(*((_QWORD *)v17 + 2), v20, WPP_2f04df46b09834ff6d8f033aca1000f6_Traceguids, (unsigned int)KeysCtx);
    }
LABEL_25:
    v18 = KeysCtx;
    Sink_Return(v9, &KeysCtx, &v31);
    if ( v31 )
      ((void (__fastcall *)(struct IWbemClassObject *))v31->lpVtbl->Release)(v31);
    return v18;
  }
  if ( a4 )
  {
    v10 = (struct IWbemContext **)((char *)this + 744);
    if ( (*((_BYTE *)this + 80) & 0x10) == 0 )
    {
      *v10 = a4;
      ((void (__fastcall *)(struct IWbemContext *))a4->lpVtbl->AddRef)(a4);
      goto LABEL_5;
    }
    KeysCtx = ((__int64 (__fastcall *)(struct IWbemContext *, char *))a4->lpVtbl->Clone)(a4, (char *)this + 744);
    if ( KeysCtx < 0 )
    {
      v22 = GetMemLogObject();
      CMemoryLog::Write(v22, KeysCtx);
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_44;
      }
      v24 = 11;
LABEL_43:
      WPP_SF_d(*((_QWORD *)v23 + 2), v24, WPP_2f04df46b09834ff6d8f033aca1000f6_Traceguids, (unsigned int)KeysCtx);
LABEL_44:
      v18 = KeysCtx;
LABEL_51:
      OnDeleteIf3<IWbemObjectSink *,long &,IWbemClassObject * &,void (*)(IWbemObjectSink *,long &,IWbemClassObject * &),&void Sink_Return(IWbemObjectSink *,long &,IWbemClassObject * &)>::~OnDeleteIf3<IWbemObjectSink *,long &,IWbemClassObject * &,void (*)(IWbemObjectSink *,long &,IWbemClassObject * &),&void Sink_Return(IWbemObjectSink *,long &,IWbemClassObject * &)>(v28);
      CReleaseMeRef<IWbemClassObject *>::release(&v26);
      return v18;
    }
    KeysCtx = CWbemNamespace::MergeGetKeysCtx(v21, *v10);
    if ( KeysCtx < 0 )
    {
      v25 = GetMemLogObject();
      CMemoryLog::Write(v25, KeysCtx);
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_44;
      }
      v24 = 12;
      goto LABEL_43;
    }
  }
LABEL_5:
  v11 = (struct IWbemClassObject **)((char *)this + 152);
  KeysCtx = CWbemNamespace::Exec_GetObjectByPath(
              a2,
              *((const unsigned __int16 **)this + 3),
              0,
              a4,
              (struct IWbemClassObject **)this + 19,
              &v31);
  if ( KeysCtx < 0 )
  {
    v16 = GetMemLogObject();
    CMemoryLog::Write(v16, KeysCtx);
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v20 = 13;
      goto LABEL_32;
    }
    goto LABEL_25;
  }
  if ( v31 )
    ((void (__fastcall *)(struct IWbemClassObject *))v31->lpVtbl->Release)(v31);
  v31 = 0;
  VariantInit(&pvarg);
  ((void (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*v11)->lpVtbl->Get)(
    *v11,
    L"__GENUS",
    0,
    &pvarg,
    0,
    0);
  v12 = pvarg.lVal == 1;
  *((_BYTE *)this + 184) = pvarg.lVal == 1;
  if ( (*((_BYTE *)this + 80) & 8) != 0 )
  {
    if ( !v12 )
    {
LABEL_50:
      v18 = -2147217385;
      KeysCtx = -2147217385;
      VariantClear(&pvarg);
      goto LABEL_51;
    }
  }
  else if ( (*((_BYTE *)this + 80) & 4) != 0 && (v12 || *((_QWORD *)this + 4)) )
  {
    goto LABEL_50;
  }
  KeysCtx = CAssocQuery::St_GetObjectInfo(
              *v11,
              (unsigned __int16 **)this + 20,
              (unsigned __int16 **)this + 22,
              (unsigned __int16 **)this + 21,
              (CAssocQuery *)((char *)this + 192));
  if ( KeysCtx < 0 )
  {
    v14 = GetMemLogObject();
    CMemoryLog::Write(v14, KeysCtx);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        WPP_2f04df46b09834ff6d8f033aca1000f6_Traceguids,
        (unsigned int)KeysCtx);
    }
    v15 = KeysCtx;
    VariantClear(&pvarg);
    ((void (__fastcall *)(struct IWbemObjectSink *, _QWORD, _QWORD, _QWORD, struct IWbemClassObject *))v9->lpVtbl->SetStatus)(
      v9,
      0,
      (unsigned int)KeysCtx,
      0,
      v31);
    if ( v31 )
      ((void (__fastcall *)(struct IWbemClassObject *))v31->lpVtbl->Release)(v31);
    v31 = 0;
    return v15;
  }
  else
  {
    *((_QWORD *)this + 18) = v9;
    ((void (__fastcall *)(struct IWbemObjectSink *))v9->lpVtbl->AddRef)(v9);
    try
    {
      if ( (*((_BYTE *)this + 80) & 8) != 0 )
        CAssocQuery::ExecSchemaQuery(this);
      else
        CAssocQuery::ExecNormalQuery(this);
    }
    catch ( CX_Exception )
    {
      KeysCtx = -2147217398;
      VariantClear(&pvarg);
      OnDeleteIf3<IWbemObjectSink *,long &,IWbemClassObject * &,void (*)(IWbemObjectSink *,long &,IWbemClassObject * &),&void Sink_Return(IWbemObjectSink *,long &,IWbemClassObject * &)>::~OnDeleteIf3<IWbemObjectSink *,long &,IWbemClassObject * &,void (*)(IWbemObjectSink *,long &,IWbemClassObject * &),&void Sink_Return(IWbemObjectSink *,long &,IWbemClassObject * &)>(v28);
      CReleaseMeRef<IWbemClassObject *>::release(&v26);
      return 2147749898LL;
    }
    v29 = 1;
    VariantClear(&pvarg);
    if ( v31 )
      ((void (__fastcall *)(struct IWbemClassObject *))v31->lpVtbl->Release)(v31);
    v31 = 0;
    return 0;
  }
}

```

## disassembly

```asm
0x180015d24  mov     [rsp+arg_10], rbx
0x180015d29  mov     [rsp+arg_18], rsi
0x180015d2e  push    rdi
0x180015d2f  push    r12
0x180015d31  push    r13
0x180015d33  push    r14
0x180015d35  push    r15
0x180015d37  sub     rsp, 80h
0x180015d3e  mov     r15, r9
0x180015d41  mov     rdi, r8
0x180015d44  mov     r12, rdx
0x180015d47  mov     rsi, rcx
0x180015d4a  call    cs:__imp_GetTickCount
0x180015d50  mov     [rsi+118h], eax
0x180015d56  mov     [rsi+2F0h], r12
0x180015d5d  lock inc dword ptr [r12+18h]
0x180015d63  mov     [rsp+0A8h+arg_0], 80041001h
0x180015d6e  mov     [rsp+0A8h+arg_8], 0
0x180015d7a  lea     rbx, [rsp+0A8h+arg_8]
0x180015d82  mov     [rsp+0A8h+var_68], rbx
0x180015d87  mov     r14, [rsp+0A8h+arg_20]
0x180015d8f  mov     [rsp+0A8h+var_48], r14
0x180015d94  lea     rax, [rsp+0A8h+arg_0]
0x180015d9c  mov     [rsp+0A8h+var_40], rax
0x180015da1  lea     rax, [rsp+0A8h+arg_8]
0x180015da9  mov     [rsp+0A8h+var_38], rax
0x180015dae  xor     r13b, r13b
0x180015db1  mov     [rsp+0A8h+var_30], r13b
0x180015db6  lea     rcx, [rsi+10h]; this
0x180015dba  mov     rdx, rdi; unsigned __int16 *
0x180015dbd  call    ?Parse@CAssocQueryParser@@QEAAJPEAG@Z; CAssocQueryParser::Parse(ushort *)
0x180015dc2  mov     [rsp+0A8h+arg_0], eax
0x180015dc9  test    eax, eax
0x180015dcb  js      loc_180016065
0x180015dd1  test    r15, r15
0x180015dd4  jz      short loc_180015DF9
0x180015dd6  lea     rdi, [rsi+2E8h]
0x180015ddd  mov     rcx, r15
0x180015de0  test    byte ptr [rsi+50h], 10h
0x180015de4  jnz     loc_1800160C3
0x180015dea  mov     [rdi], r15
0x180015ded  mov     rax, [r15]
0x180015df0  mov     rax, [rax+8]
0x180015df4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015df9  lea     rdi, [rsi+98h]
0x180015e00  lea     rax, [rsp+0A8h+arg_8]
0x180015e08  mov     [rsp+0A8h+var_80], rax; struct IWbemClassObject **
0x180015e0d  mov     [rsp+0A8h+var_88], rdi; struct IWbemClassObject **
0x180015e12  mov     r9, r15; struct IWbemContext *
0x180015e15  xor     r8d, r8d; int
0x180015e18  mov     rdx, [rsi+18h]; unsigned __int16 *
0x180015e1c  mov     rcx, r12; this
0x180015e1f  call    ?Exec_GetObjectByPath@CWbemNamespace@@QEAAJPEBGJPEAUIWbemContext@@PEAPEAUIWbemClassObject@@2@Z; CWbemNamespace::Exec_GetObjectByPath(ushort const *,long,IWbemContext *,IWbemClassObject * *,IWbemClassObject * *)
0x180015e24  mov     [rsp+0A8h+arg_0], eax
0x180015e2b  xor     r15d, r15d
0x180015e2e  test    eax, eax
0x180015e30  js      loc_180015FF8
0x180015e36  mov     rcx, [rsp+0A8h+arg_8]
0x180015e3e  test    rcx, rcx
0x180015e41  jz      short loc_180015E4F
0x180015e43  mov     rax, [rcx]
0x180015e46  mov     rax, [rax+10h]
0x180015e4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e4f  mov     [rsp+0A8h+arg_8], r15
0x180015e57  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x180015e5c  call    cs:__imp_VariantInit
0x180015e62  nop
0x180015e63  mov     rcx, [rdi]
0x180015e66  mov     rax, [rcx]
0x180015e69  mov     [rsp+0A8h+var_80], r15
0x180015e6e  mov     [rsp+0A8h+var_88], r15
0x180015e73  lea     r9, [rsp+0A8h+pvarg]
0x180015e78  xor     r8d, r8d
0x180015e7b  lea     rdx, aGenus; "__GENUS"
0x180015e82  mov     rax, [rax+20h]
0x180015e86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e8b  cmp     dword ptr [rsp+0A8h+pvarg+8], 1
0x180015e90  setz    al
0x180015e93  mov     [rsi+0B8h], al
0x180015e99  test    byte ptr [rsi+50h], 8
0x180015e9d  jnz     loc_180015FE1
0x180015ea3  test    byte ptr [rsi+50h], 4
0x180015ea7  jnz     loc_1800161A4
0x180015ead  lea     rax, [rsi+0C0h]
0x180015eb4  lea     r9, [rsi+0A8h]; unsigned __int16 **
0x180015ebb  lea     r8, [rsi+0B0h]; unsigned __int16 **
0x180015ec2  lea     rdx, [rsi+0A0h]; unsigned __int16 **
0x180015ec9  mov     [rsp+0A8h+var_88], rax; struct CWStringArray *
0x180015ece  mov     rcx, [rdi]; struct IWbemClassObject *
0x180015ed1  call    ?St_GetObjectInfo@CAssocQuery@@CAJPEAUIWbemClassObject@@PEAPEAG11AEAVCWStringArray@@@Z; CAssocQuery::St_GetObjectInfo(IWbemClassObject *,ushort * *,ushort * *,ushort * *,CWStringArray &)
0x180015ed6  mov     [rsp+0A8h+arg_0], eax
0x180015edd  test    eax, eax
0x180015edf  js      short loc_180015F52
0x180015ee1  mov     [rsi+90h], r14
0x180015ee8  mov     rax, [r14]
0x180015eeb  mov     rcx, r14
0x180015eee  mov     rax, [rax+8]
0x180015ef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ef7  nop
0x180015ef8  mov     rcx, rsi; this
0x180015efb  test    byte ptr [rsi+50h], 8
0x180015eff  jnz     loc_180015FEE
0x180015f05  call    ?ExecNormalQuery@CAssocQuery@@AEAAJXZ; CAssocQuery::ExecNormalQuery(void)
0x180015f0a  nop
0x180015f0b  mov     [rsp+0A8h+var_30], 1
0x180015f10  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x180015f15  call    cs:__imp_VariantClear
0x180015f1b  nop
0x180015f1c  mov     rcx, [rbx]
0x180015f1f  test    rcx, rcx
0x180015f22  jz      short loc_180015F30
0x180015f24  mov     rax, [rcx]
0x180015f27  mov     rax, [rax+10h]
0x180015f2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f30  mov     [rbx], r15
0x180015f33  xor     eax, eax
0x180015f35  lea     r11, [rsp+0A8h+var_28]
0x180015f3d  mov     rbx, [r11+40h]
0x180015f41  mov     rsi, [r11+48h]
0x180015f45  mov     rsp, r11
0x180015f48  pop     r15
0x180015f4a  pop     r14
0x180015f4c  pop     r13
0x180015f4e  pop     r12
0x180015f50  pop     rdi
0x180015f51  retn
0x180015f52  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180015f58  nop
0x180015f59  mov     edx, [rsp+0A8h+arg_0]
0x180015f60  mov     rcx, rax
0x180015f63  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180015f69  lea     rax, WPP_GLOBAL_Control
0x180015f70  mov     rcx, cs:WPP_GLOBAL_Control
0x180015f77  cmp     rcx, rax
0x180015f7a  jnz     loc_1800161E4
0x180015f80  mov     edi, [rsp+0A8h+arg_0]
0x180015f87  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x180015f8c  call    cs:__imp_VariantClear
0x180015f92  nop
0x180015f93  mov     rax, [r14]
0x180015f96  lea     rdx, [rsp+0A8h+arg_8]
0x180015f9e  mov     rdx, [rdx]
0x180015fa1  mov     [rsp+0A8h+var_88], rdx
0x180015fa6  xor     r9d, r9d
0x180015fa9  lea     r8, [rsp+0A8h+arg_0]
0x180015fb1  mov     r8d, [r8]
0x180015fb4  xor     edx, edx
0x180015fb6  mov     rcx, r14
0x180015fb9  mov     rax, [rax+20h]
0x180015fbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fc2  nop
0x180015fc3  mov     rcx, [rbx]
0x180015fc6  test    rcx, rcx
0x180015fc9  jz      short loc_180015FD7
0x180015fcb  mov     rdx, [rcx]
0x180015fce  mov     rax, [rdx+10h]
0x180015fd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fd7  mov     [rbx], r15
0x180015fda  mov     eax, edi
0x180015fdc  jmp     loc_180015F35
0x180015fe1  test    al, al
0x180015fe3  jnz     loc_180015EAD
0x180015fe9  jmp     loc_1800161B2
0x180015fee  call    ?ExecSchemaQuery@CAssocQuery@@AEAAXXZ; CAssocQuery::ExecSchemaQuery(void)
0x180015ff3  jmp     loc_180015F0B
0x180015ff8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180015ffe  mov     edx, [rsp+0A8h+arg_0]
0x180016005  mov     rcx, rax
0x180016008  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001600e  lea     rax, WPP_GLOBAL_Control
0x180016015  mov     rcx, cs:WPP_GLOBAL_Control
0x18001601c  cmp     rcx, rax
0x18001601f  jnz     loc_18001618B
0x180016025  mov     ebx, [rsp+0A8h+arg_0]
0x18001602c  lea     r8, [rsp+0A8h+arg_8]; struct IWbemClassObject **
0x180016034  lea     rdx, [rsp+0A8h+arg_0]; int *
0x18001603c  mov     rcx, r14; struct IWbemObjectSink *
0x18001603f  call    ?Sink_Return@@YAXPEAUIWbemObjectSink@@AEAJAEAPEAUIWbemClassObject@@@Z; Sink_Return(IWbemObjectSink *,long &,IWbemClassObject * &)
0x180016044  nop
0x180016045  mov     rcx, [rsp+0A8h+arg_8]
0x18001604d  test    rcx, rcx
0x180016050  jz      short loc_18001605E
0x180016052  mov     rdx, [rcx]
0x180016055  mov     rax, [rdx+10h]
0x180016059  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001605e  mov     eax, ebx
0x180016060  jmp     loc_180015F35
0x180016065  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001606b  mov     edx, [rsp+0A8h+arg_0]
0x180016072  mov     rcx, rax
0x180016075  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001607b  lea     rax, WPP_GLOBAL_Control
0x180016082  mov     rcx, cs:WPP_GLOBAL_Control
0x180016089  cmp     rcx, rax
0x18001608c  jz      short loc_180016025
0x18001608e  test    byte ptr [rcx+1Ch], 1
0x180016092  jz      short loc_180016025
0x180016094  cmp     byte ptr [rcx+19h], 2
0x180016098  jb      short loc_180016025
0x18001609a  mov     edx, 0Ah
0x18001609f  jmp     short loc_1800160A6
0x1800160a1  mov     edx, 0Dh
0x1800160a6  mov     r9d, [rsp+0A8h+arg_0]
0x1800160ae  lea     r8, WPP_2f04df46b09834ff6d8f033aca1000f6_Traceguids
0x1800160b5  mov     rcx, [rcx+10h]
0x1800160b9  call    WPP_SF_d
0x1800160be  jmp     loc_180016025
0x1800160c3  mov     rax, [r15]
0x1800160c6  mov     rdx, rdi
0x1800160c9  mov     rax, [rax+18h]
0x1800160cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160d2  mov     [rsp+0A8h+arg_0], eax
0x1800160d9  test    eax, eax
0x1800160db  jns     short loc_180016119
0x1800160dd  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800160e3  mov     edx, [rsp+0A8h+arg_0]
0x1800160ea  mov     rcx, rax
0x1800160ed  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800160f3  lea     rax, WPP_GLOBAL_Control
0x1800160fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180016101  cmp     rcx, rax
0x180016104  jz      short loc_180016182
0x180016106  test    byte ptr [rcx+1Ch], 1
0x18001610a  jz      short loc_180016182
0x18001610c  cmp     byte ptr [rcx+19h], 2
0x180016110  jb      short loc_180016182
0x180016112  mov     edx, 0Bh
0x180016117  jmp     short loc_18001616A
0x180016119  mov     rdx, [rdi]; struct IWbemContext *
0x18001611c  call    ?MergeGetKeysCtx@CWbemNamespace@@QEAAJPEAUIWbemContext@@@Z; CWbemNamespace::MergeGetKeysCtx(IWbemContext *)
0x180016121  mov     [rsp+0A8h+arg_0], eax
0x180016128  test    eax, eax
0x18001612a  jns     loc_180015DF9
0x180016130  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180016136  mov     edx, [rsp+0A8h+arg_0]
0x18001613d  mov     rcx, rax
0x180016140  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180016146  lea     rax, WPP_GLOBAL_Control
0x18001614d  mov     rcx, cs:WPP_GLOBAL_Control
0x180016154  cmp     rcx, rax
0x180016157  jz      short loc_180016182
0x180016159  test    byte ptr [rcx+1Ch], 1
0x18001615d  jz      short loc_180016182
0x18001615f  cmp     byte ptr [rcx+19h], 2
0x180016163  jb      short loc_180016182
0x180016165  mov     edx, 0Ch
0x18001616a  mov     r9d, [rsp+0A8h+arg_0]
0x180016172  lea     r8, WPP_2f04df46b09834ff6d8f033aca1000f6_Traceguids
0x180016179  mov     rcx, [rcx+10h]
0x18001617d  call    WPP_SF_d
0x180016182  mov     ebx, [rsp+0A8h+arg_0]
0x180016189  jmp     short loc_1800161CA
0x18001618b  test    byte ptr [rcx+1Ch], 1
0x18001618f  jz      loc_180016025
0x180016195  cmp     byte ptr [rcx+19h], 2
0x180016199  jb      loc_180016025
0x18001619f  jmp     loc_1800160A1
0x1800161a4  cmp     al, 1
0x1800161a6  jz      short loc_1800161B2
0x1800161a8  cmp     [rsi+20h], r15
0x1800161ac  jz      loc_180015EAD
0x1800161b2  mov     ebx, 80041017h
0x1800161b7  mov     [rsp+0A8h+arg_0], ebx
0x1800161be  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x1800161c3  call    cs:__imp_VariantClear
0x1800161c9  nop
0x1800161ca  lea     rcx, [rsp+0A8h+var_48]
0x1800161cf  call    ??1?$OnDeleteIf3@PEAUIWbemObjectSink@@AEAJAEAPEAUIWbemClassObject@@P6AXPEAU1@AEAJAEAPEAU2@@Z$1?Sink_Return@@YAX012@Z@@QEAA@XZ; OnDeleteIf3<IWbemObjectSink *,long &,IWbemClassObject * &,void (*)(IWbemObjectSink *,long &,IWbemClassObject * &),&Sink_Return(IWbemObjectSink *,long &,IWbemClassObject * &)>::~OnDeleteIf3<IWbemObjectSink *,long &,IWbemClassObject * &,void (*)(IWbemObjectSink *,long &,IWbemClassObject * &),&Sink_Return(IWbemObjectSink *,long &,IWbemClassObject * &)>(void)
0x1800161d4  nop
0x1800161d5  lea     rcx, [rsp+0A8h+var_68]
0x1800161da  call    ?release@?$CReleaseMeRef@PEAUIWbemClassObject@@@@QEAAXXZ; CReleaseMeRef<IWbemClassObject *>::release(void)
0x1800161df  jmp     loc_18001605E
0x1800161e4  test    byte ptr [rcx+1Ch], 1
0x1800161e8  jz      loc_180015F80
0x1800161ee  cmp     byte ptr [rcx+19h], 2
0x1800161f2  jb      loc_180015F80
0x1800161f8  mov     edx, 0Eh
0x1800161fd  mov     r9d, [rsp+0A8h+arg_0]
0x180016205  lea     r8, WPP_2f04df46b09834ff6d8f033aca1000f6_Traceguids
0x18001620c  mov     rcx, [rcx+10h]
0x180016210  call    WPP_SF_d
0x180016215  jmp     loc_180015F80
0x18001621a  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x18001621f  call    cs:__imp_VariantClear
0x180016225  nop
0x180016226  lea     rcx, [rsp+0A8h+var_48]
0x18001622b  call    ??1?$OnDeleteIf3@PEAUIWbemObjectSink@@AEAJAEAPEAUIWbemClassObject@@P6AXPEAU1@AEAJAEAPEAU2@@Z$1?Sink_Return@@YAX012@Z@@QEAA@XZ; OnDeleteIf3<IWbemObjectSink *,long &,IWbemClassObject * &,void (*)(IWbemObjectSink *,long &,IWbemClassObject * &),&Sink_Return(IWbemObjectSink *,long &,IWbemClassObject * &)>::~OnDeleteIf3<IWbemObjectSink *,long &,IWbemClassObject * &,void (*)(IWbemObjectSink *,long &,IWbemClassObject * &),&Sink_Return(IWbemObjectSink *,long &,IWbemClassObject * &)>(void)
0x180016230  nop
0x180016231  lea     rcx, [rsp+0A8h+var_68]
0x180016236  call    ?release@?$CReleaseMeRef@PEAUIWbemClassObject@@@@QEAAXXZ; CReleaseMeRef<IWbemClassObject *>::release(void)
0x18001623b  mov     eax, 8004100Ah
0x180016240  jmp     loc_180015F35
```
