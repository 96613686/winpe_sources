# DBSession::_GetTableMaxLongRevision(ulong,unsigned __int64 *)

- ea: `0x180002344`
- end: `0x180002603`
- name: `?_GetTableMaxLongRevision@DBSession@@AEAAJKPEA_K@Z`
- size: `703`
- prototype: `int(DBSession *__hidden this, unsigned int, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000224c`

## callees

- `0x180002344`
- `0x18000260c`
- `0x180002880`
- `0x1800029e0`
- `0x180002b80`
- `0x1800068f0`
- `0x18000f530`
- `0x180011ed0`
- `0x180012098`
- `0x1800131c8`
- `0x18001323c`
- `0x180013484`
- `0x1800737b4`
- `0x1800c50f0`

## import_xrefs

- `ESENT!JetOpenTableW` at `0x1800023c7`
- `ESENT!JetOpenTableW` at `0x1800023c7`
- `ESENT!JetSetCurrentIndexA` at `0x180002429`
- `ESENT!JetSetCurrentIndexA` at `0x180002429`

## string_xrefs

- `0x18000251b`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbsession.cpp`
- `0x1800025c5`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbsession.cpp`
- `0x180002573`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\jetinterop.h`
- `0x1800025ee`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\jetinterop.h`

## pseudocode

```c
__int64 __fastcall DBSession::_GetTableMaxLongRevision(DBSession *this, unsigned int a2, unsigned __int64 *a3)
{
  __int64 v5; // rdi
  unsigned int TableClassGrBit; // eax
  JET_ERR v7; // ebx
  unsigned int HresultFromJetError; // ebx
  int v9; // eax
  JET_ERR v10; // eax
  unsigned int v11; // r9d
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  int Column; // eax
  int v17; // eax
  __int64 v19; // r9
  __int64 v20; // rdx
  __int64 v21; // rcx
  int v22; // eax
  unsigned int v23; // eax
  __int64 v24; // r9
  __int64 v25; // rdx
  unsigned int v26; // eax
  struct JET_RETINFO *v27; // [rsp+38h] [rbp-48h]
  JET_SESID sesid; // [rsp+40h] [rbp-40h] BYREF
  JET_TABLEID tableid; // [rsp+48h] [rbp-38h] BYREF
  unsigned int v30; // [rsp+50h] [rbp-30h] BYREF
  unsigned int v31[2]; // [rsp+58h] [rbp-28h] BYREF
  char szIndexName[16]; // [rsp+68h] [rbp-18h] BYREF

  *a3 = 0;
  sesid = *((_QWORD *)this + 27);
  v5 = a2;
  tableid = -1;
  TableClassGrBit = GetTableClassGrBit(a2);
  v7 = JetOpenTableW(
         *((_QWORD *)this + 27),
         *((_DWORD *)this + 56),
         (&g_rgTableInfo)[12 * v5],
         0,
         0,
         TableClassGrBit | 4,
         &tableid);
  CheckCorruption(v7);
  if ( v7 < 0 )
  {
    HresultFromJetError = MakeHresultFromJetError(v7);
    v19 = 2140;
    v20 = 0;
    v21 = HresultFromJetError;
LABEL_18:
    Log_UnistoreHREvent_0(
      v21,
      v20,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbsession.cpp",
      v19);
    v22 = auto_JET_TABLEID::close((auto_JET_TABLEID *)&sesid);
    if ( v22 < 0 )
    {
      v23 = MakeHresultFromJetError(v22);
      Log_UnistoreHREvent_0(
        v23,
        0,
        "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\jetinterop.h",
        261);
    }
    return HresultFromJetError;
  }
  v30 = 0;
  HresultFromJetError = _FindLongRevisionIndex(v5, &v30);
  if ( (HresultFromJetError & 0x80000000) != 0 )
  {
    v19 = 2143;
    v20 = 1;
LABEL_17:
    v21 = HresultFromJetError;
    goto LABEL_18;
  }
  v9 = StringCchPrintfA(szIndexName, 9u, "%08x", v30);
  HresultFromJetError = v9;
  if ( v9 < 0 )
  {
    v24 = 2146;
    v25 = 1;
LABEL_28:
    Log_UnistoreHREvent_0(
      (unsigned int)v9,
      v25,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbsession.cpp",
      v24);
    auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
    return HresultFromJetError;
  }
  v10 = JetSetCurrentIndexA(sesid, tableid, szIndexName);
  if ( v10 < 0 )
  {
    v9 = MakeHresultFromJetError(v10);
    v24 = 2148;
    goto LABEL_27;
  }
  v12 = CommsESE_JetMove(*((_QWORD *)this + 27), tableid, 0x7FFFFFFF, v11);
  if ( v12 != -1603 )
  {
    if ( v12 >= 0 )
    {
      *(_QWORD *)v31 = 0;
      if ( (unsigned int)ColumnIdMappings::PropIdToColumnId(v13, (unsigned int)v5, 929300585, v31) )
      {
        if ( (v31[1] & 0x400) != 0 )
          Log_AssertionEvent_3(v15, v14, 2162);
        Column = CommsESE_JetRetrieveColumn(*((_QWORD *)this + 27), tableid, v31[0], a3, 8u, 0, 1u, v27);
        if ( Column == -1603 || Column == -1507 || Column >= 0 )
          goto LABEL_13;
        v9 = MakeHresultFromJetError(Column);
        v24 = 2179;
        goto LABEL_27;
      }
      Log_AssertionEvent_3(v15, v14, 2160);
      v19 = 2161;
      v20 = 0;
      HresultFromJetError = -2147418113;
      goto LABEL_17;
    }
    v9 = MakeHresultFromJetError(v12);
    v24 = 2156;
LABEL_27:
    HresultFromJetError = v9;
    v25 = 0;
    goto LABEL_28;
  }
LABEL_13:
  v17 = auto_JET_TABLEID::close((auto_JET_TABLEID *)&sesid);
  if ( v17 < 0 )
  {
    v26 = MakeHresultFromJetError(v17);
    Log_UnistoreHREvent_0(
      v26,
      0,
      "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\jetinterop.h",
      261);
  }
  return 0;
}

```

