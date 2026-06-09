# CAssocQuery::ExecNormalQuery(void)

- ea: `0x180017484`
- end: `0x18001787e`
- name: `?ExecNormalQuery@CAssocQuery@@AEAAJXZ`
- size: `1018`
- prototype: `__int64 __fastcall(CAssocQuery *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180015d24`

## callees

- `0x18000b140`
- `0x1800159fc`
- `0x180015a28`
- `0x1800164f0`
- `0x180017484`
- `0x180017b48`
- `0x18001933c`
- `0x18001a484`
- `0x18001af84`
- `0x18001b624`
- `0x18005fe8c`
- `0x1800da010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800174d3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800174d3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001761b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001761b`
- `wbemcomn!GetMemLogObject` at `0x18001762c`
- `wbemcomn!GetMemLogObject` at `0x1800176ca`
- `wbemcomn!GetMemLogObject` at `0x180017711`
- `wbemcomn!GetMemLogObject` at `0x180017758`
- `wbemcomn!GetMemLogObject` at `0x18001779c`
- `wbemcomn!GetMemLogObject` at `0x1800177d4`
- `wbemcomn!GetMemLogObject` at `0x180017863`
- `wbemcomn!GetMemLogObject` at `0x18001762c`
- `wbemcomn!GetMemLogObject` at `0x1800176ca`
- `wbemcomn!GetMemLogObject` at `0x180017711`
- `wbemcomn!GetMemLogObject` at `0x180017758`
- `wbemcomn!GetMemLogObject` at `0x18001779c`
- `wbemcomn!GetMemLogObject` at `0x1800177d4`
- `wbemcomn!GetMemLogObject` at `0x180017863`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180017638`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800176d6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001771d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180017764`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800177a8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800177e0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001786f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180017638`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800176d6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001771d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180017764`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800177a8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800177e0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001786f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAssocQuery::ExecNormalQuery(CAssocQuery *this)
{
  struct IWbemObjectSink *v2; // r14
  int v3; // r15d
  HANDLE EventW; // rax
  CAssocQuery *v5; // rcx
  int v6; // eax
  int v7; // ebx
  CMemoryLog *v9; // rax
  CClientCnt *v10; // rcx
  CMemoryLog *v11; // rax
  __int64 v12; // rdx
  CMemoryLog *MemLogObject; // rax
  CClientCnt *v14; // rcx
  __int64 v15; // rdx
  CMemoryLog *v16; // rax
  CMemoryLog *v17; // rax
  CMemoryLog *v18; // rax
  CMemoryLog *v19; // rax
  int ClassFilter; // [rsp+30h] [rbp-38h] BYREF
  struct IWbemClassObject *v21; // [rsp+38h] [rbp-30h] BYREF
  _QWORD v22[3]; // [rsp+40h] [rbp-28h] BYREF
  char v23; // [rsp+58h] [rbp-10h]

  ClassFilter = -2147217407;
  v21 = 0;
  v2 = (struct IWbemObjectSink *)*((_QWORD *)this + 18);
  v22[0] = v2;
  v22[1] = &ClassFilter;
  v22[2] = &v21;
  v23 = 0;
  v3 = *((_DWORD *)this + 20);
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 37) = EventW;
  if ( !EventW )
  {
    v7 = -2147217402;
    ClassFilter = -2147217402;
LABEL_17:
    ((void (__fastcall *)(struct IWbemObjectSink *, _QWORD, _QWORD, _QWORD, struct IWbemClassObject *))v2->lpVtbl->SetStatus)(
      v2,
      0,
      (unsigned int)ClassFilter,
      0,
      v21);
    return (unsigned int)v7;
  }
  ClassFilter = CAssocQuery::BuildMasterAssocClassList(this, (CAssocQuery *)((char *)this + 304));
  if ( ClassFilter < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, ClassFilter);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_56;
    }
    v15 = 16;
    goto LABEL_55;
  }
  ClassFilter = CAssocQuery::ReduceToRealClasses(this, (CAssocQuery *)((char *)this + 304));
  if ( ClassFilter < 0 )
  {
    v16 = GetMemLogObject();
    CMemoryLog::Write(v16, ClassFilter);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_56;
    }
    v15 = 17;
    goto LABEL_55;
  }
  ClassFilter = CAssocQuery::RemoveNonDynClasses(v5, (CAssocQuery *)((char *)this + 304));
  if ( ClassFilter < 0 )
  {
    v17 = GetMemLogObject();
    CMemoryLog::Write(v17, ClassFilter);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_56;
    }
    v15 = 18;
    goto LABEL_55;
  }
  ClassFilter = CAssocQuery::NormalQ_PreQueryClassFilter(this, (CAssocQuery *)((char *)this + 304));
  if ( ClassFilter < 0 )
  {
    v18 = GetMemLogObject();
    CMemoryLog::Write(v18, ClassFilter);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_56;
    }
    v15 = 19;
