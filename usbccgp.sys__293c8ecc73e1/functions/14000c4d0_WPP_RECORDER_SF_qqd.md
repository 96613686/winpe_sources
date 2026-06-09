# WPP_RECORDER_SF_qqd

- ea: `0x14000c4d0`
- end: `0x14000c60f`
- name: `WPP_RECORDER_SF_qqd`
- size: `319`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x140001314`
- `0x140001bc8`
- `0x140002630`
- `0x140007844`
- `0x140008b00`
- `0x140009f10`
- `0x14000c3e0`
- `0x14000f220`

## callees

- `0x14000c4d0`
- `0x140014d50`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000c57e`
- `WppRecorder!WppAutoLogTrace` at `0x14000c57e`

## pseudocode

```c
__int64 WPP_RECORDER_SF_qqd(__int64 a1, unsigned __int8 a2, unsigned int a3, unsigned __int16 a4, __int64 a5, ...)
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
      8,
      va2,
      4,
      0);
  LOWORD(v12) = a4;
  return WppAutoLogTrace(a1, v8, a3, a5, v12, (__int64 *)va);
}

```

## disassembly

```asm
0x14000c4d0  push    rbx
0x14000c4d2  push    rbp
0x14000c4d3  push    rsi
0x14000c4d4  push    rdi
0x14000c4d5  push    r14
0x14000c4d7  push    r15
0x14000c4d9  sub     rsp, 68h
0x14000c4dd  mov     r14d, r8d
0x14000c4e0  mov     r15, rcx
0x14000c4e3  mov     edi, r8d
0x14000c4e6  shr     rdi, 10h
0x14000c4ea  movzx   esi, dl
0x14000c4ed  lea     ebx, [r14-1]
0x14000c4f1  movzx   ebp, r9w
0x14000c4f5  mov     r10d, ebx
0x14000c4f8  and     ebx, 1Fh
0x14000c4fb  shr     r10, 5
0x14000c4ff  lea     rax, [rdi+rdi*4]
0x14000c503  and     r10d, 7FFh
0x14000c50a  mov     edx, ebx
0x14000c50c  mov     ebx, 8
0x14000c511  lea     r11, [r10+rax*4]
0x14000c515  mov     r10, cs:WPP_GLOBAL_Control
0x14000c51c  mov     eax, [r10+r11*4+2Ch]
0x14000c521  bt      eax, edx
0x14000c524  jb      short loc_14000C598
0x14000c526  mov     r9, [rsp+98h+arg_20]
0x14000c52e  lea     rax, [rsp+98h+arg_38]
0x14000c536  mov     [rsp+98h+var_40], 0
0x14000c53f  mov     r8d, r14d
0x14000c542  mov     [rsp+98h+var_48], 4
0x14000c54b  mov     edx, esi
0x14000c54d  mov     [rsp+98h+var_50], rax
0x14000c552  mov     rcx, r15
0x14000c555  mov     [rsp+98h+var_58], rbx
0x14000c55a  lea     rax, [rsp+98h+arg_30]
0x14000c562  mov     [rsp+98h+var_60], rax
0x14000c567  lea     rax, [rsp+98h+arg_28]
0x14000c56f  mov     [rsp+98h+var_68], rbx
0x14000c574  mov     [rsp+98h+var_70], rax
0x14000c579  mov     word ptr [rsp+98h+var_78], bp
0x14000c57e  call    cs:__imp_WppAutoLogTrace
0x14000c585  nop     dword ptr [rax+rax+00h]
0x14000c58a  add     rsp, 68h
0x14000c58e  pop     r15
0x14000c590  pop     r14
0x14000c592  pop     rdi
0x14000c593  pop     rsi
0x14000c594  pop     rbp
0x14000c595  pop     rbx
0x14000c596  retn
0x14000c598  lea     rcx, [rdi+rdi*4]
0x14000c59c  add     rcx, rcx
0x14000c59f  cmp     [r10+rcx*8+29h], sil
0x14000c5a4  jb      short loc_14000C526
0x14000c5a6  mov     rax, cs:pfnWppTraceMessage
0x14000c5ad  lea     rdx, [rsp+98h+arg_38]
0x14000c5b5  mov     r8, [rsp+98h+arg_20]
0x14000c5bd  mov     r9d, ebp
0x14000c5c0  mov     rcx, [r10+rcx*8+18h]
0x14000c5c5  mov     [rsp+98h+var_48], 0
0x14000c5ce  mov     [rsp+98h+var_50], 4
0x14000c5d7  mov     [rsp+98h+var_58], rdx
0x14000c5dc  lea     rdx, [rsp+98h+arg_30]
0x14000c5e4  mov     [rsp+98h+var_60], rbx
0x14000c5e9  mov     [rsp+98h+var_68], rdx
0x14000c5ee  lea     rdx, [rsp+98h+arg_28]
0x14000c5f6  mov     [rsp+98h+var_70], rbx
0x14000c5fb  mov     [rsp+98h+var_78], rdx
0x14000c600  mov     edx, 2Bh ; '+'
0x14000c605  call    _guard_dispatch_icall
0x14000c60a  jmp     loc_14000C526
```
