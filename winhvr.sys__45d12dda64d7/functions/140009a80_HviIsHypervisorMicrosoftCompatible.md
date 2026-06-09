# HviIsHypervisorMicrosoftCompatible

- ea: `0x140009a80`
- end: `0x140009ab5`
- name: `HviIsHypervisorMicrosoftCompatible`
- size: `53`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140009a00`
- `0x14001be40`

## callees

- `0x140009a40`
- `0x140009a80`

## pseudocode

```c
bool HviIsHypervisorMicrosoftCompatible()
{
  if ( (unsigned __int8)HviIsAnyHypervisorPresent() )
  {
    _RAX = 1073741825;
    __asm { cpuid }
  }
  else
  {
    LODWORD(_RAX) = 0;
  }
  return (_DWORD)_RAX == 824407624;
}

```

## disassembly

```asm
0x140009a80  push    rbx
0x140009a82  sub     rsp, 30h
0x140009a86  xorps   xmm0, xmm0
0x140009a89  movups  [rsp+38h+var_18], xmm0
0x140009a8e  call    HviIsAnyHypervisorPresent
0x140009a93  test    al, al
0x140009a95  jz      short loc_140009AA2
0x140009a97  mov     eax, 40000001h
0x140009a9c  xor     ecx, ecx
0x140009a9e  cpuid
0x140009aa0  jmp     short loc_140009AA6
0x140009aa2  mov     eax, dword ptr [rsp+38h+var_18]
0x140009aa6  cmp     eax, 31237648h
0x140009aab  setz    al
0x140009aae  add     rsp, 30h
0x140009ab2  pop     rbx
0x140009ab3  retn
```
