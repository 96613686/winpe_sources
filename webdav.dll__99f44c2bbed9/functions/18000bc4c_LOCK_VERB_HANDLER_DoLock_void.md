# LOCK_VERB_HANDLER::DoLock(void)

- ea: `0x18000bc4c`
- end: `0x18000c2fb`
- name: `?DoLock@LOCK_VERB_HANDLER@@AEAA?AW4REQUEST_NOTIFICATION_STATUS@@XZ`
- size: `1711`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000c7e0`

## callees

- `0x1800033d4`
- `0x180003634`
- `0x180005604`
- `0x18000bc4c`
- `0x180012c54`
- `0x180015038`
- `0x180015134`
- `0x18001519c`
- `0x1800153ac`
- `0x1800155d4`
- `0x18001a0cc`
- `0x18001ad3c`
- `0x18001b2cc`
- `0x18001c550`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000bf98`
- `msvcrt!_wcsicmp` at `0x18000bf98`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000bf5f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000c082`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000bf5f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000c082`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c053`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c053`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c06d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c06d`
- `XmlLite!CreateXmlReader` at `0x18000bcc2`
- `XmlLite!CreateXmlReader` at `0x18000bcc2`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000c105`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000c105`
- `iisutil!PuDbgPrint` at `0x18000c1fc`
- `iisutil!PuDbgPrint` at `0x18000c1fc`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000bfbd`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000bfbd`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000bc87`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000bfa6`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000bfb0`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000bc87`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000bfa6`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000bfb0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000be64`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000c005`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000c00f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000c2d2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000be64`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000c005`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000c00f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000c2d2`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18000c094`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18000c094`

## string_xrefs

- `0x18000c11e`: `Created`
- `0x18000bed0`: `Impersonation Failure`
- `0x18000c0da`: `Lock-Token`
- `0x18000bf8d`: `\web.config`
- `0x18000c1f0`: `Lock token %ws created for URI path %ws\n`

## pseudocode

```c
__int64 __fastcall LOCK_VERB_HANDLER::DoLock(__int64 a1)
{
  __int64 v1; // r12
  int TempFileName; // esi
  __int64 v3; // rdi
  __int64 v4; // rsi
  __int64 v5; // rbx
  int v6; // r14d
  int v7; // r15d
  __int64 v8; // r13
  unsigned int v9; // r12d
  const unsigned __int16 *EffectiveUser; // rax
  int v11; // eax
  unsigned int v12; // r14d
  int v14; // edi
  struct IHttpContext *v15; // rdx
  int v16; // ebx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  const unsigned __int16 *v20; // rbx
  unsigned __int64 v21; // rax
  void *v22; // rax
  signed int LastError; // eax
  __int64 v24; // rax
  __int64 v25; // rax
  const char *v26; // r9
  struct IPubLock *v27; // rdx
  __int64 v28; // rbx
  __int64 v29; // rax
  __int64 v30; // rdi
  __int64 v31; // rbx
  const unsigned __int16 *v32; // rax
  int v33; // [rsp+20h] [rbp-E0h]
  struct IPubLock *v34; // [rsp+60h] [rbp-A0h] BYREF
  BOOL v35; // [rsp+68h] [rbp-98h]
  void *ppvObject; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v37[3]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v38[32]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v39; // [rsp+B0h] [rbp-50h]
  int v40; // [rsp+C0h] [rbp-40h]
  int v41; // [rsp+C8h] [rbp-38h]
  int v42; // [rsp+CCh] [rbp-34h]
  int v43; // [rsp+D0h] [rbp-30h]
  _BYTE v44[32]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 *v45; // [rsp+100h] [rbp+0h]
  unsigned __int16 v46; // [rsp+110h] [rbp+10h]
  _BYTE v47[56]; // [rsp+118h] [rbp+18h] BYREF

  v1 = a1;
  v37[0] = a1;
  v35 = 0;
  STRU::STRU((STRU *)v38);
  v43 = 0;
  v41 = -1;
  v42 = -1;
  *(_WORD *)v39 = 0;
  v40 = 0;
  v34 = 0;
  ppvObject = 0;
  TempFileName = CreateXmlReader(&riid, &ppvObject, 0);
  if ( TempFileName >= 0 )
  {
    TempFileName = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 24LL))(ppvObject, v1 + 360);
    if ( TempFileName >= 0 )
    {
      TempFileName = ParseLock(
                       *(struct IHttpContext **)(v1 + 8),
                       (struct IXmlReader *)ppvObject,
                       (struct DAV_LOCK_REQUEST *)v38);
      v35 = TempFileName < 0;
    }
  }
  if ( ppvObject )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    ppvObject = 0;
  }
  if ( TempFileName >= 0 )
  {
    v3 = *(_QWORD *)(v1 + 5576);
    v4 = *(_QWORD *)(v1 + 560);
    v5 = *(_QWORD *)(*(_QWORD *)(v1 + 24) + 3328LL);
    v6 = v42;
    v7 = v41;
    v8 = v39 & -(__int64)(v43 != 0);
    v9 = *(_DWORD *)(v1 + 552);
    EffectiveUser = GetEffectiveUser(*(struct IHttpContext **)(v37[0] + 8LL));
    v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, const unsigned __int16 *, _QWORD, int, int, __int64, __int64, __int64, struct IPubLock **))(**(_QWORD **)(v5 + 16) + 48LL))(
            *(_QWORD *)(v5 + 16),
            v37[0] + 248LL,
            EffectiveUser,
            v9,
            v7,
            v6,
            v4,
            v3,
            v8,
            &v34);
    v1 = v37[0];
    TempFileName = v11;
  }
  v12 = 2;
  if ( TempFileName == -1917904270
    && (int)XML_RESPONDER::BeginXmlCommon((XML_RESPONDER *)(v1 + 448), "error", 0x1A7u, "Locked Error", 2u) >= 0 )
  {
    v33 = v42;
    if ( (int)XML_RESPONDER::SendXmlNoConflictingLock(v1 + 448, v1 + 568) >= 0
      && (int)XML_RESPONDER::FinishXmlErrorResponse((XML_RESPONDER *)(v1 + 448)) >= 0 )
    {
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v1 + 8) + 200LL))(*(_QWORD *)(v1 + 8));
      v41 = -1;
      v42 = -1;
      v43 = 0;
      *(_WORD *)v39 = 0;
      v40 = 0;
      STRU::~STRU((STRU *)v38);
      return 0;
    }
  }
  if ( TempFileName >= 0 )
  {
    if ( *(_DWORD *)(v1 + 208) == -1 )
    {
      v15 = *(struct IHttpContext **)(v1 + 8);
      LODWORD(v37[0]) = 0;
      v37[1] = 0;
      v16 = AUTO_IMPERSONATE::Impersonate((AUTO_IMPERSONATE *)v37, v15);
      if ( v16 < 0 )
      {
        v17 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v1 + 8) + 272LL))(*(_QWORD *)(v1 + 8));
        LOBYTE(v33) = 3;
        (*(void (__fastcall **)(__int64, const wchar_t *, _QWORD, _QWORD, int))(*(_QWORD *)v17 + 32LL))(
          v17,
          L"Impersonation Failure",
          0,
          (unsigned int)v16,
          v33);
        v18 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v1 + 8) + 32LL))(*(_QWORD *)(v1 + 8));
        *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18) + 536) = 0;
        v19 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v1 + 8) + 32LL))(*(_QWORD *)(v1 + 8));
        (*(void (__fastcall **)(__int64, __int64, const char *, _QWORD, int, _QWORD, _DWORD))(*(_QWORD *)v19 + 24LL))(
          v19,
          500,
          "Internal Server Error",
          0,
          v16,
          0,
          0);
        if ( LODWORD(v37[0]) )
          RevertToSelf();
        goto LABEL_54;
      }
      v20 = *(const unsigned __int16 **)(v1 + 184);
      v21 = -1;
      do
        ++v21;
      while ( v20[v21] );
      if ( v21 < 0xB || _wcsicmp(&v20[v21 - 11], L"\\web.config") )
      {
        v22 = (void *)(*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, __int64, _QWORD, _QWORD, int, int, _QWORD))(**(_QWORD **)(v1 + 240) + 72LL))(
                        *(_QWORD *)(v1 + 240),
                        v20,
                        1179926,
                        0,
                        0,
                        2,
                        128,
                        0);
        if ( v22 == (void *)-1LL )
        {
          LastError = GetLastError();
          TempFileName = LastError;
          if ( LastError > 0 )
            TempFileName = (unsigned __int16)LastError | 0x80070000;
        }
        else
        {
          CloseHandle(v22);
          TempFileName = 0;
        }
      }
      else
      {
        STRU::STRU((STRU *)v44);
        STRU::STRU((STRU *)v47);
        TempFileName = STRU::Copy((STRU *)v44, v20);
        if ( TempFileName >= 0 )
        {
          TempFileName = CreateTempFileName(
                           *(struct IBaseFileSystem **)(v1 + 240),
                           L".",
                           (struct STRU *)v44,
                           (struct STRU *)v47);
          if ( TempFileName >= 0 )
            TempFileName = CreateEmptyWebConfig(*(struct IBaseFileSystem **)(v1 + 240), v20, v45);
        }
        STRU::~STRU((STRU *)v47);
        STRU::~STRU((STRU *)v44);
      }
      v14 = 1;
      if ( LODWORD(v37[0]) )
        RevertToSelf();
    }
    else
    {
      v14 = 0;
    }
    if ( TempFileName >= 0 )
    {
      STRA::STRA((STRA *)v44);
      v24 = (*(__int64 (__fastcall **)(struct IPubLock *))(*(_QWORD *)v34 + 24LL))(v34);
      TempFileName = SAFE_snprintf((struct STRA *)v44, "<%ws>", v24);
      if ( TempFileName >= 0 )
      {
        v25 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v1 + 8) + 32LL))(*(_QWORD *)(v1 + 8));
        TempFileName = (*(__int64 (__fastcall **)(__int64, const char *, unsigned __int16 *, _QWORD, int))(*(_QWORD *)v25 + 40LL))(
                         v25,
                         "Lock-Token",
                         v45,
                         v46,
                         1);
      }
      STRA::~STRA((STRA *)v44);
      if ( TempFileName >= 0 )
      {
        v26 = "Created";
        if ( !v14 )
          v26 = "OK";
        TempFileName = XML_RESPONDER::BeginXmlCommon((XML_RESPONDER *)(v1 + 448), "prop", (v14 != 0) + 200, v26, 0);
        if ( TempFileName >= 0 )
        {
          TempFileName = XML_RESPONDER::SendXmlLockDiscovery(
                           (XML_RESPONDER *)(v1 + 448),
                           v34,
                           *(const unsigned __int16 **)(v1 + 128));
          if ( TempFileName >= 0 )
          {
            if ( *(_DWORD *)(v1 + 544) )
              TempFileName = XML_RESPONDER::FinishXmlLockResponse((XML_RESPONDER *)(v1 + 448));
          }
        }
      }
    }
  }
  v27 = v34;
  if ( v34 )
  {
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x200000) != 0 )
    {
      v28 = (*(__int64 (__fastcall **)(struct IPubLock *))(*(_QWORD *)v34 + 32LL))(v34);
      v29 = (*(__int64 (__fastcall **)(struct IPubLock *))(*(_QWORD *)v34 + 24LL))(v34);
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\iis70\\webdav\\module\\src\\lock_verb_handler.cxx",
        336,
        "LOCK_VERB_HANDLER::DoLock",
        "Lock token %ws created for URI path %ws\n",
        v29,
        v28);
      v27 = v34;
    }
    if ( TempFileName < 0 )
    {
      v30 = *(_QWORD *)(*(_QWORD *)(v1 + 24) + 3328LL);
      v31 = (*(__int64 (__fastcall **)(struct IPubLock *))(*(_QWORD *)v27 + 24LL))(v27);
      v32 = GetEffectiveUser(*(struct IHttpContext **)(v1 + 8));
      (*(void (__fastcall **)(_QWORD, __int64, const unsigned __int16 *, __int64))(**(_QWORD **)(v30 + 16) + 56LL))(
        *(_QWORD *)(v30 + 16),
        v1 + 248,
        v32,
        v31);
      v27 = v34;
    }
    (*(void (__fastcall **)(struct IPubLock *))(*(_QWORD *)v27 + 16LL))(v27);
    v34 = 0;
  }
  if ( TempFileName < 0 )
  {
    if ( v35 )
      DAV_BASE_HANDLER::FinishRequest((DAV_BASE_HANDLER *)v1, 0x190u, "Bad Request", 0, 0);
    else
      DAV_BASE_HANDLER::MapAndHandleError((DAV_BASE_HANDLER *)v1, TempFileName);
  }
  else
  {
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v1 + 8) + 200LL))(*(_QWORD *)(v1 + 8));
    v12 = 0;
  }
