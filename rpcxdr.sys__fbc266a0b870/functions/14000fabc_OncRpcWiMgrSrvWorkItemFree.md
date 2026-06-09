# OncRpcWiMgrSrvWorkItemFree

- ea: `0x14000fabc`
- end: `0x14000fc63`
- name: `OncRpcWiMgrSrvWorkItemFree`
- size: `423`
- prototype: `__int64(void)`
- caller_count: `6`
- callee_count: `6`
- tags: ``

## callers

- `0x140004600`
- `0x1400083b8`
- `0x1400085c0`
- `0x14000df80`
- `0x14000e8e0`
- `0x14000f770`

## callees

- `0x14000127c`
- `0x1400059a4`
- `0x140006798`
- `0x14000d228`
- `0x14000fabc`
- `0x140010080`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000fb09`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000fb09`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000fbdf`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000fbdf`

## pseudocode

```c
__int64 __fastcall OncRpcWiMgrSrvWorkItemFree(__int64 a1)
{
  int v2; // eax
  int v3; // eax
  __int64 v4; // rdi
  _QWORD *v5; // rax
  __int64 v6; // rdx
  _QWORD *v7; // rcx
  char v8; // r14
  int v9; // ecx
  __int64 v11; // r9
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-48h] BYREF

  v2 = *(_DWORD *)(a1 + 352);
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( (v2 & 8) == 0 )
    OncRpcBufMgrFree((char *)(a1 + 128));
  v3 = *(_DWORD *)(a1 + 2440);
  if ( (v3 & 1) == 0 )
  {
    if ( (v3 & 2) != 0 )
    {
      v11 = *(_QWORD *)(a1 + 2424);
      _InterlockedDecrement((volatile signed __int32 *)(v11 + 232));
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
      {
        WPP_SF_qd(
          WPP_GLOBAL_Control->AttachedDevice,
          17,
          WPP_cf8ac67cd1d9331d79f7433cf770f93d_Traceguids,
          v11,
          *(_DWORD *)(v11 + 232));
      }
    }
    return OncRpcWiMgrpSrvWorkItemFreeInternal(a1);
  }
  v4 = *(_QWORD *)(a1 + 2432);
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v4 + 72), &LockHandle);
  --*(_DWORD *)(v4 + 192);
  v5 = (_QWORD *)(a1 + 72);
  v6 = *(_QWORD *)(a1 + 72);
  if ( *(_QWORD *)(v6 + 8) != a1 + 72 || (v7 = *(_QWORD **)(a1 + 80), (_QWORD *)*v7 != v5) )
    __fastfail(3u);
  *v7 = v6;
  *(_QWORD *)(v6 + 8) = v7;
  v8 = 0;
  *(_QWORD *)(a1 + 80) = a1 + 72;
  *v5 = v5;
  v9 = *(_DWORD *)(v4 + 136);
  if ( (v9 & 4) != 0 && (unsigned int)dword_14001A430 > *(_DWORD *)(v4 + 192) )
  {
    v8 = 1;
    *(_DWORD *)(v4 + 136) = v9 & 0xFFFFFFFB;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_14;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
      WPP_SF_q(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0xFu,
        (__int64)WPP_cf8ac67cd1d9331d79f7433cf770f93d_Traceguids,
        v4);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
    WPP_SF_qd(
      WPP_GLOBAL_Control->AttachedDevice,
      16,
      WPP_cf8ac67cd1d9331d79f7433cf770f93d_Traceguids,
      v4,
      *(_DWORD *)(v4 + 192));
LABEL_14:
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( v8 )
    return OncRpcConnMgrReEnableDataIndication(a1);
  return OncRpcWiMgrpSrvWorkItemFreeInternal(a1);
}

```

## disassembly

