# UbpmpActionTerminatesOnConstraint

- ea: `0x180009fb8`
- end: `0x18000a00b`
- name: `UbpmpActionTerminatesOnConstraint`
- size: `83`
- prototype: `__int64 __fastcall(struct _UBPM_TRIGGER_CONSUMER_BLOCK *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800275a0`

## callees

- `0x180008f30`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180009fd3`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180009fd3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000a004`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009fd9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009fd9`

## pseudocode

```c
__int64 __fastcall UbpmpActionTerminatesOnConstraint(struct _UBPM_TRIGGER_CONSUMER_BLOCK *a1, int a2, RPC_STATUS a3)
{
  char *v3; // rbp

  v3 = (char *)a1 + 208;
  RtlAcquireSRWLockExclusive((char *)a1 + 208);
  *((_DWORD *)v3 + 2) = GetCurrentThreadId();
  UbpmpActionTerminatesOnConstraintLocked(a1, a2, a3, 0);
  *((_DWORD *)v3 + 2) = 0;
  return RtlReleaseSRWLockExclusive(v3);
}

```

## disassembly

```asm
0x180009fb8  push    rbx
0x180009fba  push    rbp
0x180009fbb  push    rsi
0x180009fbc  push    rdi
0x180009fbd  sub     rsp, 28h
0x180009fc1  lea     rbp, [rcx+0D0h]
0x180009fc8  mov     rsi, rcx
0x180009fcb  mov     rcx, rbp
0x180009fce  mov     ebx, r8d
0x180009fd1  mov     edi, edx
0x180009fd3  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180009fd9  call    cs:__imp_GetCurrentThreadId
0x180009fdf  xor     r9d, r9d; struct _GUID *
0x180009fe2  mov     r8d, ebx; unsigned int
0x180009fe5  mov     edx, edi; unsigned int
0x180009fe7  mov     [rbp+8], eax
0x180009fea  mov     rcx, rsi; struct _UBPM_TRIGGER_CONSUMER_BLOCK *
0x180009fed  call    ?UbpmpActionTerminatesOnConstraintLocked@@YAXPEAU_UBPM_TRIGGER_CONSUMER_BLOCK@@KKPEAU_GUID@@@Z; UbpmpActionTerminatesOnConstraintLocked(_UBPM_TRIGGER_CONSUMER_BLOCK *,ulong,ulong,_GUID *)
0x180009ff2  mov     rcx, rbp
0x180009ff5  mov     dword ptr [rbp+8], 0
0x180009ffc  add     rsp, 28h
0x18000a000  pop     rdi
0x18000a001  pop     rsi
0x18000a002  pop     rbp
0x18000a003  pop     rbx
0x18000a004  jmp     cs:__imp_RtlReleaseSRWLockExclusive
```
