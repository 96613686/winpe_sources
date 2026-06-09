# COPY_MOVE_BASE_HANDLER::Execute(AUTO_IMPERSONATE *)

- ea: `0x180002740`
- end: `0x180002db7`
- name: `?Execute@COPY_MOVE_BASE_HANDLER@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVAUTO_IMPERSONATE@@@Z`
- size: `1655`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002740`
- `0x180002e60`
- `0x180002f04`
- `0x1800033d4`
- `0x180003634`
- `0x1800036a4`
- `0x180003860`
- `0x1800056ac`
- `0x1800058e4`
- `0x180005a5c`
- `0x180006ec8`
- `0x18000741c`
- `0x180015204`
- `0x180019d58`
- `0x18001a914`
- `0x18001a9f8`
- `0x18001b018`
- `0x180020614`
- `0x1800206ec`
- `0x180021248`
- `0x180022520`
- `0x1800225b0`
- `0x180023010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800029a8`
- `msvcrt!_wcsicmp` at `0x1800029a8`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800027c7`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800027c7`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800029f0`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800029f0`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000277e`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002788`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000277e`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002788`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002880`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000288b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002d81`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002d8c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002880`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000288b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002d81`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002d8c`

## string_xrefs

- `0x180002cad`: `Created`
- `0x180002d28`: `Cannot Perform Overlapping Copy or Move`
- `0x180002a31`: `Cannot Copy or Move Collection To Non-Collection or Vice-Versa`
- `0x1800029c5`: `Cannot Copy or Move Resource To Itself`
- `0x180002979`: `Cannot map URI path to physical path`

## pseudocode

