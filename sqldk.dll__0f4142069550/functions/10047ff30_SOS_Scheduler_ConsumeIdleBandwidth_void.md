# SOS_Scheduler::ConsumeIdleBandwidth(void)

- ea: `0x10047ff30`
- end: `0x10048048e`
- name: `?ConsumeIdleBandwidth@SOS_Scheduler@@AEAAXXZ`
- size: `1374`
- prototype: `void __fastcall(SOS_Scheduler *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update`

## callers

- `0x100402f20`

## callees

- `0x100401230`
- `0x100401810`
- `0x1004020b0`
- `0x100402600`
- `0x100404160`
- `0x100424ef0`
- `0x10047ff30`
- `0x100488a00`
- `0x100585bd0`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x1004801b2`
- `KERNEL32!WaitForSingleObject` at `0x1004801b2`
- `KERNEL32!SwitchToThread` at `0x1004801ba`
- `KERNEL32!SwitchToThread` at `0x1004801ba`
- `KERNEL32!QueryPerformanceCounter` at `0x10047ffa0`
- `KERNEL32!QueryPerformanceCounter` at `0x10048012c`
- `KERNEL32!QueryPerformanceCounter` at `0x1004801da`
- `KERNEL32!QueryPerformanceCounter` at `0x100480465`
- `KERNEL32!QueryPerformanceCounter` at `0x10047ffa0`
- `KERNEL32!QueryPerformanceCounter` at `0x10048012c`
- `KERNEL32!QueryPerformanceCounter` at `0x1004801da`
- `KERNEL32!QueryPerformanceCounter` at `0x100480465`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100480099`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100480099`

## pseudocode

```c
void __fastcall SOS_Scheduler::ConsumeIdleBandwidth(SOS_Scheduler *this, __int64 a2, signed __int64 a3)
{
  __int64 v4; // r9
  __int64 v5; // rax
  LARGE_INTEGER v6; // rcx
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // r8
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rcx
  unsigned __int64 v13; // r12
  unsigned __int64 v14; // r14
  LARGE_INTEGER v15; // rdi
  LARGE_INTEGER v16; // r8
  int v17; // r13d
  int v18; // edi
  unsigned __int64 v19; // r15
  LARGE_INTEGER v20; // rbx
  unsigned __int64 v21; // r10
  unsigned __int64 v22; // rcx
  unsigned __int64 v23; // r9
  unsigned __int64 v24; // r9
  unsigned __int64 v25; // rax
  __int64 v26; // r9
  __int64 v27; // r9
  __int64 v28; // rbx
  LONGLONG v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rcx
  LARGE_INTEGER v32; // rax
  LARGE_INTEGER v33; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v34; // [rsp+38h] [rbp-C8h]
  LARGE_INTEGER v35; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v36; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v37; // [rsp+58h] [rbp-A8h]
  SOS_Scheduler *v38; // [rsp+60h] [rbp-A0h]
  int v39; // [rsp+68h] [rbp-98h]
  LARGE_INTEGER v40; // [rsp+70h] [rbp-90h]
  __int64 v41; // [rsp+78h] [rbp-88h]
  __int64 v42; // [rsp+80h] [rbp-80h]
  __int64 v43; // [rsp+88h] [rbp-78h]
  __int64 v44; // [rsp+90h] [rbp-70h]
  int v45; // [rsp+98h] [rbp-68h]
  int v46; // [rsp+9Ch] [rbp-64h]
  int v47; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v48; // [rsp+A8h] [rbp-58h]
  __int64 v49; // [rsp+B0h] [rbp-50h]
  __int64 v50; // [rsp+B8h] [rbp-48h]
  __int64 v51; // [rsp+C0h] [rbp-40h]
  _BYTE v52[216]; // [rsp+D0h] [rbp-30h] BYREF
  int v53; // [rsp+1A8h] [rbp+A8h]
  __int64 v54; // [rsp+1B0h] [rbp+B0h]
  LARGE_INTEGER v55; // [rsp+208h] [rbp+108h]
  LARGE_INTEGER PerformanceCount; // [rsp+210h] [rbp+110h] BYREF
  LARGE_INTEGER v57; // [rsp+218h] [rbp+118h] BYREF

  v4 = 0x624DD2F1A9FBE77LL;
  if ( dword_100715790 != 1 || *((_DWORD *)this + 922) >= 0x100000u )
  {
    if ( (byte_1007149B3 & 0x20) != 0 )
      return;
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
    {
      QueryPerformanceCounter(&PerformanceCount);
      v6 = PerformanceCount;
      v4 = 0x624DD2F1A9FBE77LL;
    }
    else
    {
      v6.QuadPart = MEMORY[0x7FFE0008];
    }
    v7 = *((_QWORD *)this + 659);
    if ( v6.QuadPart < v7 )
    {
      v8 = 0;
    }
    else
    {
      v8 = v6.QuadPart - v7;
      if ( v8 == -1 )
      {
        v9 = -1;
LABEL_15:
        v10 = *((unsigned int *)this + 1320);
        a3 = v10 * (SOS_PublicGlobals::sm_CpuTicksPerMillisecond * v9 / 0x3E8);
        *((_QWORD *)this + 657) += a3 / (unsigned int)(6400 - v10);
        v5 = *((_QWORD *)this + 657);
        goto LABEL_16;
      }
    }
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
      v9 = 1000000 * v8 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
    else
      v9 = v8 / 0xA;
    goto LABEL_15;
  }
  v5 = *((_QWORD *)this + 446);
  *((_QWORD *)this + 657) = v5;
LABEL_16:
  if ( v5 <= 0 )
    goto LABEL_65;
  *((_DWORD *)this + 1321) = 1;
  if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
  {
    v11 = rand();
    a3 = (unsigned int)v11;
    if ( v11 == 5 * (v11 / 5) )
      Spinlock<18,1,268435714>::UpdateStatSnapshot();
  }
  *((_QWORD *)this + 466) = 0;
  v12 = *((_QWORD *)this + 640);
  if ( (*(_DWORD *)(v12 + 800) & 0x1004) != 4 )
    SOS_Scheduler::TaskTransition(v12, 2, a3, v4);
  _InterlockedIncrement64((volatile signed __int64 *)this + 458);
  v13 = *((_QWORD *)this + 657);
  if ( v13 >= *((_QWORD *)this + 446) )
    v13 = *((_QWORD *)this + 446);
  v14 = __rdtsc();
  v34 = *((_QWORD *)this + 658);
  if ( Base_PublicGlobals::sm_invariantTscAvailable )
  {
    QueryPerformanceCounter(&v57);
    v15 = v57;
  }
  else
  {
    v15.QuadPart = MEMORY[0x7FFE0008];
  }
  v16 = v15;
  v55 = v15;
  v47 = 536871045;
  v48 = 0;
  v50 = 0;
  v49 = 0;
  v51 = 0;
  v35 = v15;
  if ( (SOS_PublicGlobals::sm_osStats & 4) != 0 )
    ++*((_QWORD *)this + 2099);
  v17 = byte_1007149B3 & 0x80;
  v18 = byte_1007149B4 & 4;
  do
  {
    v19 = v14;
    v20 = v16;
    if ( v18 )
      SwitchToThread();
    else
      WaitForSingleObject(*((HANDLE *)this + 465), v13 / SOS_PublicGlobals::sm_CpuTicksPerMillisecond);
    v14 = __rdtsc();
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
    {
      QueryPerformanceCounter(&v33);
      v16 = v33;
    }
    else
    {
      v16.QuadPart = MEMORY[0x7FFE0008];
    }
    v21 = v14 - v19;
    if ( v16.QuadPart < (unsigned __int64)v20.QuadPart )
    {
      v22 = 0;
    }
    else
    {
      v22 = v16.QuadPart - v20.QuadPart;
      if ( v16.QuadPart - v20.QuadPart == -1 )
      {
        v23 = -1;
        goto LABEL_43;
      }
    }
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
      v23 = 1000000 * v22 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
    else
      v23 = v22 / 0xA;
LABEL_43:
    v24 = SOS_PublicGlobals::sm_CpuTicksPerMillisecond * v23 / 0x3E8;
    if ( !v24 )
      v24 = SOS_PublicGlobals::sm_CpuTicksPerMillisecond;
    v25 = v13;
    if ( v21 > v24 << 10 )
      v21 = v24;
    v26 = *((_QWORD *)this + 658);
    *((_QWORD *)this + 657) -= v21;
    v27 = v21 + v26;
    *((_QWORD *)this + 658) = v27;
    if ( v21 < v13 )
      v25 = v21;
    v13 -= v25;
  }
  while ( v13 && v17 );
  v28 = *((_QWORD *)this + 11299);
  v29 = 0;
  if ( v16.QuadPart >= (unsigned __int64)v55.QuadPart )
    v29 = v16.QuadPart - v55.QuadPart;
  *((_QWORD *)this + 767) = v29;
  if ( v28 && (SOS_PublicGlobals::sm_osStats & 0x40) != 0 )
  {
    v30 = *((_QWORD *)this + 640);
    v37 = 0;
    v38 = this;
    v36 = 0;
    v45 = (v27 - v34) / SOS_PublicGlobals::sm_CpuTicksPerMillisecond;
    v39 = 15;
    v40 = v16;
    v41 = v30;
    v42 = 0;
    v43 = 0;
    v44 = 0;
    v46 = 0;
    v53 = 0;
    v54 = 0;
    if ( *(_QWORD *)(v28 + 64) )
      StackFrames<24>::CaptureCurrent(v52, 1);
    if ( (g_XeSosPkg_enabledBitmap & 0x80000) != 0 )
      SOS_SchedulerRingRecord::FireMatchingEvent(&v36, v52);
    SOS_RingBuffer::StoreRecordInternalWithoutEvent(v28, &v36, v52);
  }
  if ( (SOS_PublicGlobals::sm_osStats & 4) != 0 )
    SOS_Scheduler::UpdateWaitTimeStats((_DWORD)this, (unsigned int)&v47, *((_QWORD *)this + 640), 0, (__int64)&v35);
  v31 = *((_QWORD *)this + 640);
  if ( (*(_DWORD *)(v31 + 800) & 0x1004) != 4 )
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))SOS_Scheduler::TaskTransition)(
      v31,
      0,
      (LARGE_INTEGER)v16.QuadPart,
      v27);
  _InterlockedIncrement((volatile signed __int32 *)this + 1296);
  SOS_Scheduler::GetLock(this);
  *((_DWORD *)this + 1321) = 0;
