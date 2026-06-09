# UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)

- ea: `0x18000a6e0`
- end: `0x18000a6fe`
- name: `?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z`
- size: `30`
- prototype: `void __fastcall(struct _UBPM_SRWLOCK *)`
- caller_count: `27`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180002b54`
- `0x180002dc0`
- `0x180002fcc`
- `0x180003684`
- `0x18000a570`
- `0x18000a710`
- `0x18000ae40`
- `0x180013244`
- `0x180017e88`
- `0x180018254`
- `0x18002b0e0`
- `0x18002b2b0`
- `0x18002b670`
- `0x18002d6f0`
- `0x18002dcc0`
- `0x18002e0c8`
- `0x18002e220`
- `0x1800344a0`
- `0x180034d04`
- `0x180035c50`
- `0x1800367e0`
- `0x180036860`
- `0x180036940`
- `0x180036a90`
- `0x18003bc7c`
- `0x18003c08c`
- `0x18003c120`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000a6e9`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000a6e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a6ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a6ef`

## pseudocode

```c
void __fastcall UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(struct _UBPM_SRWLOCK *a1)
{
  RtlAcquireSRWLockExclusive(a1);
  *((_DWORD *)a1 + 2) = GetCurrentThreadId();
}

```

## disassembly

```asm
0x18000a6e0  push    rbx
0x18000a6e2  sub     rsp, 20h
0x18000a6e6  mov     rbx, rcx
0x18000a6e9  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000a6ef  call    cs:__imp_GetCurrentThreadId
0x18000a6f5  mov     [rbx+8], eax
0x18000a6f8  add     rsp, 20h
0x18000a6fc  pop     rbx
0x18000a6fd  retn
```
