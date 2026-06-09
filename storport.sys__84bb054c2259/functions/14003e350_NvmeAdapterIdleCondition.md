# NvmeAdapterIdleCondition

- ea: `0x14003e350`
- end: `0x14003e530`
- name: `NvmeAdapterIdleCondition`
- size: `480`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x14003e350`
- `0x14003e538`
- `0x14003e570`
- `0x14003e5ac`
- `0x1400f4674`
- `0x1400fc9a0`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14003e4fa`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14003e4fa`
- `ntoskrnl!KeCancelTimer` at `0x14003e3ad`
- `ntoskrnl!KeCancelTimer` at `0x14003e490`
- `ntoskrnl!KeCancelTimer` at `0x14003e3ad`
- `ntoskrnl!KeCancelTimer` at `0x14003e490`
- `ntoskrnl!KeRemoveQueueDpc` at `0x14003e3c8`
- `ntoskrnl!KeRemoveQueueDpc` at `0x14003e4ab`
- `ntoskrnl!KeRemoveQueueDpc` at `0x14003e3c8`
- `ntoskrnl!KeRemoveQueueDpc` at `0x14003e4ab`
- `ntoskrnl!PoFxCompleteIdleCondition` at `0x14003e423`
- `ntoskrnl!PoFxCompleteIdleCondition` at `0x14003e423`

## pseudocode

```c
__int64 __fastcall NvmeAdapterIdleCondition(__int64 a1, unsigned int a2)
{
  __int64 result; // rax
  __int64 v5; // rdi
  _QWORD *i; // rdi
  __int64 v7; // rdi

  result = NvmeAdapterCheckAndAcquirePoFx();
  if ( (_BYTE)result )
  {
    if ( (*(_DWORD *)(*(_QWORD *)(a1 + 408) + 184LL) & 0x40000000) != 0 )
    {
      v5 = *(_QWORD *)(a1 + 1152);
      if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v5 + 1312) + 40LL) + 192LL) )
      {
        KeCancelTimer((PKTIMER)(*(_QWORD *)(*(_QWORD *)(v5 + 1312) + 40LL) + 128LL));
        KeRemoveQueueDpc((PRKDPC)(*(_QWORD *)(*(_QWORD *)(v5 + 1312) + 40LL) + 64LL));
        _InterlockedCompareExchange(
          (volatile signed __int32 *)(*(_QWORD *)(*(_QWORD *)(v5 + 1312) + 40LL) + 192LL),
          0,
          1);
      }
    }
    else if ( (*(_DWORD *)(a1 + 424) & 0x40) != 0 )
    {
      NvmeAdapterAcquireStorMQControllerListLockShared(a1);
      for ( i = *(_QWORD **)(a1 + 1200); i != (_QWORD *)(a1 + 1200); i = (_QWORD *)*i )
      {
        if ( *(_DWORD *)(*(_QWORD *)(i[150] + 40LL) + 192LL) )
        {
          KeCancelTimer((PKTIMER)(*(_QWORD *)(i[150] + 40LL) + 128LL));
          KeRemoveQueueDpc((PRKDPC)(*(_QWORD *)(i[150] + 40LL) + 64LL));
          _InterlockedCompareExchange((volatile signed __int32 *)(*(_QWORD *)(i[150] + 40LL) + 192LL), 0, 1);
        }
      }
      NvmeAdapterReleaseStorMQControllerListLockShared(a1);
    }
    *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a1 + 168) + 8LL) + 64LL) = 0;
    if ( (*(_DWORD *)(*(_QWORD *)(a1 + 408) + 184LL) & 0x40000000) != 0 )
    {
      NvmeControllerPowerActive(*(_QWORD *)(a1 + 1152), 0);
      if ( (*(_DWORD *)(a1 + 152) & 0x2000LL) == 0 )
      {
        v7 = *(_QWORD *)(a1 + 1336);
        if ( v7 )
        {
          if ( *(_DWORD *)(v7 + 28) )
          {
            if ( !*(_DWORD *)(v7 + 32) )
              *(_QWORD *)(v7 + 96) = KeQueryUnbiasedInterruptTime();
          }
        }
      }
    }
    PoFxCompleteIdleCondition(**(_QWORD **)(*(_QWORD *)(a1 + 168) + 8LL), a2);
    return NvmeAdapterReleasePoFx(a1);
  }
  return result;
}

