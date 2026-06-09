# VmbChannelCleanup

- ea: `0x1400069c0`
- end: `0x140006c5d`
- name: `VmbChannelCleanup`
- size: `669`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x140007068`

## callees

- `0x1400069c0`
- `0x140006dc8`
- `0x140006e00`
- `0x140006f10`
- `0x140009604`
- `0x14000a030`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400069f9`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140006a6d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400069f9`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140006a6d`
- `ntoskrnl!ExReleaseFastMutex` at `0x140006b2a`
- `ntoskrnl!ExReleaseFastMutex` at `0x140006b2a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140006a57`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140006a57`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140006b6d`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140006b6d`
- `ntoskrnl!ObfDereferenceObject` at `0x140006bf5`
- `ntoskrnl!ObfDereferenceObject` at `0x140006c14`
- `ntoskrnl!ObfDereferenceObject` at `0x140006bf5`
- `ntoskrnl!ObfDereferenceObject` at `0x140006c14`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140006ad7`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140006ad7`
- `ntoskrnl!KeSetEvent` at `0x140006bb6`
- `ntoskrnl!KeSetEvent` at `0x140006bb6`
- `ntoskrnl!ExAcquireFastMutex` at `0x140006aea`
- `ntoskrnl!ExAcquireFastMutex` at `0x140006aea`
- `ntoskrnl!IoFreeWorkItem` at `0x140006b42`
- `ntoskrnl!IoFreeWorkItem` at `0x140006b42`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006c40`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006c40`
- `ntoskrnl!KeWaitForSingleObject` at `0x140006bd6`
- `ntoskrnl!KeWaitForSingleObject` at `0x140006bd6`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140006a30`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140006aaf`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140006a30`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140006aaf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140006abb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140006abb`

## pseudocode

```c
void __fastcall VmbChannelCleanup(ULONG_PTR BugCheckParameter2)
{
  __int64 v2; // rdi
  __int64 v3; // r8
  _QWORD *v4; // rdx
  _QWORD **v5; // rdi
  _QWORD *v6; // rax
  _QWORD *v7; // rcx
  ULONG_PTR v8; // rcx
  __int64 v9; // rax
  _QWORD *v10; // rdx
  struct _IO_WORKITEM *v11; // rcx
  void *v12; // rcx
  void *v13; // rcx

  if ( *(_DWORD *)(BugCheckParameter2 + 2200) == 12 )
    return;
  v2 = *(_QWORD *)(BugCheckParameter2 + 3160);
  if ( v2 )
  {
    KmclLockChannel(*(_QWORD *)(BugCheckParameter2 + 3160));
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v2 + 3176));
    v3 = *(_QWORD *)(BugCheckParameter2 + 3248);
    if ( *(_QWORD *)(v3 + 8) != BugCheckParameter2 + 3248 )
      goto LABEL_35;
    v4 = *(_QWORD **)(BugCheckParameter2 + 3256);
    if ( *v4 != BugCheckParameter2 + 3248 )
      goto LABEL_35;
    *v4 = v3;
    *(_QWORD *)(v3 + 8) = v4;
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v2 + 3176));
    KmclUnlockChannel(v2);
    *(_QWORD *)(BugCheckParameter2 + 3160) = 0;
  }
  v5 = (_QWORD **)(BugCheckParameter2 + 3232);
  if ( *v5 != v5 )
  {
    KeEnterCriticalRegion();
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(BugCheckParameter2 + 3176));
    while ( 1 )
    {
      v6 = *v5;
      if ( *v5 == v5 )
        break;
      if ( (_QWORD **)v6[1] != v5 )
        goto LABEL_35;
      v7 = (_QWORD *)*v6;
      if ( *(_QWORD **)(*v6 + 8LL) != v6 )
        goto LABEL_35;
      *v5 = v7;
      v7[1] = v5;
      v6[1] = v6;
      *v6 = v6;
      *(v6 - 11) = 0;
    }
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(BugCheckParameter2 + 3176));
    KeLeaveCriticalRegion();
  }
  if ( *(_QWORD *)(BugCheckParameter2 + 2192) )
    RtlFreeUnicodeString((PUNICODE_STRING)(BugCheckParameter2 + 2184));
  ExAcquireFastMutex(&KmclChannelListLock);
  v8 = BugCheckParameter2 + 2144;
  v9 = *(_QWORD *)(BugCheckParameter2 + 2144);
  if ( !v9 )
    goto LABEL_19;
  if ( *(_QWORD *)(v9 + 8) != v8 || (v10 = *(_QWORD **)(BugCheckParameter2 + 2152), *v10 != v8) )
LABEL_35:
    __fastfail(3u);
  *v10 = v9;
  *(_QWORD *)(v9 + 8) = v10;
