# TmRequestOutcomeEnlistmentExt

- ea: `0x140010500`
- end: `0x1400106b4`
- name: `TmRequestOutcomeEnlistmentExt`
- size: `436`
- prototype: `NTSTATUS __stdcall(PKENLISTMENT Enlistment, PLARGE_INTEGER TmVirtualClock)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14001c4a0`

## callees

- `0x140001e10`
- `0x140010500`
- `0x1400108c0`
- `0x14001b338`
- `0x1400209fc`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1400105b3`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400105b3`
- `ntoskrnl!KeReleaseMutex` at `0x14001068b`
- `ntoskrnl!KeReleaseMutex` at `0x1400106a1`
- `ntoskrnl!KeReleaseMutex` at `0x140021d3b`
- `ntoskrnl!KeReleaseMutex` at `0x140021d55`
- `ntoskrnl!KeReleaseMutex` at `0x14001068b`
- `ntoskrnl!KeReleaseMutex` at `0x1400106a1`
- `ntoskrnl!KeReleaseMutex` at `0x140021d3b`
- `ntoskrnl!KeReleaseMutex` at `0x140021d55`
- `ntoskrnl!DbgPrintEx` at `0x140010549`
- `ntoskrnl!DbgPrintEx` at `0x140010549`

## string_xrefs

- `0x140010538`: `KTM:  TmRollbackEnlistmentExt for tx %lx\n`

## pseudocode

```c
NTSTATUS __stdcall TmRequestOutcomeEnlistmentExt(PKENLISTMENT Enlistment, PLARGE_INTEGER TmVirtualClock)
{
  __int64 v4; // rdi
  __int64 v5; // r13
  _QWORD *v6; // rcx
  NTSTATUS v8; // ebx
  unsigned int v9; // r14d
  __int64 v10; // rdx
  int v11; // r15d

  v4 = *((_QWORD *)Enlistment + 20);
  v5 = *((_QWORD *)Enlistment + 19);
  DbgPrintEx(0x6Cu, 0x80000020, "KTM:  TmRollbackEnlistmentExt for tx %lx\n", v4);
  v6 = (_QWORD *)(v5 + 360);
  if ( TmVirtualClock && !*v6 )
    return -1072103342;
  v8 = -1072103405;
  v9 = 0;
  TmpAdjustVirtualClock(*v6, TmVirtualClock);
  TmpAcquireTransactionMutex(v4);
  KeWaitForSingleObject((char *)Enlistment + 64, Executive, 0, 0, 0);
  if ( (*((_DWORD *)Enlistment + 43) & 1) == 0 )
  {
    v11 = *(_DWORD *)(*(_QWORD *)(v4 + 512) + 128LL) & 0x40;
    do
    {
      ++v9;
      if ( (unsigned int)(*((_DWORD *)Enlistment + 42) - 258) <= 1 )
      {
        if ( *(__int64 (__fastcall **)(PKENLISTMENT *, PVOID, PVOID, ULONG, PLARGE_INTEGER))(v5 + 296) != TmpInternalCrmNotification
          && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0 )
        {
          WPP_SF_q_guid__guid_(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            12,
            *((_DWORD *)Enlistment + 40) + 176,
            v4,
            *((_QWORD *)Enlistment + 20) + 176LL,
            v5 + 136);
        }
        LOBYTE(v10) = v11 && v9 > 1;
        v8 = TmpRequestOutcomeTransaction(v4, v10);
      }
    }
    while ( v11 && v9 < 2 );
  }
  KeReleaseMutex((PRKMUTEX)((char *)Enlistment + 64), 0);
  KeReleaseMutex((PRKMUTEX)(*(_QWORD *)(v4 + 88) + 32LL), 0);
  return v8;
}

```

## disassembly

