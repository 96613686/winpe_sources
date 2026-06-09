# ColumnIdMappings::Initialize(unsigned __int64,unsigned __int64,ulong,ushort const *)

- ea: `0x180014774`
- end: `0x180014914`
- name: `?Initialize@ColumnIdMappings@@QEAAJ_K0KPEBG@Z`
- size: `416`
- prototype: `int(ColumnIdMappings *__hidden this, unsigned __int64, unsigned __int64, unsigned int, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, service_task`

## callers

- `0x180001e80`
- `0x180001f94`
- `0x1800ad418`

## callees

- `0x1800068f0`
- `0x18000f530`
- `0x180011ed0`
- `0x180012098`
- `0x180012628`
- `0x1800131c8`
- `0x18001323c`
- `0x180014774`
- `0x18001c1a0`
- `0x1800254e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001487f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001487f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014797`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014797`
- `ESENT!JetOpenTableW` at `0x180014829`
- `ESENT!JetOpenTableW` at `0x180014829`

## string_xrefs

- `0x180014897`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x1800148eb`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x1800148bc`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\jetinterop.h`

## pseudocode

```c
__int64 __fastcall ColumnIdMappings::Initialize(
        ColumnIdMappings *this,
        unsigned __int64 a2,
        JET_SESID a3,
        JET_DBID a4,
        const unsigned __int16 *a5)
{
  __int64 i; // rdi
  unsigned int TableClassGrBit; // eax
  JET_ERR v10; // ebx
  ColumnIdMappings *v11; // rcx
  int v12; // eax
  unsigned int v13; // ebx
  int v14; // eax
  unsigned int HresultFromJetError; // eax
  __int64 v17; // r9
  __int64 v18; // rdx
  JET_SESID v19; // [rsp+40h] [rbp-48h] BYREF
  JET_TABLEID ptableid; // [rsp+48h] [rbp-40h] BYREF
  int v21; // [rsp+50h] [rbp-38h] BYREF
  RTL_SRWLOCK *v22; // [rsp+58h] [rbp-30h]

  v22 = &g_columnIdMapping;
  AcquireSRWLockExclusive(&g_columnIdMapping);
  v21 = 2;
  if ( dword_18010D248 )
  {
LABEL_12:
    ReleaseSRWLockExclusive(&g_columnIdMapping);
    return 0;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           &qword_18010D268,
                           a5) )
  {
    v13 = -2147024882;
    Log_UnistoreHREvent_0(
      2147942414LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
      47);
    goto LABEL_17;
  }
  xmmword_18010D250 = a2;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= 0x36 )
    {
      dword_18010D248 = 1;
      goto LABEL_12;
    }
    v19 = a3;
    ptableid = -1;
    TableClassGrBit = GetTableClassGrBit(i);
    v10 = JetOpenTableW(a3, a4, (&g_rgTableInfo)[12 * i], 0, 0, TableClassGrBit | 4, &ptableid);
    CheckCorruption(v10);
    if ( v10 == -1305 )
      goto LABEL_8;
    if ( v10 < 0 )
      break;
    v12 = ColumnIdMappings::_CacheTableColumnIds(v11, i, a3, ptableid);
    v13 = v12;
    if ( v12 < 0 )
    {
      v17 = 71;
      v18 = 1;
      goto LABEL_16;
    }
LABEL_8:
    v14 = auto_JET_TABLEID::close((auto_JET_TABLEID *)&v19);
    if ( v14 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v14);
      Log_UnistoreHREvent_0(
        HresultFromJetError,
        0,
        "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\jetinterop.h",
        261);
    }
  }
  v12 = MakeHresultFromJetError(v10);
  v13 = v12;
  v17 = 69;
  v18 = 0;
LABEL_16:
  Log_UnistoreHREvent_0(
    (unsigned int)v12,
    v18,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
    v17);
  auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&v19);
LABEL_17:
  AutoSRWLock::~AutoSRWLock((AutoSRWLock *)&v21);
  return v13;
}

```

## disassembly

