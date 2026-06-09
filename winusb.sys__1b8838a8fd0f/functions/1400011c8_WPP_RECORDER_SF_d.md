# WPP_RECORDER_SF_d

- ea: `0x1400011c8`
- end: `0x1400012ad`
- name: `WPP_RECORDER_SF_d`
- size: `229`
- prototype: `__int64 __fastcall(_DWORD, _DWORD, _DWORD, _DWORD, __int64, char)`
- caller_count: `71`
- callee_count: `2`
- tags: ``

## callers

- `0x140001e04`
- `0x1400024d0`
- `0x1400026d0`
- `0x14000334c`
- `0x1400034cc`
- `0x140003a20`
- `0x140003e7c`
- `0x140004130`
- `0x1400043cc`
- `0x140004740`
- `0x140004908`
- `0x140004ea4`
- `0x1400053d4`
- `0x1400055fc`
- `0x140005838`
- `0x140005fe8`
- `0x1400065e0`
- `0x140006acc`
- `0x140006cb0`
- `0x140006dec`
- `0x14000751c`
- `0x1400075d8`
- `0x140007694`
- `0x1400079c8`
- `0x140007b3c`
- `0x140007fdc`
- `0x140008388`
- `0x140008aa4`
- `0x140008df0`
- `0x1400093e0`
- `0x140009634`
- `0x1400099d0`
- `0x14000a450`
- `0x14000af00`
- `0x14000b3fc`
- `0x14000b670`
- `0x14000be88`
- `0x14000c500`
- `0x14000ca60`
- `0x14000d3ac`
- `0x14000d750`
- `0x14000da50`
- `0x14000dccc`
- `0x14000e19c`
- `0x14000e7bc`
- `0x14000eff0`
- `0x14000fbe8`
- `0x140018010`
- `0x1400190b0`
- `0x140019720`

## callees

- `0x1400011c8`
- `0x140010700`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140001295`
- `WppRecorder!WppAutoLogTrace` at `0x140001295`

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
0x1400011c8  push    rbx
0x1400011ca  push    rbp
0x1400011cb  push    rsi
0x1400011cc  push    rdi
0x1400011cd  push    r14
0x1400011cf  sub     rsp, 40h
0x1400011d3  mov     ebp, r8d
0x1400011d6  mov     r14, rcx
0x1400011d9  mov     ebx, r8d
0x1400011dc  shr     rbx, 10h
0x1400011e0  movzx   esi, r9w
0x1400011e4  lea     r11d, [rbp-1]
0x1400011e8  movzx   edi, dl
0x1400011eb  mov     r10d, r11d
0x1400011ee  shr     r10, 5
0x1400011f2  lea     rax, [rbx+rbx*4]
0x1400011f6  and     r10d, 7FFh
0x1400011fd  lea     rax, [r10+rax*4]
0x140001201  mov     r10, cs:WPP_GLOBAL_Control
0x140001208  mov     eax, [r10+rax*4+2Ch]
0x14000120d  bt      eax, r11d
0x140001211  jnb     short loc_140001261
0x140001213  lea     rcx, [rbx+rbx*4]
0x140001217  add     rcx, rcx
0x14000121a  cmp     [r10+rcx*8+29h], dil
0x14000121f  jb      short loc_140001261
0x140001221  mov     rax, cs:pfnWppTraceMessage
0x140001228  lea     rdx, [rsp+68h+arg_28]
0x140001230  mov     r8, [rsp+68h+arg_20]
0x140001238  mov     r9d, esi
0x14000123b  mov     rcx, [r10+rcx*8+18h]
0x140001240  mov     [rsp+68h+var_38], 0
0x140001249  mov     [rsp+68h+var_40], 4
0x140001252  mov     [rsp+68h+var_48], rdx
0x140001257  mov     edx, 2Bh ; '+'
0x14000125c  call    _guard_dispatch_icall
0x140001261  mov     r9, [rsp+68h+arg_20]
0x140001269  lea     rax, [rsp+68h+arg_28]
0x140001271  mov     [rsp+68h+var_30], 0
0x14000127a  mov     r8d, ebp
0x14000127d  mov     [rsp+68h+var_38], 4
0x140001286  mov     edx, edi
0x140001288  mov     [rsp+68h+var_40], rax
0x14000128d  mov     rcx, r14
0x140001290  mov     word ptr [rsp+68h+var_48], si
0x140001295  call    cs:__imp_WppAutoLogTrace
0x14000129c  nop     dword ptr [rax+rax+00h]
0x1400012a1  add     rsp, 40h
0x1400012a5  pop     r14
0x1400012a7  pop     rdi
0x1400012a8  pop     rsi
0x1400012a9  pop     rbp
0x1400012aa  pop     rbx
0x1400012ab  retn
```
