# SIO_CACHE::WriteCheckpoint(void)

- ea: `0x140048918`
- end: `0x140048b1a`
- name: `?WriteCheckpoint@SIO_CACHE@@IEAAJXZ`
- size: `514`
- prototype: `__int64 __fastcall(SIO_CACHE *__hidden this)`
- caller_count: `3`
- callee_count: `11`
- tags: ``

## callers

- `0x14001dd60`
- `0x1400480e4`
- `0x140048b20`

## callees

- `0x140009f80`
- `0x14000a070`
- `0x14001df20`
- `0x140026130`
- `0x140026db0`
- `0x14004610c`
- `0x140048918`
- `0x140051bc4`
- `0x140051c00`
- `0x140052740`
- `0x140068150`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockShared` at `0x140048a52`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x140048ac1`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x140048a52`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x140048ac1`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x1400489c7`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x1400489c7`
- `HAL!KeQueryPerformanceCounter` at `0x140048951`
- `HAL!KeQueryPerformanceCounter` at `0x140048ade`
- `HAL!KeQueryPerformanceCounter` at `0x140048951`
- `HAL!KeQueryPerformanceCounter` at `0x140048ade`

## pseudocode

```c
__int64 __fastcall SIO_CACHE::WriteCheckpoint(SIO_CACHE *this)
{
  struct SIO_SPACE *v2; // r13
  LARGE_INTEGER PerformanceCounter; // rax
  __int64 v4; // rdx
  LARGE_INTEGER v5; // r14
  int CheckpointPacket; // edi
  int v7; // ecx
  volatile LONG *v8; // rbx
  __int64 v9; // rdi
  KIRQL v10; // r12
  _QWORD **v11; // rbp
  _QWORD *i; // r14
  struct SIO_LINE_ENTRY *CheckpointEntry; // rax
  unsigned int v14; // eax
  char v15; // bp
  __int64 v16; // rbx
  _QWORD v18[2]; // [rsp+20h] [rbp-148h]
  _BYTE v19[120]; // [rsp+30h] [rbp-138h] BYREF
  __int64 v20; // [rsp+A8h] [rbp-C0h]
  __int64 v21; // [rsp+F0h] [rbp-78h]
  LARGE_INTEGER v22; // [rsp+170h] [rbp+8h]
  struct SIO_SPACE *Child; // [rsp+178h] [rbp+10h]

  SC_PACKET::SC_PACKET((SC_PACKET *)v19);
  v2 = (struct SIO_SPACE *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 80LL))(*((_QWORD *)this + 1));
  PerformanceCounter = KeQueryPerformanceCounter(0);
  LOBYTE(v4) = 11;
  v5 = PerformanceCounter;
  v22 = PerformanceCounter;
  Child = (struct SIO_SPACE *)SIO_SPACE::GetChild(v2, v4);
  CheckpointPacket = SIO_SLOTS::GetCheckpointPacket(
                       (SIO_CACHE *)((char *)this + 16),
                       *((_DWORD *)this + 16),
                       (struct SC_PACKET *)v19);
  if ( CheckpointPacket < 0 )
  {
    v10 = 0;
    v8 = (volatile LONG *)((char *)this + 344);
    v15 = 0;
  }
  else
  {
    v7 = *((_DWORD *)this + 153);
    if ( v7 == 4 || v7 == 1 )
      *(_DWORD *)(*(unsigned int *)(v20 + 44) + *(_QWORD *)(v20 + 32) + 32LL) |= 1u;
    v8 = (volatile LONG *)((char *)this + 344);
    v9 = 0;
    v18[0] = (char *)this + 432;
    v10 = ExAcquireSpinLockShared((PEX_SPIN_LOCK)this + 86);
    v18[1] = (char *)this + 448;
LABEL_6:
    if ( (unsigned int)v9 >= 2 )
    {
      ExReleaseSpinLockShared((PEX_SPIN_LOCK)this + 86, v10);
      v15 = 0;
      CheckpointPacket = SIO_SLOTS::FlushSynchronous((SIO_CACHE *)((char *)this + 16), Child);
      if ( CheckpointPacket >= 0 )
      {
        CheckpointPacket = SIO_SLOTS::FlushSynchronous((SIO_CACHE *)((char *)this + 16), v2);
        if ( CheckpointPacket >= 0 )
          CheckpointPacket = SIO_SLOTS::WriteCheckpoint((SIO_CACHE *)((char *)this + 16), (struct SC_PACKET *)v19);
      }
    }
    else
    {
      v11 = (_QWORD **)v18[v9];
      for ( i = *v11; ; i = (_QWORD *)*i )
      {
        if ( i == v11 )
        {
          v9 = (unsigned int)(v9 + 1);
          goto LABEL_6;
        }
        CheckpointEntry = (struct SIO_LINE_ENTRY *)SIO_SLOTS::GetCheckpointEntry(
                                                     (SIO_CACHE *)((char *)this + 16),
                                                     (struct SC_PACKET *)v19);
        if ( !CheckpointEntry )
          break;
        v14 = SIO_CACHE::FormatLine(this, (struct SIO_CACHE_LINE *)(i - 2), 0, CheckpointEntry);
        v21 += v14;
      }
      v15 = 1;
      CheckpointPacket = -1058602970;
    }
    v5 = v22;
  }
  SIO_CACHE::LogStatus(this, 7);
  if ( v15 )
    ExReleaseSpinLockShared(v8, v10);
  v16 = *((_QWORD *)this + 80);
  _InterlockedIncrement((volatile signed __int32 *)(v16 + 36));
  _InterlockedIncrement((volatile signed __int32 *)(v16 + 28));
  _InterlockedAdd64((volatile signed __int64 *)(v16 + 48), *(_QWORD *)&KeQueryPerformanceCounter(0) - v5.QuadPart);
  SIO_LOG_PACKET::~SIO_LOG_PACKET((SIO_LOG_PACKET *)v19);
  return (unsigned int)CheckpointPacket;
}

```

