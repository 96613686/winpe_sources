# SqospRemoveFlow

- ea: `0x140004a8c`
- end: `0x140004b34`
- name: `SqospRemoveFlow`
- size: `168`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140011c5c`

## callees

- `0x140003910`
- `0x140004a8c`
- `0x140004be4`
- `0x1400110c4`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140004b00`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004b00`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004aa1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004aa1`

## pseudocode

```c
void __fastcall SqospRemoveFlow(KSPIN_LOCK *SpinLock, __int64 a2)
{
  __int64 Flow; // rax
  _QWORD *v5; // rbx
  _QWORD *v6; // rax
  __int64 v7; // rcx
  _QWORD *v8; // rdx

  *((_BYTE *)SpinLock + 8) = KeAcquireSpinLockRaiseToDpc(SpinLock);
  Flow = SqospFindFlow(SpinLock, a2);
  v5 = (_QWORD *)Flow;
  if ( Flow )
  {
    v6 = (_QWORD *)(Flow + 40);
    v7 = *v6;
    if ( *(_QWORD **)(*v6 + 8LL) != v6 || (v8 = (_QWORD *)v6[1], (_QWORD *)*v8 != v6) )
      __fastfail(3u);
    *v8 = v7;
    *(_QWORD *)(v7 + 8) = v8;
    v5[6] = 0;
    *v6 = 0;
    --*((_DWORD *)SpinLock + 30);
    BalanceFinalizeFlow(v5);
  }
  KeReleaseSpinLock(SpinLock, *((_BYTE *)SpinLock + 8));
  if ( v5 )
    SqospCleanupFlow(v5, a2);
}

```

## disassembly

```asm
0x140004a8c  mov     [rsp+arg_0], rbx
0x140004a91  mov     [rsp+arg_8], rsi
0x140004a96  push    rdi
0x140004a97  sub     rsp, 20h
0x140004a9b  mov     rsi, rdx
0x140004a9e  mov     rdi, rcx
0x140004aa1  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004aa8  nop     dword ptr [rax+rax+00h]
0x140004aad  mov     rdx, rsi
0x140004ab0  mov     rcx, rdi
0x140004ab3  mov     [rdi+8], al
0x140004ab6  call    SqospFindFlow
0x140004abb  mov     rbx, rax
0x140004abe  test    rax, rax
0x140004ac1  jz      short loc_140004AFA
0x140004ac3  add     rax, 28h ; '('
0x140004ac7  mov     rcx, [rax]
0x140004aca  cmp     [rcx+8], rax
0x140004ace  jnz     short loc_140004B2D
0x140004ad0  mov     rdx, [rax+8]
0x140004ad4  cmp     [rdx], rax
0x140004ad7  jnz     short loc_140004B2D
0x140004ad9  mov     [rdx], rcx
0x140004adc  mov     [rcx+8], rdx
0x140004ae0  mov     rcx, rbx
0x140004ae3  mov     qword ptr [rbx+30h], 0
0x140004aeb  mov     qword ptr [rax], 0
0x140004af2  dec     dword ptr [rdi+78h]
0x140004af5  call    BalanceFinalizeFlow
0x140004afa  mov     dl, [rdi+8]; NewIrql
0x140004afd  mov     rcx, rdi; SpinLock
0x140004b00  call    cs:__imp_KeReleaseSpinLock
0x140004b07  nop     dword ptr [rax+rax+00h]
0x140004b0c  test    rbx, rbx
0x140004b0f  jz      short loc_140004B1C
0x140004b11  mov     rdx, rsi
0x140004b14  mov     rcx, rbx; Entry
0x140004b17  call    SqospCleanupFlow
0x140004b1c  mov     rbx, [rsp+28h+arg_0]
0x140004b21  mov     rsi, [rsp+28h+arg_8]
0x140004b26  add     rsp, 20h
0x140004b2a  pop     rdi
0x140004b2b  retn
0x140004b2d  mov     ecx, 3
0x140004b32  int     29h; Win8: RtlFailFast(ecx)
```
