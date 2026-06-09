# WcIsExpanded

- ea: `0x140001ffc`
- end: `0x14000203f`
- name: `WcIsExpanded`
- size: `67`
- prototype: ``
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x140001fd0`
- `0x140014008`
- `0x140017ef8`
- `0x1400184f0`
- `0x140018e28`
- `0x14001ecb8`
- `0x140029608`
- `0x14002ef40`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x140002010`
- `ntoskrnl!ExAcquireFastMutex` at `0x140002010`
- `ntoskrnl!ExReleaseFastMutex` at `0x140002025`
- `ntoskrnl!ExReleaseFastMutex` at `0x140002025`

## pseudocode

```c
char __fastcall WcIsExpanded(__int64 a1)
{
  struct _FAST_MUTEX *v1; // rdi
  __int64 v2; // rbx

  v1 = (struct _FAST_MUTEX *)(a1 + 8);
  v2 = a1;
  ExAcquireFastMutex((PFAST_MUTEX)(a1 + 8));
  LOBYTE(v2) = *(_BYTE *)(v2 + 88) & 1;
  ExReleaseFastMutex(v1);
  return v2;
}

```

## disassembly

```asm
0x140001ffc  mov     [rsp+arg_0], rbx
0x140002001  push    rdi
0x140002002  sub     rsp, 20h
0x140002006  lea     rdi, [rcx+8]
0x14000200a  mov     rbx, rcx
0x14000200d  mov     rcx, rdi; FastMutex
0x140002010  call    cs:__imp_ExAcquireFastMutex
0x140002017  nop     dword ptr [rax+rax+00h]
0x14000201c  mov     bl, [rbx+58h]
0x14000201f  mov     rcx, rdi; FastMutex
0x140002022  and     bl, 1
0x140002025  call    cs:__imp_ExReleaseFastMutex
0x14000202c  nop     dword ptr [rax+rax+00h]
0x140002031  mov     al, bl
0x140002033  mov     rbx, [rsp+28h+arg_0]
0x140002038  add     rsp, 20h
0x14000203c  pop     rdi
0x14000203d  retn
```
