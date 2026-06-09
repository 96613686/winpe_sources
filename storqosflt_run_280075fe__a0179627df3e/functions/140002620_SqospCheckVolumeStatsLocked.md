# SqospCheckVolumeStatsLocked

- ea: `0x140002620`
- end: `0x14000277e`
- name: `SqospCheckVolumeStatsLocked`
- size: `350`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140002300`
- `0x140003f00`

## callees

- `0x140002620`
- `0x140004c50`
- `0x1400077c8`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000272b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000272b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400026c0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400026c0`

## pseudocode

```c
char __fastcall SqospCheckVolumeStatsLocked(__int64 a1)
{
  unsigned __int64 v2; // rdi
  __int64 *v3; // r15
  __int64 *v4; // r14
  __int64 v5; // rsi
  KIRQL v6; // al
  bool v7; // zf

  if ( *(_BYTE *)(a1 + 185) || !ClientPort || *(_DWORD *)(a1 + 188) != 2 )
    return 0;
  v2 = MEMORY[0xFFFFF78000000008];
  if ( !*(_BYTE *)(a1 + 4312) && MEMORY[0xFFFFF78000000008] >= (unsigned __int64)(*(_QWORD *)(a1 + 4304) + 40000000LL) )
  {
    v3 = (__int64 *)(a1 + 896);
    v4 = *(__int64 **)(a1 + 896);
    *(_BYTE *)(a1 + 4312) = 1;
    if ( v4 != (__int64 *)(a1 + 896) )
    {
      do
      {
        v5 = *(v4 - 2);
        v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v5);
        v7 = (*(_DWORD *)(v5 + 132) & 0xFFFFFFFD) == 0;
        *(_BYTE *)(v5 + 8) = v6;
        if ( v7 )
        {
          *(_DWORD *)(v5 + 128) = 0;
          *(_QWORD *)(v5 + 200) = 0;
          *(_QWORD *)(v5 + 208) = 0;
          *(_QWORD *)(v5 + 216) = 0;
          BalanceSetFlowMinimumIoRate(v4 - 3, 0);
          v4[54] = 0;
          _InterlockedExchange64(v4 + 60, 0);
          v4[55] = 0;
          _InterlockedExchange64(v4 + 61, 0);
        }
        KeReleaseSpinLock((PKSPIN_LOCK)v5, *(_BYTE *)(v5 + 8));
        v4 = (__int64 *)*v4;
      }
      while ( v4 != v3 );
    }
  }
  if ( v2 < *(_QWORD *)(a1 + 4296) )
    return 0;
  SqospMarkDeviceForStatsNotification(a1, v2);
  return 1;
}

```

## disassembly

```asm
0x140002620  push    rbx
0x140002622  push    rdi
0x140002623  sub     rsp, 28h
0x140002627  movzx   eax, byte ptr [rcx+0B9h]
0x14000262e  mov     rbx, rcx
0x140002631  test    al, al
0x140002633  jnz     loc_140002774
0x140002639  cmp     cs:ClientPort, 0
0x140002641  jz      loc_140002774
0x140002647  cmp     dword ptr [rcx+0BCh], 2
0x14000264e  jnz     loc_140002774
0x140002654  mov     rdi, 0FFFFF78000000008h
0x14000265e  mov     rdi, [rdi]
0x140002661  cmp     [rcx+10D8h], al
0x140002667  jnz     loc_14000275C
0x14000266d  mov     rax, [rcx+10D0h]
0x140002674  add     rax, 2625A00h
0x14000267a  cmp     rdi, rax
0x14000267d  jb      loc_14000275C
0x140002683  mov     [rsp+38h+arg_18], r14
0x140002688  mov     [rsp+38h+var_18], r15
0x14000268d  lea     r15, [rcx+380h]
0x140002694  mov     r14, [r15]
0x140002697  mov     byte ptr [rcx+10D8h], 1
0x14000269e  cmp     r14, r15
0x1400026a1  jz      loc_140002752
0x1400026a7  mov     [rsp+38h+arg_0], rbp
0x1400026ac  mov     [rsp+38h+arg_8], rsi
0x1400026b1  mov     [rsp+38h+arg_10], r12
0x1400026b6  xor     r12d, r12d
0x1400026b9  mov     rsi, [r14-10h]
0x1400026bd  mov     rcx, rsi; SpinLock
0x1400026c0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400026c7  nop     dword ptr [rax+rax+00h]
0x1400026cc  test    dword ptr [rsi+84h], 0FFFFFFFDh
0x1400026d6  mov     [rsi+8], al
0x1400026d9  jnz     short loc_140002724
0x1400026db  xor     edx, edx
0x1400026dd  mov     [rsi+80h], r12d
0x1400026e4  lea     rcx, [r14-18h]
0x1400026e8  mov     [rsi+0C8h], r12
0x1400026ef  mov     [rsi+0D0h], r12
0x1400026f6  mov     [rsi+0D8h], r12
0x1400026fd  call    BalanceSetFlowMinimumIoRate
0x140002702  mov     [r14+1B0h], r12
0x140002709  mov     rax, r12
0x14000270c  xchg    rax, [r14+1E0h]
0x140002713  mov     rax, r12
0x140002716  mov     [r14+1B8h], r12
0x14000271d  xchg    rax, [r14+1E8h]
0x140002724  movzx   edx, byte ptr [rsi+8]; NewIrql
0x140002728  mov     rcx, rsi; SpinLock
0x14000272b  call    cs:__imp_KeReleaseSpinLock
0x140002732  nop     dword ptr [rax+rax+00h]
0x140002737  mov     r14, [r14]
0x14000273a  cmp     r14, r15
0x14000273d  jnz     loc_1400026B9
0x140002743  mov     r12, [rsp+38h+arg_10]
0x140002748  mov     rsi, [rsp+38h+arg_8]
0x14000274d  mov     rbp, [rsp+38h+arg_0]
0x140002752  mov     r14, [rsp+38h+arg_18]
0x140002757  mov     r15, [rsp+38h+var_18]
0x14000275c  cmp     rdi, [rbx+10C8h]
0x140002763  jb      short loc_140002774
0x140002765  mov     rdx, rdi
0x140002768  mov     rcx, rbx
0x14000276b  call    SqospMarkDeviceForStatsNotification
0x140002770  mov     al, 1
0x140002772  jmp     short loc_140002776
0x140002774  xor     al, al
0x140002776  add     rsp, 28h
0x14000277a  pop     rdi
0x14000277b  pop     rbx
0x14000277c  retn
```
