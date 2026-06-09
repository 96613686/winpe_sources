# RtlCopyFromUser

- ea: `0x1400014d4`
- end: `0x140001534`
- name: `RtlCopyFromUser`
- size: `96`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `12`
- callee_count: `3`
- tags: ``

## callers

- `0x140003010`
- `0x140012ff0`
- `0x140013c50`
- `0x140013ff0`
- `0x1400145d0`
- `0x1400168d0`
- `0x140016c00`
- `0x1400172f0`
- `0x1400175d0`
- `0x140018370`
- `0x140018664`
- `0x140020450`

## callees

- `0x1400014bf`
- `0x1400014d4`
- `0x140002510`

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
0x1400014d4  mov     [rsp+arg_0], rbx
0x1400014d9  mov     [rsp+arg_8], rsi
0x1400014de  push    rdi
0x1400014df  sub     rsp, 20h
0x1400014e3  mov     rax, cs:__uma_functions
0x1400014ea  mov     rbx, r8
0x1400014ed  mov     rdi, rdx
0x1400014f0  mov     rsi, rcx
0x1400014f3  test    rax, rax
0x1400014f6  jz      short loc_1400014FF
0x1400014f8  call    rax ; __uma_functions
0x1400014fa  nop     dword ptr [rax]
0x1400014fd  jmp     short loc_140001523
0x1400014ff  test    rbx, rbx
0x140001502  jz      short loc_140001523
0x140001504  mov     r8d, 1; Alignment
0x14000150a  mov     rdx, rbx; Length
0x14000150d  mov     rcx, rdi; Address
0x140001510  call    ProbeForRead_0
0x140001515  mov     r8, rbx; Size
0x140001518  mov     rdx, rdi; Src
0x14000151b  mov     rcx, rsi; void *
0x14000151e  call    RtlCopyVolatileMemory
0x140001523  mov     rbx, [rsp+28h+arg_0]
0x140001528  mov     rsi, [rsp+28h+arg_8]
0x14000152d  add     rsp, 20h
0x140001531  pop     rdi
0x140001532  retn
```
