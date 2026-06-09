# OncRpcConnMgrConnectionClose

- ea: `0x1400070c4`
- end: `0x14000729c`
- name: `OncRpcConnMgrConnectionClose`
- size: `472`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x140006228`
- `0x140006a80`
- `0x140006ad0`
- `0x140008034`
- `0x14000db30`

## callees

- `0x140002170`
- `0x1400059a4`
- `0x140006798`
- `0x1400070c4`
- `0x1400082a8`
- `0x14000880c`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400070f9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000718e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400070f9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000718e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140007112`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400071dd`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000722c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140007112`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400071dd`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000722c`

## pseudocode

```c
__int64 __fastcall OncRpcConnMgrConnectionClose(__int64 a1)
{
  int v2; // ecx
  __int64 v4; // rcx
  int v5; // esi
  __int64 *v6; // rcx
  __int64 *v7; // rdx
  __int64 **v8; // rax
  __int64 v9; // rax
  __int64 **v10; // rdx
  __int64 v11; // r8
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-38h] BYREF
  struct _KLOCK_QUEUE_HANDLE v13; // [rsp+48h] [rbp-20h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  memset(&v13, 0, sizeof(v13));
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 72), &LockHandle);
  v2 = *(_DWORD *)(a1 + 80);
  if ( v2 == 5 )
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
      WPP_SF_q(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x1Bu,
        (__int64)WPP_cd42a1555dae3c8c93cac586485c41cc_Traceguids,
        a1);
    return 0;
  }
  else
  {
    if ( !v2 || v2 == 6 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
        WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_cd42a1555dae3c8c93cac586485c41cc_Traceguids, a1, v2);
      v5 = -1073741436;
    }
    else
    {
      v4 = *(_QWORD *)(a1 + 64);
      v5 = 0;
      *(_DWORD *)(a1 + 80) = 5;
      if ( v4 )
      {
        KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v4 + 40), &v13);
        v6 = (__int64 *)(a1 + 24);
        v7 = *(__int64 **)(a1 + 24);
        if ( v7[1] != a1 + 24
          || (v8 = *(__int64 ***)(a1 + 32), *v8 != v6)
          || (*v8 = v7,
              v7[1] = (__int64)v8,
              v9 = *(_QWORD *)(a1 + 64) + 264LL,
              v10 = *(__int64 ***)(*(_QWORD *)(a1 + 64) + 272LL),
              *v10 != (__int64 *)v9) )
        {
          __fastfail(3u);
        }
        *v6 = v9;
        *(_QWORD *)(a1 + 32) = v10;
        *v10 = v6;
        *(_QWORD *)(v9 + 8) = v6;
        KeReleaseInStackQueuedSpinLock(&v13);
      }
    }
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    if ( v5 >= 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
        WPP_SF_qdL(
          WPP_GLOBAL_Control->AttachedDevice,
          29,
          v11,
          a1,
          *(_DWORD *)(a1 + 4),
          *(_DWORD *)(a1 + 80),
          LockHandle.LockQueue.Next,
          LockHandle.LockQueue.Lock,
          *(_QWORD *)&LockHandle.OldIrql);
      if ( !(unsigned int)NfsStandardHeaderDereferenceNoType(a1) )
        OncRpcConnMgrpConnectionFree(a1);
    }
    return (unsigned int)v5;
  }
}

```

## disassembly

