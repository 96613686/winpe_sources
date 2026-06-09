# UdfMarkVolumeOpenAndQueueCloseDpc

- ea: `0x1400062c0`
- end: `0x140006533`
- name: `UdfMarkVolumeOpenAndQueueCloseDpc`
- size: `627`
- prototype: ``
- caller_count: `8`
- callee_count: `7`
- tags: ``

## callers

- `0x1400010f0`
- `0x140004484`
- `0x140005e80`
- `0x140007b90`
- `0x14000e438`
- `0x140012308`
- `0x140030818`
- `0x1400570f4`

## callees

- `0x1400062c0`
- `0x140009014`
- `0x14000b808`
- `0x14000ca54`
- `0x14000cad4`
- `0x140017c08`
- `0x14004ce50`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x14000638e`
- `ntoskrnl!ExReleaseResourceLite` at `0x140006504`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001cdbe`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000638e`
- `ntoskrnl!ExReleaseResourceLite` at `0x140006504`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001cdbe`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400064aa`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400064aa`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400064db`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400064db`
- `ntoskrnl!KeSetTimer` at `0x1400064f4`
- `ntoskrnl!KeSetTimer` at `0x1400064f4`
- `ntoskrnl!KeCancelTimer` at `0x140006476`
- `ntoskrnl!KeCancelTimer` at `0x140006476`
- `ntoskrnl!KeRemoveQueueDpc` at `0x14000648c`
- `ntoskrnl!KeRemoveQueueDpc` at `0x14000648c`

## pseudocode

```c
void __fastcall UdfMarkVolumeOpenAndQueueCloseDpc(__int64 a1)
{
  __int64 v2; // r15
  int v3; // edx
  int v4; // r13d
  __int64 v5; // rax
  int v6; // eax
  int v7; // ebx
  __int64 v8; // r8
  __int64 v9; // rcx
  int v10; // eax

  v2 = *(_QWORD *)(a1 + 16);
  if ( !*(_QWORD *)(v2 + 352) && (*(_DWORD *)(v2 + 48) & 0x20000000) == 0
    || KeGetCurrentThread() != *(struct _KTHREAD **)(*(_QWORD *)(v2 + 104) + 616LL) )
  {
    v3 = *(_DWORD *)(a1 + 28);
    if ( (v3 & 0x14000) == 0 && (*(_DWORD *)(*(_QWORD *)(a1 + 48) + 28LL) & 0x14000) == 0 )
    {
      v4 = *(_DWORD *)(a1 + 28) & 4;
      v5 = *(_QWORD *)(a1 + 64);
      if ( !v5 || *(_QWORD *)(v5 + 8) != 3 )
        *(_DWORD *)(a1 + 28) = v3 | 4;
      UdfAcquireResource(a1, v2 + 2024, 0, 1);
      v6 = *(_DWORD *)(a1 + 28);
      if ( (v6 & 0x8000) == 0 )
      {
        *(_DWORD *)(a1 + 28) = v6 | 0x8000;
        _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 16) + 2016LL));
      }
      v7 = *(_DWORD *)(v2 + 2128);
      ExReleaseResourceLite((PERESOURCE)(v2 + 2024));
      if ( (v7 & 4) == 0 )
      {
        UdfAcquireResource(a1, v2 + 2024, 0, 0);
        if ( (*(_DWORD *)(v2 + 2128) & 4) == 0 )
        {
          v9 = *(_QWORD *)&WPP_GLOBAL_Control;
          if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x10000000) != 0 )
          {
            WPP_SF_q(
              *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
              34,
              WPP_3e271ebed6f63f8fe36d0f7ec1e80eae_Traceguids,
              v2);
          }
          *(_DWORD *)(a1 + 28) |= 4u;
          LOBYTE(v8) = 1;
          UdfToggleMediaEjectDisable(v9, v2, v8, 0);
          if ( (*(_DWORD *)(v2 + 2128) & 2) == 0 && (*(_DWORD *)(v2 + 48) & 0x20) == 0 )
          {
            if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x10000000) != 0 )
            {
              WPP_SF_(
                *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
                36,
                WPP_3e271ebed6f63f8fe36d0f7ec1e80eae_Traceguids);
            }
            v10 = UdfSetVolumeDirtyState(a1, 0);
            if ( v10 < 0 )
              UdfRaiseStatusEx(a1, (unsigned int)v10, 0);
            *(_DWORD *)(v2 + 2128) |= 2u;
          }
          KeCancelTimer((PKTIMER)(v2 + 1920));
          KeRemoveQueueDpc((PRKDPC)(v2 + 1856));
          *(_DWORD *)(v2 + 2128) |= 4u;
          ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v2 + 1584));
          *(_QWORD *)(v2 + 1640) = KeGetCurrentThread();
          ++*(_DWORD *)(v2 + 256);
          *(_QWORD *)(v2 + 1640) = 0;
          ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v2 + 1584));
          KeSetTimer((PKTIMER)(v2 + 1920), (LARGE_INTEGER)-40000000LL, (PKDPC)(v2 + 1856));
        }
        ExReleaseResourceLite((PERESOURCE)(v2 + 2024));
        if ( !v4 )
          *(_DWORD *)(a1 + 28) &= ~4u;
      }
    }
  }
}

```

