# InpFillQueue

- ea: `0x1400026f0`
- end: `0x1400031b3`
- name: `InpFillQueue`
- size: `2755`
- prototype: `__int64 __fastcall(_QWORD *, __int64, unsigned int *)`
- caller_count: `4`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140001370`
- `0x140001780`
- `0x140001ce0`
- `0x1400022c0`

## callees

- `0x1400026f0`
- `0x1400031c0`
- `0x140004c40`
- `0x140008878`
- `0x140008c7c`
- `0x140008e78`
- `0x140008f90`
- `0x1400097ec`
- `0x140011f80`
- `0x140012280`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002721`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003077`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002721`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003077`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000305f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003099`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000305f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003099`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140002903`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140002988`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140002903`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140002988`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140002bb9`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140002bb9`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002926`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002a2f`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002cd6`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002926`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002a2f`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002cd6`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400029f9`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400029f9`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x1400028d6`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x1400028d6`
- `HAL!KeQueryPerformanceCounter` at `0x140002948`
- `HAL!KeQueryPerformanceCounter` at `0x140002f14`
- `HAL!KeQueryPerformanceCounter` at `0x140002948`
- `HAL!KeQueryPerformanceCounter` at `0x140002f14`

## pseudocode

```c
__int64 __fastcall InpFillQueue(_QWORD *a1, __int64 a2, unsigned int *a3)
{
  unsigned int v3; // r15d
  unsigned int v5; // ebp
  unsigned int v6; // r12d
  unsigned __int64 v7; // r8
  unsigned int v8; // r9d
  int *v9; // rsi
  int v10; // edi
  __int16 v11; // ax
  int v12; // r10d
  __int64 v13; // r11
  unsigned int v14; // ecx
  unsigned int v15; // r13d
  unsigned int v16; // ebp
  unsigned int v17; // ebp
  __int64 v18; // rdi
  struct _RTL_AVL_TABLE *v19; // rcx
  _QWORD *v20; // rax
  KSPIN_LOCK *v21; // rcx
  LARGE_INTEGER v22; // rax
  bool v23; // zf
  unsigned int v24; // eax
  signed __int64 *v25; // rdx
  signed __int64 v26; // r8
  signed __int64 v27; // rax
  signed __int64 v28; // rcx
  struct _RTL_AVL_TABLE *v29; // rcx
  __int128 v30; // xmm0
  _QWORD *v31; // rdx
  unsigned int v32; // r9d
  unsigned int v33; // r13d
  char v34; // cl
  _QWORD *v35; // rcx
  unsigned int v36; // esi
  unsigned int v37; // edi
  int v38; // r15d
  unsigned int v39; // r12d
  unsigned int v40; // r14d
  unsigned int v41; // ecx
  unsigned int v42; // ebp
  unsigned int v43; // eax
  _BYTE *v44; // rax
  __int64 v45; // rcx
  __int128 v46; // xmm0
  unsigned int v47; // eax
  __int64 v48; // rcx
  __int64 v49; // r9
  LARGE_INTEGER **v50; // r14
  LARGE_INTEGER **v51; // rsi
  unsigned int v52; // eax
  _QWORD *v53; // rsi
  LARGE_INTEGER *v54; // rdi
  int LowPart_low; // ecx
  int v56; // ecx
  int v57; // ecx
  _QWORD *v58; // rcx
  LONGLONG v59; // rcx
  LARGE_INTEGER **v60; // rax
  _QWORD *v61; // rcx
  LARGE_INTEGER *v62; // rax
  LONGLONG QuadPart; // rcx
  LARGE_INTEGER **v64; // rax
  int v65; // ebp
  KIRQL v66; // di
  unsigned int v67; // ecx
  unsigned int *v68; // r9
  unsigned int v69; // r8d
  int v70; // ecx
  unsigned int v71; // edx
  unsigned int v72; // eax
  unsigned int v73; // edx
  unsigned int v74; // ecx
  unsigned int v75; // eax
  signed __int32 v77[8]; // [rsp+0h] [rbp-E8h] BYREF
  __int64 v78; // [rsp+28h] [rbp-C0h]
  KIRQL v79; // [rsp+40h] [rbp-A8h]
  unsigned int v80; // [rsp+44h] [rbp-A4h]
  unsigned int v81; // [rsp+48h] [rbp-A0h]
  __int128 v82; // [rsp+50h] [rbp-98h]
  unsigned int v83; // [rsp+60h] [rbp-88h]
  unsigned int v84; // [rsp+64h] [rbp-84h]
  int *v85; // [rsp+68h] [rbp-80h]
  __int64 Buffer; // [rsp+70h] [rbp-78h] BYREF
  int v87; // [rsp+78h] [rbp-70h]
  __int64 v88; // [rsp+80h] [rbp-68h] BYREF
  int v89; // [rsp+88h] [rbp-60h]
  unsigned int *v90; // [rsp+90h] [rbp-58h]
  int v91; // [rsp+98h] [rbp-50h]
  __int16 v92; // [rsp+9Eh] [rbp-4Ah]

  v3 = *((_DWORD *)a1 + 33);
  v90 = a3;
  v81 = v3;
  v5 = v3;
  v6 = 4;
  v80 = 0;
  v79 = KeAcquireSpinLockRaiseToDpc(a1 + 88);
  while ( 1 )
  {
    LODWORD(v7) = *((_DWORD *)a1 + 32);
    v8 = *((_DWORD *)a1 + 26);
    if ( (_DWORD)v7 == v5 )
    {
      LODWORD(v7) = *(_DWORD *)a1[11];
      if ( (unsigned int)v7 >= v8 || (v7 & 7) != 0 )
        goto LABEL_88;
      *((_DWORD *)a1 + 32) = v7;
      if ( (_DWORD)v7 == v5 )
        goto LABEL_90;
    }
    v7 = (unsigned int)v7 - v5;
    if ( (unsigned int)v7 >= v8 )
      v7 = v8 + (unsigned int)v7;
    v9 = (int *)(v5 + a1[12]);
    v85 = v9;
    v10 = *((unsigned __int16 *)v9 + 2);
    v11 = *((_WORD *)v9 + 3);
    v12 = *v9;
    v13 = (unsigned int)v9[2];
    v14 = v9[3];
    v15 = 8 * v10;
    v91 = *v9;
    v92 = v11;
    if ( (unsigned int)(8 * v10) < 0x10 || v15 + 8 > (unsigned int)v7 )
    {
LABEL_88:
      a1[175] = 4;
      goto LABEL_89;
    }
    v16 = v15 + 8 + v5;
    WORD2(v82) = v10;
    WORD3(v82) = v11;
    *((_QWORD *)&v82 + 1) = __PAIR64__(v14, v13);
    if ( v16 >= v8 )
      v16 -= v8;
    LODWORD(v82) = v12;
    v84 = v16;
    v17 = 8 * SHIWORD(v12);
    v83 = v17;
    if ( v17 > v15 || v17 < 0x10 )
    {
      a1[175] = 0;
      goto LABEL_89;
    }
    if ( (unsigned __int16)v12 != 7 && (unsigned __int16)v12 != 6 && (unsigned __int16)v12 != 9 )
    {
      if ( (unsigned __int16)v12 == 11 )
      {
        if ( v15 - v17 > *((_DWORD *)a1 + 363) )
          goto LABEL_75;
        v87 = 0;
        Buffer = 0;
        if ( (unsigned int)v13 >= *((_DWORD *)a1 + 180) )
        {
          v19 = (struct _RTL_AVL_TABLE *)a1[94];
          v18 = 0;
          if ( v19 )
          {
            LODWORD(Buffer) = v13;
            v20 = RtlLookupElementGenericTableAvl(v19, &Buffer);
            if ( v20 )
              v18 = v20[1];
          }
        }
        else
        {
          _mm_lfence();
          v18 = *(_QWORD *)(a1[89] + 8 * v13);
          if ( v18 >= 0 )
            goto LABEL_75;
        }
        if ( !v18 )
          goto LABEL_75;
        if ( *(_DWORD *)(v18 + 24) == 3 )
          goto LABEL_29;
        KeAcquireSpinLockAtDpcLevel(a1 + 32);
        v21 = a1 + 32;
        if ( *(_DWORD *)(v18 + 24) == 3 )
        {
          ++*((_DWORD *)a1 + 266);
          KeReleaseSpinLockFromDpcLevel(v21);
LABEL_29:
          if ( *(_QWORD *)(v18 + 128) )
          {
            if ( KmclPerformanceCounterTimingCounters )
            {
              v22 = (LARGE_INTEGER)(*(_QWORD *)&KeQueryPerformanceCounter(0) - *(_QWORD *)(v18 + 128));
              v23 = KmclPerformanceCounterTimingCounters == 0;
              *(LARGE_INTEGER *)(v18 + 128) = v22;
              if ( !v23 )
                a1[63] += v22.QuadPart;
            }
          }
          LOBYTE(v7) = 1;
          OutpPacketCopyBouncePagesToMdl(a1, v18, v7);
          KeAcquireSpinLockAtDpcLevel(a1 + 32);
          v24 = *(_DWORD *)(v18 + 28);
          if ( v24 )
          {
            v89 = 0;
            v88 = 0;
            if ( v24 >= *((_DWORD *)a1 + 180) )
            {
              v29 = (struct _RTL_AVL_TABLE *)a1[94];
              LODWORD(v88) = v24;
              RtlDeleteElementGenericTableAvl(v29, &v88);
            }
            else
            {
              v25 = (signed __int64 *)a1[89];
              v26 = v24;
              _m_prefetchw(v25);
              v27 = *v25;
              do
              {
                v25[v26] = v27;
                v28 = v27;
                v27 = _InterlockedCompareExchange64(v25, v26, v27);
              }
              while ( v27 != v28 );
            }
            *(_DWORD *)(v18 + 28) = 0;
          }
          if ( *(_BYTE *)(v18 + 61) == 1 && *(_QWORD *)(v18 + 80) )
          {
            KmclpFreeBounceList(*a1);
            *(_QWORD *)(v18 + 80) = 0;
          }
          *(_DWORD *)(v18 + 24) = 4;
          KeReleaseSpinLockFromDpcLevel(a1 + 32);
          v30 = v82;
          v31 = (_QWORD *)(v18 + 176);
          *(_QWORD *)(v18 + 184) = v18 + 176;
          LODWORD(v7) = v15 - v17;
          *(_QWORD *)(v18 + 176) = v18 + 176;
          *(_OWORD *)(v18 + 192) = v30;
          *(_QWORD *)(v18 + 208) = v9;
          *(_DWORD *)(v18 + 216) = v17;
          *(_DWORD *)(v18 + 220) = v15;
          v32 = *(_DWORD *)(v18 + 112);
          if ( v15 - v17 > v32 )
            v33 = 0;
          else
            v33 = v15 - v17;
          v34 = *(_BYTE *)(v18 + 62) | 2;
          if ( (unsigned int)v7 > v32 )
            v34 = *(_BYTE *)(v18 + 62) & 0xFD;
          *(_BYTE *)(v18 + 62) = v34;
          *(_DWORD *)(v18 + 116) = v33;
          v35 = (_QWORD *)a1[163];
          if ( (_QWORD *)*v35 != a1 + 162 )
            __fastfail(3u);
          *v31 = a1 + 162;
          *(_QWORD *)(v18 + 184) = v35;
          *v35 = v31;
          a1[163] = v31;
          goto LABEL_72;
        }
        KeReleaseSpinLockFromDpcLevel(v21);
LABEL_75:
        a1[175] = 2;
      }
      else
      {
        a1[175] = 3;
      }
LABEL_89:
      v6 = 11;
      goto LABEL_90;
    }
    if ( *((_DWORD *)a1 + 349) <= (unsigned int)(*((_DWORD *)a1 + 328) - *((_DWORD *)a1 + 286)) )
      break;
    if ( v15 - v17 > *(_DWORD *)(*a1 + 1736LL) )
    {
      if ( *((_DWORD *)a1 + 274) )
      {
        *((_DWORD *)a1 + 350) = 0;
        *((_DWORD *)a1 + 351) = 1;
      }
      goto LABEL_89;
    }
    if ( (unsigned __int16)v12 == 9 )
    {
      if ( v17 < 0x18 || (v36 = v9[5]) == 0 || v36 > (v17 - 24) >> 3 )
      {
        if ( *((_DWORD *)a1 + 274) )
        {
          *((_DWORD *)a1 + 350) = 1;
          *((_DWORD *)a1 + 351) = 1;
        }
        goto LABEL_89;
      }
      v37 = (v17 - 24 - 8 * v36) >> 3;
    }
    else
    {
      v36 = 0;
      v37 = 0;
    }
    v38 = 16 * v36;
    v39 = (8 * (v37 + 6 * v36) + 15) & 0xFFFFFFF0;
    v40 = (v15 + 15) & 0xFFFFFFF0;
    v41 = v40 + 16 * v36 + v39 + *((_DWORD *)a1 + 348);
    v42 = v41 + 160;
    if ( (v92 & 1) != 0 )
    {
      v43 = *((_DWORD *)a1 + 363);
      if ( *((_BYTE *)a1 + 1203) )
      {
        v42 += v43;
      }
      else if ( v41 < v43 )
      {
        v42 = v43 + 160;
      }
    }
    if ( v42 > *((_DWORD *)a1 + 362) )
    {
      if ( *((_DWORD *)a1 + 274) )
      {
        *((_DWORD *)a1 + 350) = 0;
        *((_DWORD *)a1 + 351) = 1;
      }
      v3 = v81;
      v6 = 11;
      goto LABEL_90;
    }
    v44 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1[180]
                                                                   + 64LL
                                                                   + ((unsigned __int64)(v42 - 1) >> 10 << 7)));
    v45 = (__int64)v44;
    if ( v44 )
    {
      v44[16] = 0;
    }
    else
    {
      v45 = _InterlockedExchange64(a1 + 183, 0);
      if ( !v45 )
      {
        v3 = v81;
        v6 = 6;
        goto LABEL_90;
      }
      *(_BYTE *)(v45 + 16) = 1;
    }
    v46 = v82;
    a1[173] += *(_DWORD *)(v45 + 8) - v42;
    *(_DWORD *)(v45 + 40) = 0;
    *(_QWORD *)(v45 + 48) = 0;
    *(_DWORD *)(v45 + 60) = v38 + v40;
    *(_DWORD *)(v45 + 56) = v40;
    *(_DWORD *)(v45 + 64) = v40 + v39 + v38;
    *(_DWORD *)(v45 + 12) = v42;
    *(_QWORD *)v45 = a1;
    *(_DWORD *)(v45 + 84) = *((_DWORD *)a1 + 348);
    *(_QWORD *)(v45 + 72) = 0;
    *(_BYTE *)(v45 + 17) = 0;
    *(_QWORD *)(v45 + 88) = 0;
    *(_QWORD *)(v45 + 96) = 0;
    *(_OWORD *)(v45 + 120) = v46;
    *(_QWORD *)(v45 + 112) = v45 + 104;
    *(_QWORD *)(v45 + 104) = v45 + 104;
    *(_QWORD *)(v45 + 136) = v85;
    *(_DWORD *)(v45 + 148) = v83;
    *(_DWORD *)(v45 + 144) = v15;
    *(_DWORD *)(v45 + 156) = v36;
    *(_DWORD *)(v45 + 152) = v37;
    ++*((_DWORD *)a1 + 328);
    v7 = a1[163];
    if ( *(_QWORD **)v7 != a1 + 162 )
      __fastfail(3u);
    v6 = 4;
    *(_QWORD *)(v45 + 104) = a1 + 162;
    *(_QWORD *)(v45 + 112) = v7;
    *(_QWORD *)v7 = v45 + 104;
    a1[163] = v45 + 104;
