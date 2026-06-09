# _IsNonwritableInCurrentImage

- ea: `0x180001830`
- end: `0x18000187a`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001330`

## callees

- `0x1800017e0`
- `0x180001830`
- `0x180001880`

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
0x180001830  mov     [rsp+arg_0], rbx
0x180001835  push    rdi
0x180001836  sub     rsp, 20h
0x18000183a  mov     rbx, rcx
0x18000183d  lea     rdi, cs:180000000h
0x180001844  mov     rcx, rdi
0x180001847  call    _ValidateImageBase
0x18000184c  test    eax, eax
0x18000184e  jz      short loc_18000186F
0x180001850  sub     rbx, rdi
0x180001853  mov     rdx, rbx
0x180001856  mov     rcx, rdi
0x180001859  call    _FindPESection
0x18000185e  test    rax, rax
0x180001861  jz      short loc_18000186F
0x180001863  mov     eax, [rax+24h]
0x180001866  not     eax
0x180001868  shr     eax, 1Fh
0x18000186b  jmp     short loc_18000186F
0x18000186d  xor     eax, eax
0x18000186f  mov     rbx, [rsp+28h+arg_0]
0x180001874  add     rsp, 20h
0x180001878  pop     rdi
0x180001879  retn
0x180002c90  push    rbp
0x180002c92  sub     rsp, 20h
0x180002c96  mov     rbp, rdx
0x180002c99  mov     rax, [rcx]
0x180002c9c  xor     ecx, ecx
0x180002c9e  cmp     dword ptr [rax], 0C0000005h
0x180002ca4  setz    cl
0x180002ca7  mov     eax, ecx
0x180002ca9  add     rsp, 20h
0x180002cad  pop     rbp
0x180002cae  retn
```
