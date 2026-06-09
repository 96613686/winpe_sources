# WcIsPlaceHolder

- ea: `0x140001bf8`
- end: `0x140001c3d`
- name: `WcIsPlaceHolder`
- size: `69`
- prototype: ``
- caller_count: `14`
- callee_count: `0`
- tags: ``

## callers

- `0x140001b94`
- `0x140001bc8`
- `0x1400184f0`
- `0x1400198a0`
- `0x140023150`
- `0x140023840`
- `0x140024040`
- `0x140024f60`
- `0x140026de0`
- `0x140027854`
- `0x140027f24`
- `0x1400287d0`
- `0x14002893c`
- `0x14002f9f8`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x140001c0c`
- `ntoskrnl!ExAcquireFastMutex` at `0x140001c0c`
- `ntoskrnl!ExReleaseFastMutex` at `0x140001c23`
- `ntoskrnl!ExReleaseFastMutex` at `0x140001c23`

## pseudocode

```c
char __fastcall WcIsPlaceHolder(__int64 a1)
{
  struct _FAST_MUTEX *v1; // rdi
  __int64 v2; // rbx

  v1 = (struct _FAST_MUTEX *)(a1 + 8);
  v2 = a1;
  ExAcquireFastMutex((PFAST_MUTEX)(a1 + 8));
  LOBYTE(v2) = (*(_DWORD *)(v2 + 88) & 2) != 0;
  ExReleaseFastMutex(v1);
  return v2;
}

```

## disassembly

```asm
0x140001bf8  mov     [rsp+arg_0], rbx
0x140001bfd  push    rdi
0x140001bfe  sub     rsp, 20h
0x140001c02  lea     rdi, [rcx+8]
0x140001c06  mov     rbx, rcx
0x140001c09  mov     rcx, rdi; FastMutex
0x140001c0c  call    cs:__imp_ExAcquireFastMutex
0x140001c13  nop     dword ptr [rax+rax+00h]
0x140001c18  mov     ebx, [rbx+58h]
0x140001c1b  mov     rcx, rdi; FastMutex
0x140001c1e  shr     ebx, 1
0x140001c20  and     bl, 1
0x140001c23  call    cs:__imp_ExReleaseFastMutex
0x140001c2a  nop     dword ptr [rax+rax+00h]
0x140001c2f  mov     al, bl
0x140001c31  mov     rbx, [rsp+28h+arg_0]
0x140001c36  add     rsp, 20h
0x140001c3a  pop     rdi
0x140001c3b  retn
```
