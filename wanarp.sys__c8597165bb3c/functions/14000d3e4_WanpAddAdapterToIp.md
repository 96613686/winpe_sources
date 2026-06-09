# WanpAddAdapterToIp

- ea: `0x14000d3e4`
- end: `0x14000d618`
- name: `WanpAddAdapterToIp`
- size: `564`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000e89c`
- `0x140010448`
- `0x1400124bc`
- `0x140012e3c`

## callees

- `0x140002e40`
- `0x14000457c`
- `0x1400050f0`
- `0x14000d3e4`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d560`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d591`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d560`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d591`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000d551`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000d551`
- `ntoskrnl!KeInitializeEvent` at `0x14000d496`
- `ntoskrnl!KeInitializeEvent` at `0x14000d496`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d5da`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d5da`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000d4e5`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000d4e5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d4f8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d57d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d5b7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d4f8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d57d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d5b7`

## pseudocode

```c
__int64 __fastcall WanpAddAdapterToIp(__int64 a1, __int64 a2, char a3, KIRQL a4)
{
  __int64 *v4; // rbp
  _QWORD *v9; // rcx
  bool v10; // zf
  int v11; // r14d
  KIRQL v12; // al
  KIRQL v13; // al
  struct _KEVENT Event; // [rsp+30h] [rbp-78h] BYREF
  _QWORD v16[12]; // [rsp+48h] [rbp-60h] BYREF

  v4 = &WanNmrV4ProviderState;
  memset(&Event, 0, sizeof(Event));
  if ( !a3 )
    v4 = &WanNmrV6ProviderState;
  v16[0] = WanIpAddInterfaceComplete;
  v9 = (_QWORD *)v4[27];
  v16[1] = *v9;
  v16[3] = a1 + 352;
  v16[4] = a2 + 184;
  v16[5] = a2 + 88;
  v16[2] = a2;
  if ( !(unsigned __int8)RoReferenceEx(v9 + 4) )
    return 3221225473LL;
  *(_DWORD *)(a1 + 368) = *(_DWORD *)(a2 + 164);
  *(_OWORD *)(a1 + 372) = *(_OWORD *)(a2 + 168);
  KeInitializeEvent(&Event, SynchronizationEvent, 0);
  v10 = *(_DWORD *)(a2 + 108) == 2;
  *(_QWORD *)(a2 + 96) = &Event;
  if ( !v10 )
  {
    *(_QWORD *)(a2 + 24) = a1;
    *(_BYTE *)(a2 + 48) = 6;
    if ( a3 )
      *(_QWORD *)(a1 + 168) = a2;
    else
      *(_QWORD *)(a1 + 176) = a2;
  }
  if ( *(_DWORD *)(a2 + 108) )
    ++*(_DWORD *)(a1 + 184);
  _InterlockedIncrement((volatile signed __int32 *)(a2 + 64));
  KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(a2 + 56));
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 120), a4);
  v11 = (*(__int64 (__fastcall **)(_QWORD *))(*(_QWORD *)(v4[27] + 8) + 8LL))(v16);
  _InterlockedIncrement((volatile signed __int32 *)&byte_140009778[16 * *(int *)(a2 + 108)]);
  if ( v11 == 259 )
  {
    KeWaitForSingleObject(*(PVOID *)(a2 + 96), Executive, 0, 0, 0);
    v12 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 56));
    v11 = *(_DWORD *)(a2 + 104);
    *(_QWORD *)(a2 + 96) = 0;
    KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 56), v12);
  }
  if ( v11 < 0 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a2 + 64), 0xFFFFFFFF) == 1 )
      ExFreePoolWithTag((PVOID)a2, 0);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4[27] + 32), 0xFFFFFFFE) == 3 )
      WanNmrFinalizeDetach((__int64)v4);
    return 3221225473LL;
  }
  v13 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 56));
  v10 = *(_DWORD *)(a2 + 108) == 2;
  *(_QWORD *)(a2 + 96) = 0;
  if ( !v10 )
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 128));
  KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 56), v13);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14000d3e4  mov     r11, rsp
