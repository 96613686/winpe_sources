# SlbNatRemoveExternalInterfaceFromInstances

- ea: `0x140032c90`
- end: `0x140032cff`
- name: `SlbNatRemoveExternalInterfaceFromInstances`
- size: `111`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140033cc8`

## callees

- `0x14002d008`
- `0x140032be4`
- `0x140032c90`

## pseudocode

```c
void __fastcall SlbNatRemoveExternalInterfaceFromInstances(unsigned int a1, __int64 a2, __int64 a3)
{
  PVOID *i; // rbx

  if ( (xmmword_1400262E0 & 2) != 0 )
    WPP_SF_d(1025, 41, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids, a1);
  if ( dword_1400264E8 )
  {
    for ( i = (PVOID *)qword_140026338; i != &qword_140026338; i = (PVOID *)*i )
      SlbNatRemoveExternalInterfaceFromInstance((__int64)i, a1, a3);
  }
}

```

## disassembly

```asm
0x140032c90  mov     [rsp+arg_0], rbx
0x140032c95  mov     [rsp+arg_8], rsi
0x140032c9a  push    rdi
0x140032c9b  sub     rsp, 20h
0x140032c9f  mov     edi, ecx
0x140032ca1  test    byte ptr cs:xmmword_1400262E0, 2
0x140032ca8  jz      short loc_140032CC3
0x140032caa  mov     edx, 29h ; ')'
0x140032caf  lea     r8, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids
0x140032cb6  mov     ecx, 401h
0x140032cbb  mov     r9d, edi
0x140032cbe  call    WPP_SF_d
0x140032cc3  cmp     cs:dword_1400264E8, 0
0x140032cca  jz      short loc_140032CEE
0x140032ccc  mov     rbx, cs:qword_140026338
0x140032cd3  lea     rsi, qword_140026338
0x140032cda  jmp     short loc_140032CE9
0x140032cdc  mov     edx, edi
0x140032cde  mov     rcx, rbx
0x140032ce1  call    SlbNatRemoveExternalInterfaceFromInstance
0x140032ce6  mov     rbx, [rbx]
0x140032ce9  cmp     rbx, rsi
0x140032cec  jnz     short loc_140032CDC
0x140032cee  mov     rbx, [rsp+28h+arg_0]
0x140032cf3  mov     rsi, [rsp+28h+arg_8]
0x140032cf8  add     rsp, 20h
0x140032cfc  pop     rdi
0x140032cfd  retn
```