```

## disassembly

```asm
0x14003e350  push    rbx
0x14003e352  push    rbp
0x14003e353  push    rsi
0x14003e354  push    rdi
0x14003e355  sub     rsp, 28h
0x14003e359  mov     ebp, edx
0x14003e35b  mov     rbx, rcx
0x14003e35e  call    NvmeAdapterCheckAndAcquirePoFx
0x14003e363  test    al, al
0x14003e365  jz      loc_14003E437
0x14003e36b  mov     rax, [rbx+198h]
0x14003e372  test    dword ptr [rax+0B8h], 40000000h
0x14003e37c  jz      loc_14003E441
0x14003e382  mov     rdi, [rbx+480h]
0x14003e389  mov     rax, [rdi+520h]
0x14003e390  mov     rcx, [rax+28h]
0x14003e394  mov     eax, [rcx+0C0h]
0x14003e39a  test    eax, eax
0x14003e39c  jz      short loc_14003E3EC
0x14003e39e  mov     rax, [rdi+520h]
0x14003e3a5  mov     rcx, [rax+28h]
0x14003e3a9  sub     rcx, 0FFFFFFFFFFFFFF80h; PKTIMER
0x14003e3ad  call    cs:__imp_KeCancelTimer
0x14003e3b4  nop     dword ptr [rax+rax+00h]
0x14003e3b9  mov     rax, [rdi+520h]
0x14003e3c0  mov     rcx, [rax+28h]
0x14003e3c4  add     rcx, 40h ; '@'; Dpc
0x14003e3c8  call    cs:__imp_KeRemoveQueueDpc
0x14003e3cf  nop     dword ptr [rax+rax+00h]
0x14003e3d4  mov     rax, [rdi+520h]
0x14003e3db  xor     ecx, ecx
0x14003e3dd  mov     rdx, [rax+28h]
0x14003e3e1  lea     eax, [rcx+1]
0x14003e3e4  lock cmpxchg [rdx+0C0h], ecx
0x14003e3ec  mov     rax, [rbx+0A8h]
0x14003e3f3  mov     rcx, [rax+8]
0x14003e3f7  xor     eax, eax
0x14003e3f9  xchg    al, [rcx+40h]
0x14003e3fc  mov     rax, [rbx+198h]
0x14003e403  test    dword ptr [rax+0B8h], 40000000h
0x14003e40d  jnz     loc_14003E50F
0x14003e413  mov     rax, [rbx+0A8h]
0x14003e41a  mov     edx, ebp
0x14003e41c  mov     rcx, [rax+8]
0x14003e420  mov     rcx, [rcx]
0x14003e423  call    cs:__imp_PoFxCompleteIdleCondition
0x14003e42a  nop     dword ptr [rax+rax+00h]
0x14003e42f  mov     rcx, rbx
0x14003e432  call    NvmeAdapterReleasePoFx
0x14003e437  add     rsp, 28h
0x14003e43b  pop     rdi
0x14003e43c  pop     rsi
0x14003e43d  pop     rbp
0x14003e43e  pop     rbx
0x14003e43f  retn
0x14003e441  mov     eax, [rbx+1A8h]
0x14003e447  test    al, 40h
0x14003e449  jz      short loc_14003E3EC
0x14003e44b  mov     rcx, rbx
0x14003e44e  call    NvmeAdapterAcquireStorMQControllerListLockShared
0x14003e453  lea     rsi, [rbx+4B0h]
0x14003e45a  mov     rdi, [rsi]
0x14003e45d  cmp     rdi, rsi
0x14003e460  jnz     short loc_14003E46C
0x14003e462  mov     rcx, rbx
0x14003e465  call    NvmeAdapterReleaseStorMQControllerListLockShared
0x14003e46a  jmp     short loc_14003E3EC
0x14003e46c  mov     rax, [rdi+4B0h]
0x14003e473  mov     rcx, [rax+28h]
0x14003e477  mov     eax, [rcx+0C0h]
0x14003e47d  test    eax, eax
0x14003e47f  jz      short loc_14003E4CF
0x14003e481  mov     rax, [rdi+4B0h]
0x14003e488  mov     rcx, [rax+28h]
0x14003e48c  sub     rcx, 0FFFFFFFFFFFFFF80h; PKTIMER
0x14003e490  call    cs:__imp_KeCancelTimer
0x14003e497  nop     dword ptr [rax+rax+00h]
0x14003e49c  mov     rax, [rdi+4B0h]
0x14003e4a3  mov     rcx, [rax+28h]
0x14003e4a7  add     rcx, 40h ; '@'; Dpc
0x14003e4ab  call    cs:__imp_KeRemoveQueueDpc
0x14003e4b2  nop     dword ptr [rax+rax+00h]
0x14003e4b7  mov     rax, [rdi+4B0h]
0x14003e4be  xor     ecx, ecx
0x14003e4c0  mov     rdx, [rax+28h]
0x14003e4c4  lea     eax, [rcx+1]
0x14003e4c7  lock cmpxchg [rdx+0C0h], ecx
0x14003e4cf  mov     rdi, [rdi]
0x14003e4d2  jmp     short loc_14003E45D
0x14003e4d4  mov     rdi, [rbx+538h]
0x14003e4db  test    rdi, rdi
0x14003e4de  jz      loc_14003E413
0x14003e4e4  mov     eax, [rdi+1Ch]
0x14003e4e7  test    eax, eax
0x14003e4e9  jz      loc_14003E413
0x14003e4ef  mov     eax, [rdi+20h]
0x14003e4f2  test    eax, eax
0x14003e4f4  jnz     loc_14003E413
0x14003e4fa  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x14003e501  nop     dword ptr [rax+rax+00h]
0x14003e506  mov     [rdi+60h], rax
0x14003e50a  jmp     loc_14003E413
0x14003e50f  mov     rcx, [rbx+480h]
0x14003e516  xor     edx, edx
0x14003e518  call    NvmeControllerPowerActive
0x14003e51d  mov     eax, [rbx+98h]
0x14003e523  bt      rax, 0Dh
0x14003e528  jb      loc_14003E413
0x14003e52e  jmp     short loc_14003E4D4
```
