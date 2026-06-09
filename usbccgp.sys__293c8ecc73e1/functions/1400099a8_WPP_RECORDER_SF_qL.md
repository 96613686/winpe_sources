# WPP_RECORDER_SF_qL

- ea: `0x1400099a8`
- end: `0x140009ac3`
- name: `WPP_RECORDER_SF_qL`
- size: `283`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x1400018b0`
- `0x140001acc`
- `0x140004f50`
- `0x140005fc4`
- `0x140007170`
- `0x1400084c0`
- `0x140008fd0`
- `0x140011ee0`
- `0x140029f14`

## callees

- `0x1400099a8`
- `0x140014d50`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140009a44`
- `WppRecorder!WppAutoLogTrace` at `0x140009a44`

## pseudocode

```c
__int64 WPP_RECORDER_SF_qL(__int64 a1, unsigned __int8 a2, unsigned int a3, unsigned __int16 a4, __int64 a5, ...)
{
  unsigned __int64 v7; // rdi
  unsigned int v8; // esi
  int v10; // eax
  int v12; // [rsp+20h] [rbp-68h]
  __int64 v13; // [rsp+B8h] [rbp+30h] BYREF
  va_list va; // [rsp+B8h] [rbp+30h]
  va_list va1; // [rsp+C0h] [rbp+38h] BYREF

  va_start(va1, a5);
  va_start(va, a5);
  v13 = va_arg(va1, _QWORD);
  v7 = (unsigned __int64)a3 >> 16;
  v8 = a2;
  v10 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v7 + (((a3 - 1) >> 5) & 0x7FF) + 1);
  if ( _bittest(&v10, ((_BYTE)a3 - 1) & 0x1F) && *((_BYTE *)&WPP_GLOBAL_Control->Timer + 80 * v7 + 1) >= a2 )
    ((void (__fastcall *)(_QWORD, __int64, __int64, _QWORD, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      *((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v7),
      43,
      a5,
      a4,
      (__int64 *)va,
      8,
      va1,
      4,
      0);
  LOWORD(v12) = a4;
  return WppAutoLogTrace(a1, v8, a3, a5, v12, (__int64 *)va);
}

```

## disassembly

```asm
0x1400099a8  push    rbx
0x1400099aa  push    rbp
0x1400099ab  push    rsi
0x1400099ac  push    rdi
0x1400099ad  push    r14
0x1400099af  push    r15
0x1400099b1  sub     rsp, 58h
0x1400099b5  mov     r14d, r8d
0x1400099b8  mov     r15, rcx
0x1400099bb  mov     edi, r8d
0x1400099be  shr     rdi, 10h
0x1400099c2  movzx   esi, dl
0x1400099c5  lea     ebx, [r14-1]
0x1400099c9  movzx   ebp, r9w
0x1400099cd  mov     r10d, ebx
0x1400099d0  and     ebx, 1Fh
0x1400099d3  shr     r10, 5
0x1400099d7  lea     rax, [rdi+rdi*4]
0x1400099db  and     r10d, 7FFh
0x1400099e2  mov     edx, ebx
0x1400099e4  mov     ebx, 4
0x1400099e9  lea     r11, [r10+rax*4]
0x1400099ed  mov     r10, cs:WPP_GLOBAL_Control
0x1400099f4  mov     eax, [r10+r11*4+2Ch]
0x1400099f9  bt      eax, edx
0x1400099fc  jb      short loc_140009A5E
0x1400099fe  mov     r9, [rsp+88h+arg_20]
0x140009a06  lea     rax, [rsp+88h+arg_30]
0x140009a0e  mov     [rsp+88h+var_40], 0
0x140009a17  mov     r8d, r14d
0x140009a1a  mov     [rsp+88h+var_48], rbx
0x140009a1f  mov     edx, esi
0x140009a21  mov     [rsp+88h+var_50], rax
0x140009a26  mov     rcx, r15
0x140009a29  lea     rax, [rsp+88h+arg_28]
0x140009a31  mov     [rsp+88h+var_58], 8
0x140009a3a  mov     [rsp+88h+var_60], rax
0x140009a3f  mov     word ptr [rsp+88h+var_68], bp
0x140009a44  call    cs:__imp_WppAutoLogTrace
0x140009a4b  nop     dword ptr [rax+rax+00h]
0x140009a50  add     rsp, 58h
0x140009a54  pop     r15
0x140009a56  pop     r14
0x140009a58  pop     rdi
0x140009a59  pop     rsi
0x140009a5a  pop     rbp
0x140009a5b  pop     rbx
0x140009a5c  retn
0x140009a5e  lea     rcx, [rdi+rdi*4]
0x140009a62  add     rcx, rcx
0x140009a65  cmp     [r10+rcx*8+29h], sil
0x140009a6a  jb      short loc_1400099FE
0x140009a6c  mov     rax, cs:pfnWppTraceMessage
0x140009a73  lea     rdx, [rsp+88h+arg_30]
0x140009a7b  mov     r8, [rsp+88h+arg_20]
0x140009a83  mov     r9d, ebp
0x140009a86  mov     rcx, [r10+rcx*8+18h]
0x140009a8b  mov     [rsp+88h+var_48], 0
0x140009a94  mov     [rsp+88h+var_50], rbx
0x140009a99  mov     [rsp+88h+var_58], rdx
0x140009a9e  lea     rdx, [rsp+88h+arg_28]
0x140009aa6  mov     [rsp+88h+var_60], 8
0x140009aaf  mov     [rsp+88h+var_68], rdx
0x140009ab4  mov     edx, 2Bh ; '+'
0x140009ab9  call    _guard_dispatch_icall
0x140009abe  jmp     loc_1400099FE
```
