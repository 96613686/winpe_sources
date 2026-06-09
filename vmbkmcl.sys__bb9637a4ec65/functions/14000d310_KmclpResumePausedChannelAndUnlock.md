# KmclpResumePausedChannelAndUnlock

- ea: `0x14000d310`
- end: `0x14000d835`
- name: `KmclpResumePausedChannelAndUnlock`
- size: `1317`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `5`
- callee_count: `12`
- tags: ``

## callers

- `0x14000abe0`
- `0x14000afe8`
- `0x14000defc`
- `0x14000e4e0`
- `0x14000e9e0`

## callees

- `0x140005250`
- `0x140006dc8`
- `0x140006e00`
- `0x140008338`
- `0x14000ab90`
- `0x14000bb70`
- `0x14000d310`
- `0x14000defc`
- `0x14000e148`
- `0x14000f5c4`
- `0x14000f9dc`
- `0x140011ed0`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000d5cf`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000d5cf`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000d5b9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000d5b9`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000d677`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000d677`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d683`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d683`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d401`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d401`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d42e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d42e`

## pseudocode

```c
void __fastcall KmclpResumePausedChannelAndUnlock(char *Context, __int64 a2, __int64 a3)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  KIRQL v6; // al
  __int64 v7; // rdx
  char v8; // al
  __int64 (__fastcall *v9)(); // rdx
  char *i; // rbx
  __int64 v11; // r8
  __int64 v12; // r8
  __int64 v13; // r8
  int v14; // ebx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rdx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 70, a3, Context, *((_DWORD *)Context + 550));
  }
  *((_DWORD *)Context + 550) = 6;
  v4 = _InterlockedIncrement((volatile signed __int32 *)Context + 824) % 24;
  v5 = v4 + 207;
  v4 *= 2;
  *(_QWORD *)&Context[8 * v4 + 3304] = MEMORY[0xFFFFF78000000008];
  Context[16 * v5] = Context[2200];
  Context[8 * v4 + 3313] = Context[2204];
  *(_WORD *)&Context[8 * v4 + 3314] = *((_DWORD *)Context + 554);
  *(_WORD *)&Context[8 * v4 + 3316] = 2689;
  if ( !Context[1729] )
  {
    v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Context + 32);
    *((_DWORD *)Context + 66) = (*((_QWORD *)Context + 34) != (_QWORD)(Context + 272)) + 1;
    KeReleaseSpinLock((PKSPIN_LOCK)Context + 32, v6);
  }
  KmclUnlockChannel(Context);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 71, WPP_fa014546bb113ca58de70d4b381949e7_Traceguids, Context);
  }
  if ( Context[2024] )
    (*((void (__fastcall **)(char *, _QWORD))Context + 259))(Context, *((_QWORD *)Context + 255));
  else
    (*((void (__fastcall **)(char *))Context + 258))(Context);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 72, WPP_fa014546bb113ca58de70d4b381949e7_Traceguids, Context);
  }
  v8 = Context[1729];
  if ( !v8 || *((_QWORD *)Context + 266) )
  {
    v9 = KmclpVmbusManualIsr;
    if ( !v8 )
      v9 = KmclpVmbusIsr;
    (*((void (__fastcall **)(_QWORD, __int64 (__fastcall *)(), char *))Context + 312))(
      *((_QWORD *)Context + 296),
      v9,
      Context);
  }
  if ( !Context[1729] )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 73, WPP_fa014546bb113ca58de70d4b381949e7_Traceguids, Context);
    }
    LOBYTE(v7) = 1;
    OutPollQueue(Context, v7);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 74, WPP_fa014546bb113ca58de70d4b381949e7_Traceguids, Context);
    }
    InStartQueue(Context);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 75, WPP_fa014546bb113ca58de70d4b381949e7_Traceguids, Context);
    }
  }
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(Context + 3176));
  for ( i = (char *)*((_QWORD *)Context + 404); i != Context + 3232; i = *(char **)i )
  {
    KmclLockChannel(i - 3248);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 76, v11, Context, i - 3248);
    }
    KmclpStartChannelAndUnlock(i - 3248);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 77, v12, Context, i - 3248);
    }
  }
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(Context + 3176));
  KeLeaveCriticalRegion();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 78, WPP_fa014546bb113ca58de70d4b381949e7_Traceguids, Context);
  }
  if ( Context[2024] )
    (*((void (__fastcall **)(char *, _QWORD))Context + 260))(Context, *((_QWORD *)Context + 255));
  else
    (*((void (__fastcall **)(char *))Context + 259))(Context);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 79, WPP_fa014546bb113ca58de70d4b381949e7_Traceguids, Context);
  }
  KmclLockChannel(Context);
  v14 = *((_DWORD *)Context + 550);
  *((_DWORD *)Context + 550) = 7;
  v15 = _InterlockedIncrement((volatile signed __int32 *)Context + 824) % 24;
  v16 = v15 + 207;
  v17 = 2 * v15;
  *(_QWORD *)&Context[8 * v17 + 3304] = MEMORY[0xFFFFF78000000008];
  Context[16 * v16] = Context[2200];
  Context[8 * v17 + 3313] = Context[2204];
  *(_WORD *)&Context[8 * v17 + 3314] = *((_DWORD *)Context + 554);
  *(_WORD *)&Context[8 * v17 + 3316] = 2851;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 80, v13, Context, v14);
  }
  if ( v14 == 6 )
  {
    KmclpStartWaitForAction(Context);
    KmclUnlockChannel(Context);
  }
  else
  {
    KmclpContinueChannelRundownAndUnlock(Context, v17, v13);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 81, WPP_fa014546bb113ca58de70d4b381949e7_Traceguids, Context);
  }
}

```