LABEL_72:
    v5 = v84;
    v47 = v80 + 1;
    ++*((_DWORD *)a1 + 332);
    v3 = v5;
    v81 = v5;
    v80 = v47;
    if ( v47 >= 0x40 )
    {
      v6 = 1;
      goto LABEL_90;
    }
  }
  ++a1[167];
  v6 = 5;
  if ( (Microsoft_Windows_Hyper_V_KMCL_ChildEnableBits & 4) != 0 )
  {
    v48 = *a1 + 2752LL;
    v49 = *a1 + 2768LL;
    LOWORD(v78) = *(_WORD *)(*a1 + 3280LL);
    McTemplateK0jjh_EtwWriteTransfer(v48, (unsigned int)VMBUS_HIT_INCOMING_QUOTA, v7, v49, v48);
  }
LABEL_90:
  v50 = (LARGE_INTEGER **)(a1 + 162);
  v51 = (LARGE_INTEGER **)a1[162];
  if ( v51 != a1 + 162 )
  {
    do
    {
      if ( *((_WORD *)v51 + 8) == 11 )
      {
        v52 = *((_DWORD *)v51 - 15);
        if ( v52 )
          memmove(*(v51 - 9), (char *)v51[4] + *((unsigned int *)v51 + 10), v52);
      }
      else
      {
        memmove(v51 + 7, v51[4], *((unsigned int *)v51 + 10));
        *(_OWORD *)(v51 + 7) = *((_OWORD *)v51 + 1);
      }
      v51 = (LARGE_INTEGER **)*v51;
    }
    while ( v51 != v50 );
  }
