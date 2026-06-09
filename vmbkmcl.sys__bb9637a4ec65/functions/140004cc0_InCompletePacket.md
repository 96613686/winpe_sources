# InCompletePacket

- ea: `0x140004cc0`
- end: `0x14000521c`
- name: `InCompletePacket`
- size: `1372`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x140004c90`

## callees

- `0x140002190`
- `0x140003ea0`
- `0x140004790`
- `0x1400049a0`
- `0x140004cc0`
- `0x140005230`
- `0x140005ae0`
- `0x140005cf0`
- `0x140008d20`
- `0x140008f90`
- `0x14000a160`
- `0x140010d1c`
- `0x140011f80`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140004e2e`
- `ntoskrnl!KeSetEvent` at `0x140004e2e`
- `ntoskrnl!KfRaiseIrql` at `0x140004d4f`
- `ntoskrnl!KfRaiseIrql` at `0x140004d4f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004e4c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004e4c`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140004d70`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140004ea9`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140005163`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400051a3`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140004d70`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140004ea9`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140005163`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400051a3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140004db6`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140005150`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000517f`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140004db6`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140005150`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000517f`
- `HAL!KeQueryPerformanceCounter` at `0x140004d02`
- `HAL!KeQueryPerformanceCounter` at `0x140004d02`

## pseudocode

```c
void __fastcall InCompletePacket(__int64 a1, __int64 a2, const void *a3, unsigned int a4)
{
  size_t v5; // rbp
  __int64 v6; // rcx
  const void *v7; // rbx
  __int64 v9; // rax
  LARGE_INTEGER PerformanceCounter; // rax
  bool v11; // zf
  KIRQL v12; // r14
  int v13; // ecx
  __int64 v14; // rax
  __int64 v15; // r15
  _QWORD *v16; // rcx
  struct _KEVENT *v17; // rcx
  __int64 v18; // rcx
  unsigned int v19; // r8d
  __int64 v20; // rdx
  __int64 v21; // r11
  int v22; // ebx
  __int64 v23; // r10
  unsigned int v24; // r8d
  _DWORD *v25; // rdx
  unsigned int v26; // ecx
  __int64 v27; // rbx
  int v28; // edx
  unsigned int v29; // r9d
  int v30; // r10d
  unsigned int v31; // edx
  unsigned int v32; // ecx
  unsigned int v33; // eax
  unsigned int v34; // ecx
  int v35; // edx
  unsigned int v36; // r9d
  int v37; // r10d
  unsigned int v38; // eax
  __int64 v39; // rax
  int v40; // eax
  _DWORD *v41; // rcx
  unsigned int v42; // edx
  int v43; // r9d
  unsigned int v44; // eax
  unsigned int v45; // ebx
  signed __int32 v46[8]; // [rsp+0h] [rbp-A8h] BYREF
  unsigned __int8 v47; // [rsp+40h] [rbp-68h]
  __int64 v48; // [rsp+48h] [rbp-60h]
  _DWORD *v49; // [rsp+50h] [rbp-58h]
  __int64 v50; // [rsp+58h] [rbp-50h]
  __int64 v51; // [rsp+60h] [rbp-48h]

  v5 = a4;
  v6 = *(_QWORD *)(a2 + 88);
  v7 = a3;
  if ( v6 )
  {
    v9 = *(_QWORD *)(a2 + 96);
    if ( v9 )
    {
      if ( KmclPerformanceCounterTimingCounters )
      {
        *(_QWORD *)(a2 + 88) = v9 - v6;
        PerformanceCounter = KeQueryPerformanceCounter(0);
        v11 = KmclPerformanceCounterTimingCounters == 0;
        *(_QWORD *)(a2 + 96) = PerformanceCounter.QuadPart - *(_QWORD *)(a2 + 96);
        if ( !v11 )
        {
          *(_QWORD *)(a1 + 1368) += *(_QWORD *)(a2 + 88);
          *(_QWORD *)(a1 + 1376) += *(_QWORD *)(a2 + 96);
        }
      }
    }
  }
  if ( *(_QWORD *)(a2 + 48) )
    InpUnmapPacketMdl(a1, a2);
  v12 = KfRaiseIrql(2u);
  if ( (*(_BYTE *)(a2 + 16) & 0x10) == 0 )
  {
    v15 = a2 + 24;
    goto LABEL_23;
  }
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(a1 + 1088));
  v13 = *(_DWORD *)(a1 + 1096);
  if ( v13 && v13 != 10 )
  {
    v14 = *(_QWORD *)(a2 + 24);
    v15 = a2 + 24;
    if ( *(_QWORD *)(v14 + 8) != a2 + 24 || (v16 = *(_QWORD **)(a2 + 32), *v16 != v15) )
      __fastfail(3u);
    *v16 = v14;
    *(_QWORD *)(v14 + 8) = v16;
    --*(_DWORD *)(a1 + 1152);
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(a1 + 1088));
LABEL_23:
    v11 = (*(_BYTE *)(a2 + 16) & 4) == 0;
    v47 = *(_BYTE *)(a2 + 17);
    if ( v11 )
      goto LABEL_69;
    *(_QWORD *)(a2 + 64) = *(_QWORD *)(a2 + 168);
    *(_QWORD *)(a2 + 72) = a2 + 160;
    *(_QWORD *)(a2 + 56) = InpCompletionSent;
    *(_DWORD *)(a2 + 48) = *(_DWORD *)(a1 + 1452);
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(a1 + 256));
    if ( *(_DWORD *)(a1 + 264) != 1 )
      goto LABEL_65;
    v20 = *(_QWORD *)(v15 + 40);
    v21 = (unsigned int)(v5 + 16);
    v48 = v20;
    if ( (unsigned int)v21 > 0x7FFF8 )
    {
      v22 = -1073741811;
LABEL_59:
      if ( (Microsoft_Windows_Hyper_V_KMCL_ChildEnableBits & 2) != 0 )
        McTemplateK0jjxth_EtwWriteTransfer(
          *(_DWORD *)a1 + 2752,
          (unsigned int)VMBUS_SEND_PACKET,
          v19,
          *(_DWORD *)a1 + 2768,
          *(_QWORD *)a1 + 2752LL,
          v20,
          1,
          *(_WORD *)(*(_QWORD *)a1 + 3280LL));
      if ( v22 >= 0 )
        ++*(_DWORD *)(a1 + 528);
      if ( (int)OutpProcessRingResult(a1, (unsigned int)v22) >= 0 )
      {
LABEL_68:
        KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(a1 + 256));
LABEL_69:
        v45 = *(_DWORD *)(a2 + 8) - *(_DWORD *)(a2 + 12);
        InpFreePacket(a1, a2);
        KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(a1 + 1088));
        _InterlockedIncrement((volatile signed __int32 *)(a1 + 1144));
        *(_QWORD *)(a1 + 1168) += v45;
        if ( *(_DWORD *)(a1 + 1096) == 1 )
        {
          *(_BYTE *)(a1 + 1120) |= 2u;
        }
        else if ( (unsigned int)(*(_DWORD *)(a1 + 1096) - 5) <= 1 )
        {
          InpPrepareToQueueWorkerLocked(a1, 0, 0);
        }
        goto LABEL_73;
      }
      v7 = a3;
