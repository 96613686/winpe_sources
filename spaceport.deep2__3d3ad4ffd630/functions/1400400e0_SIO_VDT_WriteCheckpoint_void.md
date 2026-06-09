# SIO_VDT::WriteCheckpoint(void)

- ea: `0x1400400e0`
- end: `0x14004030b`
- name: `?WriteCheckpoint@SIO_VDT@@IEAAJXZ`
- size: `555`
- prototype: `__int64 __fastcall(SIO_VDT *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x14002b7a4`
- `0x14003f2d8`

## callees

- `0x140009f80`
- `0x14000a070`
- `0x14000ec40`
- `0x14000ed90`
- `0x14001df20`
- `0x14002aa3c`
- `0x14003f488`
- `0x1400400e0`
- `0x140051b04`
- `0x140051b40`
- `0x140052680`
- `0x140068000`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockShared` at `0x14004023e`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x140040250`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x1400402bf`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x1400402d1`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x14004023e`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x140040250`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x1400402bf`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x1400402d1`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x140040146`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x14004015f`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x140040146`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x14004015f`
- `HAL!KeQueryPerformanceCounter` at `0x140040128`
- `HAL!KeQueryPerformanceCounter` at `0x140040275`
- `HAL!KeQueryPerformanceCounter` at `0x140040128`
- `HAL!KeQueryPerformanceCounter` at `0x140040275`

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
0x1400400e0  mov     rax, rsp
0x1400400e3  mov     [rax+20h], rbx
0x1400400e7  push    rbp
0x1400400e8  push    rsi
0x1400400e9  push    rdi
0x1400400ea  push    r12
0x1400400ec  push    r13
0x1400400ee  push    r14
0x1400400f0  push    r15
0x1400400f2  sub     rsp, 120h
0x1400400f9  mov     rbx, rcx
0x1400400fc  mov     qword ptr [rax+8], 0
0x140040104  lea     rcx, [rsp+158h+var_138]; this
0x140040109  call    ??0SC_PACKET@@QEAA@XZ; SC_PACKET::SC_PACKET(void)
0x14004010e  mov     rcx, [rbx+8]
0x140040112  mov     rax, [rcx]
0x140040115  mov     rax, [rax+50h]
0x140040119  call    _guard_dispatch_icall
0x14004011e  xor     ecx, ecx; PerformanceFrequency
0x140040120  mov     [rsp+158h+arg_8], rax
0x140040128  call    cs:__imp_KeQueryPerformanceCounter
0x14004012f  nop     dword ptr [rax+rax+00h]
0x140040134  lea     r14, [rbx+0B8h]
0x14004013b  mov     [rsp+158h+arg_10], rax
0x140040143  mov     rcx, r14; SpinLock
0x140040146  call    cs:__imp_ExAcquireSpinLockShared
0x14004014d  nop     dword ptr [rax+rax+00h]
0x140040152  lea     r15, [rbx+110h]
0x140040159  mov     r12b, al
0x14004015c  mov     rcx, r15; SpinLock
0x14004015f  call    cs:__imp_ExAcquireSpinLockShared
0x140040166  nop     dword ptr [rax+rax+00h]
0x14004016b  mov     ecx, [rbx+148h]
0x140040171  lea     rsi, [rbx+10h]
0x140040175  mov     r9d, [rsi+20h]
0x140040179  lea     rbp, [rbx+0C0h]
0x140040180  add     ecx, 7
0x140040183  xor     edx, edx
0x140040185  shr     ecx, 3
0x140040188  mov     r13b, al
0x14004018b  add     ecx, 13h
0x14004018e  and     ecx, 0FFFFFFF8h
0x140040191  lea     r8d, [r9-1]
0x140040195  imul    ecx, [rbp+28h]
0x140040199  add     ecx, [rbx+68h]
0x14004019c  add     r8d, ecx
0x14004019f  mov     rcx, rsi; this
0x1400401a2  mov     eax, r8d
0x1400401a5  div     r9d
0x1400401a8  sub     r8d, edx
0x1400401ab  mov     edx, [rbx+40h]
0x1400401ae  cmp     r8d, edx
0x1400401b1  cmovb   edx, r8d; unsigned int
0x1400401b5  lea     r8, [rsp+158h+var_138]; struct SC_PACKET *
0x1400401ba  call    ?GetCheckpointPacket@SIO_SLOTS@@QEAAJKPEAVSC_PACKET@@@Z; SIO_SLOTS::GetCheckpointPacket(ulong,SC_PACKET *)
0x1400401bf  mov     edi, eax
0x1400401c1  test    eax, eax
0x1400401c3  js      short loc_140040238
0x1400401c5  lea     rdx, [rsp+158h+arg_0]; unsigned __int64 *
0x1400401cd  mov     rcx, rbp; this
0x1400401d0  call    ?FindFirstObject@SC_SPARSE@@QEAAPEAXPEA_K@Z; SC_SPARSE::FindFirstObject(unsigned __int64 *)
0x1400401d5  mov     r11, rax
0x1400401d8  test    rax, rax
0x1400401db  jz      loc_1400402B9
0x1400401e1  cmp     rax, 2
0x1400401e5  jz      short loc_140040221
0x1400401e7  lea     rdx, [rsp+158h+var_138]; struct SC_PACKET *
0x1400401ec  mov     rcx, rsi; this
0x1400401ef  call    ?GetCheckpointEntry@SIO_SLOTS@@QEAAPEAXPEAVSC_PACKET@@@Z; SIO_SLOTS::GetCheckpointEntry(SC_PACKET *)
0x1400401f4  test    rax, rax
0x1400401f7  jz      short loc_140040233
0x1400401f9  mov     r8, [rsp+158h+arg_0]
0x140040201  mov     r9, rax; struct SIO_VDT_ENTRY *
0x140040204  imul    r8, [rbx+140h]; unsigned __int64
0x14004020c  mov     rdx, r11; struct SIO_VDT_GROUP *
0x14004020f  mov     rcx, rbx; this
0x140040212  call    ?FormatGroup@SIO_VDT@@IEAAKPEAVSIO_VDT_GROUP@@_KPEAVSIO_VDT_ENTRY@@@Z; SIO_VDT::FormatGroup(SIO_VDT_GROUP *,unsigned __int64,SIO_VDT_ENTRY *)
0x140040217  mov     ecx, eax
0x140040219  add     [rsp+158h+var_78], rcx
0x140040221  lea     rdx, [rsp+158h+arg_0]; unsigned __int64 *
0x140040229  mov     rcx, rbp; this
0x14004022c  call    ?FindNextObject@SC_SPARSE@@QEAAPEAXPEA_K@Z; SC_SPARSE::FindNextObject(unsigned __int64 *)
0x140040231  jmp     short loc_1400401D5
0x140040233  mov     edi, 0C01A001Dh
0x140040238  mov     dl, r13b; OldIrql
0x14004023b  mov     rcx, r15; SpinLock
0x14004023e  call    cs:__imp_ExReleaseSpinLockShared
0x140040245  nop     dword ptr [rax+rax+00h]
0x14004024a  mov     dl, r12b; OldIrql
0x14004024d  mov     rcx, r14; SpinLock
0x140040250  call    cs:__imp_ExReleaseSpinLockShared
0x140040257  nop     dword ptr [rax+rax+00h]
0x14004025c  mov     r8d, edi
0x14004025f  mov     edx, 8
0x140040264  mov     rcx, rbx
0x140040267  call    ?LogStatus@SIO_VDT@@IEAAXW4SIO_VDT_OPERATION@@J@Z; SIO_VDT::LogStatus(SIO_VDT_OPERATION,long)
0x14004026c  lock inc dword ptr [rbx+178h]
0x140040273  xor     ecx, ecx; PerformanceFrequency
0x140040275  call    cs:__imp_KeQueryPerformanceCounter
0x14004027c  nop     dword ptr [rax+rax+00h]
0x140040281  sub     rax, [rsp+158h+arg_10]
0x140040289  lock add [rbx+188h], rax
0x140040291  lea     rcx, [rsp+158h+var_138]; this
0x140040296  call    ??1SIO_LOG_PACKET@@UEAA@XZ; SIO_LOG_PACKET::~SIO_LOG_PACKET(void)
0x14004029b  mov     rbx, [rsp+158h+arg_18]
0x1400402a3  mov     eax, edi
0x1400402a5  add     rsp, 120h
0x1400402ac  pop     r15
0x1400402ae  pop     r14
0x1400402b0  pop     r13
0x1400402b2  pop     r12
0x1400402b4  pop     rdi
0x1400402b5  pop     rsi
0x1400402b6  pop     rbp
0x1400402b7  retn
0x1400402b9  mov     dl, r13b; OldIrql
0x1400402bc  mov     rcx, r15; SpinLock
0x1400402bf  call    cs:__imp_ExReleaseSpinLockShared
0x1400402c6  nop     dword ptr [rax+rax+00h]
0x1400402cb  mov     dl, r12b; OldIrql
0x1400402ce  mov     rcx, r14; SpinLock
0x1400402d1  call    cs:__imp_ExReleaseSpinLockShared
0x1400402d8  nop     dword ptr [rax+rax+00h]
0x1400402dd  mov     rdx, [rsp+158h+arg_8]; struct SIO_SPACE *
0x1400402e5  mov     rcx, rsi; this
0x1400402e8  call    ?FlushSynchronous@SIO_SLOTS@@QEAAJPEAVSIO_SPACE@@@Z; SIO_SLOTS::FlushSynchronous(SIO_SPACE *)
0x1400402ed  mov     edi, eax
0x1400402ef  test    eax, eax
0x1400402f1  js      loc_14004025C
0x1400402f7  lea     rdx, [rsp+158h+var_138]; struct SC_PACKET *
0x1400402fc  mov     rcx, rsi; this
0x1400402ff  call    ?WriteCheckpoint@SIO_SLOTS@@QEAAJPEAVSC_PACKET@@@Z; SIO_SLOTS::WriteCheckpoint(SC_PACKET *)
0x140040304  mov     edi, eax
0x140040306  jmp     loc_14004025C
```
