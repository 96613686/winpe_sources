# SqosPostReadWrite

- ea: `0x1400011c0`
- end: `0x140001372`
- name: `SqosPostReadWrite`
- size: `434`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1400011c0`
- `0x140001940`
- `0x140001ab0`
- `0x140002490`
- `0x1400025e0`
- `0x140003080`
- `0x140004550`
- `0x140004640`

## import_xrefs

- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140001297`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140001297`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000130e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000130e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400012b9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400012b9`
- `HAL!KeQueryPerformanceCounter` at `0x1400011f3`
- `HAL!KeQueryPerformanceCounter` at `0x1400011f3`
- `FLTMGR!FltReferenceContext` at `0x140001205`
- `FLTMGR!FltReferenceContext` at `0x140001205`

## pseudocode

```c
__int64 __fastcall SqosPostReadWrite(__int64 a1, __int64 a2, __int64 a3, char a4)
{
  __int64 v5; // rax
  __int64 v7; // rdi
  LARGE_INTEGER PerformanceCounter; // rsi
  unsigned int v9; // edi
  union _SLIST_HEADER *v11; // rcx
  _QWORD *i; // r15
  _QWORD *v13; // rbp
  __int64 ***v14; // rcx
  __int64 *v15; // [rsp+20h] [rbp-68h] BYREF
  __int64 ***v16; // [rsp+28h] [rbp-60h]
  _QWORD v17[3]; // [rsp+30h] [rbp-58h] BYREF
  __int16 v18; // [rsp+48h] [rbp-40h]
  char v19; // [rsp+4Ah] [rbp-3Eh]
  int v20; // [rsp+4Bh] [rbp-3Dh]
  char v21; // [rsp+4Fh] [rbp-39h]

  *(_QWORD *)a3 = a1;
  *(_QWORD *)(a1 + 64) = a3;
  v5 = *(_QWORD *)(a3 + 32);
  v20 = 0;
  v21 = 0;
  v7 = *(_QWORD *)(v5 + 8);
  PerformanceCounter = KeQueryPerformanceCounter(0);
  FltReferenceContext((PFLT_CONTEXT)v7);
  v17[0] = v7;
  v17[1] = &Object;
  v18 = 0;
  v19 = 0;
  v17[2] = 0;
  *(LARGE_INTEGER *)(a3 + 176) = PerformanceCounter;
  if ( *(_BYTE *)(a3 + 129) )
  {
    if ( (a4 & 1) != 0 )
    {
      *(_BYTE *)(v7 + 840) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v7 + 832));
    }
    else if ( !(unsigned __int8)SqospTryAcquireDeviceLock(v7) )
    {
      v11 = (union _SLIST_HEADER *)(*(_QWORD *)(*(_QWORD *)(a3 + 32) + 8LL) + 272LL);
      *(_BYTE *)(a3 + 125) = 1;
      ExpInterlockedPushEntrySList(v11, (PSLIST_ENTRY)(a3 + 64));
      SqospQueueDeviceTimer((PFLT_CONTEXT)v7);
      v9 = 1;
      goto LABEL_3;
    }
    v16 = (__int64 ***)&v15;
    v15 = (__int64 *)&v15;
    for ( i = (_QWORD *)SqospFlushDeferredJobList(v7 + 272); i; v16 = (__int64 ***)(v13 + 12) )
    {
      v13 = i - 8;
      i = (_QWORD *)*i;
      BalanceCompleteJob(v13, v17);
      v14 = v16;
      if ( *v16 != &v15 )
        __fastfail(3u);
      v13[13] = v16;
      v13[12] = &v15;
      *v14 = (__int64 **)(v13 + 12);
    }
    BalanceCompleteJob(a3, v17);
    KeReleaseSpinLock((PKSPIN_LOCK)(v7 + 832), *(_BYTE *)(v7 + 840));
    SqospCompleteJobsOutsideLock(&v15);
  }
  v9 = 0;
  SqospDestroyJob((_BYTE *)a3);
LABEL_3:
  ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))SqospProcessJobDispatcherContext)(
    v17,
    0,
    (LARGE_INTEGER)PerformanceCounter.QuadPart);
  return v9;
}

```

## disassembly

