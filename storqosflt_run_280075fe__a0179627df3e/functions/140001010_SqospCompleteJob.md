# SqospCompleteJob

- ea: `0x140001010`
- end: `0x1400011ba`
- name: `SqospCompleteJob`
- size: `426`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400081a0`

## callees

- `0x140001010`
- `0x140001940`
- `0x140001ab0`
- `0x140002490`
- `0x1400025e0`
- `0x140003080`
- `0x140004550`
- `0x140004640`

## import_xrefs

- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400010df`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400010df`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001156`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001156`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001101`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001101`
- `HAL!KeQueryPerformanceCounter` at `0x14000103c`
- `HAL!KeQueryPerformanceCounter` at `0x14000103c`
- `FLTMGR!FltReferenceContext` at `0x14000104e`
- `FLTMGR!FltReferenceContext` at `0x14000104e`

## pseudocode

```c
__int64 __fastcall SqospCompleteJob(_BYTE *Entry, char a2)
{
  __int64 v2; // rax
  __int64 v5; // rdi
  LARGE_INTEGER PerformanceCounter; // rsi
  unsigned int v7; // edi
  union _SLIST_HEADER *v9; // rcx
  _QWORD *i; // r15
  _QWORD *v11; // rbp
  __int64 ***v12; // rcx
  __int64 *v13; // [rsp+20h] [rbp-68h] BYREF
  __int64 ***v14; // [rsp+28h] [rbp-60h]
  _QWORD v15[3]; // [rsp+30h] [rbp-58h] BYREF
  __int16 v16; // [rsp+48h] [rbp-40h]
  char v17; // [rsp+4Ah] [rbp-3Eh]
  int v18; // [rsp+4Bh] [rbp-3Dh]
  char v19; // [rsp+4Fh] [rbp-39h]

  v2 = *((_QWORD *)Entry + 4);
  v18 = 0;
  v19 = 0;
  v5 = *(_QWORD *)(v2 + 8);
  PerformanceCounter = KeQueryPerformanceCounter(0);
  FltReferenceContext((PFLT_CONTEXT)v5);
  v15[0] = v5;
  v15[1] = &Object;
  v16 = 0;
  v17 = 0;
  v15[2] = 0;
  *((LARGE_INTEGER *)Entry + 22) = PerformanceCounter;
  if ( Entry[129] )
  {
    if ( a2 )
    {
      *(_BYTE *)(v5 + 840) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + 832));
    }
    else if ( !(unsigned __int8)SqospTryAcquireDeviceLock(v5) )
    {
      v9 = (union _SLIST_HEADER *)(*(_QWORD *)(*((_QWORD *)Entry + 4) + 8LL) + 272LL);
      Entry[125] = 1;
      ExpInterlockedPushEntrySList(v9, (PSLIST_ENTRY)Entry + 4);
      SqospQueueDeviceTimer((PFLT_CONTEXT)v5);
      v7 = 1;
      goto LABEL_3;
    }
    v14 = (__int64 ***)&v13;
    v13 = (__int64 *)&v13;
    for ( i = (_QWORD *)SqospFlushDeferredJobList(v5 + 272); i; v14 = (__int64 ***)(v11 + 12) )
    {
      v11 = i - 8;
      i = (_QWORD *)*i;
      BalanceCompleteJob(v11, v15);
      v12 = v14;
      if ( *v14 != &v13 )
        __fastfail(3u);
      v11[13] = v14;
      v11[12] = &v13;
      *v12 = (__int64 **)(v11 + 12);
    }
    BalanceCompleteJob(Entry, v15);
    KeReleaseSpinLock((PKSPIN_LOCK)(v5 + 832), *(_BYTE *)(v5 + 840));
    SqospCompleteJobsOutsideLock(&v13);
  }
  v7 = 0;
  SqospDestroyJob(Entry);
LABEL_3:
  ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))SqospProcessJobDispatcherContext)(
    v15,
    0,
    (LARGE_INTEGER)PerformanceCounter.QuadPart);
  return v7;
}