LABEL_96:
  v53 = a1 + 160;
  while ( 1 )
  {
    v54 = *v50;
    if ( *v50 == (LARGE_INTEGER *)v50 )
    {
      v65 = 1;
      goto LABEL_125;
    }
    LowPart_low = LOWORD(v54[2].LowPart);
    if ( LowPart_low == 11 )
    {
      v61 = (_QWORD *)v53[1];
      if ( (_QWORD *)*v61 != v53 )
        __fastfail(3u);
      v62 = v54 - 4;
      v62->QuadPart = (LONGLONG)v53;
      v62[1].QuadPart = (LONGLONG)v61;
      *v61 = v54 - 4;
      v53[1] = v54 - 4;
      QuadPart = v54->QuadPart;
      if ( *(LARGE_INTEGER **)(v54->QuadPart + 8) != v54 || (v64 = (LARGE_INTEGER **)v54[1].QuadPart, *v64 != v54) )
        __fastfail(3u);
      *v64 = (LARGE_INTEGER *)QuadPart;
      *(_QWORD *)(QuadPart + 8) = v64;
      if ( (Microsoft_Windows_Hyper_V_KMCL_ChildEnableBits & 1) != 0 )
        McTemplateK0jjxth_EtwWriteTransfer(
          *(_DWORD *)a1 + 2752,
          (unsigned int)VMBUS_FETCH_PACKET,
          v7,
          *(_DWORD *)a1 + 2768,
          *a1 + 2752LL,
          v54[3].QuadPart,
          1,
          *(_WORD *)(*a1 + 3280LL));
      goto LABEL_96;
    }
    v56 = LowPart_low - 6;
    if ( v56 )
    {
      v57 = v56 - 1;
      if ( v57 )
      {
        if ( v57 != 2 )
        {
          *((_DWORD *)a1 + 350) = 3;
          v65 = 11;
          *((_DWORD *)a1 + 351) = 2;
          goto LABEL_125;
        }
      }
    }
    memset((char *)&v54[7] + v54[5].LowPart, 0, v54[-12].LowPart - v54[5].LowPart - 160);
    if ( LOWORD(v54[2].LowPart) == 9
      && !(unsigned __int8)InpParseGpaDirectPacket(
                             &v54[-13],
                             (unsigned int)v54[5].HighPart,
                             (unsigned int)v54[6].HighPart) )
    {
      break;
    }
    LOBYTE(v54[-11].LowPart) = v54[-11].LowPart & 0xFB | (4 * (BYTE6(v54[2].QuadPart) & 1));
    v53 = a1 + 160;
    v58 = (_QWORD *)a1[161];
    if ( (_QWORD *)*v58 != a1 + 160 )
      __fastfail(3u);
    v54[-10].QuadPart = (LONGLONG)v53;
    v54[-9].QuadPart = (LONGLONG)v58;
    *v58 = v54 - 10;
    a1[161] = v54 - 10;
    v59 = v54->QuadPart;
    if ( *(LARGE_INTEGER **)(v54->QuadPart + 8) != v54 || (v60 = (LARGE_INTEGER **)v54[1].QuadPart, *v60 != v54) )
      __fastfail(3u);
    v23 = KmclPerformanceCounterTimingCounters == 0;
    *v60 = (LARGE_INTEGER *)v59;
    *(_QWORD *)(v59 + 8) = v60;
    if ( !v23 )
      v54[-2] = KeQueryPerformanceCounter(0);
    if ( (Microsoft_Windows_Hyper_V_KMCL_ChildEnableBits & 1) != 0 )
      McTemplateK0jjxth_EtwWriteTransfer(
        *(_DWORD *)a1 + 2752,
        (unsigned int)VMBUS_FETCH_PACKET,
        v7,
        *(_DWORD *)a1 + 2768,
        *a1 + 2752LL,
        v54[3].QuadPart,
        0,
        *(_WORD *)(*a1 + 3280LL));
  }
  if ( *((_DWORD *)a1 + 274) )
  {
    *((_DWORD *)a1 + 350) = 1;
    *((_DWORD *)a1 + 351) = 2;
  }
  v65 = 11;
