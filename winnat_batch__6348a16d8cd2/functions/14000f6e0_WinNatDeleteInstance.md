# WinNatDeleteInstance

- ea: `0x14000f6e0`
- end: `0x14000f828`
- name: `WinNatDeleteInstance`
- size: `328`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x14000db20`
- `0x1400110d0`

## callees

- `0x14000a638`
- `0x14000f5cc`
- `0x14000f6e0`
- `0x14000f830`
- `0x14000f94c`
- `0x140018f48`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000f799`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000f799`

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

  v1 = (__int64 *)qword_140026AB0;
  v14 = &v13;
  v13 = (__int64 *)&v13;
  memset(&LockHandle, 0, sizeof(LockHandle));
  while ( v1 != &qword_140026AB0 )
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
  WinNatLibDeleteAddressPool((__int64)qword_140026AE0, *((_QWORD **)P + 111));
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
0x14000f6e0  push    rbp
0x14000f6e2  push    rbx
0x14000f6e3  push    rsi
0x14000f6e4  push    rdi
0x14000f6e5  mov     rbp, rsp
0x14000f6e8  sub     rsp, 58h
0x14000f6ec  mov     rbx, cs:qword_140026AB0
0x14000f6f3  lea     rsi, qword_140026AB0
0x14000f6fa  xor     eax, eax
0x14000f6fc  xorps   xmm0, xmm0
0x14000f6ff  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x14000f703  mov     rdi, rcx
0x14000f706  lea     rax, [rbp+var_38]
0x14000f70a  mov     [rbp+var_30], rax
0x14000f70e  lea     rax, [rbp+var_38]
0x14000f712  mov     [rbp+var_38], rax
0x14000f716  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x14000f71a  jmp     short loc_14000F72E
0x14000f71c  lea     rcx, [rbx-10h]; P
0x14000f720  mov     rbx, [rbx]
0x14000f723  cmp     [rcx+50h], rdi
0x14000f727  jnz     short loc_14000F72E
0x14000f729  call    WinNatDeletePacketFilter
0x14000f72e  cmp     rbx, rsi
0x14000f731  jnz     short loc_14000F71C
0x14000f733  lea     rdx, [rbp+LockHandle]
0x14000f737  mov     rcx, rdi
0x14000f73a  call    RtlAcquireScalableWriteLock
0x14000f73f  lea     rcx, [rdi+380h]
0x14000f746  mov     rax, [rcx]
0x14000f749  cmp     rax, rcx
0x14000f74c  jz      short loc_14000F795
0x14000f74e  cmp     [rax+8], rcx
0x14000f752  jnz     loc_14000F821
0x14000f758  mov     rdx, [rax]
0x14000f75b  cmp     [rdx+8], rax
0x14000f75f  jnz     loc_14000F821
0x14000f765  mov     [rcx], rdx
0x14000f768  lea     r8, [rbp+var_38]
0x14000f76c  mov     [rdx+8], rcx
0x14000f770  or      byte ptr [rax+30h], 4
0x14000f774  mov     rdx, [rbp+var_30]
0x14000f778  cmp     [rdx], r8
0x14000f77b  jnz     loc_14000F821
0x14000f781  mov     [rax+8], rdx
0x14000f785  lea     r8, [rbp+var_38]
0x14000f789  mov     [rax], r8
0x14000f78c  mov     [rdx], rax
0x14000f78f  mov     [rbp+var_30], rax
0x14000f793  jmp     short loc_14000F746
0x14000f795  lea     rcx, [rbp+LockHandle]; LockHandle
0x14000f799  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000f7a0  nop     dword ptr [rax+rax+00h]
0x14000f7a5  mov     rcx, [rbp+var_38]
0x14000f7a9  lea     rax, [rbp+var_38]
0x14000f7ad  cmp     rcx, rax
0x14000f7b0  jz      short loc_14000F7DC
0x14000f7b2  lea     rax, [rbp+var_38]
0x14000f7b6  cmp     [rcx+8], rax
0x14000f7ba  jnz     short loc_14000F821
0x14000f7bc  mov     rax, [rcx]
0x14000f7bf  cmp     [rax+8], rcx
0x14000f7c3  jnz     short loc_14000F821
0x14000f7c5  lea     rdx, [rbp+var_38]
0x14000f7c9  mov     [rbp+var_38], rax
0x14000f7cd  add     rcx, 0FFFFFFFFFFFFFFE8h; P
0x14000f7d1  mov     [rax+8], rdx
0x14000f7d5  call    WinNatDeleteAddressPoolEntry
0x14000f7da  jmp     short loc_14000F7A5
0x14000f7dc  mov     rdx, [rdi+378h]
0x14000f7e3  mov     rcx, cs:qword_140026AE0
0x14000f7ea  call    WinNatLibDeleteAddressPool
0x14000f7ef  lea     rax, [rdi+148h]
0x14000f7f6  mov     rdx, [rax]
0x14000f7f9  cmp     [rdx+8], rax
0x14000f7fd  jnz     short loc_14000F821
0x14000f7ff  mov     rcx, [rax+8]
0x14000f803  cmp     [rcx], rax
0x14000f806  jnz     short loc_14000F821
0x14000f808  mov     [rcx], rdx
0x14000f80b  mov     [rdx+8], rcx
0x14000f80f  mov     rcx, rdi; P
0x14000f812  call    WinNatDereferenceInstance
0x14000f817  add     rsp, 58h
0x14000f81b  pop     rdi
0x14000f81c  pop     rsi
0x14000f81d  pop     rbx
0x14000f81e  pop     rbp
0x14000f81f  retn
0x14000f821  mov     ecx, 3
0x14000f826  int     29h; Win8: RtlFailFast(ecx)
```
