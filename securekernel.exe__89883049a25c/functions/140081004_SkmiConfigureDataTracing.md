# SkmiConfigureDataTracing

- ea: `0x140081004`
- end: `0x140081288`
- name: `SkmiConfigureDataTracing`
- size: `644`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14005a0f8`

## callees

- `0x140003780`
- `0x140014740`
- `0x14002467c`
- `0x140025694`
- `0x140027ac0`
- `0x14002b534`
- `0x140081004`
- `0x140081290`
- `0x1400f9a80`

## pseudocode

```c
__int64 SkmiConfigureDataTracing()
{
  _QWORD *v0; // rax
  unsigned __int64 v1; // rdx
  _QWORD *v2; // rcx
  _QWORD **v3; // rax
  _QWORD *v4; // r8
  _QWORD *v5; // rax
  unsigned __int64 v6; // rdx
  __int64 v7; // rsi
  unsigned int v8; // ecx
  unsigned int v9; // ebx
  __int64 result; // rax
  __int64 v11; // rdi
  unsigned __int64 v12; // r14
  unsigned int v13; // ebp
  unsigned __int64 v14; // rbx
  __int64 v15; // r15
  __int64 PteTrace; // rax
  __int64 v17; // r13
  PVOID *v18; // r12
  PVOID StackBase; // rcx
  __int64 v20; // rdx
  __int64 v21; // rcx
  _QWORD *v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rdx
  int v25; // ecx
  __int64 v26; // rdi
  _UNKNOWN *retaddr; // [rsp+68h] [rbp+0h]
  ULONG BackTraceHash; // [rsp+70h] [rbp+8h] BYREF
  unsigned __int64 v29; // [rsp+78h] [rbp+10h] BYREF

  v0 = (_QWORD *)SkmiMemoryRangeTree;
  v1 = 0;
  v2 = 0;
  while ( v0 )
  {
    v2 = v0;
    v0 = (_QWORD *)*v0;
  }
  while ( v2 )
  {
    v1 += v2[4];
    v3 = (_QWORD **)v2[1];
    if ( v3 )
    {
      v4 = *v3;
      if ( *v3 )
      {
        do
        {
          v2 = v4;
          v4 = (_QWORD *)*v4;
        }
        while ( v4 );
      }
      else
      {
        v2 = (_QWORD *)v2[1];
      }
    }
    else
    {
      do
      {
        v5 = v2;
        v2 = (_QWORD *)(v2[2] & 0xFFFFFFFFFFFFFFFCuLL);
      }
      while ( v2 && (_QWORD *)*v2 != v5 );
    }
  }
  v6 = v1 >> 4;
  LODWORD(v7) = 0x100000;
  if ( v6 <= 0x100000 )
  {
    LODWORD(v7) = 0x2000;
    if ( v6 >= 0x2000 )
    {
      _BitScanReverse(&v8, v6);
      v7 = 1LL << v8;
    }
  }
  v9 = (((96 * (_DWORD)v7) & 0xFFF) != 0) + ((unsigned int)(96 * v7) >> 12);
  result = SkmiAllocateSystemPtes((__int64)&SkmiSystemPtes, v9);
  v11 = result;
  if ( result )
  {
    v12 = v9;
    v13 = 0;
    v29 = ((unsigned __int64)(word_140156D90 & 1) << 8) | 0x8000000000000063uLL;
    while ( 1 )
    {
      if ( v13 >= v12 )
      {
        v26 = v11 << 25 >> 16;
        result = (__int64)memset_0((void *)v26, 0, v12 << 12);
        SkmiDataTraceSize = v7;
        SkmiDataTraces = v26;
        return result;
      }
      if ( !(unsigned int)SkmiAllocateSinglePage(0, &v29) )
        break;
      v14 = v29;
      v15 = v11 + 8LL * v13;
      PteTrace = SkmiGetPteTrace(0, (unsigned int)v11 + 8 * v13, 0, v29, *(_QWORD *)v15);
      v17 = PteTrace;
      if ( PteTrace )
      {
        v18 = (PVOID *)(PteTrace + 32);
        memset_0((void *)(PteTrace + 32), 0, 0x40u);
        if ( (SkmiFlags & 0x400000) != 0 )
        {
          StackBase = KeGetPcr()->NtTib.StackBase;
          if ( StackBase )
          {
            if ( !RtlCaptureStackBackTrace((ULONG)StackBase, 8u, v18, &BackTraceHash) )
            {
              *(_QWORD *)(v17 + 40) = retaddr;
              *v18 = (PVOID)SkmiGetInstructionPointer(v21, v20);
            }
          }
        }
      }
      if ( (unsigned __int64)v15 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)v15 < 0xFFFFF6FB7DBED800uLL )
      {
        v22 = KeGetPcr()->NtTib.StackBase;
        if ( v22 )
          v23 = v22[10];
        else
          v23 = 0;
        v24 = *(_QWORD *)(v23 + 232);
        if ( v24 )
        {
          v25 = SkiKvaShadowMode;
          *(_QWORD *)(v24 + 8 * ((v15 >> 3) & 0x1FF)) = v14;
          if ( v25 != 2 && (v14 & 1) != 0 )
            v14 |= 0x8000000000000000uLL;
        }
      }
      *(_QWORD *)v15 = v14;
      ++v13;
    }
    if ( v13 )
      SkmiFreeMappedPages(v11, v13);
    return RtlInterlockedClearBitRunEx(&qword_140156F70, (unsigned int)((v11 - SkmiSystemPtes) >> 3), v12);
  }
  return result;
}

