# WPP_RECORDER_SF_dd

- ea: `0x14000c2bc`
- end: `0x14000c3cc`
- name: `WPP_RECORDER_SF_dd`
- size: `272`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x140001314`
- `0x14000fb68`
- `0x140023938`
- `0x140026f10`
- `0x140028008`
- `0x140028f7c`
- `0x14002c8e4`

## callees

- `0x14000c2bc`
- `0x140014d50`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000c351`
- `WppRecorder!WppAutoLogTrace` at `0x14000c351`

## pseudocode

```c
__int64 WPP_RECORDER_SF_dd(__int64 a1, unsigned __int8 a2, unsigned int a3, unsigned __int16 a4, __int64 a5, ...)
{
  unsigned __int64 v7; // rbx
  unsigned int v9; // edi
  int v10; // eax
  int v12; // [rsp+20h] [rbp-68h]
  __int64 v13; // [rsp+B8h] [rbp+30h] BYREF
  va_list va; // [rsp+B8h] [rbp+30h]
  va_list va1; // [rsp+C0h] [rbp+38h] BYREF

  va_start(va1, a5);
  va_start(va, a5);
  v13 = va_arg(va1, _QWORD);
  v7 = (unsigned __int64)a3 >> 16;
  v9 = a2;
  v10 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v7 + (((a3 - 1) >> 5) & 0x7FF) + 1);
  if ( _bittest(&v10, a3 - 1) && *((_BYTE *)&WPP_GLOBAL_Control->Timer + 80 * v7 + 1) >= a2 )
    ((void (__fastcall *)(_QWORD, __int64, __int64, _QWORD, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      *((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v7),
      43,
      a5,
      a4,
      (__int64 *)va,
      4,
      va1,
      4,
      0);
  LOWORD(v12) = a4;
  return WppAutoLogTrace(a1, v9, a3, a5, v12, (__int64 *)va);
}

```

## disassembly

```asm
0x14000c2bc  push    rbx
0x14000c2be  push    rbp
0x14000c2bf  push    rsi
0x14000c2c0  push    rdi
0x14000c2c1  push    r14
0x14000c2c3  push    r15
0x14000c2c5  sub     rsp, 58h
0x14000c2c9  mov     ebp, r8d
0x14000c2cc  mov     r14, rcx
0x14000c2cf  mov     ebx, r8d
0x14000c2d2  mov     r15d, 4
0x14000c2d8  shr     rbx, 10h
0x14000c2dc  movzx   esi, r9w
0x14000c2e0  lea     r11d, [rbp-1]
0x14000c2e4  movzx   edi, dl
0x14000c2e7  mov     r10d, r11d
0x14000c2ea  shr     r10, 5
0x14000c2ee  lea     rax, [rbx+rbx*4]
0x14000c2f2  and     r10d, 7FFh
0x14000c2f9  lea     rax, [r10+rax*4]
0x14000c2fd  mov     r10, cs:WPP_GLOBAL_Control
0x14000c304  mov     eax, [r10+rax*4+2Ch]
0x14000c309  bt      eax, r11d
0x14000c30d  jb      short loc_14000C36B
0x14000c30f  mov     r9, [rsp+88h+arg_20]
0x14000c317  lea     rax, [rsp+88h+arg_30]
0x14000c31f  mov     [rsp+88h+var_40], 0
0x14000c328  mov     r8d, ebp
0x14000c32b  mov     [rsp+88h+var_48], r15
0x14000c330  mov     edx, edi
0x14000c332  mov     [rsp+88h+var_50], rax
0x14000c337  mov     rcx, r14
0x14000c33a  lea     rax, [rsp+88h+arg_28]
0x14000c342  mov     [rsp+88h+var_58], r15
0x14000c347  mov     [rsp+88h+var_60], rax
0x14000c34c  mov     word ptr [rsp+88h+var_68], si
0x14000c351  call    cs:__imp_WppAutoLogTrace
0x14000c358  nop     dword ptr [rax+rax+00h]
0x14000c35d  add     rsp, 58h
0x14000c361  pop     r15
0x14000c363  pop     r14
0x14000c365  pop     rdi
0x14000c366  pop     rsi
0x14000c367  pop     rbp
0x14000c368  pop     rbx
0x14000c369  retn
0x14000c36b  lea     rcx, [rbx+rbx*4]
0x14000c36f  add     rcx, rcx
0x14000c372  cmp     [r10+rcx*8+29h], dil
0x14000c377  jb      short loc_14000C30F
0x14000c379  mov     rax, cs:pfnWppTraceMessage
0x14000c380  lea     rdx, [rsp+88h+arg_30]
0x14000c388  mov     r8, [rsp+88h+arg_20]
0x14000c390  mov     r9d, esi
0x14000c393  mov     rcx, [r10+rcx*8+18h]
0x14000c398  mov     [rsp+88h+var_48], 0
0x14000c3a1  mov     [rsp+88h+var_50], r15
0x14000c3a6  mov     [rsp+88h+var_58], rdx
0x14000c3ab  lea     rdx, [rsp+88h+arg_28]
0x14000c3b3  mov     [rsp+88h+var_60], r15
0x14000c3b8  mov     [rsp+88h+var_68], rdx
0x14000c3bd  mov     edx, 2Bh ; '+'
0x14000c3c2  call    _guard_dispatch_icall
0x14000c3c7  jmp     loc_14000C30F
```
