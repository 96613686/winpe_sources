# WPP_RECORDER_SF_dDd

- ea: `0x14000866c`
- end: `0x14000879a`
- name: `WPP_RECORDER_SF_dDd`
- size: `302`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x140008df0`
- `0x1400093e0`
- `0x1400099d0`
- `0x14000a450`
- `0x14000af00`
- `0x14000b670`

## callees

- `0x14000866c`
- `0x140010700`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140008780`
- `WppRecorder!WppAutoLogTrace` at `0x140008780`

## pseudocode

```c
__int64 WPP_RECORDER_SF_dDd(__int64 a1, unsigned __int8 a2, unsigned int a3, unsigned __int16 a4, __int64 a5, ...)
{
  unsigned __int64 v7; // rbx
  unsigned int v9; // edi
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
  v9 = a2;
  v10 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v7 + (((a3 - 1) >> 5) & 0x7FF) + 1);
  if ( _bittest(&v10, a3 - 1) && *((_BYTE *)&WPP_GLOBAL_Control->Timer + 80 * v7 + 1) >= a2 )
    ((void (__fastcall *)(_QWORD, __int64, __int64, _QWORD, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      *((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v7),
      43,
      a5,
      a4,
      (__int64 *)va,
      4,
      (__int64 *)va1,
      4,
      va2,
      4,
      0);
  LOWORD(v12) = a4;
  return WppAutoLogTrace(a1, v9, a3, a5, v12, (__int64 *)va);
}

```

## disassembly

```asm
0x14000866c  push    rbx
0x14000866e  push    rbp
0x14000866f  push    rsi
0x140008670  push    rdi
0x140008671  push    r14
0x140008673  push    r15
0x140008675  sub     rsp, 68h
0x140008679  mov     ebp, r8d
0x14000867c  mov     r14, rcx
0x14000867f  mov     ebx, r8d
0x140008682  mov     r15d, 4
0x140008688  shr     rbx, 10h
0x14000868c  movzx   esi, r9w
0x140008690  lea     r11d, [rbp-1]
0x140008694  movzx   edi, dl
0x140008697  mov     r10d, r11d
0x14000869a  shr     r10, 5
0x14000869e  lea     rax, [rbx+rbx*4]
0x1400086a2  and     r10d, 7FFh
0x1400086a9  lea     rax, [r10+rax*4]
0x1400086ad  mov     r10, cs:WPP_GLOBAL_Control
0x1400086b4  mov     eax, [r10+rax*4+2Ch]
0x1400086b9  bt      eax, r11d
0x1400086bd  jnb     short loc_14000872C
0x1400086bf  lea     rcx, [rbx+rbx*4]
0x1400086c3  add     rcx, rcx
0x1400086c6  cmp     [r10+rcx*8+29h], dil
0x1400086cb  jb      short loc_14000872C
0x1400086cd  mov     rax, cs:pfnWppTraceMessage
0x1400086d4  lea     rdx, [rsp+98h+arg_38]
0x1400086dc  mov     r8, [rsp+98h+arg_20]
0x1400086e4  mov     r9d, esi
0x1400086e7  mov     rcx, [r10+rcx*8+18h]
0x1400086ec  mov     [rsp+98h+var_48], 0
0x1400086f5  mov     [rsp+98h+var_50], r15
0x1400086fa  mov     [rsp+98h+var_58], rdx
0x1400086ff  lea     rdx, [rsp+98h+arg_30]
0x140008707  mov     [rsp+98h+var_60], r15
0x14000870c  mov     [rsp+98h+var_68], rdx
0x140008711  lea     rdx, [rsp+98h+arg_28]
0x140008719  mov     [rsp+98h+var_70], r15
0x14000871e  mov     [rsp+98h+var_78], rdx
0x140008723  lea     edx, [r15+27h]
0x140008727  call    _guard_dispatch_icall
0x14000872c  mov     r9, [rsp+98h+arg_20]
0x140008734  lea     rax, [rsp+98h+arg_38]
0x14000873c  mov     [rsp+98h+var_40], 0
0x140008745  mov     r8d, ebp
0x140008748  mov     [rsp+98h+var_48], r15
0x14000874d  mov     edx, edi
0x14000874f  mov     [rsp+98h+var_50], rax
0x140008754  mov     rcx, r14
0x140008757  mov     [rsp+98h+var_58], r15
0x14000875c  lea     rax, [rsp+98h+arg_30]
0x140008764  mov     [rsp+98h+var_60], rax
0x140008769  lea     rax, [rsp+98h+arg_28]
0x140008771  mov     [rsp+98h+var_68], r15
0x140008776  mov     [rsp+98h+var_70], rax
0x14000877b  mov     word ptr [rsp+98h+var_78], si
0x140008780  call    cs:__imp_WppAutoLogTrace
0x140008787  nop     dword ptr [rax+rax+00h]
0x14000878c  add     rsp, 68h
0x140008790  pop     r15
0x140008792  pop     r14
0x140008794  pop     rdi
0x140008795  pop     rsi
0x140008796  pop     rbp
0x140008797  pop     rbx
0x140008798  retn
```
