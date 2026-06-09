# WARMUP_APPLICATION_CONTEXT::sm_WarmupThread(void *)

- ea: `0x180004bc0`
- end: `0x180004f1d`
- name: `?sm_WarmupThread@WARMUP_APPLICATION_CONTEXT@@CAKPEAX@Z`
- size: `861`
- prototype: `__int64 __fastcall(_QWORD *Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004204`
- `0x180004bc0`
- `0x180004fe0`
- `0x180006010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180004ef5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180004ef5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004eb6`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004eb6`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004c09`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004c09`
- `iisutil!PuDbgPrint` at `0x180004d20`
- `iisutil!PuDbgPrint` at `0x180004e36`
- `iisutil!PuDbgPrint` at `0x180004ea8`
- `iisutil!PuDbgPrint` at `0x180004d20`
- `iisutil!PuDbgPrint` at `0x180004e36`
- `iisutil!PuDbgPrint` at `0x180004ea8`

## string_xrefs

- `0x180004ca4`: `User-Agent`
- `0x180004cfd`: `servercommon\inetsrv\iis\iisrearc\iis70\appwarmup\warmupcontext.cxx`
- `0x180004e04`: `servercommon\inetsrv\iis\iisrearc\iis70\appwarmup\warmupcontext.cxx`
- `0x180004e85`: `servercommon\inetsrv\iis\iisrearc\iis70\appwarmup\warmupcontext.cxx`
- `0x180004cf0`: `WARMUP_APPLICATION_CONTEXT::sm_WarmupThread`
- `0x180004df8`: `WARMUP_APPLICATION_CONTEXT::sm_WarmupThread`
- `0x180004e77`: `WARMUP_APPLICATION_CONTEXT::sm_WarmupThread`

## pseudocode

```c
__int64 __fastcall WARMUP_APPLICATION_CONTEXT::sm_WarmupThread(_QWORD *Parameter)
{
  char *v1; // r13
  char *v2; // r12
  _QWORD *v3; // rax
  char *v4; // rbx
  int v5; // r15d
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  int v10; // ebx
  const char *v11; // rdi
  int v12; // esi
  int v13; // r14d
  __int64 v14; // rax
  __int64 v15; // rax
  HANDLE *v16; // rcx
  _WORD v18[2]; // [rsp+60h] [rbp-59h] BYREF
  unsigned __int16 v19; // [rsp+64h] [rbp-55h] BYREF
  struct IHttpContext *v20; // [rsp+68h] [rbp-51h] BYREF
  _WORD v21[2]; // [rsp+70h] [rbp-49h] BYREF
  int v22; // [rsp+74h] [rbp-45h] BYREF
  const char *v23; // [rsp+78h] [rbp-41h] BYREF
  _QWORD *v24; // [rsp+80h] [rbp-39h]
  _BYTE v25[56]; // [rsp+88h] [rbp-31h] BYREF

  v1 = (char *)(Parameter + 11);
  v24 = Parameter;
  v2 = (char *)Parameter[11];
  v3 = Parameter;
  if ( v2 != (char *)(Parameter + 11) )
  {
    do
    {
      v20 = 0;
      STRU::STRU((STRU *)v25);
      v4 = v2 - 232;
      v5 = (*(__int64 (__fastcall **)(struct IGlobalApplicationPreloadProvider2 *, struct IHttpContext **))(*(_QWORD *)g_pPreloadProvider + 8LL))(
             g_pPreloadProvider,
             &v20);
      if ( v5 >= 0 )
      {
        v5 = InitializeWarmupRequest((struct WARMUP_REQUEST *)(v2 - 232), v20);
        if ( v5 >= 0 )
        {
          v5 = (*(__int64 (__fastcall **)(struct IHttpContext *, const char *, const wchar_t *))(*(_QWORD *)v20 + 136LL))(
                 v20,
                 "WARMUP_REQUEST",
                 L"1");
          if ( v5 >= 0 )
          {
            v6 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v20 + 24LL))(v20);
            v5 = (*(__int64 (__fastcall **)(__int64, const char *, const char *, __int64, int))(*(_QWORD *)v6 + 40LL))(
                   v6,
                   "User-Agent",
                   "IIS Application Initialization Warmup",
                   37,
                   1);
            if ( v5 >= 0 )
            {
              if ( (g_dwDebugFlags & 3) != 0 )
              {
                v7 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v20 + 24LL))(v20);
                v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
                PuDbgPrint(
                  g_pDebug,
                  "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\appwarmup\\warmupcontext.cxx",
                  472,
                  "WARMUP_APPLICATION_CONTEXT::sm_WarmupThread",
                  "Running warmup request [%S]\r\n",
                  *(const wchar_t **)(v8 + 72));
              }
              v5 = (*(__int64 (__fastcall **)(struct IGlobalApplicationPreloadProvider2 *, struct IHttpContext *, _QWORD))(*(_QWORD *)g_pPreloadProvider + 16LL))(
                     g_pPreloadProvider,
                     v20,
                     0);
              if ( v5 >= 0 )
              {
                v19 = 0;
                v18[0] = 0;
                v23 = 0;
                v21[0] = 0;
                v22 = 0;
                v9 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v20 + 32LL))(v20);
                (*(void (__fastcall **)(__int64, unsigned __int16 *, _WORD *, const char **, _WORD *, int *, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v9 + 184LL))(
                  v9,
                  &v19,
                  v18,
                  &v23,
                  v21,
                  &v22,
                  0,
                  0,
                  0,
                  0);
                if ( (g_dwDebugFlags & 3) != 0 )
                {
                  v10 = v22;
                  v11 = v23;
                  v12 = v18[0];
                  v13 = v19;
                  v14 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v20 + 24LL))(v20);
                  v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
                  PuDbgPrint(
                    g_pDebug,
                    "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\appwarmup\\warmupcontext.cxx",
                    508,
                    "WARMUP_APPLICATION_CONTEXT::sm_WarmupThread",
                    "Warmup Request [%S] returned \"%d.%d %s\", hr=0x%08x.\r\n",
                    *(const wchar_t **)(v15 + 72),
                    v13,
                    v12,
                    v11,
                    v10);
                  v4 = v2 - 232;
                }
              }
            }
          }
        }
      }
      if ( v20 )
      {
        (*(void (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v20 + 256LL))(v20);
        v20 = 0;
      }
      if ( v5 < 0 && (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\appwarmup\\warmupcontext.cxx",
          524,
          "WARMUP_APPLICATION_CONTEXT::sm_WarmupThread",
          "Error 0x%08x running warmup request [%S].\r\n",
          v5,
          *((const wchar_t **)v4 + 26));
      v2 = *(char **)v2;
      STRU::~STRU((STRU *)v25);
    }
    while ( v2 != v1 );
    v3 = v24;
  }
  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v3[2] + 40LL))(v3[2]);
  v16 = (HANDLE *)g_pPreloadBlock;
  if ( g_pPreloadBlock && _InterlockedExchangeAdd((volatile signed __int32 *)g_pPreloadBlock, 0xFFFFFFFF) == 1 )
    SetEvent(v16[1]);
  return 0;
}

