# _IsNonwritableInCurrentImage

- ea: `0x180001c60`
- end: `0x180001cad`
- name: `_IsNonwritableInCurrentImage`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001654`

## callees

- `0x180001c10`
- `0x180001c60`
- `0x180001cb0`

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
      return *(int *)(result + 36) >= 0;
  }
  return result;
}

```

## disassembly

```asm
0x180001c60  mov     [rsp+arg_0], rbx
0x180001c65  push    rdi
0x180001c66  sub     rsp, 20h
0x180001c6a  mov     rbx, rcx
0x180001c6d  lea     rdi, cs:180000000h
0x180001c74  mov     rcx, rdi
0x180001c77  call    _ValidateImageBase
0x180001c7c  test    eax, eax
0x180001c7e  jz      short loc_180001CA2
0x180001c80  sub     rbx, rdi
0x180001c83  mov     rdx, rbx
0x180001c86  mov     rcx, rdi
0x180001c89  call    _FindPESection
0x180001c8e  test    rax, rax
0x180001c91  jz      short loc_180001CA2
0x180001c93  mov     eax, [rax+24h]
0x180001c96  shr     eax, 1Fh
0x180001c99  not     eax
0x180001c9b  and     eax, 1
0x180001c9e  jmp     short loc_180001CA2
0x180001ca0  xor     eax, eax
0x180001ca2  mov     rbx, [rsp+28h+arg_0]
0x180001ca7  add     rsp, 20h
0x180001cab  pop     rdi
0x180001cac  retn
0x1800025f0  push    rbp
0x1800025f2  sub     rsp, 20h
0x1800025f6  mov     rbp, rdx
0x1800025f9  mov     rax, [rcx]
0x1800025fc  xor     ecx, ecx
0x1800025fe  cmp     dword ptr [rax], 0C0000005h
0x180002604  setz    cl
0x180002607  mov     eax, ecx
0x180002609  add     rsp, 20h
0x18000260d  pop     rbp
0x18000260e  retn
```
