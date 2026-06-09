# McTemplateU0d_EtwEventWriteTransfer

- ea: `0x180013f4c`
- end: `0x180013fa2`
- name: `McTemplateU0d_EtwEventWriteTransfer`
- size: `86`
- prototype: `__int64 __fastcall(int, __int64, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000cf30`

## callees

- `0x18000f970`
- `0x180018970`

## pseudocode

```c
__int64 __fastcall McTemplateU0d_EtwEventWriteTransfer(int a1, __int64 a2, int a3)
{
  _QWORD v4[4]; // [rsp+30h] [rbp-38h] BYREF
  int v5; // [rsp+80h] [rbp+18h] BYREF

  v5 = a3;
  v4[3] = 4;
  v4[2] = &v5;
  return McGenEventWrite_EtwEventWriteTransfer(a1, (unsigned int)DEVICEINSTALL_START_FAILED, a3, 2, (__int64)v4);
}

```

## disassembly

```asm
0x180013f4c  mov     r11, rsp
0x180013f4f  mov     [r11+18h], r8d
0x180013f53  sub     rsp, 68h
0x180013f57  mov     rax, cs:__security_cookie
0x180013f5e  xor     rax, rsp
0x180013f61  mov     [rsp+68h+var_18], rax
0x180013f66  lea     rax, [r11+18h]
0x180013f6a  mov     qword ptr [r11-20h], 4
0x180013f72  mov     [r11-28h], rax
0x180013f76  lea     rdx, DEVICEINSTALL_START_FAILED
0x180013f7d  lea     rax, [r11-38h]
0x180013f81  mov     r9d, 2
0x180013f87  mov     [r11-48h], rax
0x180013f8b  call    McGenEventWrite_EtwEventWriteTransfer
0x180013f90  mov     rcx, [rsp+68h+var_18]
0x180013f95  xor     rcx, rsp; StackCookie
0x180013f98  call    __security_check_cookie
0x180013f9d  add     rsp, 68h
0x180013fa1  retn
```
