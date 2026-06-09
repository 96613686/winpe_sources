# DBSession::_CreateTable(ulong,unsigned __int64 *)

- ea: `0x1800773ec`
- end: `0x180077887`
- name: `?_CreateTable@DBSession@@IEAAJKPEA_K@Z`
- size: `1179`
- prototype: `__int64 __fastcall(DBSession *__hidden this, unsigned int, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `21`
- tags: `file_ops, service_task`

## callers

- `0x1800ace68`
- `0x1800ad418`

## callees

- `0x180004464`
- `0x1800068f0`
- `0x18000f530`
- `0x180011ed0`
- `0x18001491c`
- `0x180056fd4`
- `0x18005775c`
- `0x1800582f4`
- `0x180070790`
- `0x1800737b4`
- `0x1800773ec`
- `0x180077890`
- `0x180078a34`
- `0x180078a8c`
- `0x1800974cc`
- `0x180097748`
- `0x180097acc`
- `0x1800ac7a8`
- `0x1800c50aa`
- `0x1800c50f0`
- `0x1800c5180`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077726`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077726`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18007771c`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18007771c`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x1800774dc`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x1800774dc`
- `ESENT!JetCreateTableColumnIndex3A` at `0x1800777b4`
- `ESENT!JetCreateTableColumnIndex3A` at `0x1800777b4`

## string_xrefs

- `0x1800774b9`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbsession.cpp`
- `0x180077741`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbsession.cpp`
- `0x180077847`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbsession.cpp`

## pseudocode

