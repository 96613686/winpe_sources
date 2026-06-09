# VmbusPipeClientOpenChannel

- ea: `0x180007160`
- end: `0x18000718b`
- name: `VmbusPipeClientOpenChannel`
- size: `43`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800071a0`

## pseudocode

```c
__int64 __fastcall VmbusPipeClientOpenChannel(__int64 a1, __int64 a2)
{
  _DWORD v3[2]; // [rsp+20h] [rbp-18h] BYREF
  __int64 v4; // [rsp+28h] [rbp-10h]

  v4 = 0;
  v3[0] = 1;
  v3[1] = 16;
  return VmbusPipeClientOpenChannelEx(a1, a2, v3);
}

```

## disassembly

```asm
0x180007160  mov     rax, rsp
0x180007163  sub     rsp, 38h
0x180007167  lea     r8, [rax-18h]
0x18000716b  mov     qword ptr [rax-10h], 0
0x180007173  mov     dword ptr [rax-18h], 1
0x18000717a  mov     dword ptr [rax-14h], 10h
0x180007181  call    VmbusPipeClientOpenChannelEx
0x180007186  add     rsp, 38h
0x18000718a  retn
```
