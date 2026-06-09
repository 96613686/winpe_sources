# SkmmCreateSecureAllocation

- ea: `0x1400500b4`
- end: `0x1400502f5`
- name: `SkmmCreateSecureAllocation`
- size: `577`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140014dd0`

## callees

- `0x140002ef0`
- `0x140003780`
- `0x140014740`
- `0x140027ac0`
- `0x14002b534`
- `0x1400500b4`
- `0x140081290`
- `0x1400a0df8`
- `0x1400a18a0`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmmCreateSecureAllocation(unsigned __int64 a1, __int64 a2)
{
  unsigned __int64 v3; // rdi
  __int64 result; // rax
  __int64 v5; // r14
  __int64 SystemPtes; // rax
  __int64 v7; // rsi
  unsigned int Handle; // ebx
  unsigned __int64 v9; // rbx
  __int64 PteTrace; // rax
  __int64 v11; // rbp
  PVOID *v12; // r15
  PVOID StackBase; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  _QWORD *v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rdx
  int v19; // ecx
  _UNKNOWN *retaddr; // [rsp+68h] [rbp+0h]
  _OWORD *BackTraceHash; // [rsp+70h] [rbp+8h] BYREF
  unsigned __int64 v22; // [rsp+80h] [rbp+18h] BYREF

  BackTraceHash = 0;
  if ( !a1 )
    return 3221225485LL;
  v3 = (a1 >> 12) + ((a1 & 0xFFF) != 0);
  if ( v3 != (unsigned int)v3 )
    return 3221225485LL;
  result = SkobCreateObjectEx(0, (__int64)&SkmiSecureAllocationType, 0, &BackTraceHash);
  if ( (int)result >= 0 )
  {
    v5 = (__int64)BackTraceHash;
    *BackTraceHash = 0;
    *(_OWORD *)(v5 + 16) = 0;
    *(_QWORD *)(v5 + 16) = 0;
    SystemPtes = SkmiAllocateSystemPtes((__int64)&SkmiPagedPtes, v3);
    v7 = SystemPtes;
    if ( SystemPtes )
    {
      *(_QWORD *)(v5 + 8) = v3;
      *(_QWORD *)v5 = SystemPtes << 25 >> 16;
      v22 = ((unsigned __int64)(word_140156D90 & 1) << 8) | 0x8000000000000063uLL;
      while ( v3 )
      {
        if ( !(unsigned int)SkmiAllocateSinglePage(0, &v22) )
          goto LABEL_5;
        v9 = v22;
        PteTrace = SkmiGetPteTrace(0, v7, 0, v22, *(_QWORD *)v7);
        v11 = PteTrace;
        if ( PteTrace )
        {
          v12 = (PVOID *)(PteTrace + 32);
          memset_0((void *)(PteTrace + 32), 0, 0x40u);
          if ( (SkmiFlags & 0x400000) != 0 )
          {
            StackBase = KeGetPcr()->NtTib.StackBase;
            if ( StackBase )
            {
              if ( !RtlCaptureStackBackTrace((ULONG)StackBase, 8u, v12, (PULONG)&BackTraceHash) )
              {
                *(_QWORD *)(v11 + 40) = retaddr;
                *v12 = (PVOID)SkmiGetInstructionPointer(v15, v14);
              }
            }
          }
        }
        if ( (unsigned __int64)v7 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)v7 < 0xFFFFF6FB7DBED800uLL )
        {
          v16 = KeGetPcr()->NtTib.StackBase;
          if ( v16 )
            v17 = v16[10];
          else
            v17 = 0;
          v18 = *(_QWORD *)(v17 + 232);
          if ( v18 )
          {
            v19 = SkiKvaShadowMode;
            *(_QWORD *)(v18 + 8 * ((v7 >> 3) & 0x1FF)) = v9;
            if ( v19 != 2 && (v9 & 1) != 0 )
              v9 |= 0x8000000000000000uLL;
          }
        }
        *(_QWORD *)v7 = v9;
        v7 += 8;
        --v3;
      }
      memset_0(*(void **)v5, 0, *(_QWORD *)(v5 + 8) << 12);
      Handle = SkobCreateHandle(v5, 1, 0, a2);
    }
    else
    {
LABEL_5:
      Handle = -1073741670;
    }
    SkobDereferenceObject(v5);
    return Handle;
  }
  return result;
}

```

