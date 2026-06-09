# WinUSB_IsInterruptOrBulkInPipe

- ea: `0x14000751c`
- end: `0x1400075cf`
- name: `WinUSB_IsInterruptOrBulkInPipe`
- size: `179`
- prototype: `char __fastcall(__int64)`
- caller_count: `7`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140005838`
- `0x140006acc`
- `0x140006dec`
- `0x140009634`
- `0x14001ab90`
- `0x14001af80`
- `0x14001c940`

## callees

- `0x140001020`
- `0x1400011c8`
- `0x14000751c`

## pseudocode

```c
char __fastcall WinUSB_IsInterruptOrBulkInPipe(__int64 a1)
{
  char v2; // bl
  int v3; // ecx

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      44,
      (__int64)WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids);
  v2 = a1 && *(char *)(a1 + 8) < 0 && (v3 = *(_DWORD *)(a1 + 12), v3 != 2) && v3 != 1;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      45,
      (__int64)WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids,
      v2);
  return v2;
}

```

## disassembly

```asm
0x14000751c  push    rbx
0x14000751e  push    rbp
0x14000751f  push    rsi
0x140007520  push    rdi
0x140007521  push    r14
0x140007523  sub     rsp, 30h
0x140007527  mov     rbx, rcx
0x14000752a  xor     edi, edi; __annotation("TMF:",
0x14000752c  lea     rbp, WPP_RECORDER_INITIALIZED
0x140007533  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000753a  lea     r14, WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids
0x140007541  lea     esi, [rdi+1]
0x140007544  jz      short loc_14000756A
0x140007546  mov     rcx, cs:WPP_GLOBAL_Control
0x14000754d  cmp     [rcx+48h], di
0x140007551  jz      short loc_14000756A
0x140007553  mov     rcx, [rcx+40h]
0x140007557  lea     r9d, [rdi+2Ch]
0x14000755b  mov     r8d, esi
0x14000755e  mov     [rsp+58h+var_38], r14
0x140007563  mov     dl, 5
0x140007565  call    WPP_RECORDER_SF_
0x14000756a  test    rbx, rbx
0x14000756d  jnz     short loc_140007574
0x14000756f  mov     bl, dil
0x140007572  jmp     short loc_140007589
0x140007574  cmp     [rbx+8], dil
0x140007578  jge     short loc_14000756F
0x14000757a  mov     ecx, [rbx+0Ch]
0x14000757d  cmp     ecx, 2
0x140007580  jz      short loc_14000756F
0x140007582  cmp     ecx, esi
0x140007584  mov     ebx, esi
0x140007586  cmovz   ebx, edi
0x140007589  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x140007590  jz      short loc_1400075C1
0x140007592  mov     rcx, cs:WPP_GLOBAL_Control
0x140007599  cmp     [rcx+48h], di
0x14000759d  jz      short loc_1400075C1
0x14000759f  mov     rcx, [rcx+40h]
0x1400075a3  mov     r9d, 2Dh ; '-'
0x1400075a9  movzx   r10d, bl
0x1400075ad  mov     r8d, esi
0x1400075b0  mov     [rsp+58h+var_30], r10d
0x1400075b5  mov     dl, 5
0x1400075b7  mov     [rsp+58h+var_38], r14
0x1400075bc  call    WPP_RECORDER_SF_d
0x1400075c1  mov     al, bl
0x1400075c3  add     rsp, 30h
0x1400075c7  pop     r14
0x1400075c9  pop     rdi
0x1400075ca  pop     rsi
0x1400075cb  pop     rbp
0x1400075cc  pop     rbx
0x1400075cd  retn
```