LABEL_19:
  ExReleaseFastMutex(&KmclChannelListLock);
  v11 = *(struct _IO_WORKITEM **)(BugCheckParameter2 + 2936);
  if ( v11 )
  {
    IoFreeWorkItem(v11);
    *(_QWORD *)(BugCheckParameter2 + 2936) = 0;
  }
  KmclpFreeAllBounceBlocks(BugCheckParameter2);
  if ( *(_BYTE *)(BugCheckParameter2 + 3072) )
  {
    ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(BugCheckParameter2 + 2944));
    *(_BYTE *)(BugCheckParameter2 + 3072) = 0;
  }
  if ( !*(_BYTE *)(BugCheckParameter2 + 1729) && (*(_BYTE *)(BugCheckParameter2 + 2344) & 0x20) != 0 )
    OutUninitializeQueue(BugCheckParameter2);
  if ( *(_BYTE *)(BugCheckParameter2 + 2280) )
  {
    *(_BYTE *)(BugCheckParameter2 + 2281) = 1;
    KeSetEvent((PRKEVENT)(BugCheckParameter2 + 2232), 0, 0);
    KeWaitForSingleObject((PVOID)(BugCheckParameter2 + 2256), Executive, 0, 0, 0);
    *(_BYTE *)(BugCheckParameter2 + 2280) = 0;
  }
  v12 = *(void **)(BugCheckParameter2 + 2720);
  if ( v12 )
  {
    ObfDereferenceObject(v12);
    *(_QWORD *)(BugCheckParameter2 + 2720) = 0;
  }
  v13 = *(void **)(BugCheckParameter2 + 2728);
  if ( v13 )
  {
    ObfDereferenceObject(v13);
    *(_QWORD *)(BugCheckParameter2 + 2728) = 0;
  }
  KmclChannelCleanupParentDevice(BugCheckParameter2);
  if ( (*(_BYTE *)(BugCheckParameter2 + 2344) & 8) != 0 )
    ExFreePoolWithTag((PVOID)BugCheckParameter2, 0x636D6B56u);
}

