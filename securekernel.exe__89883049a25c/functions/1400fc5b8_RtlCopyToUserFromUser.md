# RtlCopyToUserFromUser

- ea: `0x1400fc5b8`
- end: `0x1400fc624`
- name: `RtlCopyToUserFromUser`
- size: `108`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x1400406a4`
- `0x140041234`
- `0x140041954`
- `0x1400443c0`
- `0x1400aee6c`
- `0x1400afd58`
- `0x140107030`

## callees

- `0x1400442ac`
- `0x1400f38f0`
- `0x1400fc5b8`

## pseudocode

```c
void *__fastcall RtlCopyToUserFromUser(void *a1, void *Src, size_t Size)
{
  ProbeForRead(Src, Size, 1u);
  ProbeForRead(a1, Size, 1u);
  return RtlCopyVolatileMemory(a1, Src, Size);
}

```

## disassembly

```asm
0x1400fc5b8  mov     [rsp+arg_0], rbx
0x1400fc5bd  mov     [rsp+arg_8], rsi
0x1400fc5c2  push    rdi
0x1400fc5c3  sub     rsp, 20h
0x1400fc5c7  mov     rax, cs:qword_14010C3F0
0x1400fc5ce  mov     rbx, r8
0x1400fc5d1  mov     rdi, rdx
0x1400fc5d4  mov     rsi, rcx
0x1400fc5d7  test    rax, rax
0x1400fc5da  jz      short loc_1400FC5E3
0x1400fc5dc  call    rax ; qword_14010C3F0
0x1400fc5de  nop     dword ptr [rax]
0x1400fc5e1  jmp     short loc_1400FC613
0x1400fc5e3  mov     r8d, 1; Alignment
0x1400fc5e9  mov     rdx, rbx; Length
0x1400fc5ec  mov     rcx, rdi; Address
0x1400fc5ef  call    ProbeForRead
0x1400fc5f4  mov     r8d, 1; Alignment
0x1400fc5fa  mov     rdx, rbx; Length
0x1400fc5fd  mov     rcx, rsi; Address
0x1400fc600  call    ProbeForRead
0x1400fc605  mov     r8, rbx; Size
0x1400fc608  mov     rdx, rdi; Src
0x1400fc60b  mov     rcx, rsi; void *
0x1400fc60e  call    RtlCopyVolatileMemory
0x1400fc613  mov     rbx, [rsp+28h+arg_0]
0x1400fc618  mov     rsi, [rsp+28h+arg_8]
0x1400fc61d  add     rsp, 20h
0x1400fc621  pop     rdi
0x1400fc622  retn
```
