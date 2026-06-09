# RtlCopyFromUser

- ea: `0x1400121d8`
- end: `0x140012238`
- name: `RtlCopyFromUser`
- size: `96`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140010f10`
- `0x14001606c`
- `0x140016fec`
- `0x140019010`

## callees

- `0x1400121d8`
- `0x140012246`
- `0x1400184e0`

## pseudocode

```c
__int64 (*__fastcall RtlCopyFromUser(void *a1, void *Src, size_t Size))(void)
{
  __int64 (*result)(void); // rax

  result = _uma_functions;
  if ( _uma_functions )
    return (__int64 (*)(void))_uma_functions();
  if ( Size )
  {
    ProbeForRead_0(Src, Size, 1u);
    return (__int64 (*)(void))RtlCopyVolatileMemory(a1, Src, Size);
  }
  return result;
}

```

## disassembly

```asm
0x1400121d8  mov     [rsp+arg_0], rbx
0x1400121dd  mov     [rsp+arg_8], rsi
0x1400121e2  push    rdi
0x1400121e3  sub     rsp, 20h
0x1400121e7  mov     rax, cs:__uma_functions
0x1400121ee  mov     rbx, r8
0x1400121f1  mov     rdi, rdx
0x1400121f4  mov     rsi, rcx
0x1400121f7  test    rax, rax
0x1400121fa  jz      short loc_140012203
0x1400121fc  call    rax ; __uma_functions
0x1400121fe  nop     dword ptr [rax]
0x140012201  jmp     short loc_140012227
0x140012203  test    rbx, rbx
0x140012206  jz      short loc_140012227
0x140012208  mov     r8d, 1; Alignment
0x14001220e  mov     rdx, rbx; Length
0x140012211  mov     rcx, rdi; Address
0x140012214  call    ProbeForRead_0
0x140012219  mov     r8, rbx; Size
0x14001221c  mov     rdx, rdi; Src
0x14001221f  mov     rcx, rsi; void *
0x140012222  call    RtlCopyVolatileMemory
0x140012227  mov     rbx, [rsp+28h+arg_0]
0x14001222c  mov     rsi, [rsp+28h+arg_8]
0x140012231  add     rsp, 20h
0x140012235  pop     rdi
0x140012236  retn
```
