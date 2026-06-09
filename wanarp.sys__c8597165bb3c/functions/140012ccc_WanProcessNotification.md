# WanProcessNotification

- ea: `0x140012ccc`
- end: `0x140012e36`
- name: `WanProcessNotification`
- size: `362`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int, char)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400172d0`

## callees

- `0x1400051c0`
- `0x140012ccc`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140012d74`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140012e14`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140012d74`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140012e14`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140012d03`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140012d03`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140012d8a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140012d8a`

## pseudocode

```c
__int64 __fastcall WanProcessNotification(__int64 a1, unsigned int a2, unsigned int a3, char a4)
{
  __int64 *v6; // rdi
  __int64 *v7; // rax
  __int64 v8; // rcx
  KIRQL v9; // cl
  _QWORD *v11; // rax
  _QWORD *v12; // rcx
  _QWORD *v13; // rcx
  KIRQL Irql; // [rsp+58h] [rbp+10h] BYREF

  Irql = 0;
  *(_QWORD *)(a1 + 56) = 0;
  if ( a2 < 0x620 || a3 < 0x620 )
    return 3221225507LL;
  IoAcquireCancelSpinLock(&Irql);
  v6 = (__int64 *)g_lePendingV6NotificationList;
  v7 = (__int64 *)&g_lePendingV4NotificationList;
  if ( a4 )
    v6 = (__int64 *)g_lePendingV4NotificationList;
  else
    v7 = &g_lePendingV6NotificationList;
  if ( v6 != v7 )
  {
    if ( (__int64 *)v6[1] == v7 )
    {
      v8 = *v6;
      if ( *(__int64 **)(*v6 + 8) == v6 )
      {
        *v7 = v8;
        *(_QWORD *)(v8 + 8) = v7;
        memmove(*(void **)(a1 + 24), v6 + 6, 0x620u);
        _InterlockedExchange64((volatile __int64 *)(a1 + 104), 0);
        v9 = Irql;
        *(_QWORD *)(a1 + 56) = 1568;
        IoReleaseCancelSpinLock(v9);
        ExFreeToNPagedLookasideList(&g_llNotificationBlocks, v6);
        return 0;
      }
    }
LABEL_14:
    __fastfail(3u);
  }
  *(_BYTE *)(*(_QWORD *)(a1 + 184) + 3LL) |= 1u;
  v11 = (_QWORD *)(a1 + 168);
  if ( a4 )
  {
    v12 = (_QWORD *)qword_140009CE8;
    if ( *(__int64 **)qword_140009CE8 != &g_lePendingV4IrpList )
      goto LABEL_14;
    *v11 = &g_lePendingV4IrpList;
    *(_QWORD *)(a1 + 176) = v12;
    *v12 = v11;
    qword_140009CE8 = a1 + 168;
  }
  else
  {
    v13 = (_QWORD *)qword_140009C68;
    if ( *(__int64 **)qword_140009C68 != &g_lePendingV6IrpList )
      goto LABEL_14;
    *v11 = &g_lePendingV6IrpList;
    *(_QWORD *)(a1 + 176) = v13;
    *v13 = v11;
    qword_140009C68 = a1 + 168;
  }
  _InterlockedExchange64((volatile __int64 *)(a1 + 104), (__int64)&WanCancelNotificationIrp);
  IoReleaseCancelSpinLock(Irql);
  return 259;
}

```

## disassembly

