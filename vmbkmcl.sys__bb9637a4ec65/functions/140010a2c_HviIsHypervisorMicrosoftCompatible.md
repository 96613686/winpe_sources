# HviIsHypervisorMicrosoftCompatible

- ea: `0x140010a2c`
- end: `0x140010a61`
- name: `HviIsHypervisorMicrosoftCompatible`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400109ac`

## callees

- `0x1400109ec`
- `0x140010a2c`

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
0x140010a2c  push    rbx
0x140010a2e  sub     rsp, 30h
0x140010a32  xorps   xmm0, xmm0
0x140010a35  movups  [rsp+38h+var_18], xmm0
0x140010a3a  call    HviIsAnyHypervisorPresent
0x140010a3f  test    al, al
0x140010a41  jz      short loc_140010A4E
0x140010a43  mov     eax, 40000001h
0x140010a48  xor     ecx, ecx
0x140010a4a  cpuid
0x140010a4c  jmp     short loc_140010A52
0x140010a4e  mov     eax, dword ptr [rsp+38h+var_18]
0x140010a52  cmp     eax, 31237648h
0x140010a57  setz    al
0x140010a5a  add     rsp, 30h
0x140010a5e  pop     rbx
0x140010a5f  retn
```
