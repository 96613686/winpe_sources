# STATIC_META_STORED_CONTEXT::Initialize(IHttpContext *,INativeSectionException * *)

- ea: `0x180017cc8`
- end: `0x180018426`
- name: `?Initialize@STATIC_META_STORED_CONTEXT@@IEAAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@@Z`
- size: `1886`
- prototype: `__int64 __fastcall(STATIC_META_STORED_CONTEXT *__hidden this, struct IHttpContext *, struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18000d848`

## callees

- `0x180017cc8`
- `0x18001842c`
- `0x18001863c`
- `0x180018d28`
- `0x1800224e6`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001805a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001805a`
- `iisutil!SAFE_snwprintf` at `0x18001819c`
- `iisutil!SAFE_snwprintf` at `0x18001819c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180017f0e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180017f0e`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180018054`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180018054`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800180d4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800180d4`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x180017ef3`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x180017f82`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x18001801e`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x180017ef3`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x180017f82`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x18001801e`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180018282`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180018282`
- `iisutil!StringTimeToFileTime` at `0x180018036`
- `iisutil!StringTimeToFileTime` at `0x180018036`
- `iisutil!?GetString@LANG_STRING@@QEAAJPEBDKIPEAPEBGPEAK@Z` at `0x1800180c2`
- `iisutil!?GetString@LANG_STRING@@QEAAJPEBDKIPEAPEBGPEAK@Z` at `0x1800180c2`

## string_xrefs

- `0x180017f28`: `clientCache`
- `0x180017f5a`: `cacheControlCustom`
- `0x180017fa8`: `cacheControlMode`
- `0x180018274`: `no-cache`
- `0x18001826d`: `,no-cache`
- `0x1800181f8`: `cacheControlMaxAge`
- `0x1800183ae`: `accessPolicy`

## pseudocode

