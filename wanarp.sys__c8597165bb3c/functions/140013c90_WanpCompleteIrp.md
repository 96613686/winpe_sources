# WanpCompleteIrp

- ea: `0x140013c90`
- end: `0x140013dcb`
- name: `WanpCompleteIrp`
- size: `315`
- prototype: `void __fastcall(char *Entry)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000f9c8`
- `0x140010448`

## callees

- `0x1400051c0`
- `0x140013c90`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140013cf8`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140013d5c`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140013db3`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140013cf8`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140013d5c`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140013db3`
- `ntoskrnl!IofCompleteRequest` at `0x140013d6d`
- `ntoskrnl!IofCompleteRequest` at `0x140013d6d`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140013caa`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140013caa`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140013d83`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140013d83`

## pseudocode

```c
void __fastcall WanpCompleteIrp(char *Entry)
{
  char v1; // bl
  __int64 *v3; // rcx
  __int64 *v4; // rdx
  __int64 *v5; // rax
  __int64 v6; // rax
  __int64 *v7; // rbx
  __int64 **v8; // rcx
  KIRQL v9; // cl
  KIRQL Irql; // [rsp+30h] [rbp+8h] BYREF

  v1 = Entry[60];
  Irql = 0;
  IoAcquireCancelSpinLock(&Irql);
  v3 = (__int64 *)g_lePendingV6IrpList;
  v4 = &g_lePendingV4IrpList;
  if ( v1 )
    v3 = (__int64 *)g_lePendingV4IrpList;
  else
    v4 = &g_lePendingV6IrpList;
  v5 = (__int64 *)&g_lePendingV4NotificationList;
  if ( !v1 )
    v5 = &g_lePendingV6NotificationList;
  if ( !g_bQueueNotifications )
  {
    IoReleaseCancelSpinLock(Irql);
LABEL_12:
    ExFreeToNPagedLookasideList(&g_llNotificationBlocks, Entry);
    return;
  }
  if ( v3 != v4 )
  {
    if ( (__int64 *)v3[1] == v4 )
    {
      v6 = *v3;
      if ( *(__int64 **)(*v3 + 8) == v3 )
      {
        *v4 = v6;
        v7 = v3 - 21;
        *(_QWORD *)(v6 + 8) = v4;
        memmove((void *)*(v3 - 18), Entry + 48, 0x620u);
        _InterlockedExchange64(v7 + 13, 0);
        *((_DWORD *)v7 + 12) = 0;
        v7[7] = 1568;
        IoReleaseCancelSpinLock(Irql);
        IofCompleteRequest((PIRP)v7, 2);
        goto LABEL_12;
      }
    }
LABEL_14:
    __fastfail(3u);
  }
  v8 = (__int64 **)v5[1];
  if ( *v8 != v5 )
    goto LABEL_14;
  *((_QWORD *)Entry + 1) = v8;
  *(_QWORD *)Entry = v5;
  *v8 = (__int64 *)Entry;
  v9 = Irql;
  v5[1] = (__int64)Entry;
  IoReleaseCancelSpinLock(v9);
}

```

## disassembly

```asm
0x140013c90  mov     [rsp+arg_8], rbx
0x140013c95  push    rdi
0x140013c96  sub     rsp, 20h
0x140013c9a  mov     bl, [rcx+3Ch]
0x140013c9d  mov     rdi, rcx
0x140013ca0  lea     rcx, [rsp+28h+Irql]; Irql
0x140013ca5  mov     [rsp+28h+Irql], 0
0x140013caa  call    cs:__imp_IoAcquireCancelSpinLock
0x140013cb1  nop     dword ptr [rax+rax+00h]
0x140013cb6  mov     rcx, cs:g_lePendingV6IrpList
0x140013cbd  lea     rax, g_lePendingV6IrpList
0x140013cc4  test    bl, bl
0x140013cc6  lea     rdx, g_lePendingV4IrpList
0x140013ccd  lea     r8, g_lePendingV6NotificationList
0x140013cd4  cmovnz  rcx, cs:g_lePendingV4IrpList
0x140013cdc  cmovz   rdx, rax
0x140013ce0  lea     rax, g_lePendingV4NotificationList
0x140013ce7  cmovz   rax, r8
0x140013ceb  cmp     cs:g_bQueueNotifications, 0
0x140013cf2  jnz     short loc_140013D06
0x140013cf4  mov     cl, [rsp+28h+Irql]; Irql
0x140013cf8  call    cs:__imp_IoReleaseCancelSpinLock
0x140013cff  nop     dword ptr [rax+rax+00h]
0x140013d04  jmp     short loc_140013D79
0x140013d06  cmp     rcx, rdx
0x140013d09  jz      loc_140013D91
0x140013d0f  cmp     [rcx+8], rdx
0x140013d13  jnz     loc_140013D9A
0x140013d19  mov     rax, [rcx]
0x140013d1c  cmp     [rax+8], rcx
0x140013d20  jnz     short loc_140013D9A
0x140013d22  mov     [rdx], rax
0x140013d25  lea     rbx, [rcx-0A8h]
0x140013d2c  mov     [rax+8], rdx
0x140013d30  mov     r8d, 620h; Size
0x140013d36  mov     rcx, [rbx+18h]; void *
0x140013d3a  lea     rdx, [rdi+30h]; Src
0x140013d3e  call    memmove
0x140013d43  xor     eax, eax
0x140013d45  xchg    rax, [rbx+68h]
0x140013d49  mov     dword ptr [rbx+30h], 0
0x140013d50  mov     qword ptr [rbx+38h], 620h
0x140013d58  mov     cl, [rsp+28h+Irql]; Irql
0x140013d5c  call    cs:__imp_IoReleaseCancelSpinLock
0x140013d63  nop     dword ptr [rax+rax+00h]
0x140013d68  mov     dl, 2; PriorityBoost
0x140013d6a  mov     rcx, rbx; Irp
0x140013d6d  call    cs:__imp_IofCompleteRequest
0x140013d74  nop     dword ptr [rax+rax+00h]
0x140013d79  mov     rdx, rdi; Entry
0x140013d7c  lea     rcx, g_llNotificationBlocks; Lookaside
0x140013d83  call    cs:__imp_ExFreeToNPagedLookasideList
0x140013d8a  nop     dword ptr [rax+rax+00h]
0x140013d8f  jmp     short loc_140013DBF
0x140013d91  mov     rcx, [rax+8]
0x140013d95  cmp     [rcx], rax
0x140013d98  jz      short loc_140013DA1
0x140013d9a  mov     ecx, 3
0x140013d9f  int     29h; Win8: RtlFailFast(ecx)
0x140013da1  mov     [rdi+8], rcx
0x140013da5  mov     [rdi], rax
0x140013da8  mov     [rcx], rdi
0x140013dab  mov     cl, [rsp+28h+Irql]; Irql
0x140013daf  mov     [rax+8], rdi
0x140013db3  call    cs:__imp_IoReleaseCancelSpinLock
0x140013dba  nop     dword ptr [rax+rax+00h]
0x140013dbf  mov     rbx, [rsp+28h+arg_8]
0x140013dc4  add     rsp, 20h
0x140013dc8  pop     rdi
0x140013dc9  retn
```
