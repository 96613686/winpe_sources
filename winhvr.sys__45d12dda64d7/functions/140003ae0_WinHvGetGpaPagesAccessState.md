# WinHvGetGpaPagesAccessState

- ea: `0x140003ae0`
- end: `0x140003b5d`
- name: `WinHvGetGpaPagesAccessState`
- size: `125`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140003b70`

## pseudocode

```c
__int64 __fastcall WinHvGetGpaPagesAccessState(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int64 a4,
        char *a5,
        _QWORD *a6)
{
  _QWORD v7[2]; // [rsp+80h] [rbp-28h] BYREF
  _QWORD v8[3]; // [rsp+90h] [rbp-18h] BYREF

  v7[1] = a2;
  v7[0] = a1;
  v8[0] = a3;
  return WinHvpSpecialListRepHypercall(201, a4, v7, 0x18u, v8, 1, 0, 0, 0, 0, a5, 1u, 0, 0, a6);
}

```

## disassembly

```asm
0x140003ae0  mov     r11, rsp
0x140003ae3  sub     rsp, 0A8h
0x140003aea  mov     rax, [rsp+0A8h+arg_28]
0x140003af2  mov     r10, r9
0x140003af5  mov     [r11-38h], rax
0x140003af9  mov     rax, [rsp+0A8h+arg_20]
0x140003b01  mov     [r11-20h], rdx
0x140003b05  xor     edx, edx
0x140003b07  mov     [r11-40h], rdx
0x140003b0b  mov     [r11-48h], rdx
0x140003b0f  mov     [r11-28h], rcx
0x140003b13  lea     ecx, [rdx+1]
0x140003b16  mov     [r11-18h], r8
0x140003b1a  mov     [rsp+0A8h+var_50], ecx
0x140003b1e  lea     r9d, [rdx+18h]
0x140003b22  mov     [r11-58h], rax
0x140003b26  lea     r8, [r11-28h]
0x140003b2a  mov     [r11-60h], rdx
0x140003b2e  lea     rax, [r11-18h]
0x140003b32  mov     [r11-68h], rdx
0x140003b36  mov     [rsp+0A8h+var_70], edx
0x140003b3a  mov     [r11-78h], rdx
0x140003b3e  mov     rdx, r10
0x140003b41  mov     [r11-80h], rcx
0x140003b45  mov     ecx, 0C9h
0x140003b4a  mov     [rsp+0A8h+var_88], rax
0x140003b4f  call    WinHvpSpecialListRepHypercall
0x140003b54  add     rsp, 0A8h
0x140003b5b  retn
```