```c
__int64 __fastcall COPY_MOVE_BASE_HANDLER::Execute(__int64 a1, __int64 a2)
{
  __int64 v4; // rax
  struct IHttpContext *v5; // rdx
  int v6; // eax
  __int64 v7; // rdx
  int ConstrainedDepth; // eax
  unsigned int v9; // esi
  unsigned __int16 v10; // dx
  unsigned __int16 v11; // r9
  const char *v12; // r8
  unsigned __int16 v13; // r9
  int UriPathAccessPolicy; // eax
  struct IHttpContext *v16; // rcx
  unsigned int v17; // esi
  unsigned __int16 *v18; // rbx
  __int64 v19; // rax
  int v20; // r14d
  unsigned __int16 *v21; // rbx
  __int64 v22; // rax
  int v23; // edx
  DAV_BASE_HANDLER *v24; // rcx
  __int64 v25; // rax
  const wchar_t *v26; // rdx
  DWORD FileAttributesW; // eax
  int v28; // ecx
  int v29; // eax
  bool v30; // zf
  int v31; // eax
  int v32; // eax
  int IsSlashTerminated; // eax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rdx
  int v37; // r15d
  int v38; // ecx
  int v39; // eax
  int v40; // ebx
  struct LOCK_SET *v41; // r14
  int v42; // r15d
  struct IHttpServer *v43; // r15
  __int64 *v44; // rbx
  wchar_t *v45; // r12
  unsigned __int16 *v46; // r13
  int v47; // r14d
  __int64 v48; // rax
  __int64 (*v49)(void); // rax
  __int64 v50; // rax
  __int64 v51; // rdx
  const char *v52; // r8
  int v53; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v54; // [rsp+54h] [rbp-ACh] BYREF
  int v55; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v56[32]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v57; // [rsp+80h] [rbp-80h]
  unsigned int v58; // [rsp+90h] [rbp-70h]
  _BYTE v59[32]; // [rsp+98h] [rbp-68h] BYREF
  wchar_t *String1; // [rsp+B8h] [rbp-48h]
  _BYTE v61[5008]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v62[5008]; // [rsp+1460h] [rbp+1360h] BYREF

  STRU::STRU((STRU *)v56);
  STRU::STRU((STRU *)v59);
  v55 = 0;
  v53 = 1;
  v54 = 0;
  LOCK_SET::LOCK_SET((LOCK_SET *)v62);
  LOCK_SET::LOCK_SET((LOCK_SET *)v61);
  if ( (g_dwDebugFlags & 0x40000000) != 0 )
    DebugBreak();
  v4 = *(_QWORD *)(a1 + 24);
  v5 = *(struct IHttpContext **)(a1 + 8);
  *(_QWORD *)(a1 + 408) = a2;
  XML_RESPONDER::Initialize((XML_RESPONDER *)(a1 + 296), v5, (*(_DWORD *)(v4 + 8) >> 2) & 1);
  v6 = *(_DWORD *)(a1 + 208);
  if ( v6 == -1 || (v7 = 1, (v6 & 0x10) == 0) )
    v7 = 0;
  ConstrainedDepth = GetConstrainedDepth(*(_QWORD *)(a1 + 8), v7);
  *(_DWORD *)(a1 + 400) = ConstrainedDepth;
  if ( ConstrainedDepth == -1 )
  {
    v9 = 2;
    v10 = 400;
    v11 = 2;
    v12 = "Bad Request";
LABEL_78:
    v24 = (DAV_BASE_HANDLER *)a1;
    goto LABEL_79;
  }
  if ( ValidateDestinationHeader(*(struct IHttpContext **)(a1 + 8), (struct STRU *)v56) < 0 )
  {
    v13 = 1;
LABEL_10:
    DAV_BASE_HANDLER::FinishRequest((DAV_BASE_HANDLER *)a1, 0x190u, "Bad Request", v13, 0);
LABEL_11:
    LOCK_SET::~LOCK_SET((LOCK_SET *)v61);
    LOCK_SET::~LOCK_SET((LOCK_SET *)v62);
    STRU::~STRU((STRU *)v59);
    STRU::~STRU((STRU *)v56);
    return 2;
  }
  if ( (int)ValidateOverwriteHeader(*(struct IHttpContext **)(a1 + 8), &v53) < 0 )
  {
    v13 = 4;
    goto LABEL_10;
  }
  UriPathAccessPolicy = GetUriPathAccessPolicy(*(struct IHttpContext **)(a1 + 8), v57, &v54);
  v16 = *(struct IHttpContext **)(a1 + 8);
  v17 = UriPathAccessPolicy;
  if ( UriPathAccessPolicy < 0 )
  {
    v18 = v57;
    v19 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v16 + 272LL))(v16);
    (*(void (__fastcall **)(__int64, const wchar_t *, unsigned __int16 *, _QWORD, char))(*(_QWORD *)v19 + 32LL))(
      v19,
      L"Cannot query authoring rules",
      v18,
      v17,
      3);
    DAV_BASE_HANDLER::MapAndHandleError((DAV_BASE_HANDLER *)a1, v17);
    goto LABEL_11;
  }
  v9 = 2;
  if ( (v54 & 2) == 0 )
  {
    DAV_TRACE::TraceAuthoringRulesDenied(v16, -2147024891, v57, 2u, v54);
    v11 = 3;
LABEL_77:
    v12 = "Forbidden";
    v10 = 403;
    goto LABEL_78;
  }
  v20 = MapUriPathToPhysicalPath(v16, v57, (struct STRU *)v59);
  if ( v20 < 0 )
  {
    v21 = v57;
    v22 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 272LL))(*(_QWORD *)(a1 + 8));
    (*(void (__fastcall **)(__int64, const wchar_t *, unsigned __int16 *, _QWORD, char))(*(_QWORD *)v22 + 32LL))(
      v22,
      L"Cannot map URI path to physical path",
      v21,
      (unsigned int)v20,
      3);
    v23 = v20;
LABEL_20:
    v24 = (DAV_BASE_HANDLER *)a1;
LABEL_74:
    DAV_BASE_HANDLER::MapAndHandleError(v24, v23);
    goto LABEL_80;
  }
  if ( !_wcsicmp(String1, *(const wchar_t **)(a1 + 184)) )
  {
    v25 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 272LL))(*(_QWORD *)(a1 + 8));
    v26 = L"Cannot Copy or Move Resource To Itself";
LABEL_76:
    (*(void (__fastcall **)(__int64, const wchar_t *, _QWORD, _QWORD, char))(*(_QWORD *)v25 + 32LL))(v25, v26, 0, 0, 3);
    v11 = 0;
    goto LABEL_77;
  }
  if ( !v53 && (unsigned int)DoesFileOrDirExist(*(struct IBaseFileSystem **)(a1 + 240), String1) )
  {
    FileAttributesW = GetFileAttributesW(String1);
    if ( FileAttributesW == -1 || (v28 = 1, (FileAttributesW & 0x10) == 0) )
      v28 = 0;
    v29 = *(_DWORD *)(a1 + 208);
    if ( v29 == -1 || (v30 = (v29 & 0x10) == 0, v31 = 1, v30) )
      v31 = 0;
    if ( v28 != v31 )
    {
      v25 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 272LL))(*(_QWORD *)(a1 + 8));
      v26 = L"Cannot Copy or Move Collection To Non-Collection or Vice-Versa";
      goto LABEL_76;
    }
  }
  v32 = *(_DWORD *)(a1 + 208);
  if ( v32 != -1 && (v32 & 0x10) != 0 )
  {
    IsSlashTerminated = EnsureUriPathIsSlashTerminated((struct STRU *)v56);
    if ( IsSlashTerminated < 0 )
    {
      v23 = IsSlashTerminated;
      goto LABEL_20;
    }
  }
  if ( UriPrefixCompare(v57, v58, *(const unsigned __int16 **)(a1 + 72), *(_DWORD *)(a1 + 88))
    || UriPrefixCompare(*(const unsigned __int16 **)(a1 + 72), *(_DWORD *)(a1 + 88), v57, v58) )
  {
    v25 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 272LL))(*(_QWORD *)(a1 + 8));
    v26 = L"Cannot Perform Overlapping Copy or Move";
    goto LABEL_76;
  }
  if ( (unsigned int)DAV_BASE_HANDLER::ValidateHttpIfHeaders(
                       (DAV_BASE_HANDLER *)a1,
                       *(struct IHttpFileInfo **)(a1 + 32)) )
  {
    v34 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 24LL))(*(_QWORD *)(a1 + 8));
    v35 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v34 + 8LL))(v34);
    v36 = *(_QWORD *)(a1 + 24);
    v37 = *(_DWORD *)(v35 + 36);
    v38 = *(_DWORD *)(v36 + 56);
    if ( v37 != 12 || (v39 = 1, !v38) )
      v39 = 0;
    v40 = HandleDavIfAndLocks(
            *(struct IHttpContext **)(a1 + 8),
            *(struct DAV_LOCK_STORE **)(v36 + 3328),
            *(const unsigned __int16 **)(a1 + 72),
            (struct LOCK_SET *)v62,
            v39,
            v57,
            (struct LOCK_SET *)v61,
            v38,
            3u);
    if ( v40 < 0 )
      goto LABEL_71;
    v41 = (struct LOCK_SET *)v62;
    if ( v37 == 13 )
      v41 = 0;
    if ( (unsigned int)LOCK_SET::TestLocks((LOCK_SET *)v61) )
    {
      v40 = 0;
      v42 = 0;
    }
    else
    {
      v40 = DAV_BASE_HANDLER::SendLockTokenSubmittedResponse((DAV_BASE_HANDLER *)a1, (struct LOCK_SET *)v61);
      v42 = 1;
      if ( v40 < 0 )
        goto LABEL_55;
    }
    if ( !v41 )
      goto LABEL_54;
    if ( !(unsigned int)LOCK_SET::TestLocks(v41) )
    {
      v40 = DAV_BASE_HANDLER::SendLockTokenSubmittedResponse((DAV_BASE_HANDLER *)a1, v41);
      v42 = 1;
    }
    if ( v40 >= 0 )
    {
LABEL_54:
      if ( v42 )
        goto LABEL_80;
    }
LABEL_55:
    if ( v40 == 1 )
      goto LABEL_80;
    if ( v40 >= 0 )
    {
      v43 = g_pGlobalInfo;
      (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 24LL))(g_pGlobalInfo);
      v44 = *(__int64 **)(a1 + 240);
      v45 = String1;
      v46 = v57;
      v47 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v44 + 8))(v44, -1);
      if ( v47 >= 0 )
        v47 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, wchar_t *, _QWORD, int *))(*(_QWORD *)a1 + 32LL))(
                a1,
                v46,
                v45,
                (unsigned int)v53,
                &v55);
      v48 = *v44;
      if ( v47 < 0 )
        (*(void (__fastcall **)(__int64 *))(v48 + 24))(v44);
      else
        v47 = (*(__int64 (__fastcall **)(__int64 *))(v48 + 16))(v44);
      v40 = v47;
      (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)v43 + 32LL))(v43);
      if ( v47 >= 0 )
      {
        if ( *(_DWORD *)(a1 + 392) )
        {
          if ( (int)XML_RESPONDER::FinishXmlMultistatusResponse((XML_RESPONDER *)(a1 + 296)) < 0 )
          {
            v11 = 0;
            v12 = "Internal Server Error";
            v10 = 500;
            goto LABEL_78;
          }
        }
        else
        {
          v49 = *(__int64 (**)(void))(**(_QWORD **)(a1 + 8) + 32LL);
          if ( v55 )
          {
            v50 = v49();
            v51 = 204;
            v52 = "No Content";
          }
          else
          {
            v50 = v49();
            v51 = 201;
            v52 = "Created";
          }
          (*(void (__fastcall **)(__int64, __int64, const char *, _QWORD, _DWORD, _QWORD, _DWORD))(*(_QWORD *)v50 + 24LL))(
            v50,
            v51,
            v52,
            0,
            0,
            0,
            0);
        }
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 200LL))(*(_QWORD *)(a1 + 8));
        v9 = 0;
        goto LABEL_80;
      }
    }
LABEL_71:
    v24 = (DAV_BASE_HANDLER *)a1;
    if ( v40 == -2147024893 )
    {
      v11 = 0;
      v12 = "Conflict";
      v10 = 409;
LABEL_79:
      DAV_BASE_HANDLER::FinishRequest(v24, v10, v12, v11, 0);
      goto LABEL_80;
    }
    v23 = v40;
    goto LABEL_74;
  }
LABEL_80:
  LOCK_SET::~LOCK_SET((LOCK_SET *)v61);
  LOCK_SET::~LOCK_SET((LOCK_SET *)v62);
  STRU::~STRU((STRU *)v59);
  STRU::~STRU((STRU *)v56);
  return v9;
}

```

