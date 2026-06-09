# WPP_RECORDER_SF_qLL

- ea: `0x140007020`
- end: `0x14000715f`
- name: `WPP_RECORDER_SF_qLL`
- size: `319`
- prototype: ``
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x140004f50`
- `0x140006834`
- `0x140006af8`
- `0x140007170`
- `0x14000773c`
- `0x1400084c0`
- `0x140008fd0`
- `0x140009d20`
- `0x140029e6c`
- `0x140029f14`
- `0x14002d86c`
- `0x14002df80`

## callees

- `0x140007020`
- `0x140014d50`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x1400070ce`
- `WppRecorder!WppAutoLogTrace` at `0x1400070ce`

## pseudocode

```c
__int64 WPP_RECORDER_SF_qLL(__int64 a1, unsigned __int8 a2, unsigned int a3, unsigned __int16 a4, __int64 a5, ...)
{
  unsigned __int64 v7; // rdi
  unsigned int v8; // esi
  int v10; // eax
  int v12; // [rsp+20h] [rbp-78h]
  __int64 v13; // [rsp+C8h] [rbp+30h] BYREF
  va_list va; // [rsp+C8h] [rbp+30h]
  __int64 v15; // [rsp+D0h] [rbp+38h] BYREF
  va_list va1; // [rsp+D0h] [rbp+38h]
  va_list va2; // [rsp+D8h] [rbp+40h] BYREF

  va_start(va2, a5);
  va_start(va1, a5);
  va_start(va, a5);
  v13 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v15 = va_arg(va2, _QWORD);
  v7 = (unsigned __int64)a3 >> 16;
  v8 = a2;
  v10 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v7 + (((a3 - 1) >> 5) & 0x7FF) + 1);
  if ( _bittest(&v10, ((_BYTE)a3 - 1) & 0x1F) && *((_BYTE *)&WPP_GLOBAL_Control->Timer + 80 * v7 + 1) >= a2 )
    ((void (__fastcall *)(_QWORD, __int64, __int64, _QWORD, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      *((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v7),
      43,
      a5,
      a4,
      (__int64 *)va,
      8,
      (__int64 *)va1,
      4,
      va2,
      4,
      0);
  LOWORD(v12) = a4;
  return WppAutoLogTrace(a1, v8, a3, a5, v12, (__int64 *)va);
}

```

## disassembly

```asm
0x140007020  push    rbx
0x140007022  push    rbp
0x140007023  push    rsi
0x140007024  push    rdi
0x140007025  push    r14
0x140007027  push    r15
0x140007029  sub     rsp, 68h
0x14000702d  mov     r14d, r8d
0x140007030  mov     r15, rcx
0x140007033  mov     edi, r8d
0x140007036  shr     rdi, 10h
0x14000703a  movzx   esi, dl
0x14000703d  lea     ebx, [r14-1]
0x140007041  movzx   ebp, r9w
0x140007045  mov     r10d, ebx
0x140007048  and     ebx, 1Fh
0x14000704b  shr     r10, 5
0x14000704f  lea     rax, [rdi+rdi*4]
0x140007053  and     r10d, 7FFh
0x14000705a  mov     edx, ebx
0x14000705c  mov     ebx, 4
0x140007061  lea     r11, [r10+rax*4]
0x140007065  mov     r10, cs:WPP_GLOBAL_Control
0x14000706c  mov     eax, [r10+r11*4+2Ch]
0x140007071  bt      eax, edx
0x140007074  jb      short loc_1400070E8
0x140007076  mov     r9, [rsp+98h+arg_20]
0x14000707e  lea     rax, [rsp+98h+arg_38]
0x140007086  mov     [rsp+98h+var_40], 0
0x14000708f  mov     r8d, r14d
0x140007092  mov     [rsp+98h+var_48], rbx
0x140007097  mov     edx, esi
0x140007099  mov     [rsp+98h+var_50], rax
0x14000709e  mov     rcx, r15
0x1400070a1  mov     [rsp+98h+var_58], rbx
0x1400070a6  lea     rax, [rsp+98h+arg_30]
0x1400070ae  mov     [rsp+98h+var_60], rax
0x1400070b3  lea     rax, [rsp+98h+arg_28]
0x1400070bb  mov     [rsp+98h+var_68], 8
0x1400070c4  mov     [rsp+98h+var_70], rax
0x1400070c9  mov     word ptr [rsp+98h+var_78], bp
0x1400070ce  call    cs:__imp_WppAutoLogTrace
0x1400070d5  nop     dword ptr [rax+rax+00h]
0x1400070da  add     rsp, 68h
0x1400070de  pop     r15
0x1400070e0  pop     r14
0x1400070e2  pop     rdi
0x1400070e3  pop     rsi
0x1400070e4  pop     rbp
0x1400070e5  pop     rbx
0x1400070e6  retn
0x1400070e8  lea     rcx, [rdi+rdi*4]
0x1400070ec  add     rcx, rcx
0x1400070ef  cmp     [r10+rcx*8+29h], sil
0x1400070f4  jb      short loc_140007076
0x1400070f6  mov     rax, cs:pfnWppTraceMessage
0x1400070fd  lea     rdx, [rsp+98h+arg_38]
0x140007105  mov     r8, [rsp+98h+arg_20]
0x14000710d  mov     r9d, ebp
0x140007110  mov     rcx, [r10+rcx*8+18h]
0x140007115  mov     [rsp+98h+var_48], 0
0x14000711e  mov     [rsp+98h+var_50], rbx
0x140007123  mov     [rsp+98h+var_58], rdx
0x140007128  lea     rdx, [rsp+98h+arg_30]
0x140007130  mov     [rsp+98h+var_60], rbx
0x140007135  mov     [rsp+98h+var_68], rdx
0x14000713a  lea     rdx, [rsp+98h+arg_28]
0x140007142  mov     [rsp+98h+var_70], 8
0x14000714b  mov     [rsp+98h+var_78], rdx
0x140007150  mov     edx, 2Bh ; '+'
0x140007155  call    _guard_dispatch_icall
0x14000715a  jmp     loc_140007076
```