## disassembly

```asm
0x180002344  push    rbp
0x180002346  push    rbx
0x180002347  push    rsi
0x180002348  push    rdi
0x180002349  push    r14
0x18000234b  mov     rbp, rsp
0x18000234e  sub     rsp, 80h
0x180002355  mov     rax, cs:__security_cookie
0x18000235c  xor     rax, rsp
0x18000235f  mov     [rbp+var_8], rax
0x180002363  mov     qword ptr [r8], 0
0x18000236a  mov     rsi, rcx
0x18000236d  mov     rax, [rcx+0D8h]
0x180002374  mov     r14, r8
0x180002377  mov     ecx, edx; unsigned int
0x180002379  mov     [rbp+sesid], rax
0x18000237d  mov     edi, edx
0x18000237f  mov     [rbp+tableid], 0FFFFFFFFFFFFFFFFh
0x180002387  call    ?GetTableClassGrBit@@YAKK@Z; GetTableClassGrBit(ulong)
0x18000238c  lea     rdx, ?g_rgTableInfo@@3QBUUSTableInfo@@B; USTableInfo const near * const g_rgTableInfo
0x180002393  or      eax, 4
0x180002396  lea     rcx, [rbp+tableid]
0x18000239a  xor     r9d, r9d; pvParameters
0x18000239d  mov     [rsp+80h+ptableid], rcx; ptableid
0x1800023a2  lea     r8, [rdi+rdi*2]
0x1800023a6  mov     rcx, [rsi+0D8h]; sesid
0x1800023ad  shl     r8, 5
0x1800023b1  mov     [rsp+80h+grbit], eax; grbit
0x1800023b5  mov     [rsp+80h+cbParameters], 0; cbParameters
0x1800023bd  mov     r8, [r8+rdx]; szTableName
0x1800023c1  mov     edx, [rsi+0E0h]; dbid
0x1800023c7  call    cs:__imp_JetOpenTableW
0x1800023cd  mov     ecx, eax; int
0x1800023cf  mov     ebx, eax
0x1800023d1  call    ?CheckCorruption@@YAXJ@Z; CheckCorruption(long)
0x1800023d6  test    ebx, ebx
0x1800023d8  js      loc_180002548
0x1800023de  lea     rdx, [rbp+var_30]; unsigned int *
0x1800023e2  mov     [rbp+var_30], 0
0x1800023e9  mov     ecx, edi; unsigned int
0x1800023eb  call    ?_FindLongRevisionIndex@@YAJKPEAK@Z; _FindLongRevisionIndex(ulong,ulong *)
0x1800023f0  mov     ebx, eax
0x1800023f2  test    eax, eax
0x1800023f4  js      loc_18000255D
0x1800023fa  mov     r9d, [rbp+var_30]
0x1800023fe  lea     r8, a08x; "%08x"
0x180002405  mov     edx, 9; unsigned __int64
0x18000240a  lea     rcx, [rbp+szIndexName]; char *
0x18000240e  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180002413  mov     ebx, eax
0x180002415  test    eax, eax
0x180002417  js      loc_180002589
0x18000241d  mov     rdx, [rbp+tableid]; tableid
0x180002421  lea     r8, [rbp+szIndexName]; szIndexName
0x180002425  mov     rcx, [rbp+sesid]; sesid
0x180002429  call    cs:__imp_JetSetCurrentIndexA
0x18000242f  test    eax, eax
0x180002431  js      loc_180002596
0x180002437  mov     rdx, [rbp+tableid]; unsigned __int64
0x18000243b  mov     r8d, 7FFFFFFFh; int
0x180002441  mov     rcx, [rsi+0D8h]; unsigned __int64
0x180002448  call    ?CommsESE_JetMove@@YAJ_K0JK@Z; CommsESE_JetMove(unsigned __int64,unsigned __int64,long,ulong)
0x18000244d  mov     ebx, 0FFFFF9BDh
0x180002452  cmp     eax, ebx
0x180002454  jz      short loc_1800024D4
0x180002456  test    eax, eax
0x180002458  js      loc_1800025A5
0x18000245e  xor     eax, eax
0x180002460  lea     r9, [rbp+var_28]
0x180002464  mov     r8d, 37640069h
0x18000246a  mov     qword ptr [rbp+var_28], rax
0x18000246e  mov     edx, edi
0x180002470  call    ?PropIdToColumnId@ColumnIdMappings@@QEAAHW4US_TABLEID@@KPEAUColumnDetails@@@Z; ColumnIdMappings::PropIdToColumnId(US_TABLEID,ulong,ColumnDetails *)
0x180002475  test    eax, eax
0x180002477  jz      loc_180002501
0x18000247d  test    [rbp+var_28+4], 400h
0x180002484  jnz     loc_180002538
0x18000248a  mov     r8d, [rbp+var_28]; unsigned int
0x18000248e  mov     r9, r14; void *
0x180002491  mov     rdx, [rbp+tableid]; unsigned __int64
0x180002495  mov     rcx, [rsi+0D8h]; unsigned __int64
0x18000249c  mov     dword ptr [rsp+80h+ptableid], 1; JET_GRBIT
0x1800024a4  mov     qword ptr [rsp+80h+grbit], 0; unsigned int *
0x1800024ad  mov     [rsp+80h+cbParameters], 8; unsigned int
0x1800024b5  call    ?CommsESE_JetRetrieveColumn@@YAJ_K0KPEAXKPEAKKPEAUJET_RETINFO@@@Z; CommsESE_JetRetrieveColumn(unsigned __int64,unsigned __int64,ulong,void *,ulong,ulong *,ulong,JET_RETINFO *)
0x1800024ba  cmp     eax, ebx
0x1800024bc  jz      short loc_1800024D4
0x1800024be  cmp     eax, 0FFFFFA1Dh
0x1800024c3  jz      short loc_1800024D4
0x1800024c5  cmp     eax, 3ECh
0x1800024ca  jz      short loc_1800024D4
0x1800024cc  test    eax, eax
0x1800024ce  js      loc_1800025B4
0x1800024d4  lea     rcx, [rbp+sesid]; this
0x1800024d8  call    ?close@auto_JET_TABLEID@@QEAAJXZ; auto_JET_TABLEID::close(void)
0x1800024dd  test    eax, eax
0x1800024df  js      loc_1800025E1
0x1800024e5  xor     eax, eax
0x1800024e7  mov     rcx, [rbp+var_8]
0x1800024eb  xor     rcx, rsp; StackCookie
0x1800024ee  call    __security_check_cookie
0x1800024f3  add     rsp, 80h
0x1800024fa  pop     r14
0x1800024fc  pop     rdi
0x1800024fd  pop     rsi
0x1800024fe  pop     rbx
0x1800024ff  pop     rbp
0x180002500  retn
0x180002501  mov     r8d, 870h
0x180002507  call    Log_AssertionEvent_3
0x18000250c  mov     r9d, 871h
0x180002512  xor     edx, edx
0x180002514  mov     ebx, 8000FFFFh
0x180002519  mov     ecx, ebx
0x18000251b  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180002522  call    Log_UnistoreHREvent_0
0x180002527  lea     rcx, [rbp+sesid]; this
0x18000252b  call    ?close@auto_JET_TABLEID@@QEAAJXZ; auto_JET_TABLEID::close(void)
0x180002530  test    eax, eax
0x180002532  js      short loc_18000256A
0x180002534  mov     eax, ebx
0x180002536  jmp     short loc_1800024E7
0x180002538  mov     r8d, 872h
0x18000253e  call    Log_AssertionEvent_3
0x180002543  jmp     loc_18000248A
0x180002548  mov     ecx, ebx; int
0x18000254a  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x18000254f  mov     ebx, eax
0x180002551  mov     r9d, 85Ch
0x180002557  xor     edx, edx
0x180002559  mov     ecx, eax
0x18000255b  jmp     short loc_18000251B
0x18000255d  mov     r9d, 85Fh
0x180002563  mov     edx, 1
0x180002568  jmp     short loc_180002519
0x18000256a  mov     ecx, eax; int
0x18000256c  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180002571  mov     ecx, eax
0x180002573  lea     r8, aOnecoreuapBase_50; "onecoreuap\\base\\AppModel\\UserDataAcc"...
0x18000257a  mov     r9d, 105h
0x180002580  xor     edx, edx
0x180002582  call    Log_UnistoreHREvent_0
0x180002587  jmp     short loc_180002534
0x180002589  mov     r9d, 862h
0x18000258f  mov     edx, 1
0x180002594  jmp     short loc_1800025C5
0x180002596  mov     ecx, eax; int
0x180002598  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x18000259d  mov     r9d, 864h
0x1800025a3  jmp     short loc_1800025C1
0x1800025a5  mov     ecx, eax; int
0x1800025a7  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800025ac  mov     r9d, 86Ch
0x1800025b2  jmp     short loc_1800025C1
0x1800025b4  mov     ecx, eax; int
0x1800025b6  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800025bb  mov     r9d, 883h
0x1800025c1  mov     ebx, eax
0x1800025c3  xor     edx, edx
0x1800025c5  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800025cc  mov     ecx, eax
0x1800025ce  call    Log_UnistoreHREvent_0
0x1800025d3  lea     rcx, [rbp+sesid]; this
0x1800025d7  call    ??1auto_JET_TABLEID@@QEAA@XZ; auto_JET_TABLEID::~auto_JET_TABLEID(void)
0x1800025dc  jmp     loc_180002534
0x1800025e1  mov     ecx, eax; int
0x1800025e3  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800025e8  mov     r9d, 105h
0x1800025ee  lea     r8, aOnecoreuapBase_50; "onecoreuap\\base\\AppModel\\UserDataAcc"...
0x1800025f5  xor     edx, edx
0x1800025f7  mov     ecx, eax
0x1800025f9  call    Log_UnistoreHREvent_0
0x1800025fe  jmp     loc_1800024E5
```
