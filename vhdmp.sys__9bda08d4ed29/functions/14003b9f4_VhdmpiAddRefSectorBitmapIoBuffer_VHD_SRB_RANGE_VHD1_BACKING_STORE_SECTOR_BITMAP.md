# VhdmpiAddRefSectorBitmapIoBuffer(_VHD_SRB_RANGE *,_VHD1_BACKING_STORE *,_SECTOR_BITMAP *)

- ea: `0x14003b9f4`
- end: `0x14003babe`
- name: `?VhdmpiAddRefSectorBitmapIoBuffer@@YAPEAEPEAU_VHD_SRB_RANGE@@PEAU_VHD1_BACKING_STORE@@PEAU_SECTOR_BITMAP@@@Z`
- size: `202`
- prototype: `unsigned __int8 *__fastcall(struct _VHD_SRB_RANGE *, struct _VHD1_BACKING_STORE *, struct _SECTOR_BITMAP *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14001c4a0`
- `0x14003d65c`

## callees

- `0x1400237b0`
- `0x14003b9f4`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003ba21`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003ba21`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003baa5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003baa5`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003ba3a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003ba3a`

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
0x14003b9f4  push    rbx
0x14003b9f6  push    rbp
0x14003b9f7  push    rsi
0x14003b9f8  push    rdi
0x14003b9f9  sub     rsp, 48h
0x14003b9fd  mov     rbp, rcx
0x14003ba00  mov     rsi, rdx
0x14003ba03  lea     rcx, [rdx+1120h]; SpinLock
0x14003ba0a  xorps   xmm0, xmm0
0x14003ba0d  xor     eax, eax
0x14003ba0f  lea     rdx, [rsp+68h+LockHandle]; LockHandle
0x14003ba14  mov     rdi, r8
0x14003ba17  mov     qword ptr [rsp+68h+LockHandle.OldIrql], rax
0x14003ba1c  movups  xmmword ptr [rsp+68h+LockHandle.LockQueue.Next], xmm0
0x14003ba21  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14003ba28  nop     dword ptr [rax+rax+00h]
0x14003ba2d  cmp     dword ptr [rdi+30h], 0
0x14003ba31  jnz     short loc_14003BA87
0x14003ba33  lea     rcx, [rsi+1140h]; Lookaside
0x14003ba3a  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14003ba41  nop     dword ptr [rax+rax+00h]
0x14003ba46  mov     rbx, rax
0x14003ba49  test    rax, rax
0x14003ba4c  jnz     short loc_14003BA6D
0x14003ba4e  lea     r8d, [rax+0Dh]; unsigned int
0x14003ba52  mov     rdx, rsi; struct _VHD1_BACKING_STORE *
0x14003ba55  mov     rcx, rbp; struct _VHD_SRB_RANGE *
0x14003ba58  call    ?VhdmpiAcquireReserveResource@@YAEPEAU_VHD_SRB_RANGE@@PEAU_VHD1_BACKING_STORE@@K@Z; VhdmpiAcquireReserveResource(_VHD_SRB_RANGE *,_VHD1_BACKING_STORE *,ulong)
0x14003ba5d  test    al, al
0x14003ba5f  jz      short loc_14003BAA0
0x14003ba61  mov     rbx, [rsi+2278h]
0x14003ba68  test    rbx, rbx
0x14003ba6b  jz      short loc_14003BAA0
0x14003ba6d  mov     [rdi+38h], rbx
0x14003ba71  mov     ecx, [rsi+784h]
0x14003ba77  add     rcx, 0FFFFFFFFFFFFFE00h
0x14003ba7e  add     rcx, rbx
0x14003ba81  mov     [rdi+40h], rcx
0x14003ba85  jmp     short loc_14003BA9D
0x14003ba87  mov     rbx, [rdi+38h]
0x14003ba8b  cmp     rbx, [rsi+2278h]
0x14003ba92  jnz     short loc_14003BA98
0x14003ba94  xor     ebx, ebx
0x14003ba96  jmp     short loc_14003BAA0
0x14003ba98  test    rbx, rbx
0x14003ba9b  jz      short loc_14003BAA0
0x14003ba9d  inc     dword ptr [rdi+30h]
0x14003baa0  lea     rcx, [rsp+68h+LockHandle]; LockHandle
0x14003baa5  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14003baac  nop     dword ptr [rax+rax+00h]
0x14003bab1  mov     rax, rbx
0x14003bab4  add     rsp, 48h
0x14003bab8  pop     rdi
0x14003bab9  pop     rsi
0x14003baba  pop     rbp
0x14003babb  pop     rbx
0x14003babc  retn
```
