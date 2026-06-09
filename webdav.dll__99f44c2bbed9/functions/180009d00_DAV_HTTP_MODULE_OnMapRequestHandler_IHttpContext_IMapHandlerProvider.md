# DAV_HTTP_MODULE::OnMapRequestHandler(IHttpContext *,IMapHandlerProvider *)

- ea: `0x180009d00`
- end: `0x18000a041`
- name: `?OnMapRequestHandler@DAV_HTTP_MODULE@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIMapHandlerProvider@@@Z`
- size: `833`
- prototype: `enum REQUEST_NOTIFICATION_STATUS __high(struct IHttpContext *, struct IMapHandlerProvider *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000379c`
- `0x180005d3c`
- `0x180005e2c`
- `0x180009d00`
- `0x180010098`
- `0x180019ea0`
- `0x18001a250`
- `0x18001b2cc`
- `0x180023010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180009efe`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180009fc2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180009efe`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180009fc2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a00f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a00f`

## string_xrefs

- `0x180009e61`: `Impersonation Failure`

## pseudocode

```c
__int64 __fastcall DAV_HTTP_MODULE::OnMapRequestHandler(__int64 a1, struct IHttpContext *a2, __int64 a3)
{
  __int64 v5; // rax
  const wchar_t *v6; // rdx
  __int64 v8; // rdx
  struct IHttpFileInfo *v9; // rax
  __int64 v10; // rax
  int v11; // esi
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  const unsigned __int16 *v16; // rax
  int CachedFileInfo; // eax
  int v18; // esi
  unsigned int v19; // ecx
  struct MAPPED_HTTP_STATUS near **v20; // rdi
  __int64 v21; // rax
  __int64 v22; // rax
  struct IHttpFileInfo *v23; // [rsp+40h] [rbp-20h] BYREF
  struct DAV_SITE_STORED_CONTEXT *v24[3]; // [rsp+48h] [rbp-18h] BYREF
  int v25; // [rsp+98h] [rbp+38h] BYREF

  v24[0] = 0;
  v23 = 0;
  v25 = 0;
  if ( (unsigned int)IsDavRequest(a2) )
  {
    if ( !(unsigned int)IsVerbAllowed(a2, &v25) )
    {
      v5 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
      v6 = L"Verb Not Allowed";
LABEL_4:
      (*(void (__fastcall **)(__int64, const wchar_t *, _QWORD, _QWORD, char))(*(_QWORD *)v5 + 32LL))(v5, v6, 0, 0, 3);
      HandleMethodNotAllowed(a2);
      return 2;
    }
    if ( !v25 )
    {
      if ( (int)DAV_SITE_STORED_CONTEXT::GetParsedMetadata(a2, v24, 1, 1) < 0 )
        return 2;
      v8 = *(_QWORD *)a2;
      if ( !*((_DWORD *)v24[0] + 4) )
      {
        v5 = (*(__int64 (__fastcall **)(struct IHttpContext *))(v8 + 272))(a2);
        v6 = L"WebDAV Disabled";
        goto LABEL_4;
      }
      v9 = (struct IHttpFileInfo *)(*(__int64 (__fastcall **)(struct IHttpContext *))(v8 + 208))(a2);
      v23 = v9;
      if ( v9 )
      {
        (*(void (__fastcall **)(struct IHttpFileInfo *))(*(_QWORD *)v9 + 8LL))(v9);
      }
      else
      {
        v10 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 24LL))(a2);
        if ( (unsigned int)(*(_DWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10) + 36) - 4) <= 1 )
        {
          LODWORD(v24[0]) = 0;
          v24[1] = 0;
          v11 = AUTO_IMPERSONATE::Impersonate((AUTO_IMPERSONATE *)v24, a2);
          v12 = *(_QWORD *)a2;
          if ( v11 < 0 )
          {
            v13 = (*(__int64 (__fastcall **)(struct IHttpContext *))(v12 + 272))(a2);
            (*(void (__fastcall **)(__int64, const wchar_t *, _QWORD, _QWORD, char))(*(_QWORD *)v13 + 32LL))(
              v13,
              L"Impersonation Failure",
              0,
              (unsigned int)v11,
              3);
            v14 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 32LL))(a2);
            *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14) + 536) = 0;
            v15 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 32LL))(a2);
            (*(void (__fastcall **)(__int64, __int64, const char *, _QWORD, _DWORD, _QWORD, _DWORD))(*(_QWORD *)v15 + 24LL))(
              v15,
              500,
              "Internal Server Error",
              0,
              0,
              0,
              0);
LABEL_14:
            (*(void (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 200LL))(a2);
            if ( LODWORD(v24[0]) )
              RevertToSelf();
            return 2;
          }
          v16 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IHttpContext *, _QWORD))(v12 + 168))(a2, 0);
          CachedFileInfo = GetCachedFileInfo(g_pGlobalInfo, a2, v16, &v23);
          v18 = CachedFileInfo;
          if ( CachedFileInfo < 0 )
          {
            v19 = 0;
            v20 = &g_StatusMap;
            while ( *(_DWORD *)v20 != CachedFileInfo )
            {
              ++v19;
              v20 += 3;
              if ( v19 >= 0x1C )
              {
                v20 = (struct MAPPED_HTTP_STATUS near **)&g_DefaultStatus;
                break;
              }
            }
            DAV_TRACE::TraceMappedHResult(a2, CachedFileInfo, (struct MAPPED_HTTP_STATUS *)v20);
            v21 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 32LL))(a2);
            *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 8LL))(v21) + 536) = 0;
            v22 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 32LL))(a2);
            (*(void (__fastcall **)(__int64, _QWORD, struct MAPPED_HTTP_STATUS near *, _QWORD, int, _QWORD, _DWORD))(*(_QWORD *)v22 + 24LL))(
              v22,
              *((unsigned __int16 *)v20 + 2),
              v20[1],
              *((unsigned __int16 *)v20 + 8),
              v18,
              0,
              0);
            goto LABEL_14;
          }
          if ( LODWORD(v24[0]) )
            RevertToSelf();
        }
      }
      (*(void (__fastcall **)(__int64, META_SCRIPT_MAP_ENTRY *))(*(_QWORD *)a3 + 16LL))(a3, g_StaticScriptMap);
      (*(void (__fastcall **)(__int64, struct IHttpFileInfo *))(*(_QWORD *)a3 + 24LL))(a3, v23);
      if ( DAV_HTTP_MODULE::sm_pSqmWriter )
        _InterlockedIncrement((volatile signed __int32 *)(**((_QWORD **)DAV_HTTP_MODULE::sm_pSqmWriter + 1)
                                                        + *(_QWORD *)(*((_QWORD *)DAV_HTTP_MODULE::sm_pSqmWriter + 1)
                                                                    + 8LL)
                                                        * ((unsigned __int64)GetCurrentThreadId()
                                                         % *(_QWORD *)(*((_QWORD *)DAV_HTTP_MODULE::sm_pSqmWriter + 1)
                                                                     + 16LL))));
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180009d00  mov     [rsp-18h+arg_0], rbx
0x180009d05  mov     [rsp-18h+arg_8], rsi
0x180009d0a  push    rbp
0x180009d0b  push    rdi
0x180009d0c  push    r14
0x180009d0e  mov     rbp, rsp
0x180009d11  sub     rsp, 60h
0x180009d15  xor     r14d, r14d
0x180009d18  mov     rcx, rdx; struct IHttpContext *
0x180009d1b  mov     [rbp+var_18], r14
0x180009d1f  mov     rdi, r8
0x180009d22  mov     [rbp+var_20], r14
0x180009d26  mov     rbx, rdx
0x180009d29  mov     [rbp+arg_18], r14d
0x180009d2d  call    ?IsDavRequest@@YAHPEAVIHttpContext@@@Z; IsDavRequest(IHttpContext *)
0x180009d32  test    eax, eax
0x180009d34  jz      loc_18000A02A
0x180009d3a  lea     rdx, [rbp+arg_18]; int *
0x180009d3e  mov     rcx, rbx; struct IHttpContext *
0x180009d41  call    ?IsVerbAllowed@@YAHPEAVIHttpContext@@PEAH@Z; IsVerbAllowed(IHttpContext *,int *)
0x180009d46  test    eax, eax
0x180009d48  jnz     short loc_180009D92
0x180009d4a  mov     rax, [rbx]
0x180009d4d  mov     rcx, rbx
0x180009d50  mov     rax, [rax+110h]
0x180009d57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d5c  lea     rdx, aVerbNotAllowed; "Verb Not Allowed"
0x180009d63  mov     rcx, [rax]
0x180009d66  mov     r10, rax
0x180009d69  xor     r9d, r9d
0x180009d6c  mov     byte ptr [rsp+60h+var_40], 3
0x180009d71  xor     r8d, r8d
0x180009d74  mov     rax, [rcx+20h]
0x180009d78  mov     rcx, r10
0x180009d7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d80  mov     rcx, rbx; struct IHttpContext *
0x180009d83  call    ?HandleMethodNotAllowed@@YAXPEAVIHttpContext@@@Z; HandleMethodNotAllowed(IHttpContext *)
0x180009d88  mov     eax, 2
0x180009d8d  jmp     loc_18000A02C
0x180009d92  cmp     [rbp+arg_18], r14d
0x180009d96  jnz     loc_18000A02A
0x180009d9c  mov     r9d, 1; int
0x180009da2  lea     rdx, [rbp+var_18]; struct DAV_SITE_STORED_CONTEXT **
0x180009da6  mov     r8d, r9d; int
0x180009da9  mov     rcx, rbx; struct IHttpContext *
0x180009dac  call    ?GetParsedMetadata@DAV_SITE_STORED_CONTEXT@@SAJPEAVIHttpContext@@PEAPEAV1@HH@Z; DAV_SITE_STORED_CONTEXT::GetParsedMetadata(IHttpContext *,DAV_SITE_STORED_CONTEXT * *,int,int)
0x180009db1  test    eax, eax
0x180009db3  js      short loc_180009D88
0x180009db5  mov     rax, [rbp+var_18]
0x180009db9  mov     rcx, rbx
0x180009dbc  mov     rdx, [rbx]
0x180009dbf  cmp     [rax+10h], r14d
0x180009dc3  jnz     short loc_180009DDA
0x180009dc5  mov     rax, [rdx+110h]
0x180009dcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009dd1  lea     rdx, aWebdavDisabled; "WebDAV Disabled"
0x180009dd8  jmp     short loc_180009D63
0x180009dda  mov     rax, [rdx+0D0h]
0x180009de1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009de6  mov     [rbp+var_20], rax
0x180009dea  mov     rcx, rax
0x180009ded  test    rax, rax
0x180009df0  jnz     loc_180009FCA
0x180009df6  mov     rax, [rbx]
0x180009df9  mov     rcx, rbx
0x180009dfc  mov     rax, [rax+18h]
0x180009e00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e05  mov     rdx, rax
0x180009e08  mov     rcx, [rax]
0x180009e0b  mov     rax, [rcx+8]
0x180009e0f  mov     rcx, rdx
0x180009e12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e17  mov     ecx, [rax+24h]
0x180009e1a  sub     ecx, 4
0x180009e1d  cmp     ecx, 1
0x180009e20  ja      loc_180009FD6
0x180009e26  mov     rdx, rbx; struct IHttpContext *
0x180009e29  mov     dword ptr [rbp+var_18], r14d
0x180009e2d  lea     rcx, [rbp+var_18]; this
0x180009e31  mov     [rbp+var_10], r14
0x180009e35  call    ?Impersonate@AUTO_IMPERSONATE@@QEAAJPEAVIHttpContext@@@Z; AUTO_IMPERSONATE::Impersonate(IHttpContext *)
0x180009e3a  mov     esi, eax
0x180009e3c  mov     rcx, rbx
0x180009e3f  mov     rax, [rbx]
0x180009e42  test    esi, esi
0x180009e44  jns     loc_180009F09
0x180009e4a  mov     rax, [rax+110h]
0x180009e51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e56  mov     r10, rax
0x180009e59  mov     byte ptr [rsp+60h+var_40], 3
0x180009e5e  mov     r9d, esi
0x180009e61  lea     rdx, aImpersonationF; "Impersonation Failure"
0x180009e68  xor     r8d, r8d
0x180009e6b  mov     rcx, [rax]
0x180009e6e  mov     rax, [rcx+20h]
0x180009e72  mov     rcx, r10
0x180009e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e7a  mov     rax, [rbx]
0x180009e7d  mov     rcx, rbx
0x180009e80  mov     rax, [rax+20h]
0x180009e84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e89  mov     rdx, rax
0x180009e8c  mov     rcx, [rax]
0x180009e8f  mov     rax, [rcx+8]
0x180009e93  mov     rcx, rdx
0x180009e96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e9b  mov     rcx, rbx
0x180009e9e  mov     [rax+218h], r14w
0x180009ea6  mov     rax, [rbx]
0x180009ea9  mov     rax, [rax+20h]
0x180009ead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009eb2  mov     [rsp+60h+var_30], r14d
0x180009eb7  lea     r8, aInternalServer; "Internal Server Error"
0x180009ebe  mov     [rsp+60h+var_38], r14
0x180009ec3  xor     r9d, r9d
0x180009ec6  mov     [rsp+60h+var_40], r14d
0x180009ecb  mov     edx, 1F4h
0x180009ed0  mov     rcx, [rax]
0x180009ed3  mov     r10, rax
0x180009ed6  mov     rax, [rcx+18h]
0x180009eda  mov     rcx, r10
0x180009edd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ee2  mov     rax, [rbx]
0x180009ee5  mov     rcx, rbx
0x180009ee8  mov     rax, [rax+0C8h]
0x180009eef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ef4  cmp     dword ptr [rbp+var_18], r14d
0x180009ef8  jz      loc_180009D88
0x180009efe  call    cs:__imp_RevertToSelf
0x180009f04  jmp     loc_180009D88
0x180009f09  mov     rax, [rax+0A8h]
0x180009f10  xor     edx, edx
0x180009f12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f17  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; struct IHttpServer *
0x180009f1e  lea     r9, [rbp+var_20]; struct IHttpFileInfo **
0x180009f22  mov     r8, rax; unsigned __int16 *
0x180009f25  mov     rdx, rbx; struct IHttpContext *
0x180009f28  call    ?GetCachedFileInfo@@YAJPEAVIHttpServer@@PEAVIHttpContext@@PEBGPEAPEAVIHttpFileInfo@@@Z; GetCachedFileInfo(IHttpServer *,IHttpContext *,ushort const *,IHttpFileInfo * *)
0x180009f2d  mov     esi, eax
0x180009f2f  test    eax, eax
0x180009f31  jns     loc_180009FBC
0x180009f37  mov     ecx, r14d
0x180009f3a  lea     rdi, ?g_StatusMap@@3PAUMAPPED_HTTP_STATUS@@A; MAPPED_HTTP_STATUS near * g_StatusMap
0x180009f41  cmp     [rdi], esi
0x180009f43  jz      short loc_180009F57
0x180009f45  inc     ecx
0x180009f47  add     rdi, 18h
0x180009f4b  cmp     ecx, 1Ch
0x180009f4e  jb      short loc_180009F41
0x180009f50  lea     rdi, ?g_DefaultStatus@@3UMAPPED_HTTP_STATUS@@A; MAPPED_HTTP_STATUS g_DefaultStatus
0x180009f57  mov     r8, rdi; struct MAPPED_HTTP_STATUS *
0x180009f5a  mov     edx, esi; int
0x180009f5c  mov     rcx, rbx; struct IHttpContext *
0x180009f5f  call    ?TraceMappedHResult@DAV_TRACE@@SAXPEAVIHttpContext@@JPEAUMAPPED_HTTP_STATUS@@@Z; DAV_TRACE::TraceMappedHResult(IHttpContext *,long,MAPPED_HTTP_STATUS *)
0x180009f64  mov     rax, [rbx]
0x180009f67  mov     rcx, rbx
0x180009f6a  mov     rax, [rax+20h]
0x180009f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f73  mov     rdx, rax
0x180009f76  mov     rcx, [rax]
0x180009f79  mov     rax, [rcx+8]
0x180009f7d  mov     rcx, rdx
0x180009f80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f85  mov     rcx, rbx
0x180009f88  mov     [rax+218h], r14w
0x180009f90  mov     rax, [rbx]
0x180009f93  mov     rax, [rax+20h]
0x180009f97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f9c  movzx   r9d, word ptr [rdi+10h]
0x180009fa1  mov     r8, [rdi+8]
0x180009fa5  movzx   edx, word ptr [rdi+4]
0x180009fa9  mov     [rsp+60h+var_30], r14d
0x180009fae  mov     [rsp+60h+var_38], r14
0x180009fb3  mov     [rsp+60h+var_40], esi
0x180009fb7  jmp     loc_180009ED0
0x180009fbc  cmp     dword ptr [rbp+var_18], r14d
0x180009fc0  jz      short loc_180009FD6
0x180009fc2  call    cs:__imp_RevertToSelf
0x180009fc8  jmp     short loc_180009FD6
0x180009fca  mov     rax, [rax]
0x180009fcd  mov     rax, [rax+8]
0x180009fd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fd6  mov     rax, [rdi]
0x180009fd9  mov     rcx, rdi
0x180009fdc  mov     rdx, cs:?g_StaticScriptMap@@3PEAVMETA_SCRIPT_MAP_ENTRY@@EA; META_SCRIPT_MAP_ENTRY * g_StaticScriptMap
0x180009fe3  mov     rax, [rax+10h]
0x180009fe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fec  mov     rax, [rdi]
0x180009fef  mov     rcx, rdi
0x180009ff2  mov     rdx, [rbp+var_20]
0x180009ff6  mov     rax, [rax+18h]
0x180009ffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fff  mov     rbx, cs:?sm_pSqmWriter@DAV_HTTP_MODULE@@0PEAVWEBDAV_SQM_WRITER@@EA; WEBDAV_SQM_WRITER * DAV_HTTP_MODULE::sm_pSqmWriter
0x18000a006  test    rbx, rbx
0x18000a009  jz      short loc_18000A02A
0x18000a00b  mov     rbx, [rbx+8]
0x18000a00f  call    cs:__imp_GetCurrentThreadId
0x18000a015  mov     eax, eax
0x18000a017  xor     edx, edx
0x18000a019  div     qword ptr [rbx+10h]
0x18000a01d  mov     eax, edx
0x18000a01f  imul    rax, [rbx+8]
0x18000a024  add     rax, [rbx]
0x18000a027  lock inc dword ptr [rax]
0x18000a02a  xor     eax, eax
0x18000a02c  lea     r11, [rsp+60h+var_s0]
0x18000a031  mov     rbx, [r11+20h]
0x18000a035  mov     rsi, [r11+28h]
0x18000a039  mov     rsp, r11
0x18000a03c  pop     r14
0x18000a03e  pop     rdi
0x18000a03f  pop     rbp
0x18000a040  retn
```
