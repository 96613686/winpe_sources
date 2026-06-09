# SkAllocatePool

- ea: `0x14000f0f0`
- end: `0x14000f83c`
- name: `SkAllocatePool`
- size: `1868`
- prototype: `__int64 __fastcall(__int64, unsigned __int64)`
- caller_count: `167`
- callee_count: `12`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140012750`
- `0x140014dd0`
- `0x14001ce38`
- `0x14001e71c`
- `0x140020be0`
- `0x140021428`
- `0x1400280b0`
- `0x14002b5f4`
- `0x14002bfac`
- `0x14002dca8`
- `0x1400355f4`
- `0x140035d58`
- `0x140036ea8`
- `0x1400370c4`
- `0x140037398`
- `0x140037690`
- `0x140041954`
- `0x14004244c`
- `0x140044268`
- `0x140044c60`
- `0x140044d04`
- `0x140044db4`
- `0x1400455c4`
- `0x140045e4c`
- `0x140046628`
- `0x140047c98`
- `0x140048bfc`
- `0x140049388`
- `0x140049618`
- `0x140049bec`
- `0x14004a45c`
- `0x14004a890`
- `0x14004aa18`
- `0x14004bbe4`
- `0x14004bf74`
- `0x14004c54c`
- `0x14004c7b0`
- `0x14005896c`
- `0x140058d88`
- `0x14005c1e0`
- `0x14005cf30`
- `0x14005e710`
- `0x14005eda8`
- `0x14005f524`
- `0x14005f8b8`
- `0x14006011c`
- `0x1400603cc`
- `0x140061bb0`
- `0x140062334`
- `0x140062a88`

## callees

- `0x14000f0f0`
- `0x14000ffec`
- `0x140010e0c`
- `0x140029a24`
- `0x1400cb50c`
- `0x1400cdcb4`
- `0x1400cdf4c`
- `0x1400cff3c`
- `0x1400d0578`
- `0x1400d14c8`
- `0x1400d2634`
- `0x1400f3550`

## pseudocode

```c
__int64 __fastcall SkAllocatePool(__int64 a1, unsigned __int64 a2)
{
  __int64 v2; // rcx
  unsigned __int64 v3; // r14
  __int64 v5; // rsi
  int v6; // eax
  __int64 v7; // r12
  __int64 v8; // rbx
  unsigned __int64 v9; // rdi
  __int64 v10; // r8
  unsigned int v11; // r12d
  __int64 v12; // rax
  unsigned __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rax
  __int64 v16; // r9
  unsigned __int64 v17; // r9
  struct _EXCEPTION_REGISTRATION_RECORD *ExceptionList; // r10
  __int64 v19; // rdi
  unsigned int v20; // esi
  unsigned __int64 v21; // rcx
  unsigned __int64 v22; // rax
  __int64 v23; // rtt
  unsigned __int64 v24; // r8
  char v25; // cl
  _DWORD *v26; // r8
  __int64 v30; // r8
  __int64 Slow; // rdi
  __int16 v32; // ax
  int v33; // r15d
  signed __int64 v34; // rbx
  signed __int64 v35; // rax
  unsigned __int64 v36; // rbx
  unsigned int v37; // eax
  __int64 v38; // r11
  __int64 v39; // r11
  unsigned int v40; // ecx
  int v41; // r10d
  volatile signed __int64 *v42; // rdx
  signed __int64 v43; // r9
  __int64 v48; // r8
  unsigned __int64 v52; // rax
  unsigned int v53; // eax
  signed __int64 v56; // rcx
  signed __int64 v57; // r8
  signed __int64 v58; // rax
  unsigned int v59; // eax
  unsigned int v60; // r12d
  __int64 v61; // rdi
  bool v62; // cc
  unsigned int v63; // r12d
  __int16 v64; // ax
  unsigned __int64 v65; // rax
  char v66; // cl
  unsigned __int64 v67; // r8
  unsigned __int64 v68; // rdx
  unsigned __int64 v69; // rtt
  unsigned __int64 v70; // r8
  signed __int64 v71; // rax
  unsigned __int64 v72; // r9
  signed __int64 v73; // rax
  signed __int64 v74; // rtt
  signed __int64 v75; // rdx
  __int64 v76; // rcx
  __int64 v77; // r10
  int v79; // [rsp+30h] [rbp-78h]
  __int64 v80; // [rsp+40h] [rbp-68h]
  unsigned __int16 v81; // [rsp+44h] [rbp-64h]
  int v82; // [rsp+48h] [rbp-60h]
  __int64 v83; // [rsp+58h] [rbp-50h]
  unsigned __int64 *v84; // [rsp+60h] [rbp-48h]
  __int64 v85; // [rsp+68h] [rbp-40h]
  int v86; // [rsp+B0h] [rbp+8h]
  unsigned __int8 v87; // [rsp+B0h] [rbp+8h]
  unsigned int v88; // [rsp+C8h] [rbp+20h]
  signed __int64 v89; // [rsp+C8h] [rbp+20h]

  v2 = qword_14015A9A0;
  v3 = a2;
  v83 = qword_14015A9A0;
  if ( a2 <= 1 )
    v3 = 1;
  if ( v3 >= *(unsigned __int16 *)(qword_14015A9A0 + 1028) )
  {
    v11 = v3;
    goto LABEL_12;
  }
  v5 = qword_14015A9A0 + 960;
  v6 = v3 + 2;
  if ( (_DWORD)a2 == (_DWORD)v3 )
    v6 = v3;
  v7 = (unsigned int)*((unsigned __int8 *)RtlpLfhBucketIndexMap + ((unsigned __int64)(unsigned int)(v6 + 15) >> 4)) - 1;
  v8 = *((_QWORD *)&KeGetPcr()->NtTib.ExceptionList[182].Handler
       + (unsigned int)(*(_DWORD *)(qword_14015A9A0 + 1036) - 1));
  if ( !v8 )
    v8 = RtlpHpLfhThreadDataInitializeSet(v5, 1, 2);
  v9 = v5 + ((unsigned __int64)(unsigned __int16)v8 << 6);
  v10 = *(unsigned __int16 *)(v9 + 2 * v7);
  if ( *(_WORD *)(v9 + 2 * v7) )
  {
LABEL_16:
    v11 = v3;
    v14 = v5 + (unsigned int)((_DWORD)v10 << 6);
    v85 = v14;
    if ( *(_WORD *)(v14 + 4) )
    {
      v15 = *(_QWORD *)(v14 + 56);
      if ( (v15 & 0xFFF) != 0 )
      {
        v16 = *(_QWORD *)(v14 + 56);
        *(_QWORD *)(v14 + 56) = v15 - 1;
        v17 = v16 & 0xFFFFFFFFFFFFF000uLL;
        if ( v17 )
        {
          ExceptionList = KeGetPcr()->NtTib.ExceptionList;
          v19 = BYTE2(ExceptionList[182].Next);
          v86 = qword_140148348 ^ *(_DWORD *)(v17 + 40) ^ (v17 >> 12);
          v20 = *(unsigned __int8 *)(v17 + 24) - 8;
          if ( (_BYTE)v19 == BYTE3(ExceptionList[182].Next) )
          {
            v21 = qword_140148380
                ^ ((unsigned __int64)qword_140148380 >> 12)
                ^ ((qword_140148380 ^ ((unsigned __int64)qword_140148380 >> 12)) << 25)
                ^ ((qword_140148380
                  ^ ((unsigned __int64)qword_140148380 >> 12)
                  ^ ((qword_140148380 ^ ((unsigned __int64)qword_140148380 >> 12)) << 25)) >> 27);
            v23 = qword_140148380;
            v22 = _InterlockedCompareExchange64(&qword_140148380, v21, qword_140148380);
            if ( v23 != v22 )
            {
              do
              {
                v24 = v22;
                v21 = v22
                    ^ (v22 >> 12)
                    ^ ((v22 ^ (v22 >> 12)) << 25)
                    ^ ((v22 ^ (v22 >> 12) ^ ((v22 ^ (v22 >> 12)) << 25)) >> 27);
                v22 = _InterlockedCompareExchange64(&qword_140148380, v21, v22);
              }
              while ( v22 != v24 );
            }
            v25 = 29 * v21;
            BYTE3(ExceptionList[182].Next) = v25;
          }
          else
          {
            v25 = BYTE2(ExceptionList[182].Next);
          }
          BYTE2(ExceptionList[182].Next) = v25 + 1;
          v26 = (_DWORD *)(v17 + 64 + 8LL * *(unsigned __int8 *)(v17 + 36));
          while ( *v26 == -1 )
          {
            if ( v26 == (_DWORD *)(v17 + 64 + 8 * (v20 - 1LL)) )
              v26 = (_DWORD *)(v17 + 64);
            else
              v26 += 2;
          }
          _RAX = 1LL << ((unsigned __int16)(*((unsigned __int8 *)RtlpLowFragHeapRandomData + v19)
                                          * (unsigned __int16)__popcnt((unsigned int)~*v26)) >> 8);
          __asm
          {
            pdep    rcx, rax, rcx
            tzcnt   rdx, rcx
          }
          *(_QWORD *)v26 |= ((-(__int64)((unsigned int)a2 < (unsigned __int16)v86) & 0x100000000LL) + 1) << _RDX;
          v30 = (unsigned int)((_DWORD)v26 - (v17 + 64));
          LODWORD(_RCX) = _RDX + 4 * v30;
          *(_BYTE *)(v17 + 36) = (unsigned int)_RCX >> 5;
          Slow = v17 + (unsigned __int16)v86 * (_DWORD)_RCX + (unsigned int)HIWORD(v86);
          RtlHeapZero(Slow, ((unsigned int)a2 + 15LL) & 0xFFFFFFFFFFFFFFF0uLL, v30, v17);
          if ( (unsigned int)a2 < (unsigned __int16)v86 )
          {
            v32 = v86 - a2;
            if ( (unsigned __int16)v86 - (_DWORD)a2 == 1 )
              v32 = 0x8000;
            *(_WORD *)((unsigned __int16)v86 + Slow - 2) = v32;
          }
          goto LABEL_83;
        }
      }
LABEL_36:
      Slow = RtlpHpLfhSlotAllocateSlow(v5);
      goto LABEL_83;
    }
    v33 = 0;
    _m_prefetchw((const void *)(v14 + 56));
    v34 = *(_QWORD *)(v14 + 56);
    if ( (v34 & 0xFFF) == 0 )
      goto LABEL_36;
    while ( 1 )
    {
      v35 = _InterlockedCompareExchange64((volatile signed __int64 *)(v14 + 56), v34 - 1, v34);
      if ( v34 == v35 )
        break;
      v33 = 1;
      v34 = v35;
      if ( (v35 & 0xFFF) == 0 )
        goto LABEL_36;
    }
    v36 = v34 & 0xFFFFFFFFFFFFF000uLL;
    if ( !v36 )
      goto LABEL_36;
    v82 = qword_140148348 ^ *(_DWORD *)(v36 + 40) ^ (v36 >> 12);
    v80 = (-(__int64)((unsigned int)a2 < (unsigned __int16)v82) & 0x100000000LL) + 1;
    v84 = (unsigned __int64 *)(v36 + 24);
    v37 = RtlpLfhIncrementDataSlot();
    v39 = v36 + 64 + 8 * (v38 - 1);
    v40 = *(unsigned __int8 *)(v36 + 50);
    v41 = *((unsigned __int8 *)RtlpLowFragHeapRandomData + v37);
    v87 = *(_BYTE *)(v36 + 39);
    v79 = v41;
    v88 = v40;
    v42 = (volatile signed __int64 *)(v36 + 64 + 8LL * *(unsigned __int8 *)(v36 + 36));
LABEL_39:
    v43 = *v42;
    _R8 = (unsigned int)~*(_DWORD *)v42;
    if ( *(_DWORD *)v42 == -1 )
    {
      do
      {
        if ( v42 == (volatile signed __int64 *)v39 )
          v42 = (volatile signed __int64 *)(v36 + 64);
        else
          ++v42;
        v43 = *v42;
        _R8 = (unsigned int)~*(_DWORD *)v42;
      }
      while ( *(_DWORD *)v42 == -1 );
      v40 = v88;
    }
    while ( 1 )
    {
      if ( (qword_140148368 & 4) != 0 )
      {
        _RAX = 1LL << ((unsigned __int16)(v41 * __popcnt(_R8)) >> 8);
        __asm
        {
          pdep    rcx, rax, r8
          tzcnt   r10, rcx
        }
        v48 = v80 << _R10;
      }
      else
      {
        if ( v42 == (volatile signed __int64 *)v39 || v40 != 32 )
        {
          __asm { tzcnt   rcx, r8 }
          _BitScanReverse64(&v52, _R8);
          v53 = v52 - _RCX + 1;
          if ( v88 < v53 )
            v53 = v88;
          v79 = _RCX + ((v53 * v41) >> 8);
          _R8 = __ROR8__(_R8, v79);
          __asm { tzcnt   rcx, r8 }
          LODWORD(_R10) = _RCX + v79;
        }
        else
        {
          _RAX = (unsigned int)__ROR4__(_R8, v41);
          __asm { tzcnt   rcx, rax }
          LODWORD(_R10) = ((_BYTE)_RCX + (_BYTE)v41) & 0x1F;
        }
        v48 = v80 << _R10;
      }
      v56 = v43;
      v57 = v43 | v48;
      v58 = _InterlockedCompareExchange64(v42, v57, v43);
      v43 = v58;
      if ( v58 == v56 )
        break;
      v41 = v79;
      v59 = ~(_DWORD)v58;
      v40 = v88;
      _R8 = v59;
      if ( !v59 )
      {
        if ( v42 == (volatile signed __int64 *)v39 )
          v42 = (volatile signed __int64 *)(v36 + 64);
        else
          ++v42;
        goto LABEL_39;
      }
    }
    v60 = _R10 + 4 * ((_DWORD)v42 - (v36 + 64));
    *(_BYTE *)(v36 + 36) = v60 >> 5;
    v61 = HIWORD(v82) + v60 * (unsigned __int16)v82;
    if ( v87 <= 1u )
    {
      v62 = v60 <= *(unsigned __int16 *)(v36 + 48);
      v63 = (unsigned __int16)v82;
      if ( !v62 )
        RtlpHpLfhSubsegmentPrefetch(v5, v36, (unsigned int)v61, (unsigned __int16)v82);
    }
    else
    {
      if ( (int)RtlpHpLfhSubsegmentCommitBlock(v5, v36, (unsigned int)v61, v58) < 0 )
      {
        Slow = 0;
        if ( v60 != -1 )
        {
          _InterlockedAnd64(
            (volatile signed __int64 *)(v36 + 8LL * (v60 >> 5) + 64),
            __ROL8__(0xFFFFFFFEFFFFFFFEuLL, v60 & 0x1F));
          goto LABEL_71;
        }
LABEL_70:
        if ( Slow )
        {
LABEL_80:
          if ( v33 )
            RtlpHpLfhBucketUpdateAffinityMapping(v5, v5 + ((unsigned __int64)*(unsigned __int16 *)(v85 + 2) << 6));
          v11 = v3;
LABEL_83:
          if ( Slow != -1 )
            goto LABEL_92;
          goto LABEL_11;
        }
LABEL_71:
        v65 = *(_QWORD *)(v36 + 16);
        do
        {
          v89 = v65;
          v66 = BYTE6(v65);
          v67 = HIWORD(v65);
          v81 = WORD2(v65);
          if ( BYTE6(v65) == 1 )
            v66 = 2;
          WORD1(v89) = WORD1(v65) + 1;
          BYTE6(v89) = v66;
          v68 = (unsigned __int64)*(unsigned __int16 *)(v36 + 44) << 6;
          v69 = v65;
          v65 = _InterlockedCompareExchange64((volatile signed __int64 *)(v36 + 16), v89, v65);
        }
        while ( v69 != v65 );
        if ( !*(_BYTE *)(v68 + v5 + 92) )
          *(_BYTE *)(v68 + v5 + 92) = 1;
        if ( (_BYTE)v67 == 1 )
        {
          v70 = (unsigned __int64)v81 << 6;
          _m_prefetchw((const void *)(v70 + v5 + 8));
          v71 = *(_QWORD *)(v70 + v5 + 8);
          v72 = *v84;
          *v84 ^= (v71 ^ *v84) & 0xFFFFFFFFFFFFF000uLL;
          v74 = v71;
          v73 = _InterlockedCompareExchange64((volatile signed __int64 *)(v70 + v5 + 8), v36 | v71 & 0xFFF, v71);
          if ( v74 != v73 )
          {
            do
            {
              v75 = v73;
              *v84 = v72 ^ (v73 ^ v72) & 0xFFFFFFFFFFFFF000uLL;
              v73 = _InterlockedCompareExchange64((volatile signed __int64 *)(v70 + v5 + 8), v36 | v73 & 0xFFF, v73);
            }
            while ( v73 != v75 );
          }
        }
        goto LABEL_80;
      }
      v63 = (unsigned __int16)v82;
    }
    Slow = v36 + v61;
    RtlHeapZero(Slow, ((unsigned int)a2 + 15LL) & 0xFFFFFFFFFFFFFFF0uLL, v57, v43);
    if ( (unsigned int)a2 < v63 )
    {
      v64 = v63 - a2;
      if ( v63 - (_DWORD)a2 == 1 )
        v64 = 0x8000;
      *(_WORD *)(v63 + Slow - 2) = v64;
    }
    goto LABEL_70;
  }
  if ( RtlpHpLfhBucketCheckAndUpdate(v5, (unsigned int)v7, v10) )
  {
    v13 = v5 + ((unsigned __int64)BYTE4(v8) << 8) + 1472;
    LODWORD(v10) = *(unsigned __int16 *)(v13 + 2 * v7);
    if ( v9 != v13 )
      *(_WORD *)(v9 + 2 * v7) = *(_WORD *)(v13 + 2 * v7);
    goto LABEL_16;
  }
  v11 = v3;
LABEL_11:
  v2 = v83;
LABEL_12:
  if ( v3 > 0x20000 )
  {
    if ( v3 > *(unsigned int *)(v2 + 528) )
    {
      v12 = RtlpHpLargeAlloc(v2, a2, v3, 2);
    }
    else
    {
      v76 = v2 + 320;
      v77 = v76 + 192;
      if ( v3 <= *(unsigned int *)(v76 + 16) )
        v77 = v76;
      v12 = RtlpHpSegAlloc(v77, a2, v3, v3, 2);
    }
  }
  else
  {
    v12 = RtlpHpVsContextAllocate(v2 + 704, (unsigned int)a2, v11, 2);
  }
  Slow = v12;
LABEL_92:
  if ( !Slow )
    _InterlockedIncrement(&SkPoolAllocationsFailed);
  return Slow;
}