```

## disassembly

```asm
0x140081004  mov     [rsp+arg_10], rbx
0x140081009  push    rbp
0x14008100a  push    rsi
0x14008100b  push    rdi
0x14008100c  push    r12
0x14008100e  push    r13
0x140081010  push    r14
0x140081012  push    r15
0x140081014  sub     rsp, 30h
0x140081018  mov     rax, cs:SkmiMemoryRangeTree
0x14008101f  xor     r12d, r12d
0x140081022  mov     edx, r12d
0x140081025  mov     ecx, r12d
0x140081028  jmp     short loc_140081030
0x14008102a  mov     rcx, rax
0x14008102d  mov     rax, [rax]
0x140081030  test    rax, rax
0x140081033  jnz     short loc_14008102A
0x140081035  jmp     short loc_140081073
0x140081037  add     rdx, [rcx+20h]
0x14008103b  mov     rax, [rcx+8]
0x14008103f  test    rax, rax
0x140081042  jz      short loc_140081066
0x140081044  mov     r8, [rax]
0x140081047  test    r8, r8
0x14008104a  jz      short loc_14008105C
0x14008104c  mov     rax, [r8]
0x14008104f  mov     rcx, r8
0x140081052  mov     r8, rax
0x140081055  test    rax, rax
0x140081058  jnz     short loc_14008104C
0x14008105a  jmp     short loc_140081073
0x14008105c  mov     rcx, rax
0x14008105f  jmp     short loc_140081073
0x140081061  cmp     [rcx], rax
0x140081064  jz      short loc_140081073
0x140081066  mov     rax, rcx
0x140081069  mov     rcx, [rcx+10h]
0x14008106d  and     rcx, 0FFFFFFFFFFFFFFFCh
0x140081071  jnz     short loc_140081061
0x140081073  test    rcx, rcx
0x140081076  jnz     short loc_140081037
0x140081078  shr     rdx, 4
0x14008107c  mov     esi, 100000h
0x140081081  cmp     rdx, rsi
0x140081084  ja      short loc_14008109B
0x140081086  mov     esi, 2000h
0x14008108b  cmp     rdx, rsi
0x14008108e  jb      short loc_14008109B
0x140081090  bsr     ecx, edx
0x140081093  mov     esi, 1
0x140081098  shl     rsi, cl
0x14008109b  mov     eax, r12d
0x14008109e  lea     ecx, [rsi+rsi*2]
0x1400810a1  shl     ecx, 5
0x1400810a4  test    ecx, 0FFFh
0x1400810aa  setnz   al
0x1400810ad  shr     ecx, 0Ch
0x1400810b0  lea     ebx, [rax+rcx]
0x1400810b3  mov     edx, ebx
0x1400810b5  lea     rcx, SkmiSystemPtes
0x1400810bc  call    SkmiAllocateSystemPtes
0x1400810c1  mov     rdi, rax
0x1400810c4  test    rax, rax
0x1400810c7  jz      loc_14008126F
0x1400810cd  movzx   ecx, byte ptr cs:word_140156D90
0x1400810d4  mov     rax, 8000000000000063h
0x1400810de  and     ecx, 1
0x1400810e1  mov     r14d, ebx
0x1400810e4  shl     rcx, 8
0x1400810e8  mov     ebp, r12d
0x1400810eb  or      rcx, rax
0x1400810ee  mov     [rsp+68h+arg_8], rcx
0x1400810f3  mov     r15d, ebp
0x1400810f6  cmp     r15, r14
0x1400810f9  jnb     loc_140081238
0x1400810ff  lea     rdx, [rsp+68h+arg_8]
0x140081104  xor     ecx, ecx
0x140081106  call    SkmiAllocateSinglePage
0x14008110b  test    eax, eax
0x14008110d  jz      loc_14008120C
0x140081113  mov     rbx, [rsp+68h+arg_8]
0x140081118  lea     r15, [rdi+r15*8]
0x14008111c  mov     rax, [r15]
0x14008111f  mov     r9, rbx
0x140081122  xor     r8d, r8d
0x140081125  mov     [rsp+68h+var_48], rax
0x14008112a  mov     rdx, r15
0x14008112d  xor     ecx, ecx
0x14008112f  call    SkmiGetPteTrace
0x140081134  mov     r13, rax
0x140081137  test    rax, rax
0x14008113a  jz      short loc_140081194
0x14008113c  xor     edx, edx; Val
0x14008113e  lea     r12, [rax+20h]
0x140081142  mov     rcx, r12; void *
0x140081145  lea     r8d, [rdx+40h]; Size
0x140081149  call    memset_0
0x14008114e  test    cs:SkmiFlags, 400000h
0x140081158  jz      short loc_140081191
0x14008115a  mov     rcx, gs:8; FramesToSkip
0x140081163  test    rcx, rcx
0x140081166  jz      short loc_140081191
0x140081168  lea     r9, [rsp+68h+BackTraceHash]; BackTraceHash
0x14008116d  mov     r8, r12; BackTrace
0x140081170  mov     edx, 8; FramesToCapture
0x140081175  call    RtlCaptureStackBackTrace
0x14008117a  test    ax, ax
0x14008117d  jnz     short loc_140081191
0x14008117f  mov     rax, [rsp+68h]
0x140081184  mov     [r13+28h], rax
0x140081188  call    SkmiGetInstructionPointer
0x14008118d  mov     [r12], rax
0x140081191  xor     r12d, r12d
0x140081194  mov     rax, 0FFFFF6FB7DBED000h
0x14008119e  cmp     r15, rax
0x1400811a1  jb      short loc_140081202
0x1400811a3  mov     rax, 0FFFFF6FB7DBED800h
0x1400811ad  cmp     r15, rax
0x1400811b0  jnb     short loc_140081202
0x1400811b2  mov     rax, gs:8
0x1400811bb  test    rax, rax
0x1400811be  jz      short loc_1400811C6
0x1400811c0  mov     rcx, [rax+50h]
0x1400811c4  jmp     short loc_1400811C9
0x1400811c6  mov     rcx, r12
0x1400811c9  mov     rdx, [rcx+0E8h]
0x1400811d0  test    rdx, rdx
0x1400811d3  jz      short loc_140081202
0x1400811d5  mov     ecx, cs:SkiKvaShadowMode
0x1400811db  mov     rax, r15
0x1400811de  sar     rax, 3
0x1400811e2  and     eax, 1FFh
0x1400811e7  mov     [rdx+rax*8], rbx
0x1400811eb  cmp     ecx, 2
0x1400811ee  jz      short loc_140081202
0x1400811f0  test    bl, 1
0x1400811f3  jz      short loc_140081202
0x1400811f5  mov     rax, 8000000000000000h
0x1400811ff  or      rbx, rax
0x140081202  mov     [r15], rbx
0x140081205  inc     ebp
0x140081207  jmp     loc_1400810F3
0x14008120c  test    ebp, ebp
0x14008120e  jz      short loc_14008121A
0x140081210  mov     edx, ebp
0x140081212  mov     rcx, rdi
0x140081215  call    SkmiFreeMappedPages
0x14008121a  sub     rdi, cs:SkmiSystemPtes
0x140081221  lea     rcx, qword_140156F70
0x140081228  sar     rdi, 3
0x14008122c  mov     r8, r14
0x14008122f  mov     edx, edi
0x140081231  call    RtlInterlockedClearBitRunEx
0x140081236  jmp     short loc_14008126F
0x140081238  shl     rdi, 19h
0x14008123c  mov     rax, 0FFFFF68000000000h
0x140081246  shl     rax, 19h
0x14008124a  xor     edx, edx; Val
0x14008124c  sub     rdi, rax
0x14008124f  shl     r14, 0Ch
0x140081253  sar     rdi, 10h
0x140081257  mov     r8, r14; Size
0x14008125a  mov     rcx, rdi; void *
0x14008125d  call    memset_0
0x140081262  mov     cs:SkmiDataTraceSize, esi
0x140081268  mov     cs:SkmiDataTraces, rdi
0x14008126f  mov     rbx, [rsp+68h+arg_10]
0x140081277  add     rsp, 30h
0x14008127b  pop     r15
0x14008127d  pop     r14
0x14008127f  pop     r13
0x140081281  pop     r12
0x140081283  pop     rdi
0x140081284  pop     rsi
0x140081285  pop     rbp
0x140081286  retn
```
