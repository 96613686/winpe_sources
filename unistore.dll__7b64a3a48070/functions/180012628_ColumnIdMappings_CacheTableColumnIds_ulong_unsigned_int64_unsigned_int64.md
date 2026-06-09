# ColumnIdMappings::_CacheTableColumnIds(ulong,unsigned __int64,unsigned __int64)

- ea: `0x180012628`
- end: `0x180012b7b`
- name: `?_CacheTableColumnIds@ColumnIdMappings@@AEAAJK_K0@Z`
- size: `1363`
- prototype: `int(ColumnIdMappings *__hidden this, unsigned int, unsigned __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180014774`
- `0x180096c58`

## callees

- `0x180002880`
- `0x1800068f0`
- `0x18000d9c0`
- `0x18000f530`
- `0x180011ed0`
- `0x180012098`
- `0x180012628`
- `0x1800131c8`
- `0x18001b030`
- `0x18001b238`
- `0x18001b2a8`
- `0x18006f180`
- `0x18006fb5c`
- `0x180073dbc`
- `0x180078a40`
- `0x180079030`
- `0x180097ae8`
- `0x1800c50aa`
- `0x1800c50f0`

## import_xrefs

- `msvcrt!strtoul` at `0x1800127f9`
- `msvcrt!strtoul` at `0x1800127f9`
- `ESENT!JetMove` at `0x180012958`
- `ESENT!JetMove` at `0x180012958`
- `ESENT!JetRetrieveColumns` at `0x1800127b8`
- `ESENT!JetRetrieveColumns` at `0x1800127b8`
- `ESENT!JetGetTableColumnInfoA` at `0x180012691`
- `ESENT!JetGetTableColumnInfoA` at `0x180012691`

## string_xrefs

- `0x180012708`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x180012b60`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x180012a4d`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\jetinterop.h`
- `0x180012b3e`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\jetinterop.h`

## pseudocode