```asm
0x180014774  push    rbx
0x180014776  push    rbp
0x180014777  push    rsi
0x180014778  push    rdi
0x180014779  push    r14
0x18001477b  sub     rsp, 60h
0x18001477f  lea     r14, ?g_columnIdMapping@@3VColumnIdMappings@@A; ColumnIdMappings g_columnIdMapping
0x180014786  mov     ebp, r9d
0x180014789  mov     rcx, r14; SRWLock
0x18001478c  mov     [rsp+88h+var_30], r14
0x180014791  mov     rsi, r8
0x180014794  mov     rbx, rdx
0x180014797  call    cs:__imp_AcquireSRWLockExclusive
0x18001479d  cmp     cs:dword_18010D248, 0
0x1800147a4  mov     [rsp+88h+var_38], 2
0x1800147ac  jnz     loc_18001487C
0x1800147b2  mov     rdx, [rsp+88h+arg_20]
0x1800147ba  lea     rcx, qword_18010D268
0x1800147c1  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1800147c6  test    al, al
0x1800147c8  jz      loc_180014892
0x1800147ce  mov     qword ptr cs:xmmword_18010D250, rbx
0x1800147d5  xor     edi, edi
0x1800147d7  cmp     edi, 36h ; '6'
0x1800147da  jnb     loc_180014872
0x1800147e0  mov     ecx, edi; unsigned int
0x1800147e2  mov     [rsp+88h+var_48], rsi
0x1800147e7  mov     [rsp+88h+var_40], 0FFFFFFFFFFFFFFFFh
0x1800147f0  call    ?GetTableClassGrBit@@YAKK@Z; GetTableClassGrBit(ulong)
0x1800147f5  lea     rdx, ?g_rgTableInfo@@3QBUUSTableInfo@@B; USTableInfo const near * const g_rgTableInfo
0x1800147fc  or      eax, 4
0x1800147ff  lea     rcx, [rsp+88h+var_40]
0x180014804  xor     r9d, r9d; pvParameters
0x180014807  mov     [rsp+88h+ptableid], rcx; ptableid
0x18001480c  lea     r8, [rdi+rdi*2]
0x180014810  shl     r8, 5
0x180014814  mov     rcx, rsi; sesid
0x180014817  mov     [rsp+88h+grbit], eax; grbit
0x18001481b  mov     [rsp+88h+cbParameters], 0; cbParameters
0x180014823  mov     r8, [r8+rdx]; szTableName
0x180014827  mov     edx, ebp; dbid
0x180014829  call    cs:__imp_JetOpenTableW
0x18001482f  mov     ecx, eax; int
0x180014831  mov     ebx, eax
0x180014833  call    ?CheckCorruption@@YAXJ@Z; CheckCorruption(long)
0x180014838  cmp     ebx, 0FFFFFAE7h
0x18001483e  jz      short loc_18001485D
0x180014840  test    ebx, ebx
0x180014842  js      loc_1800148DA
0x180014848  mov     r9, [rsp+88h+var_40]; unsigned __int64
0x18001484d  mov     r8, rsi; unsigned __int64
0x180014850  mov     edx, edi; unsigned int
0x180014852  call    ?_CacheTableColumnIds@ColumnIdMappings@@AEAAJK_K0@Z; ColumnIdMappings::_CacheTableColumnIds(ulong,unsigned __int64,unsigned __int64)
0x180014857  mov     ebx, eax
0x180014859  test    eax, eax
0x18001485b  js      short loc_1800148CE
0x18001485d  lea     rcx, [rsp+88h+var_48]; this
0x180014862  call    ?close@auto_JET_TABLEID@@QEAAJXZ; auto_JET_TABLEID::close(void)
0x180014867  test    eax, eax
0x180014869  js      short loc_1800148AF
0x18001486b  inc     edi
0x18001486d  jmp     loc_1800147D7
0x180014872  mov     cs:dword_18010D248, 1
0x18001487c  mov     rcx, r14; SRWLock
0x18001487f  call    cs:__imp_ReleaseSRWLockExclusive
0x180014885  xor     eax, eax
0x180014887  add     rsp, 60h
0x18001488b  pop     r14
0x18001488d  pop     rdi
0x18001488e  pop     rsi
0x18001488f  pop     rbp
0x180014890  pop     rbx
0x180014891  retn
0x180014892  mov     ebx, 8007000Eh
0x180014897  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001489e  mov     ecx, ebx
0x1800148a0  mov     r9d, 2Fh ; '/'
0x1800148a6  xor     edx, edx
0x1800148a8  call    Log_UnistoreHREvent_0
0x1800148ad  jmp     short loc_180014903
0x1800148af  mov     ecx, eax; int
0x1800148b1  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800148b6  mov     r9d, 105h
0x1800148bc  lea     r8, aOnecoreuapBase_50; "onecoreuap\\base\\AppModel\\UserDataAcc"...
0x1800148c3  xor     edx, edx
0x1800148c5  mov     ecx, eax
0x1800148c7  call    Log_UnistoreHREvent_0
0x1800148cc  jmp     short loc_18001486B
0x1800148ce  mov     r9d, 47h ; 'G'
0x1800148d4  lea     edx, [r9-46h]
0x1800148d8  jmp     short loc_1800148EB
0x1800148da  mov     ecx, ebx; int
0x1800148dc  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800148e1  mov     ebx, eax
0x1800148e3  mov     r9d, 45h ; 'E'
0x1800148e9  xor     edx, edx
0x1800148eb  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800148f2  mov     ecx, eax
0x1800148f4  call    Log_UnistoreHREvent_0
0x1800148f9  lea     rcx, [rsp+88h+var_48]; this
0x1800148fe  call    ??1auto_JET_TABLEID@@QEAA@XZ; auto_JET_TABLEID::~auto_JET_TABLEID(void)
0x180014903  lea     rcx, [rsp+88h+var_38]; this
0x180014908  call    ??1AutoSRWLock@@QEAA@XZ; AutoSRWLock::~AutoSRWLock(void)
0x18001490d  mov     eax, ebx
0x18001490f  jmp     loc_180014887
```
