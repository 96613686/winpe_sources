# WinNatDeleteInstance

- ea: `0x14000f738`
- end: `0x14000f880`
- name: `WinNatDeleteInstance`
- size: `328`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x14000daf0`
- `0x140011130`

## callees

- `0x14000a638`
- `0x14000f624`
- `0x14000f738`
- `0x14000f888`
- `0x14000f9a4`
- `0x140019428`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000f7f1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000f7f1`

## pseudocode

```c
__int64 __fastcall WinNatDeleteInstance(char *P)
{
  __int64 *v1; // rbx
  PVOID *v3; // rcx
  __int64 ****v4; // rcx
  __int64 ***v5; // rax
  __int64 **v6; // rdx
  _QWORD *v7; // rdx
  char *v8; // rcx
  __int64 *v9; // rax
  char **v10; // rdx
  PVOID *v11; // rcx
  __int64 *v13; // [rsp+20h] [rbp-38h] BYREF
  __int64 **v14; // [rsp+28h] [rbp-30h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-28h] BYREF

  v1 = (__int64 *)qword_140027AB0;
  v14 = &v13;
  v13 = (__int64 *)&v13;
  memset(&LockHandle, 0, sizeof(LockHandle));
  while ( v1 != &qword_140027AB0 )
  {
    v3 = (PVOID *)(v1 - 2);
    v1 = (__int64 *)*v1;
    if ( v3[10] == P )
      WinNatDeletePacketFilter(v3);
  }
  RtlAcquireScalableWriteLock((__int64)P, &LockHandle);
  v4 = (__int64 ****)(P + 896);
  while ( 1 )
  {
    v5 = *v4;
    if ( *v4 == (__int64 ***)v4 )
      break;
    if ( v5[1] != (__int64 **)v4 )
      goto LABEL_19;
    v6 = *v5;
    if ( (*v5)[1] != (__int64 *)v5 )
      goto LABEL_19;
    *v4 = (__int64 ***)v6;
    v6[1] = (__int64 *)v4;
    *((_BYTE *)v5 + 48) |= 4u;
    v7 = v14;
    if ( *v14 != (__int64 *)&v13 )
      goto LABEL_19;
    v5[1] = v14;
    *v5 = &v13;
    *v7 = v5;
    v14 = (__int64 **)v5;
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  while ( 1 )
  {
    v8 = (char *)v13;
    if ( v13 == (__int64 *)&v13 )
      break;
    if ( (__int64 **)v13[1] != &v13 )
      goto LABEL_19;
    v9 = (__int64 *)*v13;
    if ( *(__int64 **)(*v13 + 8) != v13 )
      goto LABEL_19;
    v13 = (__int64 *)*v13;
    v9[1] = (__int64)&v13;
    WinNatDeleteAddressPoolEntry(v8 - 24);
  }
  WinNatLibDeleteAddressPool((__int64)qword_140027AE0, *((_QWORD **)P + 111));
  v10 = (char **)*((_QWORD *)P + 41);
  if ( v10[1] != P + 328 || (v11 = (PVOID *)*((_QWORD *)P + 42), *v11 != P + 328) )
LABEL_19:
    __fastfail(3u);
  *v11 = v10;
  v10[1] = (char *)v11;
  return WinNatDereferenceInstance(P);
}

```

## disassembly

