# ThreadPoolSetupCounters(long (*)(ulong,ulong,void *))

- ea: `0x180003ec0`
- end: `0x180003ee8`
- name: `?ThreadPoolSetupCounters@@YAJP6AJKKPEAX@Z@Z`
- size: `40`
- prototype: `__int64 __fastcall(int (*)(unsigned int, unsigned int, void *))`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x1800038e0`
- `0x180003ec0`

## pseudocode

```c
__int64 __fastcall ThreadPoolSetupCounters(int (*a1)(unsigned int, unsigned int, void *))
{
  __int64 result; // rax

  result = 0;
  g_pfnSetupCounters = a1;
  if ( a1 )
  {
    if ( g_pThreadPool )
      return THREAD_POOL::InitializeCounters(g_pThreadPool);
  }
  return result;
}

```

## disassembly

```asm
0x180003ec0  sub     rsp, 28h
0x180003ec4  xor     eax, eax
0x180003ec6  mov     cs:?g_pfnSetupCounters@@3P6AJKKPEAX@ZEA, rcx; long (*g_pfnSetupCounters)(ulong,ulong,void *)
0x180003ecd  test    rcx, rcx
0x180003ed0  jz      short loc_180003EE3
0x180003ed2  mov     rcx, cs:?g_pThreadPool@@3PEAVTHREAD_POOL@@EA; this
0x180003ed9  test    rcx, rcx
0x180003edc  jz      short loc_180003EE3
0x180003ede  call    ?InitializeCounters@THREAD_POOL@@QEAAJXZ; THREAD_POOL::InitializeCounters(void)
0x180003ee3  add     rsp, 28h
0x180003ee7  retn
```