## disassembly

```asm
0x14000d310  push    rbx
0x14000d312  push    rbp
0x14000d313  push    rsi
0x14000d314  push    rdi
0x14000d315  push    r12
0x14000d317  push    r13
0x14000d319  push    r14
0x14000d31b  push    r15
0x14000d31d  sub     rsp, 38h
0x14000d321  mov     rdi, rcx
0x14000d324  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d32b  lea     r13, WPP_GLOBAL_Control
0x14000d332  mov     r12b, 4
0x14000d335  mov     r15d, 1
0x14000d33b  cmp     rcx, r13
0x14000d33e  jz      short loc_14000D368
0x14000d340  mov     eax, [rcx+2Ch]
0x14000d343  test    r15b, al
0x14000d346  jz      short loc_14000D368
0x14000d348  cmp     [rcx+29h], r12b
0x14000d34c  jb      short loc_14000D368
0x14000d34e  mov     eax, [rdi+898h]
0x14000d354  lea     edx, [r15+45h]
0x14000d358  mov     rcx, [rcx+18h]
0x14000d35c  mov     r9, rdi
0x14000d35f  mov     dword ptr [rsp+78h+var_58], eax
0x14000d363  call    WPP_SF_qd
0x14000d368  mov     dword ptr [rdi+898h], 6
0x14000d372  mov     ecx, r15d
0x14000d375  lock xadd [rdi+0CE0h], ecx
0x14000d37d  add     ecx, r15d
0x14000d380  mov     eax, 2AAAAAABh
0x14000d385  imul    ecx
0x14000d387  xor     ebp, ebp
0x14000d389  sar     edx, 2
0x14000d38c  mov     eax, edx
0x14000d38e  shr     eax, 1Fh
0x14000d391  add     edx, eax
0x14000d393  lea     eax, [rdx+rdx*2]
0x14000d396  shl     eax, 3
0x14000d399  sub     ecx, eax
0x14000d39b  mov     rax, ds:0FFFFF78000000008h
0x14000d3a5  movsxd  rcx, ecx
0x14000d3a8  mov     rdx, rcx
0x14000d3ab  add     rcx, 0CFh
0x14000d3b2  add     rdx, rdx
0x14000d3b5  add     rcx, rcx
0x14000d3b8  mov     [rdi+rdx*8+0CE8h], rax
0x14000d3c0  mov     al, [rdi+898h]
0x14000d3c6  mov     [rdi+rcx*8], al
0x14000d3c9  mov     al, [rdi+89Ch]
0x14000d3cf  mov     [rdi+rdx*8+0CF1h], al
0x14000d3d6  mov     eax, [rdi+8A8h]
0x14000d3dc  mov     [rdi+rdx*8+0CF2h], ax
0x14000d3e4  mov     word ptr [rdi+rdx*8+0CF4h], 0A81h
0x14000d3ee  cmp     [rdi+6C1h], bpl
0x14000d3f5  jnz     short loc_14000D43A
0x14000d3f7  lea     rbx, [rdi+100h]
0x14000d3fe  mov     rcx, rbx; SpinLock
0x14000d401  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000d408  nop     dword ptr [rax+rax+00h]
0x14000d40d  mov     edx, ebp
0x14000d40f  mov     rcx, rbx; SpinLock
0x14000d412  mov     r8b, al
0x14000d415  lea     rax, [rdi+110h]
0x14000d41c  cmp     [rax], rax
0x14000d41f  setnz   dl
0x14000d422  add     edx, r15d
0x14000d425  mov     [rdi+108h], edx
0x14000d42b  mov     dl, r8b; NewIrql
0x14000d42e  call    cs:__imp_KeReleaseSpinLock
0x14000d435  nop     dword ptr [rax+rax+00h]
0x14000d43a  mov     rcx, rdi
0x14000d43d  call    KmclUnlockChannel
0x14000d442  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d449  lea     rsi, WPP_fa014546bb113ca58de70d4b381949e7_Traceguids
0x14000d450  cmp     rcx, r13
0x14000d453  jz      short loc_14000D477
0x14000d455  mov     eax, [rcx+2Ch]
0x14000d458  test    r15b, al
0x14000d45b  jz      short loc_14000D477
0x14000d45d  cmp     [rcx+29h], r12b
0x14000d461  jb      short loc_14000D477
0x14000d463  mov     rcx, [rcx+18h]
0x14000d467  mov     edx, 47h ; 'G'
0x14000d46c  mov     r9, rdi
0x14000d46f  mov     r8, rsi
0x14000d472  call    WPP_SF_q
0x14000d477  mov     rcx, rdi
0x14000d47a  cmp     [rdi+7E8h], bpl
0x14000d481  jz      short loc_14000D498
0x14000d483  mov     rax, [rdi+818h]
0x14000d48a  mov     rdx, [rdi+7F8h]
0x14000d491  call    _guard_dispatch_icall
0x14000d496  jmp     short loc_14000D4A4
0x14000d498  mov     rax, [rdi+810h]
0x14000d49f  call    _guard_dispatch_icall
0x14000d4a4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d4ab  cmp     rcx, r13
0x14000d4ae  jz      short loc_14000D4D2
0x14000d4b0  mov     eax, [rcx+2Ch]
0x14000d4b3  test    r15b, al
0x14000d4b6  jz      short loc_14000D4D2
0x14000d4b8  cmp     [rcx+29h], r12b
0x14000d4bc  jb      short loc_14000D4D2
0x14000d4be  mov     rcx, [rcx+18h]
0x14000d4c2  mov     edx, 48h ; 'H'
0x14000d4c7  mov     r9, rdi
0x14000d4ca  mov     r8, rsi
0x14000d4cd  call    WPP_SF_q
0x14000d4d2  mov     al, [rdi+6C1h]
0x14000d4d8  test    al, al
0x14000d4da  jz      short loc_14000D4E5
0x14000d4dc  cmp     [rdi+850h], rbp
0x14000d4e3  jz      short loc_14000D50F
0x14000d4e5  test    al, al
0x14000d4e7  lea     rcx, KmclpVmbusIsr
0x14000d4ee  mov     rax, [rdi+9C0h]
0x14000d4f5  lea     rdx, KmclpVmbusManualIsr
0x14000d4fc  cmovz   rdx, rcx
0x14000d500  mov     r8, rdi
0x14000d503  mov     rcx, [rdi+940h]
0x14000d50a  call    _guard_dispatch_icall
0x14000d50f  cmp     [rdi+6C1h], bpl
0x14000d516  jnz     loc_14000D5B9
0x14000d51c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d523  cmp     rcx, r13
0x14000d526  jz      short loc_14000D54A
0x14000d528  mov     eax, [rcx+2Ch]
0x14000d52b  test    r15b, al
0x14000d52e  jz      short loc_14000D54A
0x14000d530  cmp     [rcx+29h], r12b
0x14000d534  jb      short loc_14000D54A
0x14000d536  mov     rcx, [rcx+18h]
0x14000d53a  mov     edx, 49h ; 'I'
0x14000d53f  mov     r9, rdi
0x14000d542  mov     r8, rsi
0x14000d545  call    WPP_SF_q
0x14000d54a  mov     dl, r15b
0x14000d54d  mov     rcx, rdi
0x14000d550  call    OutPollQueue
0x14000d555  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d55c  cmp     rcx, r13
0x14000d55f  jz      short loc_14000D583
0x14000d561  mov     eax, [rcx+2Ch]
0x14000d564  test    r15b, al
0x14000d567  jz      short loc_14000D583
0x14000d569  cmp     [rcx+29h], r12b
0x14000d56d  jb      short loc_14000D583
0x14000d56f  mov     rcx, [rcx+18h]
0x14000d573  mov     edx, 4Ah ; 'J'
0x14000d578  mov     r9, rdi
0x14000d57b  mov     r8, rsi
0x14000d57e  call    WPP_SF_q
0x14000d583  mov     rcx, rdi
0x14000d586  call    InStartQueue
0x14000d58b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d592  cmp     rcx, r13
0x14000d595  jz      short loc_14000D5B9
0x14000d597  mov     eax, [rcx+2Ch]
0x14000d59a  test    r15b, al
0x14000d59d  jz      short loc_14000D5B9
0x14000d59f  cmp     [rcx+29h], r12b
0x14000d5a3  jb      short loc_14000D5B9
0x14000d5a5  mov     rcx, [rcx+18h]
0x14000d5a9  mov     edx, 4Bh ; 'K'
0x14000d5ae  mov     r9, rdi
0x14000d5b1  mov     r8, rsi
0x14000d5b4  call    WPP_SF_q
0x14000d5b9  call    cs:__imp_KeEnterCriticalRegion
0x14000d5c0  nop     dword ptr [rax+rax+00h]
0x14000d5c5  lea     rbp, [rdi+0C68h]
0x14000d5cc  mov     rcx, rbp; FastMutex
0x14000d5cf  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14000d5d6  nop     dword ptr [rax+rax+00h]
0x14000d5db  lea     r14, [rdi+0CA0h]
0x14000d5e2  mov     rbx, [r14]
0x14000d5e5  cmp     rbx, r14
0x14000d5e8  jz      loc_14000D674
0x14000d5ee  lea     rsi, [rbx-0CB0h]
0x14000d5f5  mov     rcx, rsi
0x14000d5f8  call    KmclLockChannel
0x14000d5fd  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d604  cmp     rcx, r13
0x14000d607  jz      short loc_14000D62D
0x14000d609  mov     eax, [rcx+2Ch]
0x14000d60c  test    r15b, al
0x14000d60f  jz      short loc_14000D62D
0x14000d611  cmp     [rcx+29h], r12b
0x14000d615  jb      short loc_14000D62D
0x14000d617  mov     rcx, [rcx+18h]
0x14000d61b  mov     edx, 4Ch ; 'L'
0x14000d620  mov     r9, rdi
0x14000d623  mov     [rsp+78h+var_58], rsi
0x14000d628  call    WPP_SF_qq
0x14000d62d  mov     rcx, rsi; Context
0x14000d630  call    KmclpStartChannelAndUnlock
0x14000d635  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d63c  cmp     rcx, r13
0x14000d63f  jz      short loc_14000D665
0x14000d641  mov     eax, [rcx+2Ch]
0x14000d644  test    r15b, al
0x14000d647  jz      short loc_14000D665
0x14000d649  cmp     [rcx+29h], r12b
0x14000d64d  jb      short loc_14000D665
0x14000d64f  mov     rcx, [rcx+18h]
0x14000d653  mov     edx, 4Dh ; 'M'
0x14000d658  mov     r9, rdi
0x14000d65b  mov     [rsp+78h+var_58], rsi
0x14000d660  call    WPP_SF_qq
0x14000d665  mov     rbx, [rbx]
0x14000d668  cmp     rbx, r14
0x14000d66b  jnz     short loc_14000D5EE
0x14000d66d  lea     rsi, WPP_fa014546bb113ca58de70d4b381949e7_Traceguids
0x14000d674  mov     rcx, rbp; FastMutex
0x14000d677  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14000d67e  nop     dword ptr [rax+rax+00h]
0x14000d683  call    cs:__imp_KeLeaveCriticalRegion
0x14000d68a  nop     dword ptr [rax+rax+00h]
0x14000d68f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d696  cmp     rcx, r13
0x14000d699  jz      short loc_14000D6BD
0x14000d69b  mov     eax, [rcx+2Ch]
0x14000d69e  test    r15b, al
0x14000d6a1  jz      short loc_14000D6BD
0x14000d6a3  cmp     [rcx+29h], r12b
0x14000d6a7  jb      short loc_14000D6BD
0x14000d6a9  mov     rcx, [rcx+18h]
0x14000d6ad  mov     edx, 4Eh ; 'N'
0x14000d6b2  mov     r9, rdi
0x14000d6b5  mov     r8, rsi
0x14000d6b8  call    WPP_SF_q
0x14000d6bd  cmp     byte ptr [rdi+7E8h], 0
0x14000d6c4  mov     rcx, rdi
0x14000d6c7  jz      short loc_14000D6DE
0x14000d6c9  mov     rax, [rdi+820h]
0x14000d6d0  mov     rdx, [rdi+7F8h]
0x14000d6d7  call    _guard_dispatch_icall
0x14000d6dc  jmp     short loc_14000D6EA
0x14000d6de  mov     rax, [rdi+818h]
0x14000d6e5  call    _guard_dispatch_icall
0x14000d6ea  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d6f1  cmp     rcx, r13
0x14000d6f4  jz      short loc_14000D718
0x14000d6f6  mov     eax, [rcx+2Ch]
0x14000d6f9  test    r15b, al
0x14000d6fc  jz      short loc_14000D718
0x14000d6fe  cmp     [rcx+29h], r12b
0x14000d702  jb      short loc_14000D718
0x14000d704  mov     rcx, [rcx+18h]
0x14000d708  mov     edx, 4Fh ; 'O'
0x14000d70d  mov     r9, rdi
0x14000d710  mov     r8, rsi
0x14000d713  call    WPP_SF_q
0x14000d718  mov     rcx, rdi
0x14000d71b  call    KmclLockChannel
0x14000d720  mov     ebx, [rdi+898h]
0x14000d726  mov     ecx, r15d
0x14000d729  mov     dword ptr [rdi+898h], 7
0x14000d733  lock xadd [rdi+0CE0h], ecx
0x14000d73b  add     ecx, r15d
0x14000d73e  mov     eax, 2AAAAAABh
0x14000d743  imul    ecx
0x14000d745  sar     edx, 2
0x14000d748  mov     eax, edx
0x14000d74a  shr     eax, 1Fh
0x14000d74d  add     edx, eax
0x14000d74f  lea     eax, [rdx+rdx*2]
0x14000d752  shl     eax, 3
0x14000d755  sub     ecx, eax
0x14000d757  mov     rax, ds:0FFFFF78000000008h
0x14000d761  movsxd  rcx, ecx
0x14000d764  mov     rdx, rcx
0x14000d767  add     rcx, 0CFh
0x14000d76e  add     rdx, rdx
0x14000d771  add     rcx, rcx
0x14000d774  mov     [rdi+rdx*8+0CE8h], rax
0x14000d77c  mov     al, [rdi+898h]
0x14000d782  mov     [rdi+rcx*8], al
0x14000d785  mov     al, [rdi+89Ch]
0x14000d78b  mov     [rdi+rdx*8+0CF1h], al
0x14000d792  mov     eax, [rdi+8A8h]
0x14000d798  mov     [rdi+rdx*8+0CF2h], ax
0x14000d7a0  mov     word ptr [rdi+rdx*8+0CF4h], 0B23h
0x14000d7aa  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d7b1  cmp     rcx, r13
0x14000d7b4  jz      short loc_14000D7D9
0x14000d7b6  mov     eax, [rcx+2Ch]
0x14000d7b9  test    r15b, al
0x14000d7bc  jz      short loc_14000D7D9
0x14000d7be  cmp     [rcx+29h], r12b
0x14000d7c2  jb      short loc_14000D7D9
0x14000d7c4  mov     rcx, [rcx+18h]
0x14000d7c8  mov     edx, 50h ; 'P'
0x14000d7cd  mov     r9, rdi
0x14000d7d0  mov     dword ptr [rsp+78h+var_58], ebx
0x14000d7d4  call    WPP_SF_qd
0x14000d7d9  mov     rcx, rdi; Context
0x14000d7dc  cmp     ebx, 6
0x14000d7df  jnz     short loc_14000D7F0
  ... truncated ...
```
