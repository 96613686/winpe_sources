# TmCommitEnlistmentExt

- ea: `0x14000fed0`
- end: `0x1400100c1`
- name: `TmCommitEnlistmentExt`
- size: `497`
- prototype: `NTSTATUS __stdcall(PKENLISTMENT Enlistment, PLARGE_INTEGER TmVirtualClock)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140012d80`
- `0x14001c4a0`

## callees

- `0x14000fed0`
- `0x14001a2e0`
- `0x14001b338`
- `0x1400209fc`
- `0x140020dd4`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14000ffbb`
- `ntoskrnl!KeWaitForSingleObject` at `0x140010029`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000ffbb`
- `ntoskrnl!KeWaitForSingleObject` at `0x140010029`
- `ntoskrnl!KeReleaseMutex` at `0x14000ffe5`
- `ntoskrnl!KeReleaseMutex` at `0x140010053`
- `ntoskrnl!KeReleaseMutex` at `0x14001009f`
- `ntoskrnl!KeReleaseMutex` at `0x140021c76`
- `ntoskrnl!KeReleaseMutex` at `0x14000ffe5`
- `ntoskrnl!KeReleaseMutex` at `0x140010053`
- `ntoskrnl!KeReleaseMutex` at `0x14001009f`
- `ntoskrnl!KeReleaseMutex` at `0x140021c76`
- `ntoskrnl!ObfDereferenceObject` at `0x1400100ae`
- `ntoskrnl!ObfDereferenceObject` at `0x140021c85`
- `ntoskrnl!ObfDereferenceObject` at `0x1400100ae`
- `ntoskrnl!ObfDereferenceObject` at `0x140021c85`
- `ntoskrnl!ObfReferenceObject` at `0x14000ff51`
- `ntoskrnl!ObfReferenceObject` at `0x14000ff51`
- `ntoskrnl!DbgPrintEx` at `0x14000ff02`
- `ntoskrnl!DbgPrintEx` at `0x14000ff02`

## string_xrefs

- `0x14000fef1`: `KTM:  TmCommitTransactionExt for tx %lx\n`

## pseudocode

```c
NTSTATUS __stdcall TmCommitEnlistmentExt(PKENLISTMENT Enlistment, PLARGE_INTEGER TmVirtualClock)
{
  __int64 v4; // rdi
  __int64 v5; // rbx
  _QWORD *v6; // rcx
  NTSTATUS v8; // ebx
  int v9; // ecx
  NTSTATUS v10; // eax

  v4 = *((_QWORD *)Enlistment + 20);
  v5 = *((_QWORD *)Enlistment + 19);
  DbgPrintEx(0x6Cu, 0x80000020, "KTM:  TmCommitTransactionExt for tx %lx\n", v4);
  v6 = (_QWORD *)(v5 + 360);
  if ( TmVirtualClock && !*v6 )
    return -1072103342;
  v8 = -1072103405;
  TmpAdjustVirtualClock(*v6, TmVirtualClock);
  TmpAcquireTransactionMutex(v4);
  ObfReferenceObject((PVOID)v4);
  if ( (*((_DWORD *)Enlistment + 43) & 1) != 0 )
  {
    if ( (*((_DWORD *)Enlistment + 44) & 0x40) == 0 )
    {
      v8 = -1072103337;
      goto LABEL_25;
    }
    if ( (*(_DWORD *)(v4 + 196) & 2) != 0 )
      goto LABEL_25;
    v9 = *(_DWORD *)(v4 + 192);
    if ( v9 == 1 )
    {
      _InterlockedOr((volatile signed __int32 *)(v4 + 196), 2u);
      KeWaitForSingleObject((char *)Enlistment + 64, Executive, 0, 0, 0);
      if ( (*((_DWORD *)Enlistment + 43) & 2) != 0 )
      {
        _InterlockedAnd((volatile signed __int32 *)Enlistment + 43, 0xFFFFFFFD);
        --*(_DWORD *)(v4 + 220);
      }
      KeReleaseMutex((PRKMUTEX)((char *)Enlistment + 64), 0);
      v10 = TmCommitTransactionExt((PKTRANSACTION)v4, 0);
    }
    else
    {
      if ( (unsigned int)(v9 - 3) > 1 )
      {
        if ( v9 == 7 )
        {
          v8 = -1072103421;
          goto LABEL_25;
        }
LABEL_20:
        if ( (*(_DWORD *)(v4 + 196) & 0x8000000) != 0 )
        {
          v8 = 1075380225;
        }
        else if ( *(_DWORD *)(v4 + 192) == 6 || *(_DWORD *)(v4 + 504) == 3 )
        {
          v8 = -1072103403;
        }
        goto LABEL_25;
      }
      KeWaitForSingleObject((char *)Enlistment + 64, Executive, 0, 0, 0);
      if ( (*((_DWORD *)Enlistment + 43) & 2) != 0 )
      {
        _InterlockedAnd((volatile signed __int32 *)Enlistment + 43, 0xFFFFFFFD);
        --*(_DWORD *)(v4 + 220);
      }
      KeReleaseMutex((PRKMUTEX)((char *)Enlistment + 64), 0);
      v10 = TmpTxActionDoCommit((PVOID)v4);
    }
    v8 = v10;
    goto LABEL_20;
  }
  v8 = -1072103373;
LABEL_25:
  KeReleaseMutex((PRKMUTEX)(*(_QWORD *)(v4 + 88) + 32LL), 0);
  ObfDereferenceObject((PVOID)v4);
  return v8;
}

```

