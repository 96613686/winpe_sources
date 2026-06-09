# SkmmUnmapReadOnlyNtosData

- ea: `0x1400793c4`
- end: `0x140079601`
- name: `SkmmUnmapReadOnlyNtosData`
- size: `573`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x140014dd0`
- `0x14006dcfc`

## callees

- `0x140003780`
- `0x14000b980`
- `0x140020360`
- `0x140020424`
- `0x140025024`
- `0x14002b534`
- `0x14002f3f8`
- `0x14004fe2c`
- `0x1400793c4`
- `0x140081290`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmmUnmapReadOnlyNtosData(unsigned __int64 a1, __int64 a2)
{
  unsigned __int64 v4; // r14
  __int64 v5; // rsi
  __int64 v6; // rbx
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rcx
  unsigned __int64 v11; // rdi
  unsigned int v12; // r12d
  unsigned __int64 v13; // rbx
  __int64 PteTrace; // rax
  __int64 v15; // r13
  PVOID *v16; // r15
  PVOID StackBase; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  unsigned __int64 v20; // rax
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // r8
  int v24; // edx
  _BYTE v26[256]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v27; // [rsp+130h] [rbp+30h]
  char v28; // [rsp+134h] [rbp+34h]
  char v29; // [rsp+135h] [rbp+35h]
  _UNKNOWN *retaddr; // [rsp+178h] [rbp+78h]
  __int64 BackTraceHash; // [rsp+180h] [rbp+80h] BYREF
  __int64 v32; // [rsp+188h] [rbp+88h]

  memset_0(v26, 0, 0x108u);
  v4 = ((a1 & 0xFFF) + a2 + 4095) >> 12;
  v5 = ((a1 >> 9) & 0x7FFFFFFFF8LL) - 0x98000000000LL;
  v29 = -1;
  v6 = v5 << 25 >> 16;
  v32 = v6;
  SkmiBatchFlushTbRange(v6, (unsigned int)v4, v26);
  BackTraceHash = 2;
  SKMI_SWIZZLE_INVALID_PTE(&BackTraceHash, v7, v8, v9);
  v11 = BackTraceHash;
  v12 = 0;
  if ( v4 )
  {
    do
    {
      v13 = *(_QWORD *)v5;
      PteTrace = SkmiGetPteTrace(0, v5, 0, v11, *(_QWORD *)v5);
      v15 = PteTrace;
      if ( PteTrace )
      {
        v16 = (PVOID *)(PteTrace + 32);
        memset_0((void *)(PteTrace + 32), 0, 0x40u);
        if ( (SkmiFlags & 0x400000) != 0 )
        {
          StackBase = KeGetPcr()->NtTib.StackBase;
          if ( StackBase )
          {
            if ( !RtlCaptureStackBackTrace((ULONG)StackBase, 8u, v16, (PULONG)&BackTraceHash) )
            {
              *(_QWORD *)(v15 + 40) = retaddr;
              *v16 = (PVOID)SkmiGetInstructionPointer(v19, v18);
            }
          }
        }
      }
      v20 = v11;
      if ( (unsigned __int64)v5 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)v5 < 0xFFFFF6FB7DBED800uLL )
      {
        v21 = KeGetPcr()->NtTib.StackBase;
        v22 = v21 ? v21[10] : 0LL;
        v23 = *(_QWORD *)(v22 + 232);
        if ( v23 )
        {
          v24 = SkiKvaShadowMode;
          *(_QWORD *)(v23 + 8 * ((v5 >> 3) & 0x1FF)) = v11;
          if ( v24 != 2 && (v11 & 1) != 0 )
            v20 = v11 | 0x8000000000000000uLL;
        }
      }
      *(_QWORD *)v5 = v20;
      SkmiDecrementPageReferenceCount((v13 >> 12) & 0xFFFFFFFFFFLL);
      ++v12;
      v5 += 8;
    }
    while ( v12 < v4 );
    v6 = v32;
  }
  if ( v28 )
  {
    LOBYTE(v10) = v29;
    SkeFlushEntireTb(v10, 0);
  }
  else if ( v27 )
  {
    LOBYTE(v10) = v29;
    SkeFlushRangeListTb(v10, 0, v27, v26);
  }
  return SkmmFreeReservedMapping(v6, v4 << 12);
}

```

## disassembly

