# WPP_RECORDER_SF_q

- ea: `0x1400083c8`
- end: `0x1400084b2`
- name: `WPP_RECORDER_SF_q`
- size: `234`
- prototype: ``
- caller_count: `37`
- callee_count: `2`
- tags: ``

## callers

- `0x140001bc8`
- `0x140002200`
- `0x140002630`
- `0x140002ad0`
- `0x140003470`
- `0x1400046c0`
- `0x140004b08`
- `0x140005350`
- `0x1400055c0`
- `0x140006630`
- `0x140006d40`
- `0x140007170`
- `0x140007844`
- `0x140007b3c`
- `0x140007c38`
- `0x140007f8c`
- `0x140008230`
- `0x140008980`
- `0x140008d58`
- `0x140009368`
- `0x14000a1b4`
- `0x14000a300`
- `0x14000a390`
- `0x14000b670`
- `0x14000d630`
- `0x14000eb6c`
- `0x14000f220`
- `0x140013eb0`
- `0x140014560`
- `0x1400242a4`
- `0x1400249d4`
- `0x1400253c4`
- `0x140028440`
- `0x14002a2e0`
- `0x14002b010`
- `0x14002ced0`
- `0x14002e27c`

## callees

- `0x1400083c8`
- `0x140014d50`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140008447`
- `WppRecorder!WppAutoLogTrace` at `0x140008447`

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
0x1400083c8  push    rbx
0x1400083ca  push    rbp
0x1400083cb  push    rsi
0x1400083cc  push    rdi
0x1400083cd  push    r14
0x1400083cf  sub     rsp, 40h
0x1400083d3  mov     ebp, r8d
0x1400083d6  mov     r14, rcx
0x1400083d9  mov     ebx, r8d
0x1400083dc  shr     rbx, 10h
0x1400083e0  movzx   esi, r9w
0x1400083e4  lea     r11d, [rbp-1]
0x1400083e8  movzx   edi, dl
0x1400083eb  mov     r10d, r11d
0x1400083ee  shr     r10, 5
0x1400083f2  lea     rax, [rbx+rbx*4]
0x1400083f6  and     r10d, 7FFh
0x1400083fd  lea     rax, [r10+rax*4]
0x140008401  mov     r10, cs:WPP_GLOBAL_Control
0x140008408  mov     eax, [r10+rax*4+2Ch]
0x14000840d  bt      eax, r11d
0x140008411  jb      short loc_14000845F
0x140008413  mov     r9, [rsp+68h+arg_20]
0x14000841b  lea     rax, [rsp+68h+arg_28]
0x140008423  mov     [rsp+68h+var_30], 0
0x14000842c  mov     r8d, ebp
0x14000842f  mov     [rsp+68h+var_38], 8
0x140008438  mov     edx, edi
0x14000843a  mov     [rsp+68h+var_40], rax
0x14000843f  mov     rcx, r14
0x140008442  mov     word ptr [rsp+68h+var_48], si
0x140008447  call    cs:__imp_WppAutoLogTrace
0x14000844e  nop     dword ptr [rax+rax+00h]
0x140008453  add     rsp, 40h
0x140008457  pop     r14
0x140008459  pop     rdi
0x14000845a  pop     rsi
0x14000845b  pop     rbp
0x14000845c  pop     rbx
0x14000845d  retn
0x14000845f  lea     rcx, [rbx+rbx*4]
0x140008463  add     rcx, rcx
0x140008466  cmp     [r10+rcx*8+29h], dil
0x14000846b  jb      short loc_140008413
0x14000846d  mov     rax, cs:pfnWppTraceMessage
0x140008474  lea     rdx, [rsp+68h+arg_28]
0x14000847c  mov     r8, [rsp+68h+arg_20]
0x140008484  mov     r9d, esi
0x140008487  mov     rcx, [r10+rcx*8+18h]
0x14000848c  mov     [rsp+68h+var_38], 0
0x140008495  mov     [rsp+68h+var_40], 8
0x14000849e  mov     [rsp+68h+var_48], rdx
0x1400084a3  mov     edx, 2Bh ; '+'
0x1400084a8  call    _guard_dispatch_icall
0x1400084ad  jmp     loc_140008413
```
