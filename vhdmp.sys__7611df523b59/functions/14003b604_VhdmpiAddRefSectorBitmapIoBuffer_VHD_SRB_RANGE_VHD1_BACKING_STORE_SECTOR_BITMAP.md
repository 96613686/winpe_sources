# VhdmpiAddRefSectorBitmapIoBuffer(_VHD_SRB_RANGE *,_VHD1_BACKING_STORE *,_SECTOR_BITMAP *)

- ea: `0x14003b604`
- end: `0x14003b6ce`
- name: `?VhdmpiAddRefSectorBitmapIoBuffer@@YAPEAEPEAU_VHD_SRB_RANGE@@PEAU_VHD1_BACKING_STORE@@PEAU_SECTOR_BITMAP@@@Z`
- size: `202`
- prototype: `char *__fastcall(struct _VHD_SRB_RANGE *, struct _VHD1_BACKING_STORE *, struct _SECTOR_BITMAP *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14001c080`
- `0x14003d26c`

## callees

- `0x140023390`
- `0x14003b604`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003b631`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003b631`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003b6b5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003b6b5`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003b64a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003b64a`

## pseudocode

```c
char *__fastcall VhdmpiAddRefSectorBitmapIoBuffer(
        struct _VHD_SRB_RANGE *a1,
        struct _VHD1_BACKING_STORE *a2,
        struct _SECTOR_BITMAP *a3)
{
  char *v6; // rbx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-48h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)a2 + 548, &LockHandle);
  if ( *((_DWORD *)a3 + 12) )
  {
    v6 = (char *)*((_QWORD *)a3 + 7);
    if ( v6 == *((char **)a2 + 1103) )
    {
      v6 = 0;
    }
    else if ( v6 )
    {
      goto LABEL_9;
    }
  }
  else
  {
    v6 = (char *)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)((char *)a2 + 4416));
    if ( v6 || VhdmpiAcquireReserveResource(a1, a2, 0xDu) && (v6 = (char *)*((_QWORD *)a2 + 1103)) != 0 )
    {
      *((_QWORD *)a3 + 7) = v6;
      *((_QWORD *)a3 + 8) = &v6[*((unsigned int *)a2 + 481) - 512];
LABEL_9:
      ++*((_DWORD *)a3 + 12);
    }
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  return v6;
}

```

## disassembly

```asm
0x14003b604  push    rbx
0x14003b606  push    rbp
0x14003b607  push    rsi
0x14003b608  push    rdi
0x14003b609  sub     rsp, 48h
0x14003b60d  mov     rbp, rcx
0x14003b610  mov     rsi, rdx
0x14003b613  lea     rcx, [rdx+1120h]; SpinLock
0x14003b61a  xorps   xmm0, xmm0
0x14003b61d  xor     eax, eax
0x14003b61f  lea     rdx, [rsp+68h+LockHandle]; LockHandle
0x14003b624  mov     rdi, r8
0x14003b627  mov     qword ptr [rsp+68h+LockHandle.OldIrql], rax
0x14003b62c  movups  xmmword ptr [rsp+68h+LockHandle.LockQueue.Next], xmm0
0x14003b631  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14003b638  nop     dword ptr [rax+rax+00h]
0x14003b63d  cmp     dword ptr [rdi+30h], 0
0x14003b641  jnz     short loc_14003B697
0x14003b643  lea     rcx, [rsi+1140h]; Lookaside
0x14003b64a  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14003b651  nop     dword ptr [rax+rax+00h]
0x14003b656  mov     rbx, rax
0x14003b659  test    rax, rax
0x14003b65c  jnz     short loc_14003B67D
0x14003b65e  lea     r8d, [rax+0Dh]; unsigned int
0x14003b662  mov     rdx, rsi; struct _VHD1_BACKING_STORE *
0x14003b665  mov     rcx, rbp; struct _VHD_SRB_RANGE *
0x14003b668  call    ?VhdmpiAcquireReserveResource@@YAEPEAU_VHD_SRB_RANGE@@PEAU_VHD1_BACKING_STORE@@K@Z; VhdmpiAcquireReserveResource(_VHD_SRB_RANGE *,_VHD1_BACKING_STORE *,ulong)
0x14003b66d  test    al, al
0x14003b66f  jz      short loc_14003B6B0
0x14003b671  mov     rbx, [rsi+2278h]
0x14003b678  test    rbx, rbx
0x14003b67b  jz      short loc_14003B6B0
0x14003b67d  mov     [rdi+38h], rbx
0x14003b681  mov     ecx, [rsi+784h]
0x14003b687  add     rcx, 0FFFFFFFFFFFFFE00h
0x14003b68e  add     rcx, rbx
0x14003b691  mov     [rdi+40h], rcx
0x14003b695  jmp     short loc_14003B6AD
0x14003b697  mov     rbx, [rdi+38h]
0x14003b69b  cmp     rbx, [rsi+2278h]
0x14003b6a2  jnz     short loc_14003B6A8
0x14003b6a4  xor     ebx, ebx
0x14003b6a6  jmp     short loc_14003B6B0
0x14003b6a8  test    rbx, rbx
0x14003b6ab  jz      short loc_14003B6B0
0x14003b6ad  inc     dword ptr [rdi+30h]
0x14003b6b0  lea     rcx, [rsp+68h+LockHandle]; LockHandle
0x14003b6b5  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14003b6bc  nop     dword ptr [rax+rax+00h]
0x14003b6c1  mov     rax, rbx
0x14003b6c4  add     rsp, 48h
0x14003b6c8  pop     rdi
0x14003b6c9  pop     rsi
0x14003b6ca  pop     rbp
0x14003b6cb  pop     rbx
0x14003b6cc  retn
```