```asm
0x140010500  mov     [rsp+arg_10], rbx
0x140010505  mov     [rsp+arg_18], rsi
0x14001050a  mov     [rsp+arg_0], rcx
0x14001050f  push    rdi
0x140010510  push    r12
0x140010512  push    r13
0x140010514  push    r14
0x140010516  push    r15
0x140010518  sub     rsp, 40h
0x14001051c  mov     r15, rdx
0x14001051f  mov     rsi, rcx
0x140010522  mov     rdi, [rcx+0A0h]
0x140010529  mov     [rsp+68h+arg_8], rdi
0x14001052e  mov     r13, [rcx+98h]
0x140010535  mov     r9, rdi
0x140010538  lea     r8, aKtmTmrollbacke; "KTM:  TmRollbackEnlistmentExt for tx %l"...
0x14001053f  mov     edx, 80000020h; Level
0x140010544  mov     ecx, 6Ch ; 'l'; ComponentId
0x140010549  call    cs:__imp_DbgPrintEx
0x140010550  nop     dword ptr [rax+rax+00h]
0x140010555  lea     rcx, [r13+168h]
0x14001055c  test    r15, r15
0x14001055f  jz      short loc_140010587
0x140010561  cmp     qword ptr [rcx], 0
0x140010565  jnz     short loc_140010587
0x140010567  mov     eax, 0C0190052h
0x14001056c  lea     r11, [rsp+68h+var_28]
0x140010571  mov     rbx, [r11+40h]
0x140010575  mov     rsi, [r11+48h]
0x140010579  mov     rsp, r11
0x14001057c  pop     r15
0x14001057e  pop     r14
0x140010580  pop     r13
0x140010582  pop     r12
0x140010584  pop     rdi
0x140010585  retn
0x140010587  mov     ebx, 0C0190013h
0x14001058c  xor     r14d, r14d
0x14001058f  mov     rdx, r15
0x140010592  mov     rcx, [rcx]
0x140010595  call    TmpAdjustVirtualClock
0x14001059a  mov     rcx, rdi
0x14001059d  call    TmpAcquireTransactionMutex
0x1400105a2  mov     [rsp+68h+Timeout], r14; Timeout
0x1400105a7  xor     r9d, r9d; Alertable
0x1400105aa  xor     r8d, r8d; WaitMode
0x1400105ad  xor     edx, edx; WaitReason
0x1400105af  lea     rcx, [rsi+40h]; Object
0x1400105b3  call    cs:__imp_KeWaitForSingleObject
0x1400105ba  nop     dword ptr [rax+rax+00h]
0x1400105bf  nop
0x1400105c0  mov     rax, [rdi+200h]
0x1400105c7  mov     r15d, [rax+80h]
0x1400105ce  mov     eax, [rsi+0ACh]
0x1400105d4  test    al, 1
0x1400105d6  jz      short loc_1400105E1
0x1400105d8  mov     [rsp+68h+var_38], ebx
0x1400105dc  jmp     loc_140010685
0x1400105e1  and     r15d, 40h
0x1400105e5  inc     r14d
0x1400105e8  mov     [rsp+68h+var_34], r14d
0x1400105ed  mov     eax, [rsi+0A8h]
0x1400105f3  sub     eax, 102h
0x1400105f8  cmp     eax, 1
0x1400105fb  ja      short loc_140010676
0x1400105fd  lea     rax, TmpInternalCrmNotification
0x140010604  cmp     [r13+128h], rax
0x14001060b  jz      short loc_140010657
0x14001060d  lea     rax, WPP_GLOBAL_Control
0x140010614  mov     rcx, cs:WPP_GLOBAL_Control
0x14001061b  cmp     rcx, rax
0x14001061e  jz      short loc_140010657
0x140010620  mov     eax, [rcx+2Ch]
0x140010623  test    al, 8
0x140010625  jz      short loc_140010657
0x140010627  lea     rax, [r13+88h]
0x14001062e  mov     r8, [rsi+0A0h]
0x140010635  add     r8, 0B0h
0x14001063c  mov     edx, 0Ch
0x140010641  mov     [rsp+68h+var_40], rax
0x140010646  mov     [rsp+68h+Timeout], r8
0x14001064b  mov     r9, rdi
0x14001064e  mov     rcx, [rcx+18h]
0x140010652  call    WPP_SF_q_guid__guid_
0x140010657  test    r15d, r15d
0x14001065a  jz      short loc_140010666
0x14001065c  cmp     r14d, 1
0x140010660  jbe     short loc_140010666
0x140010662  mov     dl, 1
0x140010664  jmp     short loc_140010668
0x140010666  xor     dl, dl
0x140010668  mov     rcx, rdi
0x14001066b  call    TmpRequestOutcomeTransaction
0x140010670  mov     ebx, eax
0x140010672  mov     [rsp+68h+var_38], eax
0x140010676  test    r15d, r15d
0x140010679  jz      short loc_140010685
0x14001067b  cmp     r14d, 2
0x14001067f  jb      loc_1400105E5
0x140010685  xor     edx, edx; Wait
0x140010687  lea     rcx, [rsi+40h]; Mutex
0x14001068b  call    cs:__imp_KeReleaseMutex
0x140010692  nop     dword ptr [rax+rax+00h]
0x140010697  mov     rcx, [rdi+58h]
0x14001069b  add     rcx, 20h ; ' '; Mutex
0x14001069f  xor     edx, edx; Wait
0x1400106a1  call    cs:__imp_KeReleaseMutex
0x1400106a8  nop     dword ptr [rax+rax+00h]
0x1400106ad  mov     eax, ebx
0x1400106af  jmp     loc_14001056C
0x140021d28  push    rbp
0x140021d2a  sub     rsp, 30h
0x140021d2e  mov     rbp, rdx
0x140021d31  mov     rcx, [rbp+70h]
0x140021d35  add     rcx, 40h ; '@'; Mutex
0x140021d39  xor     edx, edx; Wait
0x140021d3b  call    cs:__imp_KeReleaseMutex
0x140021d42  nop     dword ptr [rax+rax+00h]
0x140021d47  mov     rax, [rbp+78h]
0x140021d4b  mov     rcx, [rax+58h]
0x140021d4f  add     rcx, 20h ; ' '; Mutex
0x140021d53  xor     edx, edx; Wait
0x140021d55  call    cs:__imp_KeReleaseMutex
0x140021d5c  nop     dword ptr [rax+rax+00h]
0x140021d61  nop
0x140021d62  add     rsp, 30h
0x140021d66  pop     rbp
0x140021d67  retn
```
