# W3_STATIC_FILE_HANDLER::DoWork(IHttpContext *,STATIC_META_STORED_CONTEXT *,int,STRA *)

- ea: `0x180002dd8`
- end: `0x180003b4c`
- name: `?DoWork@W3_STATIC_FILE_HANDLER@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVSTATIC_META_STORED_CONTEXT@@HPEAVSTRA@@@Z`
- size: `3444`
- prototype: `__int64 __fastcall(__int64, struct IHttpContext *, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800028e0`

## callees

- `0x180001358`
- `0x180001d1c`
- `0x180002760`
- `0x180002d1c`
- `0x180002dd8`
- `0x180003d74`
- `0x180004118`
- `0x18000420c`
- `0x180004ed8`
- `0x1800055e8`
- `0x1800058d8`
- `0x1800067c6`
- `0x180006810`
- `0x180007010`

## import_xrefs

- `msvcrt!_wcsupr` at `0x1800031af`
- `msvcrt!_wcsupr` at `0x1800031af`
- `msvcrt!wcsrchr` at `0x180003058`
- `msvcrt!wcsrchr` at `0x180003058`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBGK@Z` at `0x180003a0a`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBGK@Z` at `0x180003a0a`
- `iisutil!?GetString@LANG_STRING@@QEAAJPEBDKIPEAPEBGPEAK@Z` at `0x1800039e3`
- `iisutil!?GetString@LANG_STRING@@QEAAJPEBDKIPEAPEBGPEAK@Z` at `0x1800039e3`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180003988`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180003988`
- `iisutil!?IsEmpty@STRA@@QEBA_NXZ` at `0x180003351`
- `iisutil!?IsEmpty@STRA@@QEBA_NXZ` at `0x1800033d6`
- `iisutil!?IsEmpty@STRA@@QEBA_NXZ` at `0x180003351`
- `iisutil!?IsEmpty@STRA@@QEBA_NXZ` at `0x1800033d6`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800031a6`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800031cb`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000387a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800031a6`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800031cb`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000387a`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x1800030ec`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x1800032ea`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x1800030ec`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x1800032ea`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180002e4c`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800032a6`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180002e4c`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800032a6`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800039f5`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180003a80`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180003b19`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800039f5`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180003a80`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180003b19`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800032d3`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180003377`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800033a3`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800033f7`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180003507`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180003634`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000379f`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180003a2a`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800032d3`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180003377`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800033a3`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800033f7`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180003507`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180003634`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000379f`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180003a2a`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180003384`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180003397`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180003407`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180003628`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180003782`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x1800037ad`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180003a39`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180003384`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180003397`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180003407`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180003628`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180003782`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x1800037ad`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180003a39`
- `iisutil!?EqualsNoCase@STRU@@QEBA_NPEBG@Z` at `0x1800030c1`
- `iisutil!?EqualsNoCase@STRU@@QEBA_NPEBG@Z` at `0x1800030c1`
- `iisutil!?QueryStr@STRA@@QEBAPEBDXZ` at `0x1800030df`
- `iisutil!?QueryStr@STRA@@QEBAPEBDXZ` at `0x1800030df`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000316a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800032ba`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000316a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800032ba`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000319b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003270`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000319b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003270`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000318b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800032ff`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000318b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800032ff`

## pseudocode

```c
__int64 __fastcall W3_STATIC_FILE_HANDLER::DoWork(__int64 a1, struct IHttpContext *a2, __int64 a3)
{
  __int64 v3; // rax
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rdi
  __int64 v9; // rax
  struct IHttpResponse *v10; // rsi
  struct IHttpFileInfo *v11; // r15
  __int64 v12; // rax
  const unsigned __int16 *v13; // rbx
  struct IHttpTraceContext *v14; // rax
  const struct _GUID *v15; // rdx
  __int64 v16; // rax
  const char *v17; // r8
  __int64 v18; // rdx
  __int64 v19; // r9
  struct IHttpResponse *v20; // rcx
  void (__fastcall *v21)(struct IHttpResponse *, __int64, const char *, __int64, int, _QWORD, _DWORD); // rax
  unsigned int v22; // r12d
  __int64 v23; // rax
  __int64 v24; // rax
  wchar_t *v25; // rax
  const unsigned __int16 *v26; // rcx
  __int64 (__fastcall ***v27)(_QWORD); // rax
  __int64 v28; // rax
  __int64 v29; // rbx
  int v30; // r12d
  const char *Str; // rax
  int String; // ebx
  MIME_MAP_TABLE *v33; // rcx
  const unsigned __int16 *v34; // rax
  wchar_t *v35; // rax
  const char *v36; // rbx
  const unsigned __int16 *v37; // rax
  unsigned int v38; // r9d
  META_SCRIPT_MAP_TABLE *v39; // rcx
  unsigned __int16 *v40; // rbx
  __int64 v41; // rax
  __int64 (__fastcall *v42)(unsigned __int16 *); // rbx
  unsigned __int16 *v43; // rdi
  __int64 v44; // rax
  int v45; // ecx
  int v46; // edx
  char *v47; // rdi
  const char *v48; // rax
  __int64 v49; // rdi
  STRA *v50; // rcx
  __int64 (__fastcall *v51)(struct IHttpResponse *, _QWORD, char *, _QWORD, _DWORD); // rdi
  unsigned __int16 CCH; // bx
  char *v53; // rax
  __int64 v54; // rbx
  __int64 v55; // rax
  const unsigned __int16 *v56; // rbx
  struct IHttpTraceContext *v57; // rax
  const struct _GUID *v58; // rdx
  __int64 v59; // rax
  const char *v60; // rax
  const char *v61; // rdi
  unsigned __int16 v62; // bx
  const char *v63; // rax
  __int64 v64; // rbx
  __int64 v65; // rbx
  __int64 v66; // rax
  __int64 (__fastcall *v67)(struct IHttpResponse *, __int64, char *, _QWORD, int); // rdi
  unsigned __int16 v68; // bx
  char *v69; // rax
  bool v70; // zf
  __int64 v71; // rax
  unsigned __int64 v72; // rbx
  const unsigned __int8 *v73; // rax
  int v74; // eax
  __int64 (__fastcall *v75)(struct IHttpFileInfo *); // rax
  __int64 v76; // rax
  __int64 v77; // rax
  void (__fastcall ***v78)(_QWORD, __int64, __int64); // rbx
  STRA *v79; // r13
  bool v80; // sf
  __int64 v81; // rax
  __int64 v82; // rax
  int (__fastcall *v83)(struct IHttpServer *, unsigned __int16 *, __int64, const unsigned __int16 *, _QWORD, _QWORD, int, __int64, __int64); // rdi
  __int64 v84; // rbx
  unsigned __int16 *v85; // rax
  _QWORD *v86; // r15
  __int64 v87; // rax
  __int64 v88; // rcx
  unsigned __int64 v89; // rbx
  const unsigned __int8 *v90; // rax
  int v91; // eax
  __int64 v92; // rax
  __int64 v93; // rax
  const char *v94; // rax
  __int64 (__fastcall ***v95)(_QWORD); // rax
  struct _HTTP_CACHE_POLICY *v96; // rax
  W3_STATIC_FILE_HANDLER *v97; // rcx
  int v99; // [rsp+20h] [rbp-E0h]
  struct MULTISZ *v100; // [rsp+28h] [rbp-D8h]
  int v101; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v102; // [rsp+54h] [rbp-ACh] BYREF
  unsigned __int16 v103[2]; // [rsp+58h] [rbp-A8h] BYREF
  int v104; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned __int64 v105; // [rsp+60h] [rbp-A0h] BYREF
  const unsigned __int16 *v106; // [rsp+68h] [rbp-98h] BYREF
  __int128 v107; // [rsp+70h] [rbp-90h] BYREF
  __int128 v108; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v109; // [rsp+90h] [rbp-70h]
  __int64 v110; // [rsp+98h] [rbp-68h]
  __int64 v111; // [rsp+A0h] [rbp-60h]
  __int64 v112; // [rsp+A8h] [rbp-58h]
  _BYTE v113[56]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v114[56]; // [rsp+E8h] [rbp-18h] BYREF
  char v115[32]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v116[128]; // [rsp+140h] [rbp+40h] BYREF

  v3 = *(_QWORD *)a2;
  v112 = a1;
  v6 = (*(__int64 (__fastcall **)(struct IHttpContext *))(v3 + 24))(a2);
  v7 = *(_QWORD *)a2;
  v8 = v6;
  v110 = v6;
  v9 = (*(__int64 (__fastcall **)(struct IHttpContext *))(v7 + 32))(a2);
  v104 = 0;
  v10 = (struct IHttpResponse *)v9;
  STRA::STRA((STRA *)v114, v115, 0x20u);
  v11 = (struct IHttpFileInfo *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 208LL))(a2);
  v12 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
  if ( (unsigned int)WWWServerTraceProvider::CheckTracingEnabled(v12, 0, 0) )
  {
    v13 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IHttpFileInfo *))(*(_QWORD *)v11 + 88LL))(v11);
    v14 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
    IISGeneralEvents::GENERAL_STATIC_FILE_HANDLER::RaiseEvent(v14, v15, v13);
  }
  if ( (*(_BYTE *)(a3 + 280) & 1) != 0 )
  {
    v22 = 2;
    if ( ((*(__int64 (__fastcall **)(struct IHttpFileInfo *))(*(_QWORD *)v11 + 56LL))(v11) & 2) != 0 )
    {
      v16 = (*(__int64 (__fastcall **)(struct IHttpResponse *))(*(_QWORD *)v10 + 8LL))(v10);
      v19 = 9;
      v17 = "Not Found";
      v99 = -2147024894;
      v18 = 404;
      goto LABEL_5;
    }
    if ( (unsigned int)(*(_DWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8) + 36) - 4) > 1 )
    {
      *(_WORD *)((*(__int64 (__fastcall **)(struct IHttpResponse *))(*(_QWORD *)v10 + 8LL))(v10) + 536) = 0;
      (*(void (__fastcall **)(struct IHttpResponse *, __int64, const char *, _QWORD, int, _QWORD, _DWORD))(*(_QWORD *)v10 + 24LL))(
        v10,
        405,
        "Method Not Allowed",
        0,
        -2147024895,
        0,
        0);
      v23 = (*(__int64 (__fastcall **)(struct IHttpResponse *))(*(_QWORD *)v10 + 8LL))(v10);
      *(_QWORD *)(v23 + 224) = "GET, HEAD, OPTIONS, TRACE";
      *(_WORD *)(v23 + 216) = 25;
      goto LABEL_85;
    }
    if ( (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 16LL))(v8, 26) )
    {
      v16 = (*(__int64 (__fastcall **)(struct IHttpResponse *))(*(_QWORD *)v10 + 8LL))(v10);
      v17 = "Expectation Failed";
      v19 = 0;
      v99 = 0;
      v18 = 417;
      goto LABEL_5;
    }
    v24 = *(_QWORD *)a2;
    v101 = 0;
    v109 = (unsigned __int16 *)(*(__int64 (__fastcall **)(struct IHttpContext *, _QWORD))(v24 + 184))(a2, 0);
    v25 = wcsrchr(v109, 0x2Eu);
    v26 = &::Str;
    if ( v25 )
      v26 = v25;
    v106 = v26;
    v27 = (__int64 (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 152LL))(a2);
    v111 = (**v27)(v27);
    v28 = (**(__int64 (__fastcall ***)(__int64, void *))v111)(v111, g_pStaticFileModuleContext);
    v29 = v28;
    if ( v28 && STRU::EqualsNoCase((STRU *)(v28 + 96), v106) )
    {
      v30 = *(_DWORD *)(v29 + 216);
      if ( v30 )
      {
        Str = STRA::QueryStr((STRA *)(v29 + 8));
        String = STRA::Copy((STRA *)v114, Str);
        if ( String < 0 )
          goto LABEL_87;
      }
    }
    else
    {
      v33 = *(MIME_MAP_TABLE **)(a3 + 256);
      v102 = 0;
      String = MIME_MAP_TABLE::SelectMimeMappingForFileExt(v33, v109, (struct STRA *)v114, &v104, (int *)&v102);
      if ( String < 0 )
        goto LABEL_88;
      v30 = v104;
      if ( !v104 || v102 )
      {
        memset_0(v116, 0, sizeof(v116));
        STRU::STRU((STRU *)v113, v116, 0x80u);
        v34 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IHttpContext *, _QWORD))(*(_QWORD *)a2 + 176LL))(
                                          a2,
                                          0);
        String = STRU::Copy((STRU *)v113, v34);
        if ( String < 0 )
        {
          STRU::~STRU((STRU *)v113);
          goto LABEL_87;
        }
        v35 = STRU::QueryStr((STRU *)v113);
        _wcsupr(v35);
        v36 = (const char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 64LL))(v8);
        v37 = STRU::QueryStr((STRU *)v113);
        v38 = *(_DWORD *)(a3 + 280);
        v39 = *(META_SCRIPT_MAP_TABLE **)(a3 + 272);
        v102 = 0;
        v109 = (unsigned __int16 *)META_SCRIPT_MAP_TABLE::CalculateScriptMapEntry(v39, v37, v36, v38, &v102, v100);
        v40 = v109;
        if ( !v109 )
          goto LABEL_30;
        v41 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 192LL))(a2);
        v42 = *(__int64 (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v40 + 80LL);
        v43 = (unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v41 + 80LL))(v41);
        v44 = v42(v109) - (_QWORD)v43;
        do
        {
          v45 = *(unsigned __int16 *)((char *)v43 + v44);
          v46 = *v43 - v45;
          if ( v46 )
            break;
          ++v43;
        }
        while ( v45 );
        if ( v46 )
        {
LABEL_30:
          v101 = 1;
          v30 = 0;
        }
        STRU::~STRU((STRU *)v113);
      }
      v47 = (char *)operator new(0xE0u);
      if ( !v47 )
      {
        String = -2147024882;
        goto LABEL_87;
      }
      *(_QWORD *)v47 = &STATIC_URI_STORED_CONTEXT::`vftable';
      STRA::STRA((STRA *)(v47 + 8), v47 + 64, 0x20u);
      STRU::STRU((STRU *)(v47 + 96), (unsigned __int16 *)v47 + 76, 0x20u);
      *((_DWORD *)v47 + 54) = 0;
      if ( v30 )
      {
        v48 = STRA::QueryStr((STRA *)v114);
        *((_DWORD *)v47 + 54) = 1;
        String = STRA::Copy((STRA *)(v47 + 8), v48);
        if ( String < 0 || (String = STRU::Copy((STRU *)(v47 + 96), v106), String < 0) )
        {
          (**(void (__fastcall ***)(void *))v47)(v47);
          goto LABEL_87;
        }
      }
      if ( (*(int (__fastcall **)(__int64, char *, void *))(*(_QWORD *)v111 + 8LL))(
             v111,
             v47,
             g_pStaticFileModuleContext) < 0 )
        (**(void (__fastcall ***)(void *))v47)(v47);
    }
    if ( !STRA::IsEmpty((STRA *)(a3 + 8)) )
    {
      v49 = (*(__int64 (__fastcall **)(struct IHttpResponse *))(*(_QWORD *)v10 + 8LL))(v10);
      v50 = (STRA *)(a3 + 8);
      if ( *(_QWORD *)(v49 + 64) )
      {
        v51 = *(__int64 (__fastcall **)(struct IHttpResponse *, _QWORD, char *, _QWORD, _DWORD))(*(_QWORD *)v10 + 32LL);
        CCH = STRA::QueryCCH(v50);
        v53 = STRA::QueryStr((STRA *)(a3 + 8));
        String = v51(v10, 0, v53, CCH, 0);
        if ( String < 0 )
          goto LABEL_87;
      }
      else
      {
        *(_QWORD *)(v49 + 64) = STRA::QueryStr(v50);
        *(_WORD *)(v49 + 56) = STRA::QueryCCH((STRA *)(a3 + 8));
      }
    }
    if ( !STRA::IsEmpty((STRA *)(a3 + 64)) )
    {
      v54 = (*(__int64 (__fastcall **)(struct IHttpResponse *))(*(_QWORD *)v10 + 8LL))(v10);
      *(_QWORD *)(v54 + 352) = STRA::QueryStr((STRA *)(a3 + 64));
      *(_WORD *)(v54 + 344) = STRA::QueryCCH((STRA *)(a3 + 64));
    }
    if ( !v30 )
    {
      v55 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
      if ( (unsigned int)WWWServerTraceProvider::CheckTracingEnabled(v55, 4, 3) )
      {
        v56 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IHttpFileInfo *))(*(_QWORD *)v11 + 88LL))(v11);
        v57 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
        IISSecurityEvents::SECURITY_DENIED_BY_MIMEMAP::RaiseEvent(v57, v58, v56);
      }
      v59 = (*(__int64 (__fastcall **)(struct IHttpResponse *))(*(_QWORD *)v10 + 8LL))(v10);
      v17 = "Not Found";
      v18 = 404;
      v20 = v10;
      v99 = -2147024846;
      *(_WORD *)(v59 + 536) = 0;
      v21 = *(void (__fastcall **)(struct IHttpResponse *, __int64, const char *, __int64, int, _QWORD, _DWORD))(*(_QWORD *)v10 + 24LL);
      if ( v101 )
        v19 = 17;
      else
        v19 = 3;
      goto LABEL_6;
    }
    v103[0] = 0;
    v60 = (const char *)(*(__int64 (__fastcall **)(__int64, __int64, unsigned __int16 *))(*(_QWORD *)v110 + 16LL))(
                          v110,
                          20,
                          v103);
    v61 = v60;
    if ( v60 && *v60 )
    {
      v101 = 0;
      v62 = v103[0];
      v63 = STRA::QueryStr((STRA *)v114);
      String = IsAcceptable(v63, v61, v62, &v101);
      if ( String < 0 )
        goto LABEL_87;
      if ( !v101 )
      {
        v16 = (*(__int64 (__fastcall **)(struct IHttpResponse *))(*(_QWORD *)v10 + 8LL))(v10);
        v17 = "Not Acceptable";
        v19 = 0;
        v99 = 0;
        v18 = 406;
        goto LABEL_5;
      }
    }
    if ( *(_DWORD *)(a3 + 284) )
    {
      v64 = (*(__int64 (__fastcall **)(struct IHttpResponse *))(*(_QWORD *)v10 + 8LL))(v10) + 408;
      *(_QWORD *)(v64 + 8) = (*(__int64 (__fastcall **)(struct IHttpFileInfo *, __int64))(*(_QWORD *)v11 + 96LL))(
                               v11,
                               v64);
    }
    v65 = (*(__int64 (__fastcall **)(struct IHttpResponse *))(*(_QWORD *)v10 + 8LL))(v10);
    *(_QWORD *)(v65 + 368) = (*(__int64 (__fastcall **)(struct IHttpFileInfo *))(*(_QWORD *)v11 + 112LL))(v11);
    *(_WORD *)(v65 + 360) = 29;
    v66 = (*(__int64 (__fastcall **)(struct IHttpResponse *))(*(_QWORD *)v10 + 8LL))(v10);
    v101 = 0;
    *(_QWORD *)(v66 + 384) = "bytes";
    *(_WORD *)(v66 + 376) = 5;
    String = W3_STATIC_FILE_HANDLER::CacheValidationDoWork(a2, v11, &v101);
    if ( String >= 0 )
    {
      if ( v101 )
        goto LABEL_85;
      v67 = *(__int64 (__fastcall **)(struct IHttpResponse *, __int64, char *, _QWORD, int))(*(_QWORD *)v10 + 32LL);
      v68 = STRA::QueryCCH((STRA *)v114);
      v69 = STRA::QueryStr((STRA *)v114);
      String = v67(v10, 12, v69, v68, 1);
      if ( String >= 0 )
      {
        v105 = 0;
        (*(void (__fastcall **)(struct IHttpFileInfo *, unsigned __int64 *))(*(_QWORD *)v11 + 64LL))(v11, &v105);
        if ( !v105 )
          goto LABEL_66;
        v70 = (*(__int64 (__fastcall **)(struct IHttpFileInfo *))(*(_QWORD *)v11 + 72LL))(v11) == 0;
        v71 = *(_QWORD *)v11;
        if ( v70 )
        {
          v75 = *(__int64 (__fastcall **)(struct IHttpFileInfo *))(v71 + 80);
          v107 = 0;
          LODWORD(v107) = 1;
          v108 = 0;
          *((_QWORD *)&v108 + 1) = v75(v11);
          *(_QWORD *)&v108 = v105;
          v76 = *(_QWORD *)v10;
          *((_QWORD *)&v107 + 1) = 0;
          v74 = (*(__int64 (__fastcall **)(struct IHttpResponse *, __int128 *, __int64))(v76 + 160))(
                  v10,
                  &v107,
                  0xFFFFFFFFLL);
        }
        else
        {
          v72 = v105;
          v73 = (const unsigned __int8 *)(*(__int64 (__fastcall **)(struct IHttpFileInfo *))(v71 + 72))(v11);
          v74 = W3_STATIC_FILE_HANDLER::AddResponseChunk(v10, v73, v72);
        }
        String = v74;
        if ( v74 >= 0 )
        {
LABEL_66:
          v77 = (**(__int64 (__fastcall ***)(struct IHttpContext *))a2)(a2);
          v78 = (void (__fastcall ***)(_QWORD, __int64, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v77 + 24LL))(v77);
          (**v78)(v78, 0, 1);
          v22 = 2;
          (**v78)(v78, 2, 1);
          if ( !*(_DWORD *)(a3 + 120) )
            goto LABEL_85;
          if ( *(_DWORD *)(a3 + 124) )
          {
            (*(void (__fastcall **)(struct IHttpResponse *, __int64))(*(_QWORD *)v10 + 112LL))(v10, 4);
            v81 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 48LL))(a2);
            v110 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v81 + 32LL))(v81);
            v106 = 0;
            if ( v110 )
            {
              v82 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 48LL))(a2);
              v106 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64, const char *))(*(_QWORD *)v82 + 80LL))(
                                                 v82,
                                                 "SID");
            }
            v83 = *(int (__fastcall **)(struct IHttpServer *, unsigned __int16 *, __int64, const unsigned __int16 *, _QWORD, _QWORD, int, __int64, __int64))(*(_QWORD *)g_pGlobalInfo + 64LL);
            v84 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
            v85 = STRU::QueryStr((STRU *)(a3 + 184));
            v86 = (_QWORD *)(v112 + 16);
            if ( v83(g_pGlobalInfo, v85, v110, v106, 0, 0, 1, v112 + 16, v84) < 0 )
            {
              LOWORD(v104) = 0;
              v106 = 0;
              v101 = 0;
              STRA::STRA((STRA *)v113);
              v93 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 24LL))(a2);
              v94 = (const char *)(*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v93 + 16LL))(
                                    v93,
                                    23,
                                    &v104);
              String = LANG_STRING::GetString(
                         (LANG_STRING *)W3_STATIC_FILE_HANDLER::sm_pLangString,
                         v94,
                         (unsigned __int16)v104,
                         0x2F67u,
                         &v106,
                         (unsigned int *)&v101);
              if ( String >= 0 )
              {
                String = STRA::CopyWToUTF8Unescaped((STRA *)v113, v106, v101);
                if ( String >= 0 )
                {
                  v102 = 0;
                  v107 = 0;
                  v108 = 0;
                  *((_QWORD *)&v107 + 1) = STRA::QueryStr((STRA *)v113);
                  LODWORD(v108) = STRA::QueryCCH((STRA *)v113);
                  String = (*(__int64 (__fastcall **)(struct IHttpResponse *, __int128 *, __int64, _QWORD, _DWORD, unsigned int *, _QWORD))(*(_QWORD *)v10 + 168LL))(
                             v10,
                             &v107,
                             1,
                             0,
                             0,
                             &v102,
                             0);
                  if ( String >= 0 )
                  {
                    STRA::~STRA((STRA *)v113);
                    goto LABEL_85;
                  }
                }
              }
              STRA::~STRA((STRA *)v113);
LABEL_88:
              *(_WORD *)((*(__int64 (__fastcall **)(struct IHttpResponse *))(*(_QWORD *)v10 + 8LL))(v10) + 536) = 0;
              (*(void (__fastcall **)(struct IHttpResponse *, __int64, const char *, _QWORD, int, _QWORD, _DWORD))(*(_QWORD *)v10 + 24LL))(
                v10,
                500,
                "Internal Server Error",
                0,
                String,
                0,
                0);
              goto LABEL_89;
            }
            (*(void (__fastcall **)(_QWORD, unsigned __int64 *))(*(_QWORD *)*v86 + 64LL))(*v86, &v105);
            if ( !v105 )
              goto LABEL_85;
            v87 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v86 + 72LL))(*v86);
            v88 = *v86;
            if ( v87 )
            {
              v89 = v105;
              v90 = (const unsigned __int8 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v88 + 72LL))(v88);
              v91 = W3_STATIC_FILE_HANDLER::AddResponseChunk(v10, v90, v89);
            }
            else
            {
              v107 = 0;
              LODWORD(v107) = 1;
              v108 = 0;
              *((_QWORD *)&v108 + 1) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v88 + 80LL))(v88);
              *(_QWORD *)&v108 = v105;
              v92 = *(_QWORD *)v10;
              *((_QWORD *)&v107 + 1) = 0;
              v91 = (*(__int64 (__fastcall **)(struct IHttpResponse *, __int128 *, __int64))(v92 + 160))(
                      v10,
                      &v107,
                      0xFFFFFFFFLL);
            }
            String = v91;
            v80 = v91 < 0;
          }
          else
          {
            v79 = (STRA *)(a3 + 128);
            if ( !STRA::QueryCCH(v79) )
              goto LABEL_85;
            v107 = 0;
            v108 = 0;
            *((_QWORD *)&v107 + 1) = STRA::QueryStr(v79);
            LODWORD(v108) = STRA::QueryCCH(v79);
            String = (*(__int64 (__fastcall **)(struct IHttpResponse *, __int128 *, __int64))(*(_QWORD *)v10 + 160LL))(
                       v10,
                       &v107,
                       0xFFFFFFFFLL);
            v80 = String < 0;
          }
          if ( !v80 )
            goto LABEL_85;
          goto LABEL_88;
        }
      }
    }
LABEL_87:
    v22 = 2;
    goto LABEL_88;
  }
  v16 = (*(__int64 (__fastcall **)(struct IHttpResponse *))(*(_QWORD *)v10 + 8LL))(v10);
  v17 = "Forbidden";
  v18 = 403;
  v99 = -2147024891;
  v19 = 2;
LABEL_5:
  *(_WORD *)(v16 + 536) = 0;
  v20 = v10;
  v21 = *(void (__fastcall **)(struct IHttpResponse *, __int64, const char *, __int64, int, _QWORD, _DWORD))(*(_QWORD *)v10 + 24LL);
LABEL_6:
  v21(v20, v18, v17, v19, v99, 0, 0);
LABEL_85:
  v95 = (__int64 (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(struct IHttpResponse *))(*(_QWORD *)v10 + 16LL))(v10);
  v96 = (struct _HTTP_CACHE_POLICY *)(**v95)(v95);
  W3_STATIC_FILE_HANDLER::SetupHttpCachedResponse(v97, a2, v96);
  (*(void (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 200LL))(a2);
  v22 = 0;
LABEL_89:
  STRA::~STRA((STRA *)v114);
  return v22;
}

```

