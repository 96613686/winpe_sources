# CheckIndicateDisconnect

- ea: `0x14000cf04`
- end: `0x14000d208`
- name: `CheckIndicateDisconnect`
- size: `772`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14000d210`
- `0x1400120b4`
- `0x140012efc`
- `0x140013930`

## callees

- `0x1400074c8`
- `0x140007f1c`
- `0x14000cdfc`
- `0x14000cf04`
- `0x14000dd10`
- `0x140014240`
- `0x140015b78`
- `0x14001c9f4`
- `0x14001ce30`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000d05a`
- `ntoskrnl!IofCompleteRequest` at `0x14000d05a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000cfe2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d00a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d188`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d1a4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000cfe2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d00a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d188`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d1a4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d141`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d153`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d1ca`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d1dc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d141`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d153`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d1ca`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d1dc`

## pseudocode

```c
bool __fastcall CheckIndicateDisconnect(__int64 a1, __int64 a2, KIRQL *a3, KIRQL *a4, char a5)
{
  int v7; // edx
  bool v9; // bl
  __int64 v10; // rcx
  __int64 v11; // r8
  int v12; // esi
  int v13; // ebp
  _QWORD *v14; // rbx
  __int64 v15; // rdx
  _QWORD *v16; // rax
  const char *v17; // rdx
  __int64 v18; // r9
  KSPIN_LOCK *v19; // rsi
  IRP *v20; // rbp
  __int128 v22; // [rsp+40h] [rbp-38h] BYREF

  v7 = *(_DWORD *)(a2 + 32);
  v9 = (v7 & 0x2000) != 0;
  v22 = 0;
  if ( (v7 & 0x2400) == 0 )
  {
    v10 = *(_QWORD *)(a2 + 48);
    v11 = *(_QWORD *)(v10 + 136);
    v12 = v11 == v10 + 136 ? *(_DWORD *)(v10 + 56) : *(_DWORD *)(v11 + 16) + *(unsigned __int8 *)(v11 + 63);
    v13 = v7 & 0x100;
    if ( (v7 & 0x100) != 0
      || (v7 & 0x80u) != 0 && *(_QWORD *)(v10 + 120) == v10 + 120 && v12 - *(_DWORD *)(v10 + 68) - 1 >= 0 )
    {
      *(_DWORD *)(a2 + 32) = v7 | 0x2400;
      *((_QWORD *)&v22 + 1) = &v22;
      *(_QWORD *)&v22 = &v22;
      RemovePendingIrps(a2, &v22);
      ++*(_DWORD *)(a2 + 20);
      KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 360), *a4);
      if ( a5 )
        KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 424), *a3);
      while ( 1 )
      {
        v14 = (_QWORD *)v22;
        if ( (__int128 *)v22 == &v22 )
          break;
        PgmCancelCancelRoutine(v22 - 168);
        v15 = *v14;
        if ( *(_QWORD **)(*v14 + 8LL) != v14 || (v16 = (_QWORD *)v14[1], (_QWORD *)*v16 != v14) )
          __fastfail(3u);
        *v16 = v15;
        *(_QWORD *)(v15 + 8) = v16;
        *((_DWORD *)v14 - 30) = -1073741536;
        IofCompleteRequest((PIRP)(v14 - 21), 2);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      {
        v17 = "TDI_DISCONNECT_RELEASE";
        if ( v13 )
          v17 = "TDI_DISCONNECT_ABORT";
        WPP_SF_qqsdd(
          WPP_GLOBAL_Control->AttachedDevice,
          (_DWORD)v17,
          (unsigned int)"TDI_DISCONNECT_ABORT",
          a2,
          *(_QWORD *)(a2 + 80),
          (__int64)v17,
          v12,
          *(_DWORD *)(*(_QWORD *)(a2 + 48) + 52LL));
      }
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, int))(a1 + 144))(
        *(_QWORD *)(a1 + 152),
        *(_QWORD *)(a2 + 80),
        0,
        0,
        0,
        0,
        v13 != 0 ? 2 : 4);
      v9 = 1;
      if ( (unsigned int)PgmQueueForDelayedExecution(
                           (WORKER_THREAD_ROUTINE *)CleanupPendingNaks,
                           (void *)a2,
                           (struct _LIST_ENTRY *)1,
                           v18,
                           0) )
        CleanupPendingNaks(a2, 1, 0);
      v19 = (KSPIN_LOCK *)(a1 + 424);
      if ( a5 )
        *a3 = KeAcquireSpinLockRaiseToDpc(v19);
      *a4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 360));
      *(_DWORD *)(a2 + 32) &= ~0x400u;
      CheckDeferredCleanup(a2);
      v20 = *(IRP **)(a2 + 104);
      if ( v20 )
      {
        *(_QWORD *)(a2 + 104) = 0;
        KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 360), *a4);
        if ( a5 )
          KeReleaseSpinLock(v19, *a3);
        PgmIoComplete(v20, 0, 0);
        if ( a5 )
          *a3 = KeAcquireSpinLockRaiseToDpc(v19);
        *a4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 360));
      }
    }
  }
  return v9;
}

```

