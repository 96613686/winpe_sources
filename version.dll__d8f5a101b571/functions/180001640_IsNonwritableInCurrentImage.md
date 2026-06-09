# _IsNonwritableInCurrentImage

- ea: `0x180001640`
- end: `0x18000168a`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001150`

## callees

- `0x1800015f0`
- `0x180001640`
- `0x180001690`

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
0x180001640  mov     [rsp+arg_0], rbx
0x180001645  push    rdi
0x180001646  sub     rsp, 20h
0x18000164a  mov     rbx, rcx
0x18000164d  lea     rdi, cs:180000000h
0x180001654  mov     rcx, rdi
0x180001657  call    _ValidateImageBase
0x18000165c  test    eax, eax
0x18000165e  jz      short loc_18000167F
0x180001660  sub     rbx, rdi
0x180001663  mov     rdx, rbx
0x180001666  mov     rcx, rdi
0x180001669  call    _FindPESection
0x18000166e  test    rax, rax
0x180001671  jz      short loc_18000167F
0x180001673  mov     eax, [rax+24h]
0x180001676  not     eax
0x180001678  shr     eax, 1Fh
0x18000167b  jmp     short loc_18000167F
0x18000167d  xor     eax, eax
0x18000167f  mov     rbx, [rsp+28h+arg_0]
0x180001684  add     rsp, 20h
0x180001688  pop     rdi
0x180001689  retn
0x1800034f0  push    rbp
0x1800034f2  sub     rsp, 20h
0x1800034f6  mov     rbp, rdx
0x1800034f9  mov     rax, [rcx]
0x1800034fc  xor     ecx, ecx
0x1800034fe  cmp     dword ptr [rax], 0C0000005h
0x180003504  setz    cl
0x180003507  mov     eax, ecx
0x180003509  add     rsp, 20h
0x18000350d  pop     rbp
0x18000350e  retn
```
