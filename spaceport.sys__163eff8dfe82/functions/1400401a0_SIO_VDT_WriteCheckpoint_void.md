# SIO_VDT::WriteCheckpoint(void)

- ea: `0x1400401a0`
- end: `0x1400403cb`
- name: `?WriteCheckpoint@SIO_VDT@@IEAAJXZ`
- size: `555`
- prototype: `__int64 __fastcall(SIO_VDT *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x14002b7a4`
- `0x14003f398`

## callees

- `0x140009f80`
- `0x14000a070`
- `0x14000ec40`
- `0x14000ed90`
- `0x14001df20`
- `0x14002aa3c`
- `0x14003f548`
- `0x1400401a0`
- `0x140051bc4`
- `0x140051c00`
- `0x140052740`
- `0x140068150`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockShared` at `0x1400402fe`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x140040310`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x14004037f`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x140040391`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x1400402fe`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x140040310`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x14004037f`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x140040391`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x140040206`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x14004021f`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x140040206`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x14004021f`
- `HAL!KeQueryPerformanceCounter` at `0x1400401e8`
- `HAL!KeQueryPerformanceCounter` at `0x140040335`
- `HAL!KeQueryPerformanceCounter` at `0x1400401e8`
- `HAL!KeQueryPerformanceCounter` at `0x140040335`

## pseudocode

```c
__int64 __fastcall SIO_VDT::WriteCheckpoint(SIO_VDT *this)
{
  KIRQL v2; // r12
  KIRQL v3; // r13
  unsigned int v4; // edx
  int CheckpointPacket; // edi
  void *i; // rax
  struct SIO_VDT_ENTRY *CheckpointEntry; // rax
  struct SIO_VDT_GROUP *v8; // r11
  unsigned int v9; // eax
  _BYTE v11[192]; // [rsp+20h] [rbp-138h] BYREF
  __int64 v12; // [rsp+E0h] [rbp-78h]
  unsigned __int64 v13; // [rsp+160h] [rbp+8h] BYREF
  struct SIO_SPACE *v14; // [rsp+168h] [rbp+10h]
  LARGE_INTEGER PerformanceCounter; // [rsp+170h] [rbp+18h]

  v13 = 0;
  SC_PACKET::SC_PACKET((SC_PACKET *)v11);
  v14 = (struct SIO_SPACE *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 80LL))(*((_QWORD *)this + 1));
  PerformanceCounter = KeQueryPerformanceCounter(0);
  v2 = ExAcquireSpinLockShared((PEX_SPIN_LOCK)this + 46);
  v3 = ExAcquireSpinLockShared((PEX_SPIN_LOCK)this + 68);
  v4 = *((_DWORD *)this + 16);
  if ( *((_DWORD *)this + 26)
     + *((_DWORD *)this + 58) * ((((unsigned int)(*((_DWORD *)this + 82) + 7) >> 3) + 19) & 0xFFFFFFF8)
     + *((_DWORD *)this + 12)
     - 1
     - (*((_DWORD *)this + 26)
      + *((_DWORD *)this + 58) * ((((unsigned int)(*((_DWORD *)this + 82) + 7) >> 3) + 19) & 0xFFFFFFF8)
      + *((_DWORD *)this + 12)
      - 1)
     % *((_DWORD *)this + 12) < v4 )
    v4 = *((_DWORD *)this + 26)
       + *((_DWORD *)this + 58) * ((((unsigned int)(*((_DWORD *)this + 82) + 7) >> 3) + 19) & 0xFFFFFFF8)
       + *((_DWORD *)this + 12)
       - 1
       - (*((_DWORD *)this + 26)
        + *((_DWORD *)this + 58) * ((((unsigned int)(*((_DWORD *)this + 82) + 7) >> 3) + 19) & 0xFFFFFFF8)
        + *((_DWORD *)this + 12)
        - 1)
       % *((_DWORD *)this + 12);
  CheckpointPacket = SIO_SLOTS::GetCheckpointPacket((SIO_VDT *)((char *)this + 16), v4, (struct SC_PACKET *)v11);
  if ( CheckpointPacket < 0 )
  {
LABEL_11:
    ExReleaseSpinLockShared((PEX_SPIN_LOCK)this + 68, v3);
    ExReleaseSpinLockShared((PEX_SPIN_LOCK)this + 46, v2);
  }
  else
  {
    for ( i = SC_SPARSE::FindFirstObject((SIO_VDT *)((char *)this + 192), &v13);
          i;
          i = SC_SPARSE::FindNextObject((SIO_VDT *)((char *)this + 192), &v13) )
    {
      if ( i != (void *)2 )
      {
        CheckpointEntry = (struct SIO_VDT_ENTRY *)SIO_SLOTS::GetCheckpointEntry(
                                                    (SIO_VDT *)((char *)this + 16),
                                                    (struct SC_PACKET *)v11);
        if ( !CheckpointEntry )
        {
          CheckpointPacket = -1072037859;
          goto LABEL_11;
        }
        v9 = SIO_VDT::FormatGroup(this, v8, *((_QWORD *)this + 40) * v13, CheckpointEntry);
        v12 += v9;
      }
    }
    ExReleaseSpinLockShared((PEX_SPIN_LOCK)this + 68, v3);
    ExReleaseSpinLockShared((PEX_SPIN_LOCK)this + 46, v2);
    CheckpointPacket = SIO_SLOTS::FlushSynchronous((SIO_VDT *)((char *)this + 16), v14);
    if ( CheckpointPacket >= 0 )
      CheckpointPacket = SIO_SLOTS::WriteCheckpoint((SIO_VDT *)((char *)this + 16), (struct SC_PACKET *)v11);
  }
  SIO_VDT::LogStatus(this, 8, (unsigned int)CheckpointPacket);
  _InterlockedIncrement((volatile signed __int32 *)this + 94);
  _InterlockedAdd64(
    (volatile signed __int64 *)this + 49,
    *(_QWORD *)&KeQueryPerformanceCounter(0) - PerformanceCounter.QuadPart);
  SIO_LOG_PACKET::~SIO_LOG_PACKET((SIO_LOG_PACKET *)v11);
  return (unsigned int)CheckpointPacket;
}

```

