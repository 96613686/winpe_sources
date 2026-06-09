# OncRpcSepCheckAndUpdateSeqWindow

- ea: `0x14000a6e8`
- end: `0x14000a80b`
- name: `OncRpcSepCheckAndUpdateSeqWindow`
- size: `291`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14000b624`

## callees

- `0x14000a6e8`
- `0x14000cf50`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000a714`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000a714`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000a79c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000a79c`

## pseudocode

```c
__int64 __fastcall OncRpcSepCheckAndUpdateSeqWindow(__int64 a1, int a2, _DWORD *a3)
{
  int v6; // ebx
  int v7; // edx
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rdx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+50h] [rbp-48h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  v6 = 0;
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 24), &LockHandle);
  v7 = *(_DWORD *)(a1 + 72);
  if ( v7 == -1 )
  {
    *(_DWORD *)(a1 + 72) = a2;
    *(_QWORD *)(a1 + 80) |= 1uLL;
    goto LABEL_13;
  }
  if ( a2 > v7 )
  {
    v8 = *(_QWORD *)(a1 + 80);
    *(_DWORD *)(a1 + 72) = a2;
    *(_QWORD *)(a1 + 80) = (v8 << ((unsigned __int8)a2 - (unsigned __int8)v7)) | 1;
    goto LABEL_13;
  }
  if ( a2 < v7 - 64 )
  {
    *a3 = 8;
LABEL_11:
    v6 = -1073741270;
    goto LABEL_13;
  }
  if ( a2 == v7 )
  {
    *a3 = 2;
    goto LABEL_11;
  }
  v9 = *(_QWORD *)(a1 + 80);
  v10 = 1LL << ((unsigned __int8)v7 - (unsigned __int8)a2);
  if ( (v10 & v9) != 0 )
  {
    *a3 = 4;
    goto LABEL_11;
  }
  *(_QWORD *)(a1 + 80) = v9 | v10;
LABEL_13:
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_dZdddd(
        WPP_GLOBAL_Control->AttachedDevice,
        *(_DWORD *)(a1 + 72),
        a1 + 160,
        *(_DWORD *)(a1 + 64),
        a1 + 160,
        *(_DWORD *)(a1 + 72),
        a2,
        *a3,
        v6);
  }
  else
  {
    *a3 = 0;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14000a6e8  push    rbx
0x14000a6ea  push    rsi
0x14000a6eb  push    rdi
0x14000a6ec  push    r14
0x14000a6ee  sub     rsp, 78h
0x14000a6f2  mov     esi, edx
0x14000a6f4  mov     rdi, rcx
0x14000a6f7  xorps   xmm0, xmm0
0x14000a6fa  lea     rdx, [rsp+98h+LockHandle]; LockHandle
0x14000a6ff  xor     eax, eax
0x14000a701  add     rcx, 18h; SpinLock
0x14000a705  movups  xmmword ptr [rsp+98h+LockHandle.LockQueue.Next], xmm0
0x14000a70a  mov     qword ptr [rsp+98h+LockHandle.OldIrql], rax
0x14000a70f  mov     r14, r8
0x14000a712  xor     ebx, ebx
0x14000a714  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000a71b  nop     dword ptr [rax+rax+00h]
0x14000a720  mov     edx, [rdi+48h]
0x14000a723  cmp     edx, 0FFFFFFFFh
0x14000a726  jnz     short loc_14000A734
0x14000a728  lea     edx, [rbx+1]
0x14000a72b  mov     [rdi+48h], esi
0x14000a72e  or      [rdi+50h], rdx
0x14000a732  jmp     short loc_14000A797
0x14000a734  cmp     esi, edx
0x14000a736  jle     short loc_14000A750
0x14000a738  mov     rax, [rdi+50h]
0x14000a73c  mov     ecx, esi
0x14000a73e  sub     ecx, edx
0x14000a740  mov     [rdi+48h], esi
0x14000a743  shl     rax, cl
0x14000a746  or      rax, 1
0x14000a74a  mov     [rdi+50h], rax
0x14000a74e  jmp     short loc_14000A797
0x14000a750  lea     eax, [rdx-40h]
0x14000a753  cmp     esi, eax
0x14000a755  jge     short loc_14000A760
0x14000a757  mov     dword ptr [r14], 8
0x14000a75e  jmp     short loc_14000A789
0x14000a760  cmp     esi, edx
0x14000a762  jnz     short loc_14000A76D
0x14000a764  mov     dword ptr [r14], 2
0x14000a76b  jmp     short loc_14000A789
0x14000a76d  mov     rax, [rdi+50h]
0x14000a771  mov     ecx, edx
0x14000a773  sub     ecx, esi
0x14000a775  mov     edx, 1
0x14000a77a  shl     rdx, cl
0x14000a77d  test    rax, rdx
0x14000a780  jz      short loc_14000A790
0x14000a782  mov     dword ptr [r14], 4
0x14000a789  mov     ebx, 0C000022Ah
0x14000a78e  jmp     short loc_14000A797
0x14000a790  or      rdx, rax
0x14000a793  mov     [rdi+50h], rdx
0x14000a797  lea     rcx, [rsp+98h+LockHandle]; LockHandle
0x14000a79c  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000a7a3  nop     dword ptr [rax+rax+00h]
0x14000a7a8  test    ebx, ebx
0x14000a7aa  js      short loc_14000A7B5
0x14000a7ac  mov     dword ptr [r14], 0
0x14000a7b3  jmp     short loc_14000A7FE
0x14000a7b5  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a7bc  lea     rax, WPP_GLOBAL_Control
0x14000a7c3  cmp     rcx, rax
0x14000a7c6  jz      short loc_14000A7FE
0x14000a7c8  mov     eax, [rcx+2Ch]
0x14000a7cb  test    al, 40h
0x14000a7cd  jz      short loc_14000A7FE
0x14000a7cf  mov     edx, [r14]
0x14000a7d2  lea     r8, [rdi+0A0h]
0x14000a7d9  mov     r9d, [rdi+40h]
0x14000a7dd  mov     rcx, [rcx+18h]
0x14000a7e1  mov     [rsp+98h+var_58], ebx
0x14000a7e5  mov     [rsp+98h+var_60], edx
0x14000a7e9  mov     edx, [rdi+48h]
0x14000a7ec  mov     [rsp+98h+var_68], esi
0x14000a7f0  mov     [rsp+98h+var_70], edx
0x14000a7f4  mov     [rsp+98h+var_78], r8
0x14000a7f9  call    WPP_SF_dZdddd
0x14000a7fe  mov     eax, ebx
0x14000a800  add     rsp, 78h
0x14000a804  pop     r14
0x14000a806  pop     rdi
0x14000a807  pop     rsi
0x14000a808  pop     rbx
0x14000a809  retn
```
