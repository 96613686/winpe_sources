# HviIsHypervisorMicrosoftCompatible

- ea: `0x14000c610`
- end: `0x14000c645`
- name: `HviIsHypervisorMicrosoftCompatible`
- size: `53`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000c490`
- `0x14000c4d0`
- `0x14000c510`
- `0x14000c568`
- `0x14000c64c`

## callees

- `0x14000c5d0`
- `0x14000c610`

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
0x14000c610  push    rbx
0x14000c612  sub     rsp, 30h
0x14000c616  xorps   xmm0, xmm0
0x14000c619  movups  [rsp+38h+var_18], xmm0
0x14000c61e  call    HviIsAnyHypervisorPresent
0x14000c623  test    al, al
0x14000c625  jz      short loc_14000C632
0x14000c627  mov     eax, 40000001h
0x14000c62c  xor     ecx, ecx
0x14000c62e  cpuid
0x14000c630  jmp     short loc_14000C636
0x14000c632  mov     eax, dword ptr [rsp+38h+var_18]
0x14000c636  cmp     eax, 31237648h
0x14000c63b  setz    al
0x14000c63e  add     rsp, 30h
0x14000c642  pop     rbx
0x14000c643  retn
```
