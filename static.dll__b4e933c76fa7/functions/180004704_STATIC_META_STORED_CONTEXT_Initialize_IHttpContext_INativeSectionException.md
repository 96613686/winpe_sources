# STATIC_META_STORED_CONTEXT::Initialize(IHttpContext *,INativeSectionException * *)

- ea: `0x180004704`
- end: `0x180004e4f`
- name: `?Initialize@STATIC_META_STORED_CONTEXT@@IEAAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@@Z`
- size: `1867`
- prototype: `__int64 __fastcall(STATIC_META_STORED_CONTEXT *__hidden this, struct IHttpContext *, struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180004590`

## callees

- `0x180004704`
- `0x180004e58`
- `0x1800054f0`
- `0x180005e30`
- `0x1800067d2`
- `0x180006810`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a6c`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180004b25`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180004b25`
- `iisutil!SAFE_snwprintf` at `0x180004af5`
- `iisutil!SAFE_snwprintf` at `0x180004af5`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180004cba`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180004cba`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x1800048fa`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x180004989`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x180004a26`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x1800048fa`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x180004989`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x180004a26`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004a66`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004a66`
- `iisutil!?GetString@LANG_STRING@@QEAAJPEBDKIPEAPEBGPEAK@Z` at `0x180004ad7`
- `iisutil!?GetString@LANG_STRING@@QEAAJPEBDKIPEAPEBGPEAK@Z` at `0x180004ad7`
- `iisutil!?IsEmpty@STRA@@QEBA_NXZ` at `0x180004c5e`
- `iisutil!?IsEmpty@STRA@@QEBA_NXZ` at `0x180004c9d`
- `iisutil!?IsEmpty@STRA@@QEBA_NXZ` at `0x180004c5e`
- `iisutil!?IsEmpty@STRA@@QEBA_NXZ` at `0x180004c9d`
- `iisutil!StringTimeToFileTime` at `0x180004a48`
- `iisutil!StringTimeToFileTime` at `0x180004a48`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004b31`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004b31`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180004a3b`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180004a3b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004ae5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004b52`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004ae5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004b52`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004916`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004916`

## string_xrefs

- `0x180004931`: `clientCache`
- `0x180004960`: `cacheControlCustom`
- `0x1800049b0`: `cacheControlMode`
- `0x180004cac`: `no-cache`
- `0x180004ca5`: `,no-cache`
- `0x180004c1a`: `cacheControlMaxAge`
- `0x180004ddd`: `accessPolicy`

## pseudocode

