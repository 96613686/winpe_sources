# _IsNonwritableInCurrentImage

- ea: `0x140001690`
- end: `0x1400016da`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140001140`

## callees

- `0x140001640`
- `0x140001690`
- `0x1400016e0`

## pseudocode

```c
__int64 __fastcall IsNonwritableInCurrentImage(__int64 a1)
{
  __int64 result; // rax

  result = ValidateImageBase(0x140000000uLL);
  if ( (_DWORD)result )
  {
    result = FindPESection(0x140000000uLL, a1 - 0x140000000LL);
    if ( result )
      return *(_DWORD *)(result + 36) >= 0;
  }
  return result;
}

```

## disassembly

```asm
0x140001690  mov     [rsp+arg_0], rbx
0x140001695  push    rdi
0x140001696  sub     rsp, 20h
0x14000169a  mov     rbx, rcx
0x14000169d  lea     rdi, cs:140000000h
0x1400016a4  mov     rcx, rdi
0x1400016a7  call    _ValidateImageBase
0x1400016ac  test    eax, eax
0x1400016ae  jz      short loc_1400016CF
0x1400016b0  sub     rbx, rdi
0x1400016b3  mov     rdx, rbx
0x1400016b6  mov     rcx, rdi
0x1400016b9  call    _FindPESection
0x1400016be  test    rax, rax
0x1400016c1  jz      short loc_1400016CF
0x1400016c3  mov     eax, [rax+24h]
0x1400016c6  not     eax
0x1400016c8  shr     eax, 1Fh
0x1400016cb  jmp     short loc_1400016CF
0x1400016cd  xor     eax, eax
0x1400016cf  mov     rbx, [rsp+28h+arg_0]
0x1400016d4  add     rsp, 20h
0x1400016d8  pop     rdi
0x1400016d9  retn
0x1400039c0  push    rbp
0x1400039c2  sub     rsp, 20h
0x1400039c6  mov     rbp, rdx
0x1400039c9  mov     rax, [rcx]
0x1400039cc  xor     ecx, ecx
0x1400039ce  cmp     dword ptr [rax], 0C0000005h
0x1400039d4  setz    cl
0x1400039d7  mov     eax, ecx
0x1400039d9  add     rsp, 20h
0x1400039dd  pop     rbp
0x1400039de  retn
```
