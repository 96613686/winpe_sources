# W3_STATIC_FILE_HANDLER::DoWork(IHttpContext *,STATIC_META_STORED_CONTEXT *,int,STRA *)

- ea: `0x180016708`
- end: `0x1800174f2`
- name: `?DoWork@W3_STATIC_FILE_HANDLER@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVSTATIC_META_STORED_CONTEXT@@HPEAVSTRA@@@Z`
- size: `3562`
- prototype: `enum REQUEST_NOTIFICATION_STATUS __high(struct IHttpContext *, struct STATIC_META_STORED_CONTEXT *, int, struct STRA *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180007cc0`

## callees

- `0x1800011d4`
- `0x18000bb20`
- `0x18001602c`
- `0x1800164a8`
- `0x180016538`
- `0x180016708`
- `0x180017718`
- `0x180017a44`
- `0x180017b38`
- `0x1800224c2`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `msvcrt!_wcsupr` at `0x180016bf0`
- `msvcrt!_wcsupr` at `0x180016bf0`
- `msvcrt!wcsrchr` at `0x180016a43`
- `msvcrt!wcsrchr` at `0x180016a43`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180016ac7`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180016b60`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180016cfe`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180016ac7`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180016b60`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180016cfe`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18001739c`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180017426`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800174bf`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18001739c`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180017426`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800174bf`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180016bd1`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180016d12`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180016bd1`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180016d12`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180016be1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180016c8b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180016be1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180016c8b`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180016bb0`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180016cd6`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180016bb0`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180016cd6`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18001732f`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18001732f`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18001678a`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180016cbf`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18001678a`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180016cbf`
- `iisutil!?EqualsNoCase@STRU@@QEBA_NPEBG@Z` at `0x180016aa9`
- `iisutil!?EqualsNoCase@STRU@@QEBA_NPEBG@Z` at `0x180016aa9`
- `iisutil!?GetString@LANG_STRING@@QEAAJPEBDKIPEAPEBGPEAK@Z` at `0x180017389`
- `iisutil!?GetString@LANG_STRING@@QEAAJPEBDKIPEAPEBGPEAK@Z` at `0x180017389`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBGK@Z` at `0x1800173b0`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBGK@Z` at `0x1800173b0`

## pseudocode

```c
__int64 __fastcall W3_STATIC_FILE_HANDLER::DoWork(
        __int64 a1,
        struct IHttpContext *a2,
        __int64 a3,
        __int64 a4,
        struct IScriptMapInfo *a5)
{
  __int64 v7; // rax
  const unsigned __int16 *v8; // rax
  __int64 v9; // rcx
  const unsigned __int16 *v10; // r14
  __int64 v11; // rax
  struct IHttpResponse *v12; // rdi
  struct IHttpFileInfo *v13; // r12
  int (__fastcall ***v14)(_QWORD, _OWORD *); // rax
  __int64 v15; // rbx
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rax
  __int64 v19; // rax
  const char *v20; // r8
  __int64 v21; // r9
  __int64 v22; // rdx
  struct IHttpResponse *v23; // rcx
  void (__fastcall *v24)(struct IHttpResponse *, __int64, const char *, __int64, int, _QWORD, _DWORD); // rax
  __int64 v25; // rax
  __int64 v26; // rax
  wchar_t *v27; // rax
  const unsigned __int16 *v28; // r13
  __int64 (__fastcall *v29)(struct IHttpContext *); // rax
  __int64 (__fastcall ***v30)(_QWORD); // rax
  __int64 v31; // rax
  __int64 v32; // rbx
  int v33; // r13d
  int v34; // ebx
  __int64 v35; // rax
  int v36; // eax
  const unsigned __int16 *v37; // rax
  const char *v38; // rax
  struct IScriptMapInfo *v39; // rbx
  __int64 v40; // rax
  __int64 (__fastcall *v41)(struct IScriptMapInfo *); // rbx
  unsigned __int16 *v42; // r14
  __int64 v43; // rax
  int v44; // ecx
  int v45; // edx
  char *v46; // r14
  char *v47; // rdx
  __int64 v48; // rax
  int (__fastcall ***v49)(_QWORD, _OWORD *); // rax
  const unsigned __int16 *v50; // rbx
  struct IHttpTraceContext *v51; // rax
  const struct _GUID *v52; // rdx
  __int64 v53; // rax
  const char *v54; // rax
  __int64 v55; // rbx
  __int64 v56; // rbx
  __int64 v57; // rax
  bool v58; // zf
  __int64 v59; // rax
  unsigned __int64 v60; // rbx
  const unsigned __int8 *v61; // rax
  int v62; // eax
  __int64 (__fastcall *v63)(struct IHttpFileInfo *); // rax
  __int64 v64; // rax
  __int64 v65; // rax
  void (__fastcall ***v66)(_QWORD, __int64, __int64); // rbx
  unsigned int v67; // r14d
  int v68; // ecx
  __int64 v69; // rax
  __int64 (__fastcall *v70)(struct IHttpResponse *, _OWORD *, __int64); // rax
  __int64 v71; // rax
  __int64 v72; // r13
  __int64 v73; // r12
  __int64 v74; // rax
  int (__fastcall *v75)(struct IHttpServer *, _QWORD, __int64, __int64, _QWORD, _QWORD, int, __int64, __int64); // rbx
  __int64 v76; // rax
  _QWORD *v77; // r14
  __int64 v78; // rax
  __int64 v79; // rcx
  unsigned __int64 v80; // rbx
  const unsigned __int8 *v81; // rax
  int v82; // eax
  __int64 v83; // rax
  __int64 v84; // rax
  const char *v85; // rax
  __int64 v86; // rax
  __int64 (__fastcall *v87)(struct IHttpResponse *, _OWORD *, __int64); // rax
  __int64 (__fastcall ***v88)(_QWORD); // rax
  struct _HTTP_CACHE_POLICY *v89; // rax
  W3_STATIC_FILE_HANDLER *v90; // rcx
  int v92; // [rsp+20h] [rbp-E0h]
  __int64 v93; // [rsp+30h] [rbp-D0h]
  int v94; // [rsp+50h] [rbp-B0h] BYREF
  int v95; // [rsp+54h] [rbp-ACh] BYREF
  unsigned __int16 v96[2]; // [rsp+58h] [rbp-A8h] BYREF
  int v97; // [rsp+5Ch] [rbp-A4h] BYREF
  _OWORD v98[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v99; // [rsp+80h] [rbp-80h] BYREF
  const unsigned __int16 *v100; // [rsp+88h] [rbp-78h] BYREF
  struct IScriptMapInfo *v101; // [rsp+90h] [rbp-70h]
  unsigned __int16 *v102; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v103; // [rsp+A0h] [rbp-60h]
  __int64 v104; // [rsp+A8h] [rbp-58h]
  __int64 v105; // [rsp+B0h] [rbp-50h]
  _QWORD v106[6]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v107; // [rsp+F0h] [rbp-10h]
  int v108; // [rsp+100h] [rbp+0h]
  int v109; // [rsp+104h] [rbp+4h]
  int v110; // [rsp+108h] [rbp+8h]
  _QWORD v111[2]; // [rsp+10Ch] [rbp+Ch] BYREF
  const wchar_t *v112; // [rsp+120h] [rbp+20h] BYREF
  int v113; // [rsp+128h] [rbp+28h]
  __int64 v114; // [rsp+130h] [rbp+30h]
  int v115; // [rsp+138h] [rbp+38h]
  wchar_t *String; // [rsp+140h] [rbp+40h]
  const wchar_t *v117; // [rsp+148h] [rbp+48h]
  int v118; // [rsp+150h] [rbp+50h]
  __int64 v119; // [rsp+158h] [rbp+58h]
  int v120; // [rsp+160h] [rbp+60h]
  __int64 v121; // [rsp+168h] [rbp+68h]
  _BYTE v122[32]; // [rsp+170h] [rbp+70h] BYREF
  char *v123; // [rsp+190h] [rbp+90h]
  unsigned __int16 v124; // [rsp+1A0h] [rbp+A0h]
  char v125[40]; // [rsp+1A8h] [rbp+A8h] BYREF
  unsigned __int16 v126[128]; // [rsp+1D0h] [rbp+D0h] BYREF

  v101 = a5;
  v7 = *(_QWORD *)a2;
  v105 = a1;
  v8 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IHttpContext *))(v7 + 24))(a2);
  v9 = *(_QWORD *)a2;
  v10 = v8;
  v100 = v8;
  v11 = (*(__int64 (__fastcall **)(struct IHttpContext *))(v9 + 32))(a2);
  v95 = 0;
  v12 = (struct IHttpResponse *)v11;
  STRA::STRA((STRA *)v122, v125, 0x20u);
  v13 = (struct IHttpFileInfo *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 208LL))(a2);
  v14 = (int (__fastcall ***)(_QWORD, _OWORD *))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
  *(_QWORD *)&v98[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  *(_OWORD *)((char *)v98 + 8) = 0;
  if ( (**v14)(v14, v98) >= 0 && LODWORD(v98[1]) )
  {
    v15 = (*(__int64 (__fastcall **)(struct IHttpFileInfo *))(*(_QWORD *)v13 + 88LL))(v13);
    v16 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
    v106[3] = 15;
    v110 = 2;
    v106[1] = 0;
    memset(v111, 0, 12);
    v106[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
    v106[2] = &`IISGeneralEvents::GetAreaGuid'::`2'::AreaGuid;
    v106[4] = L"GENERAL_DAV_HANDLER";
    v106[5] = 1;
    v109 = 1;
    v112 = L"ContextId";
    v117 = L"FileName";
    v107 = 0;
    v108 = 0;
    v113 = 72;
    v114 = 0;
    v115 = 16;
    String = 0;
    v118 = 31;
    v119 = v15;
    if ( v15 )
    {
      v18 = -1;
      do
        ++v18;
      while ( *(_WORD *)(v15 + 2 * v18) );
      v17 = 2 * v18 + 2;
    }
    else
    {
      v17 = 0;
    }
    v120 = v17;
    v121 = 0;
    *(_QWORD *)((char *)v111 + 4) = &v112;
    (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v16 + 16LL))(v16, v106);
  }
  if ( (*(_BYTE *)(a3 + 280) & 1) != 0 )
  {
    (*(void (__fastcall **)(struct IHttpFileInfo *))(*(_QWORD *)v13 + 56LL))(v13);
    if ( (unsigned int)(*(_DWORD *)((*(__int64 (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v10 + 8LL))(v10)
                                  + 36)
                      - 4) > 1 )
    {
      *(_WORD *)((*(__int64 (__fastcall **)(struct IHttpResponse *))(*(_QWORD *)v12 + 8LL))(v12) + 536) = 0;
      (*(void (__fastcall **)(struct IHttpResponse *, __int64, const char *, _QWORD, int, _QWORD, _DWORD))(*(_QWORD *)v12 + 24LL))(
        v12,
        405,
        "Method Not Allowed",
        0,
        -2147024895,
        0,
        0);
      v25 = (*(__int64 (__fastcall **)(struct IHttpResponse *))(*(_QWORD *)v12 + 8LL))(v12);
      *(_QWORD *)(v25 + 224) = "GET, HEAD, OPTIONS, TRACE";
      *(_WORD *)(v25 + 216) = 25;
      goto LABEL_99;
    }
    if ( (*(__int64 (__fastcall **)(const unsigned __int16 *, __int64))(*(_QWORD *)v10 + 16LL))(v10, 26) )
    {
      v19 = (*(__int64 (__fastcall **)(struct IHttpResponse *))(*(_QWORD *)v12 + 8LL))(v12);
      v20 = "Expectation Failed";
      v21 = 0;
      v92 = 0;
      v22 = 417;
      goto LABEL_11;
    }
    v26 = *(_QWORD *)a2;
    v94 = 0;
    v102 = (unsigned __int16 *)(*(__int64 (__fastcall **)(struct IHttpContext *, _QWORD))(v26 + 184))(a2, 0);
    v27 = wcsrchr(v102, 0x2Eu);
    v28 = &Src;
    if ( v27 )
      v28 = v27;
    v29 = *(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 152LL);
    v103 = v28;
    v30 = (__int64 (__fastcall ***)(_QWORD))v29(a2);
    v104 = (**v30)(v30);
    v31 = (**(__int64 (__fastcall ***)(__int64, void *))v104)(v104, g_pStaticFileModuleContext);
    v32 = v31;
    if ( v31 && STRU::EqualsNoCase((STRU *)(v31 + 96), v28) )
    {
      v33 = *(_DWORD *)(v32 + 216);
      if ( v33 )
      {
        v34 = STRA::Copy((STRA *)v122, *(const char **)(v32 + 40));
        if ( v34 < 0 )
          goto LABEL_101;
      }
    }
    else
    {
      v97 = 0;
      v34 = STATIC_META_STORED_CONTEXT::SelectMimeMappingForFileExt(
              (STATIC_META_STORED_CONTEXT *)a3,
              v102,
              (struct STRA *)v122,
              &v95,
              &v97);
      if ( v34 < 0 )
        goto LABEL_101;
      v33 = v95;
      if ( v101 )
      {
        if ( !v95 )
        {
          v34 = STRA::Copy((STRA *)v122, *((const char **)v101 + 4));
          if ( v34 < 0 )
            goto LABEL_101;
          v33 = 1;
        }
        v36 = 0;
      }
      else
      {
        v36 = v97;
      }
      if ( !v33 || v36 )
      {
        memset_0(v126, 0, sizeof(v126));
        STRU::STRU((STRU *)&v112, v126, 0x80u);
        v37 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IHttpContext *, _QWORD))(*(_QWORD *)a2 + 176LL))(
                                          a2,
                                          0);
        v34 = STRU::Copy((STRU *)&v112, v37);
        if ( v34 < 0 )
        {
          STRU::~STRU((STRU *)&v112);
          goto LABEL_101;
        }
        _wcsupr(String);
        v38 = (const char *)(*(__int64 (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v10 + 64LL))(v10);
        v101 = STATIC_META_STORED_CONTEXT::CalculateScriptMapEntry((STATIC_META_STORED_CONTEXT *)a3, String, v38);
        v39 = v101;
        if ( !v101 )
          goto LABEL_42;
        v40 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 192LL))(a2);
        v41 = *(__int64 (__fastcall **)(struct IScriptMapInfo *))(*(_QWORD *)v39 + 80LL);
        v42 = (unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v40 + 80LL))(v40);
        v43 = v41(v101) - (_QWORD)v42;
        do
        {
          v44 = *(unsigned __int16 *)((char *)v42 + v43);
          v45 = *v42 - v44;
          if ( v45 )
            break;
          ++v42;
        }
        while ( v44 );
        if ( v45 )
        {
LABEL_42:
          v94 = 1;
          v33 = 0;
        }
        STRU::~STRU((STRU *)&v112);
      }
      v46 = (char *)operator new(0xE0u);
      if ( !v46 )
      {
        v34 = -2147024882;
        goto LABEL_101;
      }
      *(_QWORD *)v46 = &STATIC_URI_STORED_CONTEXT::`vftable';
      STRA::STRA((STRA *)(v46 + 8), v46 + 64, 0x20u);
      STRU::STRU((STRU *)(v46 + 96), (unsigned __int16 *)v46 + 76, 0x20u);
      *((_DWORD *)v46 + 54) = 0;
      if ( v33 )
      {
        v47 = v123;
        *((_DWORD *)v46 + 54) = 1;
        v34 = STRA::Copy((STRA *)(v46 + 8), v47);
        if ( v34 < 0 || (v34 = STRU::Copy((STRU *)(v46 + 96), v103), v34 < 0) )
        {
          (**(void (__fastcall ***)(void *))v46)(v46);
          goto LABEL_101;
        }
      }
      if ( (*(int (__fastcall **)(__int64, char *, void *))(*(_QWORD *)v104 + 8LL))(
             v104,
             v46,
             g_pStaticFileModuleContext) < 0 )
        (**(void (__fastcall ***)(void *))v46)(v46);
      v10 = v100;
    }
    if ( *(_DWORD *)(a3 + 56) )
    {
      v35 = (*(__int64 (__fastcall **)(struct IHttpResponse *))(*(_QWORD *)v12 + 8LL))(v12);
      if ( *(_QWORD *)(v35 + 64) )
      {
        v34 = (*(__int64 (__fastcall **)(struct IHttpResponse *, _QWORD, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v12 + 32LL))(
                v12,
                0,
                *(_QWORD *)(a3 + 40),
                *(unsigned __int16 *)(a3 + 56),
                0);
        if ( v34 < 0 )
          goto LABEL_101;
      }
      else
      {
        *(_QWORD *)(v35 + 64) = *(_QWORD *)(a3 + 40);
        *(_WORD *)(v35 + 56) = *(_WORD *)(a3 + 56);
      }
    }
    if ( *(_DWORD *)(a3 + 112) )
    {
      v48 = (*(__int64 (__fastcall **)(struct IHttpResponse *))(*(_QWORD *)v12 + 8LL))(v12);
      *(_QWORD *)(v48 + 352) = *(_QWORD *)(a3 + 96);
      *(_WORD *)(v48 + 344) = *(_WORD *)(a3 + 112);
    }
    if ( !v33 )
    {
      v49 = (int (__fastcall ***)(_QWORD, _OWORD *))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
      *(_QWORD *)&v98[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
      *(_OWORD *)((char *)v98 + 8) = 0;
      if ( (**v49)(v49, v98) >= 0
        && LODWORD(v98[1])
        && HIDWORD(v98[0]) >= 3
        && (DWORD2(v98[0]) == 4 || (BYTE8(v98[0]) & 4) != 0) )
      {
        v50 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IHttpFileInfo *))(*(_QWORD *)v13 + 88LL))(v13);
        v51 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
        IISSecurityEvents::SECURITY_DENIED_BY_MIMEMAP::RaiseEvent(v51, v52, v50);
      }
      v53 = (*(__int64 (__fastcall **)(struct IHttpResponse *))(*(_QWORD *)v12 + 8LL))(v12);
      v20 = "Not Found";
      v22 = 404;
      v23 = v12;
      v92 = -2147024846;
      *(_WORD *)(v53 + 536) = 0;
      v24 = *(void (__fastcall **)(struct IHttpResponse *, __int64, const char *, __int64, int, _QWORD, _DWORD))(*(_QWORD *)v12 + 24LL);
      if ( v94 )
        v21 = 17;
      else
        v21 = 3;
      goto LABEL_12;
    }
    v96[0] = 0;
    v54 = (const char *)(*(__int64 (__fastcall **)(const unsigned __int16 *, __int64, unsigned __int16 *))(*(_QWORD *)v10 + 16LL))(
                          v10,
                          20,
                          v96);
    if ( v54 && *v54 )
    {
      v94 = 0;
      v34 = IsAcceptable(v123, v54, v96[0], &v94);
      if ( v34 < 0 )
        goto LABEL_101;
      if ( !v94 )
      {
        v19 = (*(__int64 (__fastcall **)(struct IHttpResponse *))(*(_QWORD *)v12 + 8LL))(v12);
        v20 = "Not Acceptable";
        v21 = 0;
        v92 = 0;
        v22 = 406;
        goto LABEL_11;
      }
    }
    if ( *(_DWORD *)(a3 + 284) )
    {
      v55 = (*(__int64 (__fastcall **)(struct IHttpResponse *))(*(_QWORD *)v12 + 8LL))(v12) + 408;
      *(_QWORD *)(v55 + 8) = (*(__int64 (__fastcall **)(struct IHttpFileInfo *, __int64))(*(_QWORD *)v13 + 96LL))(
                               v13,
                               v55);
    }
    v56 = (*(__int64 (__fastcall **)(struct IHttpResponse *))(*(_QWORD *)v12 + 8LL))(v12);
    *(_QWORD *)(v56 + 368) = (*(__int64 (__fastcall **)(struct IHttpFileInfo *))(*(_QWORD *)v13 + 112LL))(v13);
    *(_WORD *)(v56 + 360) = 29;
    v57 = (*(__int64 (__fastcall **)(struct IHttpResponse *))(*(_QWORD *)v12 + 8LL))(v12);
    v94 = 0;
    *(_QWORD *)(v57 + 384) = "bytes";
    *(_WORD *)(v57 + 376) = 5;
    v34 = W3_STATIC_FILE_HANDLER::CacheValidationDoWork(a2, v13, &v94);
    if ( v34 >= 0 )
    {
      if ( v94 )
        goto LABEL_99;
      v34 = (*(__int64 (__fastcall **)(struct IHttpResponse *, __int64, char *, _QWORD, int))(*(_QWORD *)v12 + 32LL))(
              v12,
              12,
              v123,
              v124,
              1);
      if ( v34 >= 0 )
      {
        v99 = 0;
        (*(void (__fastcall **)(struct IHttpFileInfo *, unsigned __int64 *))(*(_QWORD *)v13 + 64LL))(v13, &v99);
        if ( !v99 )
          goto LABEL_80;
        v58 = (*(__int64 (__fastcall **)(struct IHttpFileInfo *))(*(_QWORD *)v13 + 72LL))(v13) == 0;
        v59 = *(_QWORD *)v13;
        if ( v58 )
        {
          v63 = *(__int64 (__fastcall **)(struct IHttpFileInfo *))(v59 + 80);
          memset(v98, 0, sizeof(v98));
          LODWORD(v98[0]) = 1;
          *((_QWORD *)&v98[1] + 1) = v63(v13);
          *(_QWORD *)&v98[1] = v99;
          v64 = *(_QWORD *)v12;
          *((_QWORD *)&v98[0] + 1) = 0;
          v62 = (*(__int64 (__fastcall **)(struct IHttpResponse *, _OWORD *, __int64))(v64 + 160))(
                  v12,
                  v98,
                  0xFFFFFFFFLL);
        }
        else
        {
          v60 = v99;
          v61 = (const unsigned __int8 *)(*(__int64 (__fastcall **)(struct IHttpFileInfo *))(v59 + 72))(v13);
          v62 = W3_STATIC_FILE_HANDLER::AddResponseChunk(v12, v61, v60);
        }
        v34 = v62;
        if ( v62 >= 0 )
        {
LABEL_80:
          v65 = (**(__int64 (__fastcall ***)(struct IHttpContext *))a2)(a2);
          v66 = (void (__fastcall ***)(_QWORD, __int64, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v65 + 24LL))(v65);
          (**v66)(v66, 0, 1);
          v67 = 2;
          (**v66)(v66, 2, 1);
          if ( !*(_DWORD *)(a3 + 120) )
            goto LABEL_99;
          if ( !*(_DWORD *)(a3 + 124) )
          {
            v68 = *(_DWORD *)(a3 + 176);
            if ( !v68 )
              goto LABEL_99;
            *((_QWORD *)&v98[0] + 1) = *(_QWORD *)(a3 + 160);
            v69 = *(_QWORD *)v12;
            LODWORD(v98[1]) = v68;
            *(_QWORD *)&v98[0] = 0;
            *(_QWORD *)((char *)&v98[1] + 4) = 0;
            v70 = *(__int64 (__fastcall **)(struct IHttpResponse *, _OWORD *, __int64))(v69 + 160);
            HIDWORD(v98[1]) = 0;
            v34 = v70(v12, v98, 0xFFFFFFFFLL);
            if ( v34 >= 0 )
              goto LABEL_99;
LABEL_102:
            LODWORD(v93) = 0;
            *(_WORD *)((*(__int64 (__fastcall **)(struct IHttpResponse *))(*(_QWORD *)v12 + 8LL))(v12) + 536) = 0;
            (*(void (__fastcall **)(struct IHttpResponse *, __int64, const char *, _QWORD, int, _QWORD, __int64))(*(_QWORD *)v12 + 24LL))(
              v12,
              500,
              "Internal Server Error",
              0,
              v34,
              0,
              v93);
            goto LABEL_103;
          }
          (*(void (__fastcall **)(struct IHttpResponse *, __int64))(*(_QWORD *)v12 + 112LL))(v12, 4);
          v71 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 48LL))(a2);
          v72 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v71 + 32LL))(v71);
          v73 = 0;
          if ( v72 )
          {
            v74 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 48LL))(a2);
            v73 = (*(__int64 (__fastcall **)(__int64, const char *))(*(_QWORD *)v74 + 80LL))(v74, "SID");
          }
          v75 = *(int (__fastcall **)(struct IHttpServer *, _QWORD, __int64, __int64, _QWORD, _QWORD, int, __int64, __int64))(*(_QWORD *)g_pGlobalInfo + 64LL);
          v76 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
          v77 = (_QWORD *)(v105 + 16);
          if ( v75(g_pGlobalInfo, *(_QWORD *)(a3 + 216), v72, v73, 0, 0, 1, v105 + 16, v76) < 0 )
          {
            LOWORD(v95) = 0;
            v100 = 0;
            v94 = 0;
            STRA::STRA((STRA *)&v112);
            v84 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 24LL))(a2);
            v85 = (const char *)(*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v84 + 16LL))(
                                  v84,
                                  23,
                                  &v95);
            v34 = LANG_STRING::GetString(
                    (LANG_STRING *)W3_STATIC_FILE_HANDLER::sm_pLangString,
                    v85,
                    (unsigned __int16)v95,
                    0x2F67u,
                    &v100,
                    (unsigned int *)&v94);
            if ( v34 >= 0 )
            {
              v34 = STRA::CopyWToUTF8Unescaped((STRA *)&v112, v100, v94);
              if ( v34 >= 0 )
              {
                *((_QWORD *)&v98[0] + 1) = String;
                LODWORD(v98[1]) = v118;
                v86 = *(_QWORD *)v12;
                HIDWORD(v93) = 0;
                v97 = 0;
                v87 = *(__int64 (__fastcall **)(struct IHttpResponse *, _OWORD *, __int64))(v86 + 168);
                *(_QWORD *)&v98[0] = 0;
                *(_QWORD *)((char *)&v98[1] + 4) = 0;
                HIDWORD(v98[1]) = 0;
                v34 = v87(v12, v98, 1);
                if ( v34 >= 0 )
                {
                  STRA::~STRA((STRA *)&v112);
                  goto LABEL_99;
                }
              }
            }
            STRA::~STRA((STRA *)&v112);
          }
          else
          {
            (*(void (__fastcall **)(_QWORD, unsigned __int64 *))(*(_QWORD *)*v77 + 64LL))(*v77, &v99);
            if ( !v99 )
              goto LABEL_99;
            v78 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v77 + 72LL))(*v77);
            v79 = *v77;
            if ( v78 )
            {
              v80 = v99;
              v81 = (const unsigned __int8 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v79 + 72LL))(v79);
              v82 = W3_STATIC_FILE_HANDLER::AddResponseChunk(v12, v81, v80);
            }
            else
            {
              memset(v98, 0, sizeof(v98));
              LODWORD(v98[0]) = 1;
              *((_QWORD *)&v98[1] + 1) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v79 + 80LL))(v79);
              *(_QWORD *)&v98[1] = v99;
              v83 = *(_QWORD *)v12;
              *((_QWORD *)&v98[0] + 1) = 0;
              v82 = (*(__int64 (__fastcall **)(struct IHttpResponse *, _OWORD *, __int64))(v83 + 160))(
                      v12,
                      v98,
                      0xFFFFFFFFLL);
            }
            v34 = v82;
            if ( v82 >= 0 )
              goto LABEL_99;
          }
        }
      }
    }
LABEL_101:
    v67 = 2;
    goto LABEL_102;
  }
  v19 = (*(__int64 (__fastcall **)(struct IHttpResponse *))(*(_QWORD *)v12 + 8LL))(v12);
  v20 = "Forbidden";
  v21 = 2;
  v92 = -2147024891;
  v22 = 403;
LABEL_11:
  *(_WORD *)(v19 + 536) = 0;
  v23 = v12;
  v24 = *(void (__fastcall **)(struct IHttpResponse *, __int64, const char *, __int64, int, _QWORD, _DWORD))(*(_QWORD *)v12 + 24LL);
LABEL_12:
  v24(v23, v22, v20, v21, v92, 0, 0);
LABEL_99:
  v88 = (__int64 (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(struct IHttpResponse *))(*(_QWORD *)v12 + 16LL))(v12);
  v89 = (struct _HTTP_CACHE_POLICY *)(**v88)(v88);
  W3_STATIC_FILE_HANDLER::SetupHttpCachedResponse(v90, a2, v89);
  (*(void (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 200LL))(a2);
  v67 = 0;
LABEL_103:
  STRA::~STRA((STRA *)v122);
  return v67;
}

```

