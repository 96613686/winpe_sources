# WinNatGetBitMapForProtocol

- ea: `0x14000c948`
- end: `0x14000c987`
- name: `WinNatGetBitMapForProtocol`
- size: `63`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140008a7c`
- `0x14001a23c`
- `0x14001a878`

## callees

- `0x14000c948`
- `0x14000caa0`

## pseudocode

```c
__int64 __fastcall WinNatGetBitMapForProtocol(__int64 a1, __int64 a2)
{
  if ( (unsigned __int8)a2 != 1 )
  {
    if ( (unsigned __int8)a2 == 6 )
      return a1 + 40;
    if ( (unsigned __int8)a2 == 17 )
      return a1 + 64;
    if ( (unsigned __int8)a2 != 58 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, (unsigned int)(unsigned __int8)a2 - 17);
      return 0;
    }
  }
  return a1 + 88;
}

```

## disassembly

```asm
0x14000c948  sub     rsp, 28h
0x14000c94c  movzx   r8d, dl
0x14000c950  sub     r8d, 1
0x14000c954  jz      short loc_14000C97D
0x14000c956  sub     r8d, 5
0x14000c95a  jz      short loc_14000C977
0x14000c95c  sub     r8d, 0Bh
0x14000c960  jz      short loc_14000C971
0x14000c962  cmp     r8d, 29h ; ')'
0x14000c966  jz      short loc_14000C97D
0x14000c968  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14000c96d  xor     eax, eax
0x14000c96f  jmp     short loc_14000C981
0x14000c971  lea     rax, [rcx+40h]
0x14000c975  jmp     short loc_14000C981
0x14000c977  lea     rax, [rcx+28h]
0x14000c97b  jmp     short loc_14000C981
0x14000c97d  lea     rax, [rcx+58h]
0x14000c981  add     rsp, 28h
0x14000c985  retn
```
