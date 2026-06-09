# WinHvDeleteEventLogBuffer

- ea: `0x1400093f0`
- end: `0x140009419`
- name: `WinHvDeleteEventLogBuffer`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140002ce8`

## pseudocode

```c
__int64 __fastcall WinHvDeleteEventLogBuffer(int a1, int a2)
{
  _DWORD v3[2]; // [rsp+20h] [rbp-18h] BYREF
  __int64 v4; // [rsp+28h] [rbp-10h]

  v3[0] = a1;
  v3[1] = a2;
  v4 = 0;
  return WinHvpFastHypercall(99, v3);
}

```

## disassembly

```asm
0x1400093f0  mov     rax, rsp
0x1400093f3  sub     rsp, 38h
0x1400093f7  mov     [rax-18h], ecx
0x1400093fa  mov     ecx, 63h ; 'c'
0x1400093ff  mov     [rax-14h], edx
0x140009402  lea     rdx, [rax-18h]
0x140009406  mov     qword ptr [rax-10h], 0
0x14000940e  call    WinHvpFastHypercall
0x140009413  add     rsp, 38h
0x140009417  retn
```
