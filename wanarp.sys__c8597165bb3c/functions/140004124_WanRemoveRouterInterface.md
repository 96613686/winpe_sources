# WanRemoveRouterInterface

- ea: `0x140004124`
- end: `0x1400042ce`
- name: `WanRemoveRouterInterface`
- size: `426`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140002510`
- `0x1400120fc`

## callees

- `0x140004124`
- `0x14000e4e4`
- `0x140013dd4`
- `0x140013df4`
- `0x140014c7c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004141`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004259`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004141`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004259`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004249`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004249`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140004178`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400041c8`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400041d7`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140004178`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400041c8`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400041d7`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000415a`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000415a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000418a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004211`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000418a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004211`

## pseudocode

```c
__int64 __fastcall WanRemoveRouterInterface(unsigned int a1)
{
  KIRQL v2; // si
  _QWORD *InterfaceGivenIndex; // rax
  _QWORD *v4; // rdi
  unsigned int v5; // r14d
  __int64 v6; // rcx
  _QWORD *v7; // rax
  unsigned int *v8; // r15
  unsigned int v9; // ebp
  int v10; // ebx

  v2 = KeAcquireSpinLockRaiseToDpc(&g_rwlIfLock);
  KeAcquireSpinLockAtDpcLevel(&qword_140009C48);
  InterfaceGivenIndex = (_QWORD *)WanpFindInterfaceGivenIndex(a1);
  v4 = InterfaceGivenIndex;
  if ( InterfaceGivenIndex )
  {
    v6 = *InterfaceGivenIndex;
    if ( *(_QWORD **)(*InterfaceGivenIndex + 8LL) != InterfaceGivenIndex
      || (v7 = (_QWORD *)InterfaceGivenIndex[1], (_QWORD *)*v7 != v4) )
    {
      __fastfail(3u);
    }
    *v7 = v6;
    v5 = 0;
    *(_QWORD *)(v6 + 8) = v7;
    KeReleaseSpinLockFromDpcLevel(&qword_140009C48);
    KeReleaseSpinLockFromDpcLevel(&g_rwlIfLock);
    v8 = (unsigned int *)v4[19];
    if ( v8 )
    {
      v9 = *v8;
      v10 = *((_DWORD *)v4 + 40);
      v4[19] = 0;
      *((_DWORD *)v4 + 40) = 0;
      KeReleaseSpinLock(v4 + 7, v2);
      WanpRemoveSubnetFilters(v8, v10);
      while ( v9 )
      {
        --v9;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v4 + 16, 0xFFFFFFFF) == 1 )
          WanpDeleteInterface(v4);
      }
      ExFreePoolWithTag(v8, 0);
      KeAcquireSpinLockRaiseToDpc(v4 + 7);
    }
    WanpDeleteRouterInterface(v4);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v4 + 16, 0xFFFFFFFF) == 1 )
      WanpDeleteInterface(v4);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v4 + 16, 0xFFFFFFFF) == 1 )
      WanpDeleteInterface(v4);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v4 + 16, 0xFFFFFFFF) == 1 )
      WanpDeleteInterface(v4);
  }
  else
  {
    KeReleaseSpinLockFromDpcLevel(&qword_140009C48);
    KeReleaseSpinLock(&g_rwlIfLock, v2);
    return (unsigned int)-1073741772;
  }
  return v5;
}