```c
__int64 __fastcall ColumnIdMappings::_CacheTableColumnIds(
        ColumnIdMappings *this,
        unsigned int a2,
        JET_SESID a3,
        JET_TABLEID a4)
{
  JET_SESID v4; // r15
  __int64 v5; // rdi
  JET_ERR TableColumnInfoA; // ebx
  JET_TABLEID v8; // rdx
  __int64 v9; // rsi
  unsigned int v10; // r9d
  JET_ERR v11; // ebx
  JET_ERR v12; // ebx
  unsigned int v13; // r12d
  __int64 v14; // rcx
  int v15; // r13d
  _QWORD *v16; // rsi
  __int64 v17; // rbx
  __int64 v18; // r14
  __int64 v19; // rax
  __int64 inserted; // r14
  _DWORD *v21; // rax
  void *v22; // rbx
  __int64 v23; // rsi
  char *v24; // rsi
  unsigned int v25; // eax
  __int64 v26; // r9
  __int64 v27; // rcx
  unsigned int v28; // ebx
  int v30; // eax
  int v31; // eax
  unsigned int HresultFromJetError; // eax
  __int64 v33; // r9
  const char *v34; // r8
  unsigned int v35; // eax
  __int64 v36; // [rsp+30h] [rbp-D0h] BYREF
  int v37; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v38; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v39; // [rsp+50h] [rbp-B0h]
  int v40; // [rsp+58h] [rbp-A8h]
  _DWORD *v41; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v42; // [rsp+68h] [rbp-98h] BYREF
  __int64 v43; // [rsp+78h] [rbp-88h]
  _QWORD v44[2]; // [rsp+80h] [rbp-80h] BYREF
  JET_SESID v45; // [rsp+90h] [rbp-70h]
  __int64 v46; // [rsp+98h] [rbp-68h]
  _BYTE v47[16]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE pvResult[8]; // [rsp+B0h] [rbp-50h] BYREF
  JET_TABLEID tableid; // [rsp+B8h] [rbp-48h]
  int v50; // [rsp+C8h] [rbp-38h]
  JET_COLUMNID v51; // [rsp+CCh] [rbp-34h]
  int v52; // [rsp+E4h] [rbp-1Ch]
  int v53; // [rsp+E8h] [rbp-18h]
  JET_RETRIEVECOLUMN pretrievecolumn; // [rsp+100h] [rbp+0h] BYREF
  int v55; // [rsp+130h] [rbp+30h]
  char *v56; // [rsp+138h] [rbp+38h]
  int v57; // [rsp+140h] [rbp+40h]
  int v58; // [rsp+150h] [rbp+50h]
  int v59; // [rsp+158h] [rbp+58h]
  int v60; // [rsp+160h] [rbp+60h]
  char *v61; // [rsp+168h] [rbp+68h]
  int v62; // [rsp+170h] [rbp+70h]
  int v63; // [rsp+180h] [rbp+80h]
  int v64; // [rsp+190h] [rbp+90h]
  int *v65; // [rsp+198h] [rbp+98h]
  int v66; // [rsp+1A0h] [rbp+A0h]
  int v67; // [rsp+1B0h] [rbp+B0h]
  char String[16]; // [rsp+1C0h] [rbp+C0h] BYREF

  v4 = a3;
  v45 = a3;
  v5 = a2;
  memset_0(pvResult, 0, 0x50u);
  TableColumnInfoA = JetGetTableColumnInfoA(v4, a4, 0, pvResult, 0x50u, 1u);
  CheckCorruption(TableColumnInfoA);
  if ( TableColumnInfoA < 0 )
  {
    HresultFromJetError = MakeHresultFromJetError(TableColumnInfoA);
    v28 = HresultFromJetError;
    v34 = "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp";
    v33 = 159;
LABEL_47:
    Log_UnistoreHREvent_0(HresultFromJetError, 0, v34, v33);
    return v28;
  }
  else
  {
    v44[1] = tableid;
    v44[0] = v4;
    v46 = 40 * v5;
    utl::_HashTable<unsigned long,utl::pair<unsigned long const,ColumnDetails>,ColumnIdMappings::ColumnIdHashTraits,utl::equal_to<unsigned long>,utl::allocator<utl::pair<unsigned long const,ColumnDetails>>,0>::clear(&qword_18010C4C8[5 * v5]);
    v8 = tableid;
    v9 = 24LL * (unsigned int)v5;
    v43 = v9;
    *(RTL_SRWLOCK *)((char *)&g_columnIdMapping + v9 + 2176) = *(RTL_SRWLOCK *)((char *)&g_columnIdMapping + v9 + 2168);
    v11 = CommsESE_JetMove(v4, v8, 0x80000000, v10);
    while ( !v11 )
    {
      memset_0(&pretrievecolumn.pvData, 0, 0xB8u);
      pretrievecolumn.columnid = v51;
      pretrievecolumn.pvData = &v36;
      v55 = v50;
      v56 = String;
      v60 = v53;
      v61 = (char *)&v36 + 4;
      v64 = v52;
      v65 = &v37;
      v37 = 0;
      v36 = 0;
      pretrievecolumn.cbData = 4;
      pretrievecolumn.itagSequence = 1;
      v57 = 9;
      v58 = 1;
      v62 = 4;
      v63 = 1;
      v66 = 4;
      v67 = 1;
      v12 = JetRetrieveColumns(v4, tableid, &pretrievecolumn, 4u);
      CheckCorruption(v12);
      if ( v12 < 0 )
      {
        v25 = MakeHresultFromJetError(v12);
        v26 = 196;
        goto LABEL_28;
      }
      if ( pretrievecolumn.err )
      {
        v25 = MakeHresultFromJetError(pretrievecolumn.err);
        v26 = 198;
        goto LABEL_28;
      }
      if ( v59 )
      {
        v25 = MakeHresultFromJetError(v59);
        v26 = 200;
LABEL_28:
        v27 = v25;
        v28 = v25;
        goto LABEL_29;
      }
      String[8] = 0;
      v13 = strtoul(String, 0, 16);
      if ( !v13 )
      {
        v26 = 205;
        v28 = -2147467259;
LABEL_43:
        v27 = v28;
LABEL_29:
        Log_UnistoreHREvent_0(
          v27,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
          v26);
        auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)v44);
        return v28;
      }
      v14 = (unsigned int)v36;
      v15 = v36;
      v39 = v36;
      v16 = (__int64 *)((char *)qword_18010CD38 + v9);
      v40 = v37;
      LODWORD(v38) = v13;
      *(_QWORD *)((char *)&v38 + 4) = v36;
      HIDWORD(v38) = v37;
      v17 = *v16;
      v18 = (__int64)(v16[1] - *v16) >> 4;
      if ( v18 > 0 )
      {
        do
        {
          if ( CompareColumns(
                 (const struct PropIdAndColumnDetails *)(v17 + 16 * ((unsigned __int64)v18 >> 1)),
                 (const struct PropIdAndColumnDetails *)&v38) )
          {
            v17 += 16 * ((unsigned __int64)v18 >> 1) + 16;
            v18 += -1LL - ((unsigned __int64)v18 >> 1);
          }
          else
          {
            v18 = (unsigned __int64)v18 >> 1;
          }
        }
        while ( v18 > 0 );
        v14 = (unsigned int)v36;
        v4 = v45;
        v15 = v39;
      }
      if ( v17 != v16[1] && *(_DWORD *)(v17 + 4) == (_DWORD)v14 )
        Log_AssertionEvent(
          v14,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
          222);
      v19 = v16[1];
      if ( v17 == v19 )
      {
        if ( v19 != v16[2]
          || (unsigned __int8)utl::vector<PropIdAndColumnDetails,utl::allocator<PropIdAndColumnDetails>>::_Grow(v16) )
        {
          *(_OWORD *)v16[1] = v38;
          inserted = v16[1];
          v16[1] = inserted + 16;
        }
        else
        {
          inserted = 0;
        }
      }
      else
      {
        v42 = v38;
        v41 = v16;
        inserted = utl::vector<PropIdAndColumnDetails,utl::allocator<PropIdAndColumnDetails>>::_InsertOne(
                     v16,
                     v17,
                     &v42);
      }
      if ( !inserted )
      {
        v28 = -2147024882;
        Log_UnistoreHREvent_0(
          2147942414LL,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
          225);
        v31 = auto_JET_TABLEID::close((auto_JET_TABLEID *)v44);
        if ( v31 < 0 )
        {
          HresultFromJetError = MakeHresultFromJetError(v31);
          v33 = 261;
          v34 = "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\jetinterop.h";
          goto LABEL_47;
        }
        return v28;
      }
      v21 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
      v22 = v21;
      if ( v21 )
      {
        v23 = v46;
        v21[6] = v13;
        v21[7] = v15;
        v24 = (char *)&g_columnIdMapping + v23;
        v21[8] = HIDWORD(v39);
        v21[9] = v40;
        utl::_HashTable<unsigned long,utl::pair<unsigned long const,ColumnDetails>,ColumnIdMappings::ColumnIdHashTraits,utl::equal_to<unsigned long>,utl::allocator<utl::pair<unsigned long const,ColumnDetails>>,0>::_FindInsertPos(
          v24 + 8,
          &v41,
          v21 + 6);
        if ( BYTE8(v42) )
        {
          operator delete(v22);
          v21 = v41;
        }
        else
        {
          v21 = *(_DWORD **)utl::_HashTable<unsigned long,utl::pair<unsigned long const,ATL::CComPtr<ISyncKnowledge>>,utl::hash<unsigned long>,utl::equal_to<unsigned long>,utl::allocator<utl::pair<unsigned long const,ATL::CComPtr<ISyncKnowledge>>>,0>::_InsertAt(
                              v24 + 8,
                              v47,
                              &v41,
                              v22);
        }
      }
      if ( !v21 )
      {
        utl::vector<PropIdAndColumnDetails,utl::allocator<PropIdAndColumnDetails>>::erase(
          (char *)&g_columnIdMapping + v43 + 2168,
          v47,
          inserted);
        v26 = 231;
        v28 = -2147024882;
        goto LABEL_43;
      }
      v11 = JetMove(v4, tableid, 1, 0);
      CheckCorruption(v11);
      v9 = v43;
    }
    if ( v11 != -1603 )
    {
      v25 = MakeHresultFromJetError(v11);
      v26 = 237;
      goto LABEL_28;
    }
    v30 = auto_JET_TABLEID::close((auto_JET_TABLEID *)v44);
    if ( v30 < 0 )
    {
      v35 = MakeHresultFromJetError(v30);
      Log_UnistoreHREvent_0(
        v35,
        0,
        "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\jetinterop.h",
        261);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x180012628  mov     [rsp-8+arg_0], rbx
0x18001262d  push    rbp
0x18001262e  push    rsi
0x18001262f  push    rdi
0x180012630  push    r12
0x180012632  push    r13
0x180012634  push    r14
0x180012636  push    r15
0x180012638  lea     rbp, [rsp-0E0h]
0x180012640  sub     rsp, 1E0h
0x180012647  mov     rax, cs:__security_cookie
0x18001264e  xor     rax, rsp
0x180012651  mov     [rbp+110h+var_40], rax
0x180012658  mov     r15, r8
0x18001265b  mov     [rbp+110h+var_180], r8
0x18001265f  mov     edi, edx
0x180012661  lea     rcx, [rbp+110h+pvResult]; void *
0x180012665  mov     esi, 50h ; 'P'
0x18001266a  xor     edx, edx; Val
0x18001266c  mov     r8d, esi; Size
0x18001266f  mov     rbx, r9
0x180012672  call    memset_0
0x180012677  lea     r14d, [rsi-4Fh]
0x18001267b  xor     r8d, r8d; szColumnName
0x18001267e  mov     [rsp+210h+InfoLevel], r14d; InfoLevel
0x180012683  lea     r9, [rbp+110h+pvResult]; pvResult
0x180012687  mov     rdx, rbx; tableid
0x18001268a  mov     [rsp+210h+cbMax], esi; cbMax
0x18001268e  mov     rcx, r15; sesid
0x180012691  call    cs:__imp_JetGetTableColumnInfoA
0x180012697  mov     ecx, eax; int
0x180012699  mov     ebx, eax
0x18001269b  call    ?CheckCorruption@@YAXJ@Z; CheckCorruption(long)
0x1800126a0  test    ebx, ebx
0x1800126a2  js      loc_180012B57
0x1800126a8  mov     rax, [rbp+110h+tableid]
0x1800126ac  mov     ebx, edi
0x1800126ae  mov     [rbp+110h+var_188], rax
0x1800126b2  lea     rax, [rdi+rdi*4]
0x1800126b6  shl     rax, 3
0x1800126ba  lea     rdi, ?g_columnIdMapping@@3VColumnIdMappings@@A; ColumnIdMappings g_columnIdMapping
0x1800126c1  lea     rcx, [rdi+8]
0x1800126c5  mov     [rbp+110h+var_190], r15
0x1800126c9  add     rcx, rax
0x1800126cc  mov     [rbp+110h+var_178], rax
0x1800126d0  call    ?clear@?$_HashTable@KU?$pair@$$CBKUColumnDetails@@@utl@@UColumnIdHashTraits@ColumnIdMappings@@U?$equal_to@K@2@V?$allocator@U?$pair@$$CBKUColumnDetails@@@utl@@@2@$0A@@utl@@QEAAXXZ; utl::_HashTable<ulong,utl::pair<ulong const,ColumnDetails>,ColumnIdMappings::ColumnIdHashTraits,utl::equal_to<ulong>,utl::allocator<utl::pair<ulong const,ColumnDetails>>,0>::clear(void)
0x1800126d5  mov     rdx, [rbp+110h+tableid]; unsigned __int64
0x1800126d9  lea     rsi, [rbx+rbx*2]
0x1800126dd  shl     rsi, 3
0x1800126e1  mov     r8d, 80000000h; int
0x1800126e7  mov     [rsp+210h+var_198], rsi
0x1800126ec  lea     rcx, [rsi+rdi]
0x1800126f0  mov     rax, [rcx+878h]
0x1800126f7  mov     [rcx+880h], rax
0x1800126fe  mov     rcx, r15; unsigned __int64
0x180012701  call    ?CommsESE_JetMove@@YAJ_K0JK@Z; CommsESE_JetMove(unsigned __int64,unsigned __int64,long,ulong)
0x180012706  mov     ebx, eax
0x180012708  lea     rdi, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001270f  mov     r12d, 4
0x180012715  test    ebx, ebx
0x180012717  jnz     loc_1800129FB
0x18001271d  xor     edx, edx; Val
0x18001271f  lea     rcx, [rbp+110h+pretrievecolumn.pvData]; void *
0x180012723  mov     r8d, 0B8h; Size
0x180012729  call    memset_0
0x18001272e  mov     eax, [rbp+110h+var_144]
0x180012731  lea     r8, [rbp+110h+pretrievecolumn]; pretrievecolumn
0x180012735  mov     rdx, [rbp+110h+tableid]; tableid
0x180012739  mov     r9d, r12d; cretrievecolumn
0x18001273c  mov     [rbp+110h+pretrievecolumn.columnid], eax
0x18001273f  mov     rcx, r15; sesid
0x180012742  lea     rax, [rsp+210h+var_1E0]
0x180012747  mov     dword ptr [rsp+210h+var_1E0+4], ebx
0x18001274b  mov     [rbp+110h+pretrievecolumn.pvData], rax
0x18001274f  mov     eax, [rbp+110h+var_148]
0x180012752  mov     [rbp+110h+var_E0], eax
0x180012755  lea     rax, [rbp+110h+String]
0x18001275c  mov     [rbp+110h+var_D8], rax
0x180012760  mov     eax, [rbp+110h+var_128]
0x180012763  mov     [rbp+110h+var_B0], eax
0x180012766  lea     rax, [rsp+210h+var_1E0+4]
0x18001276b  mov     [rbp+110h+var_A8], rax
0x18001276f  mov     eax, [rbp+110h+var_12C]
0x180012772  mov     [rbp+110h+var_80], eax
0x180012778  lea     rax, [rsp+210h+var_1D8]
0x18001277d  mov     [rbp+110h+var_78], rax
0x180012784  mov     [rsp+210h+var_1D8], ebx
0x180012788  mov     dword ptr [rsp+210h+var_1E0], ebx
0x18001278c  mov     [rbp+110h+pretrievecolumn.cbData], r12d
0x180012790  mov     [rbp+110h+pretrievecolumn.itagSequence], r14d
0x180012794  mov     [rbp+110h+var_D0], 9
0x18001279b  mov     [rbp+110h+var_C0], r14d
0x18001279f  mov     [rbp+110h+var_A0], r12d
0x1800127a3  mov     [rbp+110h+var_90], r14d
0x1800127aa  mov     [rbp+110h+var_70], r12d
0x1800127b1  mov     [rbp+110h+var_60], r14d
0x1800127b8  call    cs:__imp_JetRetrieveColumns
0x1800127be  mov     ecx, eax; int
0x1800127c0  mov     ebx, eax
0x1800127c2  call    ?CheckCorruption@@YAXJ@Z; CheckCorruption(long)
0x1800127c7  test    ebx, ebx
0x1800127c9  js      loc_180012B11
0x1800127cf  mov     ecx, [rbp+110h+pretrievecolumn.err]; int
0x1800127d2  test    ecx, ecx
0x1800127d4  jnz     loc_1800129EE
0x1800127da  mov     ecx, [rbp+110h+var_B8]; int
0x1800127dd  test    ecx, ecx
0x1800127df  jnz     loc_1800129A0
0x1800127e5  mov     [rbp+110h+var_48], cl
0x1800127eb  lea     r8d, [r12+0Ch]; Radix
0x1800127f0  lea     rcx, [rbp+110h+String]; String
0x1800127f7  xor     edx, edx; EndPtr
0x1800127f9  call    cs:__imp_strtoul
0x1800127ff  mov     r12d, eax
0x180012802  test    eax, eax
0x180012804  jz      loc_180012AFF
0x18001280a  mov     eax, dword ptr [rsp+210h+var_1E0+4]
0x18001280e  mov     ecx, dword ptr [rsp+210h+var_1E0]
0x180012812  mov     r13d, ecx
0x180012815  mov     edx, [rsp+210h+var_1D8]
0x180012819  mov     dword ptr [rsp+210h+var_1C0+4], eax
0x18001281d  mov     dword ptr [rsp+210h+var_1D0+8], eax
0x180012821  lea     rax, ?g_columnIdMapping@@3VColumnIdMappings@@A; ColumnIdMappings g_columnIdMapping
0x180012828  add     rax, 878h
0x18001282e  mov     dword ptr [rsp+210h+var_1C0], ecx
0x180012832  add     rsi, rax
0x180012835  mov     [rsp+210h+var_1B8], edx
0x180012839  mov     dword ptr [rsp+210h+var_1D0], r12d
0x18001283e  mov     dword ptr [rsp+210h+var_1D0+4], ecx
0x180012842  mov     dword ptr [rsp+210h+var_1D0+0Ch], edx
0x180012846  mov     rbx, [rsi]
0x180012849  mov     r14, [rsi+8]
0x18001284d  sub     r14, rbx
0x180012850  sar     r14, 4
0x180012854  test    r14, r14
0x180012857  jle     short loc_180012893
0x180012859  mov     r15, r14
0x18001285c  lea     rdx, [rsp+210h+var_1D0]; struct PropIdAndColumnDetails *
0x180012861  shr     r15, 1
0x180012864  mov     r13, r15
0x180012867  shl     r13, 4
0x18001286b  add     r13, rbx
0x18001286e  mov     rcx, r13; struct PropIdAndColumnDetails *
0x180012871  call    ?CompareColumns@@YA_NAEBUPropIdAndColumnDetails@@0@Z; CompareColumns(PropIdAndColumnDetails const &,PropIdAndColumnDetails const &)
0x180012876  test    al, al
0x180012878  jnz     loc_180012971
0x18001287e  mov     r14, r15
0x180012881  test    r14, r14
0x180012884  jg      short loc_180012859
0x180012886  mov     ecx, dword ptr [rsp+210h+var_1E0]
0x18001288a  mov     r15, [rbp+110h+var_180]
0x18001288e  mov     r13d, dword ptr [rsp+210h+var_1C0]
0x180012893  cmp     rbx, [rsi+8]
0x180012897  jnz     loc_180012984
0x18001289d  mov     rax, [rsi+8]
0x1800128a1  cmp     rbx, rax
0x1800128a4  jnz     loc_180012A77
0x1800128aa  cmp     rax, [rsi+10h]
0x1800128ae  jnz     loc_180012A59
0x1800128b4  mov     rcx, rsi
0x1800128b7  call    ?_Grow@?$vector@UPropIdAndColumnDetails@@V?$allocator@UPropIdAndColumnDetails@@@utl@@@utl@@AEAA_NXZ; utl::vector<PropIdAndColumnDetails,utl::allocator<PropIdAndColumnDetails>>::_Grow(void)
0x1800128bc  test    al, al
0x1800128be  jnz     loc_180012A59
0x1800128c4  xor     r14d, r14d
0x1800128c7  test    r14, r14
0x1800128ca  jz      loc_180012A1C
0x1800128d0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800128d7  mov     ecx, 28h ; '('; unsigned __int64
0x1800128dc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800128e1  mov     rbx, rax
0x1800128e4  test    rax, rax
0x1800128e7  jz      short loc_18001293E
0x1800128e9  mov     rsi, [rbp+110h+var_178]
0x1800128ed  lea     rcx, ?g_columnIdMapping@@3VColumnIdMappings@@A; ColumnIdMappings g_columnIdMapping
0x1800128f4  mov     [rax+18h], r12d
0x1800128f8  lea     r8, [rbx+18h]
0x1800128fc  mov     [rax+1Ch], r13d
0x180012900  lea     rdx, [rsp+210h+var_1B0]
0x180012905  mov     eax, dword ptr [rsp+210h+var_1C0+4]
0x180012909  add     rsi, rcx
0x18001290c  mov     [rbx+20h], eax
0x18001290f  mov     eax, [rsp+210h+var_1B8]
0x180012913  mov     [rbx+24h], eax
0x180012916  lea     rcx, [rsi+8]
0x18001291a  call    ?_FindInsertPos@?$_HashTable@KU?$pair@$$CBKUColumnDetails@@@utl@@UColumnIdHashTraits@ColumnIdMappings@@U?$equal_to@K@2@V?$allocator@U?$pair@$$CBKUColumnDetails@@@utl@@@2@$0A@@utl@@AEAA?AU_InsertPosResult@12@AEBK@Z; utl::_HashTable<ulong,utl::pair<ulong const,ColumnDetails>,ColumnIdMappings::ColumnIdHashTraits,utl::equal_to<ulong>,utl::allocator<utl::pair<ulong const,ColumnDetails>>,0>::_FindInsertPos(ulong const &)
0x18001291f  cmp     byte ptr [rsp+210h+var_1A8+8], 0
0x180012924  jz      loc_180012AB4
0x18001292a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180012931  mov     rcx, rbx; Block
0x180012934  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012939  mov     rax, [rsp+210h+var_1B0]
0x18001293e  test    rax, rax
0x180012941  jz      loc_180012AD1
0x180012947  mov     rdx, [rbp+110h+tableid]; tableid
0x18001294b  xor     r9d, r9d; grbit
0x18001294e  mov     rcx, r15; sesid
0x180012951  lea     r14d, [r9+1]
0x180012955  mov     r8d, r14d; cRow
0x180012958  call    cs:__imp_JetMove
0x18001295e  mov     ecx, eax; int
0x180012960  mov     ebx, eax
0x180012962  call    ?CheckCorruption@@YAXJ@Z; CheckCorruption(long)
0x180012967  mov     rsi, [rsp+210h+var_198]
0x18001296c  jmp     loc_18001270F
0x180012971  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012975  lea     rbx, [r13+10h]
0x180012979  sub     rax, r15
0x18001297c  add     r14, rax
0x18001297f  jmp     loc_180012881
0x180012984  cmp     [rbx+4], ecx
0x180012987  jnz     loc_18001289D
0x18001298d  mov     r8d, 0DEh
0x180012993  mov     rdx, rdi
0x180012996  call    Log_AssertionEvent
0x18001299b  jmp     loc_18001289D
0x1800129a0  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800129a5  mov     r9d, 0C8h
0x1800129ab  mov     ecx, eax
0x1800129ad  mov     ebx, eax
0x1800129af  mov     r8, rdi
0x1800129b2  xor     edx, edx
0x1800129b4  call    Log_UnistoreHREvent_0
0x1800129b9  lea     rcx, [rbp+110h+var_190]; this
0x1800129bd  call    ??1auto_JET_TABLEID@@QEAA@XZ; auto_JET_TABLEID::~auto_JET_TABLEID(void)
0x1800129c2  mov     eax, ebx
0x1800129c4  mov     rcx, [rbp+110h+var_40]
0x1800129cb  xor     rcx, rsp; StackCookie
0x1800129ce  call    __security_check_cookie
0x1800129d3  mov     rbx, [rsp+210h+arg_0]
0x1800129db  add     rsp, 1E0h
0x1800129e2  pop     r15
0x1800129e4  pop     r14
0x1800129e6  pop     r13
0x1800129e8  pop     r12
0x1800129ea  pop     rdi
0x1800129eb  pop     rsi
0x1800129ec  pop     rbp
0x1800129ed  retn
0x1800129ee  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800129f3  mov     r9d, 0C6h
0x1800129f9  jmp     short loc_1800129AB
0x1800129fb  cmp     ebx, 0FFFFF9BDh
0x180012a01  jnz     loc_180012B23
0x180012a07  lea     rcx, [rbp+110h+var_190]; this
0x180012a0b  call    ?close@auto_JET_TABLEID@@QEAAJXZ; auto_JET_TABLEID::close(void)
0x180012a10  test    eax, eax
0x180012a12  js      loc_180012B35
0x180012a18  xor     eax, eax
0x180012a1a  jmp     short loc_1800129C4
0x180012a1c  mov     ebx, 8007000Eh
0x180012a21  mov     r9d, 0E1h
0x180012a27  mov     ecx, ebx
0x180012a29  mov     r8, rdi
0x180012a2c  xor     edx, edx
0x180012a2e  call    Log_UnistoreHREvent_0
0x180012a33  lea     rcx, [rbp+110h+var_190]; this
0x180012a37  call    ?close@auto_JET_TABLEID@@QEAAJXZ; auto_JET_TABLEID::close(void)
0x180012a3c  test    eax, eax
0x180012a3e  jns     short loc_1800129C2
0x180012a40  mov     ecx, eax; int
0x180012a42  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180012a47  mov     r9d, 105h
0x180012a4d  lea     r8, aOnecoreuapBase_50; "onecoreuap\\base\\AppModel\\UserDataAcc"...
0x180012a54  jmp     loc_180012B6D
0x180012a59  mov     rax, [rsi+8]
0x180012a5d  movups  xmm0, [rsp+210h+var_1D0]
0x180012a62  movdqu  xmmword ptr [rax], xmm0
0x180012a66  mov     r14, [rsi+8]
0x180012a6a  lea     rax, [r14+10h]
0x180012a6e  mov     [rsi+8], rax
0x180012a72  jmp     loc_1800128C7
0x180012a77  mov     eax, dword ptr [rsp+210h+var_1D0]
0x180012a7b  lea     r8, [rsp+210h+var_1A8]
0x180012a80  mov     dword ptr [rsp+210h+var_1A8], eax
0x180012a84  mov     rdx, rbx
0x180012a87  mov     eax, dword ptr [rsp+210h+var_1D0+4]
0x180012a8b  mov     rcx, rsi
0x180012a8e  mov     dword ptr [rsp+210h+var_1A8+4], eax
0x180012a92  mov     eax, dword ptr [rsp+210h+var_1D0+8]
0x180012a96  mov     dword ptr [rsp+210h+var_1A8+8], eax
0x180012a9a  mov     eax, dword ptr [rsp+210h+var_1D0+0Ch]
0x180012a9e  mov     dword ptr [rsp+210h+var_1A8+0Ch], eax
0x180012aa2  mov     [rsp+210h+var_1B0], rsi
0x180012aa7  call    ?_InsertOne@?$vector@UPropIdAndColumnDetails@@V?$allocator@UPropIdAndColumnDetails@@@utl@@@utl@@AEAAPEAUPropIdAndColumnDetails@@PEAU3@$$QEAU3@@Z; utl::vector<PropIdAndColumnDetails,utl::allocator<PropIdAndColumnDetails>>::_InsertOne(PropIdAndColumnDetails *,PropIdAndColumnDetails &&)
0x180012aac  mov     r14, rax
0x180012aaf  jmp     loc_1800128C7
0x180012ab4  mov     r9, rbx
0x180012ab7  lea     r8, [rsp+210h+var_1B0]
0x180012abc  lea     rdx, [rbp+110h+var_170]
0x180012ac0  lea     rcx, [rsi+8]
0x180012ac4  call    ?_InsertAt@?$_HashTable@KU?$pair@$$CBKV?$CComPtr@UISyncKnowledge@@@ATL@@@utl@@U?$hash@K@2@U?$equal_to@K@2@V?$allocator@U?$pair@$$CBKV?$CComPtr@UISyncKnowledge@@@ATL@@@utl@@@2@$0A@@utl@@AEAA?AV?$_DlistIt@U?$_HashNode@U?$pair@$$CBKV?$CComPtr@UISyncKnowledge@@@ATL@@@utl@@@utl@@U?$pair@$$CBKV?$CComPtr@UISyncKnowledge@@@ATL@@@2@@2@AEBU_InsertPosResult@12@PEAU?$_HashNode@U?$pair@$$CBKV?$CComPtr@UISyncKnowledge@@@ATL@@@utl@@@2@@Z; utl::_HashTable<ulong,utl::pair<ulong const,ATL::CComPtr<ISyncKnowledge>>,utl::hash<ulong>,utl::equal_to<ulong>,utl::allocator<utl::pair<ulong const,ATL::CComPtr<ISyncKnowledge>>>,0>::_InsertAt(utl::_HashTable<ulong,utl::pair<ulong const,ATL::CComPtr<ISyncKnowledge>>,utl::hash<ulong>,utl::equal_to<ulong>,utl::allocator<utl::pair<ulong const,ATL::CComPtr<ISyncKnowledge>>>,0>::_InsertPosResult const &,utl::_HashNode<utl::pair<ulong const,ATL::CComPtr<ISyncKnowledge>>> *)
0x180012ac9  mov     rax, [rax]
0x180012acc  jmp     loc_18001293E
0x180012ad1  mov     rax, [rsp+210h+var_198]
0x180012ad6  lea     rcx, ?g_columnIdMapping@@3VColumnIdMappings@@A; ColumnIdMappings g_columnIdMapping
0x180012add  add     rax, 878h
0x180012ae3  lea     rdx, [rbp+110h+var_170]
0x180012ae7  add     rcx, rax
0x180012aea  mov     r8, r14
0x180012aed  call    ?erase@?$vector@UPropIdAndColumnDetails@@V?$allocator@UPropIdAndColumnDetails@@@utl@@@utl@@QEAA?AV?$_ArrayIt@UPropIdAndColumnDetails@@@2@V?$_ArrayConstIt@UPropIdAndColumnDetails@@@2@@Z; utl::vector<PropIdAndColumnDetails,utl::allocator<PropIdAndColumnDetails>>::erase(utl::_ArrayConstIt<PropIdAndColumnDetails>)
  ... truncated ...
```
