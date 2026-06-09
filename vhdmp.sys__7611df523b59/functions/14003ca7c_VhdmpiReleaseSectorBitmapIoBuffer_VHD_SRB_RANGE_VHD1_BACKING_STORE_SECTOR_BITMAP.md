# VhdmpiReleaseSectorBitmapIoBuffer(_VHD_SRB_RANGE *,_VHD1_BACKING_STORE *,_SECTOR_BITMAP *)

- ea: `0x14003ca7c`
- end: `0x14003cb40`
- name: `?VhdmpiReleaseSectorBitmapIoBuffer@@YAXPEAU_VHD_SRB_RANGE@@PEAU_VHD1_BACKING_STORE@@PEAU_SECTOR_BITMAP@@@Z`
- size: `196`
- prototype: `void __fastcall(struct _VHD_SRB_RANGE *, struct _VHD1_BACKING_STORE *, struct _SECTOR_BITMAP *)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14001c080`
- `0x14003c224`
- `0x14003d26c`
- `0x14003d870`

## callees

- `0x140020d0c`
- `0x14003ca7c`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003cab1`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003cab1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003cae6`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003cae6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003cb20`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003cb20`

## pseudocode

```c
void __fastcall VhdmpiReleaseSectorBitmapIoBuffer(
        struct _VHD_SRB_RANGE *a1,
        struct _VHD1_BACKING_STORE *a2,
        struct _SECTOR_BITMAP *a3)
{
  void *v7; // rbx
  char v8; // bp
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-38h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)a2 + 548, &LockHandle);
  if ( (*((_DWORD *)a3 + 12))-- == 1 )
  {
    v7 = (void *)*((_QWORD *)a3 + 7);
    v8 = 1;
    *((_QWORD *)a3 + 7) = 0;
    *((_QWORD *)a3 + 8) = 0;
  }
  else
  {
    v7 = 0;
    v8 = 0;
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( v8 )
  {
    if ( v7 == *((void **)a2 + 1103) )
      VhdmpiReleaseReserveResource(a1, a2, 0xDu, 1u);
    else
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)((char *)a2 + 4416), v7);
  }
}

```

## disassembly

```asm
0x14003ca7c  mov     r11, rsp
0x14003ca7f  mov     [r11+8], rbx
0x14003ca83  mov     [r11+18h], rbp
0x14003ca87  push    rsi
0x14003ca88  push    rdi
0x14003ca89  push    r14
0x14003ca8b  sub     rsp, 40h
0x14003ca8f  mov     r14, rcx
0x14003ca92  xorps   xmm0, xmm0
0x14003ca95  lea     rcx, [rdx+1120h]; SpinLock
0x14003ca9c  mov     rsi, rdx
0x14003ca9f  xor     eax, eax
0x14003caa1  lea     rdx, [r11-38h]; LockHandle
0x14003caa5  movups  xmmword ptr [rsp+58h+LockHandle.LockQueue.Next], xmm0
0x14003caaa  mov     [r11-28h], rax
0x14003caae  mov     rdi, r8
0x14003cab1  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14003cab8  nop     dword ptr [rax+rax+00h]
0x14003cabd  add     dword ptr [rdi+30h], 0FFFFFFFFh
0x14003cac1  jnz     short loc_14003CADC
0x14003cac3  mov     rbx, [rdi+38h]
0x14003cac7  mov     bpl, 1
0x14003caca  mov     qword ptr [rdi+38h], 0
0x14003cad2  mov     qword ptr [rdi+40h], 0
0x14003cada  jmp     short loc_14003CAE1
0x14003cadc  xor     ebx, ebx
0x14003cade  xor     bpl, bpl
0x14003cae1  lea     rcx, [rsp+58h+LockHandle]; LockHandle
0x14003cae6  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14003caed  nop     dword ptr [rax+rax+00h]
0x14003caf2  test    bpl, bpl
0x14003caf5  jz      short loc_14003CB2C
0x14003caf7  cmp     rbx, [rsi+2278h]
0x14003cafe  jnz     short loc_14003CB16
0x14003cb00  mov     r9b, 1; unsigned __int8
0x14003cb03  mov     r8d, 0Dh; unsigned int
0x14003cb09  mov     rdx, rsi; struct _VHD1_BACKING_STORE *
0x14003cb0c  mov     rcx, r14; struct _VHD_SRB_RANGE *
0x14003cb0f  call    ?VhdmpiReleaseReserveResource@@YAXPEAU_VHD_SRB_RANGE@@PEAU_VHD1_BACKING_STORE@@KE@Z; VhdmpiReleaseReserveResource(_VHD_SRB_RANGE *,_VHD1_BACKING_STORE *,ulong,uchar)
0x14003cb14  jmp     short loc_14003CB2C
0x14003cb16  lea     rcx, [rsi+1140h]; Lookaside
0x14003cb1d  mov     rdx, rbx; Entry
0x14003cb20  call    cs:__imp_ExFreeToNPagedLookasideList
0x14003cb27  nop     dword ptr [rax+rax+00h]
0x14003cb2c  mov     rbx, [rsp+58h+arg_0]
0x14003cb31  mov     rbp, [rsp+58h+arg_10]
0x14003cb36  add     rsp, 40h
0x14003cb3a  pop     r14
0x14003cb3c  pop     rdi
0x14003cb3d  pop     rsi
0x14003cb3e  retn
```
