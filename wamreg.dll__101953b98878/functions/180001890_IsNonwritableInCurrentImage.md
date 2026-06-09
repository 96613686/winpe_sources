# _IsNonwritableInCurrentImage

- ea: `0x180001890`
- end: `0x1800018da`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800010d0`

## callees

- `0x180001840`
- `0x180001890`
- `0x1800018e0`

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
0x180001890  mov     [rsp+arg_0], rbx
0x180001895  push    rdi
0x180001896  sub     rsp, 20h
0x18000189a  mov     rbx, rcx
0x18000189d  lea     rdi, cs:180000000h
0x1800018a4  mov     rcx, rdi
0x1800018a7  call    _ValidateImageBase
0x1800018ac  test    eax, eax
0x1800018ae  jz      short loc_1800018CF
0x1800018b0  sub     rbx, rdi
0x1800018b3  mov     rdx, rbx
0x1800018b6  mov     rcx, rdi
0x1800018b9  call    _FindPESection
0x1800018be  test    rax, rax
0x1800018c1  jz      short loc_1800018CF
0x1800018c3  mov     eax, [rax+24h]
0x1800018c6  not     eax
0x1800018c8  shr     eax, 1Fh
0x1800018cb  jmp     short loc_1800018CF
0x1800018cd  xor     eax, eax
0x1800018cf  mov     rbx, [rsp+28h+arg_0]
0x1800018d4  add     rsp, 20h
0x1800018d8  pop     rdi
0x1800018d9  retn
0x180006bb0  push    rbp
0x180006bb2  sub     rsp, 20h
0x180006bb6  mov     rbp, rdx
0x180006bb9  mov     rax, [rcx]
0x180006bbc  xor     ecx, ecx
0x180006bbe  cmp     dword ptr [rax], 0C0000005h
0x180006bc4  setz    cl
0x180006bc7  mov     eax, ecx
0x180006bc9  add     rsp, 20h
0x180006bcd  pop     rbp
0x180006bce  retn
```
