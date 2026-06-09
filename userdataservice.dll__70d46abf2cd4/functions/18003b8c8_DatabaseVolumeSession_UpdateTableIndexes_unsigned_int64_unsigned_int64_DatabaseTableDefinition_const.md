# DatabaseVolumeSession::_UpdateTableIndexes(unsigned __int64,unsigned __int64,DatabaseTableDefinition const *)

- ea: `0x18003b8c8`
- end: `0x18003befc`
- name: `?_UpdateTableIndexes@DatabaseVolumeSession@@IEAAJ_K0PEBUDatabaseTableDefinition@@@Z`
- size: `1588`
- prototype: `int(DatabaseVolumeSession *__hidden this, unsigned __int64, unsigned __int64, const struct DatabaseTableDefinition *)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, service_task, installer_update`

## callers

- `0x18003c364`

## callees

- `0x1800049f0`
- `0x180008f0c`
- `0x18000e1f8`
- `0x180018c20`
- `0x18003b108`
- `0x18003b8c8`
- `0x18003bf04`
- `0x18003bf3c`
- `0x18003bf84`
- `0x18003bff8`
- `0x18003c09c`
- `0x180075f98`
- `0x180076664`
- `0x1800781d8`
- `0x1800977ac`
- `0x1800977b8`
- `0x180097fc8`
- `0x18009e334`
- `0x1800a4e74`
- `0x1800a51e8`
- `0x18012c746`
- `0x18012c76a`
- `0x18012c7b0`

## import_xrefs

- `ESENT!JetGetTableIndexInfoA` at `0x18003b939`
- `ESENT!JetGetTableIndexInfoA` at `0x18003bab1`
- `ESENT!JetGetTableIndexInfoA` at `0x18003b939`
- `ESENT!JetGetTableIndexInfoA` at `0x18003bab1`
- `ESENT!JetDeleteIndexA` at `0x18003bdc5`
- `ESENT!JetDeleteIndexA` at `0x18003bdc5`
- `ESENT!JetMove` at `0x18003b98f`
- `ESENT!JetMove` at `0x18003ba70`
- `ESENT!JetMove` at `0x18003bc0f`
- `ESENT!JetMove` at `0x18003b98f`
- `ESENT!JetMove` at `0x18003ba70`
- `ESENT!JetMove` at `0x18003bc0f`
- `ESENT!JetRetrieveColumns` at `0x18003b9ff`
- `ESENT!JetRetrieveColumns` at `0x18003b9ff`

## string_xrefs

