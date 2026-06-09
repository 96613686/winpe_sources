# WinHvCreateServicePartition

- ea: `0x14001f740`
- end: `0x14001f87e`
- name: `WinHvCreateServicePartition`
- size: `318`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task`

## callees

- `0x14001e2a0`
- `0x14001f2d0`
- `0x14001f740`
- `0x14001fb40`
- `0x1400202cc`

## import_xrefs

- `HAL!KeQueryPerformanceCounter` at `0x14001f83f`
- `HAL!KeQueryPerformanceCounter` at `0x14001f83f`

## pseudocode

```c
__int64 __fastcall WinHvCreateServicePartition(__int64 a1, unsigned __int64 *a2)
{
  char v4; // bp
  __int64 v5; // r8
  __int64 (__fastcall *v6)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD); // rdx
  __int64 v7; // r10
  int Partition; // edi
  __int64 v9; // rbx
  __int128 v11; // [rsp+60h] [rbp-48h] BYREF
  __int64 v12; // [rsp+70h] [rbp-38h]

  v11 = 0;
  v12 = 0;
  v4 = 0;
  WinHvpCreateBlackbox();
  if ( *(_BYTE *)a1 )
  {
    v5 = 0;
    v6 = WinHvLowMemoryPolicyAutoDeposit;
    a2 = (unsigned __int64 *)(a1 + 8);
    v7 = 4;
  }
  else
  {
    v6 = *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))(a1 + 24);
    v7 = 0;
    v5 = *(_QWORD *)(a1 + 32);
  }
  Partition = WinHvCreatePartitionEx(
                0,
                v7,
                0x80000000,
                1546,
                (__int64)&v11,
                0,
                a2,
                *(_QWORD *)((*(_BYTE *)a1 != 0 ? 8 : 0) + a1 + 8),
                *(_QWORD *)((*(_BYTE *)a1 != 0 ? 8 : 0) + a1 + 16),
                (__int64)v6,
                v5);
  if ( Partition >= 0 && !*(_BYTE *)a1 )
  {
    Partition = WinHvInitializePartition(*a2);
    v4 = 1;
  }
  if ( *(_QWORD *)&WinHvpBlackbox )
  {
    v9 = 2LL * (_InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&WinHvpBlackbox + 4LL), 1u) & 0x3F);
    *(_DWORD *)(*(_QWORD *)&WinHvpBlackbox + 8 * v9 + 8) = 1;
    *(_DWORD *)(*(_QWORD *)&WinHvpBlackbox + 8 * v9 + 12) = Partition;
    *(LARGE_INTEGER *)(*(_QWORD *)&WinHvpBlackbox + 8 * v9 + 16) = KeQueryPerformanceCounter(0);
  }
  if ( Partition < 0 && v4 )
    WinHvpDeletePartition(*a2, (__int64 (__fastcall *)(unsigned __int64))WinHvWithdrawAllMemory);
  return (unsigned int)Partition;
}

```

## disassembly

```asm
0x14001f740  push    rbx
0x14001f742  push    rbp
0x14001f743  push    rsi
0x14001f744  push    rdi
0x14001f745  sub     rsp, 88h
0x14001f74c  xorps   xmm0, xmm0
0x14001f74f  xor     eax, eax
0x14001f751  movups  [rsp+0A8h+var_48], xmm0
0x14001f756  mov     [rsp+0A8h+var_38], rax
0x14001f75b  mov     rsi, rdx
0x14001f75e  mov     rbx, rcx
0x14001f761  xor     bpl, bpl
0x14001f764  call    WinHvpCreateBlackbox
0x14001f769  mov     cl, [rbx]
0x14001f76b  test    cl, cl
0x14001f76d  jz      short loc_14001F783
0x14001f76f  xor     r8d, r8d
0x14001f772  lea     rdx, WinHvLowMemoryPolicyAutoDeposit
0x14001f779  lea     rsi, [rbx+8]
0x14001f77d  lea     r10d, [r8+4]
0x14001f781  jmp     short loc_14001F78E
0x14001f783  mov     rdx, [rbx+18h]
0x14001f787  xor     r10d, r10d
0x14001f78a  mov     r8, [rbx+20h]
0x14001f78e  mov     [rsp+0A8h+var_58], r8
0x14001f793  mov     al, cl
0x14001f795  neg     al
0x14001f797  mov     [rsp+0A8h+var_60], rdx
0x14001f79c  mov     r9d, 60Ah
0x14001f7a2  mov     r8d, 80000000h
0x14001f7a8  sbb     rax, rax
0x14001f7ab  mov     rdx, r10
0x14001f7ae  and     eax, 8
0x14001f7b1  neg     cl
0x14001f7b3  sbb     rcx, rcx
0x14001f7b6  mov     rax, [rax+rbx+10h]
0x14001f7bb  and     ecx, 8
0x14001f7be  mov     [rsp+0A8h+var_68], rax
0x14001f7c3  mov     rax, [rcx+rbx+8]
0x14001f7c8  mov     ecx, 2480600h
0x14001f7cd  mov     [rsp+0A8h+var_70], rax
0x14001f7d2  lea     rax, [rsp+0A8h+var_48]
0x14001f7d7  mov     [rsp+0A8h+var_78], rsi
0x14001f7dc  mov     [rsp+0A8h+var_80], 0
0x14001f7e5  mov     [rsp+0A8h+var_88], rax
0x14001f7ea  call    WinHvCreatePartitionEx
0x14001f7ef  mov     edi, eax
0x14001f7f1  test    eax, eax
0x14001f7f3  js      short loc_14001F807
0x14001f7f5  cmp     [rbx], bpl
0x14001f7f8  jnz     short loc_14001F807
0x14001f7fa  mov     rcx, [rsi]
0x14001f7fd  call    WinHvInitializePartition
0x14001f802  mov     edi, eax
0x14001f804  mov     bpl, 1
0x14001f807  mov     rcx, cs:WinHvpBlackbox
0x14001f80e  test    rcx, rcx
0x14001f811  jz      short loc_14001F857
0x14001f813  mov     ebx, 1
0x14001f818  lock xadd [rcx+4], ebx
0x14001f81d  mov     rax, cs:WinHvpBlackbox
0x14001f824  and     ebx, 3Fh
0x14001f827  add     rbx, rbx
0x14001f82a  xor     ecx, ecx; PerformanceFrequency
0x14001f82c  mov     dword ptr [rax+rbx*8+8], 1
0x14001f834  mov     rax, cs:WinHvpBlackbox
0x14001f83b  mov     [rax+rbx*8+0Ch], edi
0x14001f83f  call    cs:__imp_KeQueryPerformanceCounter
0x14001f846  nop     dword ptr [rax+rax+00h]
0x14001f84b  mov     rdx, cs:WinHvpBlackbox
0x14001f852  mov     [rdx+rbx*8+10h], rax
0x14001f857  test    edi, edi
0x14001f859  jns     short loc_14001F86F
0x14001f85b  test    bpl, bpl
0x14001f85e  jz      short loc_14001F86F
0x14001f860  mov     rcx, [rsi]
0x14001f863  lea     rdx, WinHvWithdrawAllMemory
0x14001f86a  call    WinHvpDeletePartition
0x14001f86f  mov     eax, edi
0x14001f871  add     rsp, 88h
0x14001f878  pop     rdi
0x14001f879  pop     rsi
0x14001f87a  pop     rbp
0x14001f87b  pop     rbx
0x14001f87c  retn
```