0x14000d3e7  push    rbx
0x14000d3e8  push    rbp
0x14000d3e9  push    rsi
0x14000d3ea  push    rdi
0x14000d3eb  push    r14
0x14000d3ed  sub     rsp, 80h
0x14000d3f4  xor     eax, eax
0x14000d3f6  lea     rbp, WanNmrV4ProviderState
0x14000d3fd  mov     rdi, rcx
0x14000d400  xorps   xmm0, xmm0
0x14000d403  movups  xmmword ptr [rsp+0A8h+Event.Header], xmm0
0x14000d408  mov     [r11-68h], rax
0x14000d40c  test    r8b, r8b
0x14000d40f  lea     rax, WanNmrV6ProviderState
0x14000d416  mov     r14b, r9b
0x14000d419  cmovz   rbp, rax
0x14000d41d  mov     sil, r8b
0x14000d420  lea     rax, WanIpAddInterfaceComplete
0x14000d427  mov     rbx, rdx
0x14000d42a  mov     [r11-60h], rax
0x14000d42e  mov     rcx, [rbp+0D8h]
0x14000d435  mov     rax, [rcx]
0x14000d438  add     rcx, 20h ; ' '
0x14000d43c  mov     [r11-58h], rax
0x14000d440  lea     rax, [rdi+160h]
0x14000d447  mov     [r11-48h], rax
0x14000d44b  lea     rax, [rdx+0B8h]
0x14000d452  mov     [r11-40h], rax
0x14000d456  lea     rax, [rdx+58h]
0x14000d45a  mov     [r11-38h], rax
0x14000d45e  mov     [r11-50h], rdx
0x14000d462  call    RoReferenceEx
0x14000d467  test    al, al
0x14000d469  jz      loc_14000D604
0x14000d46f  mov     eax, [rbx+0A4h]
0x14000d475  lea     rcx, [rsp+0A8h+Event]; Event
0x14000d47a  xor     r8d, r8d; State
0x14000d47d  mov     [rdi+170h], eax
0x14000d483  movups  xmm0, xmmword ptr [rbx+0A8h]
0x14000d48a  lea     edx, [r8+1]; Type
0x14000d48e  movdqu  xmmword ptr [rdi+174h], xmm0
0x14000d496  call    cs:__imp_KeInitializeEvent
0x14000d49d  nop     dword ptr [rax+rax+00h]
0x14000d4a2  cmp     dword ptr [rbx+6Ch], 2
0x14000d4a6  lea     rax, [rsp+0A8h+Event]
0x14000d4ab  mov     [rbx+60h], rax
0x14000d4af  jz      short loc_14000D4CE
0x14000d4b1  mov     [rbx+18h], rdi
0x14000d4b5  mov     byte ptr [rbx+30h], 6
0x14000d4b9  test    sil, sil
0x14000d4bc  jz      short loc_14000D4C7
0x14000d4be  mov     [rdi+0A8h], rbx
0x14000d4c5  jmp     short loc_14000D4CE
0x14000d4c7  mov     [rdi+0B0h], rbx
0x14000d4ce  cmp     dword ptr [rbx+6Ch], 0
0x14000d4d2  jz      short loc_14000D4DA
0x14000d4d4  inc     dword ptr [rdi+0B8h]
0x14000d4da  lock inc dword ptr [rbx+40h]
0x14000d4de  lea     rsi, [rbx+38h]
0x14000d4e2  mov     rcx, rsi; SpinLock
0x14000d4e5  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000d4ec  nop     dword ptr [rax+rax+00h]
0x14000d4f1  lea     rcx, [rdi+78h]; SpinLock
0x14000d4f5  mov     dl, r14b; NewIrql
0x14000d4f8  call    cs:__imp_KeReleaseSpinLock
0x14000d4ff  nop     dword ptr [rax+rax+00h]
0x14000d504  mov     rax, [rbp+0D8h]
0x14000d50b  mov     rcx, [rax+8]
0x14000d50f  mov     rax, [rcx+8]
0x14000d513  lea     rcx, [rsp+0A8h+var_60]
0x14000d518  call    _guard_dispatch_icall
0x14000d51d  movsxd  rcx, dword ptr [rbx+6Ch]
0x14000d521  mov     r14d, eax
0x14000d524  shl     rcx, 4
0x14000d528  lea     rax, byte_140009778
0x14000d52f  lock inc dword ptr [rcx+rax]
0x14000d533  cmp     r14d, 103h
0x14000d53a  jnz     short loc_14000D589
0x14000d53c  mov     rcx, [rbx+60h]; Object
0x14000d540  xor     r9d, r9d; Alertable
0x14000d543  xor     r8d, r8d; WaitMode
0x14000d546  mov     [rsp+0A8h+Timeout], 0; Timeout
0x14000d54f  xor     edx, edx; WaitReason
0x14000d551  call    cs:__imp_KeWaitForSingleObject
0x14000d558  nop     dword ptr [rax+rax+00h]
0x14000d55d  mov     rcx, rsi; SpinLock
0x14000d560  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000d567  nop     dword ptr [rax+rax+00h]
0x14000d56c  mov     r14d, [rbx+68h]
0x14000d570  mov     rcx, rsi; SpinLock
0x14000d573  mov     dl, al; NewIrql
0x14000d575  mov     qword ptr [rbx+60h], 0
0x14000d57d  call    cs:__imp_KeReleaseSpinLock
0x14000d584  nop     dword ptr [rax+rax+00h]
0x14000d589  test    r14d, r14d
0x14000d58c  js      short loc_14000D5C8
0x14000d58e  mov     rcx, rsi; SpinLock
0x14000d591  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000d598  nop     dword ptr [rax+rax+00h]
0x14000d59d  cmp     dword ptr [rbx+6Ch], 2
0x14000d5a1  mov     qword ptr [rbx+60h], 0
0x14000d5a9  jz      short loc_14000D5B2
0x14000d5ab  lock inc dword ptr [rdi+80h]
0x14000d5b2  mov     dl, al; NewIrql
0x14000d5b4  mov     rcx, rsi; SpinLock
0x14000d5b7  call    cs:__imp_KeReleaseSpinLock
0x14000d5be  nop     dword ptr [rax+rax+00h]
0x14000d5c3  mov     eax, r14d
0x14000d5c6  jmp     short loc_14000D609
0x14000d5c8  or      eax, 0FFFFFFFFh
0x14000d5cb  lock xadd [rbx+40h], eax
0x14000d5d0  cmp     eax, 1
0x14000d5d3  jnz     short loc_14000D5E6
0x14000d5d5  xor     edx, edx; Tag
0x14000d5d7  mov     rcx, rbx; P
0x14000d5da  call    cs:__imp_ExFreePoolWithTag
0x14000d5e1  nop     dword ptr [rax+rax+00h]
0x14000d5e6  mov     rdx, [rbp+0D8h]
0x14000d5ed  mov     eax, 0FFFFFFFEh
0x14000d5f2  lock xadd [rdx+20h], eax
0x14000d5f7  cmp     eax, 3
0x14000d5fa  jnz     short loc_14000D604
0x14000d5fc  mov     rcx, rbp
0x14000d5ff  call    WanNmrFinalizeDetach
0x14000d604  mov     eax, 0C0000001h
0x14000d609  add     rsp, 80h
0x14000d610  pop     r14
0x14000d612  pop     rdi
0x14000d613  pop     rsi
0x14000d614  pop     rbp
0x14000d615  pop     rbx
0x14000d616  retn
```
