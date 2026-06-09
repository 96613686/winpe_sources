# SP_POOL_DEVICE::AcquireRundownSharedNonQueued(void)

- ea: `0x140032e90`
- end: `0x140032f09`
- name: `?AcquireRundownSharedNonQueued@SP_POOL_DEVICE@@QEAAJXZ`
- size: `121`
- prototype: `__int64 __fastcall(SP_POOL_DEVICE *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140034470`
- `0x1400a11b0`
- `0x1400a6288`
- `0x1400af408`

## callees

- `0x140032e90`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140032ebb`
- `ntoskrnl!KeWaitForSingleObject` at `0x140032ebb`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140032ee5`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140032ee5`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140032ecb`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140032ecb`

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
0x140032e90  mov     [rsp+arg_0], rbx
0x140032e95  mov     [rsp+arg_8], rsi
0x140032e9a  push    rdi
0x140032e9b  sub     rsp, 30h
0x140032e9f  mov     rbx, rcx
0x140032ea2  xor     edi, edi
0x140032ea4  mov     rcx, [rcx+50h]
0x140032ea8  jmp     short loc_140032ECB
0x140032eaa  xor     r9d, r9d; Alertable
0x140032ead  mov     [rsp+38h+Timeout], rdi; Timeout
0x140032eb2  xor     r8d, r8d; WaitMode
0x140032eb5  lea     rcx, [rbx+58h]; Object
0x140032eb9  xor     edx, edx; WaitReason
0x140032ebb  call    cs:__imp_KeWaitForSingleObject
0x140032ec2  nop     dword ptr [rax+rax+00h]
0x140032ec7  mov     rcx, [rbx+50h]; RunRefCacheAware
0x140032ecb  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x140032ed2  nop     dword ptr [rax+rax+00h]
0x140032ed7  test    al, al
0x140032ed9  jz      short loc_140032EAA
0x140032edb  cmp     [rbx+70h], rdi
0x140032edf  jnz     short loc_140032EF6
0x140032ee1  mov     rcx, [rbx+50h]; RunRefCacheAware
0x140032ee5  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140032eec  nop     dword ptr [rax+rax+00h]
0x140032ef1  mov     edi, 0C000000Eh
0x140032ef6  mov     rbx, [rsp+38h+arg_0]
0x140032efb  mov     eax, edi
0x140032efd  mov     rsi, [rsp+38h+arg_8]
0x140032f02  add     rsp, 30h
0x140032f06  pop     rdi
0x140032f07  retn
```
