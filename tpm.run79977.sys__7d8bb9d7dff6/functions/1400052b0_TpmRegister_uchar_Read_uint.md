# TpmRegister<uchar>::Read(uint)

- ea: `0x1400052b0`
- end: `0x1400052de`
- name: `?Read@?$TpmRegister@E@@QEAAEI@Z`
- size: `46`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400183d0`
- `0x140018a30`
- `0x140025090`
- `0x140025250`

## callees

- `0x1400052b0`
- `0x14002f700`

## pseudocode

```c
__int64 __fastcall TpmRegister<unsigned char>::Read(unsigned int *a1)
{
  __int64 v1; // rdx

  v1 = *a1;
  if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceObject) )
    return *(unsigned __int8 *)(v1 + *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters);
  else
    return TpmReadPortByte(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters, v1);
}

```

## disassembly

```asm
0x1400052b0  sub     rsp, 28h
0x1400052b4  cmp     dword ptr cs:WPP_MAIN_CB.Queue+30h, 0
0x1400052bb  mov     edx, [rcx]
0x1400052bd  jz      short loc_1400052D0
0x1400052bf  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+28h
0x1400052c6  movzx   eax, byte ptr [rdx+rax]
0x1400052ca  add     rsp, 28h
0x1400052ce  retn
0x1400052d0  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+28h
0x1400052d7  call    TpmReadPortByte
0x1400052dc  jmp     short loc_1400052CA
```
