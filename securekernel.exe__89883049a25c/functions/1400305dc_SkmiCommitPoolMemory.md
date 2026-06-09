# SkmiCommitPoolMemory

- ea: `0x1400305dc`
- end: `0x140030a53`
- name: `SkmiCommitPoolMemory`
- size: `1143`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1400695d8`

## callees

- `0x140003780`
- `0x140009890`
- `0x140020360`
- `0x140020424`
- `0x1400272a0`
- `0x14002b534`
- `0x14002fe88`
- `0x1400305dc`
- `0x140030a5c`
- `0x140030f10`
- `0x140068c2c`
- `0x140081290`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmiCommitPoolMemory(__int64 a1, unsigned __int64 a2, unsigned __int64 a3, int a4)
{
  unsigned __int64 v7; // r15
  __int64 v8; // r14
  __int64 result; // rax
  unsigned __int64 v10; // rsi
  unsigned __int64 v11; // rbx
  bool v12; // cf
  int SecurePool; // ebx
  __int64 v14; // r8
  unsigned __int64 v15; // rbx
  signed __int64 v16; // r15
  signed __int64 v17; // r14
  __int64 DataTraceEntry; // rcx
  signed __int64 v19; // r9
  signed __int64 v20; // rax
  __int64 PteTrace; // rax
  PVOID *v22; // r12
  PVOID StackBase; // rcx
  __int64 v24; // rdx
  unsigned __int64 v25; // rcx
  __int64 v26; // rax
  __int64 v27; // r15
  PVOID *v28; // r14
  PVOID v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // rcx
  unsigned __int64 v32; // rax
  _QWORD *v33; // rcx
  __int64 v34; // rdx
  int v35; // edx
  __int64 v36; // rcx
  __int64 v37; // [rsp+30h] [rbp-D0h]
  __int64 v38; // [rsp+38h] [rbp-C8h]
  __int64 v39; // [rsp+40h] [rbp-C0h]
  _BYTE v40[256]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v41; // [rsp+150h] [rbp+50h]
  char v42; // [rsp+154h] [rbp+54h]
  char v43; // [rsp+155h] [rbp+55h]
  _UNKNOWN *retaddr; // [rsp+198h] [rbp+98h]
  unsigned __int64 BackTraceHash; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned __int64 v46; // [rsp+1B0h] [rbp+B0h]
  int v47; // [rsp+1B8h] [rbp+B8h]

  v47 = a4;
  memset_0(v40, 0, 0x108u);
  if ( (*(_DWORD *)(a1 + 4) & 2) != 0 )
  {
    v7 = a2 + *(_QWORD *)(a1 + 56);
    v8 = ((v7 >> 9) & 0x7FFFFFFFF8LL) - 0xA0000000000LL;
    result = SkmiExpandSecurePoolNtes(v8, a3 >> 12);
    if ( (int)result < 0 )
      return result;
  }
  else
  {
    v7 = 0;
    v8 = 0;
  }
  v10 = ((a2 >> 9) & 0x7FFFFFFFF8LL) - 0x98000000000LL;
  v11 = v10 + 8 * ((a3 >> 12) - 1);
  v46 = v11;
  v39 = ((v10 >> 9) & 0x7FFFFFFFF8LL) - 0x98000000000LL;
  v38 = ((v11 >> 9) & 0x7FFFFFFFF8LL) - 0x98000000000LL;
  result = SkmiReferencePoolPages(
             a1,
             (unsigned int)(v10 >> 9) & 0xFFFFFFF8,
             (unsigned int)(v11 >> 9) & 0xFFFFFFF8,
             0,
             3);
  if ( (int)result >= 0 )
  {
    v12 = v47 != 0;
    v47 = -v47;
    SecurePool = SkmiReferencePoolPages(a1, v10, v11, v8, v12 ? 2 : 0);
    if ( SecurePool >= 0 )
    {
      if ( (*(_DWORD *)(a1 + 4) & 2) != 0 && (SecurePool = SkmiAllocateSecurePool(v7, a3, v8), SecurePool < 0) )
      {
        SkmiDereferencePoolPages(a1, v10, v46, v8, 0);
      }
      else
      {
        v15 = ((unsigned __int64)(word_140156D90 & 1) << 8) | 0x8000000000000063uLL;
        while ( v10 <= v46 )
        {
          _m_prefetchw((const void *)v10);
LABEL_12:
          v16 = *(_QWORD *)v10;
          BackTraceHash = v16;
          LOBYTE(v17) = v16;
          while ( (v16 & 1) == 0 )
          {
            if ( (v16 & 2) == 0 )
            {
              _mm_pause();
              goto LABEL_12;
            }
            DataTraceEntry = SkmiAllocateDataTraceEntry(0, v10, v14, v16 & 0xFFFFFFFFFFFFFFFDuLL);
            v20 = _InterlockedCompareExchange64((volatile signed __int64 *)v10, v19, v16);
            v17 = v20;
            if ( DataTraceEntry )
            {
              if ( v20 == v16 )
              {
                PteTrace = SkmiGetPteTrace(DataTraceEntry, v10, 0, v19, v16);
                v37 = PteTrace;
                if ( PteTrace )
                {
                  v22 = (PVOID *)(PteTrace + 32);
                  memset_0((void *)(PteTrace + 32), 0, 0x40u);
                  if ( (SkmiFlags & 0x400000) != 0 )
                  {
                    StackBase = KeGetPcr()->NtTib.StackBase;
                    if ( StackBase )
                    {
                      if ( !RtlCaptureStackBackTrace((ULONG)StackBase, 8u, v22, (PULONG)&BackTraceHash) )
                      {
                        *(_QWORD *)(v37 + 40) = retaddr;
                        *v22 = (PVOID)SkmiGetInstructionPointer(v37, v24);
                        BackTraceHash = v17;
                        break;
                      }
                    }
                  }
                }
              }
            }
            BackTraceHash = v17;
            if ( v17 == v16 )
              break;
            v16 = v17;
          }
          if ( (v17 & 1) == 0 )
          {
            SKMI_UNSWIZZLE_INVALID_PTE(&BackTraceHash);
            v25 = BackTraceHash;
            *(_QWORD *)(8 * ((BackTraceHash >> 12) & 0xFFFFFFFFFFLL) - 0x180000000000LL) &= 0xFFFFF00000000000uLL;
            v15 = v25 & 0xFFFFFFFFFF000LL | v15 & 0xFFF0000000000FFFuLL;
            v26 = SkmiGetPteTrace(0, v10, 0, v15, *(_QWORD *)v10);
            v27 = v26;
            if ( v26 )
            {
              v28 = (PVOID *)(v26 + 32);
              memset_0((void *)(v26 + 32), 0, 0x40u);
              if ( (SkmiFlags & 0x400000) != 0 )
              {
                v29 = KeGetPcr()->NtTib.StackBase;
                if ( v29 )
                {
                  if ( !RtlCaptureStackBackTrace((ULONG)v29, 8u, v28, (PULONG)&BackTraceHash) )
                  {
                    *(_QWORD *)(v27 + 40) = retaddr;
                    *v28 = (PVOID)SkmiGetInstructionPointer(v31, v30);
                  }
                }
              }
            }
            v32 = v15;
            if ( v10 >= 0xFFFFF6FB7DBED000uLL && v10 < 0xFFFFF6FB7DBED800uLL )
            {
              v33 = KeGetPcr()->NtTib.StackBase;
              v34 = v33 ? v33[10] : 0LL;
              v14 = *(_QWORD *)(v34 + 232);
              if ( v14 )
              {
                v35 = SkiKvaShadowMode;
                *(_QWORD *)(v14 + 8 * (((__int64)v10 >> 3) & 0x1FF)) = v15;
                if ( v35 != 2 && (v15 & 1) != 0 )
                  v32 = v15 | 0x8000000000000000uLL;
              }
            }
            *(_QWORD *)v10 = v32;
          }
          v10 += 8LL;
        }
        SecurePool = 0;
      }
    }
    v43 = -1;
    SkmiDereferencePoolPages(a1, v39, v38, 0, (__int64)v40);
    if ( v42 )
    {
      LOBYTE(v36) = v43;
      SkeFlushEntireTb(v36, 0);
    }
    else if ( v41 )
    {
      LOBYTE(v36) = v43;
      SkeFlushRangeListTb(v36, 0, v41, v40);
    }
    return (unsigned int)SecurePool;
  }
  return result;
}

```

