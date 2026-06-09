# WinHvpReferenceVp

- ea: `0x1400025e0`
- end: `0x1400026bb`
- name: `WinHvpReferenceVp`
- size: `219`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1400096b0`
- `0x14000b060`
- `0x140023ba0`
- `0x140023c00`
- `0x14002648c`

## callees

- `0x1400025e0`
- `0x140002bf0`
- `0x140007828`

## import_xrefs

- `ntoskrnl!ExAcquireSpinLockShared` at `0x14000261e`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x14000261e`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x140002657`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x140002657`

## pseudocode

```c
__int64 __fastcall WinHvpReferenceVp(unsigned __int64 a1, unsigned int a2, _QWORD *a3)
{
  __int64 v4; // rsi
  volatile signed __int64 *v5; // rax
  __int64 v6; // rbx
  unsigned int v7; // edi
  KIRQL v8; // al
  __int64 v9; // r8
  signed __int64 v10; // rdx
  bool v11; // cc
  signed __int64 v12; // rdx

  v4 = a2;
  v5 = WinHvpReferencePartition(a1);
  v6 = (__int64)v5;
  if ( !v5 )
    return 3224698893LL;
  v7 = -1070268402;
  if ( (unsigned int)v4 < *((_DWORD *)v5 + 18) )
  {
    v8 = ExAcquireSpinLockShared((PEX_SPIN_LOCK)v5 + 20);
    v9 = *(_QWORD *)(*(_QWORD *)(v6 + 64) + 8 * v4);
    if ( v9 )
    {
      if ( _InterlockedIncrement64((volatile signed __int64 *)(v9 + 16)) <= 1 )
        __fastfail(0xEu);
      *a3 = v9;
      v7 = 0;
    }
    ExReleaseSpinLockShared((PEX_SPIN_LOCK)(v6 + 80), v8);
  }
  v10 = _InterlockedExchangeAdd64((volatile signed __int64 *)v6, 0xFFFFFFFFFFFFFFFFuLL);
  v11 = v10 <= 1;
  v12 = v10 - 1;
  if ( v11 )
  {
    if ( v12 )
      __fastfail(0xEu);
    WinHvpDeletePartitionObject(v6);
  }
  return v7;
}

```

## disassembly

```asm
0x1400025e0  mov     [rsp+arg_10], rbx
0x1400025e5  mov     [rsp+arg_18], rsi
0x1400025ea  push    r14
0x1400025ec  sub     rsp, 20h
0x1400025f0  mov     r14, r8
0x1400025f3  mov     esi, edx
0x1400025f5  call    WinHvpReferencePartition
0x1400025fa  mov     rbx, rax
0x1400025fd  test    rax, rax
0x140002600  jz      loc_1400026B4
0x140002606  mov     [rsp+28h+arg_8], rdi
0x14000260b  mov     edi, 0C035000Eh
0x140002610  cmp     esi, [rax+48h]
0x140002613  jnb     short loc_140002668
0x140002615  lea     rcx, [rax+50h]; SpinLock
0x140002619  mov     [rsp+28h+arg_0], rbp
0x14000261e  call    cs:__imp_ExAcquireSpinLockShared
0x140002625  nop     dword ptr [rax+rax+00h]
0x14000262a  mov     rcx, [rbx+40h]
0x14000262e  mov     r8, [rcx+rsi*8]
0x140002632  test    r8, r8
0x140002635  jz      short loc_140002650
0x140002637  mov     edx, 1
0x14000263c  lock xadd [r8+10h], rdx
0x140002642  inc     rdx
0x140002645  cmp     rdx, 1
0x140002649  jle     short loc_1400026A1
0x14000264b  mov     [r14], r8
0x14000264e  xor     edi, edi
0x140002650  movzx   edx, al; OldIrql
0x140002653  lea     rcx, [rbx+50h]; SpinLock
0x140002657  call    cs:__imp_ExReleaseSpinLockShared
0x14000265e  nop     dword ptr [rax+rax+00h]
0x140002663  mov     rbp, [rsp+28h+arg_0]
0x140002668  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x14000266f  lock xadd [rbx], rdx
0x140002674  sub     rdx, 1
0x140002678  jle     short loc_140002693
0x14000267a  mov     eax, edi
0x14000267c  mov     rdi, [rsp+28h+arg_8]
0x140002681  mov     rbx, [rsp+28h+arg_10]
0x140002686  mov     rsi, [rsp+28h+arg_18]
0x14000268b  add     rsp, 20h
0x14000268f  pop     r14
0x140002691  retn
0x140002693  test    rdx, rdx
0x140002696  jz      short loc_1400026AA
0x140002698  mov     ecx, 0Eh
0x14000269d  int     29h; Win8: RtlFailFast(ecx)
0x14000269f  jmp     short loc_14000267A
0x1400026a1  mov     ecx, 0Eh
0x1400026a6  int     29h; Win8: RtlFailFast(ecx)
0x1400026a8  jmp     short loc_14000264B
0x1400026aa  mov     rcx, rbx
0x1400026ad  call    WinHvpDeletePartitionObject
0x1400026b2  jmp     short loc_14000267A
0x1400026b4  mov     eax, 0C035000Dh
0x1400026b9  jmp     short loc_140002681
```