```

## disassembly

```asm
0x1400069c0  push    rbx
0x1400069c2  push    rbp
0x1400069c3  push    rsi
0x1400069c4  push    rdi
0x1400069c5  sub     rsp, 38h
0x1400069c9  cmp     dword ptr [rcx+898h], 0Ch
0x1400069d0  mov     rbx, rcx
0x1400069d3  jz      loc_140006C4C
0x1400069d9  mov     rdi, [rcx+0C58h]
0x1400069e0  xor     ebp, ebp
0x1400069e2  test    rdi, rdi
0x1400069e5  jz      short loc_140006A4B
0x1400069e7  mov     rcx, rdi
0x1400069ea  call    KmclLockChannel
0x1400069ef  lea     rsi, [rdi+0C68h]
0x1400069f6  mov     rcx, rsi; FastMutex
0x1400069f9  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140006a00  nop     dword ptr [rax+rax+00h]
0x140006a05  lea     rax, [rbx+0CB0h]
0x140006a0c  mov     r8, [rax]
0x140006a0f  cmp     [r8+8], rax
0x140006a13  jnz     loc_140006C56
0x140006a19  mov     rdx, [rax+8]
0x140006a1d  cmp     [rdx], rax
0x140006a20  jnz     loc_140006C56
0x140006a26  mov     [rdx], r8
0x140006a29  mov     rcx, rsi; FastMutex
0x140006a2c  mov     [r8+8], rdx
0x140006a30  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140006a37  nop     dword ptr [rax+rax+00h]
0x140006a3c  mov     rcx, rdi
0x140006a3f  call    KmclUnlockChannel
0x140006a44  mov     [rbx+0C58h], rbp
0x140006a4b  lea     rdi, [rbx+0CA0h]
0x140006a52  cmp     [rdi], rdi
0x140006a55  jz      short loc_140006AC7
0x140006a57  call    cs:__imp_KeEnterCriticalRegion
0x140006a5e  nop     dword ptr [rax+rax+00h]
0x140006a63  lea     rsi, [rbx+0C68h]
0x140006a6a  mov     rcx, rsi; FastMutex
0x140006a6d  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140006a74  nop     dword ptr [rax+rax+00h]
0x140006a79  mov     rax, [rdi]
0x140006a7c  cmp     rax, rdi
0x140006a7f  jz      short loc_140006AAC
0x140006a81  cmp     [rax+8], rdi
0x140006a85  jnz     loc_140006C56
0x140006a8b  mov     rcx, [rax]
0x140006a8e  cmp     [rcx+8], rax
0x140006a92  jnz     loc_140006C56
0x140006a98  mov     [rdi], rcx
0x140006a9b  mov     [rcx+8], rdi
0x140006a9f  mov     [rax+8], rax
0x140006aa3  mov     [rax], rax
0x140006aa6  mov     [rax-58h], rbp
0x140006aaa  jmp     short loc_140006A79
0x140006aac  mov     rcx, rsi; FastMutex
0x140006aaf  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140006ab6  nop     dword ptr [rax+rax+00h]
0x140006abb  call    cs:__imp_KeLeaveCriticalRegion
0x140006ac2  nop     dword ptr [rax+rax+00h]
0x140006ac7  cmp     [rbx+890h], rbp
0x140006ace  jz      short loc_140006AE3
0x140006ad0  lea     rcx, [rbx+888h]; UnicodeString
0x140006ad7  call    cs:__imp_RtlFreeUnicodeString
0x140006ade  nop     dword ptr [rax+rax+00h]
0x140006ae3  lea     rcx, KmclChannelListLock; FastMutex
0x140006aea  call    cs:__imp_ExAcquireFastMutex
0x140006af1  nop     dword ptr [rax+rax+00h]
0x140006af6  lea     rcx, [rbx+860h]
0x140006afd  mov     rax, [rcx]
0x140006b00  test    rax, rax
0x140006b03  jz      short loc_140006B23
0x140006b05  cmp     [rax+8], rcx
0x140006b09  jnz     loc_140006C56
0x140006b0f  mov     rdx, [rcx+8]
0x140006b13  cmp     [rdx], rcx
0x140006b16  jnz     loc_140006C56
0x140006b1c  mov     [rdx], rax
0x140006b1f  mov     [rax+8], rdx
0x140006b23  lea     rcx, KmclChannelListLock; FastMutex
0x140006b2a  call    cs:__imp_ExReleaseFastMutex
0x140006b31  nop     dword ptr [rax+rax+00h]
0x140006b36  mov     rcx, [rbx+0B78h]; IoWorkItem
0x140006b3d  test    rcx, rcx
0x140006b40  jz      short loc_140006B55
0x140006b42  call    cs:__imp_IoFreeWorkItem
0x140006b49  nop     dword ptr [rax+rax+00h]
0x140006b4e  mov     [rbx+0B78h], rbp
0x140006b55  mov     rcx, rbx; BugCheckParameter2
0x140006b58  call    KmclpFreeAllBounceBlocks
0x140006b5d  cmp     [rbx+0C00h], bpl
0x140006b64  jz      short loc_140006B80
0x140006b66  lea     rcx, [rbx+0B80h]; Lookaside
0x140006b6d  call    cs:__imp_ExDeleteNPagedLookasideList
0x140006b74  nop     dword ptr [rax+rax+00h]
0x140006b79  mov     [rbx+0C00h], bpl
0x140006b80  cmp     [rbx+6C1h], bpl
0x140006b87  jnz     short loc_140006B9A
0x140006b89  test    byte ptr [rbx+928h], 20h
0x140006b90  jz      short loc_140006B9A
0x140006b92  mov     rcx, rbx
0x140006b95  call    OutUninitializeQueue
0x140006b9a  cmp     [rbx+8E8h], bpl
0x140006ba1  jz      short loc_140006BE9
0x140006ba3  lea     rcx, [rbx+8B8h]; Event
0x140006baa  mov     byte ptr [rbx+8E9h], 1
0x140006bb1  xor     r8d, r8d; Wait
0x140006bb4  xor     edx, edx; Increment
0x140006bb6  call    cs:__imp_KeSetEvent
0x140006bbd  nop     dword ptr [rax+rax+00h]
0x140006bc2  lea     rcx, [rbx+8D0h]; Object
0x140006bc9  mov     [rsp+58h+Timeout], rbp; Timeout
0x140006bce  xor     r9d, r9d; Alertable
0x140006bd1  xor     r8d, r8d; WaitMode
0x140006bd4  xor     edx, edx; WaitReason
0x140006bd6  call    cs:__imp_KeWaitForSingleObject
0x140006bdd  nop     dword ptr [rax+rax+00h]
0x140006be2  mov     [rbx+8E8h], bpl
0x140006be9  mov     rcx, [rbx+0AA0h]; Object
0x140006bf0  test    rcx, rcx
0x140006bf3  jz      short loc_140006C08
0x140006bf5  call    cs:__imp_ObfDereferenceObject
0x140006bfc  nop     dword ptr [rax+rax+00h]
0x140006c01  mov     [rbx+0AA0h], rbp
0x140006c08  mov     rcx, [rbx+0AA8h]; Object
0x140006c0f  test    rcx, rcx
0x140006c12  jz      short loc_140006C27
0x140006c14  call    cs:__imp_ObfDereferenceObject
0x140006c1b  nop     dword ptr [rax+rax+00h]
0x140006c20  mov     [rbx+0AA8h], rbp
0x140006c27  mov     rcx, rbx
0x140006c2a  call    KmclChannelCleanupParentDevice
0x140006c2f  test    byte ptr [rbx+928h], 8
0x140006c36  jz      short loc_140006C4C
0x140006c38  mov     edx, 636D6B56h; Tag
0x140006c3d  mov     rcx, rbx; P
0x140006c40  call    cs:__imp_ExFreePoolWithTag
0x140006c47  nop     dword ptr [rax+rax+00h]
0x140006c4c  add     rsp, 38h
0x140006c50  pop     rdi
0x140006c51  pop     rsi
0x140006c52  pop     rbp
0x140006c53  pop     rbx
0x140006c54  retn
0x140006c56  mov     ecx, 3
0x140006c5b  int     29h; Win8: RtlFailFast(ecx)
```