- `0x18003b995`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x18003be8f`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x18003bebe`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x18003bd7d`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\jetinterop.h`
- `0x18003be72`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\jetinterop.h`

## pseudocode

```c
__int64 __fastcall DatabaseVolumeSession::_UpdateTableIndexes(
        DatabaseVolumeSession *this,
        JET_SESID a2,
        JET_TABLEID a3,
        const struct DatabaseTableDefinition *a4)
{
  const struct DatabaseTableDefinition *v5; // rbx
  JET_TABLEID v6; // r12
  JET_ERR TableIndexInfoA; // eax
  struct tagJET_INDEXCREATE_A *v8; // rdi
  JET_ERR v9; // eax
  int v10; // ecx
  JET_ERR v11; // eax
  __int64 v12; // rcx
  JET_ERR v13; // eax
  JET_ERR v14; // eax
  int v15; // r15d
  __int64 i; // r14
  size_t cbKey; // r8
  __int64 v18; // r12
  DatabaseVolumeSession *v19; // rcx
  char *v20; // rdx
  size_t v21; // r8
  int *v22; // rax
  unsigned int HresultFromJetError; // ebx
  __int64 v24; // r9
  __int64 v25; // rdx
  __int64 v26; // r9
  int v27; // eax
  __int64 v28; // rcx
  __int64 v29; // r14
  void *v30; // rcx
  void *v31; // rbx
  int v32; // eax
  unsigned int v33; // eax
  __int64 v35; // r15
  unsigned int v36; // ebx
  JET_PCSTR *v37; // r14
  JET_ERR v38; // eax
  void *v39; // rcx
  int v40; // eax
  unsigned int v41; // eax
  unsigned int v42; // [rsp+30h] [rbp-D0h] BYREF
  int v43; // [rsp+34h] [rbp-CCh] BYREF
  void *Block; // [rsp+38h] [rbp-C8h] BYREF
  int *v45; // [rsp+40h] [rbp-C0h]
  int *v46; // [rsp+48h] [rbp-B8h]
  void *v47; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v48; // [rsp+58h] [rbp-A8h]
  const struct DatabaseTableDefinition *v49; // [rsp+68h] [rbp-98h]
  _QWORD v50[2]; // [rsp+70h] [rbp-90h] BYREF
  JET_TABLEID v51; // [rsp+80h] [rbp-80h]
  _BYTE v52[40]; // [rsp+88h] [rbp-78h] BYREF
  JET_RETRIEVECOLUMN pretrievecolumn; // [rsp+B0h] [rbp-50h] BYREF
  int v54; // [rsp+E0h] [rbp-20h]
  unsigned int *v55; // [rsp+E8h] [rbp-18h]
  int v56; // [rsp+F0h] [rbp-10h]
  int v57; // [rsp+100h] [rbp+0h]
  int v58; // [rsp+108h] [rbp+8h]
  char pvResult[8]; // [rsp+110h] [rbp+10h] BYREF
  JET_TABLEID tableid; // [rsp+118h] [rbp+18h]
  JET_COLUMNID v61; // [rsp+124h] [rbp+24h]
  int v62; // [rsp+138h] [rbp+38h]
  char szIndexName[272]; // [rsp+170h] [rbp+70h] BYREF

  v51 = a3;
  v5 = a4;
  v6 = a3;
  v49 = a4;
  memset_0(pvResult, 0, 0x58u);
  TableIndexInfoA = JetGetTableIndexInfoA(a2, v6, 0, pvResult, 0x58u, 1u);
  if ( TableIndexInfoA < 0 )
  {
    HresultFromJetError = MakeHresultFromJetError(TableIndexInfoA);
    Log_HREvent(
      HresultFromJetError,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      476);
    return HresultFromJetError;
  }
  v50[1] = tableid;
  v50[0] = a2;
  v8 = (struct tagJET_INDEXCREATE_A *)operator new[](0xA5Eu);
  if ( !v8 )
  {
    HresultFromJetError = -2147024882;
    Log_HREvent(
      2147942414LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      491);
    goto LABEL_79;
  }
  utl::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>(&v47);
  utl::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>(&Block);
  v9 = JetMove(a2, tableid, 0x80000000, 0);
  while ( 2 )
  {
    if ( v9 )
    {
      v35 = v48;
      v36 = 0;
      v37 = (JET_PCSTR *)v47;
      while ( v36 < (unsigned __int64)((v35 - (__int64)v37) >> 5) )
      {
        v38 = JetDeleteIndexA(a2, v6, v37[4 * v36]);
        if ( v38 < 0 )
        {
          v27 = MakeHresultFromJetError(v38);
          v24 = 570;
          goto LABEL_53;
        }
        ++v36;
      }
      v27 = DatabaseVolumeSession::_AddMissingIndexes(v10, a2, v6, (_DWORD)v49, (__int64)&Block);
      HresultFromJetError = v27;
      if ( v27 < 0 )
      {
        v24 = 574;
        v25 = 1;
        goto LABEL_54;
      }
      v39 = Block;
      if ( Block != (void *)-1LL )
        operator delete(Block);
      if ( v37 != (JET_PCSTR *)-1LL )
      {
        utl::_RangeDestroyApc<utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>(
          v39,
          v37,
          (v35 - (__int64)v37) >> 5);
        operator delete(v37);
      }
      operator delete(v8);
      v40 = auto_JET_TABLEID::close((auto_JET_TABLEID *)v50);
      if ( v40 < 0 )
      {
        v41 = MakeHresultFromJetError(v40);
        Log_HREvent(v41, 0, "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\jetinterop.h", 261);
      }
      return 0;
    }
    else
    {
      memset_0(&pretrievecolumn.pvData, 0, 0x58u);
      pretrievecolumn.columnid = v61;
      pretrievecolumn.cbData = 260;
      pretrievecolumn.pvData = szIndexName;
      v54 = v62;
      v55 = &v42;
      pretrievecolumn.itagSequence = 1;
      v42 = 0;
      v56 = 4;
      v57 = 1;
      v11 = JetRetrieveColumns(a2, tableid, &pretrievecolumn, 2u);
      if ( v11 >= 0 )
      {
        if ( pretrievecolumn.err < 0 )
        {
          v27 = MakeHresultFromJetError(pretrievecolumn.err);
          v24 = 521;
        }
        else if ( v58 < 0 )
        {
          v27 = MakeHresultFromJetError(v58);
          v24 = 523;
        }
        else
        {
          if ( pretrievecolumn.cbActual >= 0x104 )
          {
            v24 = 526;
            HresultFromJetError = -2147467259;
LABEL_49:
            v25 = 0;
LABEL_50:
            v28 = HresultFromJetError;
            goto LABEL_55;
          }
          if ( pretrievecolumn.cbActual >= 0x104uLL )
            _report_rangecheckfailure();
          v12 = v42;
          szIndexName[pretrievecolumn.cbActual] = 0;
          if ( !(_DWORD)v12 )
          {
            Log_AssertionEvent_2(
              v12,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
              529);
            LODWORD(v12) = v42;
          }
          do
          {
            if ( (unsigned int)v12 <= 1 )
              break;
            v13 = JetMove(a2, tableid, 1, 0);
            LODWORD(v12) = --v42;
          }
          while ( !v13 );
          memset_0(v8, 0, 0xA5Eu);
          v14 = JetGetTableIndexInfoA(a2, v6, szIndexName, v8, 0xA5Eu, 0xBu);
          if ( v14 >= 0 )
          {
            v15 = -1;
            v43 = -1;
            for ( i = 0; ; i = (unsigned int)(i + 1) )
            {
              if ( (unsigned int)i >= *((_DWORD *)v5 + 10) )
                goto LABEL_28;
              cbKey = v8->cbKey;
              v18 = *((_QWORD *)v49 + 4);
              if ( cbKey == *(_QWORD *)(v18 + 48 * i + 32) )
              {
                if ( !(_DWORD)cbKey || !v8->szKey || !*(_QWORD *)(v18 + 48 * i + 16) )
                {
                  HresultFromJetError = -2147467259;
                  Log_HREvent(
                    2147500037LL,
                    0,
                    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
                    617);
                  Log_HREvent(
                    2147500037LL,
                    1,
                    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
                    590);
                  v24 = 552;
                  v25 = 1;
                  goto LABEL_50;
                }
                if ( !memcmp_0(v8->szKey, *(const void **)(v18 + 48 * i + 16), cbKey) )
                {
                  v19 = (DatabaseVolumeSession *)(*(_DWORD *)(v18 + 48 * i + 24) & 0xFFFFF7FE | 1);
                  if ( (*(_BYTE *)(v18 + 48 * i + 24) & 2) == 0 )
                    v19 = (DatabaseVolumeSession *)(*(_DWORD *)(v18 + 48 * i + 24) & 0xFFFFF7FF);
                  if ( (v8->grbit & 0xFFFFF7FF) == (_DWORD)v19
                    && (unsigned int)DatabaseVolumeSession::_IsConditionalIndexMatch(
                                       v19,
                                       v8,
                                       *(const char *const **)(v18 + 48 * i + 40)) )
                  {
                    break;
                  }
                }
              }
              v5 = v49;
            }
            v5 = v49;
            v15 = i;
            v43 = i;
LABEL_28:
            if ( v15 == -1 )
            {
              utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::basic_string<char,utl::char_traits<char>,utl::allocator<char>>(v52);
              v20 = v8->szIndexName;
              if ( v20 )
              {
                v21 = -1;
                do
                  ++v21;
                while ( v20[v21] );
              }
              else
              {
                v21 = 0;
              }
              if ( (unsigned __int8)utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::assign(
                                      v52,
                                      v20,
                                      v21) )
              {
                if ( (unsigned __int8)utl::vector<utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>,utl::allocator<utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>>>::push_back(
                                        &v47,
                                        v52) )
                {
                  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v52);
LABEL_40:
                  v9 = JetMove(a2, tableid, 1, 0);
                  v6 = v51;
                  continue;
                }
                v26 = 559;
              }
              else
              {
                v26 = 558;
              }
              HresultFromJetError = -2147024882;
              Log_HREvent(
                2147942414LL,
                0,
                "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
                v26);
              utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v52);
              goto LABEL_56;
            }
            v22 = v45;
            if ( v45 != v46 )
            {
              *v45 = v15;
              v45 = v22 + 1;
              goto LABEL_40;
            }
            if ( (unsigned __int8)utl::vector<unsigned long,utl::allocator<unsigned long>>::_PushBackOne2<unsigned long const &>(
                                    &Block,
                                    &v43) )
              goto LABEL_40;
            v24 = 563;
            HresultFromJetError = -2147024882;
            goto LABEL_49;
          }
          v27 = MakeHresultFromJetError(v14);
          v24 = 549;
        }
LABEL_53:
        HresultFromJetError = v27;
        v25 = 0;
LABEL_54:
        v28 = (unsigned int)v27;
LABEL_55:
        Log_HREvent(
          v28,
          v25,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
          v24);
LABEL_56:
        utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(&Block);
        utl::vector<utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>,utl::allocator<utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>>>::_Uninit(&v47);
        operator delete(v8);
LABEL_79:
        auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)v50);
        return HresultFromJetError;
      }
      v29 = (unsigned int)MakeHresultFromJetError(v11);
      Log_HREvent(
        v29,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
        519);
      v30 = Block;
      if ( Block != (void *)-1LL )
        operator delete(Block);
      v31 = v47;
      if ( v47 != (void *)-1LL )
      {
        utl::_RangeDestroyApc<utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>(
          v30,
          v47,
          (v48 - (__int64)v47) >> 5);
        operator delete(v31);
      }
      operator delete(v8);
      v32 = auto_JET_TABLEID::close((auto_JET_TABLEID *)v50);
      if ( v32 < 0 )
      {
        v33 = MakeHresultFromJetError(v32);
        Log_HREvent(v33, 0, "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\jetinterop.h", 261);
      }
      return (unsigned int)v29;
    }
  }
}

