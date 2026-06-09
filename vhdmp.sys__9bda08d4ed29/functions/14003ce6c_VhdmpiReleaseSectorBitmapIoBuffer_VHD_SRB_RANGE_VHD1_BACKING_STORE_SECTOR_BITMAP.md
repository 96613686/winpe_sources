# VhdmpiReleaseSectorBitmapIoBuffer(_VHD_SRB_RANGE *,_VHD1_BACKING_STORE *,_SECTOR_BITMAP *)

- ea: `0x14003ce6c`
- end: `0x14003cf30`
- name: `?VhdmpiReleaseSectorBitmapIoBuffer@@YAXPEAU_VHD_SRB_RANGE@@PEAU_VHD1_BACKING_STORE@@PEAU_SECTOR_BITMAP@@@Z`
- size: `196`
- prototype: `void __fastcall(struct _VHD_SRB_RANGE *, struct _VHD1_BACKING_STORE *, struct _SECTOR_BITMAP *)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14001c4a0`
- `0x14003c614`
- `0x14003d65c`
- `0x14003dc60`

## callees

- `0x14002112c`
- `0x14003ce6c`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003cea1`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003cea1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003ced6`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003ced6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003cf10`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003cf10`

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
0x14003ce6c  mov     r11, rsp
0x14003ce6f  mov     [r11+8], rbx
0x14003ce73  mov     [r11+18h], rbp
0x14003ce77  push    rsi
0x14003ce78  push    rdi
0x14003ce79  push    r14
0x14003ce7b  sub     rsp, 40h
0x14003ce7f  mov     r14, rcx
0x14003ce82  xorps   xmm0, xmm0
0x14003ce85  lea     rcx, [rdx+1120h]; SpinLock
0x14003ce8c  mov     rsi, rdx
0x14003ce8f  xor     eax, eax
0x14003ce91  lea     rdx, [r11-38h]; LockHandle
0x14003ce95  movups  xmmword ptr [rsp+58h+LockHandle.LockQueue.Next], xmm0
0x14003ce9a  mov     [r11-28h], rax
0x14003ce9e  mov     rdi, r8
0x14003cea1  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14003cea8  nop     dword ptr [rax+rax+00h]
0x14003cead  add     dword ptr [rdi+30h], 0FFFFFFFFh
0x14003ceb1  jnz     short loc_14003CECC
0x14003ceb3  mov     rbx, [rdi+38h]
0x14003ceb7  mov     bpl, 1
0x14003ceba  mov     qword ptr [rdi+38h], 0
0x14003cec2  mov     qword ptr [rdi+40h], 0
0x14003ceca  jmp     short loc_14003CED1
0x14003cecc  xor     ebx, ebx
0x14003cece  xor     bpl, bpl
0x14003ced1  lea     rcx, [rsp+58h+LockHandle]; LockHandle
0x14003ced6  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14003cedd  nop     dword ptr [rax+rax+00h]
0x14003cee2  test    bpl, bpl
0x14003cee5  jz      short loc_14003CF1C
0x14003cee7  cmp     rbx, [rsi+2278h]
0x14003ceee  jnz     short loc_14003CF06
0x14003cef0  mov     r9b, 1; unsigned __int8
0x14003cef3  mov     r8d, 0Dh; unsigned int
0x14003cef9  mov     rdx, rsi; struct _VHD1_BACKING_STORE *
0x14003cefc  mov     rcx, r14; struct _VHD_SRB_RANGE *
0x14003ceff  call    ?VhdmpiReleaseReserveResource@@YAXPEAU_VHD_SRB_RANGE@@PEAU_VHD1_BACKING_STORE@@KE@Z; VhdmpiReleaseReserveResource(_VHD_SRB_RANGE *,_VHD1_BACKING_STORE *,ulong,uchar)
0x14003cf04  jmp     short loc_14003CF1C
0x14003cf06  lea     rcx, [rsi+1140h]; Lookaside
0x14003cf0d  mov     rdx, rbx; Entry
0x14003cf10  call    cs:__imp_ExFreeToNPagedLookasideList
0x14003cf17  nop     dword ptr [rax+rax+00h]
0x14003cf1c  mov     rbx, [rsp+58h+arg_0]
0x14003cf21  mov     rbp, [rsp+58h+arg_10]
0x14003cf26  add     rsp, 40h
0x14003cf2a  pop     r14
0x14003cf2c  pop     rdi
0x14003cf2d  pop     rsi
0x14003cf2e  retn
```
