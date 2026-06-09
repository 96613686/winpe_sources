# _IsNonwritableInCurrentImage

- ea: `0x180002500`
- end: `0x18000254a`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001fe0`

## callees

- `0x1800024b0`
- `0x180002500`
- `0x180002550`

## pseudocode

```c
__int64 __fastcall IsNonwritableInCurrentImage(__int64 a1)
{
  __int64 result; // rax

  result = ValidateImageBase(0x180000000uLL);
  if ( (_DWORD)result )
  {
    result = FindPESection(0x180000000uLL, a1 - 0x180000000LL);
    if ( result )
      return *(_DWORD *)(result + 36) >= 0;
  }
  return result;
}

```

## disassembly

```asm
0x180002500  mov     [rsp+arg_0], rbx
0x180002505  push    rdi
0x180002506  sub     rsp, 20h
0x18000250a  mov     rbx, rcx
0x18000250d  lea     rdi, cs:180000000h
0x180002514  mov     rcx, rdi
0x180002517  call    _ValidateImageBase
0x18000251c  test    eax, eax
0x18000251e  jz      short loc_18000253F
0x180002520  sub     rbx, rdi
0x180002523  mov     rdx, rbx
0x180002526  mov     rcx, rdi
0x180002529  call    _FindPESection
0x18000252e  test    rax, rax
0x180002531  jz      short loc_18000253F
0x180002533  mov     eax, [rax+24h]
0x180002536  not     eax
0x180002538  shr     eax, 1Fh
0x18000253b  jmp     short loc_18000253F
0x18000253d  xor     eax, eax
0x18000253f  mov     rbx, [rsp+28h+arg_0]
0x180002544  add     rsp, 20h
0x180002548  pop     rdi
0x180002549  retn
0x180004510  push    rbp
0x180004512  sub     rsp, 20h
0x180004516  mov     rbp, rdx
0x180004519  mov     rax, [rcx]
0x18000451c  xor     ecx, ecx
0x18000451e  cmp     dword ptr [rax], 0C0000005h
0x180004524  setz    cl
0x180004527  mov     eax, ecx
0x180004529  add     rsp, 20h
0x18000452d  pop     rbp
0x18000452e  retn
```