```c
__int64 __fastcall DBSession::_CreateTable(DBSession *this, unsigned int a2, unsigned __int64 *a3)
{
  __int64 v3; // rsi
  JET_COLUMNCREATE_A *v4; // rax
  JET_COLUMNCREATE_A *v5; // rdi
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 HresultFromJetError; // rbx
  __int64 v10; // rdx
  __int64 v11; // rcx
  unsigned int v12; // r12d
  __int64 v13; // r14
  unsigned __int64 v14; // r15
  char **v15; // r13
  unsigned __int64 v16; // rcx
  __int64 v17; // rcx
  int v18; // eax
  unsigned __int16 *v19; // rcx
  unsigned int v20; // r8d
  __int64 v21; // rdx
  __int64 v22; // rcx
  unsigned __int16 *v23; // rax
  unsigned int v24; // ebx
  unsigned int v25; // r15d
  LCID v26; // r15d
  unsigned int v27; // ebx
  unsigned int v28; // r12d
  int v29; // eax
  __int64 v30; // r8
  int v31; // r14d
  signed int LastError; // eax
  unsigned int v33; // eax
  JET_ERR v34; // ebx
  __int64 v36; // r8
  unsigned int v37; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v38; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v39; // [rsp+48h] [rbp-B8h] BYREF
  int v40; // [rsp+4Ch] [rbp-B4h] BYREF
  LCID SystemDefaultLCID; // [rsp+50h] [rbp-B0h]
  unsigned int v42; // [rsp+54h] [rbp-ACh]
  DBSession *v43; // [rsp+58h] [rbp-A8h]
  unsigned __int64 *v44; // [rsp+60h] [rbp-A0h]
  _QWORD v45[3]; // [rsp+68h] [rbp-98h] BYREF
  JET_TABLECREATE3_A ptablecreate; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v47[352]; // [rsp+100h] [rbp+0h] BYREF
  _OWORD v48[704]; // [rsp+C00h] [rbp+B00h] BYREF
  CHAR MultiByteStr[56]; // [rsp+3800h] [rbp+3700h] BYREF

  v43 = this;
  v42 = a2;
  v44 = a3;
  v3 = 12LL * a2;
  v4 = (JET_COLUMNCREATE_A *)operator new[](saturated_mul(*((unsigned __int16 *)&g_rgTableInfo + 4 * v3 + 6), 0x38u));
  v5 = v4;
  if ( v4 )
  {
    memset_0(v4, 0, 56LL * *((unsigned __int16 *)&g_rgTableInfo + 4 * v3 + 6));
    v40 = 0;
    utl::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>>>::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>>>(
      v45,
      v6,
      v7);
    if ( (unsigned __int8)utl::vector<utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>,utl::allocator<utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>>>::_Resize<,0>(
                            v45,
                            *((unsigned __int16 *)&g_rgTableInfo + 4 * v3 + 6)) )
    {
      SystemDefaultLCID = GetSystemDefaultLCID();
      v12 = 0;
      while ( v12 < *((unsigned __int16 *)&g_rgTableInfo + 4 * v3 + 6) )
      {
        v13 = v12;
        v14 = 16LL * v12;
        v15 = (char **)(v14 * 2 + v45[0]);
        v16 = v14 * 2 + v45[0];
        v5[v13].cbStruct = 56;
        if ( (unsigned __int64)utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::capacity(v16) < 9
          && !(unsigned __int8)utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Grow(v17, 9) )
        {
          v8 = 1141;
          goto LABEL_4;
        }
        v18 = ULongToHexString(v15, *(unsigned int *)&(&g_rgTableInfo)[v3 + 1][v14 + 2]);
        LODWORD(HresultFromJetError) = v18;
        v10 = 1;
        if ( v18 < 0 )
        {
          v8 = 1142;
          v11 = (unsigned int)v18;
          goto LABEL_5;
        }
        v5[v13].szColumnName = *v15;
        v19 = (&g_rgTableInfo)[v3 + 1];
        v38 = 0;
        v39 = 0;
        v20 = *(_DWORD *)&v19[v14 + 4];
        LODWORD(v19) = *(_DWORD *)&v19[v14 + 2];
        v37 = 0;
        CEPropIdToESEPropType((unsigned int)v19, 1, v20, &v38, &v39, &v37);
        v23 = (&g_rgTableInfo)[v3 + 1];
        v24 = v37;
        if ( (v23[v14 + 4] & 1) != 0 )
          v24 = v37 | 4;
        if ( (v23[v14 + 4] & 4) != 0 )
        {
          v5[v13].cbDefault = 4;
          v5[v13].pvDefault = &v40;
          v24 |= 0x800u;
        }
        v25 = v38;
        if ( !v38 )
          Log_AssertionEvent_3(v22, v21, 1170);
        ++v12;
        v5[v13].cbMax = v39;
        v5[v13].coltyp = v25;
        v5[v13].grbit = v24;
        v5[v13].cp = 1200;
      }
      `vector constructor iterator'(
        v48,
        0x160u,
        0x20u,
        (void *(*)(void *))DBSession::UnistoreJETIndexInfo::UnistoreJETIndexInfo);
      v26 = SystemDefaultLCID;
      v27 = 0;
      v28 = v42;
      while ( v27 < *((unsigned __int16 *)&g_rgTableInfo + 4 * v3 + 12) )
      {
        v29 = DBSession::_FillIndexInfo(&v47[11 * v27], v28, v27, v26, &v47[11 * v27], &v48[22 * v27]);
        v31 = v29;
        if ( v29 < 0 )
        {
          Log_HREventPersist((unsigned int)v29, 1, v30, 1190);
          `vector destructor iterator'(
            v48,
            0x160u,
            0x20u,
            (void (*)(void *))DBSession::UnistoreJETIndexInfo::~UnistoreJETIndexInfo);
          LODWORD(HresultFromJetError) = v31;
          goto LABEL_6;
        }
        ++v27;
      }
      if ( WideCharToMultiByte(0, 0x400u, (&g_rgTableInfo)[v3], -1, MultiByteStr, 50, 0, 0) )
      {
        *(_QWORD *)&ptablecreate.cbStruct = 120;
        memset_0(&ptablecreate.szTableName, 0, 0x70u);
        ptablecreate.ulPages = 1;
        ptablecreate.szTableName = MultiByteStr;
        ptablecreate.cColumns = *((unsigned __int16 *)&g_rgTableInfo + 4 * v3 + 6);
        ptablecreate.rgindexcreate = (JET_INDEXCREATE2_A *)v47;
        v33 = *((unsigned __int16 *)&g_rgTableInfo + 4 * v3 + 12);
        ptablecreate.rgcolumncreate = v5;
        ptablecreate.cIndexes = v33;
        v34 = JetCreateTableColumnIndex3A(*((_QWORD *)v43 + 27), *((_DWORD *)v43 + 56), &ptablecreate);
        CheckCorruption(v34);
        if ( v34 >= 0 )
        {
          *v44 = ptablecreate.tableid;
          `vector destructor iterator'(
            v48,
            0x160u,
            0x20u,
            (void (*)(void *))DBSession::UnistoreJETIndexInfo::~UnistoreJETIndexInfo);
          utl::vector<utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>,utl::allocator<utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>>>::_Uninit(v45);
          operator delete(v5);
          return 0;
        }
        HresultFromJetError = (unsigned int)MakeHresultFromJetError(v34);
        Log_HREventPersist(HresultFromJetError, 0, v36, 1212);
      }
      else
      {
        LastError = GetLastError();
        LODWORD(HresultFromJetError) = LastError;
        if ( LastError > 0 )
          LODWORD(HresultFromJetError) = (unsigned __int16)LastError | 0x80070000;
        Log_UnistoreHREvent_0(
          (unsigned int)HresultFromJetError,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbsession.cpp",
          1202);
      }
      `vector destructor iterator'(
        v48,
        0x160u,
        0x20u,
        (void (*)(void *))DBSession::UnistoreJETIndexInfo::~UnistoreJETIndexInfo);
    }
    else
    {
      v8 = 1133;
LABEL_4:
      LODWORD(HresultFromJetError) = -2147024882;
      v10 = 0;
      v11 = 2147942414LL;
LABEL_5:
      Log_UnistoreHREvent_0(
        v11,
        v10,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbsession.cpp",
        v8);
    }
LABEL_6:
    utl::vector<utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>,utl::allocator<utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>>>::_Uninit(v45);
    operator delete(v5);
  }
  else
  {
    LODWORD(HresultFromJetError) = -2147024882;
    Log_UnistoreHREvent_0(
      2147942414LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbsession.cpp",
      1124);
  }
  return (unsigned int)HresultFromJetError;
}

```