LABEL_65:
      if ( (unsigned int)v5 <= *(_DWORD *)(v15 + 24) )
      {
        memmove(*(void **)(v15 + 48), v7, v5);
        *(_DWORD *)(v15 + 24) = v5;
        *(_DWORD *)(v15 + 16) = 2;
        OutpEnqueuePacket(a1, v15);
        KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(a1 + 256));
        KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(a1 + 1088));
LABEL_73:
        InpPacketCompletedLocked(a1, v47);
        InpReleaseLockAndPerformWork(a1, v12);
        return;
      }
      MicrosoftTelemetryAssertTriggeredArgsKM(v18, (unsigned int)v5);
      goto LABEL_68;
    }
    v23 = *(unsigned int *)(a1 + 192);
    v24 = *(_DWORD *)(a1 + 80);
    v25 = (_DWORD *)(v23 + *(_QWORD *)(a1 + 72));
    v51 = v23;
    v50 = ((_DWORD)v5 + 23) & 0xFFFFFFF8;
    v49 = v25;
    _m_prefetchw(v25);
    v26 = *(_DWORD *)(a1 + 196) - v23 - 8;
    if ( v26 >= v24 )
      v26 += v24;
    if ( v26 < (int)v50 + 8 )
    {
      v27 = *(_QWORD *)(a1 + 64);
      if ( !(unsigned __int8)PkpValidatePointer(v24, *(unsigned int *)(v27 + 4)) )
      {
        v22 = -1073741566;
LABEL_58:
        LOBYTE(v20) = v48;
        goto LABEL_59;
      }
      *(_DWORD *)(a1 + 196) = v28;
      v31 = v28 - v30 - 8;
      if ( v31 >= v19 )
        v31 += v19;
      if ( v31 < v29 )
      {
        if ( v29 >= v19 )
        {
          v22 = -1073741811;
          goto LABEL_58;
        }
        if ( !*(_DWORD *)(a1 + 200)
          && (unsigned int)(*(_DWORD *)(a1 + 136) + *(_DWORD *)(a1 + 204) - *(_DWORD *)(a1 + 140)) < 0x40 )
        {
          _InterlockedIncrement((volatile signed __int32 *)(a1 + 204));
        }
        v32 = v30 - *(_DWORD *)(a1 + 192);
        if ( v32 >= v19 )
          v32 += v19;
        v33 = v19 - 8;
        v34 = v29 + v32;
        if ( v34 < v19 )
          v33 = v34;
        *(_DWORD *)(v27 + 12) = v33;
        *(_DWORD *)(a1 + 200) = v50;
        _InterlockedOr(v46, 0);
        if ( !(unsigned __int8)PkpValidatePointer(v19, *(unsigned int *)(v27 + 4)) )
        {
          v22 = -1073741566;
          goto LABEL_58;
        }
        *(_DWORD *)(a1 + 196) = v35;
        v38 = v35 - v37 - 8;
        if ( v38 >= v19 )
          v38 += v19;
        if ( v38 < v36 )
        {
          v22 = -2147483643;
          goto LABEL_58;
        }
      }
      v25 = v49;
    }
    *v25 = 131083;
    v22 = 0;
    *((_WORD *)v25 + 2) = (unsigned __int64)(v21 + 7) >> 3;
    v39 = v48;
    *((_WORD *)v25 + 3) = 0;
    *((_QWORD *)v25 + 1) = v39;
    memmove(v25 + 4, a3, v5);
    v40 = PkWritePacketFooter(a1 + 64, (unsigned int)v51, (unsigned int)(v5 + 16));
    v19 = *(_DWORD *)(a1 + 192);
    v41 = *(_DWORD **)(a1 + 64);
    v42 = *(_DWORD *)(a1 + 80);
    *(_DWORD *)(a1 + 192) = v40;
    *v41 = v40;
    _InterlockedOr(v46, 0);
    v43 = v41[2];
    v44 = v41[1];
    if ( v44 >= v42 || (v44 & 7) != 0 )
    {
      v22 = -1073741566;
    }
    else
    {
      *(_DWORD *)(a1 + 196) = v44;
      if ( v19 == v44 )
      {
        if ( v43 )
          ++**(_QWORD **)(a1 + 216);
        else
          v22 = 532;
      }
    }
    goto LABEL_58;
  }
  if ( (*(_BYTE *)(a2 + 16) & 4) != 0 && !v13 )
  {
    memmove((void *)(a2 + *(unsigned int *)(a2 + 84) + *(unsigned int *)(a2 + 64) + 160LL), v7, v5);
    *(_DWORD *)(a2 + 80) = v5;
  }
  *(_BYTE *)(a2 + 16) |= 0x20u;
  ++*(_DWORD *)(a1 + 1156);
  if ( *(_DWORD *)(a1 + 1096) == 10 && *(_DWORD *)(a1 + 1152) == *(_DWORD *)(a1 + 1156) )
  {
    v17 = *(struct _KEVENT **)(a1 + 1216);
    *(_DWORD *)(a1 + 1096) = 0;
    KeSetEvent(v17, 0, 0);
    *(_QWORD *)(a1 + 1216) = 0;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 1088), v12);
}

