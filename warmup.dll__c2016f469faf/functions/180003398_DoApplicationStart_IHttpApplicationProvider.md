# DoApplicationStart(IHttpApplicationProvider *)

- ea: `0x180003398`
- end: `0x180003572`
- name: `?DoApplicationStart@@YA?AW4GLOBAL_NOTIFICATION_STATUS@@PEAVIHttpApplicationProvider@@@Z`
- size: `474`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001ce0`

## callees

- `0x180001008`
- `0x180002cb0`
- `0x180003398`
- `0x180003818`
- `0x180006010`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x18000344c`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000344c`
- `iisutil!PuDbgPrint` at `0x18000340d`
- `iisutil!PuDbgPrint` at `0x18000355f`
- `iisutil!PuDbgPrint` at `0x18000340d`
- `iisutil!PuDbgPrint` at `0x18000355f`

## string_xrefs

- `0x180003401`: `servercommon\inetsrv\iis\iisrearc\iis70\appwarmup\warmup.cxx`
- `0x18000354d`: `servercommon\inetsrv\iis\iisrearc\iis70\appwarmup\warmup.cxx`
- `0x180003484`: `Failed to get configuration.\n`

## pseudocode

```c
__int64 __fastcall DoApplicationStart(__int64 *a1)
{
  __int64 v1; // rax
  __int64 v2; // rax
  int Extended; // edi
  _QWORD *v4; // rbx
  __int64 v5; // rax
  int v7; // [rsp+50h] [rbp+8h] BYREF
  struct IHttpApplication2 *v8; // [rsp+58h] [rbp+10h] BYREF

  v1 = *a1;
  v8 = 0;
  v7 = 0;
  v2 = (*(__int64 (__fastcall **)(__int64 *))(v1 + 8))(a1);
  Extended = HttpGetExtendedInterface<IHttpApplication,IHttpApplication2>(g_pServer, v2, &v8);
  if ( Extended < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      return 0;
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\appwarmup\\warmup.cxx",
      804,
      "DoApplicationStart",
      "Failed to get IHttpApplication2\r\n");
    goto LABEL_17;
  }
  v4 = operator new(0x68u);
  if ( !v4 )
  {
    Extended = -2147024882;
    goto LABEL_17;
  }
  v4[2] = v8;
  *v4 = &WARMUP_APPLICATION_CONTEXT::`vftable';
  *((_DWORD *)v4 + 2) = 1480808257;
  STRU::STRU((STRU *)(v4 + 3));
  *((_DWORD *)v4 + 20) = 0;
  v4[12] = v4 + 11;
  v4[11] = v4 + 11;
  Extended = GetConfiguration(v8, (struct WARMUP_APPLICATION_CONTEXT *)v4);
  if ( Extended < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      return 0;
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\appwarmup\\warmup.cxx",
      827,
      "DoApplicationStart",
      "Failed to get configuration.\r\n");
    goto LABEL_17;
  }
  Extended = (*(__int64 (__fastcall **)(_QWORD *, int *))(*v4 + 48LL))(v4, &v7);
  if ( Extended < 0
    || g_pPreloadProvider
    && ((*(unsigned int (__fastcall **)(_QWORD *))(*v4 + 64LL))(v4) || !v7)
    && (Extended = (*(__int64 (__fastcall **)(_QWORD *, struct IHttpApplication2 *))(*v4 + 24LL))(v4, v8), Extended < 0)
    || (v5 = (*(__int64 (__fastcall **)(struct IHttpApplication2 *))(*(_QWORD *)v8 + 24LL))(v8),
        Extended = (*(__int64 (__fastcall **)(__int64, _QWORD *, void *))(*(_QWORD *)v5 + 8LL))(v5, v4, g_ModuleID),
        Extended < 0) )
  {
LABEL_17:
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\appwarmup\\warmup.cxx",
        877,
        "DoApplicationStart",
        "Failure 0x%08x (%d) occurred, but we can't fail this notification...\r\n",
        Extended,
        Extended);
  }
  return 0;
}

```

## disassembly