```c
__int64 __fastcall STATIC_META_STORED_CONTEXT::Initialize(
        STATIC_META_STORED_CONTEXT *this,
        struct IHttpContext *a2,
        struct INativeSectionException **a3)
{
  __int64 v3; // rax
  __int64 (__fastcall *v7)(struct IHttpContext *); // rax
  __int64 (__fastcall ***v8)(_QWORD); // rax
  __int64 v9; // r13
  __int64 (__fastcall ***v10)(_QWORD, GUID *, __int64 *); // rax
  signed int v11; // ebx
  BOOL v12; // r15d
  const unsigned __int16 *v13; // rax
  signed int LastError; // eax
  __int64 v15; // rax
  const char *v16; // rax
  __int64 v18; // rax
  const char *v19; // r8
  char *v20; // rdx
  BOOL v21; // esi
  struct IHttpServer *v22; // r9
  const char *v23; // [rsp+30h] [rbp-D0h]
  unsigned __int16 v24; // [rsp+38h] [rbp-C8h]
  struct STRU *v25; // [rsp+40h] [rbp-C0h]
  struct IHttpTraceContext *v26; // [rsp+48h] [rbp-B8h]
  unsigned __int16 v27; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v28; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v29; // [rsp+60h] [rbp-A0h] BYREF
  struct INativeConfigurationElement *v30; // [rsp+68h] [rbp-98h] BYREF
  struct INativeConfigurationElement *v31; // [rsp+70h] [rbp-90h] BYREF
  int v32; // [rsp+78h] [rbp-88h] BYREF
  __int64 v33; // [rsp+80h] [rbp-80h] BYREF
  wchar_t *String1; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v35; // [rsp+90h] [rbp-70h] BYREF
  const unsigned __int16 *v36; // [rsp+98h] [rbp-68h] BYREF
  const unsigned __int16 *v37; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v38; // [rsp+A8h] [rbp-58h] BYREF
  const unsigned __int16 *v39; // [rsp+B0h] [rbp-50h] BYREF
  const unsigned __int16 *v40; // [rsp+B8h] [rbp-48h] BYREF
  union _LARGE_INTEGER v41; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v42[32]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v43; // [rsp+E8h] [rbp-18h]
  unsigned int v44; // [rsp+F8h] [rbp-8h]
  char v45[32]; // [rsp+100h] [rbp+0h] BYREF

  v3 = *(_QWORD *)a2;
  v33 = 0;
  v30 = 0;
  v29 = 0;
  v7 = *(__int64 (__fastcall **)(struct IHttpContext *))(v3 + 160);
  v31 = 0;
  String1 = 0;
  v36 = 0;
  v28 = 0;
  v37 = 0;
  v32 = 0;
  v39 = 0;
  v38 = 0;
  v41.QuadPart = 0;
  v8 = (__int64 (__fastcall ***)(_QWORD))v7(a2);
  v9 = (**v8)(v8);
  v10 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 56LL))(g_pGlobalInfo);
  v11 = (**v10)(v10, &IID_INativeConfigurationSystem, &v33);
  if ( v11 < 0 )
    goto LABEL_24;
  v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, struct INativeConfigurationElement **, struct INativeSectionException **, __int64 *))(*(_QWORD *)v33 + 24LL))(
          v33,
          L"system.webServer/staticContent",
          v9,
          &v30,
          a3,
          &v29);
  if ( v11 < 0 )
    goto LABEL_24;
  v11 = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v29 + 24LL))(v29, &String1);
  if ( v11 < 0 )
    goto LABEL_24;
  v12 = wcscmp_0(String1, L"MACHINE/WEBROOT/APPHOST") == 0;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  v29 = 0;
  v11 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v30 + 72LL))(
          v30,
          L"enableDocFooter",
          (char *)this + 120,
          0,
          0);
  if ( v11 < 0 )
    goto LABEL_24;
  if ( *((_DWORD *)this + 30) )
  {
    v11 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v30 + 72LL))(
            v30,
            L"isDocFooterFileName",
            (char *)this + 124,
            0,
            0);
    if ( v11 < 0 )
      goto LABEL_24;
    v11 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v30 + 64LL))(
            v30,
            L"defaultDocFooter",
            &v36,
            0,
            0);
    if ( v11 < 0 )
      goto LABEL_24;
    v11 = STRA::CopyW((STATIC_META_STORED_CONTEXT *)((char *)this + 128), v36);
    if ( v11 < 0 )
      goto LABEL_24;
    v11 = STRU::Copy((STATIC_META_STORED_CONTEXT *)((char *)this + 184), v36);
    if ( v11 < 0 )
      goto LABEL_24;
  }
  v11 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, __int64 *))(*(_QWORD *)v30 + 32LL))(
          v30,
          L"clientCache",
          &v28);
  if ( v11 < 0 )
    goto LABEL_24;
  v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v28 + 64LL))(
          v28,
          L"cacheControlCustom",
          &v39,
          0,
          0);
  if ( v11 < 0 )
    goto LABEL_24;
  v11 = STRA::CopyW((STATIC_META_STORED_CONTEXT *)((char *)this + 8), v39);
  if ( v11 < 0 )
    goto LABEL_24;
  v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v28 + 48LL))(
          v28,
          L"cacheControlMode",
          &v32,
          0,
          0);
  if ( v11 < 0 )
    goto LABEL_24;
  switch ( v32 )
  {
    case 1:
      v20 = "no-cache";
      if ( *((_DWORD *)this + 14) )
        v20 = ",no-cache";
      goto LABEL_45;
    case 2:
      v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *, _QWORD, _QWORD))(*(_QWORD *)v28 + 80LL))(
              v28,
              L"cacheControlMaxAge",
              &v38,
              0,
              0);
      if ( v11 < 0 )
        goto LABEL_24;
      v19 = "max-age=%u";
      if ( *((_DWORD *)this + 14) )
        v19 = ",max-age=%u";
      v11 = StringCchPrintfA(v45, 0x20u, v19, v38 / 10000000);
      if ( v11 < 0 )
        goto LABEL_24;
      v20 = v45;
LABEL_45:
      v11 = STRA::Append((STATIC_META_STORED_CONTEXT *)((char *)this + 8), v20);
      if ( v11 < 0 )
        goto LABEL_24;
      break;
    case 3:
      v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v28 + 64LL))(
              v28,
              L"httpExpires",
              &v37,
              0,
              0);
      if ( v11 < 0 )
        goto LABEL_24;
      v11 = STRA::CopyW((STATIC_META_STORED_CONTEXT *)((char *)this + 64), v37);
      if ( v11 < 0 )
        goto LABEL_24;
      LODWORD(v13) = StringTimeToFileTime(*((const char **)this + 12), &v41);
      if ( !(_DWORD)v13 )
      {
        v27 = 0;
        v40 = v13;
        v35 = 0;
        STRU::STRU((STRU *)v42);
        LastError = GetLastError();
        v11 = LastError;
        if ( LastError > 0 )
          v11 = (unsigned __int16)LastError | 0x80070000;
        v15 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 24LL))(a2);
        v16 = (const char *)(*(__int64 (__fastcall **)(__int64, __int64, unsigned __int16 *))(*(_QWORD *)v15 + 16LL))(
                              v15,
                              23,
                              &v27);
        if ( (int)LANG_STRING::GetString(
                    (LANG_STRING *)W3_STATIC_FILE_HANDLER::sm_pLangString,
                    v16,
                    v27,
                    0x3233u,
                    &v40,
                    &v35) >= 0
          && (int)SAFE_snwprintf((struct STRU *)v42, v40, v37) >= 0 )
        {
          v18 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 32LL))(a2);
          (*(void (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v18 + 192LL))(v18, v43, v44, 1);
        }
        STRU::~STRU((STRU *)v42);
        goto LABEL_24;
      }
      break;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v28 + 72LL))(
          v28,
          L"setEtag",
          (char *)this + 284,
          0,
          0);
  if ( v11 >= 0 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    v28 = 0;
    v11 = MIME_MAP::Initialize((STATIC_META_STORED_CONTEXT *)((char *)this + 240), v30, v12);
    if ( v11 >= 0 )
    {
      (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v30 + 16LL))(v30);
      v30 = 0;
      v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, struct INativeConfigurationElement **, struct INativeSectionException **))(*(_QWORD *)v33 + 24LL))(
              v33,
              L"system.webServer/handlers",
              v9,
              &v31,
              a3);
      if ( v11 >= 0 )
      {
        v11 = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v29 + 24LL))(v29, &String1);
        if ( v11 >= 0 )
        {
          v21 = wcscmp_0(String1, L"MACHINE/WEBROOT/APPHOST") == 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
          v29 = 0;
          v11 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, char *, _QWORD))(*(_QWORD *)v31 + 48LL))(
                  v31,
                  L"accessPolicy",
                  (char *)this + 280,
                  0);
          if ( v11 >= 0 )
          {
            v11 = META_SCRIPT_MAP::Initialize(
                    (STATIC_META_STORED_CONTEXT *)((char *)this + 264),
                    v31,
                    v21,
                    v22,
                    0,
                    (struct LANG_STRING *)&v29,
                    v23,
                    v24,
                    v25,
                    v26);
            if ( v11 >= 0 )
            {
              (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v31 + 16LL))(v31);
              v31 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
              return 0;
            }
          }
        }
      }
    }
  }
LABEL_24:
  if ( v31 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v31 + 16LL))(v31);
    v31 = 0;
  }
  if ( v28 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    v28 = 0;
  }
  if ( v29 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    v29 = 0;
  }
  if ( v30 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v30 + 16LL))(v30);
    v30 = 0;
  }
  if ( v33 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180017cc8  mov     [rsp-8+arg_18], rbx
0x180017ccd  push    rbp
0x180017cce  push    rsi
0x180017ccf  push    rdi
0x180017cd0  push    r12
0x180017cd2  push    r13
0x180017cd4  push    r14
0x180017cd6  push    r15
0x180017cd8  lea     rbp, [rsp-30h]
0x180017cdd  sub     rsp, 130h
0x180017ce4  mov     rax, cs:__security_cookie
0x180017ceb  xor     rax, rsp
0x180017cee  mov     [rbp+60h+var_40], rax
0x180017cf2  mov     rax, [rdx]
0x180017cf5  mov     rdi, rcx
0x180017cf8  mov     rcx, rdx
0x180017cfb  mov     [rbp+60h+var_E0], 0
0x180017d03  mov     r12, r8
0x180017d06  mov     [rsp+160h+var_F8], 0
0x180017d0f  mov     r14, rdx
0x180017d12  mov     [rsp+160h+var_100], 0
0x180017d1b  mov     rax, [rax+0A0h]
0x180017d22  mov     [rsp+160h+var_F0], 0
0x180017d2b  mov     [rbp+60h+String1], 0
0x180017d33  mov     [rbp+60h+var_C8], 0
0x180017d3b  mov     [rsp+160h+var_108], 0
0x180017d44  mov     [rbp+60h+var_C0], 0
0x180017d4c  mov     [rsp+160h+var_E8], 0
0x180017d54  mov     [rbp+60h+var_B0], 0
0x180017d5c  mov     [rbp+60h+var_B8], 0
0x180017d64  mov     [rbp+60h+var_A0], 0
0x180017d6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d71  mov     rdx, rax
0x180017d74  mov     rcx, [rax]
0x180017d77  mov     rax, [rcx]
0x180017d7a  mov     rcx, rdx
0x180017d7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d82  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180017d89  mov     r13, rax
0x180017d8c  mov     rdx, [rcx]
0x180017d8f  mov     rax, [rdx+38h]
0x180017d93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d98  mov     r9, rax
0x180017d9b  lea     r8, [rbp+60h+var_E0]
0x180017d9f  lea     rdx, IID_INativeConfigurationSystem
0x180017da6  mov     rcx, [rax]
0x180017da9  mov     rax, [rcx]
0x180017dac  mov     rcx, r9
0x180017daf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017db4  mov     ebx, eax
0x180017db6  test    eax, eax
0x180017db8  js      loc_1800180DA
0x180017dbe  mov     rcx, [rbp+60h+var_E0]
0x180017dc2  lea     rdx, [rsp+160h+var_100]
0x180017dc7  mov     [rsp+160h+var_138], rdx
0x180017dcc  lea     r9, [rsp+160h+var_F8]
0x180017dd1  mov     r8, r13
0x180017dd4  mov     qword ptr [rsp+160h+var_140], r12
0x180017dd9  lea     rdx, aSystemWebserve; "system.webServer/staticContent"
0x180017de0  mov     rax, [rcx]
0x180017de3  mov     rax, [rax+18h]
0x180017de7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017dec  mov     ebx, eax
0x180017dee  test    eax, eax
0x180017df0  js      loc_1800180DA
0x180017df6  mov     rcx, [rsp+160h+var_100]
0x180017dfb  lea     rdx, [rbp+60h+String1]
0x180017dff  mov     rax, [rcx]
0x180017e02  mov     rax, [rax+18h]
0x180017e06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e0b  mov     ebx, eax
0x180017e0d  test    eax, eax
0x180017e0f  js      loc_1800180DA
0x180017e15  mov     rcx, [rbp+60h+String1]; String1
0x180017e19  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180017e20  call    wcscmp_0
0x180017e25  mov     rcx, [rsp+160h+var_100]
0x180017e2a  xor     r15d, r15d
0x180017e2d  test    eax, eax
0x180017e2f  setz    r15b
0x180017e33  mov     rax, [rcx]
0x180017e36  mov     rax, [rax+10h]
0x180017e3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e3f  mov     rcx, [rsp+160h+var_F8]
0x180017e44  lea     r8, [rdi+78h]
0x180017e48  mov     [rsp+160h+var_100], 0
0x180017e51  lea     rdx, aEnabledocfoote; "enableDocFooter"
0x180017e58  xor     r9d, r9d
0x180017e5b  mov     qword ptr [rsp+160h+var_140], 0
0x180017e64  mov     rax, [rcx]
0x180017e67  mov     rax, [rax+48h]
0x180017e6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e70  mov     ebx, eax
0x180017e72  test    eax, eax
0x180017e74  js      loc_1800180DA
0x180017e7a  cmp     dword ptr [rdi+78h], 0
0x180017e7e  jz      loc_180017F1E
0x180017e84  mov     rcx, [rsp+160h+var_F8]
0x180017e89  lea     r8, [rdi+7Ch]
0x180017e8d  xor     r9d, r9d
0x180017e90  mov     qword ptr [rsp+160h+var_140], 0
0x180017e99  lea     rdx, aIsdocfooterfil; "isDocFooterFileName"
0x180017ea0  mov     rax, [rcx]
0x180017ea3  mov     rax, [rax+48h]
0x180017ea7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017eac  mov     ebx, eax
0x180017eae  test    eax, eax
0x180017eb0  js      loc_1800180DA
0x180017eb6  mov     rcx, [rsp+160h+var_F8]
0x180017ebb  lea     r8, [rbp+60h+var_C8]
0x180017ebf  xor     r9d, r9d
0x180017ec2  mov     qword ptr [rsp+160h+var_140], 0
0x180017ecb  lea     rdx, aDefaultdocfoot; "defaultDocFooter"
0x180017ed2  mov     rax, [rcx]
0x180017ed5  mov     rax, [rax+40h]
0x180017ed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ede  mov     ebx, eax
0x180017ee0  test    eax, eax
0x180017ee2  js      loc_1800180DA
0x180017ee8  mov     rdx, [rbp+60h+var_C8]
0x180017eec  lea     rcx, [rdi+80h]
0x180017ef3  call    cs:__imp_?CopyW@STRA@@QEAAJPEBG@Z; STRA::CopyW(ushort const *)
0x180017ef9  mov     ebx, eax
0x180017efb  test    eax, eax
0x180017efd  js      loc_1800180DA
0x180017f03  mov     rdx, [rbp+60h+var_C8]
0x180017f07  lea     rcx, [rdi+0B8h]
0x180017f0e  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180017f14  mov     ebx, eax
0x180017f16  test    eax, eax
0x180017f18  js      loc_1800180DA
0x180017f1e  mov     rcx, [rsp+160h+var_F8]
0x180017f23  lea     r8, [rsp+160h+var_108]
0x180017f28  lea     rdx, aClientcache; "clientCache"
0x180017f2f  mov     rax, [rcx]
0x180017f32  mov     rax, [rax+20h]
0x180017f36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f3b  mov     ebx, eax
0x180017f3d  test    eax, eax
0x180017f3f  js      loc_1800180DA
0x180017f45  mov     rcx, [rsp+160h+var_108]
0x180017f4a  lea     r8, [rbp+60h+var_B0]
0x180017f4e  xor     r9d, r9d
0x180017f51  mov     qword ptr [rsp+160h+var_140], 0
0x180017f5a  lea     rdx, aCachecontrolcu; "cacheControlCustom"
0x180017f61  mov     rax, [rcx]
0x180017f64  mov     rax, [rax+40h]
0x180017f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f6d  mov     ebx, eax
0x180017f6f  test    eax, eax
0x180017f71  js      loc_1800180DA
0x180017f77  mov     rdx, [rbp+60h+var_B0]
0x180017f7b  lea     rsi, [rdi+8]
0x180017f7f  mov     rcx, rsi
0x180017f82  call    cs:__imp_?CopyW@STRA@@QEAAJPEBG@Z; STRA::CopyW(ushort const *)
0x180017f88  mov     ebx, eax
0x180017f8a  test    eax, eax
0x180017f8c  js      loc_1800180DA
0x180017f92  mov     rcx, [rsp+160h+var_108]
0x180017f97  lea     r8, [rsp+160h+var_E8]
0x180017f9c  xor     r9d, r9d
0x180017f9f  mov     qword ptr [rsp+160h+var_140], 0
0x180017fa8  lea     rdx, aCachecontrolmo; "cacheControlMode"
0x180017faf  mov     rax, [rcx]
0x180017fb2  mov     rax, [rax+30h]
0x180017fb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017fbb  mov     ebx, eax
0x180017fbd  test    eax, eax
0x180017fbf  js      loc_1800180DA
0x180017fc5  mov     ecx, [rsp+160h+var_E8]
0x180017fc9  sub     ecx, 1
0x180017fcc  jz      loc_180018269
0x180017fd2  sub     ecx, 1
0x180017fd5  jz      loc_1800181E3
0x180017fdb  cmp     ecx, 1
0x180017fde  jnz     loc_180018292
0x180017fe4  mov     rcx, [rsp+160h+var_108]
0x180017fe9  lea     r8, [rbp+60h+var_C0]
0x180017fed  xor     r9d, r9d
0x180017ff0  mov     qword ptr [rsp+160h+var_140], 0
0x180017ff9  lea     rdx, aHttpexpires; "httpExpires"
0x180018000  mov     rax, [rcx]
0x180018003  mov     rax, [rax+40h]
0x180018007  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001800c  mov     ebx, eax
0x18001800e  test    eax, eax
0x180018010  js      loc_1800180DA
0x180018016  mov     rdx, [rbp+60h+var_C0]
0x18001801a  lea     rcx, [rdi+40h]
0x18001801e  call    cs:__imp_?CopyW@STRA@@QEAAJPEBG@Z; STRA::CopyW(ushort const *)
0x180018024  mov     ebx, eax
0x180018026  test    eax, eax
0x180018028  js      loc_1800180DA
0x18001802e  mov     rcx, [rdi+60h]
0x180018032  lea     rdx, [rbp+60h+var_A0]
0x180018036  call    cs:__imp_?StringTimeToFileTime@@YAHPEBDPEAT_LARGE_INTEGER@@@Z; StringTimeToFileTime(char const *,_LARGE_INTEGER *)
0x18001803c  test    eax, eax
0x18001803e  jnz     loc_180018292
0x180018044  lea     rcx, [rbp+60h+var_98]
0x180018048  mov     [rsp+160h+var_110], ax
0x18001804d  mov     [rbp+60h+var_A8], rax
0x180018051  mov     [rbp+60h+var_D0], eax
0x180018054  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18001805a  call    cs:__imp_GetLastError
0x180018060  mov     ebx, eax
0x180018062  test    eax, eax
0x180018064  jle     short loc_18001806F
0x180018066  movzx   ebx, ax
0x180018069  or      ebx, 80070000h
0x18001806f  mov     rax, [r14]
0x180018072  mov     rcx, r14
0x180018075  mov     rax, [rax+18h]
0x180018079  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001807e  mov     r9, rax
0x180018081  lea     r8, [rsp+160h+var_110]
0x180018086  mov     edx, 17h
0x18001808b  mov     rcx, [rax]
0x18001808e  mov     rax, [rcx+10h]
0x180018092  mov     rcx, r9
0x180018095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001809a  movzx   r8d, [rsp+160h+var_110]
0x1800180a0  lea     rcx, [rbp+60h+var_D0]
0x1800180a4  mov     [rsp+160h+var_138], rcx
0x1800180a9  mov     r9d, 3233h
0x1800180af  lea     rcx, [rbp+60h+var_A8]
0x1800180b3  mov     rdx, rax
0x1800180b6  mov     qword ptr [rsp+160h+var_140], rcx
0x1800180bb  mov     rcx, cs:?sm_pLangString@W3_STATIC_FILE_HANDLER@@2PEAVLANG_STRING@@EA; LANG_STRING * W3_STATIC_FILE_HANDLER::sm_pLangString
0x1800180c2  call    cs:__imp_?GetString@LANG_STRING@@QEAAJPEBDKIPEAPEBGPEAK@Z; LANG_STRING::GetString(char const *,ulong,uint,ushort const * *,ulong *)
0x1800180c8  lea     rcx, [rbp+60h+var_98]
0x1800180cc  test    eax, eax
0x1800180ce  jns     loc_180018194
0x1800180d4  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800180da  mov     rcx, [rsp+160h+var_F0]
0x1800180df  test    rcx, rcx
0x1800180e2  jz      short loc_1800180F9
0x1800180e4  mov     rax, [rcx]
0x1800180e7  mov     rax, [rax+10h]
0x1800180eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800180f0  mov     [rsp+160h+var_F0], 0
0x1800180f9  mov     rcx, [rsp+160h+var_108]
0x1800180fe  test    rcx, rcx
0x180018101  jz      short loc_180018118
0x180018103  mov     rax, [rcx]
0x180018106  mov     rax, [rax+10h]
0x18001810a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001810f  mov     [rsp+160h+var_108], 0
0x180018118  mov     rcx, [rsp+160h+var_100]
0x18001811d  test    rcx, rcx
0x180018120  jz      short loc_180018137
0x180018122  mov     rax, [rcx]
0x180018125  mov     rax, [rax+10h]
0x180018129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001812e  mov     [rsp+160h+var_100], 0
0x180018137  mov     rcx, [rsp+160h+var_F8]
0x18001813c  test    rcx, rcx
0x18001813f  jz      short loc_180018156
0x180018141  mov     rax, [rcx]
0x180018144  mov     rax, [rax+10h]
0x180018148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001814d  mov     [rsp+160h+var_F8], 0
0x180018156  mov     rcx, [rbp+60h+var_E0]
0x18001815a  test    rcx, rcx
0x18001815d  jz      short loc_18001816B
0x18001815f  mov     rax, [rcx]
0x180018162  mov     rax, [rax+10h]
0x180018166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001816b  mov     eax, ebx
0x18001816d  mov     rcx, [rbp+60h+var_40]
0x180018171  xor     rcx, rsp; StackCookie
0x180018174  call    __security_check_cookie
0x180018179  mov     rbx, [rsp+160h+arg_18]
0x180018181  add     rsp, 130h
0x180018188  pop     r15
0x18001818a  pop     r14
0x18001818c  pop     r13
0x18001818e  pop     r12
0x180018190  pop     rdi
0x180018191  pop     rsi
0x180018192  pop     rbp
0x180018193  retn
0x180018194  mov     r8, [rbp+60h+var_C0]
0x180018198  mov     rdx, [rbp+60h+var_A8]
0x18001819c  call    cs:__imp_?SAFE_snwprintf@@YAJPEAVSTRU@@PEBGZZ; SAFE_snwprintf(STRU *,ushort const *,...)
0x1800181a2  test    eax, eax
0x1800181a4  jns     short loc_1800181AF
0x1800181a6  lea     rcx, [rbp+60h+var_98]
0x1800181aa  jmp     loc_1800180D4
0x1800181af  mov     rax, [r14]
0x1800181b2  mov     rcx, r14
0x1800181b5  mov     rax, [rax+20h]
0x1800181b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800181be  mov     r8d, [rbp+60h+var_68]
0x1800181c2  mov     r10, rax
0x1800181c5  mov     rdx, [rbp+60h+var_78]
0x1800181c9  mov     r9d, 1
0x1800181cf  mov     rcx, [rax]
0x1800181d2  mov     rax, [rcx+0C0h]
0x1800181d9  mov     rcx, r10
0x1800181dc  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
