# SP_DEVICE::FlushDestage(void)

- ea: `0x14002b608`
- end: `0x14002b79d`
- name: `?FlushDestage@SP_DEVICE@@QEAAJXZ`
- size: `405`
- prototype: `__int64 __fastcall(SP_DEVICE *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x14002b360`

## callees

- `0x14001e160`
- `0x140026130`
- `0x14002b608`
- `0x14002b7a4`
- `0x14003c778`
- `0x140046a78`
- `0x1400afca4`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14002b665`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14002b6fa`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14002b665`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14002b6fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b77b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b77b`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002b6be`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002b748`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002b6be`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002b748`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14002b6a0`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14002b72e`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14002b6a0`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14002b72e`

## pseudocode

```c
__int64 __fastcall SP_DEVICE::FlushDestage(PEX_RUNDOWN_REF_CACHE_AWARE *this)
{
  int updated; // esi
  PEX_RUNDOWN_REF_CACHE_AWARE *v2; // rdi
  unsigned int v3; // ebx
  PEX_RUNDOWN_REF_CACHE_AWARE *v4; // r14
  PEX_RUNDOWN_REF_CACHE_AWARE v6; // rbx
  KIRQL v7; // al
  __int64 v8; // rdx
  PVOID v9; // r14
  PEX_RUNDOWN_REF_CACHE_AWARE v10; // rdi
  KIRQL v11; // al
  PVOID P; // [rsp+48h] [rbp+10h] BYREF

  updated = 0;
  P = 0;
  v2 = this + 30;
  v3 = 0;
  v4 = this + 30;
  while ( v3 < 0x64 )
  {
    updated = SP_DEVICE::AcquireRundownSharedNonQueued(this);
    if ( updated < 0 )
      return (unsigned int)updated;
    v4 = this + 30;
    updated = SP_DEVICE::FlushMetadata((SP_DEVICE *)this, 0);
    ExReleaseRundownProtectionCacheAware(this[30]);
    if ( updated >= 0 )
      goto LABEL_11;
    if ( updated != -1058602989 || (updated = SpUpdateColumn((struct SP_DEVICE *)this), updated < 0) )
    {
      v6 = this[17];
      v7 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)v6 + 86);
      *((_BYTE *)v6 + 595) = 1;
      *((_DWORD *)v6 + 143) = updated;
      ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)v6 + 86, v7);
      goto LABEL_11;
    }
    ++v3;
  }
  if ( v3 == 100 )
  {
    updated = -1073741823;
    v4 = v2;
  }
LABEL_11:
  if ( (int)SP_DEVICE::AcquireRundownSharedNonQueued(this) >= 0 )
  {
    SIO_CACHE::GetPendingUnmapRanges(this[17], (struct SDB_RANGES **)&P);
    ExReleaseRundownProtectionCacheAware(*v4);
    v9 = P;
    if ( P )
    {
      LOBYTE(v8) = 11;
      SpUnmapExtents(this, v8, P);
      v10 = this[17];
      v11 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)v10 + 86);
      *((_WORD *)v10 + 256) = 256;
      ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)v10 + 86, v11);
      if ( *((__int64 *)v10 + 63) > 0 )
      {
        SIO_CACHE::LogStatus(v10, 12);
        _InterlockedExchange64((volatile __int64 *)v10 + 63, 0);
      }
      ExFreePoolWithTag(v9, 0);
    }
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x14002b608  mov     [rsp+arg_0], rbx
0x14002b60d  mov     [rsp+arg_10], rbp
0x14002b612  push    rsi
0x14002b613  push    rdi
0x14002b614  push    r14
0x14002b616  sub     rsp, 20h
0x14002b61a  xor     esi, esi
0x14002b61c  mov     [rsp+38h+P], 0
0x14002b625  lea     rdi, [rcx+0F0h]
0x14002b62c  xor     ebx, ebx
0x14002b62e  mov     r14, rdi
0x14002b631  mov     rbp, rcx
0x14002b634  cmp     ebx, 64h ; 'd'
0x14002b637  jnb     loc_14002B6CC
0x14002b63d  mov     rcx, rbp; this
0x14002b640  call    ?AcquireRundownSharedNonQueued@SP_DEVICE@@QEAAJXZ; SP_DEVICE::AcquireRundownSharedNonQueued(void)
0x14002b645  mov     esi, eax
0x14002b647  test    eax, eax
0x14002b649  js      loc_14002B787
0x14002b64f  xor     edx, edx; unsigned __int8
0x14002b651  mov     rcx, rbp; this
0x14002b654  call    ?FlushMetadata@SP_DEVICE@@QEAAJE@Z; SP_DEVICE::FlushMetadata(uchar)
0x14002b659  lea     r14, [rbp+0F0h]
0x14002b660  mov     esi, eax
0x14002b662  mov     rcx, [r14]; RunRefCacheAware
0x14002b665  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x14002b66c  nop     dword ptr [rax+rax+00h]
0x14002b671  test    esi, esi
0x14002b673  jns     short loc_14002B6D6
0x14002b675  cmp     esi, 0C0E70013h
0x14002b67b  jnz     short loc_14002B68F
0x14002b67d  mov     rcx, rbp; this
0x14002b680  call    ?SpUpdateColumn@@YAJPEAVSP_DEVICE@@@Z; SpUpdateColumn(SP_DEVICE *)
0x14002b685  mov     esi, eax
0x14002b687  test    eax, eax
0x14002b689  js      short loc_14002B68F
0x14002b68b  inc     ebx
0x14002b68d  jmp     short loc_14002B634
0x14002b68f  mov     rbx, [rbp+88h]
0x14002b696  lea     rdi, [rbx+158h]
0x14002b69d  mov     rcx, rdi; SpinLock
0x14002b6a0  call    cs:__imp_ExAcquireSpinLockExclusive
0x14002b6a7  nop     dword ptr [rax+rax+00h]
0x14002b6ac  mov     rcx, rdi; SpinLock
0x14002b6af  mov     byte ptr [rbx+253h], 1
0x14002b6b6  mov     dl, al; OldIrql
0x14002b6b8  mov     [rbx+23Ch], esi
0x14002b6be  call    cs:__imp_ExReleaseSpinLockExclusive
0x14002b6c5  nop     dword ptr [rax+rax+00h]
0x14002b6ca  jmp     short loc_14002B6D6
0x14002b6cc  jnz     short loc_14002B6D6
0x14002b6ce  mov     esi, 0C0000001h
0x14002b6d3  mov     r14, rdi
0x14002b6d6  mov     rcx, rbp; this
0x14002b6d9  call    ?AcquireRundownSharedNonQueued@SP_DEVICE@@QEAAJXZ; SP_DEVICE::AcquireRundownSharedNonQueued(void)
0x14002b6de  test    eax, eax
0x14002b6e0  js      loc_14002B787
0x14002b6e6  mov     rcx, [rbp+88h]; this
0x14002b6ed  lea     rdx, [rsp+38h+P]; struct SDB_RANGES **
0x14002b6f2  call    ?GetPendingUnmapRanges@SIO_CACHE@@QEAAJPEAPEAVSDB_RANGES@@@Z; SIO_CACHE::GetPendingUnmapRanges(SDB_RANGES * *)
0x14002b6f7  mov     rcx, [r14]; RunRefCacheAware
0x14002b6fa  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x14002b701  nop     dword ptr [rax+rax+00h]
0x14002b706  mov     r14, [rsp+38h+P]
0x14002b70b  test    r14, r14
0x14002b70e  jz      short loc_14002B787
0x14002b710  mov     r8, r14
0x14002b713  mov     dl, 0Bh
0x14002b715  mov     rcx, rbp
0x14002b718  call    ?SpUnmapExtents@@YAJPEAVSP_DEVICE@@W4_SC_SPACE_USAGE@@PEAVSDB_RANGES@@@Z; SpUnmapExtents(SP_DEVICE *,_SC_SPACE_USAGE,SDB_RANGES *)
0x14002b71d  mov     rdi, [rbp+88h]
0x14002b724  lea     rbx, [rdi+158h]
0x14002b72b  mov     rcx, rbx; SpinLock
0x14002b72e  call    cs:__imp_ExAcquireSpinLockExclusive
0x14002b735  nop     dword ptr [rax+rax+00h]
0x14002b73a  mov     rcx, rbx; SpinLock
0x14002b73d  mov     word ptr [rdi+200h], 100h
0x14002b746  mov     dl, al; OldIrql
0x14002b748  call    cs:__imp_ExReleaseSpinLockExclusive
0x14002b74f  nop     dword ptr [rax+rax+00h]
0x14002b754  cmp     qword ptr [rdi+1F8h], 0
0x14002b75c  jle     short loc_14002B776
0x14002b75e  xor     r8d, r8d
0x14002b761  mov     rcx, rdi
0x14002b764  lea     edx, [r8+0Ch]
0x14002b768  call    ?LogStatus@SIO_CACHE@@IEAAXW4SIO_CACHE_OPERATION@@J@Z; SIO_CACHE::LogStatus(SIO_CACHE_OPERATION,long)
0x14002b76d  xor     eax, eax
0x14002b76f  xchg    rax, [rdi+1F8h]
0x14002b776  xor     edx, edx; Tag
0x14002b778  mov     rcx, r14; P
0x14002b77b  call    cs:__imp_ExFreePoolWithTag
0x14002b782  nop     dword ptr [rax+rax+00h]
0x14002b787  mov     rbx, [rsp+38h+arg_0]
0x14002b78c  mov     eax, esi
0x14002b78e  mov     rbp, [rsp+38h+arg_10]
0x14002b793  add     rsp, 20h
0x14002b797  pop     r14
0x14002b799  pop     rdi
0x14002b79a  pop     rsi
0x14002b79b  retn
```