## disassembly

```asm
0x1800773ec  mov     [rsp-8+arg_18], rbx
0x1800773f1  push    rbp
0x1800773f2  push    rsi
0x1800773f3  push    rdi
0x1800773f4  push    r12
0x1800773f6  push    r13
0x1800773f8  push    r14
0x1800773fa  push    r15
0x1800773fc  lea     rbp, [rsp-3740h]
0x180077404  mov     eax, 3840h
0x180077409  call    _alloca_probe
0x18007740e  sub     rsp, rax
0x180077411  mov     rax, cs:__security_cookie
0x180077418  xor     rax, rsp
0x18007741b  mov     [rbp+3770h+var_38], rax
0x180077422  mov     r14d, edx
0x180077425  mov     eax, 38h ; '8'
0x18007742a  mov     [rsp+3870h+var_3818], rcx
0x18007742f  mov     [rsp+3870h+var_381C], r14d
0x180077434  mov     [rsp+3870h+var_3810], r8
0x180077439  lea     rsi, [r14+r14*2]
0x18007743d  shl     rsi, 5
0x180077441  lea     r14, ?g_rgTableInfo@@3QBUUSTableInfo@@B; USTableInfo const near * const g_rgTableInfo
0x180077448  movzx   ecx, word ptr [rsi+r14+0Ch]
0x18007744e  mul     rcx
0x180077451  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180077458  cmovb   rax, rcx
0x18007745c  mov     rcx, rax; unsigned __int64
0x18007745f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180077464  xor     edx, edx; Val
0x180077466  xor     r13d, r13d
0x180077469  mov     rdi, rax
0x18007746c  test    rax, rax
0x18007746f  jz      loc_180077842
0x180077475  movzx   ecx, word ptr [rsi+r14+0Ch]
0x18007747b  imul    r8, rcx, 38h ; '8'; Size
0x18007747f  mov     rcx, rax; void *
0x180077482  call    memset_0
0x180077487  lea     rcx, [rsp+3870h+var_3808]
0x18007748c  mov     [rsp+3870h+var_3824], r13d
0x180077491  call    ??0?$vector@V?$auto_xxx@PEAU_USPROPVAL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAU_USPROPVAL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>>>::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>>>(void)
0x180077496  movzx   edx, word ptr [rsi+r14+0Ch]
0x18007749c  lea     rcx, [rsp+3870h+var_3808]
0x1800774a1  call    ??$_Resize@$$V$0A@@?$vector@V?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@V?$allocator@V?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@@2@@utl@@AEAA_N_K@Z; utl::vector<utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>,utl::allocator<utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>>>::_Resize<,0>(unsigned __int64)
0x1800774a6  test    al, al
0x1800774a8  jnz     short loc_1800774DC
0x1800774aa  mov     r9d, 46Dh
0x1800774b0  mov     ebx, 8007000Eh
0x1800774b5  xor     edx, edx
0x1800774b7  mov     ecx, ebx
0x1800774b9  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800774c0  call    Log_UnistoreHREvent_0
0x1800774c5  lea     rcx, [rsp+3870h+var_3808]
0x1800774ca  call    ?_Uninit@?$vector@V?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@V?$allocator@V?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>,utl::allocator<utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>>>::_Uninit(void)
0x1800774cf  mov     rcx, rdi; Block
0x1800774d2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800774d7  jmp     loc_18007785B
0x1800774dc  call    cs:__imp_GetSystemDefaultLCID
0x1800774e2  mov     [rsp+3870h+var_3820], eax
0x1800774e6  mov     r12d, r13d
0x1800774e9  movzx   ecx, word ptr [rsi+r14+0Ch]
0x1800774ef  cmp     r12d, ecx
0x1800774f2  jnb     loc_180077635
0x1800774f8  mov     r13, [rsp+3870h+var_3808]
0x1800774fd  mov     r15d, r12d
0x180077500  imul    r14, r15, 38h ; '8'
0x180077504  shl     r15, 5
0x180077508  add     r13, r15
0x18007750b  mov     rcx, r13
0x18007750e  mov     dword ptr [r14+rdi], 38h ; '8'
0x180077516  call    ?capacity@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@QEBA_KXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::capacity(void)
0x18007751b  cmp     rax, 9
0x18007751f  jnb     short loc_180077533
0x180077521  mov     edx, 9
0x180077526  call    ?_Grow@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAA_N_K@Z; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Grow(unsigned __int64)
0x18007752b  test    al, al
0x18007752d  jz      loc_18007761D
0x180077533  lea     rdx, ?g_rgTableInfo@@3QBUUSTableInfo@@B; USTableInfo const near * const g_rgTableInfo
0x18007753a  mov     rcx, r13
0x18007753d  mov     rdx, [rsi+rdx+10h]
0x180077542  mov     edx, [r15+rdx+4]
0x180077547  call    ?ULongToHexString@@YAJAEAV?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@K@Z; ULongToHexString(utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>> &,ulong)
0x18007754c  mov     ebx, eax
0x18007754e  mov     edx, 1; int
0x180077553  test    eax, eax
0x180077555  js      loc_180077628
0x18007755b  mov     rax, [r13+0]
0x18007755f  lea     rbx, ?g_rgTableInfo@@3QBUUSTableInfo@@B; USTableInfo const near * const g_rgTableInfo
0x180077566  mov     [r14+rdi+8], rax
0x18007756b  lea     r9, [rsp+3870h+var_382C]; unsigned int *
0x180077570  mov     rcx, [rsi+rbx+10h]
0x180077575  lea     rax, [rsp+3870h+var_3830]
0x18007757a  mov     qword ptr [rsp+3870h+cbMultiByte], rax; unsigned int *
0x18007757f  xor     r13d, r13d
0x180077582  lea     rax, [rsp+3870h+var_3828]
0x180077587  mov     [rsp+3870h+var_382C], r13d
0x18007758c  mov     [rsp+3870h+var_3828], r13d
0x180077591  mov     r8d, [r15+rcx+8]; unsigned int
0x180077596  mov     ecx, [r15+rcx+4]; unsigned int
0x18007759b  mov     [rsp+3870h+var_3830], r13d
0x1800775a0  mov     [rsp+3870h+lpMultiByteStr], rax; unsigned int *
0x1800775a5  call    ?CEPropIdToESEPropType@@YAXKHKAEAK00@Z; CEPropIdToESEPropType(ulong,int,ulong,ulong &,ulong &,ulong &)
0x1800775aa  mov     rax, [rsi+rbx+10h]
0x1800775af  mov     ebx, [rsp+3870h+var_3830]
0x1800775b3  test    byte ptr [r15+rax+8], 1
0x1800775b9  jz      short loc_1800775BE
0x1800775bb  or      ebx, 4
0x1800775be  test    byte ptr [r15+rax+8], 4
0x1800775c4  jz      short loc_1800775DD
0x1800775c6  lea     rax, [rsp+3870h+var_3824]
0x1800775cb  mov     dword ptr [r14+rdi+28h], 4
0x1800775d4  mov     [r14+rdi+20h], rax
0x1800775d9  bts     ebx, 0Bh
0x1800775dd  mov     r15d, [rsp+3870h+var_382C]
0x1800775e2  test    r15d, r15d
0x1800775e5  jnz     short loc_1800775F2
0x1800775e7  mov     r8d, 492h
0x1800775ed  call    Log_AssertionEvent_3
0x1800775f2  mov     eax, [rsp+3870h+var_3828]
0x1800775f6  inc     r12d
0x1800775f9  mov     [r14+rdi+14h], eax
0x1800775fe  mov     [r14+rdi+10h], r15d
0x180077603  mov     [r14+rdi+18h], ebx
0x180077608  mov     dword ptr [r14+rdi+2Ch], 4B0h
0x180077611  lea     r14, ?g_rgTableInfo@@3QBUUSTableInfo@@B; USTableInfo const near * const g_rgTableInfo
0x180077618  jmp     loc_1800774E9
0x18007761d  mov     r9d, 475h
0x180077623  jmp     loc_1800774B0
0x180077628  mov     r9d, 476h
0x18007762e  mov     ecx, eax
0x180077630  jmp     loc_1800774B9
0x180077635  lea     r9, ??0UnistoreJETIndexInfo@DBSession@@QEAA@XZ; void *(*)(void *)
0x18007763c  mov     edx, 160h; unsigned __int64
0x180077641  mov     r8d, 20h ; ' '; unsigned __int64
0x180077647  lea     rcx, [rbp+3770h+var_2C70]; void *
0x18007764e  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x180077653  mov     r15d, [rsp+3870h+var_3820]
0x180077658  mov     ebx, r13d
0x18007765b  mov     r12d, [rsp+3870h+var_381C]
0x180077660  movzx   eax, word ptr [rsi+r14+18h]
0x180077666  cmp     ebx, eax
0x180077668  jnb     loc_1800776EF
0x18007766e  mov     ecx, ebx
0x180077670  lea     rdx, [rbp+3770h+var_2C70]
0x180077677  imul    rax, rcx, 160h
0x18007767e  mov     r9d, r15d
0x180077681  mov     r8d, ebx
0x180077684  add     rdx, rax
0x180077687  imul    rax, rcx, 58h ; 'X'
0x18007768b  mov     qword ptr [rsp+3870h+cbMultiByte], rdx
0x180077690  lea     rcx, [rbp+3770h+var_3770]
0x180077694  add     rcx, rax
0x180077697  mov     edx, r12d
0x18007769a  mov     [rsp+3870h+lpMultiByteStr], rcx
0x18007769f  call    ?_FillIndexInfo@DBSession@@AEAAJW4US_TABLEID@@KKPEAUtagJET_INDEXCREATE2_A@@PEAUUnistoreJETIndexInfo@1@@Z; DBSession::_FillIndexInfo(US_TABLEID,ulong,ulong,tagJET_INDEXCREATE2_A *,DBSession::UnistoreJETIndexInfo *)
0x1800776a4  mov     r14d, eax
0x1800776a7  test    eax, eax
0x1800776a9  js      short loc_1800776B6
0x1800776ab  inc     ebx
0x1800776ad  lea     r14, ?g_rgTableInfo@@3QBUUSTableInfo@@B; USTableInfo const near * const g_rgTableInfo
0x1800776b4  jmp     short loc_180077660
0x1800776b6  mov     edx, 1
0x1800776bb  mov     r9d, 4A6h
0x1800776c1  mov     ecx, r14d
0x1800776c4  call    Log_HREventPersist
0x1800776c9  lea     r9, ??1UnistoreJETIndexInfo@DBSession@@QEAA@XZ; void (*)(void *)
0x1800776d0  mov     edx, 160h; unsigned __int64
0x1800776d5  mov     r8d, 20h ; ' '; unsigned __int64
0x1800776db  lea     rcx, [rbp+3770h+var_2C70]; void *
0x1800776e2  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800776e7  mov     ebx, r14d
0x1800776ea  jmp     loc_1800774C5
0x1800776ef  mov     r8, [rsi+r14]; lpWideCharStr
0x1800776f3  lea     rax, [rbp+3770h+MultiByteStr]
0x1800776fa  mov     [rsp+3870h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x1800776ff  or      r9d, 0FFFFFFFFh; cchWideChar
0x180077703  mov     [rsp+3870h+lpDefaultChar], r13; lpDefaultChar
0x180077708  mov     edx, 400h; dwFlags
0x18007770d  mov     [rsp+3870h+cbMultiByte], 32h ; '2'; cbMultiByte
0x180077715  xor     ecx, ecx; CodePage
0x180077717  mov     [rsp+3870h+lpMultiByteStr], rax; lpMultiByteStr
0x18007771c  call    cs:__imp_WideCharToMultiByte
0x180077722  test    eax, eax
0x180077724  jnz     short loc_180077756
0x180077726  call    cs:__imp_GetLastError
0x18007772c  mov     ebx, eax
0x18007772e  test    eax, eax
0x180077730  jle     short loc_18007773B
0x180077732  movzx   ebx, ax
0x180077735  or      ebx, 80070000h
0x18007773b  mov     r9d, 4B2h
0x180077741  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180077748  xor     edx, edx
0x18007774a  mov     ecx, ebx
0x18007774c  call    Log_UnistoreHREvent_0
0x180077751  jmp     loc_18007781F
0x180077756  xor     edx, edx; Val
0x180077758  mov     qword ptr [rbp+3770h+ptablecreate.cbStruct], 78h ; 'x'
0x180077760  lea     rcx, [rbp+3770h+ptablecreate.szTableName]; void *
0x180077764  lea     r8d, [rdx+70h]; Size
0x180077768  call    memset_0
0x18007776d  lea     rax, [rbp+3770h+MultiByteStr]
0x180077774  mov     [rbp+3770h+ptablecreate.ulPages], 1
0x18007777b  mov     [rbp+3770h+ptablecreate.szTableName], rax
0x18007777f  lea     r8, [rbp+3770h+ptablecreate]; ptablecreate
0x180077783  movzx   eax, word ptr [rsi+r14+0Ch]
0x180077789  mov     [rbp+3770h+ptablecreate.cColumns], eax
0x18007778c  lea     rax, [rbp+3770h+var_3770]
0x180077790  mov     [rbp+3770h+ptablecreate.rgindexcreate], rax
0x180077794  movzx   eax, word ptr [rsi+r14+18h]
0x18007779a  mov     r14, [rsp+3870h+var_3818]
0x18007779f  mov     [rbp+3770h+ptablecreate.rgcolumncreate], rdi
0x1800777a3  mov     [rbp+3770h+ptablecreate.cIndexes], eax
0x1800777a6  mov     edx, [r14+0E0h]; dbid
0x1800777ad  mov     rcx, [r14+0D8h]; sesid
0x1800777b4  call    cs:__imp_JetCreateTableColumnIndex3A
0x1800777ba  mov     ecx, eax; int
0x1800777bc  mov     ebx, eax
0x1800777be  call    ?CheckCorruption@@YAXJ@Z; CheckCorruption(long)
0x1800777c3  test    ebx, ebx
0x1800777c5  js      short loc_180077807
0x1800777c7  mov     rcx, [rsp+3870h+var_3810]
0x1800777cc  lea     r9, ??1UnistoreJETIndexInfo@DBSession@@QEAA@XZ; void (*)(void *)
0x1800777d3  mov     rax, [rbp+3770h+ptablecreate.tableid]
0x1800777d7  mov     edx, 160h; unsigned __int64
0x1800777dc  mov     r8d, 20h ; ' '; unsigned __int64
0x1800777e2  mov     [rcx], rax
0x1800777e5  lea     rcx, [rbp+3770h+var_2C70]; void *
0x1800777ec  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800777f1  lea     rcx, [rsp+3870h+var_3808]
0x1800777f6  call    ?_Uninit@?$vector@V?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@V?$allocator@V?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>,utl::allocator<utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>>>::_Uninit(void)
0x1800777fb  mov     rcx, rdi; Block
0x1800777fe  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180077803  xor     eax, eax
0x180077805  jmp     short loc_18007785D
0x180077807  mov     ecx, ebx; int
0x180077809  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x18007780e  xor     edx, edx
0x180077810  mov     r9d, 4BCh
0x180077816  mov     ecx, eax
0x180077818  mov     ebx, eax
0x18007781a  call    Log_HREventPersist
0x18007781f  lea     r9, ??1UnistoreJETIndexInfo@DBSession@@QEAA@XZ; void (*)(void *)
0x180077826  mov     r8d, 20h ; ' '; unsigned __int64
0x18007782c  mov     edx, 160h; unsigned __int64
0x180077831  lea     rcx, [rbp+3770h+var_2C70]; void *
0x180077838  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18007783d  jmp     loc_1800774C5
0x180077842  mov     ebx, 8007000Eh
0x180077847  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18007784e  mov     ecx, ebx
0x180077850  mov     r9d, 464h
0x180077856  call    Log_UnistoreHREvent_0
0x18007785b  mov     eax, ebx
0x18007785d  mov     rcx, [rbp+3770h+var_38]
0x180077864  xor     rcx, rsp; StackCookie
0x180077867  call    __security_check_cookie
0x18007786c  mov     rbx, [rsp+3870h+arg_18]
0x180077874  add     rsp, 3840h
0x18007787b  pop     r15
0x18007787d  pop     r14
0x18007787f  pop     r13
0x180077881  pop     r12
0x180077883  pop     rdi
0x180077884  pop     rsi
0x180077885  pop     rbp
0x180077886  retn
```