LABEL_125:
  KeReleaseSpinLock(a1 + 88, v79);
  if ( *v50 != (LARGE_INTEGER *)v50 )
  {
    v66 = KeAcquireSpinLockRaiseToDpc(a1 + 136);
    InpUnlinkExtractionQueue(a1);
    KeReleaseSpinLock(a1 + 136, v66);
  }
  v67 = v80;
  *v90 = v80;
  if ( v65 == 11 || v6 == 11 )
    return 11;
  if ( v67 )
  {
    v68 = (unsigned int *)a1[11];
    v69 = *((_DWORD *)a1 + 26);
    if ( *v68 == v3 && (unsigned int)(*((_DWORD *)a1 + 34) + *((_DWORD *)a1 + 51) - *((_DWORD *)a1 + 35)) < 0x40 )
      _InterlockedIncrement((volatile signed __int32 *)a1 + 34);
    v70 = *((_DWORD *)a1 + 33);
    *((_DWORD *)a1 + 33) = v3;
    v68[1] = v3;
    _InterlockedOr(v77, 0);
    v71 = v68[3];
    v72 = *v68;
    if ( *v68 < v69 && (v72 & 7) == 0 )
    {
      *((_DWORD *)a1 + 32) = v72;
      v73 = v71 & 0xFFFFFFF8;
      if ( v73 )
      {
        v74 = v70 - v72 - 8;
        if ( v74 >= v69 )
          v74 += v69;
        v75 = v3 - v72 - 8;
        if ( v75 >= v69 )
          v75 += v69;
        if ( v75 >= v73 && v74 < v73 )
        {
          if ( (unsigned __int8)KmclSendSignal(*a1) )
          {
            ++a1[168];
            return 1;
          }
          ++a1[169];
        }
      }
    }
    return 1;
  }
  return v6;
}