```

## disassembly

```asm
0x14000f0f0  mov     [rsp+arg_8], rbx
0x14000f0f5  mov     [rsp+arg_0], ecx
0x14000f0f9  push    rbp
0x14000f0fa  push    rsi
0x14000f0fb  push    rdi
0x14000f0fc  push    r12
0x14000f0fe  push    r13
0x14000f100  push    r14
0x14000f102  push    r15
0x14000f104  sub     rsp, 70h
0x14000f108  mov     rcx, cs:qword_14015A9A0
0x14000f10f  mov     r14, rdx
0x14000f112  mov     rbp, rdx
0x14000f115  mov     [rsp+0A8h+var_50], rcx
0x14000f11a  mov     edx, 1
0x14000f11f  cmp     r14, rdx
0x14000f122  movzx   eax, word ptr [rcx+404h]
0x14000f129  cmovbe  r14, rdx
0x14000f12d  xor     r13d, r13d
0x14000f130  lea     r8d, [rdx+1]
0x14000f134  cmp     r14, rax
0x14000f137  jnb     loc_14000F7C3
0x14000f13d  lea     rsi, [rcx+3C0h]
0x14000f144  cmp     ebp, r14d
0x14000f147  lea     eax, [r14+2]
0x14000f14b  cmovz   eax, r14d
0x14000f14f  lea     rcx, cs:140000000h
0x14000f156  add     eax, 0Fh
0x14000f159  shr     rax, 4
0x14000f15d  movzx   r12d, byte ptr [rax+rcx+10C780h]
0x14000f166  mov     rcx, gs:0
0x14000f16f  dec     r12d
0x14000f172  mov     eax, [rsi+4Ch]
0x14000f175  sub     eax, edx
0x14000f177  mov     rbx, [rcx+rax*8+0B68h]
0x14000f17f  test    rbx, rbx
0x14000f182  jz      short loc_14000F18E
0x14000f184  mov     [rsp+0A8h+arg_18], rbx
0x14000f18c  jmp     short loc_14000F199
0x14000f18e  mov     rcx, rsi
0x14000f191  call    RtlpHpLfhThreadDataInitializeSet
0x14000f196  mov     rbx, rax
0x14000f199  movzx   edi, bx
0x14000f19c  shl     rdi, 6
0x14000f1a0  add     rdi, rsi
0x14000f1a3  movzx   eax, word ptr [rdi+r12*2]
0x14000f1a8  mov     r8d, eax
0x14000f1ab  test    eax, eax
0x14000f1ad  jnz     short loc_14000F21A
0x14000f1af  mov     edx, r12d
0x14000f1b2  mov     rcx, rsi
0x14000f1b5  call    RtlpHpLfhBucketCheckAndUpdate
0x14000f1ba  test    rax, rax
0x14000f1bd  jnz     short loc_14000F1F3
0x14000f1bf  mov     r12d, r14d
0x14000f1c2  mov     rcx, [rsp+0A8h+var_50]
0x14000f1c7  mov     r8d, 2
0x14000f1cd  cmp     r14, 20000h
0x14000f1d4  ja      loc_14000F7CB
0x14000f1da  mov     r9d, r8d
0x14000f1dd  mov     edx, ebp
0x14000f1df  mov     r8d, r12d
0x14000f1e2  add     rcx, 2C0h
0x14000f1e9  call    RtlpHpVsContextAllocate
0x14000f1ee  jmp     loc_14000F811
0x14000f1f3  shr     rbx, 20h
0x14000f1f7  movzx   ecx, bl
0x14000f1fa  shl     rcx, 8
0x14000f1fe  add     rcx, 5C0h
0x14000f205  add     rcx, rsi
0x14000f208  movzx   eax, word ptr [rcx+r12*2]
0x14000f20d  mov     r8d, eax
0x14000f210  cmp     rdi, rcx
0x14000f213  jz      short loc_14000F21A
0x14000f215  mov     [rdi+r12*2], ax
0x14000f21a  shl     r8d, 6
0x14000f21e  mov     r12d, r14d
0x14000f221  mov     edx, r8d
0x14000f224  add     rdx, rsi
0x14000f227  mov     [rsp+0A8h+var_40], rdx
0x14000f22c  cmp     [rdx+4], r13w
0x14000f231  jz      loc_14000F3E8
0x14000f237  mov     rax, [rdx+38h]
0x14000f23b  mov     r10d, 0FFFh
0x14000f241  test    r10, rax
0x14000f244  jz      loc_14000F41E
0x14000f24a  mov     r9, rax
0x14000f24d  lea     rax, [rax-1]
0x14000f251  mov     [rdx+38h], rax
0x14000f255  and     r9, 0FFFFFFFFFFFFF000h
0x14000f25c  jz      loc_14000F41E
0x14000f262  mov     r10, gs:0
0x14000f26b  mov     rax, r9
0x14000f26e  movzx   esi, byte ptr [r9+18h]
0x14000f273  shr     rax, 0Ch
0x14000f277  xor     eax, [r9+28h]
0x14000f27b  xor     eax, dword ptr cs:qword_140148348
0x14000f281  movzx   edi, byte ptr [r10+0B62h]
0x14000f289  movzx   ebx, ax
0x14000f28c  cmp     ebp, ebx
0x14000f28e  mov     [rsp+0A8h+arg_0], eax
0x14000f295  mov     rax, 100000000h
0x14000f29f  sbb     r11, r11
0x14000f2a2  sub     esi, 8
0x14000f2a5  and     r11, rax
0x14000f2a8  inc     r11
0x14000f2ab  cmp     dil, [r10+0B63h]
0x14000f2b2  jnz     short loc_14000F322
0x14000f2b4  mov     rax, cs:qword_140148380
0x14000f2bb  mov     rcx, rax
0x14000f2be  shr     rcx, 0Ch
0x14000f2c2  xor     rcx, rax
0x14000f2c5  mov     rdx, rcx
0x14000f2c8  shl     rdx, 19h
0x14000f2cc  xor     rdx, rcx
0x14000f2cf  mov     rcx, rdx
0x14000f2d2  shr     rcx, 1Bh
0x14000f2d6  xor     rcx, rdx
0x14000f2d9  lock cmpxchg cs:qword_140148380, rcx
0x14000f2e2  jz      short loc_14000F313
0x14000f2e4  mov     rcx, rax
0x14000f2e7  mov     r8, rax
0x14000f2ea  shr     rcx, 0Ch
0x14000f2ee  xor     rcx, rax
0x14000f2f1  mov     rdx, rcx
0x14000f2f4  shl     rdx, 19h
0x14000f2f8  xor     rdx, rcx
0x14000f2fb  mov     rcx, rdx
0x14000f2fe  shr     rcx, 1Bh
0x14000f302  xor     rcx, rdx
0x14000f305  lock cmpxchg cs:qword_140148380, rcx
0x14000f30e  cmp     rax, r8
0x14000f311  jnz     short loc_14000F2E4
0x14000f313  movzx   eax, cl
0x14000f316  imul    ecx, eax, 1Dh
0x14000f319  mov     [r10+0B63h], cl
0x14000f320  jmp     short loc_14000F325
0x14000f322  mov     cl, dil
0x14000f325  inc     cl
0x14000f327  lea     rdx, cs:140000000h
0x14000f32e  mov     [r10+0B62h], cl
0x14000f335  lea     r10, [r9+40h]
0x14000f339  movzx   r15d, byte ptr [rdi+rdx+1485E0h]
0x14000f342  movzx   eax, byte ptr [r9+24h]
0x14000f347  mov     edx, esi
0x14000f349  dec     rdx
0x14000f34c  lea     r8, [r10+rax*8]
0x14000f350  lea     rdx, [r10+rdx*8]
0x14000f354  jmp     short loc_14000F364
0x14000f356  cmp     r8, rdx
0x14000f359  jz      short loc_14000F361
0x14000f35b  add     r8, 8
0x14000f35f  jmp     short loc_14000F364
0x14000f361  mov     r8, r10
0x14000f364  mov     eax, [r8]
0x14000f367  not     eax
0x14000f369  mov     ecx, eax
0x14000f36b  test    eax, eax
0x14000f36d  jz      short loc_14000F356
0x14000f36f  movzx   edi, word ptr [rsp+0A8h+arg_0+2]
0x14000f377  mov     esi, 1
0x14000f37c  popcnt  rax, rcx
0x14000f381  imul    eax, r15d
0x14000f385  shr     eax, 8
0x14000f388  shlx    rax, rsi, rax
0x14000f38d  pdep    rcx, rax, rcx
0x14000f392  tzcnt   rdx, rcx
0x14000f397  shlx    rcx, r11, rdx
0x14000f39c  or      [r8], rcx
0x14000f39f  sub     r8d, r10d
0x14000f3a2  lea     ecx, [rdx+r8*4]
0x14000f3a6  mov     edx, ebp
0x14000f3a8  mov     eax, ecx
0x14000f3aa  add     rdx, 0Fh
0x14000f3ae  imul    ecx, ebx
0x14000f3b1  and     rdx, 0FFFFFFFFFFFFFFF0h
0x14000f3b5  shr     eax, 5
0x14000f3b8  mov     [r9+24h], al
0x14000f3bc  add     edi, ecx
0x14000f3be  add     rdi, r9
0x14000f3c1  mov     rcx, rdi
0x14000f3c4  call    RtlHeapZero
0x14000f3c9  cmp     ebp, ebx
0x14000f3cb  jnb     loc_14000F7B7
0x14000f3d1  mov     eax, ebx
0x14000f3d3  sub     eax, ebp
0x14000f3d5  cmp     eax, esi
0x14000f3d7  jnz     short loc_14000F3DE
0x14000f3d9  mov     eax, 8000h
0x14000f3de  mov     [rbx+rdi-2], ax
0x14000f3e3  jmp     loc_14000F7B7
0x14000f3e8  mov     r15d, r13d
0x14000f3eb  prefetchw byte ptr [rdx+38h]
0x14000f3ef  mov     rbx, [rdx+38h]
0x14000f3f3  mov     r8d, 0FFFh
0x14000f3f9  test    r8, rbx
0x14000f3fc  jz      short loc_14000F41E
0x14000f3fe  mov     r10d, 1
0x14000f404  lea     rcx, [rbx-1]
0x14000f408  mov     rax, rbx
0x14000f40b  lock cmpxchg [rdx+38h], rcx
0x14000f411  jz      short loc_14000F437
0x14000f413  mov     r15d, r10d
0x14000f416  mov     rbx, rax
0x14000f419  test    r8, rax
0x14000f41c  jnz     short loc_14000F404
0x14000f41e  mov     r8d, ebp
0x14000f421  mov     r9d, 2
0x14000f427  mov     rcx, rsi; __int64
0x14000f42a  call    RtlpHpLfhSlotAllocateSlow
0x14000f42f  mov     rdi, rax
0x14000f432  jmp     loc_14000F7B7
0x14000f437  and     rbx, 0FFFFFFFFFFFFF000h
0x14000f43e  jz      short loc_14000F41E
0x14000f440  mov     rax, rbx
0x14000f443  shr     rax, 0Ch
0x14000f447  xor     eax, [rbx+28h]
0x14000f44a  xor     eax, dword ptr cs:qword_140148348
0x14000f450  movzx   edi, ax
0x14000f453  mov     [rsp+0A8h+var_60], eax
0x14000f457  cmp     ebp, edi
0x14000f459  mov     rax, 100000000h
0x14000f463  mov     [rsp+0A8h+var_74], edi
0x14000f467  sbb     rcx, rcx
0x14000f46a  and     rcx, rax
0x14000f46d  lea     rax, [rbx+18h]
0x14000f471  movzx   r11d, byte ptr [rax]
0x14000f475  add     rcx, r10
0x14000f478  add     r11d, 0FFFFFFF8h
0x14000f47c  mov     [rsp+0A8h+var_68], rcx
0x14000f481  mov     [rsp+0A8h+var_48], rax
0x14000f486  call    RtlpLfhIncrementDataSlot
0x14000f48b  mov     ecx, eax
0x14000f48d  lea     rdx, cs:140000000h
0x14000f494  lea     r12, [rbx+40h]
0x14000f498  dec     r11
0x14000f49b  mov     r13, rbx
0x14000f49e  movzx   edx, byte ptr [rcx+rdx+1485E0h]
0x14000f4a6  mov     al, [rbx+27h]
0x14000f4a9  lea     r11, [r12+r11*8]
0x14000f4ad  movzx   ecx, byte ptr [rbx+32h]
0x14000f4b1  mov     r10d, edx
0x14000f4b4  mov     byte ptr [rsp+0A8h+arg_0], al
0x14000f4bb  movzx   eax, byte ptr [rbx+24h]
0x14000f4bf  mov     [rsp+0A8h+var_78], edx
0x14000f4c3  mov     dword ptr [rsp+0A8h+arg_18], ecx
0x14000f4ca  lea     rdx, [r12+rax*8]
0x14000f4ce  mov     r9, [rdx]
0x14000f4d1  mov     eax, r9d
0x14000f4d4  not     eax
0x14000f4d6  mov     r8d, eax
0x14000f4d9  test    eax, eax
0x14000f4db  jnz     short loc_14000F501
0x14000f4dd  cmp     rdx, r11
0x14000f4e0  jz      short loc_14000F4E8
0x14000f4e2  add     rdx, 8
0x14000f4e6  jmp     short loc_14000F4EB
0x14000f4e8  mov     rdx, r12
0x14000f4eb  mov     r9, [rdx]
0x14000f4ee  mov     eax, r9d
0x14000f4f1  not     eax
0x14000f4f3  mov     r8d, eax
0x14000f4f6  test    eax, eax
0x14000f4f8  jz      short loc_14000F4DD
0x14000f4fa  mov     ecx, dword ptr [rsp+0A8h+arg_18]
0x14000f501  mov     eax, dword ptr cs:qword_140148368
0x14000f507  test    al, 4
0x14000f509  jz      short loc_14000F534
0x14000f50b  popcnt  rax, r8
0x14000f510  imul    eax, r10d
0x14000f514  mov     ecx, 1
0x14000f519  shr     eax, 8
0x14000f51c  shlx    rax, rcx, rax
0x14000f521  pdep    rcx, rax, r8
0x14000f526  tzcnt   r10, rcx
0x14000f52b  shlx    r8, [rsp+0A8h+var_68], r10
0x14000f532  jmp     short loc_14000F59E
0x14000f534  cmp     rdx, r11
0x14000f537  jz      short loc_14000F555
0x14000f539  cmp     ecx, 20h ; ' '
0x14000f53c  jnz     short loc_14000F555
0x14000f53e  mov     ecx, r10d
0x14000f541  ror     r8d, cl
0x14000f544  mov     eax, r8d
0x14000f547  tzcnt   rcx, rax
0x14000f54c  add     r10d, ecx
0x14000f54f  and     r10d, 1Fh
0x14000f553  jmp     short loc_14000F593
0x14000f555  tzcnt   rcx, r8
0x14000f55a  bsr     rax, r8
0x14000f55e  mov     [rsp+0A8h+var_78], ecx
0x14000f562  sub     eax, ecx
0x14000f564  inc     eax
0x14000f566  cmp     dword ptr [rsp+0A8h+arg_18], eax
0x14000f56d  cmovb   eax, dword ptr [rsp+0A8h+arg_18]
0x14000f575  imul    r10d, eax
0x14000f579  shr     r10d, 8
0x14000f57d  add     r10d, ecx
0x14000f580  mov     ecx, r10d
0x14000f583  mov     [rsp+0A8h+var_78], r10d
  ... truncated ...
```
