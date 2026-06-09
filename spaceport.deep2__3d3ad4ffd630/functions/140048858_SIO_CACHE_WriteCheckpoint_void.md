# SIO_CACHE::WriteCheckpoint(void)

- ea: `0x140048858`
- end: `0x140048a5a`
- name: `?WriteCheckpoint@SIO_CACHE@@IEAAJXZ`
- size: `514`
- prototype: `__int64 __fastcall(SIO_CACHE *__hidden this)`
- caller_count: `3`
- callee_count: `11`
- tags: ``

## callers

- `0x14001dd60`
- `0x140048024`
- `0x140048a60`

## callees

- `0x140009f80`
- `0x14000a070`
- `0x14001df20`
- `0x140026130`
- `0x140026db0`
- `0x14004604c`
- `0x140048858`
- `0x140051b04`
- `0x140051b40`
- `0x140052680`
- `0x140068000`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockShared` at `0x140048992`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x140048a01`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x140048992`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x140048a01`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x140048907`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x140048907`
- `HAL!KeQueryPerformanceCounter` at `0x140048891`
- `HAL!KeQueryPerformanceCounter` at `0x140048a1e`
- `HAL!KeQueryPerformanceCounter` at `0x140048891`
- `HAL!KeQueryPerformanceCounter` at `0x140048a1e`

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
0x140048858  mov     [rsp+arg_10], rbx
0x14004885d  push    rbp
0x14004885e  push    rsi
0x14004885f  push    rdi
0x140048860  push    r12
0x140048862  push    r13
0x140048864  push    r14
0x140048866  push    r15
0x140048868  sub     rsp, 130h
0x14004886f  mov     rsi, rcx
0x140048872  lea     rcx, [rsp+168h+var_138]; this
0x140048877  call    ??0SC_PACKET@@QEAA@XZ; SC_PACKET::SC_PACKET(void)
0x14004887c  mov     rcx, [rsi+8]
0x140048880  mov     rax, [rcx]
0x140048883  mov     rax, [rax+50h]
0x140048887  call    _guard_dispatch_icall
0x14004888c  xor     ecx, ecx; PerformanceFrequency
0x14004888e  mov     r13, rax
0x140048891  call    cs:__imp_KeQueryPerformanceCounter
0x140048898  nop     dword ptr [rax+rax+00h]
0x14004889d  mov     dl, 0Bh
0x14004889f  mov     rcx, r13
0x1400488a2  mov     r14, rax
0x1400488a5  mov     [rsp+168h+arg_0], rax
0x1400488ad  call    ?GetChild@SIO_SPACE@@QEAAPEAV1@W4_SC_SPACE_USAGE@@@Z; SIO_SPACE::GetChild(_SC_SPACE_USAGE)
0x1400488b2  lea     r15, [rsi+10h]
0x1400488b6  mov     [rsp+168h+arg_8], rax
0x1400488be  mov     edx, [r15+30h]; unsigned int
0x1400488c2  lea     r8, [rsp+168h+var_138]; struct SC_PACKET *
0x1400488c7  mov     rcx, r15; this
0x1400488ca  call    ?GetCheckpointPacket@SIO_SLOTS@@QEAAJKPEAVSC_PACKET@@@Z; SIO_SLOTS::GetCheckpointPacket(ulong,SC_PACKET *)
0x1400488cf  mov     edi, eax
0x1400488d1  test    eax, eax
0x1400488d3  js      loc_1400489D9
0x1400488d9  mov     ecx, [rsi+264h]
0x1400488df  cmp     ecx, 4
0x1400488e2  jz      short loc_1400488E9
0x1400488e4  cmp     ecx, 1
0x1400488e7  jnz     short loc_1400488FD
0x1400488e9  mov     rax, [rsp+168h+var_C0]
0x1400488f1  mov     edx, [rax+2Ch]
0x1400488f4  mov     rcx, [rax+20h]
0x1400488f8  or      dword ptr [rdx+rcx+20h], 1
0x1400488fd  lea     rbx, [rsi+158h]
0x140048904  mov     rcx, rbx; SpinLock
0x140048907  call    cs:__imp_ExAcquireSpinLockShared
0x14004890e  nop     dword ptr [rax+rax+00h]
0x140048913  lea     rcx, [rsi+1B0h]
0x14004891a  xor     edi, edi
0x14004891c  mov     [rsp+168h+var_148], rcx
0x140048921  mov     r12b, al
0x140048924  lea     rcx, [rsi+1C0h]
0x14004892b  mov     [rsp+168h+var_140], rcx
0x140048930  cmp     edi, 2
0x140048933  jnb     short loc_14004898C
0x140048935  mov     rbp, [rsp+rdi*8+168h+var_148]
0x14004893a  mov     r14, [rbp+0]
0x14004893e  cmp     r14, rbp
0x140048941  jz      short loc_140048976
0x140048943  lea     rdx, [rsp+168h+var_138]; struct SC_PACKET *
0x140048948  mov     rcx, r15; this
0x14004894b  call    ?GetCheckpointEntry@SIO_SLOTS@@QEAAPEAXPEAVSC_PACKET@@@Z; SIO_SLOTS::GetCheckpointEntry(SC_PACKET *)
0x140048950  test    rax, rax
0x140048953  jz      short loc_14004897A
0x140048955  lea     rdx, [r14-10h]; struct SIO_CACHE_LINE *
0x140048959  mov     r9, rax; struct SIO_LINE_ENTRY *
0x14004895c  xor     r8d, r8d; unsigned __int8
0x14004895f  mov     rcx, rsi; this
0x140048962  call    ?FormatLine@SIO_CACHE@@IEAAKPEAVSIO_CACHE_LINE@@EPEAVSIO_LINE_ENTRY@@@Z; SIO_CACHE::FormatLine(SIO_CACHE_LINE *,uchar,SIO_LINE_ENTRY *)
0x140048967  mov     ecx, eax
0x140048969  add     [rsp+168h+var_78], rcx
0x140048971  mov     r14, [r14]
0x140048974  jmp     short loc_14004893E
0x140048976  inc     edi
0x140048978  jmp     short loc_140048930
0x14004897a  mov     bpl, 1
0x14004897d  mov     edi, 0C0E70026h
0x140048982  mov     r14, [rsp+168h+arg_0]
0x14004898a  jmp     short loc_1400489E6
0x14004898c  mov     dl, r12b; OldIrql
0x14004898f  mov     rcx, rbx; SpinLock
0x140048992  call    cs:__imp_ExReleaseSpinLockShared
0x140048999  nop     dword ptr [rax+rax+00h]
0x14004899e  mov     rdx, [rsp+168h+arg_8]; struct SIO_SPACE *
0x1400489a6  mov     rcx, r15; this
0x1400489a9  xor     bpl, bpl
0x1400489ac  call    ?FlushSynchronous@SIO_SLOTS@@QEAAJPEAVSIO_SPACE@@@Z; SIO_SLOTS::FlushSynchronous(SIO_SPACE *)
0x1400489b1  mov     edi, eax
0x1400489b3  test    eax, eax
0x1400489b5  js      short loc_140048982
0x1400489b7  mov     rdx, r13; struct SIO_SPACE *
0x1400489ba  mov     rcx, r15; this
0x1400489bd  call    ?FlushSynchronous@SIO_SLOTS@@QEAAJPEAVSIO_SPACE@@@Z; SIO_SLOTS::FlushSynchronous(SIO_SPACE *)
0x1400489c2  mov     edi, eax
0x1400489c4  test    eax, eax
0x1400489c6  js      short loc_140048982
0x1400489c8  lea     rdx, [rsp+168h+var_138]; struct SC_PACKET *
0x1400489cd  mov     rcx, r15; this
0x1400489d0  call    ?WriteCheckpoint@SIO_SLOTS@@QEAAJPEAVSC_PACKET@@@Z; SIO_SLOTS::WriteCheckpoint(SC_PACKET *)
0x1400489d5  mov     edi, eax
0x1400489d7  jmp     short loc_140048982
0x1400489d9  xor     r12b, r12b
0x1400489dc  lea     rbx, [rsi+158h]
0x1400489e3  xor     bpl, bpl
0x1400489e6  mov     r8d, edi
0x1400489e9  mov     edx, 7
0x1400489ee  mov     rcx, rsi
0x1400489f1  call    ?LogStatus@SIO_CACHE@@IEAAXW4SIO_CACHE_OPERATION@@J@Z; SIO_CACHE::LogStatus(SIO_CACHE_OPERATION,long)
0x1400489f6  test    bpl, bpl
0x1400489f9  jz      short loc_140048A0D
0x1400489fb  mov     dl, r12b; OldIrql
0x1400489fe  mov     rcx, rbx; SpinLock
0x140048a01  call    cs:__imp_ExReleaseSpinLockShared
0x140048a08  nop     dword ptr [rax+rax+00h]
0x140048a0d  mov     rbx, [rsi+280h]
0x140048a14  lock inc dword ptr [rbx+24h]
0x140048a18  lock inc dword ptr [rbx+1Ch]
0x140048a1c  xor     ecx, ecx; PerformanceFrequency
0x140048a1e  call    cs:__imp_KeQueryPerformanceCounter
0x140048a25  nop     dword ptr [rax+rax+00h]
0x140048a2a  sub     rax, r14
0x140048a2d  lock add [rbx+30h], rax
0x140048a32  lea     rcx, [rsp+168h+var_138]; this
0x140048a37  call    ??1SIO_LOG_PACKET@@UEAA@XZ; SIO_LOG_PACKET::~SIO_LOG_PACKET(void)
0x140048a3c  mov     rbx, [rsp+168h+arg_10]
0x140048a44  mov     eax, edi
0x140048a46  add     rsp, 130h
0x140048a4d  pop     r15
0x140048a4f  pop     r14
0x140048a51  pop     r13
0x140048a53  pop     r12
0x140048a55  pop     rdi
0x140048a56  pop     rsi
0x140048a57  pop     rbp
0x140048a58  retn
```