```

## disassembly

```asm
0x140001010  push    rbx
0x140001012  push    rbp
0x140001013  push    rsi
0x140001014  push    rdi
0x140001015  push    r12
0x140001017  push    r14
0x140001019  push    r15
0x14000101b  sub     rsp, 50h
0x14000101f  mov     rax, [rcx+20h]
0x140001023  mov     rbx, rcx
0x140001026  xor     r12d, r12d
0x140001029  xor     ecx, ecx; PerformanceFrequency
0x14000102b  movzx   ebp, dl
0x14000102e  mov     [rsp+88h+var_3D], r12d
0x140001033  mov     [rsp+88h+var_39], r12b
0x140001038  mov     rdi, [rax+8]
0x14000103c  call    cs:__imp_KeQueryPerformanceCounter
0x140001043  nop     dword ptr [rax+rax+00h]
0x140001048  mov     rcx, rdi; Context
0x14000104b  mov     rsi, rax
0x14000104e  call    cs:__imp_FltReferenceContext
0x140001055  nop     dword ptr [rax+rax+00h]
0x14000105a  lea     rax, Object
0x140001061  mov     [rsp+88h+var_58], rdi
0x140001066  mov     [rsp+88h+var_50], rax
0x14000106b  mov     [rsp+88h+var_40], r12w
0x140001071  mov     [rsp+88h+var_3E], r12b
0x140001076  mov     [rsp+88h+var_48], r12
0x14000107b  mov     [rbx+0B0h], rsi
0x140001082  cmp     [rbx+81h], r12b
0x140001089  jnz     short loc_1400010B7
0x14000108b  mov     rcx, rbx; Entry
0x14000108e  mov     edi, r12d
0x140001091  call    SqospDestroyJob
0x140001096  mov     r8, rsi
0x140001099  lea     rcx, [rsp+88h+var_58]
0x14000109e  xor     edx, edx
0x1400010a0  call    SqospProcessJobDispatcherContext
0x1400010a5  mov     eax, edi
0x1400010a7  add     rsp, 50h
0x1400010ab  pop     r15
0x1400010ad  pop     r14
0x1400010af  pop     r12
0x1400010b1  pop     rdi
0x1400010b2  pop     rsi
0x1400010b3  pop     rbp
0x1400010b4  pop     rbx
0x1400010b5  retn
0x1400010b7  test    bpl, bpl
0x1400010ba  jnz     short loc_1400010FA
0x1400010bc  mov     rcx, rdi
0x1400010bf  call    SqospTryAcquireDeviceLock
0x1400010c4  test    al, al
0x1400010c6  jnz     short loc_140001113
0x1400010c8  mov     rax, [rbx+20h]
0x1400010cc  lea     rdx, [rbx+40h]; ListEntry
0x1400010d0  mov     rcx, [rax+8]
0x1400010d4  add     rcx, 110h; ListHead
0x1400010db  mov     byte ptr [rbx+7Dh], 1
0x1400010df  call    cs:__imp_ExpInterlockedPushEntrySList
0x1400010e6  nop     dword ptr [rax+rax+00h]
0x1400010eb  mov     rcx, rdi; Context
0x1400010ee  call    SqospQueueDeviceTimer
0x1400010f3  mov     edi, 1
0x1400010f8  jmp     short loc_140001096
0x1400010fa  lea     rcx, [rdi+340h]; SpinLock
0x140001101  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001108  nop     dword ptr [rax+rax+00h]
0x14000110d  mov     [rdi+348h], al
0x140001113  lea     rax, [rsp+88h+var_68]
0x140001118  mov     [rsp+88h+var_60], rax
0x14000111d  lea     rcx, [rdi+110h]
0x140001124  lea     rax, [rsp+88h+var_68]
0x140001129  mov     [rsp+88h+var_68], rax
0x14000112e  call    SqospFlushDeferredJobList
0x140001133  mov     r15, rax
0x140001136  test    rax, rax
0x140001139  jnz     short loc_140001171
0x14000113b  lea     rdx, [rsp+88h+var_58]
0x140001140  mov     rcx, rbx
0x140001143  call    BalanceCompleteJob
0x140001148  movzx   edx, byte ptr [rdi+348h]; NewIrql
0x14000114f  lea     rcx, [rdi+340h]; SpinLock
0x140001156  call    cs:__imp_KeReleaseSpinLock
0x14000115d  nop     dword ptr [rax+rax+00h]
0x140001162  lea     rcx, [rsp+88h+var_68]
0x140001167  call    SqospCompleteJobsOutsideLock
0x14000116c  jmp     loc_14000108B
0x140001171  lea     rbp, [r15-40h]
0x140001175  mov     r15, [r15]
0x140001178  mov     rcx, rbp
0x14000117b  lea     rdx, [rsp+88h+var_58]
0x140001180  call    BalanceCompleteJob
0x140001185  mov     rcx, [rsp+88h+var_60]
0x14000118a  lea     rax, [rsp+88h+var_68]
0x14000118f  cmp     [rcx], rax
0x140001192  jz      short loc_14000119B
0x140001194  mov     ecx, 3
0x140001199  int     29h; Win8: RtlFailFast(ecx)
0x14000119b  mov     [rbp+68h], rcx
0x14000119f  lea     rax, [rbp+60h]
0x1400011a3  lea     rdx, [rsp+88h+var_68]
0x1400011a8  mov     [rax], rdx
0x1400011ab  mov     [rcx], rax
0x1400011ae  mov     [rsp+88h+var_60], rax
0x1400011b3  test    r15, r15
0x1400011b6  jnz     short loc_140001171
0x1400011b8  jmp     short loc_14000113B
```