## disassembly

```asm
0x180002740  push    rbp
0x180002742  push    rbx
0x180002743  push    rsi
0x180002744  push    rdi
0x180002745  push    r12
0x180002747  push    r13
0x180002749  push    r14
0x18000274b  push    r15
0x18000274d  lea     rbp, [rsp-2708h]
0x180002755  mov     eax, 2808h
0x18000275a  call    _alloca_probe
0x18000275f  sub     rsp, rax
0x180002762  mov     rax, cs:__security_cookie
0x180002769  xor     rax, rsp
0x18000276c  mov     [rbp+2740h+var_50], rax
0x180002773  mov     rdi, rcx
0x180002776  mov     rbx, rdx
0x180002779  lea     rcx, [rsp+2840h+var_27E0]
0x18000277e  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180002784  lea     rcx, [rbp+2740h+var_27A8]
0x180002788  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000278e  xor     r12d, r12d
0x180002791  lea     rcx, [rbp+2740h+var_13E0]; this
0x180002798  mov     r13d, 1
0x18000279e  mov     [rsp+2840h+var_27E8], r12d
0x1800027a3  mov     [rsp+2840h+var_27F0], r13d
0x1800027a8  mov     [rsp+2840h+var_27EC], r12d
0x1800027ad  call    ??0LOCK_SET@@QEAA@XZ; LOCK_SET::LOCK_SET(void)
0x1800027b2  lea     rcx, [rbp+2740h+var_2770]; this
0x1800027b6  call    ??0LOCK_SET@@QEAA@XZ; LOCK_SET::LOCK_SET(void)
0x1800027bb  test    cs:g_dwDebugFlags, 40000000h
0x1800027c5  jz      short loc_1800027CD
0x1800027c7  call    cs:__imp_DebugBreak
0x1800027cd  mov     rax, [rdi+18h]
0x1800027d1  lea     rcx, [rdi+128h]; this
0x1800027d8  mov     rdx, [rdi+8]; struct IHttpContext *
0x1800027dc  mov     [rdi+198h], rbx
0x1800027e3  mov     r8d, [rax+8]
0x1800027e7  shr     r8d, 2
0x1800027eb  and     r8d, r13d; int
0x1800027ee  call    ?Initialize@XML_RESPONDER@@QEAAXPEAVIHttpContext@@H@Z; XML_RESPONDER::Initialize(IHttpContext *,int)
0x1800027f3  mov     eax, [rdi+0D0h]
0x1800027f9  or      r15d, 0FFFFFFFFh
0x1800027fd  mov     bl, 10h
0x1800027ff  cmp     eax, r15d
0x180002802  jz      short loc_18000280B
0x180002804  mov     edx, r13d
0x180002807  test    bl, al
0x180002809  jnz     short loc_18000280E
0x18000280b  mov     edx, r12d
0x18000280e  mov     rcx, [rdi+8]
0x180002812  call    ?GetConstrainedDepth@@YA?AW4DAV_DEPTH@@PEAVIHttpContext@@H@Z; GetConstrainedDepth(IHttpContext *,int)
0x180002817  mov     [rdi+190h], eax
0x18000281d  cmp     eax, 0FFFFFFFFh
0x180002820  jnz     short loc_180002839
0x180002822  lea     esi, [rax+3]
0x180002825  mov     edx, 190h
0x18000282a  mov     r9d, esi
0x18000282d  lea     r8, aBadRequest; "Bad Request"
0x180002834  jmp     loc_180002D5B
0x180002839  mov     rcx, [rdi+8]; struct IHttpContext *
0x18000283d  lea     rdx, [rsp+2840h+var_27E0]; struct STRU *
0x180002842  call    ?ValidateDestinationHeader@@YAJPEAVIHttpContext@@PEAVSTRU@@@Z; ValidateDestinationHeader(IHttpContext *,STRU *)
0x180002847  test    eax, eax
0x180002849  jns     short loc_18000289B
0x18000284b  mov     r9d, r13d; unsigned __int16
0x18000284e  mov     edx, 190h; unsigned __int16
0x180002853  mov     [rsp+2840h+var_2820], r12d; int
0x180002858  lea     r8, aBadRequest; "Bad Request"
0x18000285f  mov     rcx, rdi; this
0x180002862  call    ?FinishRequest@DAV_BASE_HANDLER@@QEAAXGPEBDGJ@Z; DAV_BASE_HANDLER::FinishRequest(ushort,char const *,ushort,long)
0x180002867  lea     rcx, [rbp+2740h+var_2770]; this
0x18000286b  call    ??1LOCK_SET@@UEAA@XZ; LOCK_SET::~LOCK_SET(void)
0x180002870  lea     rcx, [rbp+2740h+var_13E0]; this
0x180002877  call    ??1LOCK_SET@@UEAA@XZ; LOCK_SET::~LOCK_SET(void)
0x18000287c  lea     rcx, [rbp+2740h+var_27A8]
0x180002880  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002886  lea     rcx, [rsp+2840h+var_27E0]
0x18000288b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002891  mov     eax, 2
0x180002896  jmp     loc_180002D94
0x18000289b  mov     rcx, [rdi+8]; struct IHttpContext *
0x18000289f  lea     rdx, [rsp+2840h+var_27F0]; int *
0x1800028a4  call    ?ValidateOverwriteHeader@@YAJPEAVIHttpContext@@PEAH@Z; ValidateOverwriteHeader(IHttpContext *,int *)
0x1800028a9  test    eax, eax
0x1800028ab  jns     short loc_1800028B5
0x1800028ad  mov     r9d, 4
0x1800028b3  jmp     short loc_18000284E
0x1800028b5  mov     rdx, [rbp+2740h+var_27C0]; unsigned __int16 *
0x1800028b9  lea     r8, [rsp+2840h+var_27EC]; unsigned int *
0x1800028be  mov     rcx, [rdi+8]; struct IHttpContext *
0x1800028c2  call    ?GetUriPathAccessPolicy@@YAJPEAVIHttpContext@@PEBGPEAK@Z; GetUriPathAccessPolicy(IHttpContext *,ushort const *,ulong *)
0x1800028c7  mov     rcx, [rdi+8]; struct IHttpContext *
0x1800028cb  mov     esi, eax
0x1800028cd  test    eax, eax
0x1800028cf  jns     short loc_180002917
0x1800028d1  mov     rdx, [rcx]
0x1800028d4  mov     rbx, [rbp+2740h+var_27C0]
0x1800028d8  mov     rax, [rdx+110h]
0x1800028df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028e4  mov     r10, rax
0x1800028e7  mov     byte ptr [rsp+2840h+var_2820], 3
0x1800028ec  mov     r9d, esi
0x1800028ef  lea     rdx, aCannotQueryAut; "Cannot query authoring rules"
0x1800028f6  mov     r8, rbx
0x1800028f9  mov     rcx, [rax]
0x1800028fc  mov     rax, [rcx+20h]
0x180002900  mov     rcx, r10
0x180002903  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002908  mov     edx, esi; int
0x18000290a  mov     rcx, rdi; this
0x18000290d  call    ?MapAndHandleError@DAV_BASE_HANDLER@@QEAAXJ@Z; DAV_BASE_HANDLER::MapAndHandleError(long)
0x180002912  jmp     loc_180002867
0x180002917  mov     eax, [rsp+2840h+var_27EC]
0x18000291b  mov     esi, 2
0x180002920  test    sil, al
0x180002923  jnz     short loc_180002943
0x180002925  mov     r8, [rbp+2740h+var_27C0]; unsigned __int16 *
0x180002929  mov     r9d, esi; unsigned int
0x18000292c  mov     edx, 80070005h; int
0x180002931  mov     [rsp+2840h+var_2820], eax; unsigned int
0x180002935  call    ?TraceAuthoringRulesDenied@DAV_TRACE@@SAXPEAVIHttpContext@@JPEBGKK@Z; DAV_TRACE::TraceAuthoringRulesDenied(IHttpContext *,long,ushort const *,ulong,ulong)
0x18000293a  lea     r9d, [rsi+1]
0x18000293e  jmp     loc_180002D4F
0x180002943  mov     rdx, [rbp+2740h+var_27C0]; unsigned __int16 *
0x180002947  lea     r8, [rbp+2740h+var_27A8]; struct STRU *
0x18000294b  call    ?MapUriPathToPhysicalPath@@YAJPEAVIHttpContext@@PEBGPEAVSTRU@@@Z; MapUriPathToPhysicalPath(IHttpContext *,ushort const *,STRU *)
0x180002950  mov     r14d, eax
0x180002953  test    eax, eax
0x180002955  jns     short loc_18000299D
0x180002957  mov     rcx, [rdi+8]
0x18000295b  mov     rbx, [rbp+2740h+var_27C0]
0x18000295f  mov     rdx, [rcx]
0x180002962  mov     rax, [rdx+110h]
0x180002969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000296e  mov     r10, rax
0x180002971  mov     byte ptr [rsp+2840h+var_2820], 3
0x180002976  mov     r9d, r14d
0x180002979  lea     rdx, aCannotMapUriPa; "Cannot map URI path to physical path"
0x180002980  mov     r8, rbx
0x180002983  mov     rcx, [rax]
0x180002986  mov     rax, [rcx+20h]
0x18000298a  mov     rcx, r10
0x18000298d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002992  mov     edx, r14d
0x180002995  mov     rcx, rdi
0x180002998  jmp     loc_180002D0E
0x18000299d  mov     rdx, [rdi+0B8h]; String2
0x1800029a4  mov     rcx, [rbp+2740h+String1]; String1
0x1800029a8  call    cs:__imp__wcsicmp
0x1800029ae  test    eax, eax
0x1800029b0  jnz     short loc_1800029D1
0x1800029b2  mov     rcx, [rdi+8]
0x1800029b6  mov     rax, [rcx]
0x1800029b9  mov     rax, [rax+110h]
0x1800029c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029c5  lea     rdx, aCannotCopyOrMo; "Cannot Copy or Move Resource To Itself"
0x1800029cc  jmp     loc_180002D2F
0x1800029d1  cmp     [rsp+2840h+var_27F0], r12d
0x1800029d6  jnz     short loc_180002A3D
0x1800029d8  mov     rdx, [rbp+2740h+String1]; unsigned __int16 *
0x1800029dc  mov     rcx, [rdi+0F0h]; struct IBaseFileSystem *
0x1800029e3  call    ?DoesFileOrDirExist@@YAHPEAVIBaseFileSystem@@PEBG@Z; DoesFileOrDirExist(IBaseFileSystem *,ushort const *)
0x1800029e8  test    eax, eax
0x1800029ea  jz      short loc_180002A3D
0x1800029ec  mov     rcx, [rbp+2740h+String1]; lpFileName
0x1800029f0  call    cs:__imp_GetFileAttributesW
0x1800029f6  cmp     eax, r15d
0x1800029f9  jz      short loc_180002A02
0x1800029fb  mov     ecx, r13d
0x1800029fe  test    bl, al
0x180002a00  jnz     short loc_180002A05
0x180002a02  mov     ecx, r12d
0x180002a05  mov     eax, [rdi+0D0h]
0x180002a0b  cmp     eax, r15d
0x180002a0e  jz      short loc_180002A17
0x180002a10  test    bl, al
0x180002a12  mov     eax, r13d
0x180002a15  jnz     short loc_180002A1A
0x180002a17  mov     eax, r12d
0x180002a1a  cmp     ecx, eax
0x180002a1c  jz      short loc_180002A3D
0x180002a1e  mov     rcx, [rdi+8]
0x180002a22  mov     rax, [rcx]
0x180002a25  mov     rax, [rax+110h]
0x180002a2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a31  lea     rdx, aCannotCopyOrMo_0; "Cannot Copy or Move Collection To Non-C"...
0x180002a38  jmp     loc_180002D2F
0x180002a3d  mov     eax, [rdi+0D0h]
0x180002a43  cmp     eax, r15d
0x180002a46  jz      short loc_180002A61
0x180002a48  test    bl, al
0x180002a4a  jz      short loc_180002A61
0x180002a4c  lea     rcx, [rsp+2840h+var_27E0]; struct STRU *
0x180002a51  call    ?EnsureUriPathIsSlashTerminated@@YAJPEAVSTRU@@@Z; EnsureUriPathIsSlashTerminated(STRU *)
0x180002a56  test    eax, eax
0x180002a58  jns     short loc_180002A61
0x180002a5a  mov     edx, eax
0x180002a5c  jmp     loc_180002995
0x180002a61  mov     r9d, [rdi+58h]; unsigned int
0x180002a65  mov     r8, [rdi+48h]; unsigned __int16 *
0x180002a69  mov     edx, [rbp+2740h+var_27B0]; unsigned int
0x180002a6c  mov     rcx, [rbp+2740h+var_27C0]; unsigned __int16 *
0x180002a70  call    ?UriPrefixCompare@@YAHPEBGI0I@Z; UriPrefixCompare(ushort const *,uint,ushort const *,uint)
0x180002a75  test    eax, eax
0x180002a77  jnz     loc_180002D15
0x180002a7d  mov     r9d, [rbp+2740h+var_27B0]; unsigned int
0x180002a81  mov     r8, [rbp+2740h+var_27C0]; unsigned __int16 *
0x180002a85  mov     edx, [rdi+58h]; unsigned int
0x180002a88  mov     rcx, [rdi+48h]; unsigned __int16 *
0x180002a8c  call    ?UriPrefixCompare@@YAHPEBGI0I@Z; UriPrefixCompare(ushort const *,uint,ushort const *,uint)
0x180002a91  test    eax, eax
0x180002a93  jnz     loc_180002D15
0x180002a99  mov     rdx, [rdi+20h]; struct IHttpFileInfo *
0x180002a9d  mov     rcx, rdi; this
0x180002aa0  call    ?ValidateHttpIfHeaders@DAV_BASE_HANDLER@@QEAAHPEAVIHttpFileInfo@@@Z; DAV_BASE_HANDLER::ValidateHttpIfHeaders(IHttpFileInfo *)
0x180002aa5  test    eax, eax
0x180002aa7  jz      loc_180002D68
0x180002aad  mov     rcx, [rdi+8]
0x180002ab1  mov     rax, [rcx]
0x180002ab4  mov     rax, [rax+18h]
0x180002ab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002abd  mov     rdx, rax
0x180002ac0  mov     rcx, [rax]
0x180002ac3  mov     rax, [rcx+8]
0x180002ac7  mov     rcx, rdx
0x180002aca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002acf  mov     rdx, [rdi+18h]
0x180002ad3  mov     r8, [rbp+2740h+var_27C0]
0x180002ad7  mov     r15d, [rax+24h]
0x180002adb  mov     ecx, [rdx+38h]
0x180002ade  cmp     r15d, 0Ch
0x180002ae2  jnz     short loc_180002AEB
0x180002ae4  mov     eax, r13d
0x180002ae7  test    ecx, ecx
0x180002ae9  jnz     short loc_180002AEE
0x180002aeb  mov     eax, r12d
0x180002aee  mov     rdx, [rdx+0D00h]; struct DAV_LOCK_STORE *
0x180002af5  lea     r9, [rbp+2740h+var_13E0]; struct LOCK_SET *
0x180002afc  mov     [rsp+2840h+var_2800], 3; unsigned int
0x180002b04  mov     [rsp+2840h+var_2808], ecx; int
0x180002b08  lea     rcx, [rbp+2740h+var_2770]
0x180002b0c  mov     [rsp+2840h+var_2810], rcx; struct LOCK_SET *
0x180002b11  mov     rcx, [rdi+8]; struct IHttpContext *
0x180002b15  mov     [rsp+2840h+var_2818], r8; unsigned __int16 *
0x180002b1a  mov     r8, [rdi+48h]; unsigned __int16 *
0x180002b1e  mov     [rsp+2840h+var_2820], eax; int
0x180002b22  call    ?HandleDavIfAndLocks@@YAJPEAVIHttpContext@@PEAVDAV_LOCK_STORE@@PEBGPEAVLOCK_SET@@H23HK@Z; HandleDavIfAndLocks(IHttpContext *,DAV_LOCK_STORE *,ushort const *,LOCK_SET *,int,ushort const *,LOCK_SET *,int,ulong)
0x180002b27  mov     ebx, eax
0x180002b29  test    eax, eax
0x180002b2b  js      loc_180002CF0
0x180002b31  cmp     r15d, 0Dh
0x180002b35  lea     r14, [rbp+2740h+var_13E0]
0x180002b3c  lea     rcx, [rbp+2740h+var_2770]; this
0x180002b40  cmovz   r14, r12
0x180002b44  call    ?TestLocks@LOCK_SET@@QEAAHXZ; LOCK_SET::TestLocks(void)
0x180002b49  test    eax, eax
0x180002b4b  jnz     short loc_180002B64
0x180002b4d  lea     rdx, [rbp+2740h+var_2770]; struct LOCK_SET *
0x180002b51  mov     rcx, rdi; this
0x180002b54  call    ?SendLockTokenSubmittedResponse@DAV_BASE_HANDLER@@IEAAJPEAVLOCK_SET@@@Z; DAV_BASE_HANDLER::SendLockTokenSubmittedResponse(LOCK_SET *)
0x180002b59  mov     ebx, eax
0x180002b5b  mov     r15d, r13d
0x180002b5e  test    eax, eax
0x180002b60  js      short loc_180002B98
0x180002b62  jmp     short loc_180002B6A
0x180002b64  mov     ebx, r12d
0x180002b67  mov     r15d, r12d
0x180002b6a  test    r14, r14
0x180002b6d  jz      short loc_180002B8F
0x180002b6f  mov     rcx, r14; this
0x180002b72  call    ?TestLocks@LOCK_SET@@QEAAHXZ; LOCK_SET::TestLocks(void)
0x180002b77  test    eax, eax
0x180002b79  jnz     short loc_180002B8B
0x180002b7b  mov     rdx, r14; struct LOCK_SET *
0x180002b7e  mov     rcx, rdi; this
0x180002b81  call    ?SendLockTokenSubmittedResponse@DAV_BASE_HANDLER@@IEAAJPEAVLOCK_SET@@@Z; DAV_BASE_HANDLER::SendLockTokenSubmittedResponse(LOCK_SET *)
0x180002b86  mov     ebx, eax
0x180002b88  mov     r15d, r13d
0x180002b8b  test    ebx, ebx
0x180002b8d  js      short loc_180002B98
0x180002b8f  test    r15d, r15d
0x180002b92  jnz     loc_180002D68
0x180002b98  cmp     ebx, r13d
0x180002b9b  jz      loc_180002D68
0x180002ba1  test    ebx, ebx
0x180002ba3  js      loc_180002CF0
0x180002ba9  mov     r15, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180002bb0  mov     rcx, r15
0x180002bb3  mov     rax, [r15]
0x180002bb6  mov     rax, [rax+18h]
0x180002bba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bbf  mov     rbx, [rdi+0F0h]
0x180002bc6  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180002bca  mov     r12, [rbp+2740h+String1]
0x180002bce  mov     rcx, rbx
0x180002bd1  mov     r13, [rbp+2740h+var_27C0]
0x180002bd5  mov     rax, [rbx]
0x180002bd8  mov     rax, [rax+8]
0x180002bdc  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
