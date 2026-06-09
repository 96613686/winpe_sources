# RtlCopyToUser

- ea: `0x14001439c`
- end: `0x1400143f9`
- name: `RtlCopyToUser`
- size: `93`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x140009020`
- `0x140015a70`
- `0x140015dc4`
- `0x140016734`
- `0x140016aa8`
- `0x140016d68`
- `0x14001771c`
- `0x1400179f4`
- `0x140017ad0`

## callees

- `0x14000403f`
- `0x140007c90`
- `0x14001439c`

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
0x14001439c  mov     [rsp+arg_0], rbx
0x1400143a1  mov     [rsp+arg_8], rsi
0x1400143a6  push    rdi
0x1400143a7  sub     rsp, 20h
0x1400143ab  mov     rax, cs:qword_1400117B0
0x1400143b2  mov     rbx, r8
0x1400143b5  mov     rsi, rdx
0x1400143b8  mov     rdi, rcx
0x1400143bb  test    rax, rax
0x1400143be  jz      short loc_1400143C7
0x1400143c0  call    rax ; qword_1400117B0
0x1400143c2  nop     dword ptr [rax]
0x1400143c5  jmp     short loc_1400143E8
0x1400143c7  test    rbx, rbx
0x1400143ca  jz      short loc_1400143E8
0x1400143cc  mov     r8d, 1; Alignment
0x1400143d2  mov     rdx, rbx; Length
0x1400143d5  call    ProbeForRead_0
0x1400143da  mov     r8, rbx; Size
0x1400143dd  mov     rdx, rsi; Src
0x1400143e0  mov     rcx, rdi; void *
0x1400143e3  call    RtlCopyVolatileMemory
0x1400143e8  mov     rbx, [rsp+28h+arg_0]
0x1400143ed  mov     rsi, [rsp+28h+arg_8]
0x1400143f2  add     rsp, 20h
0x1400143f6  pop     rdi
0x1400143f7  retn
```