## disassembly

```asm
0x1400500b4  mov     [rsp+arg_8], rbx
0x1400500b9  push    rbp
0x1400500ba  push    rsi
0x1400500bb  push    rdi
0x1400500bc  push    r12
0x1400500be  push    r13
0x1400500c0  push    r14
0x1400500c2  push    r15
0x1400500c4  sub     rsp, 30h
0x1400500c8  xor     r13d, r13d
0x1400500cb  mov     r12, rdx
0x1400500ce  mov     [rsp+68h+BackTraceHash], r13
0x1400500d3  test    rcx, rcx
0x1400500d6  jz      loc_1400502DA
0x1400500dc  test    rcx, 0FFFh
0x1400500e3  mov     edi, r13d
0x1400500e6  setnz   dil
0x1400500ea  shr     rcx, 0Ch
0x1400500ee  add     rdi, rcx
0x1400500f1  mov     ebx, edi
0x1400500f3  cmp     rdi, rbx
0x1400500f6  jnz     loc_1400502DA
0x1400500fc  lea     r9, [rsp+68h+BackTraceHash]
0x140050101  xor     r8d, r8d
0x140050104  lea     rdx, SkmiSecureAllocationType
0x14005010b  xor     ecx, ecx
0x14005010d  call    SkobCreateObjectEx
0x140050112  test    eax, eax
0x140050114  js      loc_1400502DF
0x14005011a  mov     r14, [rsp+68h+BackTraceHash]
0x14005011f  lea     rcx, SkmiPagedPtes
0x140050126  xorps   xmm0, xmm0
0x140050129  mov     edx, ebx
0x14005012b  movups  xmmword ptr [r14], xmm0
0x14005012f  movups  xmmword ptr [r14+10h], xmm0
0x140050134  mov     [r14+10h], r13
0x140050138  call    SkmiAllocateSystemPtes
0x14005013d  mov     rsi, rax
0x140050140  test    rax, rax
0x140050143  jnz     short loc_14005014F
0x140050145  mov     ebx, 0C000009Ah
0x14005014a  jmp     loc_1400502CE
0x14005014f  mov     rcx, rax
0x140050152  mov     [r14+8], rdi
0x140050156  shl     rcx, 19h
0x14005015a  mov     rax, 0FFFFF68000000000h
0x140050164  shl     rax, 19h
0x140050168  sub     rcx, rax
0x14005016b  sar     rcx, 10h
0x14005016f  mov     [r14], rcx
0x140050172  mov     rcx, 8000000000000063h
0x14005017c  movzx   eax, byte ptr cs:word_140156D90
0x140050183  and     eax, 1
0x140050186  shl     rax, 8
0x14005018a  or      rax, rcx
0x14005018d  mov     [rsp+68h+arg_10], rax
0x140050195  test    rdi, rdi
0x140050198  jz      loc_1400502AA
0x14005019e  lea     rdx, [rsp+68h+arg_10]
0x1400501a6  xor     ecx, ecx
0x1400501a8  call    SkmiAllocateSinglePage
0x1400501ad  test    eax, eax
0x1400501af  jz      short loc_140050145
0x1400501b1  mov     rax, [rsi]
0x1400501b4  xor     r8d, r8d
0x1400501b7  mov     rbx, [rsp+68h+arg_10]
0x1400501bf  mov     rdx, rsi
0x1400501c2  mov     r9, rbx
0x1400501c5  mov     [rsp+68h+var_48], rax
0x1400501ca  xor     ecx, ecx
0x1400501cc  call    SkmiGetPteTrace
0x1400501d1  mov     rbp, rax
0x1400501d4  test    rax, rax
0x1400501d7  jz      short loc_14005022D
0x1400501d9  xor     edx, edx; Val
0x1400501db  lea     r15, [rax+20h]
0x1400501df  mov     rcx, r15; void *
0x1400501e2  lea     r8d, [rdx+40h]; Size
0x1400501e6  call    memset_0
0x1400501eb  test    cs:SkmiFlags, 400000h
0x1400501f5  jz      short loc_14005022D
0x1400501f7  mov     rcx, gs:8; FramesToSkip
0x140050200  test    rcx, rcx
0x140050203  jz      short loc_14005022D
0x140050205  lea     r9, [rsp+68h+BackTraceHash]; BackTraceHash
0x14005020a  mov     r8, r15; BackTrace
0x14005020d  mov     edx, 8; FramesToCapture
0x140050212  call    RtlCaptureStackBackTrace
0x140050217  test    ax, ax
0x14005021a  jnz     short loc_14005022D
0x14005021c  mov     rax, [rsp+68h]
0x140050221  mov     [rbp+28h], rax
0x140050225  call    SkmiGetInstructionPointer
0x14005022a  mov     [r15], rax
0x14005022d  mov     rax, 0FFFFF6FB7DBED000h
0x140050237  cmp     rsi, rax
0x14005023a  jb      short loc_14005029B
0x14005023c  mov     rax, 0FFFFF6FB7DBED800h
0x140050246  cmp     rsi, rax
0x140050249  jnb     short loc_14005029B
0x14005024b  mov     rax, gs:8
0x140050254  test    rax, rax
0x140050257  jz      short loc_14005025F
0x140050259  mov     rcx, [rax+50h]
0x14005025d  jmp     short loc_140050262
0x14005025f  mov     rcx, r13
0x140050262  mov     rdx, [rcx+0E8h]
0x140050269  test    rdx, rdx
0x14005026c  jz      short loc_14005029B
0x14005026e  mov     ecx, cs:SkiKvaShadowMode
0x140050274  mov     rax, rsi
0x140050277  sar     rax, 3
0x14005027b  and     eax, 1FFh
0x140050280  mov     [rdx+rax*8], rbx
0x140050284  cmp     ecx, 2
0x140050287  jz      short loc_14005029B
0x140050289  test    bl, 1
0x14005028c  jz      short loc_14005029B
0x14005028e  mov     rax, 8000000000000000h
0x140050298  or      rbx, rax
0x14005029b  mov     [rsi], rbx
0x14005029e  add     rsi, 8
0x1400502a2  dec     rdi
0x1400502a5  jmp     loc_140050195
0x1400502aa  mov     r8, [r14+8]
0x1400502ae  xor     edx, edx; Val
0x1400502b0  mov     rcx, [r14]; void *
0x1400502b3  shl     r8, 0Ch; Size
0x1400502b7  call    memset_0
0x1400502bc  mov     r9, r12
0x1400502bf  xor     r8d, r8d
0x1400502c2  mov     dl, 1
0x1400502c4  mov     rcx, r14
0x1400502c7  call    SkobCreateHandle
0x1400502cc  mov     ebx, eax
0x1400502ce  mov     rcx, r14
0x1400502d1  call    SkobDereferenceObject
0x1400502d6  mov     eax, ebx
0x1400502d8  jmp     short loc_1400502DF
0x1400502da  mov     eax, 0C000000Dh
0x1400502df  mov     rbx, [rsp+68h+arg_8]
0x1400502e4  add     rsp, 30h
0x1400502e8  pop     r15
0x1400502ea  pop     r14
0x1400502ec  pop     r13
0x1400502ee  pop     r12
0x1400502f0  pop     rdi
0x1400502f1  pop     rsi
0x1400502f2  pop     rbp
0x1400502f3  retn
```