```

## disassembly

```asm
0x1400026f0  push    rbx
0x1400026f2  push    rbp
0x1400026f3  push    r12
0x1400026f5  push    r14
0x1400026f7  push    r15
0x1400026f9  sub     rsp, 0C0h
0x140002700  mov     r15d, [rcx+84h]
0x140002707  mov     rbx, rcx
0x14000270a  add     rcx, 2C0h; SpinLock
0x140002711  mov     [rsp+0E8h+var_58], r8
0x140002719  mov     [rsp+0E8h+var_A0], r15d
0x14000271e  mov     ebp, r15d
0x140002721  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002728  nop     dword ptr [rax+rax+00h]
0x14000272d  mov     [rsp+0E8h+arg_8], rsi
0x140002735  xor     r14d, r14d
0x140002738  mov     [rsp+0E8h+var_30], rdi
0x140002740  mov     r12d, 4
0x140002746  mov     [rsp+0E8h+var_A4], r14d
0x14000274b  mov     [rsp+0E8h+var_A8], al
0x14000274f  mov     [rsp+0E8h+var_38], r13
0x140002757  nop     word ptr [rax+rax+00000000h]
0x140002760  mov     r8d, [rbx+80h]
0x140002767  mov     r9d, [rbx+68h]
0x14000276b  cmp     r8d, ebp
0x14000276e  jnz     short loc_14000279A
0x140002770  mov     rax, [rbx+58h]
0x140002774  mov     r8d, [rax]
0x140002777  cmp     r8d, r9d
0x14000277a  jnb     loc_140002DD1
0x140002780  test    r8b, 7
0x140002784  jnz     loc_140002DD1
0x14000278a  mov     [rbx+80h], r8d
0x140002791  cmp     r8d, ebp
0x140002794  jz      loc_140002DE2
0x14000279a  sub     r8d, ebp
0x14000279d  cmp     r8d, r9d
0x1400027a0  jb      short loc_1400027A5
0x1400027a2  add     r8d, r9d
0x1400027a5  mov     rsi, [rbx+60h]
0x1400027a9  mov     ecx, ebp
0x1400027ab  add     rsi, rcx
0x1400027ae  mov     [rsp+0E8h+var_80], rsi
0x1400027b3  movzx   edi, word ptr [rsi+4]
0x1400027b7  movzx   eax, word ptr [rsi+6]
0x1400027bb  mov     r10d, [rsi]
0x1400027be  mov     r11d, [rsi+8]
0x1400027c2  mov     ecx, [rsi+0Ch]
0x1400027c5  lea     r13d, ds:0[rdi*8]
0x1400027cd  mov     [rsp+0E8h+var_50], r10d
0x1400027d5  nop
0x1400027d6  mov     [rsp+0E8h+var_4A], ax
0x1400027de  cmp     r13d, 10h
0x1400027e2  jb      loc_140002DD1
0x1400027e8  lea     edx, [r13+8]
0x1400027ec  cmp     edx, r8d
0x1400027ef  ja      loc_140002DD1
0x1400027f5  add     ebp, edx
0x1400027f7  mov     word ptr [rsp+0E8h+var_98+4], di
0x1400027fc  mov     edx, ebp
0x1400027fe  mov     word ptr [rsp+0E8h+var_98+6], ax
0x140002803  sub     edx, r9d
0x140002806  mov     dword ptr [rsp+0E8h+var_98+8], r11d
0x14000280b  cmp     ebp, r9d
0x14000280e  mov     dword ptr [rsp+0E8h+var_98+0Ch], ecx
0x140002812  cmovnb  ebp, edx
0x140002815  movzx   edx, r10w
0x140002819  mov     word ptr [rsp+0E8h+var_98], dx
0x14000281e  mov     edx, r10d
0x140002821  shr     edx, 10h
0x140002824  mov     [rsp+0E8h+var_84], ebp
0x140002828  mov     word ptr [rsp+0E8h+var_98+2], dx
0x14000282d  movsx   ebp, word ptr [rsp+0E8h+var_98+2]
0x140002832  shl     ebp, 3
0x140002835  mov     [rsp+0E8h+var_88], ebp
0x140002839  cmp     ebp, r13d
0x14000283c  ja      loc_140002DC4
0x140002842  cmp     ebp, 10h
0x140002845  jb      loc_140002DC4
0x14000284b  movzx   edx, r10w
0x14000284f  cmp     edx, 7
0x140002852  jz      loc_140002ACC
0x140002858  mov     ecx, edx
0x14000285a  sub     ecx, 6
0x14000285d  jz      loc_140002ACC
0x140002863  sub     ecx, 3
0x140002866  jz      loc_140002ACC
0x14000286c  sub     ecx, 1
0x14000286f  jz      loc_140002CF2
0x140002875  cmp     ecx, 1
0x140002878  jnz     loc_140002CF2
0x14000287e  mov     eax, r13d
0x140002881  sub     eax, ebp
0x140002883  cmp     eax, [rbx+5ACh]
0x140002889  ja      loc_140002CE2
0x14000288f  xor     eax, eax
0x140002891  mov     [rsp+0E8h+var_74], rax
0x140002896  mov     [rsp+70h], rax
0x14000289b  cmp     r11d, [rbx+2D0h]
0x1400028a2  jnb     short loc_1400028BD
0x1400028a4  lfence
0x1400028a7  mov     rax, [rbx+2C8h]
0x1400028ae  mov     rdi, [rax+r11*8]
0x1400028b2  test    rdi, rdi
0x1400028b5  jns     loc_140002CE2
0x1400028bb  jmp     short loc_1400028EB
0x1400028bd  mov     rcx, [rbx+2F0h]; Table
0x1400028c4  mov     rdi, r14
0x1400028c7  test    rcx, rcx
0x1400028ca  jz      short loc_1400028EB
0x1400028cc  lea     rdx, [rsp+0E8h+Buffer]; Buffer
0x1400028d1  mov     [rsp+0E8h+Buffer], r11d
0x1400028d6  call    cs:__imp_RtlLookupElementGenericTableAvl
0x1400028dd  nop     dword ptr [rax+rax+00h]
0x1400028e2  test    rax, rax
0x1400028e5  jz      short loc_1400028EB
0x1400028e7  mov     rdi, [rax+8]
0x1400028eb  test    rdi, rdi
0x1400028ee  jz      loc_140002CE2
0x1400028f4  mov     eax, [rdi+18h]
0x1400028f7  cmp     eax, 3
0x1400028fa  jz      short loc_140002932
0x1400028fc  lea     rcx, [rbx+100h]; SpinLock
0x140002903  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000290a  nop     dword ptr [rax+rax+00h]
0x14000290f  cmp     dword ptr [rdi+18h], 3
0x140002913  lea     rcx, [rbx+100h]; SpinLock
0x14000291a  jnz     loc_140002CD6
0x140002920  inc     dword ptr [rbx+428h]
0x140002926  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000292d  nop     dword ptr [rax+rax+00h]
0x140002932  cmp     qword ptr [rdi+80h], 0
0x14000293a  jz      short loc_140002973
0x14000293c  cmp     cs:KmclPerformanceCounterTimingCounters, 0
0x140002944  jz      short loc_140002973
0x140002946  xor     ecx, ecx; PerformanceFrequency
0x140002948  call    cs:__imp_KeQueryPerformanceCounter
0x14000294f  nop     dword ptr [rax+rax+00h]
0x140002954  sub     rax, [rdi+80h]
0x14000295b  cmp     cs:KmclPerformanceCounterTimingCounters, 0
0x140002963  mov     [rdi+80h], rax
0x14000296a  jz      short loc_140002973
0x14000296c  add     [rbx+1F8h], rax
0x140002973  mov     r8b, 1
0x140002976  mov     rdx, rdi
0x140002979  mov     rcx, rbx
0x14000297c  call    OutpPacketCopyBouncePagesToMdl
0x140002981  lea     rcx, [rbx+100h]; SpinLock
0x140002988  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000298f  nop     dword ptr [rax+rax+00h]
0x140002994  mov     eax, [rdi+1Ch]
0x140002997  test    eax, eax
0x140002999  jz      short loc_140002A09
0x14000299b  xor     ecx, ecx
0x14000299d  mov     [rsp+0E8h+var_64], rcx
0x1400029a5  mov     [rsp+80h], rcx
0x1400029ad  cmp     eax, [rbx+2D0h]
0x1400029b3  jnb     short loc_1400029E3
0x1400029b5  mov     rdx, [rbx+2C8h]
0x1400029bc  mov     r8d, eax
0x1400029bf  prefetchw byte ptr [rdx]
0x1400029c2  mov     rax, [rdx]
0x1400029c5  nop     word ptr [rax+rax+00000000h]
0x1400029d0  mov     [rdx+r8*8], rax
0x1400029d4  mov     rcx, rax
0x1400029d7  lock cmpxchg [rdx], r8
0x1400029dc  cmp     rax, rcx
0x1400029df  jnz     short loc_1400029D0
0x1400029e1  jmp     short loc_140002A05
0x1400029e3  mov     rcx, [rbx+2F0h]; Table
0x1400029ea  lea     rdx, [rsp+0E8h+var_68]; Buffer
0x1400029f2  mov     [rsp+0E8h+var_68], eax
0x1400029f9  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x140002a00  nop     dword ptr [rax+rax+00h]
0x140002a05  mov     [rdi+1Ch], r14d
0x140002a09  cmp     byte ptr [rdi+3Dh], 1
0x140002a0d  jnz     short loc_140002A24
0x140002a0f  mov     rdx, [rdi+50h]
0x140002a13  test    rdx, rdx
0x140002a16  jz      short loc_140002A24
0x140002a18  mov     rcx, [rbx]
0x140002a1b  call    KmclpFreeBounceList
0x140002a20  mov     [rdi+50h], r14
0x140002a24  lea     rcx, [rbx+100h]; SpinLock
0x140002a2b  mov     [rdi+18h], r12d
0x140002a2f  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140002a36  nop     dword ptr [rax+rax+00h]
0x140002a3b  movups  xmm0, [rsp+0E8h+var_98]
0x140002a40  lea     rdx, [rdi+0B0h]
0x140002a47  mov     r8d, r13d
0x140002a4a  mov     [rdi+0B8h], rdx
0x140002a51  sub     r8d, ebp
0x140002a54  mov     [rdx], rdx
0x140002a57  movups  xmmword ptr [rdi+0C0h], xmm0
0x140002a5e  mov     [rdi+0D0h], rsi
0x140002a65  mov     [rdi+0D8h], ebp
0x140002a6b  mov     [rdi+0DCh], r13d
0x140002a72  mov     r9d, [rdi+70h]
0x140002a76  movzx   ecx, byte ptr [rdi+3Eh]
0x140002a7a  cmp     r8d, r9d
0x140002a7d  ja      short loc_140002A84
0x140002a7f  sub     r13d, ebp
0x140002a82  jmp     short loc_140002A87
0x140002a84  mov     r13d, r14d
0x140002a87  movzx   eax, cl
0x140002a8a  or      cl, 2
0x140002a8d  and     al, 0FDh
0x140002a8f  movzx   ecx, cl
0x140002a92  cmp     r8d, r9d
0x140002a95  movzx   eax, al
0x140002a98  cmova   ecx, eax
0x140002a9b  lea     rax, [rbx+510h]
0x140002aa2  mov     [rdi+3Eh], cl
0x140002aa5  mov     [rdi+74h], r13d
0x140002aa9  mov     rcx, [rax+8]
0x140002aad  cmp     [rcx], rax
0x140002ab0  jz      short loc_140002AB9
0x140002ab2  mov     ecx, 3
0x140002ab7  int     29h; Win8: RtlFailFast(ecx)
0x140002ab9  mov     [rdx], rax
0x140002abc  mov     [rdx+8], rcx
0x140002ac0  mov     [rcx], rdx
0x140002ac3  mov     [rax+8], rdx
0x140002ac7  jmp     loc_140002CA7
0x140002acc  mov     ecx, [rbx+520h]
0x140002ad2  mov     eax, [rbx+478h]
0x140002ad8  sub     ecx, eax
0x140002ada  cmp     [rbx+574h], ecx
0x140002ae0  jbe     loc_140002D7E
0x140002ae6  mov     rax, [rbx]
0x140002ae9  mov     ecx, r13d
0x140002aec  sub     ecx, ebp
0x140002aee  cmp     ecx, [rax+6C8h]
0x140002af4  ja      loc_140002D62
0x140002afa  cmp     edx, 9
0x140002afd  jz      short loc_140002B07
0x140002aff  mov     esi, r14d
0x140002b02  mov     edi, r14d
0x140002b05  jmp     short loc_140002B37
0x140002b07  cmp     ebp, 18h
0x140002b0a  jb      loc_140002D3F
0x140002b10  mov     esi, [rsi+14h]
0x140002b13  test    esi, esi
0x140002b15  jz      loc_140002D3F
0x140002b1b  lea     edi, [rbp-18h]
0x140002b1e  mov     eax, edi
0x140002b20  shr     eax, 3
0x140002b23  cmp     esi, eax
0x140002b25  ja      loc_140002D3F
0x140002b2b  lea     eax, ds:0[rsi*8]
0x140002b32  sub     edi, eax
0x140002b34  shr     edi, 3
0x140002b37  lea     eax, [rsi+rsi*2]
0x140002b3a  mov     r15d, esi
0x140002b3d  lea     ecx, [rdi+rax*2]
0x140002b40  shl     r15d, 4
0x140002b44  lea     r12d, ds:0Fh[rcx*8]
0x140002b4c  mov     ecx, [rbx+570h]
0x140002b52  and     r12d, 0FFFFFFF0h
0x140002b56  lea     r14d, [r13+0Fh]
0x140002b5a  add     ecx, r12d
0x140002b5d  and     r14d, 0FFFFFFF0h
0x140002b61  add     ecx, r15d
0x140002b64  add     ecx, r14d
0x140002b67  test    byte ptr [rsp+0E8h+var_4A], 1
0x140002b6f  lea     ebp, [rcx+0A0h]
0x140002b75  jz      short loc_140002B94
0x140002b77  cmp     byte ptr [rbx+4B3h], 0
0x140002b7e  mov     eax, [rbx+5ACh]
0x140002b84  jz      short loc_140002B8A
0x140002b86  add     ebp, eax
0x140002b88  jmp     short loc_140002B94
0x140002b8a  cmp     ecx, eax
0x140002b8c  jnb     short loc_140002B94
0x140002b8e  lea     ebp, [rax+0A0h]
0x140002b94  cmp     ebp, [rbx+5A8h]
0x140002b9a  ja      loc_140002D12
0x140002ba0  mov     rax, [rbx+5A0h]
0x140002ba7  lea     ecx, [rbp-1]
0x140002baa  shr     rcx, 0Ah
0x140002bae  add     rax, 40h ; '@'
0x140002bb2  shl     rcx, 7
0x140002bb6  add     rcx, rax; Lookaside
0x140002bb9  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140002bc0  nop     dword ptr [rax+rax+00h]
0x140002bc5  mov     rcx, rax
0x140002bc8  test    rax, rax
0x140002bcb  jz      short loc_140002BD3
0x140002bcd  mov     byte ptr [rax+10h], 0
0x140002bd1  jmp     short loc_140002BE9
0x140002bd3  xor     ecx, ecx
0x140002bd5  xchg    rcx, [rbx+5B8h]
0x140002bdc  test    rcx, rcx
0x140002bdf  jz      loc_140002D02
0x140002be5  mov     byte ptr [rcx+10h], 1
0x140002be9  mov     eax, [rcx+8]
0x140002bec  lea     rdx, [rbx+510h]
0x140002bf3  movups  xmm0, [rsp+0E8h+var_98]
0x140002bf8  sub     eax, ebp
0x140002bfa  add     [rbx+568h], rax
  ... truncated ...
```
