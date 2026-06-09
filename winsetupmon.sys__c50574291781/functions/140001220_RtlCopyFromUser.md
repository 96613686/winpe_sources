# RtlCopyFromUser

- ea: `0x140001220`
- end: `0x140001280`
- name: `RtlCopyFromUser`
- size: `96`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x140011010`
- `0x14001e044`
- `0x14001e174`
- `0x14001e23c`
- `0x14001e2ec`
- `0x14001e464`
- `0x14001e524`
- `0x14001e5cc`
- `0x14001e630`
- `0x14001e71c`

## callees

- `0x140001220`
- `0x1400012a6`
- `0x14000f930`

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
0x140001220  mov     [rsp+arg_0], rbx
0x140001225  mov     [rsp+arg_8], rsi
0x14000122a  push    rdi
0x14000122b  sub     rsp, 20h
0x14000122f  mov     rax, cs:__uma_functions
0x140001236  mov     rbx, r8
0x140001239  mov     rdi, rdx
0x14000123c  mov     rsi, rcx
0x14000123f  test    rax, rax
0x140001242  jz      short loc_14000124B
0x140001244  call    rax ; __uma_functions
0x140001246  nop     dword ptr [rax]
0x140001249  jmp     short loc_14000126F
0x14000124b  test    rbx, rbx
0x14000124e  jz      short loc_14000126F
0x140001250  mov     r8d, 1; Alignment
0x140001256  mov     rdx, rbx; Length
0x140001259  mov     rcx, rdi; Address
0x14000125c  call    ProbeForRead_0
0x140001261  mov     r8, rbx; Size
0x140001264  mov     rdx, rdi; Src
0x140001267  mov     rcx, rsi; void *
0x14000126a  call    RtlCopyVolatileMemory
0x14000126f  mov     rbx, [rsp+28h+arg_0]
0x140001274  mov     rsi, [rsp+28h+arg_8]
0x140001279  add     rsp, 20h
0x14000127d  pop     rdi
0x14000127e  retn
```
