# _IsNonwritableInCurrentImage

- ea: `0x1800020b0`
- end: `0x1800020fa`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001a00`

## callees

- `0x180002060`
- `0x1800020b0`
- `0x180002100`

## pseudocode

```c
__int64 __fastcall IsNonwritableInCurrentImage(__int64 a1)
{
  __int64 result; // rax

  result = ValidateImageBase(0x180000000uLL);
  if ( (_DWORD)result )
  {
    result = FindPESection(0x180000000LL, a1 - 0x180000000LL);
    if ( result )
      return *(_DWORD *)(result + 36) >= 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800020b0  mov     [rsp+arg_0], rbx
0x1800020b5  push    rdi
0x1800020b6  sub     rsp, 20h
0x1800020ba  mov     rbx, rcx
0x1800020bd  lea     rdi, cs:180000000h
0x1800020c4  mov     rcx, rdi
0x1800020c7  call    _ValidateImageBase
0x1800020cc  test    eax, eax
0x1800020ce  jz      short loc_1800020EF
0x1800020d0  sub     rbx, rdi
0x1800020d3  mov     rdx, rbx
0x1800020d6  mov     rcx, rdi
0x1800020d9  call    _FindPESection
0x1800020de  test    rax, rax
0x1800020e1  jz      short loc_1800020EF
0x1800020e3  mov     eax, [rax+24h]
0x1800020e6  not     eax
0x1800020e8  shr     eax, 1Fh
0x1800020eb  jmp     short loc_1800020EF
0x1800020ed  xor     eax, eax
0x1800020ef  mov     rbx, [rsp+28h+arg_0]
0x1800020f4  add     rsp, 20h
0x1800020f8  pop     rdi
0x1800020f9  retn
0x180003f40  push    rbp
0x180003f42  sub     rsp, 20h
0x180003f46  mov     rbp, rdx
0x180003f49  mov     rax, [rcx]
0x180003f4c  xor     ecx, ecx
0x180003f4e  cmp     dword ptr [rax], 0C0000005h
0x180003f54  setz    cl
0x180003f57  mov     eax, ecx
0x180003f59  add     rsp, 20h
0x180003f5d  pop     rbp
0x180003f5e  retn
```
