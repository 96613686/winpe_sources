# SlbNatRemoveExternalInterfaceFromInstances

- ea: `0x140033dc0`
- end: `0x140033e2f`
- name: `SlbNatRemoveExternalInterfaceFromInstances`
- size: `111`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140034fd8`

## callees

- `0x14002e008`
- `0x140033d14`
- `0x140033dc0`

## pseudocode

```c
void __fastcall SlbNatRemoveExternalInterfaceFromInstances(unsigned int a1, __int64 a2, __int64 a3)
{
  PVOID *i; // rbx

  if ( (xmmword_1400272E0 & 2) != 0 )
    WPP_SF_d(1025, 41, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids, a1);
  if ( dword_1400274E8 )
  {
    for ( i = (PVOID *)qword_140027338; i != &qword_140027338; i = (PVOID *)*i )
      SlbNatRemoveExternalInterfaceFromInstance((__int64)i, a1, a3);
  }
}

```

## disassembly

```asm
0x140033dc0  mov     [rsp+arg_0], rbx
0x140033dc5  mov     [rsp+arg_8], rsi
0x140033dca  push    rdi
0x140033dcb  sub     rsp, 20h
0x140033dcf  mov     edi, ecx
0x140033dd1  test    byte ptr cs:xmmword_1400272E0, 2
0x140033dd8  jz      short loc_140033DF3
0x140033dda  mov     edx, 29h ; ')'
0x140033ddf  lea     r8, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids
0x140033de6  mov     ecx, 401h
0x140033deb  mov     r9d, edi
0x140033dee  call    WPP_SF_d
0x140033df3  cmp     cs:dword_1400274E8, 0
0x140033dfa  jz      short loc_140033E1E
0x140033dfc  mov     rbx, cs:qword_140027338
0x140033e03  lea     rsi, qword_140027338
0x140033e0a  jmp     short loc_140033E19
0x140033e0c  mov     edx, edi
0x140033e0e  mov     rcx, rbx
0x140033e11  call    SlbNatRemoveExternalInterfaceFromInstance
0x140033e16  mov     rbx, [rbx]
0x140033e19  cmp     rbx, rsi
0x140033e1c  jnz     short loc_140033E0C
0x140033e1e  mov     rbx, [rsp+28h+arg_0]
0x140033e23  mov     rsi, [rsp+28h+arg_8]
0x140033e28  add     rsp, 20h
0x140033e2c  pop     rdi
0x140033e2d  retn
```
