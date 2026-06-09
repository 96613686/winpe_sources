# RtlCopyFromUser

- ea: `0x140001044`
- end: `0x1400010a4`
- name: `RtlCopyFromUser`
- size: `96`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140004010`
- `0x14000adb4`

## callees

- `0x14000102f`
- `0x140001044`
- `0x140002be0`

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
0x140001044  mov     [rsp+arg_0], rbx
0x140001049  mov     [rsp+arg_8], rsi
0x14000104e  push    rdi
0x14000104f  sub     rsp, 20h
0x140001053  mov     rax, cs:__uma_functions
0x14000105a  mov     rbx, r8
0x14000105d  mov     rdi, rdx
0x140001060  mov     rsi, rcx
0x140001063  test    rax, rax
0x140001066  jz      short loc_14000106F
0x140001068  call    rax ; __uma_functions
0x14000106a  nop     dword ptr [rax]
0x14000106d  jmp     short loc_140001093
0x14000106f  test    rbx, rbx
0x140001072  jz      short loc_140001093
0x140001074  mov     r8d, 1; Alignment
0x14000107a  mov     rdx, rbx; Length
0x14000107d  mov     rcx, rdi; Address
0x140001080  call    ProbeForRead_0
0x140001085  mov     r8, rbx; Size
0x140001088  mov     rdx, rdi; Src
0x14000108b  mov     rcx, rsi; void *
0x14000108e  call    RtlCopyVolatileMemory
0x140001093  mov     rbx, [rsp+28h+arg_0]
0x140001098  mov     rsi, [rsp+28h+arg_8]
0x14000109d  add     rsp, 20h
0x1400010a1  pop     rdi
0x1400010a2  retn
```
