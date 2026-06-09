# HviIsAnyHypervisorPresent

- ea: `0x140009a40`
- end: `0x140009a7a`
- name: `HviIsAnyHypervisorPresent`
- size: `58`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140009a80`
- `0x14001be40`
- `0x14002a804`

## callees

- `0x140009a40`

## pseudocode

```c
bool HviIsAnyHypervisorPresent()
{
  char v1; // r8

  _RAX = 1;
  v1 = 0;
  __asm { cpuid }
  if ( (int)_RCX < 0 )
  {
    _RAX = 1073741825;
    __asm { cpuid }
    return (_DWORD)_RAX != 1986945624;
  }
  return v1;
}

```

## disassembly

```asm
0x140009a40  push    rbx
0x140009a42  sub     rsp, 10h
0x140009a46  xor     ecx, ecx
0x140009a48  mov     r9d, 1
0x140009a4e  mov     eax, r9d
0x140009a51  xor     r8b, r8b
0x140009a54  cpuid
0x140009a56  test    ecx, ecx
0x140009a58  jns     short loc_140009A70
0x140009a5a  xor     ecx, ecx
0x140009a5c  movzx   r8d, r8b
0x140009a60  mov     eax, 40000001h
0x140009a65  cpuid
0x140009a67  cmp     eax, 766E6258h
0x140009a6c  cmovnz  r8d, r9d
0x140009a70  mov     al, r8b
0x140009a73  add     rsp, 10h
0x140009a77  pop     rbx
0x140009a78  retn
```
