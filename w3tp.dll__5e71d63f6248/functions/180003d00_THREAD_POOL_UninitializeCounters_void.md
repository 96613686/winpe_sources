# THREAD_POOL::UninitializeCounters(void)

- ea: `0x180003d00`
- end: `0x180003d4a`
- name: `?UninitializeCounters@THREAD_POOL@@QEAAXXZ`
- size: `74`
- prototype: `void __fastcall(THREAD_POOL *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180003ef0`

## callees

- `0x180005010`

## pseudocode

```c
void __fastcall THREAD_POOL::UninitializeCounters(THREAD_POOL *this)
{
  ((void (__fastcall *)(__int64))g_pfnSetupCounters)(1);
  ((void (__fastcall *)(__int64))g_pfnSetupCounters)(1);
  ((void (__fastcall *)(__int64))g_pfnSetupCounters)(1);
}

```

## disassembly

```asm
0x180003d00  sub     rsp, 28h
0x180003d04  mov     rax, cs:?g_pfnSetupCounters@@3P6AJKKPEAX@ZEA; long (*g_pfnSetupCounters)(ulong,ulong,void *)
0x180003d0b  xor     r8d, r8d
0x180003d0e  lea     edx, [r8+3]
0x180003d12  lea     ecx, [rdx-2]
0x180003d15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d1a  mov     rax, cs:?g_pfnSetupCounters@@3P6AJKKPEAX@ZEA; long (*g_pfnSetupCounters)(ulong,ulong,void *)
0x180003d21  xor     r8d, r8d
0x180003d24  lea     edx, [r8+4]
0x180003d28  lea     ecx, [rdx-3]
0x180003d2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d30  mov     rax, cs:?g_pfnSetupCounters@@3P6AJKKPEAX@ZEA; long (*g_pfnSetupCounters)(ulong,ulong,void *)
0x180003d37  xor     r8d, r8d
0x180003d3a  lea     edx, [r8+5]
0x180003d3e  lea     ecx, [rdx-4]
0x180003d41  add     rsp, 28h
0x180003d45  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