```

## disassembly

```asm
0x140004cc0  mov     [rsp+Src], r8
0x140004cc5  push    rbx
0x140004cc6  push    rbp
0x140004cc7  push    rsi
0x140004cc8  push    rdi
0x140004cc9  push    r12
0x140004ccb  push    r14
0x140004ccd  sub     rsp, 78h
0x140004cd1  mov     rdi, rcx
0x140004cd4  mov     ebp, r9d
0x140004cd7  mov     rcx, [rdx+58h]
0x140004cdb  mov     rbx, r8
0x140004cde  mov     rsi, rdx
0x140004ce1  test    rcx, rcx
0x140004ce4  jz      short loc_140004D36
0x140004ce6  mov     rax, [rdx+60h]
0x140004cea  test    rax, rax
0x140004ced  jz      short loc_140004D36
0x140004cef  cmp     cs:KmclPerformanceCounterTimingCounters, 0
0x140004cf7  jz      short loc_140004D36
0x140004cf9  sub     rax, rcx
0x140004cfc  xor     ecx, ecx; PerformanceFrequency
0x140004cfe  mov     [rdx+58h], rax
0x140004d02  call    cs:__imp_KeQueryPerformanceCounter
0x140004d09  nop     dword ptr [rax+rax+00h]
0x140004d0e  sub     rax, [rsi+60h]
0x140004d12  cmp     cs:KmclPerformanceCounterTimingCounters, 0
0x140004d1a  mov     [rsi+60h], rax
0x140004d1e  jz      short loc_140004D36
0x140004d20  mov     rax, [rsi+58h]
0x140004d24  add     [rdi+558h], rax
0x140004d2b  mov     rax, [rsi+60h]
0x140004d2f  add     [rdi+560h], rax
0x140004d36  cmp     qword ptr [rsi+30h], 0
0x140004d3b  jz      short loc_140004D48
0x140004d3d  mov     rdx, rsi
0x140004d40  mov     rcx, rdi
0x140004d43  call    InpUnmapPacketMdl
0x140004d48  mov     cl, 2; NewIrql
0x140004d4a  mov     [rsp+0A8h+var_38], r15
0x140004d4f  call    cs:__imp_KfRaiseIrql
0x140004d56  nop     dword ptr [rax+rax+00h]
0x140004d5b  test    byte ptr [rsi+10h], 10h
0x140004d5f  movzx   r14d, al
0x140004d63  jz      loc_140004E5D
0x140004d69  lea     rcx, [rdi+440h]; SpinLock
0x140004d70  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140004d77  nop     dword ptr [rax+rax+00h]
0x140004d7c  mov     ecx, [rdi+448h]
0x140004d82  test    ecx, ecx
0x140004d84  jz      short loc_140004DCE
0x140004d86  cmp     ecx, 0Ah
0x140004d89  jz      short loc_140004DCE
0x140004d8b  mov     rax, [rsi+18h]
0x140004d8f  lea     r15, [rsi+18h]
0x140004d93  cmp     [rax+8], r15
0x140004d97  jnz     short loc_140004DC7
0x140004d99  mov     rcx, [r15+8]
0x140004d9d  cmp     [rcx], r15
0x140004da0  jnz     short loc_140004DC7
0x140004da2  mov     [rcx], rax
0x140004da5  mov     [rax+8], rcx
0x140004da9  lea     rcx, [rdi+440h]; SpinLock
0x140004db0  dec     dword ptr [rdi+480h]
0x140004db6  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140004dbd  nop     dword ptr [rax+rax+00h]
0x140004dc2  jmp     loc_140004E61
0x140004dc7  mov     ecx, 3
0x140004dcc  int     29h; Win8: RtlFailFast(ecx)
0x140004dce  test    byte ptr [rsi+10h], 4
0x140004dd2  jz      short loc_140004DF9
0x140004dd4  test    ecx, ecx
0x140004dd6  jnz     short loc_140004DF9
0x140004dd8  mov     eax, [rsi+54h]
0x140004ddb  mov     r8, rbp; Size
0x140004dde  mov     ecx, [rsi+40h]
0x140004de1  add     rax, rsi
0x140004de4  add     rcx, 0A0h
0x140004deb  mov     rdx, rbx; Src
0x140004dee  add     rcx, rax; void *
0x140004df1  call    memmove
0x140004df6  mov     [rsi+50h], ebp
0x140004df9  or      byte ptr [rsi+10h], 20h
0x140004dfd  inc     dword ptr [rdi+484h]
0x140004e03  cmp     dword ptr [rdi+448h], 0Ah
0x140004e0a  mov     eax, [rdi+484h]
0x140004e10  jnz     short loc_140004E41
0x140004e12  cmp     [rdi+480h], eax
0x140004e18  jnz     short loc_140004E41
0x140004e1a  mov     rcx, [rdi+4C0h]; Event
0x140004e21  xor     ebx, ebx
0x140004e23  xor     r8d, r8d; Wait
0x140004e26  mov     [rdi+448h], ebx
0x140004e2c  xor     edx, edx; Increment
0x140004e2e  call    cs:__imp_KeSetEvent
0x140004e35  nop     dword ptr [rax+rax+00h]
0x140004e3a  mov     [rdi+4C0h], rbx
0x140004e41  movzx   edx, r14b; NewIrql
0x140004e45  lea     rcx, [rdi+440h]; SpinLock
0x140004e4c  call    cs:__imp_KeReleaseSpinLock
0x140004e53  nop     dword ptr [rax+rax+00h]
0x140004e58  jmp     loc_140005209
0x140004e5d  lea     r15, [rsi+18h]
0x140004e61  test    byte ptr [rsi+10h], 4
0x140004e65  movzx   eax, byte ptr [rsi+11h]
0x140004e69  mov     [rsp+0A8h+var_68], al
0x140004e6d  mov     [rsp+0A8h+arg_0], r13
0x140004e75  jz      loc_14000518B
0x140004e7b  lea     rcx, [rsi+0A0h]
0x140004e82  mov     rax, [rcx+8]
0x140004e86  mov     [rsi+40h], rax
0x140004e8a  lea     rax, InpCompletionSent
0x140004e91  mov     [rsi+48h], rcx
0x140004e95  lea     rcx, [rdi+100h]; SpinLock
0x140004e9c  mov     [rsi+38h], rax
0x140004ea0  mov     eax, [rdi+5ACh]
0x140004ea6  mov     [rsi+30h], eax
0x140004ea9  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140004eb0  nop     dword ptr [rax+rax+00h]
0x140004eb5  cmp     dword ptr [rdi+108h], 1
0x140004ebc  jnz     loc_14000511A
0x140004ec2  mov     rdx, [r15+28h]
0x140004ec6  lea     r11d, [rbp+10h]
0x140004eca  mov     [rsp+0A8h+var_60], rdx
0x140004ecf  cmp     r11d, 7FFF8h
0x140004ed6  jbe     short loc_140004EE2
0x140004ed8  mov     ebx, 0C000000Dh
0x140004edd  jmp     loc_1400050B6
0x140004ee2  mov     r10d, [rdi+0C0h]
0x140004ee9  lea     eax, [r11+7]
0x140004eed  mov     rdx, [rdi+48h]
0x140004ef1  and     eax, 0FFFFFFF8h
0x140004ef4  mov     r8d, [rdi+50h]
0x140004ef8  add     rdx, r10
0x140004efb  mov     [rsp+0A8h+var_48], r10
0x140004f00  mov     [rsp+0A8h+var_50], rax
0x140004f05  lea     r9d, [rax+8]
0x140004f09  mov     [rsp+0A8h+var_58], rdx
0x140004f0e  prefetchw byte ptr [rdx]
0x140004f11  mov     ecx, [rdi+0C4h]
0x140004f17  sub     ecx, r10d
0x140004f1a  add     ecx, 0FFFFFFF8h
0x140004f1d  cmp     ecx, r8d
0x140004f20  lea     eax, [rcx+r8]
0x140004f24  cmovnb  ecx, eax
0x140004f27  cmp     ecx, r9d
0x140004f2a  jnb     loc_140005018
0x140004f30  mov     rbx, [rdi+40h]
0x140004f34  mov     ecx, r8d
0x140004f37  mov     edx, [rbx+4]
0x140004f3a  call    PkpValidatePointer
0x140004f3f  test    al, al
0x140004f41  jnz     short loc_140004F4D
0x140004f43  mov     ebx, 0C0000102h
0x140004f48  jmp     loc_1400050B1
0x140004f4d  mov     [rdi+0C4h], edx
0x140004f53  sub     edx, r10d
0x140004f56  add     edx, 0FFFFFFF8h
0x140004f59  cmp     edx, r8d
0x140004f5c  jb      short loc_140004F61
0x140004f5e  add     edx, r8d
0x140004f61  cmp     edx, r9d
0x140004f64  jnb     loc_140005013
0x140004f6a  cmp     r9d, r8d
0x140004f6d  jb      short loc_140004F79
0x140004f6f  mov     ebx, 0C000000Dh
0x140004f74  jmp     loc_1400050B1
0x140004f79  cmp     dword ptr [rdi+0C8h], 0
0x140004f80  jnz     short loc_140004FA4
0x140004f82  mov     edx, [rdi+88h]
0x140004f88  mov     ecx, [rdi+0CCh]
0x140004f8e  mov     eax, [rdi+8Ch]
0x140004f94  sub     ecx, eax
0x140004f96  add     ecx, edx
0x140004f98  cmp     ecx, 40h ; '@'
0x140004f9b  jnb     short loc_140004FA4
0x140004f9d  lock inc dword ptr [rdi+0CCh]
0x140004fa4  mov     ecx, r10d
0x140004fa7  sub     ecx, [rdi+0C0h]
0x140004fad  cmp     ecx, r8d
0x140004fb0  lea     eax, [rcx+r8]
0x140004fb4  cmovnb  ecx, eax
0x140004fb7  lea     eax, [r8-8]
0x140004fbb  add     ecx, r9d
0x140004fbe  cmp     ecx, r8d
0x140004fc1  cmovb   eax, ecx
0x140004fc4  mov     [rbx+0Ch], eax
0x140004fc7  mov     rax, [rsp+0A8h+var_50]
0x140004fcc  mov     [rdi+0C8h], eax
0x140004fd2  lock or [rsp+0A8h+var_A8], 0
0x140004fd7  mov     edx, [rbx+4]
0x140004fda  mov     ecx, r8d
0x140004fdd  call    PkpValidatePointer
0x140004fe2  test    al, al
0x140004fe4  jnz     short loc_140004FF0
0x140004fe6  mov     ebx, 0C0000102h
0x140004feb  jmp     loc_1400050B1
0x140004ff0  mov     [rdi+0C4h], edx
0x140004ff6  sub     edx, r10d
0x140004ff9  lea     eax, [rdx-8]
0x140004ffc  cmp     eax, r8d
0x140004fff  jb      short loc_140005004
0x140005001  add     eax, r8d
0x140005004  cmp     eax, r9d
0x140005007  jnb     short loc_140005013
0x140005009  mov     ebx, 80000005h
0x14000500e  jmp     loc_1400050B1
0x140005013  mov     rdx, [rsp+0A8h+var_58]
0x140005018  nop
0x140005019  lea     rax, [r11+7]
0x14000501d  mov     dword ptr [rdx], 2000Bh
0x140005023  lea     rcx, [rdx+10h]; void *
0x140005027  shr     rax, 3
0x14000502b  xor     ebx, ebx
0x14000502d  mov     [rdx+4], ax
0x140005031  mov     r8, rbp; Size
0x140005034  mov     rax, [rsp+0A8h+var_60]
0x140005039  mov     [rdx+6], bx
0x14000503d  mov     [rdx+8], rax
0x140005041  mov     rdx, [rsp+0A8h+Src]; Src
0x140005049  call    memmove
0x14000504e  mov     edx, dword ptr [rsp+0A8h+var_48]
0x140005052  lea     r8d, [rbp+10h]
0x140005056  lea     rcx, [rdi+40h]
0x14000505a  call    PkWritePacketFooter
0x14000505f  mov     r8d, [rdi+0C0h]
0x140005066  mov     rcx, [rdi+40h]
0x14000506a  mov     edx, [rdi+50h]
0x14000506d  mov     [rdi+0C0h], eax
0x140005073  mov     [rcx], eax
0x140005075  lock or [rsp+0A8h+var_A8], ebx
0x140005079  mov     r9d, [rcx+8]
0x14000507d  mov     eax, [rcx+4]
0x140005080  cmp     eax, edx
0x140005082  jnb     short loc_1400050AB
0x140005084  test    al, 7
0x140005086  jnz     short loc_1400050AB
0x140005088  mov     [rdi+0C4h], eax
0x14000508e  cmp     r8d, eax
0x140005091  jnz     short loc_1400050B0
0x140005093  test    r9d, r9d
0x140005096  jnz     short loc_14000509F
0x140005098  mov     ebx, 214h
0x14000509d  jmp     short loc_1400050B0
0x14000509f  mov     rax, [rdi+0D8h]
0x1400050a6  inc     qword ptr [rax]
0x1400050a9  jmp     short loc_1400050B0
0x1400050ab  mov     ebx, 0C0000102h
0x1400050b0  nop
0x1400050b1  mov     rdx, [rsp+0A8h+var_60]
0x1400050b6  test    cs:Microsoft_Windows_Hyper_V_KMCL_ChildEnableBits, 2
0x1400050bd  jz      short loc_1400050FA
0x1400050bf  mov     rax, [rdi]
0x1400050c2  lea     rcx, [rax+0AC0h]
0x1400050c9  lea     r9, [rax+0AD0h]
0x1400050d0  movzx   eax, word ptr [rax+0CD0h]
0x1400050d7  mov     [rsp+0A8h+var_70], ax
0x1400050dc  mov     [rsp+0A8h+var_78], 1
0x1400050e4  mov     [rsp+0A8h+var_80], rdx
0x1400050e9  lea     rdx, VMBUS_SEND_PACKET
0x1400050f0  mov     [rsp+0A8h+var_88], rcx
0x1400050f5  call    McTemplateK0jjxth_EtwWriteTransfer
0x1400050fa  test    ebx, ebx
0x1400050fc  js      short loc_140005104
0x1400050fe  inc     dword ptr [rdi+210h]
0x140005104  mov     edx, ebx
0x140005106  mov     rcx, rdi
0x140005109  call    OutpProcessRingResult
0x14000510e  test    eax, eax
0x140005110  jns     short loc_140005178
0x140005112  mov     rbx, [rsp+0A8h+Src]
0x14000511a  mov     r8d, [r15+18h]
0x14000511e  cmp     ebp, r8d
0x140005121  ja      short loc_140005171
0x140005123  mov     rcx, [r15+30h]; void *
0x140005127  mov     r8, rbp; Size
0x14000512a  mov     rdx, rbx; Src
0x14000512d  call    memmove
0x140005132  mov     rdx, r15
0x140005135  mov     [r15+18h], ebp
0x140005139  mov     rcx, rdi
0x14000513c  mov     dword ptr [r15+10h], 2
0x140005144  call    OutpEnqueuePacket
0x140005149  lea     rcx, [rdi+100h]; SpinLock
0x140005150  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140005157  nop     dword ptr [rax+rax+00h]
0x14000515c  lea     rcx, [rdi+440h]; SpinLock
0x140005163  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000516a  nop     dword ptr [rax+rax+00h]
0x14000516f  jmp     short loc_1400051E8
0x140005171  mov     edx, ebp
0x140005173  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x140005178  lea     rcx, [rdi+100h]; SpinLock
0x14000517f  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140005186  nop     dword ptr [rax+rax+00h]
0x14000518b  mov     ebx, [rsi+8]
0x14000518e  mov     rdx, rsi
0x140005191  sub     ebx, [rsi+0Ch]
0x140005194  mov     rcx, rdi
0x140005197  call    InpFreePacket
  ... truncated ...
```