```

## disassembly

```asm
0x180004bc0  push    rbp
0x180004bc2  push    rbx
0x180004bc3  push    rsi
0x180004bc4  push    rdi
0x180004bc5  push    r12
0x180004bc7  push    r13
0x180004bc9  push    r14
0x180004bcb  push    r15
0x180004bcd  lea     rbp, [rsp-1Fh]
0x180004bd2  sub     rsp, 0D8h
0x180004bd9  mov     rax, cs:__security_cookie
0x180004be0  xor     rax, rsp
0x180004be3  mov     [rbp+57h+var_50], rax
0x180004be7  lea     r13, [rcx+58h]
0x180004beb  mov     [rbp+57h+var_90], rcx
0x180004bef  mov     r12, [r13+0]
0x180004bf3  xor     edi, edi
0x180004bf5  mov     rax, rcx
0x180004bf8  cmp     r12, r13
0x180004bfb  jz      loc_180004EC9
0x180004c01  lea     rcx, [rbp+57h+var_88]
0x180004c05  mov     [rbp+57h+var_A8], rdi
0x180004c09  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180004c0f  mov     rcx, cs:?g_pPreloadProvider@@3PEAVIGlobalApplicationPreloadProvider2@@EA; IGlobalApplicationPreloadProvider2 * g_pPreloadProvider
0x180004c16  lea     rdx, [rbp+57h+var_A8]
0x180004c1a  lea     rbx, [r12-0E8h]
0x180004c22  mov     rax, [rcx]
0x180004c25  mov     rax, [rax+8]
0x180004c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c2e  mov     r15d, eax
0x180004c31  test    eax, eax
0x180004c33  js      loc_180004E46
0x180004c39  mov     rdx, [rbp+57h+var_A8]; struct IHttpContext *
0x180004c3d  mov     rcx, rbx; struct WARMUP_REQUEST *
0x180004c40  call    ?InitializeWarmupRequest@@YAJPEAUWARMUP_REQUEST@@PEAVIHttpContext@@@Z; InitializeWarmupRequest(WARMUP_REQUEST *,IHttpContext *)
0x180004c45  mov     r15d, eax
0x180004c48  test    eax, eax
0x180004c4a  js      loc_180004E46
0x180004c50  mov     rcx, [rbp+57h+var_A8]
0x180004c54  lea     r8, a1; "1"
0x180004c5b  lea     rdx, aWarmupRequest; "WARMUP_REQUEST"
0x180004c62  mov     rax, [rcx]
0x180004c65  mov     rax, [rax+88h]
0x180004c6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c71  mov     r15d, eax
0x180004c74  test    eax, eax
0x180004c76  js      loc_180004E46
0x180004c7c  mov     rcx, [rbp+57h+var_A8]
0x180004c80  mov     rax, [rcx]
0x180004c83  mov     rax, [rax+18h]
0x180004c87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c8c  mov     r10, rax
0x180004c8f  mov     dword ptr [rsp+110h+var_F0], 1
0x180004c97  mov     r9d, 25h ; '%'
0x180004c9d  lea     r8, aIisApplication_0; "IIS Application Initialization Warmup"
0x180004ca4  lea     rdx, aUserAgent; "User-Agent"
0x180004cab  mov     rcx, [rax]
0x180004cae  mov     rax, [rcx+28h]
0x180004cb2  mov     rcx, r10
0x180004cb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cba  mov     r15d, eax
0x180004cbd  test    eax, eax
0x180004cbf  js      loc_180004E46
0x180004cc5  test    byte ptr cs:g_dwDebugFlags, 3
0x180004ccc  jz      short loc_180004D26
0x180004cce  mov     rcx, [rbp+57h+var_A8]
0x180004cd2  mov     rax, [rcx]
0x180004cd5  mov     rax, [rax+18h]
0x180004cd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cde  mov     rdx, rax
0x180004ce1  mov     rcx, [rax]
0x180004ce4  mov     rax, [rcx+8]
0x180004ce8  mov     rcx, rdx
0x180004ceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cf0  lea     r9, aWarmupApplicat_1; "WARMUP_APPLICATION_CONTEXT::sm_WarmupTh"...
0x180004cf7  mov     r8d, 1D8h
0x180004cfd  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180004d04  mov     rcx, [rax+48h]
0x180004d08  lea     rax, aRunningWarmupR; "Running warmup request [%S]\r\n"
0x180004d0f  mov     [rsp+110h+var_E8], rcx
0x180004d14  mov     rcx, cs:g_pDebug
0x180004d1b  mov     [rsp+110h+var_F0], rax
0x180004d20  call    cs:__imp_PuDbgPrint
0x180004d26  mov     rcx, cs:?g_pPreloadProvider@@3PEAVIGlobalApplicationPreloadProvider2@@EA; IGlobalApplicationPreloadProvider2 * g_pPreloadProvider
0x180004d2d  xor     r8d, r8d
0x180004d30  mov     rdx, [rbp+57h+var_A8]
0x180004d34  mov     rax, [rcx]
0x180004d37  mov     rax, [rax+10h]
0x180004d3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d40  mov     r15d, eax
0x180004d43  test    eax, eax
0x180004d45  js      loc_180004E46
0x180004d4b  mov     rcx, [rbp+57h+var_A8]
0x180004d4f  mov     [rbp+57h+var_AC], di
0x180004d53  mov     [rbp+57h+var_B0], di
0x180004d57  mov     [rbp+57h+var_98], rdi
0x180004d5b  mov     [rbp+57h+var_A0], di
0x180004d5f  mov     [rbp+57h+var_9C], edi
0x180004d62  mov     rax, [rcx]
0x180004d65  mov     rax, [rax+20h]
0x180004d69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d6e  mov     [rsp+110h+var_C8], rdi
0x180004d73  lea     r9, [rbp+57h+var_98]
0x180004d77  mov     [rsp+110h+var_D0], rdi
0x180004d7c  lea     r8, [rbp+57h+var_B0]
0x180004d80  mov     r10, rax
0x180004d83  mov     [rsp+110h+var_D8], rdi
0x180004d88  mov     rcx, [rax]
0x180004d8b  lea     rdx, [rbp+57h+var_AC]
0x180004d8f  mov     [rsp+110h+var_E0], rdi
0x180004d94  mov     rax, [rcx+0B8h]
0x180004d9b  lea     rcx, [rbp+57h+var_9C]
0x180004d9f  mov     [rsp+110h+var_E8], rcx
0x180004da4  lea     rcx, [rbp+57h+var_A0]
0x180004da8  mov     [rsp+110h+var_F0], rcx
0x180004dad  mov     rcx, r10
0x180004db0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004db5  test    byte ptr cs:g_dwDebugFlags, 3
0x180004dbc  jz      loc_180004E46
0x180004dc2  mov     rcx, [rbp+57h+var_A8]
0x180004dc6  mov     ebx, [rbp+57h+var_9C]
0x180004dc9  mov     rdi, [rbp+57h+var_98]
0x180004dcd  movzx   esi, [rbp+57h+var_B0]
0x180004dd1  mov     rax, [rcx]
0x180004dd4  movzx   r14d, [rbp+57h+var_AC]
0x180004dd9  mov     rax, [rax+18h]
0x180004ddd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004de2  mov     rdx, rax
0x180004de5  mov     rcx, [rax]
0x180004de8  mov     rax, [rcx+8]
0x180004dec  mov     rcx, rdx
0x180004def  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004df4  mov     dword ptr [rsp+110h+var_C8], ebx
0x180004df8  lea     r9, aWarmupApplicat_1; "WARMUP_APPLICATION_CONTEXT::sm_WarmupTh"...
0x180004dff  mov     [rsp+110h+var_D0], rdi
0x180004e04  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180004e0b  mov     dword ptr [rsp+110h+var_D8], esi
0x180004e0f  mov     r8d, 1FCh
0x180004e15  mov     rcx, [rax+48h]
0x180004e19  lea     rax, aWarmupRequestS; "Warmup Request [%S] returned \"%d.%d %s"...
0x180004e20  mov     dword ptr [rsp+110h+var_E0], r14d
0x180004e25  mov     [rsp+110h+var_E8], rcx
0x180004e2a  mov     rcx, cs:g_pDebug
0x180004e31  mov     [rsp+110h+var_F0], rax
0x180004e36  call    cs:__imp_PuDbgPrint
0x180004e3c  xor     edi, edi
0x180004e3e  lea     rbx, [r12-0E8h]
0x180004e46  mov     rcx, [rbp+57h+var_A8]
0x180004e4a  test    rcx, rcx
0x180004e4d  jz      short loc_180004E62
0x180004e4f  mov     rax, [rcx]
0x180004e52  mov     rax, [rax+100h]
0x180004e59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e5e  mov     [rbp+57h+var_A8], rdi
0x180004e62  test    r15d, r15d
0x180004e65  jns     short loc_180004EAE
0x180004e67  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180004e6e  jz      short loc_180004EAE
0x180004e70  mov     rax, [rbx+0D0h]
0x180004e77  lea     r9, aWarmupApplicat_1; "WARMUP_APPLICATION_CONTEXT::sm_WarmupTh"...
0x180004e7e  mov     rcx, cs:g_pDebug
0x180004e85  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180004e8c  mov     [rsp+110h+var_E0], rax
0x180004e91  mov     r8d, 20Ch
0x180004e97  lea     rax, aError0x08xRunn; "Error 0x%08x running warmup request [%S"...
0x180004e9e  mov     dword ptr [rsp+110h+var_E8], r15d
0x180004ea3  mov     [rsp+110h+var_F0], rax
0x180004ea8  call    cs:__imp_PuDbgPrint
0x180004eae  mov     r12, [r12]
0x180004eb2  lea     rcx, [rbp+57h+var_88]
0x180004eb6  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180004ebc  cmp     r12, r13
0x180004ebf  jnz     loc_180004C01
0x180004ec5  mov     rax, [rbp+57h+var_90]
0x180004ec9  mov     rcx, [rax+10h]
0x180004ecd  mov     rax, [rcx]
0x180004ed0  mov     rax, [rax+28h]
0x180004ed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ed9  mov     rcx, cs:?g_pPreloadBlock@@3PEAVPRELOAD_BLOCK@@EA; PRELOAD_BLOCK * g_pPreloadBlock
0x180004ee0  test    rcx, rcx
0x180004ee3  jz      short loc_180004EFB
0x180004ee5  or      eax, 0FFFFFFFFh
0x180004ee8  lock xadd [rcx], eax
0x180004eec  cmp     eax, 1
0x180004eef  jnz     short loc_180004EFB
0x180004ef1  mov     rcx, [rcx+8]; hEvent
0x180004ef5  call    cs:__imp_SetEvent
0x180004efb  xor     eax, eax
0x180004efd  mov     rcx, [rbp+57h+var_50]
0x180004f01  xor     rcx, rsp; StackCookie
0x180004f04  call    __security_check_cookie
0x180004f09  add     rsp, 0D8h
0x180004f10  pop     r15
0x180004f12  pop     r14
0x180004f14  pop     r13
0x180004f16  pop     r12
0x180004f18  pop     rdi
0x180004f19  pop     rsi
0x180004f1a  pop     rbx
0x180004f1b  pop     rbp
0x180004f1c  retn
```
