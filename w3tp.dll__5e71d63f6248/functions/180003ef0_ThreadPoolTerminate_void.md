# ThreadPoolTerminate(void)

- ea: `0x180003ef0`
- end: `0x180003fa7`
- name: `?ThreadPoolTerminate@@YAJXZ`
- size: `183`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001f8c`
- `0x180003be0`
- `0x180003d00`
- `0x180003ef0`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180003f51`
- `iisutil!PuDbgPrint` at `0x180003f51`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x180003f86`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x180003f86`

## string_xrefs

- `0x180003f4a`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3tp\thread_functions.cxx`
- `0x180003f31`: `W3TP: ThreadPoolTerminate() called but pool still in use\n`
- `0x180003f38`: `ThreadPoolTerminate`

## pseudocode

```c
__int64 ThreadPoolTerminate(void)
{
  void *v0; // rbx

  if ( g_pfnSetupCounters && g_pThreadPool )
    THREAD_POOL::UninitializeCounters(g_pThreadPool);
  if ( _InterlockedDecrement(&g_cInitializeCount) < 0 )
  {
    if ( g_pThreadPool )
    {
      THREAD_POOL::TerminateThreadPool(g_pThreadPool);
      g_pThreadPool = 0;
    }
    else
    {
      v0 = WIN32_COMPLETION_PACKET::sm_Allocator;
      if ( WIN32_COMPLETION_PACKET::sm_Allocator )
      {
        ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER((ALLOC_CACHE_HANDLER *)WIN32_COMPLETION_PACKET::sm_Allocator);
        operator delete(v0);
      }
      WIN32_COMPLETION_PACKET::sm_Allocator = 0;
    }
  }
  else if ( (g_dwDebugFlags & 3) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3tp\\thread_functions.cxx",
      228,
      "ThreadPoolTerminate",
      "W3TP: ThreadPoolTerminate() called but pool still in use\n");
  }
  return 0;
}

```

## disassembly

```asm
0x180003ef0  push    rbx
0x180003ef2  sub     rsp, 30h
0x180003ef6  cmp     cs:?g_pfnSetupCounters@@3P6AJKKPEAX@ZEA, 0; long (*g_pfnSetupCounters)(ulong,ulong,void *)
0x180003efe  jz      short loc_180003F11
0x180003f00  mov     rcx, cs:?g_pThreadPool@@3PEAVTHREAD_POOL@@EA; this
0x180003f07  test    rcx, rcx
0x180003f0a  jz      short loc_180003F11
0x180003f0c  call    ?UninitializeCounters@THREAD_POOL@@QEAAXXZ; THREAD_POOL::UninitializeCounters(void)
0x180003f11  or      eax, 0FFFFFFFFh
0x180003f14  lock xadd cs:?g_cInitializeCount@@3JA, eax; long g_cInitializeCount
0x180003f1c  cmp     eax, 1
0x180003f1f  js      short loc_180003F59
0x180003f21  test    cs:g_dwDebugFlags, 3
0x180003f28  jz      short loc_180003F9F
0x180003f2a  mov     rcx, cs:g_pDebug
0x180003f31  lea     rax, aW3tpThreadpool; "W3TP: ThreadPoolTerminate() called but "...
0x180003f38  lea     r9, aThreadpoolterm_0; "ThreadPoolTerminate"
0x180003f3f  mov     [rsp+38h+var_18], rax
0x180003f44  mov     r8d, 0E4h
0x180003f4a  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180003f51  call    cs:__imp_PuDbgPrint
0x180003f57  jmp     short loc_180003F9F
0x180003f59  mov     rcx, cs:?g_pThreadPool@@3PEAVTHREAD_POOL@@EA; this
0x180003f60  test    rcx, rcx
0x180003f63  jz      short loc_180003F77
0x180003f65  call    ?TerminateThreadPool@THREAD_POOL@@QEAAXXZ; THREAD_POOL::TerminateThreadPool(void)
0x180003f6a  mov     cs:?g_pThreadPool@@3PEAVTHREAD_POOL@@EA, 0; THREAD_POOL * g_pThreadPool
0x180003f75  jmp     short loc_180003F9F
0x180003f77  mov     rbx, cs:?sm_Allocator@WIN32_COMPLETION_PACKET@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * WIN32_COMPLETION_PACKET::sm_Allocator
0x180003f7e  test    rbx, rbx
0x180003f81  jz      short loc_180003F94
0x180003f83  mov     rcx, rbx
0x180003f86  call    cs:__imp_??1ALLOC_CACHE_HANDLER@@QEAA@XZ; ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(void)
0x180003f8c  mov     rcx, rbx; Block
0x180003f8f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003f94  mov     cs:?sm_Allocator@WIN32_COMPLETION_PACKET@@0PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * WIN32_COMPLETION_PACKET::sm_Allocator
0x180003f9f  xor     eax, eax
0x180003fa1  add     rsp, 30h
0x180003fa5  pop     rbx
0x180003fa6  retn
```
