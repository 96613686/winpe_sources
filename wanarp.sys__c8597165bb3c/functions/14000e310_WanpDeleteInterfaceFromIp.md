# WanpDeleteInterfaceFromIp

- ea: `0x14000e310`
- end: `0x14000e4dd`
- name: `WanpDeleteInterfaceFromIp`
- size: `461`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `8`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140002510`
- `0x14000e6f8`
- `0x14000e89c`
- `0x14000f094`
- `0x140010448`
- `0x1400124bc`
- `0x140012e3c`
- `0x140015f60`

## callees

- `0x14000457c`
- `0x1400050f0`
- `0x14000e280`
- `0x14000e310`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e325`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e3f4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e325`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e3f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e3b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e4c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e3b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e4c2`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000e459`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000e459`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000e406`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000e406`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e372`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e470`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e4a4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e372`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e470`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e4a4`

## pseudocode

```c
__int64 __fastcall WanpDeleteInterfaceFromIp(char *P)
{
  KSPIN_LOCK *v1; // rbp
  KIRQL v3; // al
  __int64 v4; // rdi
  __int64 *v5; // rsi
  unsigned int v6; // r14d
  KIRQL v7; // si
  bool v8; // zf
  __int64 v9; // rcx
  _QWORD v11[7]; // [rsp+20h] [rbp-38h] BYREF

  v1 = (KSPIN_LOCK *)(P + 56);
  v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)P + 7);
  v4 = *((_QWORD *)P + 3);
  v5 = &WanNmrV4ProviderState;
  if ( !P[20] )
    v5 = &WanNmrV6ProviderState;
  _InterlockedIncrement((volatile signed __int32 *)P + 16);
  if ( *((_QWORD *)P + 11) )
  {
    v11[1] = *((_QWORD *)P + 11);
    v11[0] = WanIpDeleteInterfaceComplete;
    KeReleaseSpinLock(v1, v3);
    v6 = (*(__int64 (__fastcall **)(_QWORD *))(*(_QWORD *)(v5[27] + 8) + 16LL))(v11);
    if ( v6 != 259 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)P + 16, 0xFFFFFFFF) == 1 )
        ExFreePoolWithTag(P, 0);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v5[27] + 32), 0xFFFFFFFE) == 3 )
        WanNmrFinalizeDetach((__int64)v5);
    }
    _InterlockedIncrement(&dword_14000977C[4 * *((int *)P + 27)]);
    v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 120));
    KeAcquireSpinLockAtDpcLevel(v1);
    v8 = *((_DWORD *)P + 27) == 1;
    P[48] = 0;
    *((_QWORD *)P + 11) = 0;
    if ( v8 )
    {
      v9 = *((_QWORD *)P + 3);
      if ( P[20] )
        *(_QWORD *)(v9 + 168) = 0;
      else
        *(_QWORD *)(v9 + 176) = 0;
    }
    if ( *((_DWORD *)P + 27) )
      --*(_DWORD *)(*((_QWORD *)P + 3) + 184LL);
    KeReleaseSpinLockFromDpcLevel(v1);
    KeReleaseSpinLock((PKSPIN_LOCK)(*((_QWORD *)P + 3) + 120LL), v7);
    if ( *((_DWORD *)P + 27) != 2 && _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 128), 0xFFFFFFFF) == 1 )
      WanpDeleteAdapter((PVOID)v4);
  }
  else
  {
    v6 = 0;
    KeReleaseSpinLock(v1, v3);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)P + 16, 0xFFFFFFFF) == 1 )
    ExFreePoolWithTag(P, 0);
  return v6;
}