## disassembly

```asm
0x140048918  mov     [rsp+arg_10], rbx
0x14004891d  push    rbp
0x14004891e  push    rsi
0x14004891f  push    rdi
0x140048920  push    r12
0x140048922  push    r13
0x140048924  push    r14
0x140048926  push    r15
0x140048928  sub     rsp, 130h
0x14004892f  mov     rsi, rcx
0x140048932  lea     rcx, [rsp+168h+var_138]; this
0x140048937  call    ??0SC_PACKET@@QEAA@XZ; SC_PACKET::SC_PACKET(void)
0x14004893c  mov     rcx, [rsi+8]
0x140048940  mov     rax, [rcx]
0x140048943  mov     rax, [rax+50h]
0x140048947  call    _guard_dispatch_icall
0x14004894c  xor     ecx, ecx; PerformanceFrequency
0x14004894e  mov     r13, rax
0x140048951  call    cs:__imp_KeQueryPerformanceCounter
0x140048958  nop     dword ptr [rax+rax+00h]
0x14004895d  mov     dl, 0Bh
0x14004895f  mov     rcx, r13
0x140048962  mov     r14, rax
0x140048965  mov     [rsp+168h+arg_0], rax
0x14004896d  call    ?GetChild@SIO_SPACE@@QEAAPEAV1@W4_SC_SPACE_USAGE@@@Z; SIO_SPACE::GetChild(_SC_SPACE_USAGE)
0x140048972  lea     r15, [rsi+10h]
0x140048976  mov     [rsp+168h+arg_8], rax
0x14004897e  mov     edx, [r15+30h]; unsigned int
0x140048982  lea     r8, [rsp+168h+var_138]; struct SC_PACKET *
0x140048987  mov     rcx, r15; this
0x14004898a  call    ?GetCheckpointPacket@SIO_SLOTS@@QEAAJKPEAVSC_PACKET@@@Z; SIO_SLOTS::GetCheckpointPacket(ulong,SC_PACKET *)
0x14004898f  mov     edi, eax
0x140048991  test    eax, eax
0x140048993  js      loc_140048A99
0x140048999  mov     ecx, [rsi+264h]
0x14004899f  cmp     ecx, 4
0x1400489a2  jz      short loc_1400489A9
0x1400489a4  cmp     ecx, 1
0x1400489a7  jnz     short loc_1400489BD
0x1400489a9  mov     rax, [rsp+168h+var_C0]
0x1400489b1  mov     edx, [rax+2Ch]
0x1400489b4  mov     rcx, [rax+20h]
0x1400489b8  or      dword ptr [rdx+rcx+20h], 1
0x1400489bd  lea     rbx, [rsi+158h]
0x1400489c4  mov     rcx, rbx; SpinLock
0x1400489c7  call    cs:__imp_ExAcquireSpinLockShared
0x1400489ce  nop     dword ptr [rax+rax+00h]
0x1400489d3  lea     rcx, [rsi+1B0h]
0x1400489da  xor     edi, edi
0x1400489dc  mov     [rsp+168h+var_148], rcx
0x1400489e1  mov     r12b, al
0x1400489e4  lea     rcx, [rsi+1C0h]
0x1400489eb  mov     [rsp+168h+var_140], rcx
0x1400489f0  cmp     edi, 2
0x1400489f3  jnb     short loc_140048A4C
0x1400489f5  mov     rbp, [rsp+rdi*8+168h+var_148]
0x1400489fa  mov     r14, [rbp+0]
0x1400489fe  cmp     r14, rbp
0x140048a01  jz      short loc_140048A36
0x140048a03  lea     rdx, [rsp+168h+var_138]; struct SC_PACKET *
0x140048a08  mov     rcx, r15; this
0x140048a0b  call    ?GetCheckpointEntry@SIO_SLOTS@@QEAAPEAXPEAVSC_PACKET@@@Z; SIO_SLOTS::GetCheckpointEntry(SC_PACKET *)
0x140048a10  test    rax, rax
0x140048a13  jz      short loc_140048A3A
0x140048a15  lea     rdx, [r14-10h]; struct SIO_CACHE_LINE *
0x140048a19  mov     r9, rax; struct SIO_LINE_ENTRY *
0x140048a1c  xor     r8d, r8d; unsigned __int8
0x140048a1f  mov     rcx, rsi; this
0x140048a22  call    ?FormatLine@SIO_CACHE@@IEAAKPEAVSIO_CACHE_LINE@@EPEAVSIO_LINE_ENTRY@@@Z; SIO_CACHE::FormatLine(SIO_CACHE_LINE *,uchar,SIO_LINE_ENTRY *)
0x140048a27  mov     ecx, eax
0x140048a29  add     [rsp+168h+var_78], rcx
0x140048a31  mov     r14, [r14]
0x140048a34  jmp     short loc_1400489FE
0x140048a36  inc     edi
0x140048a38  jmp     short loc_1400489F0
0x140048a3a  mov     bpl, 1
0x140048a3d  mov     edi, 0C0E70026h
0x140048a42  mov     r14, [rsp+168h+arg_0]
0x140048a4a  jmp     short loc_140048AA6
0x140048a4c  mov     dl, r12b; OldIrql
0x140048a4f  mov     rcx, rbx; SpinLock
0x140048a52  call    cs:__imp_ExReleaseSpinLockShared
0x140048a59  nop     dword ptr [rax+rax+00h]
0x140048a5e  mov     rdx, [rsp+168h+arg_8]; struct SIO_SPACE *
0x140048a66  mov     rcx, r15; this
0x140048a69  xor     bpl, bpl
0x140048a6c  call    ?FlushSynchronous@SIO_SLOTS@@QEAAJPEAVSIO_SPACE@@@Z; SIO_SLOTS::FlushSynchronous(SIO_SPACE *)
0x140048a71  mov     edi, eax
0x140048a73  test    eax, eax
0x140048a75  js      short loc_140048A42
0x140048a77  mov     rdx, r13; struct SIO_SPACE *
0x140048a7a  mov     rcx, r15; this
0x140048a7d  call    ?FlushSynchronous@SIO_SLOTS@@QEAAJPEAVSIO_SPACE@@@Z; SIO_SLOTS::FlushSynchronous(SIO_SPACE *)
0x140048a82  mov     edi, eax
0x140048a84  test    eax, eax
0x140048a86  js      short loc_140048A42
0x140048a88  lea     rdx, [rsp+168h+var_138]; struct SC_PACKET *
0x140048a8d  mov     rcx, r15; this
0x140048a90  call    ?WriteCheckpoint@SIO_SLOTS@@QEAAJPEAVSC_PACKET@@@Z; SIO_SLOTS::WriteCheckpoint(SC_PACKET *)
0x140048a95  mov     edi, eax
0x140048a97  jmp     short loc_140048A42
0x140048a99  xor     r12b, r12b
0x140048a9c  lea     rbx, [rsi+158h]
0x140048aa3  xor     bpl, bpl
0x140048aa6  mov     r8d, edi
0x140048aa9  mov     edx, 7
0x140048aae  mov     rcx, rsi
0x140048ab1  call    ?LogStatus@SIO_CACHE@@IEAAXW4SIO_CACHE_OPERATION@@J@Z; SIO_CACHE::LogStatus(SIO_CACHE_OPERATION,long)
0x140048ab6  test    bpl, bpl
0x140048ab9  jz      short loc_140048ACD
0x140048abb  mov     dl, r12b; OldIrql
0x140048abe  mov     rcx, rbx; SpinLock
0x140048ac1  call    cs:__imp_ExReleaseSpinLockShared
0x140048ac8  nop     dword ptr [rax+rax+00h]
0x140048acd  mov     rbx, [rsi+280h]
0x140048ad4  lock inc dword ptr [rbx+24h]
0x140048ad8  lock inc dword ptr [rbx+1Ch]
0x140048adc  xor     ecx, ecx; PerformanceFrequency
0x140048ade  call    cs:__imp_KeQueryPerformanceCounter
0x140048ae5  nop     dword ptr [rax+rax+00h]
0x140048aea  sub     rax, r14
0x140048aed  lock add [rbx+30h], rax
0x140048af2  lea     rcx, [rsp+168h+var_138]; this
0x140048af7  call    ??1SIO_LOG_PACKET@@UEAA@XZ; SIO_LOG_PACKET::~SIO_LOG_PACKET(void)
0x140048afc  mov     rbx, [rsp+168h+arg_10]
0x140048b04  mov     eax, edi
0x140048b06  add     rsp, 130h
0x140048b0d  pop     r15
0x140048b0f  pop     r14
0x140048b11  pop     r13
0x140048b13  pop     r12
0x140048b15  pop     rdi
0x140048b16  pop     rsi
0x140048b17  pop     rbp
0x140048b18  retn
```