```

## disassembly

```asm
0x140004124  push    rbx
0x140004126  push    rbp
0x140004127  push    rsi
0x140004128  push    rdi
0x140004129  push    r12
0x14000412b  push    r13
0x14000412d  push    r14
0x14000412f  push    r15
0x140004131  sub     rsp, 28h
0x140004135  mov     ebx, ecx
0x140004137  lea     rbp, g_rwlIfLock
0x14000413e  mov     rcx, rbp; SpinLock
0x140004141  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004148  nop     dword ptr [rax+rax+00h]
0x14000414d  lea     r15, qword_140009C48
0x140004154  mov     sil, al
0x140004157  mov     rcx, r15; SpinLock
0x14000415a  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140004161  nop     dword ptr [rax+rax+00h]
0x140004166  mov     ecx, ebx
0x140004168  call    WanpFindInterfaceGivenIndex
0x14000416d  mov     rdi, rax
0x140004170  test    rax, rax
0x140004173  jnz     short loc_1400041A1
0x140004175  mov     rcx, r15; SpinLock
0x140004178  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000417f  nop     dword ptr [rax+rax+00h]
0x140004184  mov     dl, sil; NewIrql
0x140004187  mov     rcx, rbp; SpinLock
0x14000418a  call    cs:__imp_KeReleaseSpinLock
0x140004191  nop     dword ptr [rax+rax+00h]
0x140004196  mov     r14d, 0C0000034h
0x14000419c  jmp     loc_1400042B2
0x1400041a1  mov     rcx, [rax]
0x1400041a4  cmp     [rcx+8], rdi
0x1400041a8  jnz     loc_1400042C7
0x1400041ae  mov     rax, [rax+8]
0x1400041b2  cmp     [rax], rdi
0x1400041b5  jnz     loc_1400042C7
0x1400041bb  mov     [rax], rcx
0x1400041be  xor     r14d, r14d
0x1400041c1  mov     [rcx+8], rax
0x1400041c5  mov     rcx, r15; SpinLock
0x1400041c8  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400041cf  nop     dword ptr [rax+rax+00h]
0x1400041d4  mov     rcx, rbp; SpinLock
0x1400041d7  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400041de  nop     dword ptr [rax+rax+00h]
0x1400041e3  mov     r15, [rdi+98h]
0x1400041ea  or      r13d, 0FFFFFFFFh
0x1400041ee  test    r15, r15
0x1400041f1  jz      short loc_140004268
0x1400041f3  mov     ebp, [r15]
0x1400041f6  lea     rcx, [rdi+38h]; SpinLock
0x1400041fa  mov     ebx, [rdi+0A0h]
0x140004200  mov     dl, sil; NewIrql
0x140004203  mov     [rdi+98h], r14
0x14000420a  mov     [rdi+0A0h], r14d
0x140004211  call    cs:__imp_KeReleaseSpinLock
0x140004218  nop     dword ptr [rax+rax+00h]
0x14000421d  mov     edx, ebx
0x14000421f  mov     rcx, r15
0x140004222  call    WanpRemoveSubnetFilters
0x140004227  jmp     short loc_140004240
0x140004229  dec     ebp
0x14000422b  mov     eax, r13d
0x14000422e  lock xadd [rdi+40h], eax
0x140004233  add     eax, r13d
0x140004236  jnz     short loc_140004240
0x140004238  mov     rcx, rdi
0x14000423b  call    WanpDeleteInterface
0x140004240  test    ebp, ebp
0x140004242  jnz     short loc_140004229
0x140004244  xor     edx, edx; Tag
0x140004246  mov     rcx, r15; P
0x140004249  call    cs:__imp_ExFreePoolWithTag
0x140004250  nop     dword ptr [rax+rax+00h]
0x140004255  lea     rcx, [rdi+38h]; SpinLock
0x140004259  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004260  nop     dword ptr [rax+rax+00h]
0x140004265  mov     sil, al
0x140004268  mov     dl, sil
0x14000426b  mov     rcx, rdi; P
0x14000426e  call    WanpDeleteRouterInterface
0x140004273  mov     eax, r13d
0x140004276  lock xadd [rdi+40h], eax
0x14000427b  add     eax, r13d
0x14000427e  jnz     short loc_140004288
0x140004280  mov     rcx, rdi
0x140004283  call    WanpDeleteInterface
0x140004288  mov     eax, r13d
0x14000428b  lock xadd [rdi+40h], eax
0x140004290  add     eax, r13d
0x140004293  jnz     short loc_14000429D
0x140004295  mov     rcx, rdi
0x140004298  call    WanpDeleteInterface
0x14000429d  mov     edx, r13d
0x1400042a0  lock xadd [rdi+40h], edx
0x1400042a5  add     edx, r13d
0x1400042a8  jnz     short loc_1400042B2
0x1400042aa  mov     rcx, rdi
0x1400042ad  call    WanpDeleteInterface
0x1400042b2  mov     eax, r14d
0x1400042b5  add     rsp, 28h
0x1400042b9  pop     r15
0x1400042bb  pop     r14
0x1400042bd  pop     r13
0x1400042bf  pop     r12
0x1400042c1  pop     rdi
0x1400042c2  pop     rsi
0x1400042c3  pop     rbp
0x1400042c4  pop     rbx
0x1400042c5  retn
0x1400042c7  mov     ecx, 3
0x1400042cc  int     29h; Win8: RtlFailFast(ecx)
```