LABEL_54:
  v41 = -1;
  v42 = -1;
  v43 = 0;
  *(_WORD *)v39 = 0;
  v40 = 0;
  STRU::~STRU((STRU *)v38);
  return v12;
}

```

## disassembly

```asm
0x18000bc4c  push    rbp
0x18000bc4e  push    rbx
0x18000bc4f  push    rsi
0x18000bc50  push    rdi
0x18000bc51  push    r12
0x18000bc53  push    r13
0x18000bc55  push    r14
0x18000bc57  push    r15
0x18000bc59  lea     rbp, [rsp-68h]
0x18000bc5e  sub     rsp, 168h
0x18000bc65  mov     rax, cs:__security_cookie
0x18000bc6c  xor     rax, rsp
0x18000bc6f  mov     [rbp+0A0h+var_50], rax
0x18000bc73  mov     r12, rcx
0x18000bc76  mov     [rsp+1A0h+var_128], rcx
0x18000bc7b  xor     r15d, r15d
0x18000bc7e  lea     rcx, [rbp+0A0h+var_110]
0x18000bc82  mov     [rsp+1A0h+var_138], r15d
0x18000bc87  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000bc8d  mov     rax, [rbp+0A0h+var_F0]
0x18000bc91  lea     rdx, [rsp+1A0h+ppvObject]; ppvObject
0x18000bc96  or      r13, 0FFFFFFFFFFFFFFFFh
0x18000bc9a  mov     [rbp+0A0h+var_D0], r15d
0x18000bc9e  mov     [rbp+0A0h+var_D8], r13d
0x18000bca2  lea     rcx, riid; riid
0x18000bca9  mov     [rbp+0A0h+var_D4], r13d
0x18000bcad  xor     r8d, r8d; pMalloc
0x18000bcb0  mov     [rax], r15w
0x18000bcb4  mov     [rbp+0A0h+var_E0], r15d
0x18000bcb8  mov     [rsp+1A0h+var_140], r15
0x18000bcbd  mov     [rsp+1A0h+ppvObject], r15
0x18000bcc2  call    cs:__imp_CreateXmlReader
0x18000bcc8  mov     esi, eax
0x18000bcca  test    eax, eax
0x18000bccc  js      short loc_18000BD0E
0x18000bcce  mov     rcx, [rsp+1A0h+ppvObject]
0x18000bcd3  lea     rdx, [r12+168h]
0x18000bcdb  mov     rax, [rcx]
0x18000bcde  mov     rax, [rax+18h]
0x18000bce2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bce7  mov     esi, eax
0x18000bce9  test    eax, eax
0x18000bceb  js      short loc_18000BD0E
0x18000bced  mov     rdx, [rsp+1A0h+ppvObject]; struct IXmlReader *
0x18000bcf2  lea     r8, [rbp+0A0h+var_110]; struct DAV_LOCK_REQUEST *
0x18000bcf6  mov     rcx, [r12+8]; struct IHttpContext *
0x18000bcfb  call    ?ParseLock@@YAJPEAVIHttpContext@@PEAUIXmlReader@@PEAVDAV_LOCK_REQUEST@@@Z; ParseLock(IHttpContext *,IXmlReader *,DAV_LOCK_REQUEST *)
0x18000bd00  mov     ebx, r15d
0x18000bd03  test    eax, eax
0x18000bd05  mov     esi, eax
0x18000bd07  sets    bl
0x18000bd0a  mov     [rsp+1A0h+var_138], ebx
0x18000bd0e  mov     rcx, [rsp+1A0h+ppvObject]
0x18000bd13  test    rcx, rcx
0x18000bd16  jz      short loc_18000BD29
0x18000bd18  mov     rax, [rcx]
0x18000bd1b  mov     rax, [rax+10h]
0x18000bd1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd24  mov     [rsp+1A0h+ppvObject], r15
0x18000bd29  test    esi, esi
0x18000bd2b  js      loc_18000BDCD
0x18000bd31  mov     rax, [r12+18h]
0x18000bd36  mov     rdi, [r12+15C8h]
0x18000bd3e  mov     rsi, [r12+230h]
0x18000bd46  mov     rcx, [rsp+1A0h+var_128]
0x18000bd4b  mov     rbx, [rax+0D00h]
0x18000bd52  mov     eax, [rbp+0A0h+var_D0]
0x18000bd55  mov     r14d, [rbp+0A0h+var_D4]
0x18000bd59  neg     eax
0x18000bd5b  mov     rcx, [rcx+8]; struct IHttpContext *
0x18000bd5f  mov     r15d, [rbp+0A0h+var_D8]
0x18000bd63  sbb     r13, r13
0x18000bd66  and     r13, [rbp+0A0h+var_F0]
0x18000bd6a  mov     r12d, [r12+228h]
0x18000bd72  call    ?GetEffectiveUser@@YAPEBGPEAVIHttpContext@@@Z; GetEffectiveUser(IHttpContext *)
0x18000bd77  mov     r10, [rbx+10h]
0x18000bd7b  mov     r8, rax
0x18000bd7e  mov     rdx, [rsp+1A0h+var_128]
0x18000bd83  mov     r9d, r12d
0x18000bd86  add     rdx, 0F8h
0x18000bd8d  mov     rcx, [r10]
0x18000bd90  mov     rax, [rcx+30h]
0x18000bd94  lea     rcx, [rsp+1A0h+var_140]
0x18000bd99  mov     [rsp+1A0h+var_158], rcx
0x18000bd9e  mov     rcx, r10
0x18000bda1  mov     [rsp+1A0h+var_160], r13
0x18000bda6  mov     [rsp+1A0h+var_168], rdi
0x18000bdab  mov     [rsp+1A0h+var_170], rsi
0x18000bdb0  mov     dword ptr [rsp+1A0h+var_178], r14d
0x18000bdb5  mov     dword ptr [rsp+1A0h+var_180], r15d
0x18000bdba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdbf  mov     r12, [rsp+1A0h+var_128]
0x18000bdc4  xor     r15d, r15d
0x18000bdc7  or      r13, 0FFFFFFFFFFFFFFFFh
0x18000bdcb  mov     esi, eax
0x18000bdcd  mov     r14d, 2
0x18000bdd3  cmp     esi, 8DAF1A72h
0x18000bdd9  jnz     loc_18000BE71
0x18000bddf  lea     rbx, [r12+1C0h]
0x18000bde7  mov     [rsp+1A0h+var_180], r14w; unsigned __int16
0x18000bded  mov     rcx, rbx; this
0x18000bdf0  lea     r9, aLockedError; "Locked Error"
0x18000bdf7  mov     r8d, 1A7h; unsigned __int16
0x18000bdfd  lea     rdx, aError; "error"
0x18000be04  call    ?BeginXmlCommon@XML_RESPONDER@@AEAAJPEBDG0G@Z; XML_RESPONDER::BeginXmlCommon(char const *,ushort,char const *,ushort)
0x18000be09  test    eax, eax
0x18000be0b  js      short loc_18000BE71
0x18000be0d  mov     eax, [rbp+0A0h+var_D4]
0x18000be10  lea     rdx, [r12+238h]
0x18000be18  mov     rcx, rbx
0x18000be1b  mov     dword ptr [rsp+1A0h+var_180], eax
0x18000be1f  call    ?SendXmlNoConflictingLock@XML_RESPONDER@@QEAAJPEAVLOCK_SET@@W4DAV_DEPTH@@W4DAV_LOCK_TYPE@@W4DAV_LOCK_SCOPE@@@Z; XML_RESPONDER::SendXmlNoConflictingLock(LOCK_SET *,DAV_DEPTH,DAV_LOCK_TYPE,DAV_LOCK_SCOPE)
0x18000be24  test    eax, eax
0x18000be26  js      short loc_18000BE71
0x18000be28  mov     rcx, rbx; this
0x18000be2b  call    ?FinishXmlErrorResponse@XML_RESPONDER@@QEAAJXZ; XML_RESPONDER::FinishXmlErrorResponse(void)
0x18000be30  test    eax, eax
0x18000be32  js      short loc_18000BE71
0x18000be34  mov     rcx, [r12+8]
0x18000be39  mov     rax, [rcx]
0x18000be3c  mov     rax, [rax+0C8h]
0x18000be43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be48  mov     rax, [rbp+0A0h+var_F0]
0x18000be4c  lea     rcx, [rbp+0A0h+var_110]
0x18000be50  mov     [rbp+0A0h+var_D8], r13d
0x18000be54  mov     [rbp+0A0h+var_D4], r13d
0x18000be58  mov     [rbp+0A0h+var_D0], r15d
0x18000be5c  mov     [rax], r15w
0x18000be60  mov     [rbp+0A0h+var_E0], r15d
0x18000be64  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000be6a  xor     eax, eax
0x18000be6c  jmp     loc_18000C2DB
0x18000be71  test    esi, esi
0x18000be73  js      loc_18000C181
0x18000be79  cmp     dword ptr [r12+0D0h], 0FFFFFFFFh
0x18000be82  jz      short loc_18000BE8C
0x18000be84  mov     edi, r15d
0x18000be87  jmp     loc_18000C088
0x18000be8c  mov     rdx, [r12+8]; struct IHttpContext *
0x18000be91  lea     rcx, [rsp+1A0h+var_128]; this
0x18000be96  mov     dword ptr [rsp+1A0h+var_128], r15d
0x18000be9b  mov     [rbp+0A0h+var_120], r15
0x18000be9f  call    ?Impersonate@AUTO_IMPERSONATE@@QEAAJPEAVIHttpContext@@@Z; AUTO_IMPERSONATE::Impersonate(IHttpContext *)
0x18000bea4  mov     ebx, eax
0x18000bea6  test    eax, eax
0x18000bea8  jns     loc_18000BF6A
0x18000beae  mov     rdx, [r12+8]
0x18000beb3  mov     rcx, [rdx]
0x18000beb6  mov     rax, [rcx+110h]
0x18000bebd  mov     rcx, rdx
0x18000bec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bec5  mov     r10, rax
0x18000bec8  mov     byte ptr [rsp+1A0h+var_180], 3
0x18000becd  mov     r9d, ebx
0x18000bed0  lea     rdx, aImpersonationF; "Impersonation Failure"
0x18000bed7  xor     r8d, r8d
0x18000beda  mov     rcx, [rax]
0x18000bedd  mov     rax, [rcx+20h]
0x18000bee1  mov     rcx, r10
0x18000bee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bee9  mov     rcx, [r12+8]
0x18000beee  mov     rax, [rcx]
0x18000bef1  mov     rax, [rax+20h]
0x18000bef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000befa  mov     rdx, rax
0x18000befd  mov     rcx, [rax]
0x18000bf00  mov     rax, [rcx+8]
0x18000bf04  mov     rcx, rdx
0x18000bf07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf0c  mov     [rax+218h], r15w
0x18000bf14  mov     rcx, [r12+8]
0x18000bf19  mov     rax, [rcx]
0x18000bf1c  mov     rax, [rax+20h]
0x18000bf20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf25  mov     r10, rax
0x18000bf28  mov     dword ptr [rsp+1A0h+var_170], r15d
0x18000bf2d  xor     r9d, r9d
0x18000bf30  mov     [rsp+1A0h+var_178], r15
0x18000bf35  mov     edx, 1F4h
0x18000bf3a  mov     dword ptr [rsp+1A0h+var_180], ebx
0x18000bf3e  mov     rcx, [rax]
0x18000bf41  lea     r8, aInternalServer; "Internal Server Error"
0x18000bf48  mov     rax, [rcx+18h]
0x18000bf4c  mov     rcx, r10
0x18000bf4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf54  cmp     dword ptr [rsp+1A0h+var_128], r15d
0x18000bf59  jz      loc_18000C2B6
0x18000bf5f  call    cs:__imp_RevertToSelf
0x18000bf65  jmp     loc_18000C2B6
0x18000bf6a  mov     rbx, [r12+0B8h]
0x18000bf72  mov     rax, r13
0x18000bf75  inc     rax
0x18000bf78  cmp     [rbx+rax*2], r15w
0x18000bf7d  jnz     short loc_18000BF75
0x18000bf7f  cmp     rax, 0Bh
0x18000bf83  jb      loc_18000C017
0x18000bf89  add     rax, 0FFFFFFFFFFFFFFF5h
0x18000bf8d  lea     rdx, aWebConfig; "\\web.config"
0x18000bf94  lea     rcx, [rbx+rax*2]; String1
0x18000bf98  call    cs:__imp__wcsicmp
0x18000bf9e  test    eax, eax
0x18000bfa0  jnz     short loc_18000C017
0x18000bfa2  lea     rcx, [rbp+0A0h+var_C0]
0x18000bfa6  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000bfac  lea     rcx, [rbp+0A0h+var_88]
0x18000bfb0  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000bfb6  mov     rdx, rbx
0x18000bfb9  lea     rcx, [rbp+0A0h+var_C0]
0x18000bfbd  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000bfc3  mov     esi, eax
0x18000bfc5  test    eax, eax
0x18000bfc7  js      short loc_18000C001
0x18000bfc9  mov     rcx, [r12+0F0h]; struct IBaseFileSystem *
0x18000bfd1  lea     r9, [rbp+0A0h+var_88]; struct STRU *
0x18000bfd5  lea     r8, [rbp+0A0h+var_C0]; struct STRU *
0x18000bfd9  lea     rdx, asc_180027680; "."
0x18000bfe0  call    ?CreateTempFileName@@YAJPEAVIBaseFileSystem@@PEBGPEAVSTRU@@2@Z; CreateTempFileName(IBaseFileSystem *,ushort const *,STRU *,STRU *)
0x18000bfe5  mov     esi, eax
0x18000bfe7  test    eax, eax
0x18000bfe9  js      short loc_18000C001
0x18000bfeb  mov     r8, [rbp+0A0h+var_A0]; unsigned __int16 *
0x18000bfef  mov     rdx, rbx; unsigned __int16 *
0x18000bff2  mov     rcx, [r12+0F0h]; struct IBaseFileSystem *
0x18000bffa  call    ?CreateEmptyWebConfig@@YAJPEAVIBaseFileSystem@@PEBG1@Z; CreateEmptyWebConfig(IBaseFileSystem *,ushort const *,ushort const *)
0x18000bfff  mov     esi, eax
0x18000c001  lea     rcx, [rbp+0A0h+var_88]
0x18000c005  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000c00b  lea     rcx, [rbp+0A0h+var_C0]
0x18000c00f  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000c015  jmp     short loc_18000C076
0x18000c017  mov     rcx, [r12+0F0h]
0x18000c01f  xor     r9d, r9d
0x18000c022  mov     [rsp+1A0h+var_168], r15
0x18000c027  mov     r8d, 120116h
0x18000c02d  mov     dword ptr [rsp+1A0h+var_170], 80h
0x18000c035  mov     rdx, rbx
0x18000c038  mov     dword ptr [rsp+1A0h+var_178], r14d
0x18000c03d  mov     rax, [rcx]
0x18000c040  mov     qword ptr [rsp+1A0h+var_180], r15
0x18000c045  mov     rax, [rax+48h]
0x18000c049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c04e  cmp     rax, r13
0x18000c051  jnz     short loc_18000C06A
0x18000c053  call    cs:__imp_GetLastError
0x18000c059  mov     esi, eax
0x18000c05b  test    eax, eax
0x18000c05d  jle     short loc_18000C076
0x18000c05f  movzx   esi, ax
0x18000c062  or      esi, 80070000h
0x18000c068  jmp     short loc_18000C076
0x18000c06a  mov     rcx, rax; hObject
0x18000c06d  call    cs:__imp_CloseHandle
0x18000c073  mov     esi, r15d
0x18000c076  mov     edi, 1
0x18000c07b  cmp     dword ptr [rsp+1A0h+var_128], r15d
0x18000c080  jz      short loc_18000C088
0x18000c082  call    cs:__imp_RevertToSelf
0x18000c088  test    esi, esi
0x18000c08a  js      loc_18000C181
0x18000c090  lea     rcx, [rbp+0A0h+var_C0]
0x18000c094  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x18000c09a  mov     rcx, [rsp+1A0h+var_140]
0x18000c09f  mov     rax, [rcx]
0x18000c0a2  mov     rax, [rax+18h]
0x18000c0a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0ab  mov     r8, rax
0x18000c0ae  lea     rdx, aWs; "<%ws>"
0x18000c0b5  lea     rcx, [rbp+0A0h+var_C0]; struct STRA *
0x18000c0b9  call    ?SAFE_snprintf@@YAJPEAVSTRA@@PEBDZZ; SAFE_snprintf(STRA *,char const *,...)
0x18000c0be  mov     esi, eax
0x18000c0c0  test    eax, eax
0x18000c0c2  js      short loc_18000C101
0x18000c0c4  mov     rcx, [r12+8]
0x18000c0c9  mov     rax, [rcx]
0x18000c0cc  mov     rax, [rax+20h]
0x18000c0d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0d5  movzx   r9d, [rbp+0A0h+var_90]
0x18000c0da  lea     rdx, aLockToken; "Lock-Token"
0x18000c0e1  mov     r8, [rbp+0A0h+var_A0]
0x18000c0e5  mov     r10, rax
0x18000c0e8  mov     dword ptr [rsp+1A0h+var_180], 1
0x18000c0f0  mov     rcx, [rax]
0x18000c0f3  mov     rax, [rcx+28h]
0x18000c0f7  mov     rcx, r10
0x18000c0fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0ff  mov     esi, eax
0x18000c101  lea     rcx, [rbp+0A0h+var_C0]
0x18000c105  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000c10b  test    esi, esi
0x18000c10d  js      short loc_18000C181
0x18000c10f  test    edi, edi
0x18000c111  mov     [rsp+1A0h+var_180], r15w; unsigned __int16
0x18000c117  lea     rcx, aOk; "OK"
0x18000c11e  lea     r9, aCreated; "Created"
0x18000c125  cmovz   r9, rcx; char *
0x18000c129  lea     rbx, [r12+1C0h]
0x18000c131  neg     edi
0x18000c133  lea     rdx, aProp_0; "prop"
0x18000c13a  mov     rcx, rbx; this
0x18000c13d  sbb     r8w, r8w
  ... truncated ...
```