LABEL_55:
    WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_2f04df46b09834ff6d8f033aca1000f6_Traceguids, (unsigned int)ClassFilter);
LABEL_56:
    v7 = ClassFilter;
    OnDeleteIf3<IWbemObjectSink *,long &,IWbemClassObject * &,void (*)(IWbemObjectSink *,long &,IWbemClassObject * &),&void Sink_Return(IWbemObjectSink *,long &,IWbemClassObject * &)>::~OnDeleteIf3<IWbemObjectSink *,long &,IWbemClassObject * &,void (*)(IWbemObjectSink *,long &,IWbemClassObject * &),&void Sink_Return(IWbemObjectSink *,long &,IWbemClassObject * &)>(v22);
    return (unsigned int)v7;
  }
  if ( g_bDontAllowNewConnections )
  {
    v7 = -2147217357;
LABEL_22:
    ClassFilter = v7;
  }
  else
  {
    if ( (v3 & 2) != 0 )
      v6 = CAssocQuery::NormalQ_ReferencesOf(this);
    else
      v6 = CAssocQuery::NormalQ_AssociatorsOf(this);
    v7 = v6;
    ClassFilter = v6;
    if ( v6 < 0 )
    {
      v11 = GetMemLogObject();
      CMemoryLog::Write(v11, ClassFilter);
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v12 = 20;
LABEL_57:
        WPP_SF_d(*((_QWORD *)v10 + 2), v12, WPP_2f04df46b09834ff6d8f033aca1000f6_Traceguids, (unsigned int)ClassFilter);
      }
    }
    else
    {
      while ( 1 )
      {
        if ( !*((_DWORD *)this + 72) )
        {
          if ( (v3 & 1) != 0 )
          {
            v7 = CAssocQuery::ResolveEpPathsToObjects(this, -1);
            ClassFilter = v7;
          }
          if ( v7 < 0 )
          {
            v19 = GetMemLogObject();
            CMemoryLog::Write(v19, ClassFilter);
            v7 = ClassFilter;
          }
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              22,
              WPP_2f04df46b09834ff6d8f033aca1000f6_Traceguids,
              (unsigned int)v7);
            v7 = ClassFilter;
          }
          goto LABEL_17;
        }
        WaitForSingleObject(*((HANDLE *)this + 37), 0xFAu);
        if ( (v3 & 1) == 0 || (v3 & 4) != 0 )
        {
          v7 = ClassFilter;
        }
        else
        {
          v7 = CAssocQuery::ResolveEpPathsToObjects(this, 5);
          ClassFilter = v7;
        }
        if ( v7 < 0 )
          break;
        if ( *((_BYTE *)this + 760) )
        {
          v7 = -2147217358;
          goto LABEL_22;
        }
      }
      v9 = GetMemLogObject();
      CMemoryLog::Write(v9, ClassFilter);
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v12 = 21;
        goto LABEL_57;
      }
    }
    v7 = ClassFilter;
  }
  Sink_Return(v2, &ClassFilter, &v21);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180017484  push    rbp