LABEL_65:
  ++*((_DWORD *)this + 1297);
  if ( (dword_100715790 != 1 || *((_DWORD *)this + 922) >= 0x100000u)
    && (*((_DWORD *)this + 936) || *((__int64 *)this + 657) > 0) )
  {
    if ( *((_QWORD *)this + 664) )
    {
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&PerformanceCount);
        v32 = PerformanceCount;
      }
      else
      {
        v32.QuadPart = MEMORY[0x7FFE0008];
      }
      *((LARGE_INTEGER *)this + 659) = v32;
    }
    else
    {
      SOS_Scheduler::EnqueueIdleConsumer(this);
    }
  }
}

```

## disassembly

```asm
0x10047ff30  push    rbp
0x10047ff32  push    rbx
0x10047ff33  push    rsi
0x10047ff34  lea     rbp, [rsp-0E0h]
0x10047ff3c  sub     rsp, 1E0h
0x10047ff43  xor     ebx, ebx
0x10047ff45  mov     rsi, rcx
0x10047ff48  cmp     cs:dword_100715790, 1
0x10047ff4f  mov     rdx, 0CCCCCCCCCCCCCCCDh
0x10047ff59  mov     r9, 624DD2F1A9FBE77h
0x10047ff63  jnz     short loc_10047FF84
0x10047ff65  cmp     dword ptr [rcx+0E68h], 100000h
0x10047ff6f  jnb     short loc_10047FF84
0x10047ff71  mov     rax, [rcx+0DF0h]
0x10047ff78  mov     [rcx+1488h], rax
0x10047ff7f  jmp     loc_100480056
0x10047ff84  test    cs:byte_1007149B3, 20h
0x10047ff8b  jnz     loc_100480483
0x10047ff91  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, ebx; int Base_PublicGlobals::sm_invariantTscAvailable
0x10047ff97  jz      short loc_10047FFC3
0x10047ff99  lea     rcx, [rbp+0F0h+PerformanceCount]; lpPerformanceCount
0x10047ffa0  call    cs:__imp_QueryPerformanceCounter
0x10047ffa6  mov     rcx, qword ptr [rbp+0F0h+PerformanceCount]
0x10047ffad  mov     rdx, 0CCCCCCCCCCCCCCCDh
0x10047ffb7  mov     r9, 624DD2F1A9FBE77h
0x10047ffc1  jmp     short loc_10047FFCB
0x10047ffc3  mov     rcx, ds:7FFE0008h
0x10047ffcb  mov     rax, [rsi+1498h]
0x10047ffd2  cmp     rcx, rax
0x10047ffd5  jb      short loc_10047FFE5
0x10047ffd7  sub     rcx, rax
0x10047ffda  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x10047ffde  jnz     short loc_10047FFE8
0x10047ffe0  mov     r8, rcx
0x10047ffe3  jmp     short loc_100480012
0x10047ffe5  mov     rcx, rbx
0x10047ffe8  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, ebx; int Base_PublicGlobals::sm_invariantTscAvailable
0x10047ffee  jz      short loc_100480005
0x10047fff0  imul    rax, rcx, 0F4240h
0x10047fff7  xor     edx, edx
0x10047fff9  div     cs:?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A; _LARGE_INTEGER Base_PublicGlobals::sm_QueryPerformanceFrequency
0x100480000  mov     r8, rax
0x100480003  jmp     short loc_100480012
0x100480005  mov     rax, rdx
0x100480008  mul     rcx
0x10048000b  mov     r8, rdx
0x10048000e  shr     r8, 3
0x100480012  imul    r8, cs:?sm_CpuTicksPerMillisecond@SOS_PublicGlobals@@2_KA; unsigned __int64 SOS_PublicGlobals::sm_CpuTicksPerMillisecond
0x10048001a  mov     ecx, [rsi+14A0h]
0x100480020  mov     rax, r9
0x100480023  mul     r8
0x100480026  mov     eax, 1900h
0x10048002b  sub     r8, rdx
0x10048002e  sub     eax, ecx
0x100480030  shr     r8, 1
0x100480033  add     r8, rdx
0x100480036  shr     r8, 9
0x10048003a  imul    r8, rcx
0x10048003e  mov     ecx, eax
0x100480040  mov     rax, r8
0x100480043  cqo
0x100480045  idiv    rcx
0x100480048  add     [rsi+1488h], rax
0x10048004f  mov     rax, [rsi+1488h]
0x100480056  test    rax, rax
0x100480059  jle     loc_10048040B
0x10048005f  mov     [rsp+1F0h+arg_0], rdi
0x100480067  mov     [rsp+1F0h+var_18], r12
0x10048006f  mov     [rsp+1F0h+var_20], r13
0x100480077  mov     dword ptr [rsi+14A4h], 1
0x100480081  cmp     cs:?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA, bl; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x100480087  mov     [rsp+1F0h+var_28], r14
0x10048008f  mov     [rsp+1F0h+var_30], r15
0x100480097  jz      short loc_1004800C0
0x100480099  call    cs:__imp_rand
0x10048009f  mov     r8d, eax
0x1004800a2  mov     eax, 66666667h
0x1004800a7  imul    r8d
0x1004800aa  sar     edx, 1
0x1004800ac  mov     ecx, edx
0x1004800ae  shr     ecx, 1Fh
0x1004800b1  add     edx, ecx
0x1004800b3  lea     ecx, [rdx+rdx*4]
0x1004800b6  cmp     r8d, ecx
0x1004800b9  jnz     short loc_1004800C0
0x1004800bb  call    ?UpdateStatSnapshot@?$Spinlock@$0BC@$00$0BAAAABAC@@@AEAAXXZ; Spinlock<18,1,268435714>::UpdateStatSnapshot(void)
0x1004800c0  mov     [rsi+0E90h], rbx
0x1004800c7  mov     rcx, [rsi+1400h]
0x1004800ce  mov     eax, [rcx+320h]
0x1004800d4  and     eax, 1004h
0x1004800d9  cmp     eax, 4
0x1004800dc  jz      short loc_1004800E8
0x1004800de  mov     edx, 2
0x1004800e3  call    ?TaskTransition@SOS_Scheduler@@SAXPEAVWorker@@W4Transition@1@@Z; SOS_Scheduler::TaskTransition(Worker *,SOS_Scheduler::Transition)
0x1004800e8  lock inc qword ptr [rsi+0E50h]
0x1004800f0  mov     r12, [rsi+1488h]
0x1004800f7  mov     rax, [rsi+0DF0h]
0x1004800fe  cmp     r12, rax
0x100480101  cmovnb  r12, rax
0x100480105  rdtsc
0x100480107  shl     rdx, 20h
0x10048010b  or      rax, rdx
0x10048010e  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, ebx; int Base_PublicGlobals::sm_invariantTscAvailable
0x100480114  mov     r14, rax
0x100480117  mov     rax, [rsi+1490h]
0x10048011e  mov     [rsp+1F0h+var_1B8], rax
0x100480123  jz      short loc_10048013B
0x100480125  lea     rcx, [rbp+0F0h+arg_18]; lpPerformanceCount
0x10048012c  call    cs:__imp_QueryPerformanceCounter
0x100480132  mov     rdi, qword ptr [rbp+0F0h+arg_18]
0x100480139  jmp     short loc_100480143
0x10048013b  mov     rdi, ds:7FFE0008h
0x100480143  test    byte ptr cs:?sm_osStats@SOS_PublicGlobals@@2KA, 4; ulong SOS_PublicGlobals::sm_osStats
0x10048014a  mov     r8, rdi
0x10048014d  mov     [rbp+0F0h+arg_8], rdi
0x100480154  mov     [rbp+0F0h+var_150], 20000085h
0x10048015b  mov     [rbp+0F0h+var_148], rbx
0x10048015f  mov     [rbp+0F0h+var_138], rbx
0x100480163  mov     [rbp+0F0h+var_140], rbx
0x100480167  mov     [rbp+0F0h+var_130], rbx
0x10048016b  mov     [rsp+1F0h+var_1B0], rdi
0x100480170  jz      short loc_100480179
0x100480172  inc     qword ptr [rsi+4198h]
0x100480179  movzx   r13d, cs:byte_1007149B3
0x100480181  movzx   edi, cs:byte_1007149B4
0x100480188  and     r13d, 80h
0x10048018f  and     edi, 4
0x100480192  mov     r15, r14
0x100480195  mov     rbx, r8
0x100480198  test    edi, edi
0x10048019a  jnz     short loc_1004801BA
0x10048019c  mov     rcx, [rsi+0E88h]; hHandle
0x1004801a3  xor     edx, edx
0x1004801a5  mov     rax, r12
0x1004801a8  div     cs:?sm_CpuTicksPerMillisecond@SOS_PublicGlobals@@2_KA; unsigned __int64 SOS_PublicGlobals::sm_CpuTicksPerMillisecond
0x1004801af  mov     rdx, rax; dwMilliseconds
0x1004801b2  call    cs:__imp_WaitForSingleObject
0x1004801b8  jmp     short loc_1004801C0
0x1004801ba  call    cs:__imp_SwitchToThread
0x1004801c0  rdtsc
0x1004801c2  shl     rdx, 20h
0x1004801c6  or      rax, rdx
0x1004801c9  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, 0; int Base_PublicGlobals::sm_invariantTscAvailable
0x1004801d0  mov     r14, rax
0x1004801d3  jz      short loc_1004801E7
0x1004801d5  lea     rcx, [rsp+1F0h+var_1C0]; lpPerformanceCount
0x1004801da  call    cs:__imp_QueryPerformanceCounter
0x1004801e0  mov     r8, qword ptr [rsp+1F0h+var_1C0]
0x1004801e5  jmp     short loc_1004801EF
0x1004801e7  mov     r8, ds:7FFE0008h
0x1004801ef  mov     r10, r14
0x1004801f2  sub     r10, r15
0x1004801f5  cmp     r8, rbx
0x1004801f8  jb      short loc_10048020B
0x1004801fa  mov     rcx, r8
0x1004801fd  sub     rcx, rbx
0x100480200  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x100480204  jnz     short loc_10048020D
0x100480206  mov     r9, rcx
0x100480209  jmp     short loc_10048023F
0x10048020b  xor     ecx, ecx
0x10048020d  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, 0; int Base_PublicGlobals::sm_invariantTscAvailable
0x100480214  jz      short loc_10048022B
0x100480216  imul    rax, rcx, 0F4240h
0x10048021d  xor     edx, edx
0x10048021f  div     cs:?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A; _LARGE_INTEGER Base_PublicGlobals::sm_QueryPerformanceFrequency
0x100480226  mov     r9, rax
0x100480229  jmp     short loc_10048023F
0x10048022b  mov     rax, 0CCCCCCCCCCCCCCCDh
0x100480235  mul     rcx
0x100480238  mov     r9, rdx
0x10048023b  shr     r9, 3
0x10048023f  imul    r9, cs:?sm_CpuTicksPerMillisecond@SOS_PublicGlobals@@2_KA; unsigned __int64 SOS_PublicGlobals::sm_CpuTicksPerMillisecond
0x100480247  mov     rax, 624DD2F1A9FBE77h
0x100480251  mul     r9
0x100480254  sub     r9, rdx
0x100480257  shr     r9, 1
0x10048025a  add     r9, rdx
0x10048025d  shr     r9, 9
0x100480261  test    r9, r9
0x100480264  cmovz   r9, cs:?sm_CpuTicksPerMillisecond@SOS_PublicGlobals@@2_KA; unsigned __int64 SOS_PublicGlobals::sm_CpuTicksPerMillisecond
0x10048026c  mov     rax, r9
0x10048026f  shl     rax, 0Ah
0x100480273  cmp     r10, rax
0x100480276  mov     rax, r12
0x100480279  cmova   r10, r9
0x10048027d  mov     r9, [rsi+1490h]
0x100480284  sub     [rsi+1488h], r10
0x10048028b  add     r9, r10
0x10048028e  cmp     r10, r12
0x100480291  mov     [rsi+1490h], r9
0x100480298  cmovb   rax, r10
0x10048029c  sub     r12, rax
0x10048029f  jz      short loc_1004802AA
0x1004802a1  test    r13d, r13d
0x1004802a4  jnz     loc_100480192
0x1004802aa  mov     rbx, [rsi+16118h]
0x1004802b1  xor     r14d, r14d
0x1004802b4  mov     r15, [rsp+1F0h+var_30]
0x1004802bc  mov     rcx, r8
0x1004802bf  sub     rcx, [rbp+0F0h+arg_8]
0x1004802c6  mov     eax, r14d
0x1004802c9  cmp     r8, [rbp+0F0h+arg_8]
0x1004802d0  mov     r13, [rsp+1F0h+var_20]
0x1004802d8  mov     r12, [rsp+1F0h+var_18]
0x1004802e0  cmovnb  rax, rcx
0x1004802e4  mov     rdi, [rsp+1F0h+arg_0]
0x1004802ec  mov     [rsi+17F8h], rax
0x1004802f3  test    rbx, rbx
0x1004802f6  jz      loc_1004803A6
0x1004802fc  test    byte ptr cs:?sm_osStats@SOS_PublicGlobals@@2KA, 40h; ulong SOS_PublicGlobals::sm_osStats
0x100480303  jz      loc_1004803A6
0x100480309  sub     r9, [rsp+1F0h+var_1B8]
0x10048030e  xor     eax, eax
0x100480310  mov     rcx, [rsi+1400h]
0x100480317  xor     edx, edx
0x100480319  mov     [rsp+1F0h+var_198], rax
0x10048031e  xorps   xmm0, xmm0
0x100480321  mov     rax, r9
0x100480324  mov     [rsp+1F0h+var_190], rsi
0x100480329  div     cs:?sm_CpuTicksPerMillisecond@SOS_PublicGlobals@@2_KA; unsigned __int64 SOS_PublicGlobals::sm_CpuTicksPerMillisecond
0x100480330  movups  [rsp+1F0h+var_1A8], xmm0
0x100480335  mov     [rbp+0F0h+var_158], eax
0x100480338  mov     [rsp+1F0h+var_188], 0Fh
0x100480340  mov     [rsp+1F0h+var_180], r8
0x100480345  mov     [rsp+1F0h+var_178], rcx
0x10048034a  mov     [rbp+0F0h+var_170], r14
0x10048034e  mov     [rbp+0F0h+var_168], r14
0x100480352  mov     [rbp+0F0h+var_160], r14
0x100480356  mov     [rbp+0F0h+var_154], r14d
0x10048035a  mov     [rbp+0F0h+var_48], r14d
0x100480361  mov     [rbp+0F0h+var_40], r14
0x100480368  cmp     [rbx+40h], r14
0x10048036c  jz      short loc_10048037B
0x10048036e  lea     edx, [r14+1]
0x100480372  lea     rcx, [rbp+0F0h+var_120]
0x100480376  call    ?CaptureCurrent@?$StackFrames@$0BI@@@QEAAXI@Z; StackFrames<24>::CaptureCurrent(uint)
0x10048037b  test    cs:?g_XeSosPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$0FD@@@@@A, 80000h; XBitmap<StaticStorage<83>> g_XeSosPkg_enabledBitmap
0x100480385  jz      short loc_100480395
0x100480387  lea     rdx, [rbp+0F0h+var_120]
0x10048038b  lea     rcx, [rsp+1F0h+var_1A8]
0x100480390  call    ?FireMatchingEvent@SOS_SchedulerRingRecord@@QEAAXPEAV?$StackFrames@$0BI@@@@Z; SOS_SchedulerRingRecord::FireMatchingEvent(StackFrames<24> *)
0x100480395  lea     r8, [rbp+0F0h+var_120]
0x100480399  mov     rcx, rbx
0x10048039c  lea     rdx, [rsp+1F0h+var_1A8]
0x1004803a1  call    ?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z; SOS_RingBuffer::StoreRecordInternalWithoutEvent(SOS_RingBufferRecord *,StackFrames<24> *)
0x1004803a6  test    byte ptr cs:?sm_osStats@SOS_PublicGlobals@@2KA, 4; ulong SOS_PublicGlobals::sm_osStats
0x1004803ad  jz      short loc_1004803CF
0x1004803af  mov     r8, [rsi+1400h]
0x1004803b6  lea     rax, [rsp+1F0h+var_1B0]
0x1004803bb  xor     r9d, r9d
0x1004803be  mov     [rsp+1F0h+var_1D0], rax
0x1004803c3  lea     rdx, [rbp+0F0h+var_150]
0x1004803c7  mov     rcx, rsi
0x1004803ca  call    ?UpdateWaitTimeStats@SOS_Scheduler@@QEAAXPEBVSOS_WaitInfo@@PEAVWorker@@W4SOS_RESULT@@PEBV?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z; SOS_Scheduler::UpdateWaitTimeStats(SOS_WaitInfo const *,Worker *,SOS_RESULT,SOS_Ticks<InterruptTicks<unsigned __int64>,-3> const *)
0x1004803cf  mov     rcx, [rsi+1400h]
0x1004803d6  mov     eax, [rcx+320h]
0x1004803dc  and     eax, 1004h
0x1004803e1  cmp     eax, 4
0x1004803e4  jz      short loc_1004803ED
0x1004803e6  xor     edx, edx
0x1004803e8  call    ?TaskTransition@SOS_Scheduler@@SAXPEAVWorker@@W4Transition@1@@Z; SOS_Scheduler::TaskTransition(Worker *,SOS_Scheduler::Transition)
0x1004803ed  lock inc dword ptr [rsi+1440h]
0x1004803f4  mov     rcx, rsi; this
0x1004803f7  call    ?GetLock@SOS_Scheduler@@IEAAXXZ; SOS_Scheduler::GetLock(void)
0x1004803fc  mov     [rsi+14A4h], r14d
0x100480403  mov     r14, [rsp+1F0h+var_28]
0x10048040b  inc     dword ptr [rsi+1444h]
0x100480411  cmp     cs:dword_100715790, 1
0x100480418  jnz     short loc_100480426
0x10048041a  cmp     dword ptr [rsi+0E68h], 100000h
0x100480424  jb      short loc_100480483
0x100480426  cmp     dword ptr [rsi+0EA0h], 0
0x10048042d  jnz     short loc_100480439
0x10048042f  cmp     qword ptr [rsi+1488h], 0
0x100480437  jle     short loc_100480483
0x100480439  cmp     qword ptr [rsi+14C0h], 0
0x100480441  jnz     short loc_100480455
0x100480443  mov     rcx, rsi; this
0x100480446  add     rsp, 1E0h
0x10048044d  pop     rsi
0x10048044e  pop     rbx
0x10048044f  pop     rbp
0x100480450  jmp     ?EnqueueIdleConsumer@SOS_Scheduler@@AEAAXXZ; SOS_Scheduler::EnqueueIdleConsumer(void)
0x100480455  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, 0; int Base_PublicGlobals::sm_invariantTscAvailable
0x10048045c  jz      short loc_100480474
0x10048045e  lea     rcx, [rbp+0F0h+PerformanceCount]; lpPerformanceCount
0x100480465  call    cs:__imp_QueryPerformanceCounter
0x10048046b  mov     rax, qword ptr [rbp+0F0h+PerformanceCount]
0x100480472  jmp     short loc_10048047C
0x100480474  mov     rax, ds:7FFE0008h
0x10048047c  mov     [rsi+1498h], rax
0x100480483  add     rsp, 1E0h
0x10048048a  pop     rsi
0x10048048b  pop     rbx
0x10048048c  pop     rbp
0x10048048d  retn
```