```asm
0x140012ccc  push    rbx
0x140012cce  push    rbp
0x140012ccf  push    rsi
0x140012cd0  push    rdi
0x140012cd1  sub     rsp, 28h
0x140012cd5  mov     ebp, 620h
0x140012cda  mov     [rsp+48h+Irql], 0
0x140012cdf  mov     qword ptr [rcx+38h], 0
0x140012ce7  mov     sil, r9b
0x140012cea  mov     rbx, rcx
0x140012ced  cmp     edx, ebp
0x140012cef  jb      loc_140012E27
0x140012cf5  cmp     r8d, ebp
0x140012cf8  jb      loc_140012E27
0x140012cfe  lea     rcx, [rsp+48h+Irql]; Irql
0x140012d03  call    cs:__imp_IoAcquireCancelSpinLock
0x140012d0a  nop     dword ptr [rax+rax+00h]
0x140012d0f  mov     rdi, cs:g_lePendingV6NotificationList
0x140012d16  lea     rcx, g_lePendingV6NotificationList
0x140012d1d  test    sil, sil
0x140012d20  lea     rax, g_lePendingV4NotificationList
0x140012d27  cmovnz  rdi, cs:g_lePendingV4NotificationList
0x140012d2f  cmovz   rax, rcx
0x140012d33  cmp     rdi, rax
0x140012d36  jz      short loc_140012D9D
0x140012d38  cmp     [rdi+8], rax
0x140012d3c  jnz     loc_140012DED
0x140012d42  mov     rcx, [rdi]
0x140012d45  cmp     [rcx+8], rdi
0x140012d49  jnz     loc_140012DED
0x140012d4f  mov     [rax], rcx
0x140012d52  lea     rdx, [rdi+30h]; Src
0x140012d56  mov     [rcx+8], rax
0x140012d5a  mov     r8d, ebp; Size
0x140012d5d  mov     rcx, [rbx+18h]; void *
0x140012d61  call    memmove
0x140012d66  xor     eax, eax
0x140012d68  xchg    rax, [rbx+68h]
0x140012d6c  mov     cl, [rsp+48h+Irql]; Irql
0x140012d70  mov     [rbx+38h], rbp
0x140012d74  call    cs:__imp_IoReleaseCancelSpinLock
0x140012d7b  nop     dword ptr [rax+rax+00h]
0x140012d80  mov     rdx, rdi; Entry
0x140012d83  lea     rcx, g_llNotificationBlocks; Lookaside
0x140012d8a  call    cs:__imp_ExFreeToNPagedLookasideList
0x140012d91  nop     dword ptr [rax+rax+00h]
0x140012d96  xor     eax, eax
0x140012d98  jmp     loc_140012E2C
0x140012d9d  mov     rax, [rbx+0B8h]
0x140012da4  or      byte ptr [rax+3], 1
0x140012da8  lea     rax, [rbx+0A8h]
0x140012daf  test    sil, sil
0x140012db2  jz      short loc_140012DDA
0x140012db4  mov     rcx, cs:qword_140009CE8
0x140012dbb  lea     rdx, g_lePendingV4IrpList
0x140012dc2  cmp     [rcx], rdx
0x140012dc5  jnz     short loc_140012DED
0x140012dc7  mov     [rax], rdx
0x140012dca  mov     [rax+8], rcx
0x140012dce  mov     [rcx], rax
0x140012dd1  mov     cs:qword_140009CE8, rax
0x140012dd8  jmp     short loc_140012E05
0x140012dda  mov     rcx, cs:qword_140009C68
0x140012de1  lea     rdx, g_lePendingV6IrpList
0x140012de8  cmp     [rcx], rdx
0x140012deb  jz      short loc_140012DF4
0x140012ded  mov     ecx, 3
0x140012df2  int     29h; Win8: RtlFailFast(ecx)
0x140012df4  mov     [rax], rdx
0x140012df7  mov     [rax+8], rcx
0x140012dfb  mov     [rcx], rax
0x140012dfe  mov     cs:qword_140009C68, rax
0x140012e05  lea     rax, WanCancelNotificationIrp
0x140012e0c  xchg    rax, [rbx+68h]
0x140012e10  mov     cl, [rsp+48h+Irql]; Irql
0x140012e14  call    cs:__imp_IoReleaseCancelSpinLock
0x140012e1b  nop     dword ptr [rax+rax+00h]
0x140012e20  mov     eax, 103h
0x140012e25  jmp     short loc_140012E2C
0x140012e27  mov     eax, 0C0000023h
0x140012e2c  add     rsp, 28h
0x140012e30  pop     rdi
0x140012e31  pop     rsi
0x140012e32  pop     rbp
0x140012e33  pop     rbx
0x140012e34  retn
```
