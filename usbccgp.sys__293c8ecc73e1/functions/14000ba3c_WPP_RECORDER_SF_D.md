# WPP_RECORDER_SF_D

- ea: `0x14000ba3c`
- end: `0x14000bb21`
- name: `WPP_RECORDER_SF_D`
- size: `229`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x140001bc8`
- `0x140002200`
- `0x140002ad0`
- `0x140006d40`
- `0x140007170`
- `0x14000b9d0`
- `0x140010c08`
- `0x1400145e0`
- `0x140022008`
- `0x140023214`
- `0x140026294`
- `0x1400265cc`
- `0x140028f7c`

## callees

- `0x14000ba3c`
- `0x140014d50`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000bb09`
- `WppRecorder!WppAutoLogTrace` at `0x14000bb09`

## pseudocode

```c
__int64 WPP_RECORDER_SF_D(__int64 a1, unsigned __int8 a2, unsigned int a3, unsigned __int16 a4, __int64 a5, ...)
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
      4,
      0);
  LOWORD(v12) = a4;
  return WppAutoLogTrace(a1, v9, a3, a5, v12, va);
}

```

## disassembly

```asm
0x14000ba3c  push    rbx
0x14000ba3e  push    rbp
0x14000ba3f  push    rsi
0x14000ba40  push    rdi
0x14000ba41  push    r14
0x14000ba43  sub     rsp, 40h
0x14000ba47  mov     ebp, r8d
0x14000ba4a  mov     r14, rcx
0x14000ba4d  mov     ebx, r8d
0x14000ba50  shr     rbx, 10h
0x14000ba54  movzx   esi, r9w
0x14000ba58  lea     r11d, [rbp-1]
0x14000ba5c  movzx   edi, dl
0x14000ba5f  mov     r10d, r11d
0x14000ba62  shr     r10, 5
0x14000ba66  lea     rax, [rbx+rbx*4]
0x14000ba6a  and     r10d, 7FFh
0x14000ba71  lea     rax, [r10+rax*4]
0x14000ba75  mov     r10, cs:WPP_GLOBAL_Control
0x14000ba7c  mov     eax, [r10+rax*4+2Ch]
0x14000ba81  bt      eax, r11d
0x14000ba85  jnb     short loc_14000BAD5
0x14000ba87  lea     rcx, [rbx+rbx*4]
0x14000ba8b  add     rcx, rcx
0x14000ba8e  cmp     [r10+rcx*8+29h], dil
0x14000ba93  jb      short loc_14000BAD5
0x14000ba95  mov     rax, cs:pfnWppTraceMessage
0x14000ba9c  lea     rdx, [rsp+68h+arg_28]
0x14000baa4  mov     r8, [rsp+68h+arg_20]
0x14000baac  mov     r9d, esi
0x14000baaf  mov     rcx, [r10+rcx*8+18h]
0x14000bab4  mov     [rsp+68h+var_38], 0
0x14000babd  mov     [rsp+68h+var_40], 4
0x14000bac6  mov     [rsp+68h+var_48], rdx
0x14000bacb  mov     edx, 2Bh ; '+'
0x14000bad0  call    _guard_dispatch_icall
0x14000bad5  mov     r9, [rsp+68h+arg_20]
0x14000badd  lea     rax, [rsp+68h+arg_28]
0x14000bae5  mov     [rsp+68h+var_30], 0
0x14000baee  mov     r8d, ebp
0x14000baf1  mov     [rsp+68h+var_38], 4
0x14000bafa  mov     edx, edi
0x14000bafc  mov     [rsp+68h+var_40], rax
0x14000bb01  mov     rcx, r14
0x14000bb04  mov     word ptr [rsp+68h+var_48], si
0x14000bb09  call    cs:__imp_WppAutoLogTrace
0x14000bb10  nop     dword ptr [rax+rax+00h]
0x14000bb15  add     rsp, 40h
0x14000bb19  pop     r14
0x14000bb1b  pop     rdi
0x14000bb1c  pop     rsi
0x14000bb1d  pop     rbp
0x14000bb1e  pop     rbx
0x14000bb1f  retn
```
