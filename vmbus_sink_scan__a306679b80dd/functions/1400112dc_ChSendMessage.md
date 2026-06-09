# ChSendMessage

- ea: `0x1400112dc`
- end: `0x1400112ef`
- name: `ChSendMessage`
- size: `19`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x14000f9cc`
- `0x14000fc04`
- `0x14000ff34`
- `0x1400103d0`
- `0x1400104c8`
- `0x140010834`
- `0x140011c40`
- `0x14002dbf0`
- `0x14002de40`

## callees

- `0x14001360c`

## pseudocode

```c
__int64 __fastcall ChSendMessage(__int64 a1, __int64 a2)
{
  return XPartSendMessage(a1, a2 - 56);
}

```

## disassembly

```asm
0x1400112dc  sub     rsp, 28h
0x1400112e0  add     rdx, 0FFFFFFFFFFFFFFC8h
0x1400112e4  call    XPartSendMessage
0x1400112e9  add     rsp, 28h
0x1400112ed  retn
```
