# SP_POOL_DEVICE::AcquireRundownSharedNonQueued(void)

- ea: `0x140032f40`
- end: `0x140032fb9`
- name: `?AcquireRundownSharedNonQueued@SP_POOL_DEVICE@@QEAAJXZ`
- size: `121`
- prototype: `__int64 __fastcall(SP_POOL_DEVICE *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140034530`
- `0x1400a12e0`
- `0x1400a63b8`
- `0x1400af5a8`

## callees

- `0x140032f40`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140032f6b`
- `ntoskrnl!KeWaitForSingleObject` at `0x140032f6b`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140032f95`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140032f95`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140032f7b`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140032f7b`

## pseudocode

```c
__int64 __fastcall SP_POOL_DEVICE::AcquireRundownSharedNonQueued(SP_POOL_DEVICE *this)
{
  unsigned int v2; // edi
  struct _EX_RUNDOWN_REF_CACHE_AWARE *i; // rcx

  v2 = 0;
  for ( i = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)*((_QWORD *)this + 10);
        !ExAcquireRundownProtectionCacheAware(i);
        i = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)*((_QWORD *)this + 10) )
  {
    KeWaitForSingleObject((char *)this + 88, Executive, 0, 0, 0);
  }
  if ( !*((_QWORD *)this + 14) )
  {
    ExReleaseRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)this + 10));
    return (unsigned int)-1073741810;
  }
  return v2;
}

```

## disassembly

```asm
0x140032f40  mov     [rsp+arg_0], rbx
0x140032f45  mov     [rsp+arg_8], rsi
0x140032f4a  push    rdi
0x140032f4b  sub     rsp, 30h
0x140032f4f  mov     rbx, rcx
0x140032f52  xor     edi, edi
0x140032f54  mov     rcx, [rcx+50h]
0x140032f58  jmp     short loc_140032F7B
0x140032f5a  xor     r9d, r9d; Alertable
0x140032f5d  mov     [rsp+38h+Timeout], rdi; Timeout
0x140032f62  xor     r8d, r8d; WaitMode
0x140032f65  lea     rcx, [rbx+58h]; Object
0x140032f69  xor     edx, edx; WaitReason
0x140032f6b  call    cs:__imp_KeWaitForSingleObject
0x140032f72  nop     dword ptr [rax+rax+00h]
0x140032f77  mov     rcx, [rbx+50h]; RunRefCacheAware
0x140032f7b  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x140032f82  nop     dword ptr [rax+rax+00h]
0x140032f87  test    al, al
0x140032f89  jz      short loc_140032F5A
0x140032f8b  cmp     [rbx+70h], rdi
0x140032f8f  jnz     short loc_140032FA6
0x140032f91  mov     rcx, [rbx+50h]; RunRefCacheAware
0x140032f95  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140032f9c  nop     dword ptr [rax+rax+00h]
0x140032fa1  mov     edi, 0C000000Eh
0x140032fa6  mov     rbx, [rsp+38h+arg_0]
0x140032fab  mov     eax, edi
0x140032fad  mov     rsi, [rsp+38h+arg_8]
0x140032fb2  add     rsp, 30h
0x140032fb6  pop     rdi
0x140032fb7  retn
```
