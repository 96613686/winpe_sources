# WanpIpAddSubInterface

- ea: `0x14000e530`
- end: `0x14000e6f0`
- name: `WanpIpAddSubInterface`
- size: `448`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000e89c`
- `0x140010448`
- `0x1400124bc`
- `0x140012e3c`

## callees

- `0x1400050b0`
- `0x1400050f0`
- `0x14000e530`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e5df`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e67f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e6a2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e5df`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e67f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e6a2`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000e66f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000e66f`
- `ntoskrnl!KeInitializeEvent` at `0x14000e5cf`
- `ntoskrnl!KeInitializeEvent` at `0x14000e5cf`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e60e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e6c7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e60e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e6c7`

## pseudocode

```c
__int64 __fastcall WanpIpAddSubInterface(__int64 a1, __int64 a2, __int64 a3, char a4)
{
  bool v4; // zf
  __int64 v7; // rax
  __int64 v9; // rcx
  KIRQL v11; // al
  __int64 v12; // rcx
  int v13; // edi
  KIRQL v14; // al
  struct _KEVENT Event; // [rsp+30h] [rbp-49h] BYREF
  _QWORD v17[6]; // [rsp+48h] [rbp-31h] BYREF
  __int64 v18; // [rsp+78h] [rbp-1h] BYREF
  int v19; // [rsp+80h] [rbp+7h]
  _BYTE v20[28]; // [rsp+84h] [rbp+Bh] BYREF

  v4 = *(_DWORD *)(a3 + 100) == 0;
  v7 = *(_QWORD *)(a1 + 352);
  v9 = *(unsigned int *)(a3 + 64);
  v18 = v7;
  v17[0] = WanIpAddSubInterfaceComplete;
  v17[1] = *(_QWORD *)(a2 + 88);
  v17[3] = &v18;
  v17[4] = a3 + 272;
  memset(v20, 0, sizeof(v20));
  v17[5] = a3 + 128;
  memset(&Event, 0, sizeof(Event));
  v19 = v9;
  v17[2] = a3;
  if ( v4 )
    v18 = v9;
  KeInitializeEvent(&Event, SynchronizationEvent, 0);
  v11 = KeAcquireSpinLockRaiseToDpc(*(PKSPIN_LOCK *)(a3 + 80));
  v4 = *(_DWORD *)(a3 + 100) == 0;
  *(_QWORD *)(a3 + 136) = &Event;
  *(_QWORD *)(a3 + 16) = a2;
  *(_QWORD *)(a3 + 8) = a1;
  if ( !v4 )
    *(_QWORD *)(a2 + 40) = a3;
  KeReleaseSpinLock(*(PKSPIN_LOCK *)(a3 + 80), v11);
  v12 = qword_1400090D8;
  if ( !a4 )
    v12 = qword_140009328;
  v13 = (*(__int64 (__fastcall **)(_QWORD *))(*(_QWORD *)(v12 + 8) + 32LL))(v17);
  _InterlockedIncrement((volatile signed __int32 *)&byte_140009780[16 * *(int *)(a3 + 100)]);
  if ( v13 == 259 )
  {
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    v14 = KeAcquireSpinLockRaiseToDpc(*(PKSPIN_LOCK *)(a3 + 80));
    v13 = *(_DWORD *)(a3 + 144);
    *(_QWORD *)(a3 + 136) = 0;
LABEL_10:
    _InterlockedIncrement((volatile signed __int32 *)(a3 + 96));
    goto LABEL_11;
  }
  v14 = KeAcquireSpinLockRaiseToDpc(*(PKSPIN_LOCK *)(a3 + 80));
  *(_QWORD *)(a3 + 136) = 0;
  if ( v13 >= 0 )
    goto LABEL_10;
LABEL_11:
  KeReleaseSpinLock(*(PKSPIN_LOCK *)(a3 + 80), v14);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14000e530  push    rbp
0x14000e532  push    rbx
0x14000e533  push    rsi
0x14000e534  push    rdi
0x14000e535  push    r14
0x14000e537  lea     rbp, [rsp-37h]
0x14000e53c  sub     rsp, 0B0h
0x14000e543  mov     rax, cs:__security_cookie
0x14000e54a  xor     rax, rsp
0x14000e54d  mov     [rbp+57h+var_30], rax
0x14000e551  xor     eax, eax
0x14000e553  xorps   xmm0, xmm0
0x14000e556  cmp     dword ptr [r8+64h], 0
0x14000e55b  mov     rsi, rcx
0x14000e55e  mov     [rbp+57h+Event.Header.WaitListHead.Blink], rax
0x14000e562  mov     rbx, r8
0x14000e565  mov     rax, [rcx+160h]
0x14000e56c  mov     r14b, r9b
0x14000e56f  mov     ecx, [r8+40h]
0x14000e573  mov     rdi, rdx
0x14000e576  mov     [rbp+57h+var_58], rax
0x14000e57a  lea     rax, WanIpAddSubInterfaceComplete
0x14000e581  mov     [rbp+57h+var_88], rax
0x14000e585  mov     rax, [rdx+58h]
0x14000e589  mov     [rbp+57h+var_80], rax
0x14000e58d  lea     rax, [rbp+57h+var_58]
0x14000e591  mov     [rbp+57h+var_70], rax
0x14000e595  lea     rax, [r8+110h]
0x14000e59c  mov     [rbp+57h+var_68], rax
0x14000e5a0  lea     rax, [r8+80h]
0x14000e5a7  movups  xmmword ptr [rbp+57h+var_4C], xmm0
0x14000e5ab  mov     [rbp+57h+var_60], rax
0x14000e5af  movups  xmmword ptr [rbp+57h+Event.Header], xmm0
0x14000e5b3  mov     [rbp+57h+var_50], ecx
0x14000e5b6  movups  xmmword ptr [rbp+57h+var_4C+0Ch], xmm0
0x14000e5ba  mov     [rbp+57h+var_78], rbx
0x14000e5be  jnz     short loc_14000E5C4
0x14000e5c0  mov     [rbp+57h+var_58], rcx
0x14000e5c4  xor     r8d, r8d; State
0x14000e5c7  lea     rcx, [rbp+57h+Event]; Event
0x14000e5cb  lea     edx, [r8+1]; Type
0x14000e5cf  call    cs:__imp_KeInitializeEvent
0x14000e5d6  nop     dword ptr [rax+rax+00h]
0x14000e5db  mov     rcx, [rbx+50h]; SpinLock
0x14000e5df  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000e5e6  nop     dword ptr [rax+rax+00h]
0x14000e5eb  cmp     dword ptr [rbx+64h], 0
0x14000e5ef  lea     rcx, [rbp+57h+Event]
0x14000e5f3  mov     [rbx+88h], rcx
0x14000e5fa  mov     [rbx+10h], rdi
0x14000e5fe  mov     [rbx+8], rsi
0x14000e602  jz      short loc_14000E608
0x14000e604  mov     [rdi+28h], rbx
0x14000e608  mov     rcx, [rbx+50h]; SpinLock
0x14000e60c  mov     dl, al; NewIrql
0x14000e60e  call    cs:__imp_KeReleaseSpinLock
0x14000e615  nop     dword ptr [rax+rax+00h]
0x14000e61a  mov     rcx, cs:qword_1400090D8
0x14000e621  test    r14b, r14b
0x14000e624  cmovz   rcx, cs:qword_140009328
0x14000e62c  mov     rax, [rcx+8]
0x14000e630  lea     rcx, [rbp+57h+var_88]
0x14000e634  mov     rax, [rax+20h]
0x14000e638  call    _guard_dispatch_icall
0x14000e63d  movsxd  rcx, dword ptr [rbx+64h]
0x14000e641  mov     edi, eax
0x14000e643  shl     rcx, 4
0x14000e647  lea     rax, byte_140009780
0x14000e64e  lock inc dword ptr [rcx+rax]
0x14000e652  cmp     edi, 103h
0x14000e658  jnz     short loc_14000E69E
0x14000e65a  xor     r9d, r9d; Alertable
0x14000e65d  mov     [rsp+0D0h+Timeout], 0; Timeout
0x14000e666  xor     r8d, r8d; WaitMode
0x14000e669  lea     rcx, [rbp+57h+Event]; Object
0x14000e66d  xor     edx, edx; WaitReason
0x14000e66f  call    cs:__imp_KeWaitForSingleObject
0x14000e676  nop     dword ptr [rax+rax+00h]
0x14000e67b  mov     rcx, [rbx+50h]; SpinLock
0x14000e67f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000e686  nop     dword ptr [rax+rax+00h]
0x14000e68b  mov     edi, [rbx+90h]
0x14000e691  mov     qword ptr [rbx+88h], 0
0x14000e69c  jmp     short loc_14000E6BD
0x14000e69e  mov     rcx, [rbx+50h]; SpinLock
0x14000e6a2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000e6a9  nop     dword ptr [rax+rax+00h]
0x14000e6ae  mov     qword ptr [rbx+88h], 0
0x14000e6b9  test    edi, edi
0x14000e6bb  js      short loc_14000E6C1
0x14000e6bd  lock inc dword ptr [rbx+60h]
0x14000e6c1  mov     rcx, [rbx+50h]; SpinLock
0x14000e6c5  mov     dl, al; NewIrql
0x14000e6c7  call    cs:__imp_KeReleaseSpinLock
0x14000e6ce  nop     dword ptr [rax+rax+00h]
0x14000e6d3  mov     eax, edi
0x14000e6d5  mov     rcx, [rbp+57h+var_30]
0x14000e6d9  xor     rcx, rsp; StackCookie
0x14000e6dc  call    __security_check_cookie
0x14000e6e1  add     rsp, 0B0h
0x14000e6e8  pop     r14
0x14000e6ea  pop     rdi
0x14000e6eb  pop     rsi
0x14000e6ec  pop     rbx
0x14000e6ed  pop     rbp
0x14000e6ee  retn
```
