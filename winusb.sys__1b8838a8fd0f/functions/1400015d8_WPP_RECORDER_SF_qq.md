# WPP_RECORDER_SF_qq

- ea: `0x1400015d8`
- end: `0x1400016e2`
- name: `WPP_RECORDER_SF_qq`
- size: `266`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x140007b3c`
- `0x140008388`
- `0x14000d5b8`
- `0x14000e640`
- `0x14000ea0c`
- `0x14000fe14`
- `0x1400190b0`

## callees

- `0x1400015d8`
- `0x140010700`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x1400016c8`
- `WppRecorder!WppAutoLogTrace` at `0x1400016c8`

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
0x1400015d8  push    rbx
0x1400015da  push    rbp
0x1400015db  push    rsi
0x1400015dc  push    rdi
0x1400015dd  push    r14
0x1400015df  push    r15
0x1400015e1  sub     rsp, 58h
0x1400015e5  mov     ebp, r8d
0x1400015e8  mov     r14, rcx
0x1400015eb  mov     ebx, r8d
0x1400015ee  mov     r15d, 8
0x1400015f4  shr     rbx, 10h
0x1400015f8  movzx   esi, r9w
0x1400015fc  lea     r11d, [rbp-1]
0x140001600  movzx   edi, dl
0x140001603  mov     r10d, r11d
0x140001606  shr     r10, 5
0x14000160a  lea     rax, [rbx+rbx*4]
0x14000160e  and     r10d, 7FFh
0x140001615  lea     rax, [r10+rax*4]
0x140001619  mov     r10, cs:WPP_GLOBAL_Control
0x140001620  mov     eax, [r10+rax*4+2Ch]
0x140001625  bt      eax, r11d
0x140001629  jnb     short loc_140001686
0x14000162b  lea     rcx, [rbx+rbx*4]
0x14000162f  add     rcx, rcx
0x140001632  cmp     [r10+rcx*8+29h], dil
0x140001637  jb      short loc_140001686
0x140001639  mov     rax, cs:pfnWppTraceMessage
0x140001640  lea     rdx, [rsp+88h+arg_30]
0x140001648  mov     r8, [rsp+88h+arg_20]
0x140001650  mov     r9d, esi
0x140001653  mov     rcx, [r10+rcx*8+18h]
0x140001658  mov     [rsp+88h+var_48], 0
0x140001661  mov     [rsp+88h+var_50], r15
0x140001666  mov     [rsp+88h+var_58], rdx
0x14000166b  lea     rdx, [rsp+88h+arg_28]
0x140001673  mov     [rsp+88h+var_60], r15
0x140001678  mov     [rsp+88h+var_68], rdx
0x14000167d  lea     edx, [r15+23h]
0x140001681  call    _guard_dispatch_icall
0x140001686  mov     r9, [rsp+88h+arg_20]
0x14000168e  lea     rax, [rsp+88h+arg_30]
0x140001696  mov     [rsp+88h+var_40], 0
0x14000169f  mov     r8d, ebp
0x1400016a2  mov     [rsp+88h+var_48], r15
0x1400016a7  mov     edx, edi
0x1400016a9  mov     [rsp+88h+var_50], rax
0x1400016ae  mov     rcx, r14
0x1400016b1  lea     rax, [rsp+88h+arg_28]
0x1400016b9  mov     [rsp+88h+var_58], r15
0x1400016be  mov     [rsp+88h+var_60], rax
0x1400016c3  mov     word ptr [rsp+88h+var_68], si
0x1400016c8  call    cs:__imp_WppAutoLogTrace
0x1400016cf  nop     dword ptr [rax+rax+00h]
0x1400016d4  add     rsp, 58h
0x1400016d8  pop     r15
0x1400016da  pop     r14
0x1400016dc  pop     rdi
0x1400016dd  pop     rsi
0x1400016de  pop     rbp
0x1400016df  pop     rbx
0x1400016e0  retn
```