```asm
0x14000fabc  push    rbx
0x14000fabe  push    rbp
0x14000fabf  push    rdi
0x14000fac0  push    r14
0x14000fac2  sub     rsp, 58h
0x14000fac6  xor     eax, eax
0x14000fac8  xorps   xmm0, xmm0
0x14000facb  mov     qword ptr [rsp+78h+LockHandle.OldIrql], rax
0x14000fad0  mov     rbx, rcx
0x14000fad3  mov     eax, [rcx+160h]
0x14000fad9  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x14000fade  test    al, 8
0x14000fae0  jnz     short loc_14000FAEB
0x14000fae2  sub     rcx, 0FFFFFFFFFFFFFF80h; Entry
0x14000fae6  call    OncRpcBufMgrFree
0x14000faeb  mov     eax, [rbx+988h]
0x14000faf1  test    al, 1
0x14000faf3  jz      loc_14000FC01
0x14000faf9  mov     rdi, [rbx+980h]
0x14000fb00  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x14000fb05  lea     rcx, [rdi+48h]; SpinLock
0x14000fb09  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000fb10  nop     dword ptr [rax+rax+00h]
0x14000fb15  dec     dword ptr [rdi+0C0h]
0x14000fb1b  lea     rax, [rbx+48h]
0x14000fb1f  mov     rdx, [rax]
0x14000fb22  cmp     [rdx+8], rax
0x14000fb26  jnz     loc_14000FBFA
0x14000fb2c  mov     rcx, [rax+8]
0x14000fb30  cmp     [rcx], rax
0x14000fb33  jnz     loc_14000FBFA
0x14000fb39  mov     [rcx], rdx
0x14000fb3c  lea     rbp, WPP_GLOBAL_Control
0x14000fb43  mov     [rdx+8], rcx
0x14000fb47  xor     r14b, r14b
0x14000fb4a  mov     [rax+8], rax
0x14000fb4e  mov     [rax], rax
0x14000fb51  mov     ecx, [rdi+88h]
0x14000fb57  test    cl, 4
0x14000fb5a  jz      short loc_14000FBA3
0x14000fb5c  mov     eax, [rdi+0C0h]
0x14000fb62  cmp     cs:dword_14001A430, eax
0x14000fb68  jbe     short loc_14000FBA3
0x14000fb6a  and     ecx, 0FFFFFFFBh
0x14000fb6d  mov     r14b, 1
0x14000fb70  mov     [rdi+88h], ecx
0x14000fb76  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fb7d  cmp     rcx, rbp
0x14000fb80  jz      short loc_14000FBDA
0x14000fb82  test    dword ptr [rcx+2Ch], 100h
0x14000fb89  jz      short loc_14000FBA3
0x14000fb8b  mov     rcx, [rcx+18h]
0x14000fb8f  lea     r8, WPP_cf8ac67cd1d9331d79f7433cf770f93d_Traceguids
0x14000fb96  mov     edx, 0Fh
0x14000fb9b  mov     r9, rdi
0x14000fb9e  call    WPP_SF_q
0x14000fba3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fbaa  cmp     rcx, rbp
0x14000fbad  jz      short loc_14000FBDA
0x14000fbaf  test    dword ptr [rcx+2Ch], 100h
0x14000fbb6  jz      short loc_14000FBDA
0x14000fbb8  mov     eax, [rdi+0C0h]
0x14000fbbe  lea     r8, WPP_cf8ac67cd1d9331d79f7433cf770f93d_Traceguids
0x14000fbc5  mov     rcx, [rcx+18h]
0x14000fbc9  mov     edx, 10h
0x14000fbce  mov     r9, rdi
0x14000fbd1  mov     [rsp+78h+var_58], eax
0x14000fbd5  call    WPP_SF_qd
0x14000fbda  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x14000fbdf  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000fbe6  nop     dword ptr [rax+rax+00h]
0x14000fbeb  test    r14b, r14b
0x14000fbee  jz      short loc_14000FC50
0x14000fbf0  mov     rcx, rbx
0x14000fbf3  call    OncRpcConnMgrReEnableDataIndication
0x14000fbf8  jmp     short loc_14000FC58
0x14000fbfa  mov     ecx, 3
0x14000fbff  int     29h; Win8: RtlFailFast(ecx)
0x14000fc01  test    al, 2
0x14000fc03  jz      short loc_14000FC50
0x14000fc05  mov     r9, [rbx+978h]
0x14000fc0c  lock dec dword ptr [r9+0E8h]
0x14000fc14  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fc1b  lea     rbp, WPP_GLOBAL_Control
0x14000fc22  cmp     rcx, rbp
0x14000fc25  jz      short loc_14000FC50
0x14000fc27  test    dword ptr [rcx+2Ch], 100h
0x14000fc2e  jz      short loc_14000FC50
0x14000fc30  mov     eax, [r9+0E8h]
0x14000fc37  lea     r8, WPP_cf8ac67cd1d9331d79f7433cf770f93d_Traceguids
0x14000fc3e  mov     rcx, [rcx+18h]
0x14000fc42  mov     edx, 11h
0x14000fc47  mov     [rsp+78h+var_58], eax
0x14000fc4b  call    WPP_SF_qd
0x14000fc50  mov     rcx, rbx
0x14000fc53  call    OncRpcWiMgrpSrvWorkItemFreeInternal
0x14000fc58  add     rsp, 58h
0x14000fc5c  pop     r14
0x14000fc5e  pop     rdi
0x14000fc5f  pop     rbp
0x14000fc60  pop     rbx
0x14000fc61  retn
```
