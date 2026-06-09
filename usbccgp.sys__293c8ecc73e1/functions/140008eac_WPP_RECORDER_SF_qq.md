# WPP_RECORDER_SF_qq

- ea: `0x140008eac`
- end: `0x140008fbc`
- name: `WPP_RECORDER_SF_qq`
- size: `272`
- prototype: ``
- caller_count: `23`
- callee_count: `2`
- tags: ``

## callers

- `0x140002ad0`
- `0x140003e88`
- `0x140004078`
- `0x1400059e4`
- `0x140005fc4`
- `0x140007170`
- `0x140007844`
- `0x140007e70`
- `0x140008b00`
- `0x140009210`
- `0x140009368`
- `0x140009590`
- `0x140009f10`
- `0x14000a068`
- `0x14000a1b4`
- `0x14000d630`
- `0x14000e360`
- `0x14000f220`
- `0x140014060`
- `0x1400142fc`
- `0x140014890`
- `0x140028cc0`
- `0x14002cfb0`

## callees

- `0x140008eac`
- `0x140014d50`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140008f41`
- `WppRecorder!WppAutoLogTrace` at `0x140008f41`

## pseudocode

```c
__int64 WPP_RECORDER_SF_qq(__int64 a1, unsigned __int8 a2, unsigned int a3, unsigned __int16 a4, __int64 a5, ...)
{
  unsigned __int64 v7; // rbx
  unsigned int v9; // edi
  int v10; // eax
  int v12; // [rsp+20h] [rbp-68h]
  __int64 v13; // [rsp+B8h] [rbp+30h] BYREF
  va_list va; // [rsp+B8h] [rbp+30h]
  va_list va1; // [rsp+C0h] [rbp+38h] BYREF

  va_start(va1, a5);
  va_start(va, a5);
  v13 = va_arg(va1, _QWORD);
  v7 = (unsigned __int64)a3 >> 16;
  v9 = a2;
  v10 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v7 + (((a3 - 1) >> 5) & 0x7FF) + 1);
  if ( _bittest(&v10, a3 - 1) && *((_BYTE *)&WPP_GLOBAL_Control->Timer + 80 * v7 + 1) >= a2 )
    ((void (__fastcall *)(_QWORD, __int64, __int64, _QWORD, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      *((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v7),
      43,
      a5,
      a4,
      (__int64 *)va,
      8,
      va1,
      8,
      0);
  LOWORD(v12) = a4;
  return WppAutoLogTrace(a1, v9, a3, a5, v12, (__int64 *)va);
}

```

## disassembly

```asm
0x140008eac  push    rbx
0x140008eae  push    rbp
0x140008eaf  push    rsi
0x140008eb0  push    rdi
0x140008eb1  push    r14
0x140008eb3  push    r15
0x140008eb5  sub     rsp, 58h
0x140008eb9  mov     ebp, r8d
0x140008ebc  mov     r14, rcx
0x140008ebf  mov     ebx, r8d
0x140008ec2  mov     r15d, 8
0x140008ec8  shr     rbx, 10h
0x140008ecc  movzx   esi, r9w
0x140008ed0  lea     r11d, [rbp-1]
0x140008ed4  movzx   edi, dl
0x140008ed7  mov     r10d, r11d
0x140008eda  shr     r10, 5
0x140008ede  lea     rax, [rbx+rbx*4]
0x140008ee2  and     r10d, 7FFh
0x140008ee9  lea     rax, [r10+rax*4]
0x140008eed  mov     r10, cs:WPP_GLOBAL_Control
0x140008ef4  mov     eax, [r10+rax*4+2Ch]
0x140008ef9  bt      eax, r11d
0x140008efd  jb      short loc_140008F5B
0x140008eff  mov     r9, [rsp+88h+arg_20]
0x140008f07  lea     rax, [rsp+88h+arg_30]
0x140008f0f  mov     [rsp+88h+var_40], 0
0x140008f18  mov     r8d, ebp
0x140008f1b  mov     [rsp+88h+var_48], r15
0x140008f20  mov     edx, edi
0x140008f22  mov     [rsp+88h+var_50], rax
0x140008f27  mov     rcx, r14
0x140008f2a  lea     rax, [rsp+88h+arg_28]
0x140008f32  mov     [rsp+88h+var_58], r15
0x140008f37  mov     [rsp+88h+var_60], rax
0x140008f3c  mov     word ptr [rsp+88h+var_68], si
0x140008f41  call    cs:__imp_WppAutoLogTrace
0x140008f48  nop     dword ptr [rax+rax+00h]
0x140008f4d  add     rsp, 58h
0x140008f51  pop     r15
0x140008f53  pop     r14
0x140008f55  pop     rdi
0x140008f56  pop     rsi
0x140008f57  pop     rbp
0x140008f58  pop     rbx
0x140008f59  retn
0x140008f5b  lea     rcx, [rbx+rbx*4]
0x140008f5f  add     rcx, rcx
0x140008f62  cmp     [r10+rcx*8+29h], dil
0x140008f67  jb      short loc_140008EFF
0x140008f69  mov     rax, cs:pfnWppTraceMessage
0x140008f70  lea     rdx, [rsp+88h+arg_30]
0x140008f78  mov     r8, [rsp+88h+arg_20]
0x140008f80  mov     r9d, esi
0x140008f83  mov     rcx, [r10+rcx*8+18h]
0x140008f88  mov     [rsp+88h+var_48], 0
0x140008f91  mov     [rsp+88h+var_50], r15
0x140008f96  mov     [rsp+88h+var_58], rdx
0x140008f9b  lea     rdx, [rsp+88h+arg_28]
0x140008fa3  mov     [rsp+88h+var_60], r15
0x140008fa8  mov     [rsp+88h+var_68], rdx
0x140008fad  mov     edx, 2Bh ; '+'
0x140008fb2  call    _guard_dispatch_icall
0x140008fb7  jmp     loc_140008EFF
```
