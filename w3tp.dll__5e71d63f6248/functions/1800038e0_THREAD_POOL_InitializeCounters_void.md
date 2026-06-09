# THREAD_POOL::InitializeCounters(void)

- ea: `0x1800038e0`
- end: `0x180003948`
- name: `?InitializeCounters@THREAD_POOL@@QEAAJXZ`
- size: `104`
- prototype: `__int64 __fastcall(THREAD_POOL *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180003ec0`

## callees

- `0x1800038e0`
- `0x180005010`

## pseudocode

```c
__int64 __fastcall THREAD_POOL::InitializeCounters(THREAD_POOL *this)
{
  __int64 result; // rax

  result = ((__int64 (__fastcall *)(__int64, __int64, __int64))g_pfnSetupCounters)(1, 3, *(_QWORD *)this + 16LL);
  if ( (int)result >= 0 )
  {
    result = ((__int64 (__fastcall *)(__int64, __int64, __int64))g_pfnSetupCounters)(1, 4, *(_QWORD *)this + 20LL);
    if ( (int)result >= 0 )
      return ((__int64 (__fastcall *)(__int64, __int64, __int64))g_pfnSetupCounters)(1, 5, *(_QWORD *)this + 52LL);
  }
  return result;
}

```

## disassembly

```asm
0x1800038e0  push    rbx
0x1800038e2  sub     rsp, 20h
0x1800038e6  mov     r8, [rcx]
0x1800038e9  mov     edx, 3
0x1800038ee  mov     rax, cs:?g_pfnSetupCounters@@3P6AJKKPEAX@ZEA; long (*g_pfnSetupCounters)(ulong,ulong,void *)
0x1800038f5  mov     rbx, rcx
0x1800038f8  add     r8, 10h
0x1800038fc  lea     ecx, [rdx-2]
0x1800038ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003904  test    eax, eax
0x180003906  js      short loc_180003942
0x180003908  mov     r8, [rbx]
0x18000390b  mov     edx, 4
0x180003910  mov     rax, cs:?g_pfnSetupCounters@@3P6AJKKPEAX@ZEA; long (*g_pfnSetupCounters)(ulong,ulong,void *)
0x180003917  add     r8, 14h
0x18000391b  lea     ecx, [rdx-3]
0x18000391e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003923  test    eax, eax
0x180003925  js      short loc_180003942
0x180003927  mov     r8, [rbx]
0x18000392a  mov     edx, 5
0x18000392f  mov     rax, cs:?g_pfnSetupCounters@@3P6AJKKPEAX@ZEA; long (*g_pfnSetupCounters)(ulong,ulong,void *)
0x180003936  add     r8, 34h ; '4'
0x18000393a  lea     ecx, [rdx-4]
0x18000393d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003942  add     rsp, 20h
0x180003946  pop     rbx
0x180003947  retn
```
