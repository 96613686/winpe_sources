# WinHvSignalEventWithSchedulerAssist

- ea: `0x140002830`
- end: `0x140002bdf`
- name: `WinHvSignalEventWithSchedulerAssist`
- size: `943`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config`

## callees

- `0x140002830`
- `0x140002bf0`
- `0x140002ce8`
- `0x140007828`
- `0x140009c90`
- `0x14000a040`
- `0x14000b040`
- `0x14001b350`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140002b47`
- `ntoskrnl!KeGetCurrentIrql` at `0x140002b47`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140002898`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140002898`
- `ntoskrnl!ExAcquireFastMutex` at `0x140002b61`
- `ntoskrnl!ExAcquireFastMutex` at `0x140002b61`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002b7d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002b7d`
- `ntoskrnl!HvlInvokeHypercall` at `0x14000292f`
- `ntoskrnl!HvlInvokeHypercall` at `0x14000292f`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140002a98`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140002a98`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140002acb`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140002acb`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x1400029ab`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x1400029ab`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x1400029e9`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x1400029e9`

## pseudocode

```c
__int64 __fastcall WinHvSignalEventWithSchedulerAssist(int a1, unsigned __int16 a2)
{
  __int64 LockArray_high; // rcx
  __int64 v5; // rcx
  __int64 *v6; // r14
  __int64 v7; // rax
  __int64 v8; // r14
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // rcx
  unsigned __int16 v12; // ax
  signed int v13; // r15d
  __int64 v14; // rsi
  char v15; // bl
  __int64 v16; // r13
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rsi
  struct _EX_RUNDOWN_REF *v22; // r14
  int v23; // r12d
  KIRQL v24; // al
  struct _EX_RUNDOWN_REF *v25; // r8
  signed __int64 v26; // rax
  bool v27; // cc
  signed __int64 v28; // rax
  signed __int64 v29; // rbx
  signed __int64 v30; // rbx
  _DWORD v32[2]; // [rsp+38h] [rbp-19h] BYREF
  __int64 v33; // [rsp+40h] [rbp-11h]
  _QWORD v34[12]; // [rsp+48h] [rbp-9h] BYREF

  if ( qword_140016230 )
  {
    memset(v34, 0, 0x40u);
    LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
    v34[5] = 0;
    v5 = *(unsigned __int16 *)(WinHvpProcessorToNode + 2 * LockArray_high);
    LOWORD(v34[4]) = v5;
    v6 = (__int64 *)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(WinHvpNodeToHypercallLookaside + (v5 << 7)));
    v34[5] = v6;
    v34[7] = WinHvpReleasePoolBuffers;
    if ( !v6 )
    {
      LOBYTE(v34[6]) = KeGetCurrentIrql();
      if ( LOBYTE(v34[6]) >= 2u )
      {
        LOBYTE(v34[6]) = KeAcquireSpinLockRaiseToDpc(&WinHvpFallbackSpinLock);
        v6 = WinHvpFallbackBuffer;
      }
      else
      {
        ExAcquireFastMutex(&WinHvpFallbackMutex);
        v6 = WinHvpFallbackBuffer2;
      }
      v34[5] = v6;
      v34[7] = WinHvpReleaseFallbackBuffers;
    }
    v7 = v6[2];
    v34[1] = v7;
    v8 = v6[4];
    v34[0] = v34;
    v34[2] = v8;
    *(_DWORD *)v7 = a1;
    *(_WORD *)(v7 + 4) = a2;
    *(_WORD *)(v7 + 6) = 0;
    if ( *(_BYTE *)(v34[0] + 24LL) )
    {
      v13 = WinHvpSlowHypercallRemote(243, 0, *(_QWORD *)(v34[0] + 8LL), *(_QWORD *)(v34[0] + 16LL), 0);
    }
    else
    {
      if ( *(_QWORD *)(v34[0] + 16LL) )
        v9 = *(_QWORD *)(*(_QWORD *)(v34[0] + 40LL) + 40LL);
      else
        v9 = 0;
      if ( *(_QWORD *)(v34[0] + 8LL) )
        v10 = *(_QWORD *)(*(_QWORD *)(v34[0] + 40LL) + 24LL);
      else
        v10 = 0;
      v11 = 243;
      if ( WinHvpNested )
        v11 = 2147483891LL;
      if ( WinHvpConnected )
      {
        v12 = HvlInvokeHypercall(v11, v10, v9);
        if ( v12 )
          v13 = v12 | 0xC0350000;
        else
          v13 = 0;
      }
      else
      {
        v13 = -1070264320;
      }
    }
    if ( v13 < 0 )
    {
      ((void (__fastcall *)(_QWORD))v34[7])(v34[0]);
    }
    else
    {
      v14 = *(_QWORD *)v8;
      v15 = *(_BYTE *)(v8 + 12);
      v16 = *(unsigned int *)(v8 + 8);
      ((void (__fastcall *)(_QWORD))v34[7])(v34[0]);
      if ( v15 )
      {
        v17 = WinHvpReferencePartition(v14);
        v21 = v17;
        if ( v17 )
        {
          v22 = 0;
          v23 = -1070268402;
          if ( (unsigned int)v16 < *(_DWORD *)(v17 + 72) )
          {
            _mm_lfence();
            v24 = ExAcquireSpinLockShared((PEX_SPIN_LOCK)(v17 + 80));
            v25 = *(struct _EX_RUNDOWN_REF **)(*(_QWORD *)(v21 + 64) + 8 * v16);
            if ( v25 )
            {
              if ( _InterlockedIncrement64((volatile signed __int64 *)&v25[2]) <= 1 )
                __fastfail(0xEu);
              v22 = v25;
              v23 = 0;
            }
            ExReleaseSpinLockShared((PEX_SPIN_LOCK)(v21 + 80), v24);
          }
          v26 = _InterlockedExchangeAdd64((volatile signed __int64 *)v21, 0xFFFFFFFFFFFFFFFFuLL);
          v27 = v26 <= 1;
          v28 = v26 - 1;
          if ( v27 )
          {
            if ( v28 )
              __fastfail(0xEu);
            WinHvpDeletePartitionObject(v21, v18, v19, v20);
          }
          if ( v23 >= 0 && ExAcquireRundownProtection(v22 + 23) )
          {
            ((void (__fastcall *)(__int64, ULONG_PTR))qword_140016230)(1, v22[24].Count);
            ExReleaseRundownProtection(v22 + 23);
          }
          if ( v22 )
          {
            v29 = _InterlockedExchangeAdd64((volatile signed __int64 *)&v22[2], 0xFFFFFFFFFFFFFFFFuLL);
            v27 = v29 <= 1;
            v30 = v29 - 1;
            if ( v27 )
            {
              if ( v30 )
                __fastfail(0xEu);
              WinHvpFreePoolWithTag(v22, 1467369559);
            }
          }
        }
      }
    }
    return (unsigned int)v13;
  }
  else
  {
    v32[0] = a1;
    v32[1] = a2;
    v33 = 0;
    return WinHvpFastHypercall(93, v32);
  }
}