```asm
0x14000f738  push    rbp
0x14000f73a  push    rbx
0x14000f73b  push    rsi
0x14000f73c  push    rdi
0x14000f73d  mov     rbp, rsp
0x14000f740  sub     rsp, 58h
0x14000f744  mov     rbx, cs:qword_140027AB0
0x14000f74b  lea     rsi, qword_140027AB0
0x14000f752  xor     eax, eax
0x14000f754  xorps   xmm0, xmm0
0x14000f757  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x14000f75b  mov     rdi, rcx
0x14000f75e  lea     rax, [rbp+var_38]
0x14000f762  mov     [rbp+var_30], rax
0x14000f766  lea     rax, [rbp+var_38]
0x14000f76a  mov     [rbp+var_38], rax
0x14000f76e  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x14000f772  jmp     short loc_14000F786
0x14000f774  lea     rcx, [rbx-10h]; P
0x14000f778  mov     rbx, [rbx]
0x14000f77b  cmp     [rcx+50h], rdi
0x14000f77f  jnz     short loc_14000F786
0x14000f781  call    WinNatDeletePacketFilter
0x14000f786  cmp     rbx, rsi
0x14000f789  jnz     short loc_14000F774
0x14000f78b  lea     rdx, [rbp+LockHandle]
0x14000f78f  mov     rcx, rdi
0x14000f792  call    RtlAcquireScalableWriteLock
0x14000f797  lea     rcx, [rdi+380h]
0x14000f79e  mov     rax, [rcx]
0x14000f7a1  cmp     rax, rcx
0x14000f7a4  jz      short loc_14000F7ED
0x14000f7a6  cmp     [rax+8], rcx
0x14000f7aa  jnz     loc_14000F879
0x14000f7b0  mov     rdx, [rax]
0x14000f7b3  cmp     [rdx+8], rax
0x14000f7b7  jnz     loc_14000F879
0x14000f7bd  mov     [rcx], rdx
0x14000f7c0  lea     r8, [rbp+var_38]
0x14000f7c4  mov     [rdx+8], rcx
0x14000f7c8  or      byte ptr [rax+30h], 4
0x14000f7cc  mov     rdx, [rbp+var_30]
0x14000f7d0  cmp     [rdx], r8
0x14000f7d3  jnz     loc_14000F879
0x14000f7d9  mov     [rax+8], rdx
0x14000f7dd  lea     r8, [rbp+var_38]
0x14000f7e1  mov     [rax], r8
0x14000f7e4  mov     [rdx], rax
0x14000f7e7  mov     [rbp+var_30], rax
0x14000f7eb  jmp     short loc_14000F79E
0x14000f7ed  lea     rcx, [rbp+LockHandle]; LockHandle
0x14000f7f1  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000f7f8  nop     dword ptr [rax+rax+00h]
0x14000f7fd  mov     rcx, [rbp+var_38]
0x14000f801  lea     rax, [rbp+var_38]
0x14000f805  cmp     rcx, rax
0x14000f808  jz      short loc_14000F834
0x14000f80a  lea     rax, [rbp+var_38]
0x14000f80e  cmp     [rcx+8], rax
0x14000f812  jnz     short loc_14000F879
0x14000f814  mov     rax, [rcx]
0x14000f817  cmp     [rax+8], rcx
0x14000f81b  jnz     short loc_14000F879
0x14000f81d  lea     rdx, [rbp+var_38]
0x14000f821  mov     [rbp+var_38], rax
0x14000f825  add     rcx, 0FFFFFFFFFFFFFFE8h; P
0x14000f829  mov     [rax+8], rdx
0x14000f82d  call    WinNatDeleteAddressPoolEntry
0x14000f832  jmp     short loc_14000F7FD
0x14000f834  mov     rdx, [rdi+378h]
0x14000f83b  mov     rcx, cs:qword_140027AE0
0x14000f842  call    WinNatLibDeleteAddressPool
0x14000f847  lea     rax, [rdi+148h]
0x14000f84e  mov     rdx, [rax]
0x14000f851  cmp     [rdx+8], rax
0x14000f855  jnz     short loc_14000F879
0x14000f857  mov     rcx, [rax+8]
0x14000f85b  cmp     [rcx], rax
0x14000f85e  jnz     short loc_14000F879
0x14000f860  mov     [rcx], rdx
0x14000f863  mov     [rdx+8], rcx
0x14000f867  mov     rcx, rdi; P
0x14000f86a  call    WinNatDereferenceInstance
0x14000f86f  add     rsp, 58h
0x14000f873  pop     rdi
0x14000f874  pop     rsi
0x14000f875  pop     rbx
0x14000f876  pop     rbp
0x14000f877  retn
0x14000f879  mov     ecx, 3
0x14000f87e  int     29h; Win8: RtlFailFast(ecx)
```