## disassembly

```asm
0x1400305dc  mov     [rsp-8+arg_8], rbx
0x1400305e1  mov     [rsp-8+arg_18], r9d
0x1400305e6  push    rbp
0x1400305e7  push    rsi
0x1400305e8  push    rdi
0x1400305e9  push    r12
0x1400305eb  push    r13
0x1400305ed  push    r14
0x1400305ef  push    r15
0x1400305f1  lea     rbp, [rsp-60h]
0x1400305f6  sub     rsp, 160h
0x1400305fd  mov     r12, r8
0x140030600  mov     rsi, rdx
0x140030603  mov     r13, rcx
0x140030606  xor     edx, edx; Val
0x140030608  mov     r8d, 108h; Size
0x14003060e  lea     rcx, [rsp+190h+var_140]; void *
0x140030613  call    memset_0
0x140030618  mov     eax, [r13+4]
0x14003061c  mov     rbx, r12
0x14003061f  shr     rbx, 0Ch
0x140030623  mov     r9, 7FFFFFFFF8h
0x14003062d  test    al, 2
0x14003062f  jz      short loc_140030670
0x140030631  mov     r15, [r13+38h]
0x140030635  add     r15, rsi
0x140030638  mov     r14, r15
0x14003063b  shr     r14, 9
0x14003063f  and     r14, r9
0x140030642  mov     rcx, 0FFFFF60000000000h
0x14003064c  add     r14, rcx
0x14003064f  mov     rdx, rbx
0x140030652  mov     rcx, r14
0x140030655  call    SkmiExpandSecurePoolNtes
0x14003065a  xor     edi, edi
0x14003065c  test    eax, eax
0x14003065e  js      loc_140030A37
0x140030664  mov     r9, 7FFFFFFFF8h
0x14003066e  jmp     short loc_140030678
0x140030670  xor     edi, edi
0x140030672  mov     r15d, edi
0x140030675  mov     r14d, edi
0x140030678  shr     rsi, 9
0x14003067c  and     rsi, r9
0x14003067f  mov     r8, 0FFFFF68000000000h
0x140030689  mov     rax, r8
0x14003068c  add     rsi, rax
0x14003068f  dec     rbx
0x140030692  mov     rdx, rsi
0x140030695  shr     rdx, 9
0x140030699  and     rdx, r9
0x14003069c  lea     rbx, [rsi+rbx*8]
0x1400306a0  mov     [rbp+90h+arg_10], rbx
0x1400306a7  mov     rax, r8
0x1400306aa  mov     rcx, rbx
0x1400306ad  add     rdx, rax
0x1400306b0  shr     rcx, 9
0x1400306b4  and     rcx, r9
0x1400306b7  mov     [rsp+190h+var_150], rdx
0x1400306bc  mov     rax, r8
0x1400306bf  add     rax, rcx
0x1400306c2  mov     dword ptr [rsp+190h+var_170], 3
0x1400306ca  mov     r8, rax
0x1400306cd  mov     [rsp+190h+var_158], rax
0x1400306d2  xor     r9d, r9d
0x1400306d5  mov     rcx, r13
0x1400306d8  call    SkmiReferencePoolPages
0x1400306dd  test    eax, eax
0x1400306df  js      loc_140030A37
0x1400306e5  neg     [rbp+90h+arg_18]
0x1400306eb  mov     r9, r14
0x1400306ee  mov     r8, rbx
0x1400306f1  mov     rdx, rsi
0x1400306f4  sbb     eax, eax
0x1400306f6  mov     rcx, r13
0x1400306f9  and     eax, 2
0x1400306fc  mov     dword ptr [rsp+190h+var_170], eax
0x140030700  call    SkmiReferencePoolPages
0x140030705  mov     ebx, eax
0x140030707  test    eax, eax
0x140030709  js      loc_1400309E1
0x14003070f  mov     eax, [r13+4]
0x140030713  test    al, 2
0x140030715  jz      short loc_14003074A
0x140030717  mov     r8, r14
0x14003071a  mov     rdx, r12
0x14003071d  mov     rcx, r15
0x140030720  call    SkmiAllocateSecurePool
0x140030725  mov     ebx, eax
0x140030727  test    eax, eax
0x140030729  jns     short loc_14003074A
0x14003072b  mov     r8, [rbp+90h+arg_10]
0x140030732  mov     r9, r14
0x140030735  mov     rdx, rsi
0x140030738  mov     [rsp+190h+var_170], rdi
0x14003073d  mov     rcx, r13
0x140030740  call    SkmiDereferencePoolPages
0x140030745  jmp     loc_1400309E1
0x14003074a  movzx   ebx, byte ptr cs:word_140156D90
0x140030751  mov     rax, 8000000000000063h
0x14003075b  and     ebx, 1
0x14003075e  shl     rbx, 8
0x140030762  or      rbx, rax
0x140030765  jmp     loc_1400309D2
0x14003076a  prefetchw byte ptr [rsi]
0x14003076d  mov     r15, [rsi]
0x140030770  mov     [rbp+90h+BackTraceHash], r15
0x140030777  mov     r14, r15
0x14003077a  test    r15b, 1
0x14003077e  jnz     loc_140030851
0x140030784  test    r15b, 2
0x140030788  jz      loc_14003082A
0x14003078e  mov     r9, r15
0x140030791  mov     rdx, rsi
0x140030794  and     r9, 0FFFFFFFFFFFFFFFDh
0x140030798  xor     ecx, ecx
0x14003079a  call    SkmiAllocateDataTraceEntry
0x14003079f  mov     rcx, rax
0x1400307a2  mov     rax, r15
0x1400307a5  lock cmpxchg [rsi], r9
0x1400307aa  mov     r14, rax
0x1400307ad  test    rcx, rcx
0x1400307b0  jz      short loc_140030816
0x1400307b2  cmp     rax, r15
0x1400307b5  jnz     short loc_140030816
0x1400307b7  xor     r8d, r8d
0x1400307ba  mov     [rsp+190h+var_170], r15
0x1400307bf  mov     rdx, rsi
0x1400307c2  call    SkmiGetPteTrace
0x1400307c7  mov     [rsp+190h+var_160], rax
0x1400307cc  test    rax, rax
0x1400307cf  jz      short loc_140030816
0x1400307d1  xor     edx, edx; Val
0x1400307d3  lea     r12, [rax+20h]
0x1400307d7  mov     rcx, r12; void *
0x1400307da  lea     r8d, [rdx+40h]; Size
0x1400307de  call    memset_0
0x1400307e3  test    cs:SkmiFlags, 400000h
0x1400307ed  jz      short loc_140030816
0x1400307ef  mov     rcx, gs:8; FramesToSkip
0x1400307f8  test    rcx, rcx
0x1400307fb  jz      short loc_140030816
0x1400307fd  lea     r9, [rbp+90h+BackTraceHash]; BackTraceHash
0x140030804  mov     r8, r12; BackTrace
0x140030807  mov     edx, 8; FramesToCapture
0x14003080c  call    RtlCaptureStackBackTrace
0x140030811  test    ax, ax
0x140030814  jz      short loc_140030831
0x140030816  mov     [rbp+90h+BackTraceHash], r14
0x14003081d  cmp     r14, r15
0x140030820  jz      short loc_140030851
0x140030822  mov     r15, r14
0x140030825  jmp     loc_14003077A
0x14003082a  pause
0x14003082c  jmp     loc_14003076D
0x140030831  mov     rax, [rbp+98h]
0x140030838  mov     rcx, [rsp+190h+var_160]
0x14003083d  mov     [rcx+28h], rax
0x140030841  call    SkmiGetInstructionPointer
0x140030846  mov     [r12], rax
0x14003084a  mov     [rbp+90h+BackTraceHash], r14
0x140030851  test    r14b, 1
0x140030855  jnz     loc_1400309CE
0x14003085b  lea     rcx, [rbp+90h+BackTraceHash]
0x140030862  call    SKMI_UNSWIZZLE_INVALID_PTE
0x140030867  mov     rcx, [rbp+90h+BackTraceHash]
0x14003086e  mov     rax, 0FFFFFFFFFFh
0x140030878  mov     r8, rcx
0x14003087b  shr     r8, 0Ch
0x14003087f  and     r8, rax
0x140030882  mov     rdx, 0FFFFEFFFFFFFFFFFh
0x14003088c  mov     r9, 0FFFFE80000000000h
0x140030896  mov     rax, r9
0x140030899  sub     rdx, rax
0x14003089c  sar     rdx, 3
0x1400308a0  cmp     r8, rdx
0x1400308a3  ja      loc_140030A16
0x1400308a9  mov     rax, r9
0x1400308ac  mov     rax, [rax+r8*8]
0x1400308b0  mov     rdx, 0FFFFF00000000000h
0x1400308ba  and     rax, rdx
0x1400308bd  mov     rdx, r9
0x1400308c0  mov     [rdx+r8*8], rax
0x1400308c4  mov     rax, 0FFF0000000000FFFh
0x1400308ce  and     rbx, rax
0x1400308d1  xor     r8d, r8d
0x1400308d4  mov     rax, 0FFFFFFFFFF000h
0x1400308de  mov     rdx, rsi
0x1400308e1  and     rcx, rax
0x1400308e4  mov     rax, [rsi]
0x1400308e7  or      rbx, rcx
0x1400308ea  mov     [rsp+190h+var_170], rax
0x1400308ef  mov     r9, rbx
0x1400308f2  xor     ecx, ecx
0x1400308f4  call    SkmiGetPteTrace
0x1400308f9  mov     r15, rax
0x1400308fc  test    rax, rax
0x1400308ff  jz      short loc_140030959
0x140030901  xor     edx, edx; Val
0x140030903  lea     r14, [rax+20h]
0x140030907  mov     rcx, r14; void *
0x14003090a  lea     r8d, [rdx+40h]; Size
0x14003090e  call    memset_0
0x140030913  test    cs:SkmiFlags, 400000h
0x14003091d  jz      short loc_140030959
0x14003091f  mov     rcx, gs:8; FramesToSkip
0x140030928  test    rcx, rcx
0x14003092b  jz      short loc_140030959
0x14003092d  lea     r9, [rbp+90h+BackTraceHash]; BackTraceHash
0x140030934  mov     r8, r14; BackTrace
0x140030937  mov     edx, 8; FramesToCapture
0x14003093c  call    RtlCaptureStackBackTrace
0x140030941  test    ax, ax
0x140030944  jnz     short loc_140030959
0x140030946  mov     rax, [rbp+98h]
0x14003094d  mov     [r15+28h], rax
0x140030951  call    SkmiGetInstructionPointer
0x140030956  mov     [r14], rax
0x140030959  mov     rax, rbx
0x14003095c  mov     rcx, 0FFFFF6FB7DBED000h
0x140030966  cmp     rsi, rcx
0x140030969  jb      short loc_1400309CB
0x14003096b  mov     rcx, 0FFFFF6FB7DBED800h
0x140030975  cmp     rsi, rcx
0x140030978  jnb     short loc_1400309CB
0x14003097a  mov     rcx, gs:8
0x140030983  test    rcx, rcx
0x140030986  jz      short loc_14003098E
0x140030988  mov     rdx, [rcx+50h]
0x14003098c  jmp     short loc_140030991
0x14003098e  mov     rdx, rdi
0x140030991  mov     r8, [rdx+0E8h]
0x140030998  test    r8, r8
0x14003099b  jz      short loc_1400309CB
0x14003099d  mov     edx, cs:SkiKvaShadowMode
0x1400309a3  mov     rcx, rsi
0x1400309a6  sar     rcx, 3
0x1400309aa  and     ecx, 1FFh
0x1400309b0  mov     [r8+rcx*8], rbx
0x1400309b4  cmp     edx, 2
0x1400309b7  jz      short loc_1400309CB
0x1400309b9  test    bl, 1
0x1400309bc  jz      short loc_1400309CB
0x1400309be  mov     rcx, 8000000000000000h
0x1400309c8  or      rax, rcx
0x1400309cb  mov     [rsi], rax
0x1400309ce  add     rsi, 8
0x1400309d2  cmp     rsi, [rbp+90h+arg_10]
0x1400309d9  jbe     loc_14003076A
0x1400309df  mov     ebx, edi
0x1400309e1  mov     r8, [rsp+190h+var_158]
0x1400309e6  lea     rax, [rsp+190h+var_140]
0x1400309eb  mov     rdx, [rsp+190h+var_150]
0x1400309f0  xor     r9d, r9d
0x1400309f3  mov     rcx, r13
0x1400309f6  mov     [rsp+190h+var_170], rax
0x1400309fb  mov     [rbp+90h+var_3B], 0FFh
0x1400309ff  call    SkmiDereferencePoolPages
0x140030a04  cmp     [rbp+90h+var_3C], dil
0x140030a08  jz      short loc_140030A1D
0x140030a0a  mov     cl, [rbp+90h+var_3B]
0x140030a0d  xor     edx, edx
0x140030a0f  call    SkeFlushEntireTb
0x140030a14  jmp     short loc_140030A35
0x140030a16  mov     ecx, 3Fh ; '?'
0x140030a1b  int     29h; Win8: RtlFailFast(ecx)
0x140030a1d  mov     r8d, [rbp+90h+var_40]
0x140030a21  test    r8d, r8d
0x140030a24  jz      short loc_140030A35
0x140030a26  mov     cl, [rbp+90h+var_3B]
0x140030a29  lea     r9, [rsp+190h+var_140]
0x140030a2e  xor     edx, edx
0x140030a30  call    SkeFlushRangeListTb
0x140030a35  mov     eax, ebx
0x140030a37  mov     rbx, [rsp+190h+arg_8]
0x140030a3f  add     rsp, 160h
0x140030a46  pop     r15
0x140030a48  pop     r14
0x140030a4a  pop     r13
0x140030a4c  pop     r12
0x140030a4e  pop     rdi
0x140030a4f  pop     rsi
0x140030a50  pop     rbp
0x140030a51  retn
```