## disassembly

```asm
0x14000cf04  mov     rax, rsp
0x14000cf07  mov     [rax+18h], rbx
0x14000cf0b  mov     [rax+20h], rbp
0x14000cf0f  mov     [rax+8], rcx
0x14000cf13  push    rsi
0x14000cf14  push    rdi
0x14000cf15  push    r12
0x14000cf17  push    r13
0x14000cf19  push    r14
0x14000cf1b  sub     rsp, 50h
0x14000cf1f  mov     rdi, rdx
0x14000cf22  mov     r13, r9
0x14000cf25  mov     edx, [rdx+20h]
0x14000cf28  mov     r9d, 2400h
0x14000cf2e  mov     ebx, edx
0x14000cf30  xorps   xmm0, xmm0
0x14000cf33  shr     ebx, 0Dh
0x14000cf36  mov     r14, r8
0x14000cf39  and     bl, 1
0x14000cf3c  movups  xmmword ptr [rax-38h], xmm0
0x14000cf40  test    r9d, edx
0x14000cf43  jnz     loc_14000D1EC
0x14000cf49  mov     rcx, [rdi+30h]
0x14000cf4d  lea     rax, [rcx+88h]
0x14000cf54  mov     r8, [rax]
0x14000cf57  cmp     r8, rax
0x14000cf5a  jnz     short loc_14000CF61
0x14000cf5c  mov     esi, [rcx+38h]
0x14000cf5f  jmp     short loc_14000CF6A
0x14000cf61  movzx   esi, byte ptr [r8+3Fh]
0x14000cf66  add     esi, [r8+10h]
0x14000cf6a  mov     ebp, edx
0x14000cf6c  and     ebp, 100h
0x14000cf72  jnz     short loc_14000CF97
0x14000cf74  test    dl, dl
0x14000cf76  jns     loc_14000D1EC
0x14000cf7c  lea     rax, [rcx+78h]
0x14000cf80  cmp     [rax], rax
0x14000cf83  jnz     loc_14000D1EC
0x14000cf89  mov     eax, esi
0x14000cf8b  sub     eax, [rcx+44h]
0x14000cf8e  cmp     eax, 1
0x14000cf91  js      loc_14000D1EC
0x14000cf97  mov     eax, ebp
0x14000cf99  mov     rcx, rdi
0x14000cf9c  neg     eax
0x14000cf9e  sbb     eax, eax
0x14000cfa0  or      edx, r9d
0x14000cfa3  and     eax, 0FFFFFFFEh
0x14000cfa6  mov     [rdi+20h], edx
0x14000cfa9  add     eax, 4
0x14000cfac  lea     rdx, [rsp+78h+var_38]
0x14000cfb1  mov     [rsp+78h+arg_8], eax
0x14000cfb8  lea     rax, [rsp+78h+var_38]
0x14000cfbd  mov     [rsp+78h+var_30], rax
0x14000cfc2  lea     rax, [rsp+78h+var_38]
0x14000cfc7  mov     [rsp+78h+var_38], rax
0x14000cfcc  call    RemovePendingIrps
0x14000cfd1  inc     dword ptr [rdi+14h]
0x14000cfd4  lea     r12, [rdi+168h]
0x14000cfdb  mov     dl, [r13+0]; NewIrql
0x14000cfdf  mov     rcx, r12; SpinLock
0x14000cfe2  call    cs:__imp_KeReleaseSpinLock
0x14000cfe9  nop     dword ptr [rax+rax+00h]
0x14000cfee  cmp     [rsp+78h+arg_20], 0
0x14000cff6  jz      short loc_14000D016
0x14000cff8  mov     rcx, [rsp+78h+arg_0]
0x14000d000  mov     dl, [r14]; NewIrql
0x14000d003  add     rcx, 1A8h; SpinLock
0x14000d00a  call    cs:__imp_KeReleaseSpinLock
0x14000d011  nop     dword ptr [rax+rax+00h]
0x14000d016  mov     rbx, [rsp+78h+var_38]
0x14000d01b  lea     rax, [rsp+78h+var_38]
0x14000d020  cmp     rbx, rax
0x14000d023  jz      short loc_14000D06F
0x14000d025  lea     rcx, [rbx-0A8h]
0x14000d02c  call    PgmCancelCancelRoutine
0x14000d031  mov     rdx, [rbx]
0x14000d034  cmp     [rdx+8], rbx
0x14000d038  jnz     short loc_14000D068
0x14000d03a  mov     rax, [rbx+8]
0x14000d03e  cmp     [rax], rbx
0x14000d041  jnz     short loc_14000D068
0x14000d043  mov     [rax], rdx
0x14000d046  lea     rcx, [rbx-0A8h]; Irp
0x14000d04d  mov     [rdx+8], rax
0x14000d051  mov     dl, 2; PriorityBoost
0x14000d053  mov     dword ptr [rbx-78h], 0C0000120h
0x14000d05a  call    cs:__imp_IofCompleteRequest
0x14000d061  nop     dword ptr [rax+rax+00h]
0x14000d066  jmp     short loc_14000D016
0x14000d068  mov     ecx, 3
0x14000d06d  int     29h; Win8: RtlFailFast(ecx)
0x14000d06f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d076  lea     rax, WPP_GLOBAL_Control
0x14000d07d  cmp     rcx, rax
0x14000d080  jz      short loc_14000D0C6
0x14000d082  mov     eax, [rcx+2Ch]
0x14000d085  test    al, 4
0x14000d087  jz      short loc_14000D0C6
0x14000d089  mov     rax, [rdi+30h]
0x14000d08d  lea     r8, aTdiDisconnectA; "TDI_DISCONNECT_ABORT"
0x14000d094  mov     rcx, [rcx+18h]
0x14000d098  lea     rdx, aTdiDisconnectR; "TDI_DISCONNECT_RELEASE"
0x14000d09f  test    ebp, ebp
0x14000d0a1  mov     r9, rdi
0x14000d0a4  mov     eax, [rax+34h]
0x14000d0a7  cmovnz  rdx, r8
0x14000d0ab  mov     [rsp+78h+var_40], eax
0x14000d0af  mov     rax, [rdi+50h]
0x14000d0b3  mov     [rsp+78h+var_48], esi
0x14000d0b7  mov     [rsp+78h+var_50], rdx
0x14000d0bc  mov     [rsp+78h+var_58], rax
0x14000d0c1  call    WPP_SF_qqsdd
0x14000d0c6  mov     rsi, [rsp+78h+arg_0]
0x14000d0ce  xor     ebp, ebp
0x14000d0d0  mov     ecx, [rsp+78h+arg_8]
0x14000d0d7  xor     r9d, r9d
0x14000d0da  mov     rdx, [rdi+50h]
0x14000d0de  xor     r8d, r8d
0x14000d0e1  mov     [rsp+78h+var_48], ecx
0x14000d0e5  mov     rax, [rsi+90h]
0x14000d0ec  mov     rcx, [rsi+98h]
0x14000d0f3  mov     [rsp+78h+var_50], rbp
0x14000d0f8  mov     dword ptr [rsp+78h+var_58], ebp
0x14000d0fc  call    _guard_dispatch_icall
0x14000d101  lea     r8d, [rbp+1]
0x14000d105  mov     byte ptr [rsp+78h+var_58], bpl
0x14000d10a  mov     rdx, rdi
0x14000d10d  lea     rcx, CleanupPendingNaks
0x14000d114  mov     bl, 1
0x14000d116  call    PgmQueueForDelayedExecution
0x14000d11b  test    eax, eax
0x14000d11d  jz      short loc_14000D12D
0x14000d11f  xor     r8d, r8d
0x14000d122  lea     edx, [rbp+1]
0x14000d125  mov     rcx, rdi
0x14000d128  call    CleanupPendingNaks
0x14000d12d  add     rsi, 1A8h
0x14000d134  cmp     [rsp+78h+arg_20], bpl
0x14000d13c  jz      short loc_14000D150
0x14000d13e  mov     rcx, rsi; SpinLock
0x14000d141  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000d148  nop     dword ptr [rax+rax+00h]
0x14000d14d  mov     [r14], al
0x14000d150  mov     rcx, r12; SpinLock
0x14000d153  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000d15a  nop     dword ptr [rax+rax+00h]
0x14000d15f  mov     [r13+0], al
0x14000d163  mov     rcx, rdi
0x14000d166  btr     dword ptr [rdi+20h], 0Ah
0x14000d16b  call    CheckDeferredCleanup
0x14000d170  mov     rbp, [rdi+68h]
0x14000d174  test    rbp, rbp
0x14000d177  jz      short loc_14000D1EC
0x14000d179  mov     qword ptr [rdi+68h], 0
0x14000d181  mov     rcx, r12; SpinLock
0x14000d184  mov     dl, [r13+0]; NewIrql
0x14000d188  call    cs:__imp_KeReleaseSpinLock
0x14000d18f  nop     dword ptr [rax+rax+00h]
0x14000d194  cmp     [rsp+78h+arg_20], 0
0x14000d19c  jz      short loc_14000D1B0
0x14000d19e  mov     dl, [r14]; NewIrql
0x14000d1a1  mov     rcx, rsi; SpinLock
0x14000d1a4  call    cs:__imp_KeReleaseSpinLock
0x14000d1ab  nop     dword ptr [rax+rax+00h]
0x14000d1b0  xor     r8d, r8d
0x14000d1b3  xor     edx, edx
0x14000d1b5  mov     rcx, rbp; Irp
0x14000d1b8  call    PgmIoComplete
0x14000d1bd  cmp     [rsp+78h+arg_20], 0
0x14000d1c5  jz      short loc_14000D1D9
0x14000d1c7  mov     rcx, rsi; SpinLock
0x14000d1ca  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000d1d1  nop     dword ptr [rax+rax+00h]
0x14000d1d6  mov     [r14], al
0x14000d1d9  mov     rcx, r12; SpinLock
0x14000d1dc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000d1e3  nop     dword ptr [rax+rax+00h]
0x14000d1e8  mov     [r13+0], al
0x14000d1ec  lea     r11, [rsp+78h+var_28]
0x14000d1f1  mov     al, bl
0x14000d1f3  mov     rbx, [r11+40h]
0x14000d1f7  mov     rbp, [r11+48h]
0x14000d1fb  mov     rsp, r11
0x14000d1fe  pop     r14
0x14000d200  pop     r13
0x14000d202  pop     r12
0x14000d204  pop     rdi
0x14000d205  pop     rsi
0x14000d206  retn
```
