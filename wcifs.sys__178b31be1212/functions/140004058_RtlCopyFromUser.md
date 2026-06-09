# RtlCopyFromUser

- ea: `0x140004058`
- end: `0x1400040b8`
- name: `RtlCopyFromUser`
- size: `96`
- prototype: `__int64 (*__fastcall(void *, void *Src, size_t Size))(void)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140009010`
- `0x14001a364`
- `0x140031e90`

## callees

- `0x14000403f`
- `0x140004058`
- `0x140007c90`

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
0x140004058  mov     [rsp+arg_0], rbx
0x14000405d  mov     [rsp+arg_8], rsi
0x140004062  push    rdi
0x140004063  sub     rsp, 20h
0x140004067  mov     rax, cs:__uma_functions
0x14000406e  mov     rbx, r8
0x140004071  mov     rdi, rdx
0x140004074  mov     rsi, rcx
0x140004077  test    rax, rax
0x14000407a  jz      short loc_140004083
0x14000407c  call    rax ; __uma_functions
0x14000407e  nop     dword ptr [rax]
0x140004081  jmp     short loc_1400040A7
0x140004083  test    rbx, rbx
0x140004086  jz      short loc_1400040A7
0x140004088  mov     r8d, 1; Alignment
0x14000408e  mov     rdx, rbx; Length
0x140004091  mov     rcx, rdi; Address
0x140004094  call    ProbeForRead_0
0x140004099  mov     r8, rbx; Size
0x14000409c  mov     rdx, rdi; Src
0x14000409f  mov     rcx, rsi; void *
0x1400040a2  call    RtlCopyVolatileMemory
0x1400040a7  mov     rbx, [rsp+28h+arg_0]
0x1400040ac  mov     rsi, [rsp+28h+arg_8]
0x1400040b1  add     rsp, 20h
0x1400040b5  pop     rdi
0x1400040b6  retn
```