```asm
0x1400070c4  mov     r11, rsp
0x1400070c7  mov     [r11+8], rbx
0x1400070cb  mov     [r11+10h], rsi
0x1400070cf  push    rdi
0x1400070d0  sub     rsp, 60h
0x1400070d4  xor     eax, eax
0x1400070d6  lea     rdx, [r11-38h]; LockHandle
0x1400070da  xorps   xmm0, xmm0
0x1400070dd  xorps   xmm1, xmm1
0x1400070e0  mov     rbx, rcx
0x1400070e3  add     rcx, 48h ; 'H'; SpinLock
0x1400070e7  movups  xmmword ptr [rsp+68h+LockHandle.LockQueue.Next], xmm0
0x1400070ec  mov     [r11-28h], rax
0x1400070f0  movups  xmmword ptr [rsp+68h+var_20.LockQueue.Next], xmm1
0x1400070f5  mov     [r11-10h], rax
0x1400070f9  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140007100  nop     dword ptr [rax+rax+00h]
0x140007105  mov     ecx, [rbx+50h]
0x140007108  cmp     ecx, 5
0x14000710b  jnz     short loc_140007157
0x14000710d  lea     rcx, [rsp+68h+LockHandle]; LockHandle
0x140007112  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140007119  nop     dword ptr [rax+rax+00h]
0x14000711e  mov     rcx, cs:WPP_GLOBAL_Control
0x140007125  lea     rdi, WPP_GLOBAL_Control
0x14000712c  cmp     rcx, rdi
0x14000712f  jz      short loc_140007150
0x140007131  mov     eax, [rcx+2Ch]
0x140007134  test    al, 8
0x140007136  jz      short loc_140007150
0x140007138  mov     rcx, [rcx+18h]
0x14000713c  lea     r8, WPP_cd42a1555dae3c8c93cac586485c41cc_Traceguids
0x140007143  mov     edx, 1Bh
0x140007148  mov     r9, rbx
0x14000714b  call    WPP_SF_q
0x140007150  xor     eax, eax
0x140007152  jmp     loc_14000728B
0x140007157  lea     rdi, WPP_GLOBAL_Control
0x14000715e  test    ecx, ecx
0x140007160  jz      loc_1400071F2
0x140007166  cmp     ecx, 6
0x140007169  jz      loc_1400071F2
0x14000716f  mov     rcx, [rbx+40h]
0x140007173  xor     esi, esi
0x140007175  mov     dword ptr [rbx+50h], 5
0x14000717c  test    rcx, rcx
0x14000717f  jz      loc_140007227
0x140007185  add     rcx, 28h ; '('; SpinLock
0x140007189  lea     rdx, [rsp+68h+var_20]; LockHandle
0x14000718e  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140007195  nop     dword ptr [rax+rax+00h]
0x14000719a  lea     rcx, [rbx+18h]
0x14000719e  mov     rdx, [rcx]
0x1400071a1  cmp     [rdx+8], rcx
0x1400071a5  jnz     short loc_1400071EB
0x1400071a7  mov     rax, [rcx+8]
0x1400071ab  cmp     [rax], rcx
0x1400071ae  jnz     short loc_1400071EB
0x1400071b0  mov     [rax], rdx
0x1400071b3  mov     [rdx+8], rax
0x1400071b7  mov     rax, [rbx+40h]
0x1400071bb  add     rax, 108h
0x1400071c1  mov     rdx, [rax+8]
0x1400071c5  cmp     [rdx], rax
0x1400071c8  jnz     short loc_1400071EB
0x1400071ca  mov     [rcx], rax
0x1400071cd  mov     [rcx+8], rdx
0x1400071d1  mov     [rdx], rcx
0x1400071d4  mov     [rax+8], rcx
0x1400071d8  lea     rcx, [rsp+68h+var_20]; LockHandle
0x1400071dd  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400071e4  nop     dword ptr [rax+rax+00h]
0x1400071e9  jmp     short loc_140007227
0x1400071eb  mov     ecx, 3
0x1400071f0  int     29h; Win8: RtlFailFast(ecx)
0x1400071f2  mov     r10, cs:WPP_GLOBAL_Control
0x1400071f9  cmp     r10, rdi
0x1400071fc  jz      short loc_140007222
0x1400071fe  mov     eax, [r10+2Ch]
0x140007202  test    al, 8
0x140007204  jz      short loc_140007222
0x140007206  mov     [rsp+68h+var_48], ecx
0x14000720a  lea     r8, WPP_cd42a1555dae3c8c93cac586485c41cc_Traceguids
0x140007211  mov     rcx, [r10+18h]
0x140007215  mov     edx, 1Ch
0x14000721a  mov     r9, rbx
0x14000721d  call    WPP_SF_qd
0x140007222  mov     esi, 0C0000184h
0x140007227  lea     rcx, [rsp+68h+LockHandle]; LockHandle
0x14000722c  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140007233  nop     dword ptr [rax+rax+00h]
0x140007238  test    esi, esi
0x14000723a  js      short loc_140007289
0x14000723c  mov     rax, cs:WPP_GLOBAL_Control
0x140007243  cmp     rax, rdi
0x140007246  jz      short loc_140007275
0x140007248  mov     eax, [rax+2Ch]
0x14000724b  test    al, 8
0x14000724d  jz      short loc_140007275
0x14000724f  mov     ecx, [rbx+4]
0x140007252  mov     edx, 1Dh
0x140007257  mov     eax, [rbx+50h]
0x14000725a  mov     r9, rbx
0x14000725d  mov     [rsp+68h+var_40], eax
0x140007261  mov     [rsp+68h+var_48], ecx
0x140007265  mov     rcx, cs:WPP_GLOBAL_Control
0x14000726c  mov     rcx, [rcx+18h]
0x140007270  call    WPP_SF_qdL
0x140007275  mov     rcx, rbx
0x140007278  call    NfsStandardHeaderDereferenceNoType
0x14000727d  test    eax, eax
0x14000727f  jnz     short loc_140007289
0x140007281  mov     rcx, rbx
0x140007284  call    OncRpcConnMgrpConnectionFree
0x140007289  mov     eax, esi
0x14000728b  mov     rbx, [rsp+68h+arg_0]
0x140007290  mov     rsi, [rsp+68h+arg_8]
0x140007295  add     rsp, 60h
0x140007299  pop     rdi
0x14000729a  retn
```