## disassembly

```asm
0x180016708  mov     [rsp-8+arg_18], rbx
0x18001670d  push    rbp
0x18001670e  push    rsi
0x18001670f  push    rdi
0x180016710  push    r12
0x180016712  push    r13
0x180016714  push    r14
0x180016716  push    r15
0x180016718  lea     rbp, [rsp-1E0h]
0x180016720  sub     rsp, 2E0h
0x180016727  mov     rax, cs:__security_cookie
0x18001672e  xor     rax, rsp
0x180016731  mov     [rbp+210h+var_40], rax
0x180016738  mov     rax, [rbp+210h+arg_20]
0x18001673f  mov     r15, r8
0x180016742  mov     [rbp+210h+var_280], rax
0x180016746  mov     rsi, rdx
0x180016749  mov     rax, [rdx]
0x18001674c  mov     [rbp+210h+var_260], rcx
0x180016750  mov     rcx, rdx
0x180016753  mov     rax, [rax+18h]
0x180016757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001675c  mov     rcx, [rsi]
0x18001675f  mov     r14, rax
0x180016762  mov     [rbp+210h+var_288], rax
0x180016766  mov     rax, [rcx+20h]
0x18001676a  mov     rcx, rsi
0x18001676d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016772  xor     ebx, ebx
0x180016774  lea     rdx, [rbp+210h+var_168]
0x18001677b  lea     rcx, [rbp+210h+var_1A0]
0x18001677f  mov     [rsp+310h+var_2BC], ebx
0x180016783  mov     rdi, rax
0x180016786  lea     r8d, [rbx+20h]
0x18001678a  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180016790  mov     rcx, [rsi]
0x180016793  mov     rax, [rcx+0D0h]
0x18001679a  mov     rcx, rsi
0x18001679d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167a2  mov     rcx, [rsi]
0x1800167a5  mov     r12, rax
0x1800167a8  mov     rax, [rcx+110h]
0x1800167af  mov     rcx, rsi
0x1800167b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167b7  mov     r8, rax
0x1800167ba  lea     rdx, [rsp+310h+var_2B0]
0x1800167bf  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x1800167c6  xorps   xmm0, xmm0
0x1800167c9  mov     qword ptr [rsp+310h+var_2B0], rax
0x1800167ce  movdqu  [rsp+310h+var_2B0+8], xmm0
0x1800167d4  mov     rcx, [r8]
0x1800167d7  mov     rax, [rcx]
0x1800167da  mov     rcx, r8
0x1800167dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167e2  lea     r13d, [rbx+2]
0x1800167e6  test    eax, eax
0x1800167e8  js      loc_1800168E6
0x1800167ee  cmp     dword ptr [rsp+310h+var_2A0], ebx
0x1800167f2  jz      loc_1800168E6
0x1800167f8  mov     rax, [r12]
0x1800167fc  mov     rcx, r12
0x1800167ff  mov     rax, [rax+58h]
0x180016803  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016808  mov     rcx, [rsi]
0x18001680b  mov     rbx, rax
0x18001680e  mov     rax, [rcx+110h]
0x180016815  mov     rcx, rsi
0x180016818  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001681d  mov     rcx, rax
0x180016820  mov     [rbp+210h+var_238], 0Fh
0x180016828  xor     eax, eax
0x18001682a  mov     [rbp+210h+var_208], r13d
0x18001682e  mov     [rbp+210h+var_248], rax
0x180016832  xor     edx, edx
0x180016834  mov     [rbp+210h+var_204], rax
0x180016838  xorps   xmm0, xmm0
0x18001683b  mov     [rbp+210h+var_1FC], eax
0x18001683e  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180016845  mov     [rbp+210h+var_250], rax
0x180016849  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISGeneralEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISGeneralEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x180016850  mov     [rbp+210h+var_240], rax
0x180016854  lea     rax, aGeneralDavHand; "GENERAL_DAV_HANDLER"
0x18001685b  mov     [rbp+210h+var_230], rax
0x18001685f  lea     eax, [rdx+1]
0x180016862  mov     [rbp+210h+var_228], rax
0x180016866  mov     [rbp+210h+var_20C], eax
0x180016869  lea     rax, aContextid; "ContextId"
0x180016870  mov     [rbp+210h+var_1F0], rax
0x180016874  lea     rax, aFilename; "FileName"
0x18001687b  mov     [rbp+210h+var_1C8], rax
0x18001687f  movdqa  [rbp+210h+var_220], xmm0
0x180016884  mov     [rbp+210h+var_210], edx
0x180016887  mov     [rbp+210h+var_1E8], 48h ; 'H'
0x18001688e  mov     [rbp+210h+var_1E0], rdx
0x180016892  mov     [rbp+210h+var_1D8], 10h
0x180016899  mov     [rbp+210h+String], rdx
0x18001689d  mov     [rbp+210h+var_1C0], 1Fh
0x1800168a4  mov     [rbp+210h+var_1B8], rbx
0x1800168a8  test    rbx, rbx
0x1800168ab  jnz     short loc_1800168B1
0x1800168ad  mov     eax, ebx
0x1800168af  jmp     short loc_1800168C7
0x1800168b1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800168b5  inc     rax
0x1800168b8  cmp     [rbx+rax*2], dx
0x1800168bc  jnz     short loc_1800168B5
0x1800168be  lea     eax, ds:2[rax*2]
0x1800168c5  xor     ebx, ebx
0x1800168c7  mov     [rbp+210h+var_1B0], eax
0x1800168ca  lea     rdx, [rbp+210h+var_250]
0x1800168ce  lea     rax, [rbp+210h+var_1F0]
0x1800168d2  mov     [rbp+210h+var_1A8], rbx
0x1800168d6  mov     [rbp+210h+var_204+4], rax
0x1800168da  mov     rax, [rcx]
0x1800168dd  mov     rax, [rax+10h]
0x1800168e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168e6  test    byte ptr [r15+118h], 1
0x1800168ee  jnz     short loc_18001693A
0x1800168f0  mov     rax, [rdi]
0x1800168f3  mov     rcx, rdi
0x1800168f6  mov     rax, [rax+8]
0x1800168fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168ff  mov     dword ptr [rsp+310h+var_2E0], ebx
0x180016903  lea     r8, aForbidden; "Forbidden"
0x18001690a  mov     [rsp+310h+var_2E8], rbx
0x18001690f  mov     r9d, r13d
0x180016912  mov     dword ptr [rsp+310h+var_2F0], 80070005h
0x18001691a  mov     edx, 193h
0x18001691f  mov     [rax+218h], bx
0x180016926  mov     rcx, rdi
0x180016929  mov     rax, [rdi]
0x18001692c  mov     rax, [rax+18h]
0x180016930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016935  jmp     loc_18001742E
0x18001693a  mov     rax, [r12]
0x18001693e  mov     rcx, r12
0x180016941  mov     rax, [rax+38h]
0x180016945  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001694a  mov     rax, [r14]
0x18001694d  mov     rcx, r14
0x180016950  mov     rax, [rax+8]
0x180016954  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016959  mov     ecx, [rax+24h]
0x18001695c  sub     ecx, 4
0x18001695f  cmp     ecx, 1
0x180016962  jbe     short loc_1800169D4
0x180016964  mov     rax, [rdi]
0x180016967  mov     rcx, rdi
0x18001696a  mov     rax, [rax+8]
0x18001696e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016973  mov     dword ptr [rsp+310h+var_2E0], ebx
0x180016977  lea     r8, aMethodNotAllow; "Method Not Allowed"
0x18001697e  xor     r9d, r9d
0x180016981  mov     [rsp+310h+var_2E8], rbx
0x180016986  mov     edx, 195h
0x18001698b  mov     dword ptr [rsp+310h+var_2F0], 80070001h
0x180016993  mov     [rax+218h], bx
0x18001699a  mov     rcx, rdi
0x18001699d  mov     rax, [rdi]
0x1800169a0  mov     rax, [rax+18h]
0x1800169a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169a9  mov     rax, [rdi]
0x1800169ac  mov     rcx, rdi
0x1800169af  mov     rax, [rax+8]
0x1800169b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169b8  lea     rcx, aGetHeadOptions; "GET, HEAD, OPTIONS, TRACE"
0x1800169bf  mov     [rax+0E0h], rcx
0x1800169c6  mov     word ptr [rax+0D8h], 19h
0x1800169cf  jmp     loc_18001742E
0x1800169d4  mov     rax, [r14]
0x1800169d7  xor     r8d, r8d
0x1800169da  mov     rcx, r14
0x1800169dd  mov     rax, [rax+10h]
0x1800169e1  lea     edx, [r8+1Ah]
0x1800169e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169ea  test    rax, rax
0x1800169ed  jz      short loc_180016A1F
0x1800169ef  mov     rax, [rdi]
0x1800169f2  mov     rcx, rdi
0x1800169f5  mov     rax, [rax+8]
0x1800169f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169fe  mov     dword ptr [rsp+310h+var_2E0], ebx
0x180016a02  lea     r8, aExpectationFai; "Expectation Failed"
0x180016a09  mov     [rsp+310h+var_2E8], rbx
0x180016a0e  xor     r9d, r9d
0x180016a11  mov     dword ptr [rsp+310h+var_2F0], ebx
0x180016a15  mov     edx, 1A1h
0x180016a1a  jmp     loc_18001691F
0x180016a1f  mov     rax, [rsi]
0x180016a22  xor     edx, edx
0x180016a24  mov     rcx, rsi
0x180016a27  mov     [rsp+310h+var_2C0], ebx
0x180016a2b  mov     rax, [rax+0B8h]
0x180016a32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a37  mov     edx, 2Eh ; '.'; Ch
0x180016a3c  mov     [rbp+210h+var_278], rax
0x180016a40  mov     rcx, rax; Str
0x180016a43  call    cs:__imp_wcsrchr
0x180016a49  mov     rcx, [rsi]
0x180016a4c  lea     r13, Src
0x180016a53  test    rax, rax
0x180016a56  cmovnz  r13, rax
0x180016a5a  mov     rax, [rcx+98h]
0x180016a61  mov     rcx, rsi
0x180016a64  mov     [rbp+210h+var_270], r13
0x180016a68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a6d  mov     rdx, rax
0x180016a70  mov     rcx, [rax]
0x180016a73  mov     rax, [rcx]
0x180016a76  mov     rcx, rdx
0x180016a79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a7e  mov     rdx, cs:?g_pStaticFileModuleContext@@3PEAXEA; void * g_pStaticFileModuleContext
0x180016a85  mov     r8, rax
0x180016a88  mov     [rbp+210h+var_268], rax
0x180016a8c  mov     rcx, [rax]
0x180016a8f  mov     rax, [rcx]
0x180016a92  mov     rcx, r8
0x180016a95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a9a  mov     rbx, rax
0x180016a9d  test    rax, rax
0x180016aa0  jz      short loc_180016B12
0x180016aa2  lea     rcx, [rax+60h]
0x180016aa6  mov     rdx, r13
0x180016aa9  call    cs:__imp_?EqualsNoCase@STRU@@QEBA_NPEBG@Z; STRU::EqualsNoCase(ushort const *)
0x180016aaf  test    al, al
0x180016ab1  jz      short loc_180016B12
0x180016ab3  mov     r13d, [rbx+0D8h]
0x180016aba  test    r13d, r13d
0x180016abd  jz      short loc_180016AD7
0x180016abf  mov     rdx, [rbx+28h]
0x180016ac3  lea     rcx, [rbp+210h+var_1A0]
0x180016ac7  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180016acd  mov     ebx, eax
0x180016acf  test    eax, eax
0x180016ad1  js      loc_180017472
0x180016ad7  xor     ebx, ebx
0x180016ad9  cmp     [r15+38h], ebx
0x180016add  jz      loc_180016D92
0x180016ae3  mov     rax, [rdi]
0x180016ae6  mov     rcx, rdi
0x180016ae9  mov     rax, [rax+8]
0x180016aed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016af2  cmp     [rax+40h], rbx
0x180016af6  jnz     loc_180016D68
0x180016afc  mov     rcx, [r15+28h]
0x180016b00  mov     [rax+40h], rcx
0x180016b04  movzx   ecx, word ptr [r15+38h]
0x180016b09  mov     [rax+38h], cx
0x180016b0d  jmp     loc_180016D92
0x180016b12  mov     rdx, [rbp+210h+var_278]; unsigned __int16 *
0x180016b16  lea     rax, [rsp+310h+var_2B4]
0x180016b1b  lea     r9, [rsp+310h+var_2BC]; int *
0x180016b20  mov     [rsp+310h+var_2F0], rax; int *
0x180016b25  lea     r8, [rbp+210h+var_1A0]; struct STRA *
0x180016b29  mov     [rsp+310h+var_2B4], 0
0x180016b31  mov     rcx, r15; this
0x180016b34  call    ?SelectMimeMappingForFileExt@STATIC_META_STORED_CONTEXT@@QEAAJPEBGPEAVSTRA@@PEAH2@Z; STATIC_META_STORED_CONTEXT::SelectMimeMappingForFileExt(ushort const *,STRA *,int *,int *)
0x180016b39  mov     ebx, eax
0x180016b3b  test    eax, eax
0x180016b3d  js      loc_180017472
0x180016b43  mov     rax, [rbp+210h+var_280]
0x180016b47  xor     ebx, ebx
0x180016b49  mov     r13d, [rsp+310h+var_2BC]
0x180016b4e  test    rax, rax
0x180016b51  jz      short loc_180016B7A
0x180016b53  test    r13d, r13d
0x180016b56  jnz     short loc_180016B76
0x180016b58  mov     rdx, [rax+20h]
0x180016b5c  lea     rcx, [rbp+210h+var_1A0]
0x180016b60  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180016b66  mov     ebx, eax
0x180016b68  test    eax, eax
0x180016b6a  js      loc_180017472
0x180016b70  xor     ebx, ebx
0x180016b72  lea     r13d, [rbx+1]
0x180016b76  mov     eax, ebx
0x180016b78  jmp     short loc_180016B7E
0x180016b7a  mov     eax, [rsp+310h+var_2B4]
0x180016b7e  test    r13d, r13d
0x180016b81  jz      short loc_180016B8B
0x180016b83  test    eax, eax
0x180016b85  jz      loc_180016C91
0x180016b8b  xor     edx, edx; Val
0x180016b8d  lea     rcx, [rbp+210h+var_140]; void *
0x180016b94  mov     r8d, 100h; Size
0x180016b9a  call    memset_0
0x180016b9f  mov     r8d, 80h
0x180016ba5  lea     rdx, [rbp+210h+var_140]
0x180016bac  lea     rcx, [rbp+210h+var_1F0]
0x180016bb0  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180016bb6  mov     rax, [rsi]
0x180016bb9  xor     edx, edx
0x180016bbb  mov     rcx, rsi
0x180016bbe  mov     rax, [rax+0B0h]
0x180016bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016bca  mov     rdx, rax
0x180016bcd  lea     rcx, [rbp+210h+var_1F0]
0x180016bd1  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180016bd7  mov     ebx, eax
0x180016bd9  test    eax, eax
  ... truncated ...
```