0x180017486  push    rbx
0x180017487  push    rsi
0x180017488  push    rdi
0x180017489  push    r14
0x18001748b  push    r15
0x18001748d  mov     rbp, rsp
0x180017490  sub     rsp, 68h
0x180017494  mov     rdi, rcx
0x180017497  mov     [rbp+var_38], 80041001h
0x18001749e  mov     [rbp+var_30], 0
0x1800174a6  mov     r14, [rcx+90h]
0x1800174ad  mov     [rbp+var_28], r14
0x1800174b1  lea     rax, [rbp+var_38]
0x1800174b5  mov     [rbp+var_20], rax
0x1800174b9  lea     rax, [rbp+var_30]
0x1800174bd  mov     [rbp+var_18], rax
0x1800174c1  mov     [rbp+var_10], 0
0x1800174c5  mov     r15d, [rcx+50h]
0x1800174c9  xor     r9d, r9d; lpName
0x1800174cc  xor     r8d, r8d; bInitialState
0x1800174cf  xor     edx, edx; bManualReset
0x1800174d1  xor     ecx, ecx; lpEventAttributes
0x1800174d3  call    cs:__imp_CreateEventW
0x1800174d9  mov     [rdi+128h], rax
0x1800174e0  test    rax, rax
0x1800174e3  jz      loc_1800175E1
0x1800174e9  lea     rbx, [rdi+130h]
0x1800174f0  mov     rdx, rbx; struct CFlexArray *
0x1800174f3  mov     rcx, rdi; this
0x1800174f6  call    ?BuildMasterAssocClassList@CAssocQuery@@AEAAJAEAVCFlexArray@@@Z; CAssocQuery::BuildMasterAssocClassList(CFlexArray &)
0x1800174fb  mov     [rbp+var_38], eax
0x1800174fe  test    eax, eax
0x180017500  js      loc_180017711
0x180017506  mov     rdx, rbx; struct CFlexArray *
0x180017509  mov     rcx, rdi; this
0x18001750c  call    ?ReduceToRealClasses@CAssocQuery@@AEAAJAEAVCFlexArray@@@Z; CAssocQuery::ReduceToRealClasses(CFlexArray &)
0x180017511  mov     [rbp+var_38], eax
0x180017514  test    eax, eax
0x180017516  js      loc_180017758
0x18001751c  mov     rdx, rbx; struct CFlexArray *
0x18001751f  call    ?RemoveNonDynClasses@CAssocQuery@@AEAAJAEAVCFlexArray@@@Z; CAssocQuery::RemoveNonDynClasses(CFlexArray &)
0x180017524  mov     [rbp+var_38], eax
0x180017527  test    eax, eax
0x180017529  js      loc_18001779C
0x18001752f  mov     rdx, rbx; struct CFlexArray *
0x180017532  mov     rcx, rdi; this
0x180017535  call    ?NormalQ_PreQueryClassFilter@CAssocQuery@@AEAAJAEAVCFlexArray@@@Z; CAssocQuery::NormalQ_PreQueryClassFilter(CFlexArray &)
0x18001753a  mov     [rbp+var_38], eax
0x18001753d  test    eax, eax
0x18001753f  js      loc_1800177D4
0x180017545  cmp     cs:?g_bDontAllowNewConnections@@3HA, 0; int g_bDontAllowNewConnections
0x18001754c  jnz     loc_1800175F5
0x180017552  mov     rcx, rdi; this
0x180017555  test    r15b, 2
0x180017559  jz      loc_1800175EB
0x18001755f  call    ?NormalQ_ReferencesOf@CAssocQuery@@AEAAJXZ; CAssocQuery::NormalQ_ReferencesOf(void)
0x180017564  mov     ebx, eax
0x180017566  mov     [rbp+var_38], eax
0x180017569  test    eax, eax
0x18001756b  js      loc_1800176CA
0x180017571  mov     esi, r15d
0x180017574  and     esi, 1
0x180017577  cmp     dword ptr [rdi+120h], 0
0x18001757e  jnz     loc_18001760F
0x180017584  test    esi, esi
0x180017586  jnz     loc_18001765A
0x18001758c  test    ebx, ebx
0x18001758e  js      loc_180017863
0x180017594  lea     rax, WPP_GLOBAL_Control
0x18001759b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800175a2  cmp     rcx, rax
0x1800175a5  jz      short loc_1800175B1
0x1800175a7  test    byte ptr [rcx+1Ch], 1
0x1800175ab  jnz     loc_1800176A0
0x1800175b1  mov     rcx, [r14]
0x1800175b4  mov     rax, [rcx+20h]
0x1800175b8  mov     rcx, [rbp+var_30]
0x1800175bc  mov     [rsp+68h+var_48], rcx
0x1800175c1  xor     r9d, r9d
0x1800175c4  mov     r8d, [rbp+var_38]
0x1800175c8  xor     edx, edx
0x1800175ca  mov     rcx, r14
0x1800175cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175d2  mov     eax, ebx
0x1800175d4  add     rsp, 68h
0x1800175d8  pop     r15
0x1800175da  pop     r14
0x1800175dc  pop     rdi
0x1800175dd  pop     rsi
0x1800175de  pop     rbx
0x1800175df  pop     rbp
0x1800175e0  retn
0x1800175e1  mov     ebx, 80041006h
0x1800175e6  mov     [rbp+var_38], ebx
0x1800175e9  jmp     short loc_1800175B1
0x1800175eb  call    ?NormalQ_AssociatorsOf@CAssocQuery@@AEAAJXZ; CAssocQuery::NormalQ_AssociatorsOf(void)
0x1800175f0  jmp     loc_180017564
0x1800175f5  mov     ebx, 80041033h
0x1800175fa  mov     [rbp+var_38], ebx
0x1800175fd  lea     r8, [rbp+var_30]; struct IWbemClassObject **
0x180017601  lea     rdx, [rbp+var_38]; int *
0x180017605  mov     rcx, r14; struct IWbemObjectSink *
0x180017608  call    ?Sink_Return@@YAXPEAUIWbemObjectSink@@AEAJAEAPEAUIWbemClassObject@@@Z; Sink_Return(IWbemObjectSink *,long &,IWbemClassObject * &)
0x18001760d  jmp     short loc_1800175D2
0x18001760f  mov     edx, 0FAh; dwMilliseconds
0x180017614  mov     rcx, [rdi+128h]; hHandle
0x18001761b  call    cs:__imp_WaitForSingleObject
0x180017621  test    esi, esi
0x180017623  jnz     short loc_180017686
0x180017625  mov     ebx, [rbp+var_38]
0x180017628  test    ebx, ebx
0x18001762a  jns     short loc_18001766F
0x18001762c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180017632  mov     edx, [rbp+var_38]
0x180017635  mov     rcx, rax
0x180017638  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001763e  lea     rax, WPP_GLOBAL_Control
0x180017645  mov     rcx, cs:WPP_GLOBAL_Control
0x18001764c  cmp     rcx, rax
0x18001764f  jnz     loc_18001784D
0x180017655  mov     ebx, [rbp+var_38]
0x180017658  jmp     short loc_1800175FD
0x18001765a  or      edx, 0FFFFFFFFh; int
0x18001765d  mov     rcx, rdi; this
0x180017660  call    ?ResolveEpPathsToObjects@CAssocQuery@@AEAAJH@Z; CAssocQuery::ResolveEpPathsToObjects(int)
0x180017665  mov     ebx, eax
0x180017667  mov     [rbp+var_38], eax
0x18001766a  jmp     loc_18001758C
0x18001766f  cmp     byte ptr [rdi+2F8h], 0
0x180017676  jz      loc_180017577
0x18001767c  mov     ebx, 80041032h
0x180017681  jmp     loc_1800175FA
0x180017686  test    r15b, 4
0x18001768a  jnz     short loc_180017625
0x18001768c  mov     edx, 5; int
0x180017691  mov     rcx, rdi; this
0x180017694  call    ?ResolveEpPathsToObjects@CAssocQuery@@AEAAJH@Z; CAssocQuery::ResolveEpPathsToObjects(int)
0x180017699  mov     ebx, eax
0x18001769b  mov     [rbp+var_38], eax
0x18001769e  jmp     short loc_180017628
0x1800176a0  cmp     byte ptr [rcx+19h], 2
0x1800176a4  jb      loc_1800175B1
0x1800176aa  mov     edx, 16h
0x1800176af  mov     r9d, ebx
0x1800176b2  lea     r8, WPP_2f04df46b09834ff6d8f033aca1000f6_Traceguids
0x1800176b9  mov     rcx, [rcx+10h]
0x1800176bd  call    WPP_SF_d
0x1800176c2  mov     ebx, [rbp+var_38]
0x1800176c5  jmp     loc_1800175B1
0x1800176ca  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800176d0  mov     edx, [rbp+var_38]
0x1800176d3  mov     rcx, rax
0x1800176d6  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800176dc  lea     rax, WPP_GLOBAL_Control
0x1800176e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800176ea  cmp     rcx, rax
0x1800176ed  jz      loc_180017655
0x1800176f3  test    byte ptr [rcx+1Ch], 1
0x1800176f7  jz      loc_180017655
0x1800176fd  cmp     byte ptr [rcx+19h], 2
0x180017701  jb      loc_180017655
0x180017707  mov     edx, 14h
0x18001770c  jmp     loc_180017834
0x180017711  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180017717  mov     edx, [rbp+var_38]
0x18001771a  mov     rcx, rax
0x18001771d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180017723  lea     rax, WPP_GLOBAL_Control
0x18001772a  mov     rcx, cs:WPP_GLOBAL_Control
0x180017731  cmp     rcx, rax
0x180017734  jz      loc_18001781E
0x18001773a  test    byte ptr [rcx+1Ch], 1
0x18001773e  jz      loc_18001781E
0x180017744  cmp     byte ptr [rcx+19h], 2
0x180017748  jb      loc_18001781E
0x18001774e  mov     edx, 10h
0x180017753  jmp     loc_18001780A
0x180017758  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001775e  mov     edx, [rbp+var_38]
0x180017761  mov     rcx, rax
0x180017764  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001776a  lea     rax, WPP_GLOBAL_Control
0x180017771  mov     rcx, cs:WPP_GLOBAL_Control
0x180017778  cmp     rcx, rax
0x18001777b  jz      loc_18001781E
0x180017781  test    byte ptr [rcx+1Ch], 1
0x180017785  jz      loc_18001781E
0x18001778b  cmp     byte ptr [rcx+19h], 2
0x18001778f  jb      loc_18001781E
0x180017795  mov     edx, 11h
0x18001779a  jmp     short loc_18001780A
0x18001779c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800177a2  mov     edx, [rbp+var_38]
0x1800177a5  mov     rcx, rax
0x1800177a8  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800177ae  lea     rax, WPP_GLOBAL_Control
0x1800177b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800177bc  cmp     rcx, rax
0x1800177bf  jz      short loc_18001781E
0x1800177c1  test    byte ptr [rcx+1Ch], 1
0x1800177c5  jz      short loc_18001781E
0x1800177c7  cmp     byte ptr [rcx+19h], 2
0x1800177cb  jb      short loc_18001781E
0x1800177cd  mov     edx, 12h
0x1800177d2  jmp     short loc_18001780A
0x1800177d4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800177da  mov     edx, [rbp+var_38]
0x1800177dd  mov     rcx, rax
0x1800177e0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800177e6  lea     rax, WPP_GLOBAL_Control
0x1800177ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800177f4  cmp     rcx, rax
0x1800177f7  jz      short loc_18001781E
0x1800177f9  test    byte ptr [rcx+1Ch], 1
0x1800177fd  jz      short loc_18001781E
0x1800177ff  cmp     byte ptr [rcx+19h], 2
0x180017803  jb      short loc_18001781E
0x180017805  mov     edx, 13h
0x18001780a  mov     r9d, [rbp+var_38]
0x18001780e  lea     r8, WPP_2f04df46b09834ff6d8f033aca1000f6_Traceguids
0x180017815  mov     rcx, [rcx+10h]
0x180017819  call    WPP_SF_d
0x18001781e  mov     ebx, [rbp+var_38]
0x180017821  lea     rcx, [rbp+var_28]
0x180017825  call    ??1?$OnDeleteIf3@PEAUIWbemObjectSink@@AEAJAEAPEAUIWbemClassObject@@P6AXPEAU1@AEAJAEAPEAU2@@Z$1?Sink_Return@@YAX012@Z@@QEAA@XZ; OnDeleteIf3<IWbemObjectSink *,long &,IWbemClassObject * &,void (*)(IWbemObjectSink *,long &,IWbemClassObject * &),&Sink_Return(IWbemObjectSink *,long &,IWbemClassObject * &)>::~OnDeleteIf3<IWbemObjectSink *,long &,IWbemClassObject * &,void (*)(IWbemObjectSink *,long &,IWbemClassObject * &),&Sink_Return(IWbemObjectSink *,long &,IWbemClassObject * &)>(void)
0x18001782a  jmp     loc_1800175D2
0x18001782f  mov     edx, 15h
0x180017834  mov     r9d, [rbp+var_38]
0x180017838  lea     r8, WPP_2f04df46b09834ff6d8f033aca1000f6_Traceguids
0x18001783f  mov     rcx, [rcx+10h]
0x180017843  call    WPP_SF_d
0x180017848  jmp     loc_180017655
0x18001784d  test    byte ptr [rcx+1Ch], 1
0x180017851  jz      loc_180017655
0x180017857  cmp     byte ptr [rcx+19h], 2
0x18001785b  jb      loc_180017655
0x180017861  jmp     short loc_18001782F
0x180017863  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180017869  mov     edx, [rbp+var_38]
0x18001786c  mov     rcx, rax
0x18001786f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180017875  mov     ebx, [rbp+var_38]
0x180017878  jmp     loc_180017594
```
