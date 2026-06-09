# _IsNonwritableInCurrentImage

- ea: `0x1800015e0`
- end: `0x18000162a`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800010f0`

## callees

- `0x180001590`
- `0x1800015e0`
- `0x180001630`

## pseudocode

```c
__int64 __fastcall IsNonwritableInCurrentImage(__int64 a1)
{
  __int64 result; // rax

  result = ValidateImageBase(&_ImageBase);
  if ( (_DWORD)result )
  {
    result = FindPESection((__int64)&_ImageBase, a1 - (_QWORD)&_ImageBase);
    if ( result )
      return *(_DWORD *)(result + 36) >= 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800015e0  mov     [rsp+arg_0], rbx
0x1800015e5  push    rdi
0x1800015e6  sub     rsp, 20h
0x1800015ea  mov     rbx, rcx
0x1800015ed  lea     rdi, __ImageBase
0x1800015f4  mov     rcx, rdi
0x1800015f7  call    _ValidateImageBase
0x1800015fc  test    eax, eax
0x1800015fe  jz      short loc_18000161F
0x180001600  sub     rbx, rdi
0x180001603  mov     rdx, rbx
0x180001606  mov     rcx, rdi
0x180001609  call    _FindPESection
0x18000160e  test    rax, rax
0x180001611  jz      short loc_18000161F
0x180001613  mov     eax, [rax+24h]
0x180001616  not     eax
0x180001618  shr     eax, 1Fh
0x18000161b  jmp     short loc_18000161F
0x18000161d  xor     eax, eax
0x18000161f  mov     rbx, [rsp+28h+arg_0]
0x180001624  add     rsp, 20h
0x180001628  pop     rdi
0x180001629  retn
0x180003f80  push    rbp
0x180003f82  sub     rsp, 20h
0x180003f86  mov     rbp, rdx
0x180003f89  mov     rax, [rcx]
0x180003f8c  xor     ecx, ecx
0x180003f8e  cmp     dword ptr [rax], 0C0000005h
0x180003f94  setz    cl
0x180003f97  mov     eax, ecx
0x180003f99  add     rsp, 20h
0x180003f9d  pop     rbp
0x180003f9e  retn
```
