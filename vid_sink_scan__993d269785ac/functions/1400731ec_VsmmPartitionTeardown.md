# VsmmPartitionTeardown

- ea: `0x1400731ec`
- end: `0x1400733a3`
- name: `VsmmPartitionTeardown`
- size: `439`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140011dd0`

## callees

- `0x140034554`
- `0x140034584`
- `0x140034914`
- `0x1400731ec`
- `0x1400733ac`
- `0x140073420`
- `0x140073548`
- `0x1400735d8`
- `0x140073b44`
- `0x140074edc`
- `0x14007556c`
- `0x140075858`
- `0x140075a88`
- `0x14007a578`
- `0x14009e44c`
- `0x1400cc878`
- `0x1400e3428`
- `0x1400ea8b8`
- `0x1400f80e4`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140073212`
- `ntoskrnl!KeWaitForSingleObject` at `0x140073212`
- `ntoskrnl!ExFlushLookasideListEx` at `0x140073378`
- `ntoskrnl!ExFlushLookasideListEx` at `0x140073378`

## pseudocode

```c
void __fastcall VsmmPartitionTeardown(__int64 a1)
{
  __int64 v2; // rax
  _QWORD *v3; // r14
  unsigned __int8 i; // di
  __int64 v5; // rbp
  int j; // esi

  KeWaitForSingleObject((PVOID)(a1 + 8576), Executive, 0, 0, 0);
  VsmmMemXferPartitionTeardown(a1);
  VidVpGlobalSuspendBegin(a1);
  VsmmEpfPartitionReset(a1);
  if ( *(_BYTE *)(a1 + 10648) )
    VidOpCtrlExUnblock(a1 + 10488);
  _InterlockedDecrement((volatile signed __int32 *)(a1 + 3216));
  VsmmVaGpaRangepBackgroundDecommitTeardown(a1);
  if ( (unsigned __int64)((*(_QWORD *)(a1 + 10432) >> 61) - 3LL) <= 1 )
    VsmmPartitionUnblockDeviceAttach(a1);
  VidObjectLockAcquireShared(a1);
  VidObjectLockAcquireExclusive(a1 + 3736);
  VsmmDmSlpCleanup(a1);
  VsmmPpmInfoTeardown(a1);
  v2 = *(_QWORD *)(a1 + 32) & 0x1E0LL;
  if ( v2 == 32 )
  {
    if ( *(_BYTE *)(a1 + 8848) && (*(_DWORD *)(a1 + 8636) != 2 || *(_DWORD *)(a1 + 8632) != 2) )
      VsmmSvcPartitionTeardown(a1);
  }
  else if ( ((v2 - 64) & 0xFFFFFFFFFFFFFFDFuLL) == 0 )
  {
    VsmmHwIsoPartitionTeardown(a1);
  }
  if ( (*(_DWORD *)(a1 + 16) & 0x8000LL) != 0 )
    VsmmVaGpaCoreTeardown(a1);
  VsmmGpaRangeCleanup(a1);
  VsmmCryptPartitionKeysRelease(a1);
  VsmmTeardownMemoryBlockReadWriteBuffers(a1);
  if ( (*(_DWORD *)(a1 + 32) & 0x1E0LL) == 0x60 )
    VidTdxTeardown(a1);
  VidObjectLockRelease(a1 + 3736);
  VidObjectLockRelease(a1);
  v3 = VidDeviceExtension;
  for ( i = 0; i < *(_BYTE *)(a1 + 2040); ++i )
  {
    v5 = *(_QWORD *)(v3[33] + 8LL * *(unsigned __int8 *)(i + a1 + 2041)) + 224LL;
    for ( j = 0; j != 2; ++j )
      ExFlushLookasideListEx((PLOOKASIDE_LIST_EX)(v5 + 96LL * j));
  }
}

```

## disassembly

