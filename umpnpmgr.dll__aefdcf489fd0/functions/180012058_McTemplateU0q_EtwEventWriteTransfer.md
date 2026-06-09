# McTemplateU0q_EtwEventWriteTransfer

- ea: `0x180012058`
- end: `0x1800120a7`
- name: `McTemplateU0q_EtwEventWriteTransfer`
- size: `79`
- prototype: `__int64 __fastcall(int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180009d70`
- `0x18000aba0`

## callees

- `0x18000f970`
- `0x180018970`

## pseudocode

```c
__int64 __fastcall McTemplateU0q_EtwEventWriteTransfer(int a1, int a2, int a3)
{
  _QWORD v4[4]; // [rsp+30h] [rbp-38h] BYREF
  int v5; // [rsp+80h] [rbp+18h] BYREF

  v5 = a3;
  v4[3] = 4;
  v4[2] = &v5;
  return McGenEventWrite_EtwEventWriteTransfer(a1, a2, a3, 2, (__int64)v4);
}

```

## disassembly

```asm
0x180012058  mov     r11, rsp
0x18001205b  mov     [r11+18h], r8d
0x18001205f  sub     rsp, 68h
0x180012063  mov     rax, cs:__security_cookie
0x18001206a  xor     rax, rsp
0x18001206d  mov     [rsp+68h+var_18], rax
0x180012072  lea     rax, [r11+18h]
0x180012076  mov     qword ptr [r11-20h], 4
0x18001207e  mov     [r11-28h], rax
0x180012082  mov     r9d, 2
0x180012088  lea     rax, [r11-38h]
0x18001208c  mov     [r11-48h], rax
0x180012090  call    McGenEventWrite_EtwEventWriteTransfer
0x180012095  mov     rcx, [rsp+68h+var_18]
0x18001209a  xor     rcx, rsp; StackCookie
0x18001209d  call    __security_check_cookie
0x1800120a2  add     rsp, 68h
0x1800120a6  retn
```
