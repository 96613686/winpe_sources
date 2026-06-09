# WPP_RECORDER_SF_q

- ea: `0x1400013d0`
- end: `0x1400014b5`
- name: `WPP_RECORDER_SF_q`
- size: `229`
- prototype: ``
- caller_count: `18`
- callee_count: `2`
- tags: ``

## callers

- `0x140004740`
- `0x14000c17c`
- `0x14000cfd0`
- `0x14000dccc`
- `0x14000e080`
- `0x14000ea0c`
- `0x14000fbe8`
- `0x14000fe14`
- `0x1400194d0`
- `0x14001ab90`
- `0x14001af80`
- `0x14001b1e0`
- `0x14001b370`
- `0x14001c734`
- `0x14001cb74`
- `0x14001cf28`
- `0x14001d590`
- `0x14001e03c`

## callees

- `0x1400013d0`
- `0x140010700`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000149d`
- `WppRecorder!WppAutoLogTrace` at `0x14000149d`

## pseudocode

```c
__int64 WPP_RECORDER_SF_q(__int64 a1, unsigned __int8 a2, unsigned int a3, unsigned __int16 a4, __int64 a5, ...)
{
  unsigned __int64 v7; // rbx
  unsigned int v9; // edi
  int v10; // eax
  int v12; // [rsp+20h] [rbp-48h]
  va_list va; // [rsp+98h] [rbp+30h] BYREF

  va_start(va, a5);
  v7 = (unsigned __int64)a3 >> 16;
  v9 = a2;
  v10 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v7 + (((a3 - 1) >> 5) & 0x7FF) + 1);
  if ( _bittest(&v10, a3 - 1) && *((_BYTE *)&WPP_GLOBAL_Control->Timer + 80 * v7 + 1) >= a2 )
    ((void (__fastcall *)(_QWORD, __int64, __int64, _QWORD, char *, __int64, _QWORD))pfnWppTraceMessage)(
      *((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v7),
      43,
      a5,
      a4,
      va,
      8,
      0);
  LOWORD(v12) = a4;
  return WppAutoLogTrace(a1, v9, a3, a5, v12, va);
}

```

## disassembly

```asm
0x1400013d0  push    rbx
0x1400013d2  push    rbp
0x1400013d3  push    rsi
0x1400013d4  push    rdi
0x1400013d5  push    r14
0x1400013d7  sub     rsp, 40h
0x1400013db  mov     ebp, r8d
0x1400013de  mov     r14, rcx
0x1400013e1  mov     ebx, r8d
0x1400013e4  shr     rbx, 10h
0x1400013e8  movzx   esi, r9w
0x1400013ec  lea     r11d, [rbp-1]
0x1400013f0  movzx   edi, dl
0x1400013f3  mov     r10d, r11d
0x1400013f6  shr     r10, 5
0x1400013fa  lea     rax, [rbx+rbx*4]
0x1400013fe  and     r10d, 7FFh
0x140001405  lea     rax, [r10+rax*4]
0x140001409  mov     r10, cs:WPP_GLOBAL_Control
0x140001410  mov     eax, [r10+rax*4+2Ch]
0x140001415  bt      eax, r11d
0x140001419  jnb     short loc_140001469
0x14000141b  lea     rcx, [rbx+rbx*4]
0x14000141f  add     rcx, rcx
0x140001422  cmp     [r10+rcx*8+29h], dil
0x140001427  jb      short loc_140001469
0x140001429  mov     rax, cs:pfnWppTraceMessage
0x140001430  lea     rdx, [rsp+68h+arg_28]
0x140001438  mov     r8, [rsp+68h+arg_20]
0x140001440  mov     r9d, esi
0x140001443  mov     rcx, [r10+rcx*8+18h]
0x140001448  mov     [rsp+68h+var_38], 0
0x140001451  mov     [rsp+68h+var_40], 8
0x14000145a  mov     [rsp+68h+var_48], rdx
0x14000145f  mov     edx, 2Bh ; '+'
0x140001464  call    _guard_dispatch_icall
0x140001469  mov     r9, [rsp+68h+arg_20]
0x140001471  lea     rax, [rsp+68h+arg_28]
0x140001479  mov     [rsp+68h+var_30], 0
0x140001482  mov     r8d, ebp
0x140001485  mov     [rsp+68h+var_38], 8
0x14000148e  mov     edx, edi
0x140001490  mov     [rsp+68h+var_40], rax
0x140001495  mov     rcx, r14
0x140001498  mov     word ptr [rsp+68h+var_48], si
0x14000149d  call    cs:__imp_WppAutoLogTrace
0x1400014a4  nop     dword ptr [rax+rax+00h]
0x1400014a9  add     rsp, 40h
0x1400014ad  pop     r14
0x1400014af  pop     rdi
0x1400014b0  pop     rsi
0x1400014b1  pop     rbp
0x1400014b2  pop     rbx
0x1400014b3  retn
```