```asm
0x1400731ec  push    rbx
0x1400731ee  push    rbp
0x1400731ef  push    rsi
0x1400731f0  push    rdi
0x1400731f1  push    r14
0x1400731f3  sub     rsp, 30h
0x1400731f7  mov     rbx, rcx
0x1400731fa  mov     [rsp+58h+Timeout], 0; Timeout
0x140073203  add     rcx, 2180h; Object
0x14007320a  xor     r9d, r9d; Alertable
0x14007320d  xor     r8d, r8d; WaitMode
0x140073210  xor     edx, edx; WaitReason
0x140073212  call    cs:__imp_KeWaitForSingleObject
0x140073219  nop     dword ptr [rax+rax+00h]
0x14007321e  mov     rcx, rbx
0x140073221  call    VsmmMemXferPartitionTeardown
0x140073226  mov     rcx, rbx
0x140073229  call    VidVpGlobalSuspendBegin
0x14007322e  mov     rcx, rbx
0x140073231  call    VsmmEpfPartitionReset
0x140073236  cmp     byte ptr [rbx+2998h], 0
0x14007323d  jz      short loc_14007324B
0x14007323f  lea     rcx, [rbx+28F8h]
0x140073246  call    VidOpCtrlExUnblock
0x14007324b  lock dec dword ptr [rbx+0C90h]
0x140073252  mov     rcx, rbx
0x140073255  call    VsmmVaGpaRangepBackgroundDecommitTeardown
0x14007325a  mov     rax, [rbx+28C0h]
0x140073261  shr     rax, 3Dh
0x140073265  sub     rax, 3
0x140073269  cmp     rax, 1
0x14007326d  ja      short loc_140073277
0x14007326f  mov     rcx, rbx
0x140073272  call    VsmmPartitionUnblockDeviceAttach
0x140073277  mov     rcx, rbx
0x14007327a  call    VidObjectLockAcquireShared
0x14007327f  lea     rdi, [rbx+0E98h]
0x140073286  mov     rcx, rdi
0x140073289  call    VidObjectLockAcquireExclusive
0x14007328e  mov     rcx, rbx
0x140073291  call    VsmmDmSlpCleanup
0x140073296  mov     rcx, rbx
0x140073299  call    VsmmPpmInfoTeardown
0x14007329e  mov     rax, [rbx+20h]
0x1400732a2  mov     esi, 1E0h
0x1400732a7  and     rax, rsi
0x1400732aa  cmp     rax, 20h ; ' '
0x1400732ae  jnz     short loc_1400732D5
0x1400732b0  cmp     byte ptr [rbx+2290h], 0
0x1400732b7  jz      short loc_1400732E9
0x1400732b9  cmp     dword ptr [rbx+21BCh], 2
0x1400732c0  jnz     short loc_1400732CB
0x1400732c2  cmp     dword ptr [rbx+21B8h], 2
0x1400732c9  jz      short loc_1400732E9
0x1400732cb  mov     rcx, rbx
0x1400732ce  call    VsmmSvcPartitionTeardown
0x1400732d3  jmp     short loc_1400732E9
0x1400732d5  add     rax, 0FFFFFFFFFFFFFFC0h
0x1400732d9  test    rax, 0FFFFFFFFFFFFFFDFh
0x1400732df  jnz     short loc_1400732E9
0x1400732e1  mov     rcx, rbx
0x1400732e4  call    VsmmHwIsoPartitionTeardown
0x1400732e9  mov     eax, [rbx+10h]
0x1400732ec  bt      rax, 0Fh
0x1400732f1  jnb     short loc_1400732FB
0x1400732f3  mov     rcx, rbx
0x1400732f6  call    VsmmVaGpaCoreTeardown
0x1400732fb  mov     rcx, rbx
0x1400732fe  call    VsmmGpaRangeCleanup
0x140073303  mov     rcx, rbx
0x140073306  call    VsmmCryptPartitionKeysRelease
0x14007330b  mov     rcx, rbx
0x14007330e  call    VsmmTeardownMemoryBlockReadWriteBuffers
0x140073313  mov     eax, [rbx+20h]
0x140073316  and     rax, rsi
0x140073319  cmp     rax, 60h ; '`'
0x14007331d  jnz     short loc_140073327
0x14007331f  mov     rcx, rbx
0x140073322  call    VidTdxTeardown
0x140073327  mov     rcx, rdi
0x14007332a  call    VidObjectLockRelease
0x14007332f  mov     rcx, rbx
0x140073332  call    VidObjectLockRelease
0x140073337  mov     r14, cs:VidDeviceExtension
0x14007333e  xor     dil, dil
0x140073341  cmp     [rbx+7F8h], dil
0x140073348  jbe     short loc_140073397
0x14007334a  movzx   eax, dil
0x14007334e  movzx   ecx, byte ptr [rax+rbx+7F9h]
0x140073356  mov     rax, [r14+108h]
0x14007335d  mov     rbp, [rax+rcx*8]
0x140073361  add     rbp, 0E0h
0x140073368  xor     esi, esi
0x14007336a  movsxd  rax, esi
0x14007336d  lea     rcx, [rax+rax*2]
0x140073371  shl     rcx, 5
0x140073375  add     rcx, rbp; Lookaside
0x140073378  call    cs:__imp_ExFlushLookasideListEx
0x14007337f  nop     dword ptr [rax+rax+00h]
0x140073384  inc     esi
0x140073386  cmp     esi, 2
0x140073389  jnz     short loc_14007336A
0x14007338b  inc     dil
0x14007338e  cmp     dil, [rbx+7F8h]
0x140073395  jb      short loc_14007334A
0x140073397  add     rsp, 30h
0x14007339b  pop     r14
0x14007339d  pop     rdi
0x14007339e  pop     rsi
0x14007339f  pop     rbp
0x1400733a0  pop     rbx
0x1400733a1  retn
```
