# WPP_RECORDER_SF_qDD

- ea: `0x140009450`
- end: `0x140009588`
- name: `WPP_RECORDER_SF_qDD`
- size: `312`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140001bc8`
- `0x140002200`
- `0x140008d58`
- `0x14002c430`

## callees

- `0x140009450`
- `0x140014d50`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000956e`
- `WppRecorder!WppAutoLogTrace` at `0x14000956e`

## pseudocode

```c
__int64 WPP_RECORDER_SF_qDD(__int64 a1, unsigned __int8 a2, unsigned int a3, unsigned __int16 a4, __int64 a5, ...)
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
    pfnWppTraceMessage(
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
0x140009450  push    rbx
0x140009452  push    rbp
0x140009453  push    rsi
0x140009454  push    rdi
0x140009455  push    r14
0x140009457  push    r15
0x140009459  sub     rsp, 68h
0x14000945d  mov     r14d, r8d
0x140009460  mov     r15, rcx
0x140009463  mov     edi, r8d
0x140009466  shr     rdi, 10h
0x14000946a  movzx   esi, dl
0x14000946d  lea     ebx, [r14-1]
0x140009471  movzx   ebp, r9w
0x140009475  mov     r10d, ebx
0x140009478  and     ebx, 1Fh
0x14000947b  shr     r10, 5
0x14000947f  lea     rax, [rdi+rdi*4]
0x140009483  and     r10d, 7FFh
0x14000948a  mov     edx, ebx
0x14000948c  mov     ebx, 4
0x140009491  lea     r11, [r10+rax*4]
0x140009495  mov     r10, cs:WPP_GLOBAL_Control
0x14000949c  mov     eax, [r10+r11*4+2Ch]
0x1400094a1  bt      eax, edx
0x1400094a4  jnb     short loc_140009516
0x1400094a6  lea     rcx, [rdi+rdi*4]
0x1400094aa  add     rcx, rcx
0x1400094ad  cmp     [r10+rcx*8+29h], sil
0x1400094b2  jb      short loc_140009516
0x1400094b4  mov     rax, cs:pfnWppTraceMessage
0x1400094bb  lea     rdx, [rsp+98h+arg_38]
0x1400094c3  mov     r8, [rsp+98h+arg_20]
0x1400094cb  mov     r9d, ebp
0x1400094ce  mov     rcx, [r10+rcx*8+18h]
0x1400094d3  mov     [rsp+98h+var_48], 0
0x1400094dc  mov     [rsp+98h+var_50], rbx
0x1400094e1  mov     [rsp+98h+var_58], rdx
0x1400094e6  lea     rdx, [rsp+98h+arg_30]
0x1400094ee  mov     [rsp+98h+var_60], rbx
0x1400094f3  mov     [rsp+98h+var_68], rdx
0x1400094f8  lea     rdx, [rsp+98h+arg_28]
0x140009500  mov     [rsp+98h+var_70], 8
0x140009509  mov     [rsp+98h+var_78], rdx
0x14000950e  lea     edx, [rbx+27h]
0x140009511  call    _guard_dispatch_icall
0x140009516  mov     r9, [rsp+98h+arg_20]
0x14000951e  lea     rax, [rsp+98h+arg_38]
0x140009526  mov     [rsp+98h+var_40], 0
0x14000952f  mov     r8d, r14d
0x140009532  mov     [rsp+98h+var_48], rbx
0x140009537  mov     edx, esi
0x140009539  mov     [rsp+98h+var_50], rax
0x14000953e  mov     rcx, r15
0x140009541  mov     [rsp+98h+var_58], rbx
0x140009546  lea     rax, [rsp+98h+arg_30]
0x14000954e  mov     [rsp+98h+var_60], rax
0x140009553  lea     rax, [rsp+98h+arg_28]
0x14000955b  mov     [rsp+98h+var_68], 8
0x140009564  mov     [rsp+98h+var_70], rax
0x140009569  mov     word ptr [rsp+98h+var_78], bp
0x14000956e  call    cs:__imp_WppAutoLogTrace
0x140009575  nop     dword ptr [rax+rax+00h]
0x14000957a  add     rsp, 68h
0x14000957e  pop     r15
0x140009580  pop     r14
0x140009582  pop     rdi
0x140009583  pop     rsi
0x140009584  pop     rbp
0x140009585  pop     rbx
0x140009586  retn
```
