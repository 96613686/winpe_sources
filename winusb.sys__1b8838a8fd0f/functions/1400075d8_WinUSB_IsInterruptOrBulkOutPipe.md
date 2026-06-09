# WinUSB_IsInterruptOrBulkOutPipe

- ea: `0x1400075d8`
- end: `0x14000768b`
- name: `WinUSB_IsInterruptOrBulkOutPipe`
- size: `179`
- prototype: `char __fastcall(__int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140005838`
- `0x140006acc`
- `0x140006dec`
- `0x14000b3fc`

## callees

- `0x140001020`
- `0x1400011c8`
- `0x1400075d8`

## pseudocode

```c
char __fastcall WinUSB_IsInterruptOrBulkOutPipe(__int64 a1)
{
  char v2; // bl
  int v3; // ecx

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      46,
      (__int64)WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids);
  v2 = a1 && *(char *)(a1 + 8) >= 0 && (v3 = *(_DWORD *)(a1 + 12), v3 != 2) && v3 != 1;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      47,
      (__int64)WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids,
      v2);
  return v2;
}

```

## disassembly

```asm
0x1400075d8  push    rbx
0x1400075da  push    rbp
0x1400075db  push    rsi
0x1400075dc  push    rdi
0x1400075dd  push    r14
0x1400075df  sub     rsp, 30h
0x1400075e3  mov     rbx, rcx
0x1400075e6  xor     edi, edi; __annotation("TMF:",
0x1400075e8  lea     rbp, WPP_RECORDER_INITIALIZED
0x1400075ef  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400075f6  lea     r14, WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids
0x1400075fd  lea     esi, [rdi+1]
0x140007600  jz      short loc_140007626
0x140007602  mov     rcx, cs:WPP_GLOBAL_Control
0x140007609  cmp     [rcx+48h], di
0x14000760d  jz      short loc_140007626
0x14000760f  mov     rcx, [rcx+40h]
0x140007613  lea     r9d, [rdi+2Eh]
0x140007617  mov     r8d, esi
0x14000761a  mov     [rsp+58h+var_38], r14
0x14000761f  mov     dl, 5
0x140007621  call    WPP_RECORDER_SF_
0x140007626  test    rbx, rbx
0x140007629  jnz     short loc_140007630
0x14000762b  mov     bl, dil
0x14000762e  jmp     short loc_140007645
0x140007630  cmp     [rbx+8], dil
0x140007634  jl      short loc_14000762B
0x140007636  mov     ecx, [rbx+0Ch]
0x140007639  cmp     ecx, 2
0x14000763c  jz      short loc_14000762B
0x14000763e  cmp     ecx, esi
0x140007640  mov     ebx, esi
0x140007642  cmovz   ebx, edi
0x140007645  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14000764c  jz      short loc_14000767D
0x14000764e  mov     rcx, cs:WPP_GLOBAL_Control
0x140007655  cmp     [rcx+48h], di
0x140007659  jz      short loc_14000767D
0x14000765b  mov     rcx, [rcx+40h]
0x14000765f  mov     r9d, 2Fh ; '/'
0x140007665  movzx   r10d, bl
0x140007669  mov     r8d, esi
0x14000766c  mov     [rsp+58h+var_30], r10d
0x140007671  mov     dl, 5
0x140007673  mov     [rsp+58h+var_38], r14
0x140007678  call    WPP_RECORDER_SF_d
0x14000767d  mov     al, bl
0x14000767f  add     rsp, 30h
0x140007683  pop     r14
0x140007685  pop     rdi
0x140007686  pop     rsi
0x140007687  pop     rbp
0x140007688  pop     rbx
0x140007689  retn
```