```asm
0x1400793c4  mov     [rsp-8+arg_10], rbx
0x1400793c9  push    rbp
0x1400793ca  push    rsi
0x1400793cb  push    rdi
0x1400793cc  push    r12
0x1400793ce  push    r13
0x1400793d0  push    r14
0x1400793d2  push    r15
0x1400793d4  lea     rbp, [rsp-40h]
0x1400793d9  sub     rsp, 140h
0x1400793e0  mov     r14, rdx
0x1400793e3  mov     rsi, rcx
0x1400793e6  xor     edx, edx; Val
0x1400793e8  lea     rcx, [rsp+170h+var_140]; void *
0x1400793ed  mov     r8d, 108h; Size
0x1400793f3  call    memset_0
0x1400793f8  mov     eax, esi
0x1400793fa  mov     rcx, 0FFFFF68000000000h
0x140079404  and     eax, 0FFFh
0x140079409  shr     rsi, 9
0x14007940d  add     r14, 0FFFh
0x140079414  add     r14, rax
0x140079417  mov     rax, 7FFFFFFFF8h
0x140079421  and     rsi, rax
0x140079424  shr     r14, 0Ch
0x140079428  mov     rax, rcx
0x14007942b  add     rsi, rax
0x14007942e  mov     rbx, rsi
0x140079431  shl     rbx, 19h
0x140079435  mov     rax, rcx
0x140079438  shl     rax, 19h
0x14007943c  lea     r8, [rsp+170h+var_140]
0x140079441  sub     rbx, rax
0x140079444  mov     [rbp+70h+var_3B], 0FFh
0x140079448  sar     rbx, 10h
0x14007944c  mov     edx, r14d
0x14007944f  mov     rcx, rbx
0x140079452  mov     [rbp+70h+arg_8], rbx
0x140079459  call    SkmiBatchFlushTbRange
0x14007945e  lea     rcx, [rbp+70h+BackTraceHash]
0x140079465  mov     [rbp+70h+BackTraceHash], 2
0x140079470  call    SKMI_SWIZZLE_INVALID_PTE
0x140079475  mov     rdi, [rbp+70h+BackTraceHash]
0x14007947c  xor     r15d, r15d
0x14007947f  mov     r12d, r15d
0x140079482  test    r14, r14
0x140079485  jz      loc_1400795AC
0x14007948b  mov     rbx, [rsi]
0x14007948e  mov     r9, rdi
0x140079491  mov     rax, [rsi]
0x140079494  xor     r8d, r8d
0x140079497  mov     rdx, rsi
0x14007949a  mov     [rsp+170h+var_150], rax
0x14007949f  xor     ecx, ecx
0x1400794a1  call    SkmiGetPteTrace
0x1400794a6  mov     r13, rax
0x1400794a9  test    rax, rax
0x1400794ac  jz      short loc_140079506
0x1400794ae  xor     edx, edx; Val
0x1400794b0  lea     r15, [rax+20h]
0x1400794b4  mov     rcx, r15; void *
0x1400794b7  lea     r8d, [rdx+40h]; Size
0x1400794bb  call    memset_0
0x1400794c0  test    cs:SkmiFlags, 400000h
0x1400794ca  jz      short loc_140079503
0x1400794cc  mov     rcx, gs:8; FramesToSkip
0x1400794d5  test    rcx, rcx
0x1400794d8  jz      short loc_140079503
0x1400794da  lea     r9, [rbp+70h+BackTraceHash]; BackTraceHash
0x1400794e1  mov     r8, r15; BackTrace
0x1400794e4  mov     edx, 8; FramesToCapture
0x1400794e9  call    RtlCaptureStackBackTrace
0x1400794ee  test    ax, ax
0x1400794f1  jnz     short loc_140079503
0x1400794f3  mov     rax, [rbp+78h]
0x1400794f7  mov     [r13+28h], rax
0x1400794fb  call    SkmiGetInstructionPointer
0x140079500  mov     [r15], rax
0x140079503  xor     r15d, r15d
0x140079506  mov     rax, rdi
0x140079509  mov     rcx, 0FFFFF6FB7DBED000h
0x140079513  cmp     rsi, rcx
0x140079516  jb      short loc_140079579
0x140079518  mov     rcx, 0FFFFF6FB7DBED800h
0x140079522  cmp     rsi, rcx
0x140079525  jnb     short loc_140079579
0x140079527  mov     rcx, gs:8
0x140079530  test    rcx, rcx
0x140079533  jz      short loc_14007953B
0x140079535  mov     rdx, [rcx+50h]
0x140079539  jmp     short loc_14007953E
0x14007953b  mov     rdx, r15
0x14007953e  mov     r8, [rdx+0E8h]
0x140079545  test    r8, r8
0x140079548  jz      short loc_140079579
0x14007954a  mov     edx, cs:SkiKvaShadowMode
0x140079550  mov     rcx, rsi
0x140079553  sar     rcx, 3
0x140079557  and     ecx, 1FFh
0x14007955d  mov     [r8+rcx*8], rdi
0x140079561  cmp     edx, 2
0x140079564  jz      short loc_140079579
0x140079566  test    dil, 1
0x14007956a  jz      short loc_140079579
0x14007956c  mov     rcx, 8000000000000000h
0x140079576  or      rax, rcx
0x140079579  shr     rbx, 0Ch
0x14007957d  mov     rcx, 0FFFFFFFFFFh
0x140079587  and     rcx, rbx; BugCheckParameter3
0x14007958a  mov     [rsi], rax
0x14007958d  call    SkmiDecrementPageReferenceCount
0x140079592  inc     r12d
0x140079595  add     rsi, 8
0x140079599  mov     eax, r12d
0x14007959c  cmp     rax, r14
0x14007959f  jb      loc_14007948B
0x1400795a5  mov     rbx, [rbp+70h+arg_8]
0x1400795ac  cmp     [rbp+70h+var_3C], r15b
0x1400795b0  jz      short loc_1400795BE
0x1400795b2  mov     cl, [rbp+70h+var_3B]
0x1400795b5  xor     edx, edx
0x1400795b7  call    SkeFlushEntireTb
0x1400795bc  jmp     short loc_1400795D6
0x1400795be  mov     r8d, [rbp+70h+var_40]
0x1400795c2  test    r8d, r8d
0x1400795c5  jz      short loc_1400795D6
0x1400795c7  mov     cl, [rbp+70h+var_3B]
0x1400795ca  lea     r9, [rsp+170h+var_140]
0x1400795cf  xor     edx, edx
0x1400795d1  call    SkeFlushRangeListTb
0x1400795d6  shl     r14, 0Ch
0x1400795da  mov     rcx, rbx
0x1400795dd  mov     rdx, r14
0x1400795e0  call    SkmmFreeReservedMapping
0x1400795e5  mov     rbx, [rsp+170h+arg_10]
0x1400795ed  add     rsp, 140h
0x1400795f4  pop     r15
0x1400795f6  pop     r14
0x1400795f8  pop     r13
0x1400795fa  pop     r12
0x1400795fc  pop     rdi
0x1400795fd  pop     rsi
0x1400795fe  pop     rbp
0x1400795ff  retn
```
