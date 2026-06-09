# OncRpcConnMgrpConnectionDisconnectPostIrpCompletion

- ea: `0x140008110`
- end: `0x14000829f`
- name: `OncRpcConnMgrpConnectionDisconnectPostIrpCompletion`
- size: `399`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140007d58`

## callees

- `0x140006798`
- `0x140008110`
- `0x140015680`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000814c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400081d9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000814c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400081d9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000822c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000823d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000822c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000823d`

## pseudocode

```c
void __fastcall OncRpcConnMgrpConnectionDisconnectPostIrpCompletion(__int64 a1)
{
  __int64 v1; // rbx
  char v3; // si
  int v4; // edx
  int v5; // eax
  __int64 v6; // rcx
  __int64 *v7; // rcx
  __int64 *v8; // rdx
  __int64 **v9; // rax
  __int64 v10; // rax
  __int64 **v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rdx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-38h] BYREF
  struct _KLOCK_QUEUE_HANDLE v16; // [rsp+38h] [rbp-20h] BYREF

  v1 = *(_QWORD *)(a1 + 56);
  memset(&v16, 0, sizeof(v16));
  memset(&LockHandle, 0, sizeof(LockHandle));
  v3 = 0;
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v1 + 72), &v16);
  v4 = *(_DWORD *)(v1 + 80);
  if ( v4 == 3 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_cd42a1555dae3c8c93cac586485c41cc_Traceguids, v1);
    *(_DWORD *)(v1 + 80) = 4;
    v4 = 4;
  }
  *(_DWORD *)(v1 + 136) |= 1u;
  v5 = *(_DWORD *)(v1 + 136);
  if ( *(_QWORD *)(v1 + 104) && (v5 & 2) == 0 )
  {
    v3 = 1;
    *(_DWORD *)(v1 + 136) = v5 | 2;
  }
  v6 = *(_QWORD *)(v1 + 64);
  if ( v6 && v4 == 4 )
  {
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v6 + 40), &LockHandle);
    v7 = (__int64 *)(v1 + 24);
    v8 = *(__int64 **)(v1 + 24);
    if ( v8[1] != v1 + 24
      || (v9 = *(__int64 ***)(v1 + 32), *v9 != v7)
      || (*v9 = v8,
          v8[1] = (__int64)v9,
          v10 = *(_QWORD *)(v1 + 64) + 264LL,
          v11 = *(__int64 ***)(*(_QWORD *)(v1 + 64) + 272LL),
          *v11 != (__int64 *)v10) )
    {
      __fastfail(3u);
    }
    *v7 = v10;
    *(_QWORD *)(v1 + 32) = v11;
    *v11 = v7;
    *(_QWORD *)(v10 + 8) = v7;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  KeReleaseInStackQueuedSpinLock(&v16);
  if ( v3 )
    (*(void (__fastcall **)(__int64, _QWORD))(v1 + 104))(v1, 0);
  if ( *(_QWORD *)(a1 + 8) )
  {
    v12 = *(_QWORD *)(a1 + 40);
    if ( v12 )
    {
      v13 = *(unsigned int *)(v12 + 48);
      v14 = *(_QWORD *)(v12 + 56);
    }
    else
    {
      v13 = 0;
      v14 = 0;
    }
    (*(void (__fastcall **)(__int64, __int64, _QWORD))(a1 + 8))(v13, v14, *(_QWORD *)(a1 + 16));
  }
}

```

## disassembly

