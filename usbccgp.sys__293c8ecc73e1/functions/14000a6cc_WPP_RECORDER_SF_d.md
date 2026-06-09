# WPP_RECORDER_SF_d

- ea: `0x14000a6cc`
- end: `0x14000a7b6`
- name: `WPP_RECORDER_SF_d`
- size: `234`
- prototype: ``
- caller_count: `54`
- callee_count: `2`
- tags: ``

## callers

- `0x140001314`
- `0x140003b3c`
- `0x140004078`
- `0x1400047d0`
- `0x140005940`
- `0x14000a068`
- `0x14000a448`
- `0x14000a7bc`
- `0x14000aed0`
- `0x14000e584`
- `0x14000e994`
- `0x14000f558`
- `0x140010650`
- `0x140010f80`
- `0x1400114d8`
- `0x14001268c`
- `0x1400133e0`
- `0x1400145e0`
- `0x140022008`
- `0x140022240`
- `0x140022ee4`
- `0x140022fe8`
- `0x140023414`
- `0x140023694`
- `0x140023938`
- `0x1400242a4`
- `0x14002484c`
- `0x1400249d4`
- `0x140026294`
- `0x1400265cc`
- `0x140026b6c`
- `0x14002772c`
- `0x140027dcc`
- `0x140028008`
- `0x140028440`
- `0x140028800`
- `0x140028f7c`
- `0x14002977c`
- `0x14002990c`
- `0x140029a38`
- `0x140029b50`
- `0x14002a2e0`
- `0x14002a9b0`
- `0x14002b010`
- `0x14002b99c`
- `0x14002c2cc`
- `0x14002c430`
- `0x14002c604`
- `0x14002c8e4`
- `0x14002ca84`

## callees

- `0x14000a6cc`
- `0x140014d50`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000a74b`
- `WppRecorder!WppAutoLogTrace` at `0x14000a74b`

## pseudocode

```c
__int64 WPP_RECORDER_SF_d(__int64 a1, unsigned __int8 a2, unsigned int a3, unsigned __int16 a4, __int64 a5, ...)
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
0x14000a6cc  push    rbx
0x14000a6ce  push    rbp
0x14000a6cf  push    rsi
0x14000a6d0  push    rdi
0x14000a6d1  push    r14
0x14000a6d3  sub     rsp, 40h
0x14000a6d7  mov     ebp, r8d
0x14000a6da  mov     r14, rcx
0x14000a6dd  mov     ebx, r8d
0x14000a6e0  shr     rbx, 10h
0x14000a6e4  movzx   esi, r9w
0x14000a6e8  lea     r11d, [rbp-1]
0x14000a6ec  movzx   edi, dl
0x14000a6ef  mov     r10d, r11d
0x14000a6f2  shr     r10, 5
0x14000a6f6  lea     rax, [rbx+rbx*4]
0x14000a6fa  and     r10d, 7FFh
0x14000a701  lea     rax, [r10+rax*4]
0x14000a705  mov     r10, cs:WPP_GLOBAL_Control
0x14000a70c  mov     eax, [r10+rax*4+2Ch]
0x14000a711  bt      eax, r11d
0x14000a715  jb      short loc_14000A763
0x14000a717  mov     r9, [rsp+68h+arg_20]
0x14000a71f  lea     rax, [rsp+68h+arg_28]
0x14000a727  mov     [rsp+68h+var_30], 0
0x14000a730  mov     r8d, ebp
0x14000a733  mov     [rsp+68h+var_38], 4
0x14000a73c  mov     edx, edi
0x14000a73e  mov     [rsp+68h+var_40], rax
0x14000a743  mov     rcx, r14
0x14000a746  mov     word ptr [rsp+68h+var_48], si
0x14000a74b  call    cs:__imp_WppAutoLogTrace
0x14000a752  nop     dword ptr [rax+rax+00h]
0x14000a757  add     rsp, 40h
0x14000a75b  pop     r14
0x14000a75d  pop     rdi
0x14000a75e  pop     rsi
0x14000a75f  pop     rbp
0x14000a760  pop     rbx
0x14000a761  retn
0x14000a763  lea     rcx, [rbx+rbx*4]
0x14000a767  add     rcx, rcx
0x14000a76a  cmp     [r10+rcx*8+29h], dil
0x14000a76f  jb      short loc_14000A717
0x14000a771  mov     rax, cs:pfnWppTraceMessage
0x14000a778  lea     rdx, [rsp+68h+arg_28]
0x14000a780  mov     r8, [rsp+68h+arg_20]
0x14000a788  mov     r9d, esi
0x14000a78b  mov     rcx, [r10+rcx*8+18h]
0x14000a790  mov     [rsp+68h+var_38], 0
0x14000a799  mov     [rsp+68h+var_40], 4
0x14000a7a2  mov     [rsp+68h+var_48], rdx
0x14000a7a7  mov     edx, 2Bh ; '+'
0x14000a7ac  call    _guard_dispatch_icall
0x14000a7b1  jmp     loc_14000A717
```