```asm
0x1400011c0  push    rbx
0x1400011c2  push    rbp
0x1400011c3  push    rsi
0x1400011c4  push    rdi
0x1400011c5  push    r12
0x1400011c7  push    r14
0x1400011c9  push    r15
0x1400011cb  sub     rsp, 50h
0x1400011cf  mov     [r8], rcx
0x1400011d2  mov     rbx, r8
0x1400011d5  mov     [rcx+40h], rbx
0x1400011d9  xor     r12d, r12d
0x1400011dc  mov     rax, [r8+20h]
0x1400011e0  xor     ecx, ecx; PerformanceFrequency
0x1400011e2  mov     ebp, r9d
0x1400011e5  mov     [rsp+88h+var_3D], r12d
0x1400011ea  mov     [rsp+88h+var_39], r12b
0x1400011ef  mov     rdi, [rax+8]
0x1400011f3  call    cs:__imp_KeQueryPerformanceCounter
0x1400011fa  nop     dword ptr [rax+rax+00h]
0x1400011ff  mov     rcx, rdi; Context
0x140001202  mov     rsi, rax
0x140001205  call    cs:__imp_FltReferenceContext
0x14000120c  nop     dword ptr [rax+rax+00h]
0x140001211  lea     rax, Object
0x140001218  mov     [rsp+88h+var_58], rdi
0x14000121d  mov     [rsp+88h+var_50], rax
0x140001222  mov     [rsp+88h+var_40], r12w
0x140001228  mov     [rsp+88h+var_3E], r12b
0x14000122d  mov     [rsp+88h+var_48], r12
0x140001232  mov     [rbx+0B0h], rsi
0x140001239  cmp     [rbx+81h], r12b
0x140001240  jnz     short loc_14000126E
0x140001242  mov     rcx, rbx; Entry
0x140001245  mov     edi, r12d
0x140001248  call    SqospDestroyJob
0x14000124d  mov     r8, rsi
0x140001250  lea     rcx, [rsp+88h+var_58]
0x140001255  xor     edx, edx
0x140001257  call    SqospProcessJobDispatcherContext
0x14000125c  mov     eax, edi
0x14000125e  add     rsp, 50h
0x140001262  pop     r15
0x140001264  pop     r14
0x140001266  pop     r12
0x140001268  pop     rdi
0x140001269  pop     rsi
0x14000126a  pop     rbp
0x14000126b  pop     rbx
0x14000126c  retn
0x14000126e  test    bpl, 1
0x140001272  jnz     short loc_1400012B2
0x140001274  mov     rcx, rdi
0x140001277  call    SqospTryAcquireDeviceLock
0x14000127c  test    al, al
0x14000127e  jnz     short loc_1400012CB
0x140001280  mov     rax, [rbx+20h]
0x140001284  lea     rdx, [rbx+40h]; ListEntry
0x140001288  mov     rcx, [rax+8]
0x14000128c  add     rcx, 110h; ListHead
0x140001293  mov     byte ptr [rbx+7Dh], 1
0x140001297  call    cs:__imp_ExpInterlockedPushEntrySList
0x14000129e  nop     dword ptr [rax+rax+00h]
0x1400012a3  mov     rcx, rdi; Context
0x1400012a6  call    SqospQueueDeviceTimer
0x1400012ab  mov     edi, 1
0x1400012b0  jmp     short loc_14000124D
0x1400012b2  lea     rcx, [rdi+340h]; SpinLock
0x1400012b9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400012c0  nop     dword ptr [rax+rax+00h]
0x1400012c5  mov     [rdi+348h], al
0x1400012cb  lea     rax, [rsp+88h+var_68]
0x1400012d0  mov     [rsp+88h+var_60], rax
0x1400012d5  lea     rcx, [rdi+110h]
0x1400012dc  lea     rax, [rsp+88h+var_68]
0x1400012e1  mov     [rsp+88h+var_68], rax
0x1400012e6  call    SqospFlushDeferredJobList
0x1400012eb  mov     r15, rax
0x1400012ee  test    rax, rax
0x1400012f1  jnz     short loc_140001329
0x1400012f3  lea     rdx, [rsp+88h+var_58]
0x1400012f8  mov     rcx, rbx
0x1400012fb  call    BalanceCompleteJob
0x140001300  movzx   edx, byte ptr [rdi+348h]; NewIrql
0x140001307  lea     rcx, [rdi+340h]; SpinLock
0x14000130e  call    cs:__imp_KeReleaseSpinLock
0x140001315  nop     dword ptr [rax+rax+00h]
0x14000131a  lea     rcx, [rsp+88h+var_68]
0x14000131f  call    SqospCompleteJobsOutsideLock
0x140001324  jmp     loc_140001242
0x140001329  lea     rbp, [r15-40h]
0x14000132d  mov     r15, [r15]
0x140001330  mov     rcx, rbp
0x140001333  lea     rdx, [rsp+88h+var_58]
0x140001338  call    BalanceCompleteJob
0x14000133d  mov     rcx, [rsp+88h+var_60]
0x140001342  lea     rax, [rsp+88h+var_68]
0x140001347  cmp     [rcx], rax
0x14000134a  jz      short loc_140001353
0x14000134c  mov     ecx, 3
0x140001351  int     29h; Win8: RtlFailFast(ecx)
0x140001353  mov     [rbp+68h], rcx
0x140001357  lea     rax, [rbp+60h]
0x14000135b  lea     rdx, [rsp+88h+var_68]
0x140001360  mov     [rax], rdx
0x140001363  mov     [rcx], rax
0x140001366  mov     [rsp+88h+var_60], rax
0x14000136b  test    r15, r15
0x14000136e  jnz     short loc_140001329
0x140001370  jmp     short loc_1400012F3
```