```asm
0x140008110  mov     r11, rsp
0x140008113  mov     [r11+8], rbx
0x140008117  mov     [r11+10h], rsi
0x14000811b  push    rdi
0x14000811c  sub     rsp, 50h
0x140008120  mov     rbx, [rcx+38h]
0x140008124  lea     rdx, [r11-20h]; LockHandle
0x140008128  xor     eax, eax
0x14000812a  xorps   xmm0, xmm0
0x14000812d  xorps   xmm1, xmm1
0x140008130  mov     rdi, rcx
0x140008133  movups  xmmword ptr [rsp+58h+var_20.LockQueue.Next], xmm0
0x140008138  lea     rcx, [rbx+48h]; SpinLock
0x14000813c  mov     [r11-10h], rax
0x140008140  movups  xmmword ptr [rsp+58h+LockHandle.LockQueue.Next], xmm1
0x140008145  mov     [r11-28h], rax
0x140008149  xor     sil, sil
0x14000814c  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140008153  nop     dword ptr [rax+rax+00h]
0x140008158  mov     edx, [rbx+50h]
0x14000815b  cmp     edx, 3
0x14000815e  jnz     short loc_14000819E
0x140008160  mov     rcx, cs:WPP_GLOBAL_Control
0x140008167  lea     rax, WPP_GLOBAL_Control
0x14000816e  cmp     rcx, rax
0x140008171  jz      short loc_140008192
0x140008173  mov     eax, [rcx+2Ch]
0x140008176  test    al, 8
0x140008178  jz      short loc_140008192
0x14000817a  mov     rcx, [rcx+18h]
0x14000817e  lea     r8, WPP_cd42a1555dae3c8c93cac586485c41cc_Traceguids
0x140008185  mov     edx, 14h
0x14000818a  mov     r9, rbx
0x14000818d  call    WPP_SF_q
0x140008192  mov     dword ptr [rbx+50h], 4
0x140008199  mov     edx, 4
0x14000819e  or      dword ptr [rbx+88h], 1
0x1400081a5  cmp     qword ptr [rbx+68h], 0
0x1400081aa  mov     eax, [rbx+88h]
0x1400081b0  jz      short loc_1400081C2
0x1400081b2  test    al, 2
0x1400081b4  jnz     short loc_1400081C2
0x1400081b6  or      eax, 2
0x1400081b9  mov     sil, 1
0x1400081bc  mov     [rbx+88h], eax
0x1400081c2  mov     rcx, [rbx+40h]
0x1400081c6  test    rcx, rcx
0x1400081c9  jz      short loc_140008238
0x1400081cb  cmp     edx, 4
0x1400081ce  jnz     short loc_140008238
0x1400081d0  add     rcx, 28h ; '('; SpinLock
0x1400081d4  lea     rdx, [rsp+58h+LockHandle]; LockHandle
0x1400081d9  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400081e0  nop     dword ptr [rax+rax+00h]
0x1400081e5  lea     rcx, [rbx+18h]
0x1400081e9  mov     rdx, [rcx]
0x1400081ec  cmp     [rdx+8], rcx
0x1400081f0  jnz     loc_140008277
0x1400081f6  mov     rax, [rcx+8]
0x1400081fa  cmp     [rax], rcx
0x1400081fd  jnz     short loc_140008277
0x1400081ff  mov     [rax], rdx
0x140008202  mov     [rdx+8], rax
0x140008206  mov     rax, [rbx+40h]
0x14000820a  add     rax, 108h
0x140008210  mov     rdx, [rax+8]
0x140008214  cmp     [rdx], rax
0x140008217  jnz     short loc_140008277
0x140008219  mov     [rcx], rax
0x14000821c  mov     [rcx+8], rdx
0x140008220  mov     [rdx], rcx
0x140008223  mov     [rax+8], rcx
0x140008227  lea     rcx, [rsp+58h+LockHandle]; LockHandle
0x14000822c  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140008233  nop     dword ptr [rax+rax+00h]
0x140008238  lea     rcx, [rsp+58h+var_20]; LockHandle
0x14000823d  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140008244  nop     dword ptr [rax+rax+00h]
0x140008249  test    sil, sil
0x14000824c  jz      short loc_14000825C
0x14000824e  mov     rax, [rbx+68h]
0x140008252  xor     edx, edx
0x140008254  mov     rcx, rbx
0x140008257  call    _guard_dispatch_icall
0x14000825c  mov     r9, [rdi+8]
0x140008260  test    r9, r9
0x140008263  jz      short loc_14000828E
0x140008265  mov     rax, [rdi+28h]
0x140008269  test    rax, rax
0x14000826c  jz      short loc_14000827E
0x14000826e  mov     ecx, [rax+30h]
0x140008271  mov     rdx, [rax+38h]
0x140008275  jmp     short loc_140008282
0x140008277  mov     ecx, 3
0x14000827c  int     29h; Win8: RtlFailFast(ecx)
0x14000827e  xor     ecx, ecx
0x140008280  xor     edx, edx
0x140008282  mov     r8, [rdi+10h]
0x140008286  mov     rax, r9
0x140008289  call    _guard_dispatch_icall
0x14000828e  mov     rbx, [rsp+58h+arg_0]
0x140008293  mov     rsi, [rsp+58h+arg_8]
0x140008298  add     rsp, 50h
0x14000829c  pop     rdi
0x14000829d  retn
```
