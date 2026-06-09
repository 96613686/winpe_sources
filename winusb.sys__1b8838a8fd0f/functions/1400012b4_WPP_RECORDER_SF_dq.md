# WPP_RECORDER_SF_dq

- ea: `0x1400012b4`
- end: `0x1400013c8`
- name: `WPP_RECORDER_SF_dq`
- size: `276`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400065e0`
- `0x1400194d0`

## callees

- `0x1400012b4`
- `0x140010700`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x1400013ae`
- `WppRecorder!WppAutoLogTrace` at `0x1400013ae`

## pseudocode

```c
__int64 WPP_RECORDER_SF_dq(__int64 a1, unsigned __int8 a2, unsigned int a3, unsigned __int16 a4, __int64 a5, ...)
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
      4,
      va1,
      8,
      0);
  LOWORD(v12) = a4;
  return WppAutoLogTrace(a1, v8, a3, a5, v12, (__int64 *)va);
}

```

## disassembly

```asm
0x1400012b4  push    rbx
0x1400012b6  push    rbp
0x1400012b7  push    rsi
0x1400012b8  push    rdi
0x1400012b9  push    r14
0x1400012bb  push    r15
0x1400012bd  sub     rsp, 58h
0x1400012c1  mov     r14d, r8d
0x1400012c4  mov     r15, rcx
0x1400012c7  mov     edi, r8d
0x1400012ca  shr     rdi, 10h
0x1400012ce  movzx   esi, dl
0x1400012d1  lea     ebx, [r14-1]
0x1400012d5  movzx   ebp, r9w
0x1400012d9  mov     r10d, ebx
0x1400012dc  and     ebx, 1Fh
0x1400012df  shr     r10, 5
0x1400012e3  lea     rax, [rdi+rdi*4]
0x1400012e7  and     r10d, 7FFh
0x1400012ee  mov     edx, ebx
0x1400012f0  mov     ebx, 8
0x1400012f5  lea     r11, [r10+rax*4]
0x1400012f9  mov     r10, cs:WPP_GLOBAL_Control
0x140001300  mov     eax, [r10+r11*4+2Ch]
0x140001305  bt      eax, edx
0x140001308  jnb     short loc_140001368
0x14000130a  lea     rcx, [rdi+rdi*4]
0x14000130e  add     rcx, rcx
0x140001311  cmp     [r10+rcx*8+29h], sil
0x140001316  jb      short loc_140001368
0x140001318  mov     rax, cs:pfnWppTraceMessage
0x14000131f  lea     rdx, [rsp+88h+arg_30]
0x140001327  mov     r8, [rsp+88h+arg_20]
0x14000132f  mov     r9d, ebp
0x140001332  mov     rcx, [r10+rcx*8+18h]
0x140001337  mov     [rsp+88h+var_48], 0
0x140001340  mov     [rsp+88h+var_50], rbx
0x140001345  mov     [rsp+88h+var_58], rdx
0x14000134a  lea     rdx, [rsp+88h+arg_28]
0x140001352  mov     [rsp+88h+var_60], 4
0x14000135b  mov     [rsp+88h+var_68], rdx
0x140001360  lea     edx, [rbx+23h]
0x140001363  call    _guard_dispatch_icall
0x140001368  mov     r9, [rsp+88h+arg_20]
0x140001370  lea     rax, [rsp+88h+arg_30]
0x140001378  mov     [rsp+88h+var_40], 0
0x140001381  mov     r8d, r14d
0x140001384  mov     [rsp+88h+var_48], rbx
0x140001389  mov     edx, esi
0x14000138b  mov     [rsp+88h+var_50], rax
0x140001390  mov     rcx, r15
0x140001393  lea     rax, [rsp+88h+arg_28]
0x14000139b  mov     [rsp+88h+var_58], 4
0x1400013a4  mov     [rsp+88h+var_60], rax
0x1400013a9  mov     word ptr [rsp+88h+var_68], bp
0x1400013ae  call    cs:__imp_WppAutoLogTrace
0x1400013b5  nop     dword ptr [rax+rax+00h]
0x1400013ba  add     rsp, 58h
0x1400013be  pop     r15
0x1400013c0  pop     r14
0x1400013c2  pop     rdi
0x1400013c3  pop     rsi
0x1400013c4  pop     rbp
0x1400013c5  pop     rbx
0x1400013c6  retn
```
