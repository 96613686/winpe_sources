# DereferenceClientContext

- ea: `0x18000a034`
- end: `0x18000a0a2`
- name: `DereferenceClientContext`
- size: `110`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180009c80`
- `0x180009cb0`

## callees

- `0x18000a034`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000a086`
- `ntdll!RtlFreeHeap` at `0x18000a086`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000a06e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000a091`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000a06e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000a091`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000a048`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000a048`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000a05d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000a05d`

## pseudocode

```c
BOOLEAN __fastcall DereferenceClientContext(_DWORD *P)
{
  char *v1; // rdi
  struct _TP_WORK *v4; // rcx

  v1 = (char *)(P + 2);
  RtlAcquireSRWLockExclusive(P + 2);
  if ( P[4]-- != 1 )
    return RtlReleaseSRWLockExclusive(v1);
  v4 = (struct _TP_WORK *)*((_QWORD *)P + 8);
  if ( v4 )
  {
    CloseThreadpoolWork(v4);
    *((_QWORD *)P + 8) = 0;
  }
  RtlReleaseSRWLockExclusive(v1);
  return RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
}

```

## disassembly

```asm
0x18000a034  mov     [rsp+arg_8], rbx
0x18000a039  push    rdi
0x18000a03a  sub     rsp, 20h
0x18000a03e  lea     rdi, [rcx+8]
0x18000a042  mov     rbx, rcx
0x18000a045  mov     rcx, rdi
0x18000a048  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000a04e  add     dword ptr [rbx+10h], 0FFFFFFFFh
0x18000a052  jnz     short loc_18000A08E
0x18000a054  mov     rcx, [rbx+40h]; pwk
0x18000a058  test    rcx, rcx
0x18000a05b  jz      short loc_18000A06B
0x18000a05d  call    cs:__imp_CloseThreadpoolWork
0x18000a063  mov     qword ptr [rbx+40h], 0
0x18000a06b  mov     rcx, rdi
0x18000a06e  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000a074  mov     rcx, gs:60h
0x18000a07d  mov     r8, rbx; P
0x18000a080  xor     edx, edx; Flags
0x18000a082  mov     rcx, [rcx+30h]; HeapHandle
0x18000a086  call    cs:__imp_RtlFreeHeap
0x18000a08c  jmp     short loc_18000A097
0x18000a08e  mov     rcx, rdi
0x18000a091  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000a097  mov     rbx, [rsp+28h+arg_8]
0x18000a09c  add     rsp, 20h
0x18000a0a0  pop     rdi
0x18000a0a1  retn
```
