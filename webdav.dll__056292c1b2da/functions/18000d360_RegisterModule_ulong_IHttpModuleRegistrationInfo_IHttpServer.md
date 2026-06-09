# RegisterModule(ulong,IHttpModuleRegistrationInfo *,IHttpServer *)

- ea: `0x18000d360`
- end: `0x18000d48c`
- name: `?RegisterModule@@YAJKPEAVIHttpModuleRegistrationInfo@@PEAVIHttpServer@@@Z`
- size: `300`
- prototype: `int(unsigned int, struct IHttpModuleRegistrationInfo *, struct IHttpServer *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x1800011d4`
- `0x18000806c`
- `0x180008374`
- `0x18000d360`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000d389`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000d389`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x18000d379`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x18000d379`

## string_xrefs

- `0x18000d36d`: `System\CurrentControlSet\Services\W3SVC\Parameters\webdav`

## pseudocode

```c
__int64 __fastcall RegisterModule(__int64 a1, struct IHttpModuleRegistrationInfo *a2, struct IHttpServer *a3)
{
  int v5; // edi
  _QWORD *v6; // rax
  _QWORD *v7; // rbx
  _QWORD *v8; // rax
  _QWORD *v9; // rsi

  g_dwDebugFlags = PuLoadDebugFlagsFromRegStr("System\\CurrentControlSet\\Services\\W3SVC\\Parameters\\webdav", 0);
  if ( g_dwDebugFlags < 0 )
    DebugBreak();
  g_pStaticFileModuleContext = (void *)(*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *))(*(_QWORD *)a2 + 8LL))(a2);
  g_DavModuleContext = g_pStaticFileModuleContext;
  g_pGlobalInfo = a3;
  v5 = GlobalInitialize(a2);
  if ( v5 >= 0 )
  {
    v6 = operator new(0x10u);
    v7 = v6;
    if ( v6 )
    {
      *v6 = &DAV_MODULE_FACTORY::`vftable';
      v6[1] = &DAV_HTTP_MODULE::`vftable';
      v5 = (*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *, _QWORD *, __int64, _QWORD))(*(_QWORD *)a2 + 16LL))(
             a2,
             v6,
             536871056,
             0);
      if ( v5 >= 0 )
      {
        v8 = operator new(8u);
        v9 = v8;
        if ( v8 )
        {
          *v8 = &DAV_GLOBAL_MODULE::`vftable';
          v5 = (*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *, _QWORD *, __int64))(*(_QWORD *)a2 + 24LL))(
                 a2,
                 v8,
                 256);
          if ( v5 >= 0 )
            return 0;
          (*(void (__fastcall **)(_QWORD *))(*v9 + 104LL))(v9);
        }
        else
        {
          v5 = -2147024888;
        }
      }
      (*(void (__fastcall **)(_QWORD *))(*v7 + 8LL))(v7);
    }
    else
    {
      v5 = -2147024888;
    }
  }
  GlobalTerminate();
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000d360  push    rbx
0x18000d362  push    rsi
0x18000d363  push    rdi
0x18000d364  push    r14
0x18000d366  sub     rsp, 38h
0x18000d36a  mov     r14, rdx
0x18000d36d  lea     rcx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\W3"...
0x18000d374  xor     edx, edx
0x18000d376  mov     rbx, r8
0x18000d379  call    cs:__imp_PuLoadDebugFlagsFromRegStr
0x18000d37f  mov     cs:g_dwDebugFlags, eax
0x18000d385  test    eax, eax
0x18000d387  jns     short loc_18000D38F
0x18000d389  call    cs:__imp_DebugBreak
0x18000d38f  mov     rax, [r14]
0x18000d392  mov     rcx, r14
0x18000d395  mov     rax, [rax+8]
0x18000d399  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d39e  mov     rcx, r14; struct IHttpModuleRegistrationInfo *
0x18000d3a1  mov     cs:?g_pStaticFileModuleContext@@3PEAXEA, rax; void * g_pStaticFileModuleContext
0x18000d3a8  mov     cs:?g_DavModuleContext@@3PEAXEA, rax; void * g_DavModuleContext
0x18000d3af  mov     cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA, rbx; IHttpServer * g_pGlobalInfo
0x18000d3b6  call    ?GlobalInitialize@@YAJPEAVIHttpModuleRegistrationInfo@@@Z; GlobalInitialize(IHttpModuleRegistrationInfo *)
0x18000d3bb  mov     edi, eax
0x18000d3bd  test    eax, eax
0x18000d3bf  js      loc_18000D47B
0x18000d3c5  mov     ecx, 10h; Size
0x18000d3ca  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d3cf  mov     rbx, rax
0x18000d3d2  test    rax, rax
0x18000d3d5  jz      loc_18000D476
0x18000d3db  lea     rax, ??_7DAV_MODULE_FACTORY@@6B@; const DAV_MODULE_FACTORY::`vftable'
0x18000d3e2  xor     r9d, r9d
0x18000d3e5  mov     [rbx], rax
0x18000d3e8  mov     r8d, 20000090h
0x18000d3ee  lea     rax, ??_7DAV_HTTP_MODULE@@6B@; const DAV_HTTP_MODULE::`vftable'
0x18000d3f5  mov     rdx, rbx
0x18000d3f8  mov     [rbx+8], rax
0x18000d3fc  mov     rcx, r14
0x18000d3ff  mov     rax, [r14]
0x18000d402  mov     rax, [rax+10h]
0x18000d406  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d40b  mov     edi, eax
0x18000d40d  test    eax, eax
0x18000d40f  js      short loc_18000D465
0x18000d411  mov     ecx, 8; Size
0x18000d416  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d41b  mov     rsi, rax
0x18000d41e  test    rax, rax
0x18000d421  jz      short loc_18000D460
0x18000d423  lea     rax, ??_7DAV_GLOBAL_MODULE@@6B@; const DAV_GLOBAL_MODULE::`vftable'
0x18000d42a  mov     r8d, 100h
0x18000d430  mov     [rsi], rax
0x18000d433  mov     rdx, rsi
0x18000d436  mov     rcx, [r14]
0x18000d439  mov     rax, [rcx+18h]
0x18000d43d  mov     rcx, r14
0x18000d440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d445  mov     edi, eax
0x18000d447  test    eax, eax
0x18000d449  jns     short loc_18000D45C
0x18000d44b  mov     rax, [rsi]
0x18000d44e  mov     rcx, rsi
0x18000d451  mov     rax, [rax+68h]
0x18000d455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d45a  jmp     short loc_18000D465
0x18000d45c  xor     eax, eax
0x18000d45e  jmp     short loc_18000D482
0x18000d460  mov     edi, 80070008h
0x18000d465  mov     rax, [rbx]
0x18000d468  mov     rcx, rbx
0x18000d46b  mov     rax, [rax+8]
0x18000d46f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d474  jmp     short loc_18000D47B
0x18000d476  mov     edi, 80070008h
0x18000d47b  call    ?GlobalTerminate@@YAXXZ; GlobalTerminate(void)
0x18000d480  mov     eax, edi
0x18000d482  add     rsp, 38h
0x18000d486  pop     r14
0x18000d488  pop     rdi
0x18000d489  pop     rsi
0x18000d48a  pop     rbx
0x18000d48b  retn
```