```asm
0x180003398  mov     [rsp+arg_10], rbx
0x18000339d  push    rdi
0x18000339e  sub     rsp, 40h
0x1800033a2  mov     rax, [rcx]
0x1800033a5  mov     [rsp+48h+arg_8], 0
0x1800033ae  mov     [rsp+48h+arg_0], 0
0x1800033b6  mov     rax, [rax+8]
0x1800033ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033bf  mov     rcx, cs:?g_pServer@@3PEAVIHttpServer@@EA; IHttpServer * g_pServer
0x1800033c6  lea     r8, [rsp+48h+arg_8]
0x1800033cb  mov     rdx, rax
0x1800033ce  call    ??$HttpGetExtendedInterface@VIHttpApplication@@VIHttpApplication2@@@@YAJPEAVIHttpServer@@PEAVIHttpApplication@@PEAPEAVIHttpApplication2@@@Z; HttpGetExtendedInterface<IHttpApplication,IHttpApplication2>(IHttpServer *,IHttpApplication *,IHttpApplication2 * *)
0x1800033d3  mov     edi, eax
0x1800033d5  test    eax, eax
0x1800033d7  jns     short loc_180003418
0x1800033d9  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800033e0  jz      loc_180003565
0x1800033e6  lea     rax, aFailedToGetIht; "Failed to get IHttpApplication2\r\n"
0x1800033ed  mov     r8d, 324h
0x1800033f3  mov     rcx, cs:g_pDebug
0x1800033fa  lea     r9, aDoapplications; "DoApplicationStart"
0x180003401  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180003408  mov     [rsp+48h+var_28], rax
0x18000340d  call    cs:__imp_PuDbgPrint
0x180003413  jmp     loc_180003527
0x180003418  mov     ecx, 68h ; 'h'; Size
0x18000341d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003422  mov     rbx, rax
0x180003425  test    rax, rax
0x180003428  jz      loc_180003522
0x18000342e  mov     rcx, [rsp+48h+arg_8]
0x180003433  lea     rax, ??_7WARMUP_APPLICATION_CONTEXT@@6B@; const WARMUP_APPLICATION_CONTEXT::`vftable'
0x18000343a  mov     [rbx+10h], rcx
0x18000343e  lea     rcx, [rbx+18h]
0x180003442  mov     [rbx], rax
0x180003445  mov     dword ptr [rbx+8], 58435741h
0x18000344c  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180003452  lea     rcx, [rbx+58h]
0x180003456  mov     dword ptr [rbx+50h], 0
0x18000345d  mov     [rcx+8], rcx
0x180003461  mov     rdx, rbx; struct WARMUP_APPLICATION_CONTEXT *
0x180003464  mov     [rcx], rcx
0x180003467  mov     rcx, [rsp+48h+arg_8]; struct IHttpApplication2 *
0x18000346c  call    ?GetConfiguration@@YAJPEAVIHttpApplication2@@PEAVWARMUP_APPLICATION_CONTEXT@@@Z; GetConfiguration(IHttpApplication2 *,WARMUP_APPLICATION_CONTEXT *)
0x180003471  mov     edi, eax
0x180003473  test    eax, eax
0x180003475  jns     short loc_180003496
0x180003477  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000347e  jz      loc_180003565
0x180003484  lea     rax, aFailedToGetCon; "Failed to get configuration.\r\n"
0x18000348b  mov     r8d, 33Bh
0x180003491  jmp     loc_1800033F3
0x180003496  mov     rax, [rbx]
0x180003499  lea     rdx, [rsp+48h+arg_0]
0x18000349e  mov     rcx, rbx
0x1800034a1  mov     rax, [rax+30h]
0x1800034a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034aa  mov     edi, eax
0x1800034ac  test    eax, eax
0x1800034ae  js      short loc_180003527
0x1800034b0  cmp     cs:?g_pPreloadProvider@@3PEAVIGlobalApplicationPreloadProvider2@@EA, 0; IGlobalApplicationPreloadProvider2 * g_pPreloadProvider
0x1800034b8  jz      short loc_1800034ED
0x1800034ba  mov     rax, [rbx]
0x1800034bd  mov     rcx, rbx
0x1800034c0  mov     rax, [rax+40h]
0x1800034c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034c9  test    eax, eax
0x1800034cb  jnz     short loc_1800034D3
0x1800034cd  cmp     [rsp+48h+arg_0], eax
0x1800034d1  jnz     short loc_1800034ED
0x1800034d3  mov     rax, [rbx]
0x1800034d6  mov     rcx, rbx
0x1800034d9  mov     rdx, [rsp+48h+arg_8]
0x1800034de  mov     rax, [rax+18h]
0x1800034e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034e7  mov     edi, eax
0x1800034e9  test    eax, eax
0x1800034eb  js      short loc_180003527
0x1800034ed  mov     rcx, [rsp+48h+arg_8]
0x1800034f2  mov     rax, [rcx]
0x1800034f5  mov     rax, [rax+18h]
0x1800034f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034fe  mov     r8, cs:?g_ModuleID@@3PEAXEA; void * g_ModuleID
0x180003505  mov     r9, rax
0x180003508  mov     rdx, rbx
0x18000350b  mov     rcx, [rax]
0x18000350e  mov     rax, [rcx+8]
0x180003512  mov     rcx, r9
0x180003515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000351a  mov     edi, eax
0x18000351c  test    eax, eax
0x18000351e  jns     short loc_180003565
0x180003520  jmp     short loc_180003527
0x180003522  mov     edi, 8007000Eh
0x180003527  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000352e  jz      short loc_180003565
0x180003530  mov     rcx, cs:g_pDebug
0x180003537  lea     rax, aFailure0x08xDO; "Failure 0x%08x (%d) occurred, but we ca"...
0x18000353e  mov     [rsp+48h+var_18], edi
0x180003542  lea     r9, aDoapplications; "DoApplicationStart"
0x180003549  mov     [rsp+48h+var_20], edi
0x18000354d  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180003554  mov     r8d, 36Dh
0x18000355a  mov     [rsp+48h+var_28], rax
0x18000355f  call    cs:__imp_PuDbgPrint
0x180003565  mov     rbx, [rsp+48h+arg_10]
0x18000356a  xor     eax, eax
0x18000356c  add     rsp, 40h
0x180003570  pop     rdi
0x180003571  retn
```
