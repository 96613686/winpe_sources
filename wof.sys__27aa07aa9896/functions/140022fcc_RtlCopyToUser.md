# RtlCopyToUser

- ea: `0x140022fcc`
- end: `0x140023029`
- name: `RtlCopyToUser`
- size: `93`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x140012020`
- `0x140022220`
- `0x14002378c`
- `0x14002382c`
- `0x1400376f0`
- `0x140037d20`
- `0x14003ba5c`
- `0x14003bf4c`
- `0x14003e0b8`

## callees

- `0x14000da43`
- `0x140011590`
- `0x140022fcc`

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
0x140022fcc  mov     [rsp+arg_0], rbx
0x140022fd1  mov     [rsp+arg_8], rsi
0x140022fd6  push    rdi
0x140022fd7  sub     rsp, 20h
0x140022fdb  mov     rax, cs:qword_14001E850
0x140022fe2  mov     rbx, r8
0x140022fe5  mov     rsi, rdx
0x140022fe8  mov     rdi, rcx
0x140022feb  test    rax, rax
0x140022fee  jz      short loc_140022FF7
0x140022ff0  call    rax ; qword_14001E850
0x140022ff2  nop     dword ptr [rax]
0x140022ff5  jmp     short loc_140023018
0x140022ff7  test    rbx, rbx
0x140022ffa  jz      short loc_140023018
0x140022ffc  mov     r8d, 1; Alignment
0x140023002  mov     rdx, rbx; Length
0x140023005  call    ProbeForRead_0
0x14002300a  mov     r8, rbx; Size
0x14002300d  mov     rdx, rsi; Src
0x140023010  mov     rcx, rdi; void *
0x140023013  call    RtlCopyVolatileMemory
0x140023018  mov     rbx, [rsp+28h+arg_0]
0x14002301d  mov     rsi, [rsp+28h+arg_8]
0x140023022  add     rsp, 20h
0x140023026  pop     rdi
0x140023027  retn
```
