# _IsNonwritableInCurrentImage

- ea: `0x180001820`
- end: `0x18000186a`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001320`

## callees

- `0x1800017d0`
- `0x180001820`
- `0x180001870`

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
0x180001820  mov     [rsp+arg_0], rbx
0x180001825  push    rdi
0x180001826  sub     rsp, 20h
0x18000182a  mov     rbx, rcx
0x18000182d  lea     rdi, cs:180000000h
0x180001834  mov     rcx, rdi
0x180001837  call    _ValidateImageBase
0x18000183c  test    eax, eax
0x18000183e  jz      short loc_18000185F
0x180001840  sub     rbx, rdi
0x180001843  mov     rdx, rbx
0x180001846  mov     rcx, rdi
0x180001849  call    _FindPESection
0x18000184e  test    rax, rax
0x180001851  jz      short loc_18000185F
0x180001853  mov     eax, [rax+24h]
0x180001856  not     eax
0x180001858  shr     eax, 1Fh
0x18000185b  jmp     short loc_18000185F
0x18000185d  xor     eax, eax
0x18000185f  mov     rbx, [rsp+28h+arg_0]
0x180001864  add     rsp, 20h
0x180001868  pop     rdi
0x180001869  retn
0x180002bd0  push    rbp
0x180002bd2  sub     rsp, 20h
0x180002bd6  mov     rbp, rdx
0x180002bd9  mov     rax, [rcx]
0x180002bdc  xor     ecx, ecx
0x180002bde  cmp     dword ptr [rax], 0C0000005h
0x180002be4  setz    cl
0x180002be7  mov     eax, ecx
0x180002be9  add     rsp, 20h
0x180002bed  pop     rbp
0x180002bee  retn
```