## disassembly

```asm
0x1400401a0  mov     rax, rsp
0x1400401a3  mov     [rax+20h], rbx
0x1400401a7  push    rbp
0x1400401a8  push    rsi
0x1400401a9  push    rdi
0x1400401aa  push    r12
0x1400401ac  push    r13
0x1400401ae  push    r14
0x1400401b0  push    r15
0x1400401b2  sub     rsp, 120h
0x1400401b9  mov     rbx, rcx
0x1400401bc  mov     qword ptr [rax+8], 0
0x1400401c4  lea     rcx, [rsp+158h+var_138]; this
0x1400401c9  call    ??0SC_PACKET@@QEAA@XZ; SC_PACKET::SC_PACKET(void)
0x1400401ce  mov     rcx, [rbx+8]
0x1400401d2  mov     rax, [rcx]
0x1400401d5  mov     rax, [rax+50h]
0x1400401d9  call    _guard_dispatch_icall
0x1400401de  xor     ecx, ecx; PerformanceFrequency
0x1400401e0  mov     [rsp+158h+arg_8], rax
0x1400401e8  call    cs:__imp_KeQueryPerformanceCounter
0x1400401ef  nop     dword ptr [rax+rax+00h]
0x1400401f4  lea     r14, [rbx+0B8h]
0x1400401fb  mov     [rsp+158h+arg_10], rax
0x140040203  mov     rcx, r14; SpinLock
0x140040206  call    cs:__imp_ExAcquireSpinLockShared
0x14004020d  nop     dword ptr [rax+rax+00h]
0x140040212  lea     r15, [rbx+110h]
0x140040219  mov     r12b, al
0x14004021c  mov     rcx, r15; SpinLock
0x14004021f  call    cs:__imp_ExAcquireSpinLockShared
0x140040226  nop     dword ptr [rax+rax+00h]
0x14004022b  mov     ecx, [rbx+148h]
0x140040231  lea     rsi, [rbx+10h]
0x140040235  mov     r9d, [rsi+20h]
0x140040239  lea     rbp, [rbx+0C0h]
0x140040240  add     ecx, 7
0x140040243  xor     edx, edx
0x140040245  shr     ecx, 3
0x140040248  mov     r13b, al
0x14004024b  add     ecx, 13h
0x14004024e  and     ecx, 0FFFFFFF8h
0x140040251  lea     r8d, [r9-1]
0x140040255  imul    ecx, [rbp+28h]
0x140040259  add     ecx, [rbx+68h]
0x14004025c  add     r8d, ecx
0x14004025f  mov     rcx, rsi; this
0x140040262  mov     eax, r8d
0x140040265  div     r9d
0x140040268  sub     r8d, edx
0x14004026b  mov     edx, [rbx+40h]
0x14004026e  cmp     r8d, edx
0x140040271  cmovb   edx, r8d; unsigned int
0x140040275  lea     r8, [rsp+158h+var_138]; struct SC_PACKET *
0x14004027a  call    ?GetCheckpointPacket@SIO_SLOTS@@QEAAJKPEAVSC_PACKET@@@Z; SIO_SLOTS::GetCheckpointPacket(ulong,SC_PACKET *)
0x14004027f  mov     edi, eax
0x140040281  test    eax, eax
0x140040283  js      short loc_1400402F8
0x140040285  lea     rdx, [rsp+158h+arg_0]; unsigned __int64 *
0x14004028d  mov     rcx, rbp; this
0x140040290  call    ?FindFirstObject@SC_SPARSE@@QEAAPEAXPEA_K@Z; SC_SPARSE::FindFirstObject(unsigned __int64 *)
0x140040295  mov     r11, rax
0x140040298  test    rax, rax
0x14004029b  jz      loc_140040379
0x1400402a1  cmp     rax, 2
0x1400402a5  jz      short loc_1400402E1
0x1400402a7  lea     rdx, [rsp+158h+var_138]; struct SC_PACKET *
0x1400402ac  mov     rcx, rsi; this
0x1400402af  call    ?GetCheckpointEntry@SIO_SLOTS@@QEAAPEAXPEAVSC_PACKET@@@Z; SIO_SLOTS::GetCheckpointEntry(SC_PACKET *)
0x1400402b4  test    rax, rax
0x1400402b7  jz      short loc_1400402F3
0x1400402b9  mov     r8, [rsp+158h+arg_0]
0x1400402c1  mov     r9, rax; struct SIO_VDT_ENTRY *
0x1400402c4  imul    r8, [rbx+140h]; unsigned __int64
0x1400402cc  mov     rdx, r11; struct SIO_VDT_GROUP *
0x1400402cf  mov     rcx, rbx; this
0x1400402d2  call    ?FormatGroup@SIO_VDT@@IEAAKPEAVSIO_VDT_GROUP@@_KPEAVSIO_VDT_ENTRY@@@Z; SIO_VDT::FormatGroup(SIO_VDT_GROUP *,unsigned __int64,SIO_VDT_ENTRY *)
0x1400402d7  mov     ecx, eax
0x1400402d9  add     [rsp+158h+var_78], rcx
0x1400402e1  lea     rdx, [rsp+158h+arg_0]; unsigned __int64 *
0x1400402e9  mov     rcx, rbp; this
0x1400402ec  call    ?FindNextObject@SC_SPARSE@@QEAAPEAXPEA_K@Z; SC_SPARSE::FindNextObject(unsigned __int64 *)
0x1400402f1  jmp     short loc_140040295
0x1400402f3  mov     edi, 0C01A001Dh
0x1400402f8  mov     dl, r13b; OldIrql
0x1400402fb  mov     rcx, r15; SpinLock
0x1400402fe  call    cs:__imp_ExReleaseSpinLockShared
0x140040305  nop     dword ptr [rax+rax+00h]
0x14004030a  mov     dl, r12b; OldIrql
0x14004030d  mov     rcx, r14; SpinLock
0x140040310  call    cs:__imp_ExReleaseSpinLockShared
0x140040317  nop     dword ptr [rax+rax+00h]
0x14004031c  mov     r8d, edi
0x14004031f  mov     edx, 8
0x140040324  mov     rcx, rbx
0x140040327  call    ?LogStatus@SIO_VDT@@IEAAXW4SIO_VDT_OPERATION@@J@Z; SIO_VDT::LogStatus(SIO_VDT_OPERATION,long)
0x14004032c  lock inc dword ptr [rbx+178h]
0x140040333  xor     ecx, ecx; PerformanceFrequency
0x140040335  call    cs:__imp_KeQueryPerformanceCounter
0x14004033c  nop     dword ptr [rax+rax+00h]
0x140040341  sub     rax, [rsp+158h+arg_10]
0x140040349  lock add [rbx+188h], rax
0x140040351  lea     rcx, [rsp+158h+var_138]; this
0x140040356  call    ??1SIO_LOG_PACKET@@UEAA@XZ; SIO_LOG_PACKET::~SIO_LOG_PACKET(void)
0x14004035b  mov     rbx, [rsp+158h+arg_18]
0x140040363  mov     eax, edi
0x140040365  add     rsp, 120h
0x14004036c  pop     r15
0x14004036e  pop     r14
0x140040370  pop     r13
0x140040372  pop     r12
0x140040374  pop     rdi
0x140040375  pop     rsi
0x140040376  pop     rbp
0x140040377  retn
0x140040379  mov     dl, r13b; OldIrql
0x14004037c  mov     rcx, r15; SpinLock
0x14004037f  call    cs:__imp_ExReleaseSpinLockShared
0x140040386  nop     dword ptr [rax+rax+00h]
0x14004038b  mov     dl, r12b; OldIrql
0x14004038e  mov     rcx, r14; SpinLock
0x140040391  call    cs:__imp_ExReleaseSpinLockShared
0x140040398  nop     dword ptr [rax+rax+00h]
0x14004039d  mov     rdx, [rsp+158h+arg_8]; struct SIO_SPACE *
0x1400403a5  mov     rcx, rsi; this
0x1400403a8  call    ?FlushSynchronous@SIO_SLOTS@@QEAAJPEAVSIO_SPACE@@@Z; SIO_SLOTS::FlushSynchronous(SIO_SPACE *)
0x1400403ad  mov     edi, eax
0x1400403af  test    eax, eax
0x1400403b1  js      loc_14004031C
0x1400403b7  lea     rdx, [rsp+158h+var_138]; struct SC_PACKET *
0x1400403bc  mov     rcx, rsi; this
0x1400403bf  call    ?WriteCheckpoint@SIO_SLOTS@@QEAAJPEAVSC_PACKET@@@Z; SIO_SLOTS::WriteCheckpoint(SC_PACKET *)
0x1400403c4  mov     edi, eax
0x1400403c6  jmp     loc_14004031C
```
