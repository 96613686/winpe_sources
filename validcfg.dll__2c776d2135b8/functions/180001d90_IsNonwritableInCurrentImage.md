# _IsNonwritableInCurrentImage

- ea: `0x180001d90`
- end: `0x180001dda`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001870`

## callees

- `0x180001d40`
- `0x180001d90`
- `0x180001de0`

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
0x180001d90  mov     [rsp+arg_0], rbx
0x180001d95  push    rdi
0x180001d96  sub     rsp, 20h
0x180001d9a  mov     rbx, rcx
0x180001d9d  lea     rdi, cs:180000000h
0x180001da4  mov     rcx, rdi
0x180001da7  call    _ValidateImageBase
0x180001dac  test    eax, eax
0x180001dae  jz      short loc_180001DCF
0x180001db0  sub     rbx, rdi
0x180001db3  mov     rdx, rbx
0x180001db6  mov     rcx, rdi
0x180001db9  call    _FindPESection
0x180001dbe  test    rax, rax
0x180001dc1  jz      short loc_180001DCF
0x180001dc3  mov     eax, [rax+24h]
0x180001dc6  not     eax
0x180001dc8  shr     eax, 1Fh
0x180001dcb  jmp     short loc_180001DCF
0x180001dcd  xor     eax, eax
0x180001dcf  mov     rbx, [rsp+28h+arg_0]
0x180001dd4  add     rsp, 20h
0x180001dd8  pop     rdi
0x180001dd9  retn
0x1800034a0  push    rbp
0x1800034a2  sub     rsp, 20h
0x1800034a6  mov     rbp, rdx
0x1800034a9  mov     rax, [rcx]
0x1800034ac  xor     ecx, ecx
0x1800034ae  cmp     dword ptr [rax], 0C0000005h
0x1800034b4  setz    cl
0x1800034b7  mov     eax, ecx
0x1800034b9  add     rsp, 20h
0x1800034bd  pop     rbp
0x1800034be  retn
```
