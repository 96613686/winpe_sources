# RtlCopyToUser

- ea: `0x14000d198`
- end: `0x14000d1f5`
- name: `RtlCopyToUser`
- size: `93`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x140003020`
- `0x140012154`
- `0x1400122b8`
- `0x140013690`
- `0x1400147e0`
- `0x140017950`
- `0x140017e20`
- `0x14001e120`

## callees

- `0x1400014bf`
- `0x140002510`
- `0x14000d198`

## pseudocode

```c
void *__fastcall RtlCopyToUser(void *a1, void *Src, size_t Size)
{
  void *result; // rax

  result = 0;
  if ( Size )
  {
    ProbeForRead_0(a1, Size, 1u);
    return RtlCopyVolatileMemory(a1, Src, Size);
  }
  return result;
}

```

## disassembly

```asm
0x14000d198  mov     [rsp+arg_0], rbx
0x14000d19d  mov     [rsp+arg_8], rsi
0x14000d1a2  push    rdi
0x14000d1a3  sub     rsp, 20h
0x14000d1a7  mov     rax, cs:qword_14000A450
0x14000d1ae  mov     rbx, r8
0x14000d1b1  mov     rsi, rdx
0x14000d1b4  mov     rdi, rcx
0x14000d1b7  test    rax, rax
0x14000d1ba  jz      short loc_14000D1C3
0x14000d1bc  call    rax ; qword_14000A450
0x14000d1be  nop     dword ptr [rax]
0x14000d1c1  jmp     short loc_14000D1E4
0x14000d1c3  test    rbx, rbx
0x14000d1c6  jz      short loc_14000D1E4
0x14000d1c8  mov     r8d, 1; Alignment
0x14000d1ce  mov     rdx, rbx; Length
0x14000d1d1  call    ProbeForRead_0
0x14000d1d6  mov     r8, rbx; Size
0x14000d1d9  mov     rdx, rsi; Src
0x14000d1dc  mov     rcx, rdi; void *
0x14000d1df  call    RtlCopyVolatileMemory
0x14000d1e4  mov     rbx, [rsp+28h+arg_0]
0x14000d1e9  mov     rsi, [rsp+28h+arg_8]
0x14000d1ee  add     rsp, 20h
0x14000d1f2  pop     rdi
0x14000d1f3  retn
```
