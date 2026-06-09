# WPP_RECORDER_SF_

- ea: `0x140001020`
- end: `0x1400010d9`
- name: `WPP_RECORDER_SF_`
- size: `185`
- prototype: `__int64 __fastcall(_DWORD, _DWORD, _DWORD, _DWORD, __int64)`
- caller_count: `90`
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
- `0x140004080`
- `0x140004130`
- `0x1400043cc`
- `0x140004740`
- `0x140004908`
- `0x140004ea4`
- `0x14000529c`
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
- `0x140007b3c`
- `0x140007fdc`
- `0x140008388`
- `0x1400088a0`
- `0x140008aa4`
- `0x140008d10`
- `0x140008df0`
- `0x1400093e0`
- `0x140009634`
- `0x1400099d0`
- `0x14000a450`
- `0x14000ad90`
- `0x14000ae20`
- `0x14000af00`
- `0x14000b3fc`
- `0x14000b670`
- `0x14000be88`
- `0x14000c17c`
- `0x14000c500`
- `0x14000c948`
- `0x14000ca60`
- `0x14000ced8`
- `0x14000cfd0`
- `0x14000d26c`
- `0x14000d3ac`

## callees

- `0x140001020`
- `0x140010700`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x1400010c1`
- `WppRecorder!WppAutoLogTrace` at `0x1400010c1`

## pseudocode

```c
__int64 __fastcall WPP_RECORDER_SF_(__int64 a1, unsigned __int8 a2, unsigned int a3, unsigned __int16 a4, __int64 a5)
{
  unsigned __int64 v7; // rbx
  unsigned int v9; // edi
  int v10; // eax
  int v12; // [rsp+20h] [rbp-38h]

  v7 = (unsigned __int64)a3 >> 16;
  v9 = a2;
  v10 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v7 + (((a3 - 1) >> 5) & 0x7FF) + 1);
  if ( _bittest(&v10, a3 - 1) && *((_BYTE *)&WPP_GLOBAL_Control->Timer + 80 * v7 + 1) >= a2 )
    ((void (__fastcall *)(_QWORD, __int64, __int64, _QWORD, _QWORD))pfnWppTraceMessage)(
      *((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v7),
      43,
      a5,
      a4,
      0);
  LOWORD(v12) = a4;
  return WppAutoLogTrace(a1, v9, a3, a5, v12, 0);
}

```

## disassembly

```asm
0x140001020  push    rbx
0x140001022  push    rbp
0x140001023  push    rsi
0x140001024  push    rdi
0x140001025  push    r14
0x140001027  sub     rsp, 30h
0x14000102b  mov     ebp, r8d
0x14000102e  mov     r14, rcx
0x140001031  mov     ebx, r8d
0x140001034  shr     rbx, 10h
0x140001038  movzx   esi, r9w
0x14000103c  lea     r11d, [rbp-1]
0x140001040  movzx   edi, dl
0x140001043  mov     r10d, r11d
0x140001046  shr     r10, 5
0x14000104a  lea     rax, [rbx+rbx*4]
0x14000104e  and     r10d, 7FFh
0x140001055  lea     rax, [r10+rax*4]
0x140001059  mov     r10, cs:WPP_GLOBAL_Control
0x140001060  mov     eax, [r10+rax*4+2Ch]
0x140001065  bt      eax, r11d
0x140001069  jnb     short loc_1400010A3
0x14000106b  lea     rcx, [rbx+rbx*4]
0x14000106f  add     rcx, rcx
0x140001072  cmp     [r10+rcx*8+29h], dil
0x140001077  jb      short loc_1400010A3
0x140001079  mov     rax, cs:pfnWppTraceMessage
0x140001080  mov     r9d, esi
0x140001083  mov     r8, [rsp+58h+arg_20]
0x14000108b  mov     edx, 2Bh ; '+'
0x140001090  mov     rcx, [r10+rcx*8+18h]
0x140001095  mov     [rsp+58h+var_38], 0
0x14000109e  call    _guard_dispatch_icall
0x1400010a3  mov     r9, [rsp+58h+arg_20]
0x1400010ab  mov     r8d, ebp
0x1400010ae  mov     [rsp+58h+var_30], 0
0x1400010b7  mov     edx, edi
0x1400010b9  mov     rcx, r14
0x1400010bc  mov     word ptr [rsp+58h+var_38], si
0x1400010c1  call    cs:__imp_WppAutoLogTrace
0x1400010c8  nop     dword ptr [rax+rax+00h]
0x1400010cd  add     rsp, 30h
0x1400010d1  pop     r14
0x1400010d3  pop     rdi
0x1400010d4  pop     rsi
0x1400010d5  pop     rbp
0x1400010d6  pop     rbx
0x1400010d7  retn
```