```c
__int64 __fastcall STATIC_META_STORED_CONTEXT::Initialize(
        STATIC_META_STORED_CONTEXT *this,
        struct IHttpContext *a2,
        struct INativeSectionException **a3)
{
  __int64 v3; // rax
  __int64 (__fastcall *v6)(struct IHttpContext *); // rax
  __int64 (__fastcall ***v8)(_QWORD); // rax
  const unsigned __int16 *v9; // rbx
  __int64 (__fastcall ***v10)(_QWORD, GUID *, __int64 *); // rax
  signed int v11; // r14d
  BOOL v12; // r12d
  const char *Str; // rax
  signed int LastError; // eax
  __int64 v15; // rax
  const char *v16; // rax
  __int64 v17; // rsi
  void (__fastcall *v18)(__int64, unsigned __int16 *, _QWORD, __int64); // rdi
  unsigned int CCH; // ebx
  unsigned __int16 *v20; // rax
  __int64 v22; // rbx
  bool v23; // al
  const char *v24; // r8
  char *v25; // rdx
  bool IsEmpty; // al
  BOOL v27; // ebx
  struct IHttpServer *v28; // r9
  const char *v29; // [rsp+30h] [rbp-D0h]
  unsigned __int16 v30; // [rsp+38h] [rbp-C8h]
  struct STRU *v31; // [rsp+40h] [rbp-C0h]
  struct IHttpTraceContext *v32; // [rsp+48h] [rbp-B8h]
  unsigned __int16 v33; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v34; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v35; // [rsp+60h] [rbp-A0h] BYREF
  struct INativeConfigurationElement *v36; // [rsp+68h] [rbp-98h] BYREF
  struct INativeConfigurationElement *v37; // [rsp+70h] [rbp-90h] BYREF
  int v38; // [rsp+78h] [rbp-88h] BYREF
  __int64 v39; // [rsp+80h] [rbp-80h] BYREF
  wchar_t *String1; // [rsp+88h] [rbp-78h] BYREF
  const unsigned __int16 *v41; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v42; // [rsp+98h] [rbp-68h] BYREF
  const unsigned __int16 *v43; // [rsp+A0h] [rbp-60h] BYREF
  const unsigned __int16 *v44; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v45; // [rsp+B0h] [rbp-50h] BYREF
  const unsigned __int16 *v46; // [rsp+B8h] [rbp-48h] BYREF
  union _LARGE_INTEGER v47; // [rsp+C0h] [rbp-40h] BYREF
  char v48[56]; // [rsp+C8h] [rbp-38h] BYREF
  char v49[32]; // [rsp+100h] [rbp+0h] BYREF

  v3 = *(_QWORD *)a2;
  v39 = 0;
  v36 = 0;
  v35 = 0;
  v6 = *(__int64 (__fastcall **)(struct IHttpContext *))(v3 + 160);
  v37 = 0;
  String1 = 0;
  v43 = 0;
  v34 = 0;
  v44 = 0;
  v38 = 0;
  v46 = 0;
  v45 = 0;
  v47.QuadPart = 0;
  v8 = (__int64 (__fastcall ***)(_QWORD))v6(a2);
  v9 = (const unsigned __int16 *)(**v8)(v8);
  v41 = v9;
  v10 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 56LL))(g_pGlobalInfo);
  v11 = (**v10)(v10, &IID_INativeConfigurationSystem, &v39);
  if ( v11 < 0 )
    goto LABEL_26;
  v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 *, struct INativeConfigurationElement **, struct INativeSectionException **, __int64 *))(*(_QWORD *)v39 + 24LL))(
          v39,
          L"system.webServer/staticContent",
          v9,
          &v36,
          a3,
          &v35);
  if ( v11 < 0 )
    goto LABEL_26;
  v11 = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v35 + 24LL))(v35, &String1);
  if ( v11 < 0 )
    goto LABEL_26;
  v12 = wcscmp_0(String1, L"MACHINE/WEBROOT/APPHOST") == 0;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  v35 = 0;
  v11 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v36 + 72LL))(
          v36,
          L"enableDocFooter",
          (char *)this + 120,
          0,
          0);
  if ( v11 < 0 )
    goto LABEL_26;
  if ( *((_DWORD *)this + 30) )
  {
    v11 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v36 + 72LL))(
            v36,
            L"isDocFooterFileName",
            (char *)this + 124,
            0,
            0);
    if ( v11 < 0 )
      goto LABEL_26;
    v11 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v36 + 64LL))(
            v36,
            L"defaultDocFooter",
            &v43,
            0,
            0);
    if ( v11 < 0 )
      goto LABEL_26;
    v11 = STRA::CopyW((STATIC_META_STORED_CONTEXT *)((char *)this + 128), v43);
    if ( v11 < 0 )
      goto LABEL_26;
    v11 = STRU::Copy((STATIC_META_STORED_CONTEXT *)((char *)this + 184), v43);
    if ( v11 < 0 )
      goto LABEL_26;
  }
  v11 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, __int64 *))(*(_QWORD *)v36 + 32LL))(
          v36,
          L"clientCache",
          &v34);
  if ( v11 < 0 )
    goto LABEL_26;
  v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v34 + 64LL))(
          v34,
          L"cacheControlCustom",
          &v46,
          0,
          0);
  if ( v11 < 0 )
    goto LABEL_26;
  v11 = STRA::CopyW((STATIC_META_STORED_CONTEXT *)((char *)this + 8), v46);
  if ( v11 < 0 )
    goto LABEL_26;
  v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v34 + 48LL))(
          v34,
          L"cacheControlMode",
          &v38,
          0,
          0);
  if ( v11 < 0 )
    goto LABEL_26;
  switch ( v38 )
  {
    case 1:
      IsEmpty = STRA::IsEmpty((STATIC_META_STORED_CONTEXT *)((char *)this + 8));
      v25 = "no-cache";
      if ( !IsEmpty )
        v25 = ",no-cache";
      goto LABEL_44;
    case 2:
      v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *, _QWORD, _QWORD))(*(_QWORD *)v34 + 80LL))(
              v34,
              L"cacheControlMaxAge",
              &v45,
              0,
              0);
      if ( v11 < 0 )
        goto LABEL_26;
      v22 = v45 / 10000000;
      v23 = STRA::IsEmpty((STATIC_META_STORED_CONTEXT *)((char *)this + 8));
      v24 = "max-age=%u";
      if ( !v23 )
        v24 = ",max-age=%u";
      v11 = StringCchPrintfA(v49, 0x20u, v24, (unsigned int)v22);
      if ( v11 < 0 )
        goto LABEL_26;
      v25 = v49;
LABEL_44:
      v11 = STRA::Append((STATIC_META_STORED_CONTEXT *)((char *)this + 8), v25);
      if ( v11 < 0 )
        goto LABEL_26;
      break;
    case 3:
      v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v34 + 64LL))(
              v34,
              L"httpExpires",
              &v44,
              0,
              0);
      if ( v11 < 0 )
        goto LABEL_26;
      v11 = STRA::CopyW((STATIC_META_STORED_CONTEXT *)((char *)this + 64), v44);
      if ( v11 < 0 )
        goto LABEL_26;
      Str = STRA::QueryStr((STATIC_META_STORED_CONTEXT *)((char *)this + 64));
      if ( !StringTimeToFileTime(Str, &v47) )
      {
        v33 = 0;
        v41 = 0;
        v42 = 0;
        STRU::STRU((STRU *)v48);
        LastError = GetLastError();
        v11 = LastError;
        if ( LastError > 0 )
          v11 = (unsigned __int16)LastError | 0x80070000;
        v15 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 24LL))(a2);
        v16 = (const char *)(*(__int64 (__fastcall **)(__int64, __int64, unsigned __int16 *))(*(_QWORD *)v15 + 16LL))(
                              v15,
                              23,
                              &v33);
        if ( (int)LANG_STRING::GetString(
                    (LANG_STRING *)W3_STATIC_FILE_HANDLER::sm_pLangString,
                    v16,
                    v33,
                    0x3233u,
                    &v41,
                    &v42) < 0
          || (int)SAFE_snwprintf((struct STRU *)v48, v41, v44) < 0 )
        {
          STRU::~STRU((STRU *)v48);
        }
        else
        {
          v17 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 32LL))(a2);
          v18 = *(void (__fastcall **)(__int64, unsigned __int16 *, _QWORD, __int64))(*(_QWORD *)v17 + 192LL);
          CCH = STRU::QueryCCH((STRU *)v48);
          v20 = STRU::QueryStr((STRU *)v48);
          v18(v17, v20, CCH, 1);
          STRU::~STRU((STRU *)v48);
        }
        goto LABEL_26;
      }
      break;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v34 + 72LL))(
          v34,
          L"setEtag",
          (char *)this + 284,
          0,
          0);
  if ( v11 >= 0 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    v34 = 0;
    v11 = MIME_MAP::Initialize((STATIC_META_STORED_CONTEXT *)((char *)this + 240), v36, v12);
    if ( v11 >= 0 )
    {
      (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v36 + 16LL))(v36);
      v36 = 0;
      v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 *, struct INativeConfigurationElement **, struct INativeSectionException **))(*(_QWORD *)v39 + 24LL))(
              v39,
              L"system.webServer/handlers",
              v41,
              &v37,
              a3);
      if ( v11 >= 0 )
      {
        v11 = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v35 + 24LL))(v35, &String1);
        if ( v11 >= 0 )
        {
          v27 = wcscmp_0(String1, L"MACHINE/WEBROOT/APPHOST") == 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
          v35 = 0;
          v11 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, char *, _QWORD))(*(_QWORD *)v37 + 48LL))(
                  v37,
                  L"accessPolicy",
                  (char *)this + 280,
                  0);
          if ( v11 >= 0 )
          {
            v11 = META_SCRIPT_MAP::Initialize(
                    (STATIC_META_STORED_CONTEXT *)((char *)this + 264),
                    v37,
                    v27,
                    v28,
                    0,
                    (struct LANG_STRING *)&v35,
                    v29,
                    v30,
                    v31,
                    v32);
            if ( v11 >= 0 )
            {
              (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v37 + 16LL))(v37);
              v37 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
              return 0;
            }
          }
        }
      }
    }
  }
LABEL_26:
  if ( v37 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v37 + 16LL))(v37);
    v37 = 0;
  }
  if ( v34 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    v34 = 0;
  }
  if ( v35 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    v35 = 0;
  }
  if ( v36 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v36 + 16LL))(v36);
    v36 = 0;
  }
  if ( v39 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180004704  mov     [rsp-8+arg_18], rbx
0x180004709  push    rbp
0x18000470a  push    rsi
0x18000470b  push    rdi
0x18000470c  push    r12
0x18000470e  push    r13
0x180004710  push    r14
0x180004712  push    r15
0x180004714  lea     rbp, [rsp-30h]
0x180004719  sub     rsp, 130h
0x180004720  mov     rax, cs:__security_cookie
0x180004727  xor     rax, rsp
0x18000472a  mov     [rbp+60h+var_40], rax
0x18000472e  mov     rax, [rdx]
0x180004731  xor     esi, esi
0x180004733  mov     rdi, rcx
0x180004736  mov     [rbp+60h+var_E0], rsi
0x18000473a  mov     rcx, rdx
0x18000473d  mov     [rsp+160h+var_F8], rsi
0x180004742  mov     r13, r8
0x180004745  mov     [rsp+160h+var_100], rsi
0x18000474a  mov     rax, [rax+0A0h]
0x180004751  mov     r15, rdx
0x180004754  mov     [rsp+160h+var_F0], rsi
0x180004759  mov     [rbp+60h+String1], rsi
0x18000475d  mov     [rbp+60h+var_C0], rsi
0x180004761  mov     [rsp+160h+var_108], rsi
0x180004766  mov     [rbp+60h+var_B8], rsi
0x18000476a  mov     [rsp+160h+var_E8], esi
0x18000476e  mov     [rbp+60h+var_A8], rsi
0x180004772  mov     [rbp+60h+var_B0], rsi
0x180004776  mov     [rbp+60h+var_A0], rsi
0x18000477a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000477f  mov     rdx, rax
0x180004782  mov     rcx, [rax]
0x180004785  mov     rax, [rcx]
0x180004788  mov     rcx, rdx
0x18000478b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004790  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180004797  mov     rbx, rax
0x18000479a  mov     [rbp+60h+var_D0], rax
0x18000479e  mov     rdx, [rcx]
0x1800047a1  mov     rax, [rdx+38h]
0x1800047a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047aa  mov     r9, rax
0x1800047ad  lea     r8, [rbp+60h+var_E0]
0x1800047b1  lea     rdx, IID_INativeConfigurationSystem
0x1800047b8  mov     rcx, [rax]
0x1800047bb  mov     rax, [rcx]
0x1800047be  mov     rcx, r9
0x1800047c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047c6  mov     r14d, eax
0x1800047c9  test    eax, eax
0x1800047cb  js      loc_180004B5A
0x1800047d1  mov     rcx, [rbp+60h+var_E0]
0x1800047d5  lea     rdx, [rsp+160h+var_100]
0x1800047da  mov     [rsp+160h+var_138], rdx
0x1800047df  lea     r9, [rsp+160h+var_F8]
0x1800047e4  mov     r8, rbx
0x1800047e7  mov     qword ptr [rsp+160h+var_140], r13
0x1800047ec  lea     rdx, aSystemWebserve; "system.webServer/staticContent"
0x1800047f3  mov     rax, [rcx]
0x1800047f6  mov     rax, [rax+18h]
0x1800047fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047ff  mov     r14d, eax
0x180004802  test    eax, eax
0x180004804  js      loc_180004B5A
0x18000480a  mov     rcx, [rsp+160h+var_100]
0x18000480f  lea     rdx, [rbp+60h+String1]
0x180004813  mov     rax, [rcx]
0x180004816  mov     rax, [rax+18h]
0x18000481a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000481f  mov     r14d, eax
0x180004822  test    eax, eax
0x180004824  js      loc_180004B5A
0x18000482a  mov     rcx, [rbp+60h+String1]; String1
0x18000482e  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180004835  call    wcscmp_0
0x18000483a  mov     rcx, [rsp+160h+var_100]
0x18000483f  test    eax, eax
0x180004841  mov     r12d, esi
0x180004844  setz    r12b
0x180004848  mov     rax, [rcx]
0x18000484b  mov     rax, [rax+10h]
0x18000484f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004854  mov     rcx, [rsp+160h+var_F8]
0x180004859  lea     r8, [rdi+78h]
0x18000485d  mov     [rsp+160h+var_100], rsi
0x180004862  lea     rdx, aEnabledocfoote; "enableDocFooter"
0x180004869  xor     r9d, r9d
0x18000486c  mov     qword ptr [rsp+160h+var_140], rsi
0x180004871  mov     rax, [rcx]
0x180004874  mov     rax, [rax+48h]
0x180004878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000487d  mov     r14d, eax
0x180004880  test    eax, eax
0x180004882  js      loc_180004B5A
0x180004888  cmp     [rdi+78h], esi
0x18000488b  jz      loc_180004927
0x180004891  mov     rcx, [rsp+160h+var_F8]
0x180004896  lea     r8, [rdi+7Ch]
0x18000489a  xor     r9d, r9d
0x18000489d  mov     qword ptr [rsp+160h+var_140], rsi
0x1800048a2  lea     rdx, aIsdocfooterfil; "isDocFooterFileName"
0x1800048a9  mov     rax, [rcx]
0x1800048ac  mov     rax, [rax+48h]
0x1800048b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048b5  mov     r14d, eax
0x1800048b8  test    eax, eax
0x1800048ba  js      loc_180004B5A
0x1800048c0  mov     rcx, [rsp+160h+var_F8]
0x1800048c5  lea     r8, [rbp+60h+var_C0]
0x1800048c9  xor     r9d, r9d
0x1800048cc  mov     qword ptr [rsp+160h+var_140], rsi
0x1800048d1  lea     rdx, aDefaultdocfoot; "defaultDocFooter"
0x1800048d8  mov     rax, [rcx]
0x1800048db  mov     rax, [rax+40h]
0x1800048df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048e4  mov     r14d, eax
0x1800048e7  test    eax, eax
0x1800048e9  js      loc_180004B5A
0x1800048ef  mov     rdx, [rbp+60h+var_C0]
0x1800048f3  lea     rcx, [rdi+80h]
0x1800048fa  call    cs:__imp_?CopyW@STRA@@QEAAJPEBG@Z; STRA::CopyW(ushort const *)
0x180004900  mov     r14d, eax
0x180004903  test    eax, eax
0x180004905  js      loc_180004B5A
0x18000490b  mov     rdx, [rbp+60h+var_C0]
0x18000490f  lea     rcx, [rdi+0B8h]
0x180004916  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000491c  mov     r14d, eax
0x18000491f  test    eax, eax
0x180004921  js      loc_180004B5A
0x180004927  mov     rcx, [rsp+160h+var_F8]
0x18000492c  lea     r8, [rsp+160h+var_108]
0x180004931  lea     rdx, aClientcache; "clientCache"
0x180004938  mov     rax, [rcx]
0x18000493b  mov     rax, [rax+20h]
0x18000493f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004944  mov     r14d, eax
0x180004947  test    eax, eax
0x180004949  js      loc_180004B5A
0x18000494f  mov     rcx, [rsp+160h+var_108]
0x180004954  lea     r8, [rbp+60h+var_A8]
0x180004958  xor     r9d, r9d
0x18000495b  mov     qword ptr [rsp+160h+var_140], rsi
0x180004960  lea     rdx, aCachecontrolcu; "cacheControlCustom"
0x180004967  mov     rax, [rcx]
0x18000496a  mov     rax, [rax+40h]
0x18000496e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004973  mov     r14d, eax
0x180004976  test    eax, eax
0x180004978  js      loc_180004B5A
0x18000497e  mov     rdx, [rbp+60h+var_A8]
0x180004982  lea     rsi, [rdi+8]
0x180004986  mov     rcx, rsi
0x180004989  call    cs:__imp_?CopyW@STRA@@QEAAJPEBG@Z; STRA::CopyW(ushort const *)
0x18000498f  mov     r14d, eax
0x180004992  test    eax, eax
0x180004994  js      loc_180004B58
0x18000499a  mov     rcx, [rsp+160h+var_108]
0x18000499f  lea     r8, [rsp+160h+var_E8]
0x1800049a4  xor     r9d, r9d
0x1800049a7  mov     qword ptr [rsp+160h+var_140], 0
0x1800049b0  lea     rdx, aCachecontrolmo; "cacheControlMode"
0x1800049b7  mov     rax, [rcx]
0x1800049ba  mov     rax, [rax+30h]
0x1800049be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049c3  mov     r14d, eax
0x1800049c6  test    eax, eax
0x1800049c8  js      loc_180004B58
0x1800049ce  mov     ecx, [rsp+160h+var_E8]
0x1800049d2  sub     ecx, 1
0x1800049d5  jz      loc_180004C9A
0x1800049db  sub     ecx, 1
0x1800049de  jz      loc_180004C05
0x1800049e4  xor     esi, esi
0x1800049e6  cmp     ecx, 1
0x1800049e9  jnz     loc_180004CCD
0x1800049ef  mov     rcx, [rsp+160h+var_108]
0x1800049f4  lea     r8, [rbp+60h+var_B8]
0x1800049f8  xor     r9d, r9d
0x1800049fb  mov     qword ptr [rsp+160h+var_140], rsi
0x180004a00  lea     rdx, aHttpexpires; "httpExpires"
0x180004a07  mov     rax, [rcx]
0x180004a0a  mov     rax, [rax+40h]
0x180004a0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a13  mov     r14d, eax
0x180004a16  test    eax, eax
0x180004a18  js      loc_180004B5A
0x180004a1e  mov     rdx, [rbp+60h+var_B8]
0x180004a22  lea     rcx, [rdi+40h]
0x180004a26  call    cs:__imp_?CopyW@STRA@@QEAAJPEBG@Z; STRA::CopyW(ushort const *)
0x180004a2c  mov     r14d, eax
0x180004a2f  test    eax, eax
0x180004a31  js      loc_180004B5A
0x180004a37  lea     rcx, [rdi+40h]
0x180004a3b  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180004a41  mov     rcx, rax
0x180004a44  lea     rdx, [rbp+60h+var_A0]
0x180004a48  call    cs:__imp_?StringTimeToFileTime@@YAHPEBDPEAT_LARGE_INTEGER@@@Z; StringTimeToFileTime(char const *,_LARGE_INTEGER *)
0x180004a4e  test    eax, eax
0x180004a50  jnz     loc_180004CCD
0x180004a56  lea     rcx, [rbp+60h+var_98]
0x180004a5a  mov     [rsp+160h+var_110], si
0x180004a5f  mov     [rbp+60h+var_D0], rsi
0x180004a63  mov     [rbp+60h+var_C8], esi
0x180004a66  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180004a6c  call    cs:__imp_GetLastError
0x180004a72  mov     r14d, eax
0x180004a75  test    eax, eax
0x180004a77  jle     short loc_180004A84
0x180004a79  movzx   r14d, ax
0x180004a7d  or      r14d, 80070000h
0x180004a84  mov     rax, [r15]
0x180004a87  mov     rcx, r15
0x180004a8a  mov     rax, [rax+18h]
0x180004a8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a93  mov     r9, rax
0x180004a96  lea     r8, [rsp+160h+var_110]
0x180004a9b  mov     edx, 17h
0x180004aa0  mov     rcx, [rax]
0x180004aa3  mov     rax, [rcx+10h]
0x180004aa7  mov     rcx, r9
0x180004aaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004aaf  movzx   r8d, [rsp+160h+var_110]
0x180004ab5  lea     rcx, [rbp+60h+var_C8]
0x180004ab9  mov     [rsp+160h+var_138], rcx
0x180004abe  mov     r9d, 3233h
0x180004ac4  lea     rcx, [rbp+60h+var_D0]
0x180004ac8  mov     rdx, rax
0x180004acb  mov     qword ptr [rsp+160h+var_140], rcx
0x180004ad0  mov     rcx, cs:?sm_pLangString@W3_STATIC_FILE_HANDLER@@2PEAVLANG_STRING@@EA; LANG_STRING * W3_STATIC_FILE_HANDLER::sm_pLangString
0x180004ad7  call    cs:__imp_?GetString@LANG_STRING@@QEAAJPEBDKIPEAPEBGPEAK@Z; LANG_STRING::GetString(char const *,ulong,uint,ushort const * *,ulong *)
0x180004add  lea     rcx, [rbp+60h+var_98]
0x180004ae1  test    eax, eax
0x180004ae3  jns     short loc_180004AED
0x180004ae5  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180004aeb  jmp     short loc_180004B5A
0x180004aed  mov     r8, [rbp+60h+var_B8]
0x180004af1  mov     rdx, [rbp+60h+var_D0]
0x180004af5  call    cs:__imp_?SAFE_snwprintf@@YAJPEAVSTRU@@PEBGZZ; SAFE_snwprintf(STRU *,ushort const *,...)
0x180004afb  test    eax, eax
0x180004afd  jns     short loc_180004B05
0x180004aff  lea     rcx, [rbp+60h+var_98]
0x180004b03  jmp     short loc_180004AE5
0x180004b05  mov     rax, [r15]
0x180004b08  mov     rcx, r15
0x180004b0b  mov     rax, [rax+20h]
0x180004b0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b14  mov     rsi, rax
0x180004b17  mov     rcx, [rax]
0x180004b1a  mov     rdi, [rcx+0C0h]
0x180004b21  lea     rcx, [rbp+60h+var_98]
0x180004b25  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180004b2b  lea     rcx, [rbp+60h+var_98]
0x180004b2f  mov     ebx, eax
0x180004b31  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180004b37  mov     r9d, 1
0x180004b3d  mov     r8d, ebx
0x180004b40  mov     rdx, rax
0x180004b43  mov     rcx, rsi
0x180004b46  mov     rax, rdi
0x180004b49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b4e  lea     rcx, [rbp+60h+var_98]
0x180004b52  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180004b58  xor     esi, esi
0x180004b5a  mov     rcx, [rsp+160h+var_F0]
0x180004b5f  test    rcx, rcx
0x180004b62  jz      short loc_180004B75
0x180004b64  mov     rax, [rcx]
0x180004b67  mov     rax, [rax+10h]
0x180004b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b70  mov     [rsp+160h+var_F0], rsi
0x180004b75  mov     rcx, [rsp+160h+var_108]
0x180004b7a  test    rcx, rcx
0x180004b7d  jz      short loc_180004B90
0x180004b7f  mov     rax, [rcx]
0x180004b82  mov     rax, [rax+10h]
0x180004b86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b8b  mov     [rsp+160h+var_108], rsi
0x180004b90  mov     rcx, [rsp+160h+var_100]
0x180004b95  test    rcx, rcx
0x180004b98  jz      short loc_180004BAB
0x180004b9a  mov     rax, [rcx]
0x180004b9d  mov     rax, [rax+10h]
0x180004ba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ba6  mov     [rsp+160h+var_100], rsi
0x180004bab  mov     rcx, [rsp+160h+var_F8]
0x180004bb0  test    rcx, rcx
0x180004bb3  jz      short loc_180004BC6
0x180004bb5  mov     rax, [rcx]
0x180004bb8  mov     rax, [rax+10h]
0x180004bbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bc1  mov     [rsp+160h+var_F8], rsi
0x180004bc6  mov     rcx, [rbp+60h+var_E0]
0x180004bca  test    rcx, rcx
0x180004bcd  jz      short loc_180004BDB
0x180004bcf  mov     rax, [rcx]
0x180004bd2  mov     rax, [rax+10h]
  ... truncated ...
```