## disassembly

```asm
0x14000fed0  push    rbx
0x14000fed2  push    rsi
0x14000fed3  push    rdi
0x14000fed4  push    r14
0x14000fed6  sub     rsp, 38h
0x14000feda  mov     r14, rdx
0x14000fedd  mov     rsi, rcx
0x14000fee0  mov     rdi, [rcx+0A0h]
0x14000fee7  mov     rbx, [rcx+98h]
0x14000feee  mov     r9, rdi
0x14000fef1  lea     r8, Format; "KTM:  TmCommitTransactionExt for tx %lx"...
0x14000fef8  mov     edx, 80000020h; Level
0x14000fefd  mov     ecx, 6Ch ; 'l'; ComponentId
0x14000ff02  call    cs:__imp_DbgPrintEx
0x14000ff09  nop     dword ptr [rax+rax+00h]
0x14000ff0e  lea     rcx, [rbx+168h]
0x14000ff15  test    r14, r14
0x14000ff18  jz      short loc_14000FF30
0x14000ff1a  cmp     qword ptr [rcx], 0
0x14000ff1e  jnz     short loc_14000FF30
0x14000ff20  mov     eax, 0C0190052h
0x14000ff25  add     rsp, 38h
0x14000ff29  pop     r14
0x14000ff2b  pop     rdi
0x14000ff2c  pop     rsi
0x14000ff2d  pop     rbx
0x14000ff2e  retn
0x14000ff30  mov     [rsp+58h+arg_0], rdi
0x14000ff35  mov     ebx, 0C0190013h
0x14000ff3a  mov     rdx, r14
0x14000ff3d  mov     rcx, [rcx]
0x14000ff40  call    TmpAdjustVirtualClock
0x14000ff45  mov     rcx, rdi
0x14000ff48  call    TmpAcquireTransactionMutex
0x14000ff4d  nop
0x14000ff4e  mov     rcx, rdi; Object
0x14000ff51  call    cs:__imp_ObfReferenceObject
0x14000ff58  nop     dword ptr [rax+rax+00h]
0x14000ff5d  mov     eax, [rsi+0ACh]
0x14000ff63  test    al, 1
0x14000ff65  jnz     short loc_14000FF71
0x14000ff67  mov     ebx, 0C0190033h
0x14000ff6c  jmp     loc_140010095
0x14000ff71  mov     eax, [rsi+0B0h]
0x14000ff77  test    al, 40h
0x14000ff79  jnz     short loc_14000FF85
0x14000ff7b  mov     ebx, 0C0190057h
0x14000ff80  jmp     loc_140010095
0x14000ff85  mov     eax, [rdi+0C4h]
0x14000ff8b  test    al, 2
0x14000ff8d  jnz     loc_140010095
0x14000ff93  mov     ecx, [rdi+0C0h]
0x14000ff99  cmp     ecx, 1
0x14000ff9c  jnz     short loc_14000FFFD
0x14000ff9e  lock or dword ptr [rdi+0C4h], 2
0x14000ffa6  mov     [rsp+58h+Timeout], 0; Timeout
0x14000ffaf  xor     r9d, r9d; Alertable
0x14000ffb2  xor     r8d, r8d; WaitMode
0x14000ffb5  xor     edx, edx; WaitReason
0x14000ffb7  lea     rcx, [rsi+40h]; Object
0x14000ffbb  call    cs:__imp_KeWaitForSingleObject
0x14000ffc2  nop     dword ptr [rax+rax+00h]
0x14000ffc7  mov     eax, [rsi+0ACh]
0x14000ffcd  test    al, 2
0x14000ffcf  jz      short loc_14000FFDF
0x14000ffd1  lock and dword ptr [rsi+0ACh], 0FFFFFFFDh
0x14000ffd9  dec     dword ptr [rdi+0DCh]
0x14000ffdf  xor     edx, edx; Wait
0x14000ffe1  lea     rcx, [rsi+40h]; Mutex
0x14000ffe5  call    cs:__imp_KeReleaseMutex
0x14000ffec  nop     dword ptr [rax+rax+00h]
0x14000fff1  xor     edx, edx; Wait
0x14000fff3  mov     rcx, rdi; Transaction
0x14000fff6  call    TmCommitTransactionExt
0x14000fffb  jmp     short loc_140010069
0x14000fffd  lea     eax, [rcx-3]
0x140010000  cmp     eax, 1
0x140010003  jbe     short loc_140010014
0x140010005  cmp     ecx, 7
0x140010008  jnz     short loc_14001006B
0x14001000a  mov     ebx, 0C0190003h
0x14001000f  jmp     loc_140010095
0x140010014  mov     [rsp+58h+Timeout], 0; Timeout
0x14001001d  xor     r9d, r9d; Alertable
0x140010020  xor     r8d, r8d; WaitMode
0x140010023  xor     edx, edx; WaitReason
0x140010025  lea     rcx, [rsi+40h]; Object
0x140010029  call    cs:__imp_KeWaitForSingleObject
0x140010030  nop     dword ptr [rax+rax+00h]
0x140010035  mov     eax, [rsi+0ACh]
0x14001003b  test    al, 2
0x14001003d  jz      short loc_14001004D
0x14001003f  lock and dword ptr [rsi+0ACh], 0FFFFFFFDh
0x140010047  dec     dword ptr [rdi+0DCh]
0x14001004d  xor     edx, edx; Wait
0x14001004f  lea     rcx, [rsi+40h]; Mutex
0x140010053  call    cs:__imp_KeReleaseMutex
0x14001005a  nop     dword ptr [rax+rax+00h]
0x14001005f  xor     edx, edx
0x140010061  mov     rcx, rdi; Object
0x140010064  call    TmpTxActionDoCommit
0x140010069  mov     ebx, eax
0x14001006b  mov     eax, [rdi+0C4h]
0x140010071  bt      eax, 1Bh
0x140010075  jnb     short loc_14001007E
0x140010077  mov     ebx, 40190001h
0x14001007c  jmp     short loc_140010095
0x14001007e  cmp     dword ptr [rdi+0C0h], 6
0x140010085  jz      short loc_140010090
0x140010087  cmp     dword ptr [rdi+1F8h], 3
0x14001008e  jnz     short loc_140010095
0x140010090  mov     ebx, 0C0190015h
0x140010095  mov     rcx, [rdi+58h]
0x140010099  add     rcx, 20h ; ' '; Mutex
0x14001009d  xor     edx, edx; Wait
0x14001009f  call    cs:__imp_KeReleaseMutex
0x1400100a6  nop     dword ptr [rax+rax+00h]
0x1400100ab  mov     rcx, rdi; Object
0x1400100ae  call    cs:__imp_ObfDereferenceObject
0x1400100b5  nop     dword ptr [rax+rax+00h]
0x1400100ba  mov     eax, ebx
0x1400100bc  jmp     loc_14000FF25
0x140021c5e  push    rbx
0x140021c60  push    rbp
0x140021c61  sub     rsp, 38h
0x140021c65  mov     rbp, rdx
0x140021c68  mov     rbx, [rbp+60h]
0x140021c6c  mov     rcx, [rbx+58h]
0x140021c70  add     rcx, 20h ; ' '; Mutex
0x140021c74  xor     edx, edx; Wait
0x140021c76  call    cs:__imp_KeReleaseMutex
0x140021c7d  nop     dword ptr [rax+rax+00h]
0x140021c82  mov     rcx, rbx; Object
0x140021c85  call    cs:__imp_ObfDereferenceObject
0x140021c8c  nop     dword ptr [rax+rax+00h]
0x140021c91  nop
0x140021c92  add     rsp, 38h
0x140021c96  pop     rbp
0x140021c97  pop     rbx
0x140021c98  retn
```
