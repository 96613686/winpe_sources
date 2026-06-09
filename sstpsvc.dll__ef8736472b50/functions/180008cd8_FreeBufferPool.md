# FreeBufferPool

- ea: `0x180008cd8`
- end: `0x180008d33`
- name: `FreeBufferPool`
- size: `91`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003bc0`
- `0x1800059f0`

## callees

- `0x180007f48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008cec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008cec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008d0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008d0a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008d19`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008d19`

## pseudocode

```c
char __fastcall FreeBufferPool(__int64 a1)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  __int64 v2; // rbx

  v1 = (struct _RTL_CRITICAL_SECTION *)(a1 + 64);
  v2 = a1;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 64));
  FreeUnusedBufferPoolBlocks(v2);
  LOBYTE(v2) = *(_DWORD *)(v2 + 12) == 0;
  LeaveCriticalSection(v1);
  DeleteCriticalSection(v1);
  return v2;
}

```

## disassembly

```asm
0x180008cd8  mov     [rsp+arg_0], rbx
0x180008cdd  push    rdi
0x180008cde  sub     rsp, 20h
0x180008ce2  lea     rdi, [rcx+40h]
0x180008ce6  mov     rbx, rcx
0x180008ce9  mov     rcx, rdi; lpCriticalSection
0x180008cec  call    cs:__imp_EnterCriticalSection
0x180008cf3  nop     dword ptr [rax+rax+00h]
0x180008cf8  mov     rcx, rbx
0x180008cfb  call    FreeUnusedBufferPoolBlocks
0x180008d00  cmp     dword ptr [rbx+0Ch], 0
0x180008d04  mov     rcx, rdi; lpCriticalSection
0x180008d07  setz    bl
0x180008d0a  call    cs:__imp_LeaveCriticalSection
0x180008d11  nop     dword ptr [rax+rax+00h]
0x180008d16  mov     rcx, rdi; lpCriticalSection
0x180008d19  call    cs:__imp_DeleteCriticalSection
0x180008d20  nop     dword ptr [rax+rax+00h]
0x180008d25  mov     al, bl
0x180008d27  mov     rbx, [rsp+28h+arg_0]
0x180008d2c  add     rsp, 20h
0x180008d30  pop     rdi
0x180008d31  retn
```