## disassembly

```asm
0x1400062c0  mov     [rsp+arg_8], rbx
0x1400062c5  mov     [rsp+arg_10], rsi
0x1400062ca  push    rdi
0x1400062cb  push    r12
0x1400062cd  push    r13
0x1400062cf  push    r14
0x1400062d1  push    r15
0x1400062d3  sub     rsp, 20h
0x1400062d7  mov     r14, rcx
0x1400062da  mov     r15, [rcx+10h]
0x1400062de  cmp     qword ptr [r15+160h], 0
0x1400062e6  jnz     short loc_1400062F2
0x1400062e8  test    dword ptr [r15+30h], 20000000h
0x1400062f0  jz      short loc_14000630C
0x1400062f2  mov     rdx, gs:188h
0x1400062fb  mov     rax, [r15+68h]
0x1400062ff  cmp     rdx, [rax+268h]
0x140006306  jz      loc_14000651A
0x14000630c  mov     edx, [rcx+1Ch]
0x14000630f  mov     r8d, 14000h
0x140006315  test    r8d, edx
0x140006318  jnz     loc_14000651A
0x14000631e  mov     rax, [rcx+30h]
0x140006322  test    [rax+1Ch], r8d
0x140006326  jnz     loc_14000651A
0x14000632c  mov     r13d, edx
0x14000632f  and     r13d, 4
0x140006333  mov     [rsp+48h+arg_0], r15
0x140006338  mov     rax, [rcx+40h]
0x14000633c  test    rax, rax
0x14000633f  jz      short loc_140006348
0x140006341  cmp     qword ptr [rax+8], 3
0x140006346  jz      short loc_14000634E
0x140006348  or      edx, 4
0x14000634b  mov     [rcx+1Ch], edx
0x14000634e  lea     r12, [r15+7E8h]
0x140006355  mov     r9d, 1
0x14000635b  xor     r8d, r8d
0x14000635e  mov     rdx, r12
0x140006361  call    UdfAcquireResource
0x140006366  mov     eax, [r14+1Ch]
0x14000636a  mov     ecx, 8000h
0x14000636f  test    ecx, eax
0x140006371  jnz     short loc_140006384
0x140006373  or      eax, ecx
0x140006375  mov     [r14+1Ch], eax
0x140006379  mov     rax, [r14+10h]
0x14000637d  lock inc dword ptr [rax+7E0h]
0x140006384  mov     ebx, [r15+850h]
0x14000638b  mov     rcx, r12; Resource
0x14000638e  call    cs:__imp_ExReleaseResourceLite
0x140006395  nop     dword ptr [rax+rax+00h]
0x14000639a  bt      ebx, 2
0x14000639e  jb      loc_14000651A
0x1400063a4  xor     r9d, r9d
0x1400063a7  xor     r8d, r8d
0x1400063aa  mov     rdx, r12
0x1400063ad  mov     rcx, r14
0x1400063b0  call    UdfAcquireResource
0x1400063b5  nop
0x1400063b6  mov     eax, [r15+850h]
0x1400063bd  test    al, 4
0x1400063bf  jnz     loc_140006501
0x1400063c5  lea     rbx, WPP_GLOBAL_Control
0x1400063cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400063d3  cmp     rcx, rbx
0x1400063d6  jz      short loc_1400063F9
0x1400063d8  test    dword ptr [rcx+2Ch], 10000000h
0x1400063df  jz      short loc_1400063F9
0x1400063e1  mov     edx, 22h ; '"'
0x1400063e6  mov     r9, r15
0x1400063e9  lea     r8, WPP_3e271ebed6f63f8fe36d0f7ec1e80eae_Traceguids
0x1400063f0  mov     rcx, [rcx+18h]
0x1400063f4  call    WPP_SF_q
0x1400063f9  or      dword ptr [r14+1Ch], 4
0x1400063fe  xor     r9d, r9d
0x140006401  mov     r8b, 1
0x140006404  mov     rdx, r15
0x140006407  call    UdfToggleMediaEjectDisable
0x14000640c  mov     eax, [r15+850h]
0x140006413  test    al, 2
0x140006415  jnz     short loc_14000646C
0x140006417  mov     eax, [r15+30h]
0x14000641b  test    al, 20h
0x14000641d  jnz     short loc_14000646C
0x14000641f  mov     rcx, cs:WPP_GLOBAL_Control
0x140006426  cmp     rcx, rbx
0x140006429  jz      short loc_140006449
0x14000642b  test    dword ptr [rcx+2Ch], 10000000h
0x140006432  jz      short loc_140006449
0x140006434  mov     edx, 24h ; '$'
0x140006439  lea     r8, WPP_3e271ebed6f63f8fe36d0f7ec1e80eae_Traceguids
0x140006440  mov     rcx, [rcx+18h]
0x140006444  call    WPP_SF_
0x140006449  xor     edx, edx
0x14000644b  mov     rcx, r14
0x14000644e  call    UdfSetVolumeDirtyState
0x140006453  test    eax, eax
0x140006455  jns     short loc_140006464
0x140006457  xor     r8d, r8d
0x14000645a  mov     edx, eax
0x14000645c  mov     rcx, r14
0x14000645f  call    UdfRaiseStatusEx
0x140006464  or      dword ptr [r15+850h], 2
0x14000646c  lea     rsi, [r15+780h]
0x140006473  mov     rcx, rsi; PKTIMER
0x140006476  call    cs:__imp_KeCancelTimer
0x14000647d  nop     dword ptr [rax+rax+00h]
0x140006482  lea     rdi, [r15+740h]
0x140006489  mov     rcx, rdi; Dpc
0x14000648c  call    cs:__imp_KeRemoveQueueDpc
0x140006493  nop     dword ptr [rax+rax+00h]
0x140006498  or      dword ptr [r15+850h], 4
0x1400064a0  lea     rbx, [r15+630h]
0x1400064a7  mov     rcx, rbx; FastMutex
0x1400064aa  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400064b1  nop     dword ptr [rax+rax+00h]
0x1400064b6  mov     rax, gs:188h
0x1400064bf  mov     [r15+668h], rax
0x1400064c6  inc     dword ptr [r15+100h]
0x1400064cd  mov     qword ptr [r15+668h], 0
0x1400064d8  mov     rcx, rbx; FastMutex
0x1400064db  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1400064e2  nop     dword ptr [rax+rax+00h]
0x1400064e7  mov     r8, rdi; Dpc
0x1400064ea  mov     rdx, 0FFFFFFFFFD9DA600h; DueTime
0x1400064f1  mov     rcx, rsi; Timer
0x1400064f4  call    cs:__imp_KeSetTimer
0x1400064fb  nop     dword ptr [rax+rax+00h]
0x140006500  nop
0x140006501  mov     rcx, r12; Resource
0x140006504  call    cs:__imp_ExReleaseResourceLite
0x14000650b  nop     dword ptr [rax+rax+00h]
0x140006510  test    r13d, r13d
0x140006513  jnz     short loc_14000651A
0x140006515  and     dword ptr [r14+1Ch], 0FFFFFFFBh
0x14000651a  mov     rbx, [rsp+48h+arg_8]
0x14000651f  mov     rsi, [rsp+48h+arg_10]
0x140006524  add     rsp, 20h
0x140006528  pop     r15
0x14000652a  pop     r14
0x14000652c  pop     r13
0x14000652e  pop     r12
0x140006530  pop     rdi
0x140006531  retn
0x14001cd96  push    rbp
0x14001cd98  sub     rsp, 20h
0x14001cd9c  mov     rbp, rdx
0x14001cd9f  test    cl, cl
0x14001cda1  jz      short loc_14001CDB3
0x14001cda3  xor     r9d, r9d
0x14001cda6  xor     r8d, r8d
0x14001cda9  mov     rdx, [rbp+50h]
0x14001cdad  call    UdfToggleMediaEjectDisable
0x14001cdb2  nop
0x14001cdb3  mov     rcx, [rbp+50h]
0x14001cdb7  add     rcx, 7E8h; Resource
0x14001cdbe  call    cs:__imp_ExReleaseResourceLite
0x14001cdc5  nop     dword ptr [rax+rax+00h]
0x14001cdca  nop
0x14001cdcb  add     rsp, 20h
0x14001cdcf  pop     rbp
0x14001cdd0  retn
```