```

## disassembly

```asm
0x18003b8c8  mov     [rsp-8+arg_0], rbx
0x18003b8cd  push    rbp
0x18003b8ce  push    rsi
0x18003b8cf  push    rdi
0x18003b8d0  push    r12
0x18003b8d2  push    r13
0x18003b8d4  push    r14
0x18003b8d6  push    r15
0x18003b8d8  lea     rbp, [rsp-190h]
0x18003b8e0  sub     rsp, 290h
0x18003b8e7  mov     rax, cs:__security_cookie
0x18003b8ee  xor     rax, rsp
0x18003b8f1  mov     [rbp+1C0h+var_40], rax
0x18003b8f8  mov     r13, rdx
0x18003b8fb  mov     [rbp+1C0h+var_240], r8
0x18003b8ff  xor     edx, edx; Val
0x18003b901  lea     rcx, [rbp+1C0h+pvResult]; void *
0x18003b905  mov     rbx, r9
0x18003b908  mov     r12, r8
0x18003b90b  mov     [rsp+2C0h+var_258], rbx
0x18003b910  lea     r8d, [rdx+58h]; Size
0x18003b914  call    memset_0
0x18003b919  mov     r14d, 1
0x18003b91f  lea     r9, [rbp+1C0h+pvResult]; pvResult
0x18003b923  mov     [rsp+2C0h+InfoLevel], r14d; InfoLevel
0x18003b928  xor     r8d, r8d; szIndexName
0x18003b92b  mov     rdx, r12; tableid
0x18003b92e  mov     [rsp+2C0h+cbResult], 58h ; 'X'; cbResult
0x18003b936  mov     rcx, r13; sesid
0x18003b939  call    cs:__imp_JetGetTableIndexInfoA
0x18003b93f  test    eax, eax
0x18003b941  js      loc_18003BEB1
0x18003b947  mov     rax, [rbp+1C0h+tableid]
0x18003b94b  mov     ecx, 0A5Eh; unsigned __int64
0x18003b950  mov     [rsp+2C0h+var_248], rax
0x18003b955  mov     [rsp+2C0h+var_250], r13
0x18003b95a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003b95f  mov     rdi, rax
0x18003b962  test    rax, rax
0x18003b965  jz      loc_18003BE8A
0x18003b96b  lea     rcx, [rsp+2C0h+var_270]
0x18003b970  call    ??0?$vector@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>(void)
0x18003b975  lea     rcx, [rsp+2C0h+Block]
0x18003b97a  call    ??0?$vector@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>(void)
0x18003b97f  mov     rdx, [rbp+1C0h+tableid]; tableid
0x18003b983  xor     r9d, r9d; grbit
0x18003b986  mov     r8d, 80000000h; cRow
0x18003b98c  mov     rcx, r13; sesid
0x18003b98f  call    cs:__imp_JetMove
0x18003b995  lea     rsi, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18003b99c  test    eax, eax
0x18003b99e  jnz     loc_18003BD99
0x18003b9a4  xor     edx, edx; Val
0x18003b9a6  lea     r8d, [rax+58h]; Size
0x18003b9aa  lea     rcx, [rbp+1C0h+pretrievecolumn.pvData]; void *
0x18003b9ae  call    memset_0
0x18003b9b3  mov     eax, [rbp+1C0h+var_19C]
0x18003b9b6  lea     r8, [rbp+1C0h+pretrievecolumn]; pretrievecolumn
0x18003b9ba  mov     rdx, [rbp+1C0h+tableid]; tableid
0x18003b9be  mov     r9d, 2; cretrievecolumn
0x18003b9c4  mov     [rbp+1C0h+pretrievecolumn.columnid], eax
0x18003b9c7  mov     rcx, r13; sesid
0x18003b9ca  lea     rax, [rbp+1C0h+szIndexName]
0x18003b9ce  mov     [rbp+1C0h+pretrievecolumn.cbData], 104h
0x18003b9d5  mov     [rbp+1C0h+pretrievecolumn.pvData], rax
0x18003b9d9  mov     eax, [rbp+1C0h+var_188]
0x18003b9dc  mov     [rbp+1C0h+var_1E0], eax
0x18003b9df  lea     rax, [rsp+2C0h+var_290]
0x18003b9e4  mov     [rbp+1C0h+var_1D8], rax
0x18003b9e8  mov     [rbp+1C0h+pretrievecolumn.itagSequence], r14d
0x18003b9ec  mov     [rsp+2C0h+var_290], 0
0x18003b9f4  mov     [rbp+1C0h+var_1D0], 4
0x18003b9fb  mov     [rbp+1C0h+var_1C0], r14d
0x18003b9ff  call    cs:__imp_JetRetrieveColumns
0x18003ba05  test    eax, eax
0x18003ba07  js      loc_18003BCFD
0x18003ba0d  mov     ecx, [rbp+1C0h+pretrievecolumn.err]; int
0x18003ba10  test    ecx, ecx
0x18003ba12  js      loc_18003BCC3
0x18003ba18  mov     ecx, [rbp+1C0h+var_1B8]; int
0x18003ba1b  test    ecx, ecx
0x18003ba1d  js      loc_18003BCB6
0x18003ba23  cmp     [rbp+1C0h+pretrievecolumn.cbActual], 104h
0x18003ba2a  jnb     loc_18003BCA5
0x18003ba30  mov     eax, [rbp+1C0h+pretrievecolumn.cbActual]
0x18003ba33  cmp     rax, 104h
0x18003ba39  jnb     loc_18003BC9F
0x18003ba3f  mov     ecx, [rsp+2C0h+var_290]
0x18003ba43  mov     [rbp+rax+1C0h+szIndexName], 0
0x18003ba48  test    ecx, ecx
0x18003ba4a  jnz     short loc_18003BA5E
0x18003ba4c  mov     r8d, 211h
0x18003ba52  mov     rdx, rsi
0x18003ba55  call    Log_AssertionEvent_2
0x18003ba5a  mov     ecx, [rsp+2C0h+var_290]
0x18003ba5e  cmp     ecx, r14d
0x18003ba61  jbe     short loc_18003BA84
0x18003ba63  mov     rdx, [rbp+1C0h+tableid]; tableid
0x18003ba67  xor     r9d, r9d; grbit
0x18003ba6a  mov     r8d, r14d; cRow
0x18003ba6d  mov     rcx, r13; sesid
0x18003ba70  call    cs:__imp_JetMove
0x18003ba76  mov     ecx, [rsp+2C0h+var_290]
0x18003ba7a  dec     ecx
0x18003ba7c  mov     [rsp+2C0h+var_290], ecx
0x18003ba80  test    eax, eax
0x18003ba82  jz      short loc_18003BA5E
0x18003ba84  xor     edx, edx; Val
0x18003ba86  mov     r8d, 0A5Eh; Size
0x18003ba8c  mov     rcx, rdi; void *
0x18003ba8f  call    memset_0
0x18003ba94  mov     r9, rdi; pvResult
0x18003ba97  mov     [rsp+2C0h+InfoLevel], 0Bh; InfoLevel
0x18003ba9f  lea     r8, [rbp+1C0h+szIndexName]; szIndexName
0x18003baa3  mov     [rsp+2C0h+cbResult], 0A5Eh; cbResult
0x18003baab  mov     rdx, r12; tableid
0x18003baae  mov     rcx, r13; sesid
0x18003bab1  call    cs:__imp_JetGetTableIndexInfoA
0x18003bab7  test    eax, eax
0x18003bab9  js      loc_18003BC90
0x18003babf  or      r15d, 0FFFFFFFFh
0x18003bac3  mov     [rsp+2C0h+var_28C], r15d
0x18003bac8  xor     r14d, r14d
0x18003bacb  cmp     r14d, [rbx+28h]
0x18003bacf  jnb     loc_18003BB70
0x18003bad5  mov     r9, [rsp+2C0h+var_258]
0x18003bada  lea     rbx, [r14+r14*2]
0x18003bade  mov     r8d, [rdi+18h]; Size
0x18003bae2  add     rbx, rbx
0x18003bae5  mov     r12, [r9+20h]
0x18003bae9  cmp     r8, [r12+rbx*8+20h]
0x18003baee  jnz     short loc_18003BB56
0x18003baf0  test    r8d, r8d
0x18003baf3  jz      loc_18003BC1E
0x18003baf9  cmp     qword ptr [rdi+10h], 0
0x18003bafe  jz      loc_18003BC1E
0x18003bb04  cmp     qword ptr [r12+rbx*8+10h], 0
0x18003bb0a  jz      loc_18003BC1E
0x18003bb10  mov     rdx, [r12+rbx*8+10h]; Buf2
0x18003bb15  mov     rcx, [rdi+10h]; Buf1
0x18003bb19  call    memcmp_0
0x18003bb1e  test    eax, eax
0x18003bb20  jnz     short loc_18003BB56
0x18003bb22  mov     edx, [r12+rbx*8+18h]
0x18003bb27  mov     r8d, 0FFFFF7FFh
0x18003bb2d  mov     eax, [rdi+1Ch]
0x18003bb30  and     edx, r8d
0x18003bb33  mov     ecx, edx
0x18003bb35  or      ecx, 1
0x18003bb38  test    dl, 2
0x18003bb3b  cmovz   ecx, edx; this
0x18003bb3e  and     eax, r8d
0x18003bb41  cmp     eax, ecx
0x18003bb43  jnz     short loc_18003BB56
0x18003bb45  mov     r8, [r12+rbx*8+28h]; char **
0x18003bb4a  mov     rdx, rdi; struct tagJET_INDEXCREATE_A *
0x18003bb4d  call    ?_IsConditionalIndexMatch@DatabaseVolumeSession@@IEAAHPEBUtagJET_INDEXCREATE_A@@PEBQEBD@Z; DatabaseVolumeSession::_IsConditionalIndexMatch(tagJET_INDEXCREATE_A const *,char const * const *)
0x18003bb52  test    eax, eax
0x18003bb54  jnz     short loc_18003BB63
0x18003bb56  mov     rbx, [rsp+2C0h+var_258]
0x18003bb5b  inc     r14d
0x18003bb5e  jmp     loc_18003BACB
0x18003bb63  mov     rbx, [rsp+2C0h+var_258]
0x18003bb68  mov     r15d, r14d
0x18003bb6b  mov     [rsp+2C0h+var_28C], r14d
0x18003bb70  cmp     r15d, 0FFFFFFFFh
0x18003bb74  jnz     short loc_18003BBCD
0x18003bb76  lea     rcx, [rbp+1C0h+var_238]
0x18003bb7a  call    ??0?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@QEAA@XZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::basic_string<char,utl::char_traits<char>,utl::allocator<char>>(void)
0x18003bb7f  mov     rdx, [rdi+8]; Src
0x18003bb83  test    rdx, rdx
0x18003bb86  jz      short loc_18003BB98
0x18003bb88  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003bb8c  inc     r8
0x18003bb8f  cmp     byte ptr [rdx+r8], 0
0x18003bb94  jnz     short loc_18003BB8C
0x18003bb96  jmp     short loc_18003BB9B
0x18003bb98  xor     r8d, r8d; Size
0x18003bb9b  lea     rcx, [rbp+1C0h+var_238]; void *
0x18003bb9f  call    ?assign@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@QEAA_NPEBD_K@Z; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::assign(char const *,unsigned __int64)
0x18003bba4  test    al, al
0x18003bba6  jz      loc_18003BC61
0x18003bbac  lea     rdx, [rbp+1C0h+var_238]
0x18003bbb0  lea     rcx, [rsp+2C0h+var_270]
0x18003bbb5  call    ?push_back@?$vector@V?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@V?$allocator@V?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@@2@@utl@@QEAA_N$$QEAV?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@2@@Z; utl::vector<utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>,utl::allocator<utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>>>::push_back(utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>> &&)
0x18003bbba  test    al, al
0x18003bbbc  jz      loc_18003BC59
0x18003bbc2  lea     rcx, [rbp+1C0h+var_238]; void *
0x18003bbc6  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18003bbcb  jmp     short loc_18003BBFE
0x18003bbcd  mov     rax, [rsp+2C0h+var_280]
0x18003bbd2  cmp     rax, [rsp+2C0h+var_278]
0x18003bbd7  jz      short loc_18003BBE7
0x18003bbd9  mov     [rax], r15d
0x18003bbdc  add     rax, 4
0x18003bbe0  mov     [rsp+2C0h+var_280], rax
0x18003bbe5  jmp     short loc_18003BBFE
0x18003bbe7  lea     rdx, [rsp+2C0h+var_28C]
0x18003bbec  lea     rcx, [rsp+2C0h+Block]
0x18003bbf1  call    ??$_PushBackOne2@AEBK@?$vector@KV?$allocator@K@utl@@@utl@@AEAA_NAEBK@Z; utl::vector<ulong,utl::allocator<ulong>>::_PushBackOne2<ulong const &>(ulong const &)
0x18003bbf6  test    al, al
0x18003bbf8  jz      loc_18003BC83
0x18003bbfe  mov     rdx, [rbp+1C0h+tableid]; tableid
0x18003bc02  xor     r9d, r9d; grbit
0x18003bc05  mov     rcx, r13; sesid
0x18003bc08  lea     r14d, [r9+1]
0x18003bc0c  mov     r8d, r14d; cRow
0x18003bc0f  call    cs:__imp_JetMove
0x18003bc15  mov     r12, [rbp+1C0h+var_240]
0x18003bc19  jmp     loc_18003B99C
0x18003bc1e  mov     ebx, 80004005h
0x18003bc23  mov     r9d, 269h
0x18003bc29  mov     ecx, ebx
0x18003bc2b  mov     r8, rsi
0x18003bc2e  xor     edx, edx
0x18003bc30  call    Log_HREvent
0x18003bc35  mov     r14d, 1
0x18003bc3b  mov     r9d, 24Eh
0x18003bc41  mov     edx, r14d
0x18003bc44  mov     r8, rsi
0x18003bc47  mov     ecx, ebx
0x18003bc49  call    Log_HREvent
0x18003bc4e  mov     r9d, 228h
0x18003bc54  mov     edx, r14d
0x18003bc57  jmp     short loc_18003BCB2
0x18003bc59  mov     r9d, 22Fh
0x18003bc5f  jmp     short loc_18003BC67
0x18003bc61  mov     r9d, 22Eh
0x18003bc67  mov     ebx, 8007000Eh
0x18003bc6c  mov     r8, rsi
0x18003bc6f  mov     ecx, ebx
0x18003bc71  xor     edx, edx
0x18003bc73  call    Log_HREvent
0x18003bc78  lea     rcx, [rbp+1C0h+var_238]; void *
0x18003bc7c  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18003bc81  jmp     short loc_18003BCDC
0x18003bc83  mov     r9d, 233h
0x18003bc89  mov     ebx, 8007000Eh
0x18003bc8e  jmp     short loc_18003BCB0
0x18003bc90  mov     ecx, eax; int
0x18003bc92  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x18003bc97  mov     r9d, 225h
0x18003bc9d  jmp     short loc_18003BCCE
0x18003bc9f  call    __report_rangecheckfailure
0x18003bca5  mov     r9d, 20Eh
0x18003bcab  mov     ebx, 80004005h
0x18003bcb0  xor     edx, edx
0x18003bcb2  mov     ecx, ebx
0x18003bcb4  jmp     short loc_18003BCD4
0x18003bcb6  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x18003bcbb  mov     r9d, 20Bh
0x18003bcc1  jmp     short loc_18003BCCE
0x18003bcc3  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x18003bcc8  mov     r9d, 209h
0x18003bcce  mov     ebx, eax
0x18003bcd0  xor     edx, edx
0x18003bcd2  mov     ecx, eax
0x18003bcd4  mov     r8, rsi
0x18003bcd7  call    Log_HREvent
0x18003bcdc  lea     rcx, [rsp+2C0h+Block]
0x18003bce1  call    ?_Uninit@?$vector@UUdmEmailParticipant@@V?$allocator@UUdmEmailParticipant@@@utl@@@utl@@AEAAXXZ; utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(void)
0x18003bce6  lea     rcx, [rsp+2C0h+var_270]
0x18003bceb  call    ?_Uninit@?$vector@V?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@V?$allocator@V?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>,utl::allocator<utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>>>::_Uninit(void)
0x18003bcf0  mov     rcx, rdi; Block
0x18003bcf3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003bcf8  jmp     loc_18003BEA5
0x18003bcfd  mov     ecx, eax; int
0x18003bcff  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x18003bd04  mov     r9d, 207h
0x18003bd0a  mov     r8, rsi
0x18003bd0d  xor     edx, edx
0x18003bd0f  mov     ecx, eax
0x18003bd11  mov     r14d, eax
0x18003bd14  call    Log_HREvent
0x18003bd19  mov     rcx, [rsp+2C0h+Block]; Block
0x18003bd1e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18003bd22  jz      short loc_18003BD30
0x18003bd24  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18003bd2b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003bd30  mov     rbx, [rsp+2C0h+var_270]
0x18003bd35  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18003bd39  jz      short loc_18003BD5E
0x18003bd3b  mov     r8, [rsp+2C0h+var_268]
0x18003bd40  mov     rdx, rbx
0x18003bd43  sub     r8, rbx
0x18003bd46  sar     r8, 5
0x18003bd4a  call    ??$_RangeDestroyApc@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@0@PEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>(utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>> &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,unsigned __int64)
0x18003bd4f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18003bd56  mov     rcx, rbx; Block
0x18003bd59  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003bd5e  mov     rcx, rdi; Block
0x18003bd61  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003bd66  lea     rcx, [rsp+2C0h+var_250]; this
0x18003bd6b  call    ?close@auto_JET_TABLEID@@QEAAJXZ; auto_JET_TABLEID::close(void)
0x18003bd70  test    eax, eax
0x18003bd72  jns     short loc_18003BD91
0x18003bd74  mov     ecx, eax; int
0x18003bd76  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x18003bd7b  mov     ecx, eax
0x18003bd7d  lea     r8, aOnecoreuapBase_94; "onecoreuap\\base\\AppModel\\UserDataAcc"...
  ... truncated ...
```