## disassembly

```asm
0x180002dd8  mov     [rsp-8+arg_18], rbx
0x180002ddd  push    rbp
0x180002dde  push    rsi
0x180002ddf  push    rdi
0x180002de0  push    r12
0x180002de2  push    r13
0x180002de4  push    r14
0x180002de6  push    r15
0x180002de8  lea     rbp, [rsp-150h]
0x180002df0  sub     rsp, 250h
0x180002df7  mov     rax, cs:__security_cookie
0x180002dfe  xor     rax, rsp
0x180002e01  mov     [rbp+180h+var_40], rax
0x180002e08  mov     rax, [rdx]
0x180002e0b  mov     r13, r8
0x180002e0e  mov     [rbp+180h+var_1D8], rcx
0x180002e12  mov     r14, rdx
0x180002e15  mov     rcx, rdx
0x180002e18  mov     rax, [rax+18h]
0x180002e1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e21  mov     rcx, [r14]
0x180002e24  mov     rdi, rax
0x180002e27  mov     [rbp+180h+var_1E8], rax
0x180002e2b  mov     rax, [rcx+20h]
0x180002e2f  mov     rcx, r14
0x180002e32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e37  xor     ebx, ebx
0x180002e39  lea     rdx, [rbp+180h+var_160]
0x180002e3d  lea     rcx, [rbp+180h+var_198]
0x180002e41  mov     [rsp+280h+var_224], ebx
0x180002e45  mov     rsi, rax
0x180002e48  lea     r8d, [rbx+20h]
0x180002e4c  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180002e52  mov     rcx, [r14]
0x180002e55  mov     rax, [rcx+0D0h]
0x180002e5c  mov     rcx, r14
0x180002e5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e64  mov     rcx, [r14]
0x180002e67  mov     r15, rax
0x180002e6a  mov     rax, [rcx+110h]
0x180002e71  mov     rcx, r14
0x180002e74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e79  xor     r8d, r8d
0x180002e7c  xor     edx, edx
0x180002e7e  mov     rcx, rax
0x180002e81  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x180002e86  test    eax, eax
0x180002e88  jz      short loc_180002EBB
0x180002e8a  mov     rax, [r15]
0x180002e8d  mov     rcx, r15
0x180002e90  mov     rax, [rax+58h]
0x180002e94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e99  mov     rcx, [r14]
0x180002e9c  mov     rbx, rax
0x180002e9f  mov     rax, [rcx+110h]
0x180002ea6  mov     rcx, r14
0x180002ea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002eae  mov     r8, rbx; unsigned __int16 *
0x180002eb1  mov     rcx, rax; struct IHttpTraceContext *
0x180002eb4  call    ?RaiseEvent@GENERAL_STATIC_FILE_HANDLER@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBG@Z; IISGeneralEvents::GENERAL_STATIC_FILE_HANDLER::RaiseEvent(IHttpTraceContext *,_GUID const *,ushort const *)
0x180002eb9  xor     ebx, ebx
0x180002ebb  test    byte ptr [r13+118h], 1
0x180002ec3  jnz     short loc_180002F12
0x180002ec5  mov     rax, [rsi]
0x180002ec8  mov     rcx, rsi
0x180002ecb  mov     rax, [rax+8]
0x180002ecf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ed4  mov     dword ptr [rsp+280h+var_250], ebx
0x180002ed8  lea     r8, aForbidden; "Forbidden"
0x180002edf  mov     [rsp+280h+var_258], rbx
0x180002ee4  mov     edx, 193h
0x180002ee9  mov     dword ptr [rsp+280h+var_260], 80070005h
0x180002ef1  mov     r9d, 2
0x180002ef7  mov     [rax+218h], bx
0x180002efe  mov     rcx, rsi
0x180002f01  mov     rax, [rsi]
0x180002f04  mov     rax, [rax+18h]
0x180002f08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f0d  jmp     loc_180003A88
0x180002f12  mov     rax, [r15]
0x180002f15  mov     rcx, r15
0x180002f18  mov     rax, [rax+38h]
0x180002f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f21  mov     r12d, 2
0x180002f27  test    r12b, al
0x180002f2a  jz      short loc_180002F5F
0x180002f2c  mov     rax, [rsi]
0x180002f2f  mov     rcx, rsi
0x180002f32  mov     rax, [rax+8]
0x180002f36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f3b  mov     dword ptr [rsp+280h+var_250], ebx
0x180002f3f  lea     r9d, [r12+7]
0x180002f44  mov     [rsp+280h+var_258], rbx
0x180002f49  lea     r8, aNotFound; "Not Found"
0x180002f50  mov     dword ptr [rsp+280h+var_260], 80070002h
0x180002f58  mov     edx, 194h
0x180002f5d  jmp     short loc_180002EF7
0x180002f5f  mov     rax, [rdi]
0x180002f62  mov     rcx, rdi
0x180002f65  mov     rax, [rax+8]
0x180002f69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f6e  mov     ecx, [rax+24h]
0x180002f71  sub     ecx, 4
0x180002f74  cmp     ecx, 1
0x180002f77  jbe     short loc_180002FE9
0x180002f79  mov     rax, [rsi]
0x180002f7c  mov     rcx, rsi
0x180002f7f  mov     rax, [rax+8]
0x180002f83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f88  mov     dword ptr [rsp+280h+var_250], ebx
0x180002f8c  lea     r8, aMethodNotAllow; "Method Not Allowed"
0x180002f93  xor     r9d, r9d
0x180002f96  mov     [rsp+280h+var_258], rbx
0x180002f9b  mov     edx, 195h
0x180002fa0  mov     dword ptr [rsp+280h+var_260], 80070001h
0x180002fa8  mov     [rax+218h], bx
0x180002faf  mov     rcx, rsi
0x180002fb2  mov     rax, [rsi]
0x180002fb5  mov     rax, [rax+18h]
0x180002fb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fbe  mov     rax, [rsi]
0x180002fc1  mov     rcx, rsi
0x180002fc4  mov     rax, [rax+8]
0x180002fc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fcd  lea     rcx, aGetHeadOptions; "GET, HEAD, OPTIONS, TRACE"
0x180002fd4  mov     [rax+0E0h], rcx
0x180002fdb  mov     word ptr [rax+0D8h], 19h
0x180002fe4  jmp     loc_180003A88
0x180002fe9  mov     rax, [rdi]
0x180002fec  xor     r8d, r8d
0x180002fef  mov     rcx, rdi
0x180002ff2  mov     rax, [rax+10h]
0x180002ff6  lea     edx, [r8+1Ah]
0x180002ffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fff  test    rax, rax
0x180003002  jz      short loc_180003034
0x180003004  mov     rax, [rsi]
0x180003007  mov     rcx, rsi
0x18000300a  mov     rax, [rax+8]
0x18000300e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003013  mov     dword ptr [rsp+280h+var_250], ebx
0x180003017  lea     r8, aExpectationFai; "Expectation Failed"
0x18000301e  mov     [rsp+280h+var_258], rbx
0x180003023  xor     r9d, r9d
0x180003026  mov     dword ptr [rsp+280h+var_260], ebx
0x18000302a  mov     edx, 1A1h
0x18000302f  jmp     loc_180002EF7
0x180003034  mov     rax, [r14]
0x180003037  xor     edx, edx
0x180003039  mov     rcx, r14
0x18000303c  mov     [rsp+280h+var_230], ebx
0x180003040  mov     rax, [rax+0B8h]
0x180003047  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000304c  mov     edx, 2Eh ; '.'; Ch
0x180003051  mov     [rbp+180h+var_1F0], rax
0x180003055  mov     rcx, rax; Str
0x180003058  call    cs:__imp_wcsrchr
0x18000305e  test    rax, rax
0x180003061  lea     rcx, Str
0x180003068  cmovnz  rcx, rax
0x18000306c  mov     [rsp+280h+var_218], rcx
0x180003071  mov     rcx, [r14]
0x180003074  mov     rax, [rcx+98h]
0x18000307b  mov     rcx, r14
0x18000307e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003083  mov     rdx, rax
0x180003086  mov     rcx, [rax]
0x180003089  mov     rax, [rcx]
0x18000308c  mov     rcx, rdx
0x18000308f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003094  mov     rdx, cs:?g_pStaticFileModuleContext@@3PEAXEA; void * g_pStaticFileModuleContext
0x18000309b  mov     r8, rax
0x18000309e  mov     [rbp+180h+var_1E0], rax
0x1800030a2  mov     rcx, [rax]
0x1800030a5  mov     rax, [rcx]
0x1800030a8  mov     rcx, r8
0x1800030ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030b0  mov     rbx, rax
0x1800030b3  test    rax, rax
0x1800030b6  jz      short loc_180003101
0x1800030b8  mov     rdx, [rsp+280h+var_218]
0x1800030bd  lea     rcx, [rax+60h]
0x1800030c1  call    cs:__imp_?EqualsNoCase@STRU@@QEBA_NPEBG@Z; STRU::EqualsNoCase(ushort const *)
0x1800030c7  test    al, al
0x1800030c9  jz      short loc_180003101
0x1800030cb  mov     r12d, [rbx+0D8h]
0x1800030d2  test    r12d, r12d
0x1800030d5  jz      loc_18000334A
0x1800030db  lea     rcx, [rbx+8]
0x1800030df  call    cs:__imp_?QueryStr@STRA@@QEBAPEBDXZ; STRA::QueryStr(void)
0x1800030e5  mov     rdx, rax
0x1800030e8  lea     rcx, [rbp+180h+var_198]
0x1800030ec  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x1800030f2  mov     ebx, eax
0x1800030f4  test    eax, eax
0x1800030f6  js      loc_180003ACC
0x1800030fc  jmp     loc_18000334A
0x180003101  mov     rdx, [rbp+180h+var_1F0]; unsigned __int16 *
0x180003105  lea     rax, [rsp+280h+var_22C]
0x18000310a  mov     rcx, [r13+100h]; this
0x180003111  lea     r9, [rsp+280h+var_224]; int *
0x180003116  lea     r8, [rbp+180h+var_198]; struct STRA *
0x18000311a  mov     [rsp+280h+var_260], rax; int *
0x18000311f  mov     [rsp+280h+var_22C], 0
0x180003127  call    ?SelectMimeMappingForFileExt@MIME_MAP_TABLE@@QEAAJPEBGPEAVSTRA@@PEAH2@Z; MIME_MAP_TABLE::SelectMimeMappingForFileExt(ushort const *,STRA *,int *,int *)
0x18000312c  mov     ebx, eax
0x18000312e  test    eax, eax
0x180003130  js      loc_180003AD2
0x180003136  mov     r12d, [rsp+280h+var_224]
0x18000313b  test    r12d, r12d
0x18000313e  jz      short loc_18000314B
0x180003140  cmp     [rsp+280h+var_22C], 0
0x180003145  jz      loc_180003276
0x18000314b  xor     edx, edx; Val
0x18000314d  lea     rcx, [rbp+180h+var_140]; void *
0x180003151  mov     r8d, 100h; Size
0x180003157  call    memset_0
0x18000315c  mov     r8d, 80h
0x180003162  lea     rdx, [rbp+180h+var_140]
0x180003166  lea     rcx, [rbp+180h+var_1D0]
0x18000316a  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180003170  mov     rax, [r14]
0x180003173  xor     edx, edx
0x180003175  mov     rcx, r14
0x180003178  mov     rax, [rax+0B0h]
0x18000317f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003184  mov     rdx, rax
0x180003187  lea     rcx, [rbp+180h+var_1D0]
0x18000318b  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180003191  lea     rcx, [rbp+180h+var_1D0]
0x180003195  mov     ebx, eax
0x180003197  test    eax, eax
0x180003199  jns     short loc_1800031A6
0x18000319b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800031a1  jmp     loc_180003ACC
0x1800031a6  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800031ac  mov     rcx, rax; String
0x1800031af  call    cs:__imp__wcsupr
0x1800031b5  mov     rax, [rdi]
0x1800031b8  mov     rcx, rdi
0x1800031bb  mov     rax, [rax+40h]
0x1800031bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031c4  lea     rcx, [rbp+180h+var_1D0]
0x1800031c8  mov     rbx, rax
0x1800031cb  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800031d1  mov     r9d, [r13+118h]; unsigned int
0x1800031d8  lea     rcx, [rsp+280h+var_22C]
0x1800031dd  mov     [rsp+280h+var_260], rcx; unsigned int *
0x1800031e2  mov     r8, rbx; char *
0x1800031e5  mov     rcx, [r13+110h]; this
0x1800031ec  mov     rdx, rax; unsigned __int16 *
0x1800031ef  mov     [rsp+280h+var_22C], 0
0x1800031f7  call    ?CalculateScriptMapEntry@META_SCRIPT_MAP_TABLE@@QEAAPEAVMETA_SCRIPT_MAP_ENTRY@@PEBGPEBDKPEAKPEAVMULTISZ@@@Z; META_SCRIPT_MAP_TABLE::CalculateScriptMapEntry(ushort const *,char const *,ulong,ulong *,MULTISZ *)
0x1800031fc  mov     [rbp+180h+var_1F0], rax
0x180003200  mov     rbx, rax
0x180003203  test    rax, rax
0x180003206  jz      short loc_180003261
0x180003208  mov     rcx, [r14]
0x18000320b  mov     rax, [rcx+0C0h]
0x180003212  mov     rcx, r14
0x180003215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000321a  mov     rcx, [rbx]
0x18000321d  mov     rdx, rax
0x180003220  mov     rbx, [rcx+50h]
0x180003224  mov     rcx, [rax]
0x180003227  mov     rax, [rcx+50h]
0x18000322b  mov     rcx, rdx
0x18000322e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003233  mov     rcx, [rbp+180h+var_1F0]
0x180003237  mov     rdi, rax
0x18000323a  mov     rax, rbx
0x18000323d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003242  sub     rax, rdi
0x180003245  mov     r8d, 2
0x18000324b  movzx   edx, word ptr [rdi]
0x18000324e  movzx   ecx, word ptr [rdi+rax]
0x180003252  sub     edx, ecx
0x180003254  jnz     short loc_18000325D
0x180003256  add     rdi, r8
0x180003259  test    ecx, ecx
0x18000325b  jnz     short loc_18000324B
0x18000325d  test    edx, edx
0x18000325f  jz      short loc_18000326C
0x180003261  mov     [rsp+280h+var_230], 1
0x180003269  xor     r12d, r12d
0x18000326c  lea     rcx, [rbp+180h+var_1D0]
0x180003270  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180003276  mov     ecx, 0E0h; Size
0x18000327b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003280  mov     rdi, rax
0x180003283  test    rax, rax
0x180003286  jz      loc_180003AC7
0x18000328c  lea     rax, ??_7STATIC_URI_STORED_CONTEXT@@6B@; const STATIC_URI_STORED_CONTEXT::`vftable'
0x180003293  mov     ebx, 20h ; ' '
0x180003298  mov     r8d, ebx
0x18000329b  mov     [rdi], rax
0x18000329e  lea     rdx, [rdi+40h]
0x1800032a2  lea     rcx, [rdi+8]
0x1800032a6  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x1800032ac  lea     rdx, [rdi+98h]
  ... truncated ...
```
