# WPP_RECORDER_SF_

- ea: `0x1400088b4`
- end: `0x14000896f`
- name: `WPP_RECORDER_SF_`
- size: `187`
- prototype: ``
- caller_count: `49`
- callee_count: `2`
- tags: ``

## callers

- `0x14000159c`
- `0x140001acc`
- `0x140001bc8`
- `0x140002ad0`
- `0x140003470`
- `0x1400049c0`
- `0x140004f50`
- `0x1400055c0`
- `0x140005750`
- `0x1400059e4`
- `0x140005fc4`
- `0x140006834`
- `0x140007170`
- `0x140007a8c`
- `0x140008810`
- `0x140008b00`
- `0x140009590`
- `0x140009acc`
- `0x14000a448`
- `0x14000d444`
- `0x14000d900`
- `0x14000eb6c`
- `0x14000ecc8`
- `0x14000f558`
- `0x14000fb68`
- `0x140011280`
- `0x14001268c`
- `0x1400131c0`
- `0x140013314`
- `0x140022008`
- `0x140023214`
- `0x140023694`
- `0x1400242a4`
- `0x1400253c4`
- `0x140025d6c`
- `0x140025f38`
- `0x140026294`
- `0x1400265cc`
- `0x140028d78`
- `0x140028f7c`
- `0x14002977c`
- `0x14002a018`
- `0x14002a2e0`
- `0x14002aec4`
- `0x14002b010`
- `0x14002b3bc`
- `0x14002c604`
- `0x14002d698`
- `0x14002d748`

## callees

- `0x1400088b4`
- `0x140014d50`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000891d`
- `WppRecorder!WppAutoLogTrace` at `0x14000891d`

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
0x1400088b4  push    rbx
0x1400088b6  push    rbp
0x1400088b7  push    rsi
0x1400088b8  push    rdi
0x1400088b9  push    r14
0x1400088bb  sub     rsp, 30h
0x1400088bf  mov     ebp, r8d
0x1400088c2  mov     r14, rcx
0x1400088c5  mov     ebx, r8d
0x1400088c8  shr     rbx, 10h
0x1400088cc  movzx   esi, r9w
0x1400088d0  lea     r11d, [rbp-1]
0x1400088d4  movzx   edi, dl
0x1400088d7  mov     r10d, r11d
0x1400088da  shr     r10, 5
0x1400088de  lea     rax, [rbx+rbx*4]
0x1400088e2  and     r10d, 7FFh
0x1400088e9  lea     rax, [r10+rax*4]
0x1400088ed  mov     r10, cs:WPP_GLOBAL_Control
0x1400088f4  mov     eax, [r10+rax*4+2Ch]
0x1400088f9  bt      eax, r11d
0x1400088fd  jb      short loc_140008935
0x1400088ff  mov     r9, [rsp+58h+arg_20]
0x140008907  mov     r8d, ebp
0x14000890a  mov     [rsp+58h+var_30], 0
0x140008913  mov     edx, edi
0x140008915  mov     rcx, r14
0x140008918  mov     word ptr [rsp+58h+var_38], si
0x14000891d  call    cs:__imp_WppAutoLogTrace
0x140008924  nop     dword ptr [rax+rax+00h]
0x140008929  add     rsp, 30h
0x14000892d  pop     r14
0x14000892f  pop     rdi
0x140008930  pop     rsi
0x140008931  pop     rbp
0x140008932  pop     rbx
0x140008933  retn
0x140008935  lea     rcx, [rbx+rbx*4]
0x140008939  add     rcx, rcx
0x14000893c  cmp     [r10+rcx*8+29h], dil
0x140008941  jb      short loc_1400088FF
0x140008943  mov     rax, cs:pfnWppTraceMessage
0x14000894a  mov     r9d, esi
0x14000894d  mov     r8, [rsp+58h+arg_20]
0x140008955  mov     edx, 2Bh ; '+'
0x14000895a  mov     rcx, [r10+rcx*8+18h]
0x14000895f  mov     [rsp+58h+var_38], 0
0x140008968  call    _guard_dispatch_icall
0x14000896d  jmp     short loc_1400088FF
```
