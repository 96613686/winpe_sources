# _IsNonwritableInCurrentImage

- ea: `0x180001910`
- end: `0x18000195a`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800013f0`

## callees

- `0x1800018c0`
- `0x180001910`
- `0x180001960`

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
0x180001910  mov     [rsp+arg_0], rbx
0x180001915  push    rdi
0x180001916  sub     rsp, 20h
0x18000191a  mov     rbx, rcx
0x18000191d  lea     rdi, cs:180000000h
0x180001924  mov     rcx, rdi
0x180001927  call    _ValidateImageBase
0x18000192c  test    eax, eax
0x18000192e  jz      short loc_18000194F
0x180001930  sub     rbx, rdi
0x180001933  mov     rdx, rbx
0x180001936  mov     rcx, rdi
0x180001939  call    _FindPESection
0x18000193e  test    rax, rax
0x180001941  jz      short loc_18000194F
0x180001943  mov     eax, [rax+24h]
0x180001946  not     eax
0x180001948  shr     eax, 1Fh
0x18000194b  jmp     short loc_18000194F
0x18000194d  xor     eax, eax
0x18000194f  mov     rbx, [rsp+28h+arg_0]
0x180001954  add     rsp, 20h
0x180001958  pop     rdi
0x180001959  retn
0x180006b50  push    rbp
0x180006b52  sub     rsp, 20h
0x180006b56  mov     rbp, rdx
0x180006b59  mov     rax, [rcx]
0x180006b5c  xor     ecx, ecx
0x180006b5e  cmp     dword ptr [rax], 0C0000005h
0x180006b64  setz    cl
0x180006b67  mov     eax, ecx
0x180006b69  add     rsp, 20h
0x180006b6d  pop     rbp
0x180006b6e  retn
```