```

## disassembly

```asm
0x14000e310  push    rbx
0x14000e312  push    rbp
0x14000e313  push    rsi
0x14000e314  push    rdi
0x14000e315  push    r14
0x14000e317  sub     rsp, 30h
0x14000e31b  lea     rbp, [rcx+38h]
0x14000e31f  mov     rbx, rcx
0x14000e322  mov     rcx, rbp; SpinLock
0x14000e325  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000e32c  nop     dword ptr [rax+rax+00h]
0x14000e331  cmp     byte ptr [rbx+14h], 0
0x14000e335  lea     rcx, WanNmrV6ProviderState
0x14000e33c  mov     rdi, [rbx+18h]
0x14000e340  lea     rsi, WanNmrV4ProviderState
0x14000e347  cmovz   rsi, rcx
0x14000e34b  lock inc dword ptr [rbx+40h]
0x14000e34f  mov     rcx, [rbx+58h]
0x14000e353  test    rcx, rcx
0x14000e356  jz      loc_14000E49C
0x14000e35c  lea     rdx, WanIpDeleteInterfaceComplete
0x14000e363  mov     [rsp+58h+var_30], rcx
0x14000e368  mov     [rsp+58h+var_38], rdx
0x14000e36d  mov     rcx, rbp; SpinLock
0x14000e370  mov     dl, al; NewIrql
0x14000e372  call    cs:__imp_KeReleaseSpinLock
0x14000e379  nop     dword ptr [rax+rax+00h]
0x14000e37e  mov     rax, [rsi+0D8h]
0x14000e385  mov     rcx, [rax+8]
0x14000e389  mov     rax, [rcx+10h]
0x14000e38d  lea     rcx, [rsp+58h+var_38]
0x14000e392  call    _guard_dispatch_icall
0x14000e397  mov     r14d, eax
0x14000e39a  cmp     eax, 103h
0x14000e39f  jz      short loc_14000E3DD
0x14000e3a1  or      ecx, 0FFFFFFFFh
0x14000e3a4  lock xadd [rbx+40h], ecx
0x14000e3a9  cmp     ecx, 1
0x14000e3ac  jnz     short loc_14000E3BF
0x14000e3ae  xor     edx, edx; Tag
0x14000e3b0  mov     rcx, rbx; P
0x14000e3b3  call    cs:__imp_ExFreePoolWithTag
0x14000e3ba  nop     dword ptr [rax+rax+00h]
0x14000e3bf  mov     rdx, [rsi+0D8h]
0x14000e3c6  mov     eax, 0FFFFFFFEh
0x14000e3cb  lock xadd [rdx+20h], eax
0x14000e3d0  cmp     eax, 3
0x14000e3d3  jnz     short loc_14000E3DD
0x14000e3d5  mov     rcx, rsi
0x14000e3d8  call    WanNmrFinalizeDetach
0x14000e3dd  movsxd  rax, dword ptr [rbx+6Ch]
0x14000e3e1  lea     rcx, dword_14000977C
0x14000e3e8  shl     rax, 4
0x14000e3ec  lock inc dword ptr [rax+rcx]
0x14000e3f0  lea     rcx, [rdi+78h]; SpinLock
0x14000e3f4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000e3fb  nop     dword ptr [rax+rax+00h]
0x14000e400  mov     rcx, rbp; SpinLock
0x14000e403  mov     sil, al
0x14000e406  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000e40d  nop     dword ptr [rax+rax+00h]
0x14000e412  cmp     dword ptr [rbx+6Ch], 1
0x14000e416  mov     byte ptr [rbx+30h], 0
0x14000e41a  mov     qword ptr [rbx+58h], 0
0x14000e422  jnz     short loc_14000E446
0x14000e424  cmp     byte ptr [rbx+14h], 0
0x14000e428  mov     rcx, [rbx+18h]
0x14000e42c  jz      short loc_14000E43B
0x14000e42e  mov     qword ptr [rcx+0A8h], 0
0x14000e439  jmp     short loc_14000E446
0x14000e43b  mov     qword ptr [rcx+0B0h], 0
0x14000e446  cmp     dword ptr [rbx+6Ch], 0
0x14000e44a  jz      short loc_14000E456
0x14000e44c  mov     rax, [rbx+18h]
0x14000e450  dec     dword ptr [rax+0B8h]
0x14000e456  mov     rcx, rbp; SpinLock
0x14000e459  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000e460  nop     dword ptr [rax+rax+00h]
0x14000e465  mov     rcx, [rbx+18h]
0x14000e469  mov     dl, sil; NewIrql
0x14000e46c  add     rcx, 78h ; 'x'; SpinLock
0x14000e470  call    cs:__imp_KeReleaseSpinLock
0x14000e477  nop     dword ptr [rax+rax+00h]
0x14000e47c  cmp     dword ptr [rbx+6Ch], 2
0x14000e480  jz      short loc_14000E4B0
0x14000e482  or      eax, 0FFFFFFFFh
0x14000e485  lock xadd [rdi+80h], eax
0x14000e48d  cmp     eax, 1
0x14000e490  jnz     short loc_14000E4B0
0x14000e492  mov     rcx, rdi; P
0x14000e495  call    WanpDeleteAdapter
0x14000e49a  jmp     short loc_14000E4B0
0x14000e49c  xor     r14d, r14d
0x14000e49f  mov     dl, al; NewIrql
0x14000e4a1  mov     rcx, rbp; SpinLock
0x14000e4a4  call    cs:__imp_KeReleaseSpinLock
0x14000e4ab  nop     dword ptr [rax+rax+00h]
0x14000e4b0  or      eax, 0FFFFFFFFh
0x14000e4b3  lock xadd [rbx+40h], eax
0x14000e4b8  cmp     eax, 1
0x14000e4bb  jnz     short loc_14000E4CE
0x14000e4bd  xor     edx, edx; Tag
0x14000e4bf  mov     rcx, rbx; P
0x14000e4c2  call    cs:__imp_ExFreePoolWithTag
0x14000e4c9  nop     dword ptr [rax+rax+00h]
0x14000e4ce  mov     eax, r14d
0x14000e4d1  add     rsp, 30h
0x14000e4d5  pop     r14
0x14000e4d7  pop     rdi
0x14000e4d8  pop     rsi
0x14000e4d9  pop     rbp
0x14000e4da  pop     rbx
0x14000e4db  retn
```
