# DlrmProcessReadWriteRequest

- ea: `0x1401404ac`
- end: `0x140140800`
- name: `DlrmProcessReadWriteRequest`
- size: `852`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140008eb0`
- `0x1400604a0`

## callees

- `0x1400290b0`
- `0x14013fcf4`
- `0x1401404ac`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1401404d5`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14014065c`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1401407bb`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1401404d5`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14014065c`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1401407bb`
- `ntoskrnl!KeSetEvent` at `0x140140636`
- `ntoskrnl!KeSetEvent` at `0x1401407a7`
- `ntoskrnl!KeSetEvent` at `0x140140636`
- `ntoskrnl!KeSetEvent` at `0x1401407a7`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x1401405a3`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x140140714`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x1401405a3`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x140140714`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x14014061c`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x14014078d`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x14014061c`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x14014078d`

## pseudocode

```c
LONG __fastcall DlrmProcessReadWriteRequest(__int64 *a1, unsigned int a2)
{
  LONG result; // eax
  __int64 v3; // rsi
  ULONGLONG UnbiasedInterruptTime; // rax
  __int64 v6; // rdi
  int v7; // r10d
  ULONGLONG v8; // rbp
  __int64 v9; // r8
  unsigned __int64 v10; // r8
  unsigned __int64 v11; // rdx
  unsigned int i; // r9d
  __int64 v13; // rcx
  PLIST_ENTRY Pool; // rax
  __int64 v15; // rax
  __int64 v16; // r9
  unsigned int j; // edx
  __int64 v18; // rcx
  unsigned __int64 v19; // r8
  unsigned __int64 v20; // rdx
  unsigned int k; // r9d
  __int64 v22; // rcx
  PLIST_ENTRY v23; // rax
  __int64 v24; // r9
  __int64 v25; // r9
  unsigned int m; // edx
  __int64 v27; // rcx
  signed __int32 v28[18]; // [rsp+0h] [rbp-48h] BYREF

  result = *((_DWORD *)a1 + 7);
  v3 = a2;
  if ( result )
  {
    result = *((_DWORD *)a1 + 18);
    if ( !result )
    {
      UnbiasedInterruptTime = KeQueryUnbiasedInterruptTime();
      v6 = *((int *)a1 + 16);
      v7 = *((_DWORD *)a1 + 9);
      v8 = UnbiasedInterruptTime;
      LODWORD(UnbiasedInterruptTime) = HIDWORD(KeGetPcr()[1].LockArray);
      v9 = 2LL * ((unsigned int)UnbiasedInterruptTime % *((_DWORD *)a1 + 6));
      *(_QWORD *)(a1[2] + 8 * v9) = v3
                                  + *(_QWORD *)(a1[2]
                                              + 16LL * ((unsigned int)UnbiasedInterruptTime % *((_DWORD *)a1 + 6)));
      *(_QWORD *)(a1[2] + 8 * v9 + 8) += v3;
      if ( (int)v6 < v7 )
      {
        if ( (unsigned int)v6 > 5 )
          v10 = 0;
        else
          v10 = a1[v6 + 32] * *((unsigned __int16 *)a1 + 34);
        v11 = 0;
        for ( i = 0; i < *((_DWORD *)a1 + 6); v11 += *(_QWORD *)(a1[2] + 16 * v13) )
          v13 = i++;
        if ( v11 >> 10 >= v10 )
        {
          result = _InterlockedCompareExchange((volatile signed __int32 *)a1 + 18, 1, 0);
          if ( result )
            return result;
          if ( !*a1 )
            goto LABEL_20;
          Pool = ExInterlockedRemoveHeadList((PLIST_ENTRY)a1 + 13, (PKSPIN_LOCK)a1 + 28);
          if ( !Pool )
          {
            v15 = *a1;
            if ( *a1 && (*(_DWORD *)v15 == 1094997074 || *(_DWORD *)v15 == 1314275652) )
              v16 = *(_QWORD *)(v15 + 8);
            else
              v16 = 0;
            Pool = (PLIST_ENTRY)RaidAllocatePool(64, 24, 1296851282, v16);
            if ( !Pool )
            {
              ++*((_DWORD *)a1 + 131);
LABEL_20:
              *((_DWORD *)a1 + 18) = 0;
              goto LABEL_26;
            }
            ++*((_DWORD *)a1 + 130);
            BYTE4(Pool[1].Flink) |= 1u;
          }
          LODWORD(Pool[1].Flink) = 1;
          ExInterlockedInsertTailList((PLIST_ENTRY)(a1 + 29), Pool, (PKSPIN_LOCK)a1 + 31);
          _InterlockedOr(v28, 0);
          result = KeSetEvent((PRKEVENT)(a1 + 5), 0, 0);
          ++*((_DWORD *)a1 + 110);
          return result;
        }
        if ( v8 - a1[10] >= g_DlrmScaleUpTimeWindow100ns )
        {
          a1[10] = KeQueryUnbiasedInterruptTime();
          for ( j = 0; j < *((_DWORD *)a1 + 6); *(_QWORD *)(a1[2] + 16 * v18) = 0 )
            v18 = j++;
        }
      }
LABEL_26:
      if ( (int)v6 <= 1 || v8 - a1[11] < g_DlrmScaleDownTimeWindow100ns )
        return DlrmCheckAndUpdateTimeBasedTelemetry(a1, v8);
      if ( (int)v6 >= 6 )
        v19 = 0;
      else
        v19 = a1[v6 + 38] * *((unsigned __int16 *)a1 + 34);
      v20 = 0;
      for ( k = 0; k < *((_DWORD *)a1 + 6); v20 += *(_QWORD *)(a1[2] + 16 * v22 + 8) )
        v22 = k++;
      if ( v20 >> 10 > v19 )
      {
        a1[11] = KeQueryUnbiasedInterruptTime();
        for ( m = 0; m < *((_DWORD *)a1 + 6); *(_QWORD *)(a1[2] + 16 * v27 + 8) = 0 )
          v27 = m++;
        return DlrmCheckAndUpdateTimeBasedTelemetry(a1, v8);
      }
      result = _InterlockedCompareExchange((volatile signed __int32 *)a1 + 18, 1, 0);
      if ( result )
        return result;
      if ( *a1 )
      {
        v23 = ExInterlockedRemoveHeadList((PLIST_ENTRY)a1 + 13, (PKSPIN_LOCK)a1 + 28);
        if ( !v23 )
        {
          v24 = *a1;
          if ( *a1 && (*(_DWORD *)v24 == 1094997074 || *(_DWORD *)v24 == 1314275652) )
            v25 = *(_QWORD *)(v24 + 8);
          else
            v25 = 0;
          v23 = (PLIST_ENTRY)RaidAllocatePool(64, 24, 1296851282, v25);
          if ( !v23 )
          {
            ++*((_DWORD *)a1 + 131);
            goto LABEL_44;
          }
          ++*((_DWORD *)a1 + 130);
          BYTE4(v23[1].Flink) |= 1u;
        }
        LODWORD(v23[1].Flink) = 3;
        ExInterlockedInsertTailList((PLIST_ENTRY)(a1 + 29), v23, (PKSPIN_LOCK)a1 + 31);
        _InterlockedOr(v28, 0);
        result = KeSetEvent((PRKEVENT)(a1 + 5), 0, 0);
        ++*((_DWORD *)a1 + 111);
        return result;
      }
LABEL_44:
      *((_DWORD *)a1 + 18) = 0;
      return DlrmCheckAndUpdateTimeBasedTelemetry(a1, v8);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1401404ac  push    rbx
0x1401404ae  push    rbp
0x1401404af  push    rsi
0x1401404b0  push    rdi
0x1401404b1  push    r14
0x1401404b3  sub     rsp, 20h
0x1401404b7  mov     eax, [rcx+1Ch]
0x1401404ba  xor     r14d, r14d
0x1401404bd  mov     esi, edx
0x1401404bf  mov     rbx, rcx
0x1401404c2  test    eax, eax
0x1401404c4  jz      loc_1401407F4
0x1401404ca  mov     eax, [rcx+48h]
0x1401404cd  test    eax, eax
0x1401404cf  jnz     loc_1401407F4
0x1401404d5  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x1401404dc  nop     dword ptr [rax+rax+00h]
0x1401404e1  movsxd  rdi, dword ptr [rbx+40h]
0x1401404e5  xor     edx, edx
0x1401404e7  mov     r10d, [rbx+24h]
0x1401404eb  mov     rbp, rax
0x1401404ee  mov     eax, gs:1A4h
0x1401404f6  div     dword ptr [rbx+18h]
0x1401404f9  mov     rcx, [rbx+10h]
0x1401404fd  mov     r8d, edx
0x140140500  add     r8, r8
0x140140503  mov     rcx, [rcx+r8*8]
0x140140507  mov     rax, [rbx+10h]
0x14014050b  add     rcx, rsi
0x14014050e  mov     [rax+r8*8], rcx
0x140140512  mov     rax, [rbx+10h]
0x140140516  mov     rdx, [rax+r8*8+8]
0x14014051b  mov     rax, [rbx+10h]
0x14014051f  add     rdx, rsi
0x140140522  lea     esi, [r14+1]
0x140140526  mov     [rax+r8*8+8], rdx
0x14014052b  cmp     edi, r10d
0x14014052e  jge     loc_140140689
0x140140534  mov     r10, [rbx+50h]
0x140140538  cmp     edi, 5
0x14014053b  ja      short loc_14014054D
0x14014053d  movzx   r8d, word ptr [rbx+44h]
0x140140542  imul    r8, [rbx+rdi*8+100h]
0x14014054b  jmp     short loc_140140550
0x14014054d  mov     r8, r14
0x140140550  mov     rdx, r14
0x140140553  mov     r9d, r14d
0x140140556  cmp     [rbx+18h], r14d
0x14014055a  jbe     short loc_140140576
0x14014055c  mov     rax, [rbx+10h]
0x140140560  mov     ecx, r9d
0x140140563  add     r9d, esi
0x140140566  add     rcx, rcx
0x140140569  mov     rcx, [rax+rcx*8]
0x14014056d  add     rdx, rcx
0x140140570  cmp     r9d, [rbx+18h]
0x140140574  jb      short loc_14014055C
0x140140576  shr     rdx, 0Ah
0x14014057a  cmp     rdx, r8
0x14014057d  jb      loc_14014064D
0x140140583  xor     eax, eax
0x140140585  lock cmpxchg [rbx+48h], esi
0x14014058a  jnz     loc_1401407F4
0x140140590  cmp     [rbx], r14
0x140140593  jz      short loc_1401405F5
0x140140595  lea     rdx, [rbx+0E0h]; Lock
0x14014059c  lea     rcx, [rbx+0D0h]; ListHead
0x1401405a3  call    cs:__imp_ExInterlockedRemoveHeadList
0x1401405aa  nop     dword ptr [rax+rax+00h]
0x1401405af  test    rax, rax
0x1401405b2  jnz     short loc_140140608
0x1401405b4  mov     rax, [rbx]
0x1401405b7  test    rax, rax
0x1401405ba  jz      short loc_1401405D4
0x1401405bc  mov     ecx, [rax]
0x1401405be  cmp     ecx, 41445452h
0x1401405c4  jnz     short loc_1401405CC
0x1401405c6  mov     r9, [rax+8]
0x1401405ca  jmp     short loc_1401405D7
0x1401405cc  cmp     ecx, 4E564144h
0x1401405d2  jz      short loc_1401405C6
0x1401405d4  mov     r9, r14
0x1401405d7  mov     edx, 18h
0x1401405dc  mov     r8d, 4D4C6152h
0x1401405e2  lea     ecx, [rdx+28h]
0x1401405e5  call    RaidAllocatePool
0x1401405ea  test    rax, rax
0x1401405ed  jnz     short loc_1401405FE
0x1401405ef  add     [rbx+20Ch], esi
0x1401405f5  mov     [rbx+48h], r14d
0x1401405f9  jmp     loc_140140689
0x1401405fe  add     [rbx+208h], esi
0x140140604  or      [rax+14h], sil
0x140140608  lea     r8, [rbx+0F8h]; Lock
0x14014060f  mov     [rax+10h], esi
0x140140612  lea     rcx, [rbx+0E8h]; ListHead
0x140140619  mov     rdx, rax; ListEntry
0x14014061c  call    cs:__imp_ExInterlockedInsertTailList
0x140140623  nop     dword ptr [rax+rax+00h]
0x140140628  lock or [rsp+48h+var_48], r14d
0x14014062d  lea     rcx, [rbx+28h]; Event
0x140140631  xor     r8d, r8d; Wait
0x140140634  xor     edx, edx; Increment
0x140140636  call    cs:__imp_KeSetEvent
0x14014063d  nop     dword ptr [rax+rax+00h]
0x140140642  add     [rbx+1B8h], esi
0x140140648  jmp     loc_1401407F4
0x14014064d  mov     rax, rbp
0x140140650  sub     rax, r10
0x140140653  cmp     rax, cs:g_DlrmScaleUpTimeWindow100ns
0x14014065a  jb      short loc_140140689
0x14014065c  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x140140663  nop     dword ptr [rax+rax+00h]
0x140140668  mov     [rbx+50h], rax
0x14014066c  mov     edx, r14d
0x14014066f  cmp     [rbx+18h], r14d
0x140140673  jbe     short loc_140140689
0x140140675  mov     rax, [rbx+10h]
0x140140679  mov     ecx, edx
0x14014067b  add     edx, esi
0x14014067d  add     rcx, rcx
0x140140680  mov     [rax+rcx*8], r14
0x140140684  cmp     edx, [rbx+18h]
0x140140687  jb      short loc_140140675
0x140140689  cmp     edi, esi
0x14014068b  jle     loc_1401407E9
0x140140691  mov     rax, [rbx+58h]
0x140140695  mov     rcx, rbp
0x140140698  sub     rcx, rax
0x14014069b  cmp     rcx, cs:g_DlrmScaleDownTimeWindow100ns
0x1401406a2  jb      loc_1401407E9
0x1401406a8  cmp     edi, 6
0x1401406ab  jge     short loc_1401406BD
0x1401406ad  movzx   r8d, word ptr [rbx+44h]
0x1401406b2  imul    r8, [rbx+rdi*8+130h]
0x1401406bb  jmp     short loc_1401406C0
0x1401406bd  mov     r8, r14
0x1401406c0  mov     rdx, r14
0x1401406c3  mov     r9d, r14d
0x1401406c6  cmp     [rbx+18h], r14d
0x1401406ca  jbe     short loc_1401406E7
0x1401406cc  mov     rax, [rbx+10h]
0x1401406d0  mov     ecx, r9d
0x1401406d3  add     r9d, esi
0x1401406d6  add     rcx, rcx
0x1401406d9  mov     rcx, [rax+rcx*8+8]
0x1401406de  add     rdx, rcx
0x1401406e1  cmp     r9d, [rbx+18h]
0x1401406e5  jb      short loc_1401406CC
0x1401406e7  shr     rdx, 0Ah
0x1401406eb  cmp     rdx, r8
0x1401406ee  ja      loc_1401407BB
0x1401406f4  xor     eax, eax
0x1401406f6  lock cmpxchg [rbx+48h], esi
0x1401406fb  jnz     loc_1401407F4
0x140140701  cmp     [rbx], r14
0x140140704  jz      short loc_140140765
0x140140706  lea     rdx, [rbx+0E0h]; Lock
0x14014070d  lea     rcx, [rbx+0D0h]; ListHead
0x140140714  call    cs:__imp_ExInterlockedRemoveHeadList
0x14014071b  nop     dword ptr [rax+rax+00h]
0x140140720  test    rax, rax
0x140140723  jnz     short loc_140140775
0x140140725  mov     r9, [rbx]
0x140140728  test    r9, r9
0x14014072b  jz      short loc_140140744
0x14014072d  mov     eax, [r9]
0x140140730  cmp     eax, 41445452h
0x140140735  jnz     short loc_14014073D
0x140140737  mov     r9, [r9+8]
0x14014073b  jmp     short loc_140140747
0x14014073d  cmp     eax, 4E564144h
0x140140742  jz      short loc_140140737
0x140140744  mov     r9, r14
0x140140747  mov     edx, 18h
0x14014074c  mov     r8d, 4D4C6152h
0x140140752  lea     ecx, [rdx+28h]
0x140140755  call    RaidAllocatePool
0x14014075a  test    rax, rax
0x14014075d  jnz     short loc_14014076B
0x14014075f  add     [rbx+20Ch], esi
0x140140765  mov     [rbx+48h], r14d
0x140140769  jmp     short loc_1401407E9
0x14014076b  add     [rbx+208h], esi
0x140140771  or      [rax+14h], sil
0x140140775  lea     r8, [rbx+0F8h]; Lock
0x14014077c  mov     dword ptr [rax+10h], 3
0x140140783  lea     rcx, [rbx+0E8h]; ListHead
0x14014078a  mov     rdx, rax; ListEntry
0x14014078d  call    cs:__imp_ExInterlockedInsertTailList
0x140140794  nop     dword ptr [rax+rax+00h]
0x140140799  lock or [rsp+48h+var_48], r14d
0x14014079e  lea     rcx, [rbx+28h]; Event
0x1401407a2  xor     r8d, r8d; Wait
0x1401407a5  xor     edx, edx; Increment
0x1401407a7  call    cs:__imp_KeSetEvent
0x1401407ae  nop     dword ptr [rax+rax+00h]
0x1401407b3  add     [rbx+1BCh], esi
0x1401407b9  jmp     short loc_1401407F4
0x1401407bb  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x1401407c2  nop     dword ptr [rax+rax+00h]
0x1401407c7  mov     [rbx+58h], rax
0x1401407cb  mov     edx, r14d
0x1401407ce  cmp     [rbx+18h], r14d
0x1401407d2  jbe     short loc_1401407E9
0x1401407d4  mov     rax, [rbx+10h]
0x1401407d8  mov     ecx, edx
0x1401407da  add     edx, esi
0x1401407dc  add     rcx, rcx
0x1401407df  mov     [rax+rcx*8+8], r14
0x1401407e4  cmp     edx, [rbx+18h]
0x1401407e7  jb      short loc_1401407D4
0x1401407e9  mov     rdx, rbp
0x1401407ec  mov     rcx, rbx
0x1401407ef  call    DlrmCheckAndUpdateTimeBasedTelemetry
0x1401407f4  add     rsp, 20h
0x1401407f8  pop     r14
0x1401407fa  pop     rdi
0x1401407fb  pop     rsi
0x1401407fc  pop     rbp
0x1401407fd  pop     rbx
0x1401407fe  retn
```
