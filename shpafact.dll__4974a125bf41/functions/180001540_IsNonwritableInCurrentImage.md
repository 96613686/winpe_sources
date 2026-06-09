# _IsNonwritableInCurrentImage

- ea: `0x180001540`
- end: `0x18000158a`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001050`

## callees

- `0x1800014f0`
- `0x180001540`
- `0x180001590`

## pseudocode

```c
__int64 __fastcall IsNonwritableInCurrentImage(__int64 a1)
{
  __int64 result; // rax

  result = ValidateImageBase(&_ImageBase);
  if ( (_DWORD)result )
  {
    result = FindPESection(&_ImageBase, a1 - (_QWORD)&_ImageBase);
    if ( result )
      return *(_DWORD *)(result + 36) >= 0;
  }
  return result;
}

```

## disassembly

```asm
0x180001540  mov     [rsp+arg_0], rbx
0x180001545  push    rdi
0x180001546  sub     rsp, 20h
0x18000154a  mov     rbx, rcx
0x18000154d  lea     rdi, __ImageBase
0x180001554  mov     rcx, rdi
0x180001557  call    _ValidateImageBase
0x18000155c  test    eax, eax
0x18000155e  jz      short loc_18000157F
0x180001560  sub     rbx, rdi
0x180001563  mov     rdx, rbx
0x180001566  mov     rcx, rdi
0x180001569  call    _FindPESection
0x18000156e  test    rax, rax
0x180001571  jz      short loc_18000157F
0x180001573  mov     eax, [rax+24h]
0x180001576  not     eax
0x180001578  shr     eax, 1Fh
0x18000157b  jmp     short loc_18000157F
0x18000157d  xor     eax, eax
0x18000157f  mov     rbx, [rsp+28h+arg_0]
0x180001584  add     rsp, 20h
0x180001588  pop     rdi
0x180001589  retn
0x180003a00  push    rbp
0x180003a02  sub     rsp, 20h
0x180003a06  mov     rbp, rdx
0x180003a09  mov     rax, [rcx]
0x180003a0c  xor     ecx, ecx
0x180003a0e  cmp     dword ptr [rax], 0C0000005h
0x180003a14  setz    cl
0x180003a17  mov     eax, ecx
0x180003a19  add     rsp, 20h
0x180003a1d  pop     rbp
0x180003a1e  retn
```