```

## disassembly

```asm
0x140002830  mov     rax, rsp
0x140002833  push    rbp
0x140002834  push    rbx
0x140002835  push    rsi
0x140002836  push    rdi
0x140002837  lea     rbp, [rax-5Fh]
0x14000283b  sub     rsp, 88h
0x140002842  cmp     cs:qword_140016230, 0
0x14000284a  movzx   esi, dx
0x14000284d  mov     ebx, ecx
0x14000284f  jz      loc_140002A58
0x140002855  mov     [rax+18h], r14
0x140002859  lea     rcx, [rbp+57h+var_60]; void *
0x14000285d  xor     edx, edx; Val
0x14000285f  mov     [rax-28h], r15
0x140002863  mov     r8d, 40h ; '@'; Size
0x140002869  call    memset
0x14000286e  mov     eax, gs:1A4h
0x140002876  xor     edi, edi
0x140002878  mov     ecx, eax
0x14000287a  mov     rax, cs:WinHvpProcessorToNode
0x140002881  mov     [rbp+57h+var_38], rdi
0x140002885  movzx   ecx, word ptr [rax+rcx*2]
0x140002889  mov     [rbp+57h+var_40], cx
0x14000288d  shl     rcx, 7
0x140002891  add     rcx, cs:WinHvpNodeToHypercallLookaside; Lookaside
0x140002898  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14000289f  nop     dword ptr [rax+rax+00h]
0x1400028a4  mov     r14, rax
0x1400028a7  mov     [rbp+57h+var_38], rax
0x1400028ab  lea     rax, WinHvpReleasePoolBuffers
0x1400028b2  mov     [rbp+57h+var_28], rax
0x1400028b6  test    r14, r14
0x1400028b9  jz      loc_140002B47
0x1400028bf  mov     rax, [r14+10h]
0x1400028c3  lea     rcx, [rbp+57h+var_60]
0x1400028c7  mov     [rbp+57h+var_58], rax
0x1400028cb  mov     r14, [r14+20h]
0x1400028cf  mov     [rbp+57h+var_60], rcx
0x1400028d3  mov     [rbp+57h+var_50], r14
0x1400028d7  mov     [rax], ebx
0x1400028d9  mov     [rax+4], si
0x1400028dd  mov     [rax+6], di
0x1400028e1  mov     rax, [rbp+57h+var_60]
0x1400028e5  cmp     [rax+18h], dil
0x1400028e9  jnz     loc_140002ADC
0x1400028ef  cmp     [rax+10h], rdi
0x1400028f3  jnz     loc_140002A84
0x1400028f9  mov     r8, rdi
0x1400028fc  cmp     [rax+8], rdi
0x140002900  jz      loc_140002BA7
0x140002906  mov     rdx, [rax+28h]
0x14000290a  mov     rdx, [rdx+18h]
0x14000290e  cmp     cs:WinHvpNested, dil
0x140002915  mov     ecx, 0F3h
0x14000291a  mov     eax, 800000F3h
0x14000291f  cmovnz  ecx, eax
0x140002922  cmp     cs:WinHvpConnected, dil
0x140002929  jz      loc_140002BAF
0x14000292f  call    cs:__imp_HvlInvokeHypercall
0x140002936  nop     dword ptr [rax+rax+00h]
0x14000293b  test    ax, ax
0x14000293e  jnz     loc_140002AFD
0x140002944  mov     r15d, edi
0x140002947  mov     rcx, [rbp+57h+var_60]
0x14000294b  mov     rax, [rbp+57h+var_28]
0x14000294f  test    r15d, r15d
0x140002952  js      loc_140002B0D
0x140002958  mov     rsi, [r14]
0x14000295b  movzx   ebx, byte ptr [r14+0Ch]
0x140002960  mov     [rsp+0A0h+arg_8], r13
0x140002968  mov     r13d, [r14+8]
0x14000296c  call    _guard_dispatch_icall
0x140002971  test    bl, bl
0x140002973  jz      loc_140002A30
0x140002979  mov     rcx, rsi
0x14000297c  call    WinHvpReferencePartition
0x140002981  mov     rsi, rax
0x140002984  test    rax, rax
0x140002987  jz      loc_140002A30
0x14000298d  mov     r14, rdi
0x140002990  mov     [rsp+0A0h+arg_0], r12
0x140002998  mov     r12d, 0C035000Eh
0x14000299e  cmp     r13d, [rax+48h]
0x1400029a2  jnb     short loc_1400029F5
0x1400029a4  lfence
0x1400029a7  lea     rcx, [rax+50h]; SpinLock
0x1400029ab  call    cs:__imp_ExAcquireSpinLockShared
0x1400029b2  nop     dword ptr [rax+rax+00h]
0x1400029b7  mov     rcx, [rsi+40h]
0x1400029bb  mov     r8, [rcx+r13*8]
0x1400029bf  test    r8, r8
0x1400029c2  jz      short loc_1400029E2
0x1400029c4  mov     edx, 1
0x1400029c9  lock xadd [r8+10h], rdx
0x1400029cf  inc     rdx
0x1400029d2  cmp     rdx, 1
0x1400029d6  jle     loc_140002BBA
0x1400029dc  mov     r14, r8
0x1400029df  mov     r12d, edi
0x1400029e2  movzx   edx, al; OldIrql
0x1400029e5  lea     rcx, [rsi+50h]; SpinLock
0x1400029e9  call    cs:__imp_ExReleaseSpinLockShared
0x1400029f0  nop     dword ptr [rax+rax+00h]
0x1400029f5  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1400029fc  mov     rax, rbx
0x1400029ff  lock xadd [rsi], rax
0x140002a04  sub     rax, 1
0x140002a08  jle     loc_140002B17
0x140002a0e  test    r12d, r12d
0x140002a11  mov     r12, [rsp+0A0h+arg_0]
0x140002a19  jns     short loc_140002A91
0x140002a1b  test    r14, r14
0x140002a1e  jz      short loc_140002A30
0x140002a20  lock xadd [r14+10h], rbx
0x140002a26  sub     rbx, 1
0x140002a2a  jle     loc_140002B2C
0x140002a30  mov     r13, [rsp+0A0h+arg_8]
0x140002a38  mov     r14, [rsp+0A0h+arg_10]
0x140002a40  mov     eax, r15d
0x140002a43  mov     r15, [rsp+80h]
0x140002a4b  add     rsp, 88h
0x140002a52  pop     rdi
0x140002a53  pop     rsi
0x140002a54  pop     rbx
0x140002a55  pop     rbp
0x140002a56  retn
0x140002a58  xor     edi, edi
0x140002a5a  lea     rdx, [rbp+57h+var_70]
0x140002a5e  mov     [rbp+57h+var_70], rdi
0x140002a62  mov     ecx, 5Dh ; ']'
0x140002a67  mov     dword ptr [rbp+57h+var_70], ebx
0x140002a6a  mov     word ptr [rbp+57h+var_70+4], si
0x140002a6e  mov     [rbp+57h+var_68], rdi
0x140002a72  call    WinHvpFastHypercall
0x140002a77  add     rsp, 88h
0x140002a7e  pop     rdi
0x140002a7f  pop     rsi
0x140002a80  pop     rbx
0x140002a81  pop     rbp
0x140002a82  retn
0x140002a84  mov     r8, [rax+28h]
0x140002a88  mov     r8, [r8+28h]
0x140002a8c  jmp     loc_1400028FC
0x140002a91  lea     rcx, [r14+0B8h]; RunRef
0x140002a98  call    cs:__imp_ExAcquireRundownProtection
0x140002a9f  nop     dword ptr [rax+rax+00h]
0x140002aa4  test    al, al
0x140002aa6  jz      loc_140002A1B
0x140002aac  mov     rdx, [r14+0C0h]
0x140002ab3  mov     ecx, 1
0x140002ab8  mov     rax, cs:qword_140016230
0x140002abf  call    _guard_dispatch_icall
0x140002ac4  lea     rcx, [r14+0B8h]; RunRef
0x140002acb  call    cs:__imp_ExReleaseRundownProtection
0x140002ad2  nop     dword ptr [rax+rax+00h]
0x140002ad7  jmp     loc_140002A1B
0x140002adc  mov     r9, [rax+10h]
0x140002ae0  xor     edx, edx
0x140002ae2  mov     r8, [rax+8]
0x140002ae6  mov     ecx, 0F3h
0x140002aeb  mov     [rsp+20h], rdi
0x140002af0  call    WinHvpSlowHypercallRemote
0x140002af5  mov     r15d, eax
0x140002af8  jmp     loc_140002947
0x140002afd  movzx   r15d, ax
0x140002b01  or      r15d, 0C0350000h
0x140002b08  jmp     loc_140002947
0x140002b0d  call    _guard_dispatch_icall
0x140002b12  jmp     loc_140002A38
0x140002b17  test    rax, rax
0x140002b1a  jz      loc_140002BC6
0x140002b20  mov     ecx, 0Eh
0x140002b25  int     29h; Win8: RtlFailFast(ecx)
0x140002b27  jmp     loc_140002A0E
0x140002b2c  test    rbx, rbx
0x140002b2f  jnz     loc_140002BD3
0x140002b35  mov     edx, 57764857h
0x140002b3a  mov     rcx, r14
0x140002b3d  call    WinHvpFreePoolWithTag
0x140002b42  jmp     loc_140002A30
0x140002b47  call    cs:__imp_KeGetCurrentIrql
0x140002b4e  nop     dword ptr [rax+rax+00h]
0x140002b53  mov     [rbp+57h+var_30], al
0x140002b56  cmp     al, 2
0x140002b58  jnb     short loc_140002B76
0x140002b5a  lea     rcx, WinHvpFallbackMutex; FastMutex
0x140002b61  call    cs:__imp_ExAcquireFastMutex
0x140002b68  nop     dword ptr [rax+rax+00h]
0x140002b6d  lea     r14, WinHvpFallbackBuffer2
0x140002b74  jmp     short loc_140002B93
0x140002b76  lea     rcx, WinHvpFallbackSpinLock; SpinLock
0x140002b7d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002b84  nop     dword ptr [rax+rax+00h]
0x140002b89  mov     [rbp+57h+var_30], al
0x140002b8c  lea     r14, WinHvpFallbackBuffer
0x140002b93  lea     rax, WinHvpReleaseFallbackBuffers
0x140002b9a  mov     [rbp+57h+var_38], r14
0x140002b9e  mov     [rbp+57h+var_28], rax
0x140002ba2  jmp     loc_1400028BF
0x140002ba7  mov     rdx, rdi
0x140002baa  jmp     loc_14000290E
0x140002baf  mov     r15d, 0C0351000h
0x140002bb5  jmp     loc_140002947
0x140002bba  mov     ecx, 0Eh
0x140002bbf  int     29h; Win8: RtlFailFast(ecx)
0x140002bc1  jmp     loc_1400029DC
0x140002bc6  mov     rcx, rsi
0x140002bc9  call    WinHvpDeletePartitionObject
0x140002bce  jmp     loc_140002A0E
0x140002bd3  mov     ecx, 0Eh
0x140002bd8  int     29h; Win8: RtlFailFast(ecx)
0x140002bda  jmp     loc_140002A30
```
