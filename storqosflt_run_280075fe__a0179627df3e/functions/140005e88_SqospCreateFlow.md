# SqospCreateFlow

- ea: `0x140005e88`
- end: `0x140006033`
- name: `SqospCreateFlow`
- size: `427`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x140003870`

## callees

- `0x140003910`
- `0x140003ec0`
- `0x1400046d0`
- `0x14000507c`
- `0x140005de4`
- `0x140005e88`
- `0x140009240`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x140006014`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140006014`
- `ntoskrnl!PcwCreateInstance` at `0x140005ff3`
- `ntoskrnl!PcwCreateInstance` at `0x140005ff3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005f98`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005fad`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005f98`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005fad`
- `ntoskrnl!KeInitializeSpinLock` at `0x140005edc`
- `ntoskrnl!KeInitializeSpinLock` at `0x140005edc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005f0c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005f21`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005f0c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005f21`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140005ea6`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140005ea6`

## pseudocode

```c
__int64 __fastcall SqospCreateFlow(_BYTE *SpinLock, __int64 a2, __int64 a3)
{
  __int64 Flow; // rsi
  KSPIN_LOCK *v7; // rax
  KSPIN_LOCK *v8; // rbx
  char v9; // r15
  PKSPIN_LOCK *v10; // rdx
  struct _PCW_DATA Data; // [rsp+30h] [rbp-48h] BYREF

  Flow = 0;
  v7 = (KSPIN_LOCK *)ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(a2 + 48));
  v8 = v7;
  if ( v7 )
  {
    memset(v7, 0, 0x240u);
    *((_BYTE *)v8 + 441) = 1;
    KeInitializeSpinLock(v8 + 60);
    if ( (int)SqospBuildFlowName(a2, a3, v8 + 7) < 0 )
      goto LABEL_12;
    v9 = 0;
    *(_BYTE *)(a2 + 840) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 832));
    SpinLock[8] = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)SpinLock);
    Flow = SqospFindFlow(SpinLock, a2);
    if ( !Flow )
    {
      v8[1] = (KSPIN_LOCK)SpinLock;
      v10 = (PKSPIN_LOCK *)*((_QWORD *)SpinLock + 14);
      if ( *v10 != (PKSPIN_LOCK)(SpinLock + 104) )
        __fastfail(3u);
      Flow = (__int64)v8;
      v9 = 1;
      v8 = 0;
      *(_QWORD *)(Flow + 40) = SpinLock + 104;
      *(_QWORD *)(Flow + 48) = v10;
      *v10 = (PKSPIN_LOCK)(Flow + 40);
      *((_QWORD *)SpinLock + 14) = Flow + 40;
      ++*((_DWORD *)SpinLock + 30);
      BalanceInitializeFlow(Flow, a2);
      if ( *((_DWORD *)SpinLock + 33) == 1 )
        SqospAssignClientIoRates(SpinLock);
    }
    KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, SpinLock[8]);
    KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 832), *(_BYTE *)(a2 + 840));
    if ( v9 && HIBYTE(word_14000D2A8) )
    {
      Data.Data = (const void *)Flow;
      Data.Size = 576;
      PcwCreateInstance((PPCW_INSTANCE *)(Flow + 16), SqosPcFlowCounterSet, (PCUNICODE_STRING)(Flow + 56), 1u, &Data);
    }
    if ( v8 )
    {
LABEL_12:
      SqospFreeUnicodeString(v8 + 7);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(a2 + 48), v8);
    }
  }
  return Flow;
}

```

## disassembly

```asm
0x140005e88  push    rbx
0x140005e8a  push    rbp
0x140005e8b  push    rsi
0x140005e8c  push    rdi
0x140005e8d  push    r12
0x140005e8f  push    r14
0x140005e91  push    r15
0x140005e93  sub     rsp, 40h
0x140005e97  mov     rdi, rcx
0x140005e9a  mov     r15, r8
0x140005e9d  lea     rcx, [rdx+30h]; Lookaside
0x140005ea1  mov     rbp, rdx
0x140005ea4  xor     esi, esi
0x140005ea6  call    cs:__imp_ExAllocateFromLookasideListEx
0x140005ead  nop     dword ptr [rax+rax+00h]
0x140005eb2  mov     rbx, rax
0x140005eb5  test    rax, rax
0x140005eb8  jz      loc_140006020
0x140005ebe  xor     edx, edx; Val
0x140005ec0  mov     r8d, 240h; Size
0x140005ec6  mov     rcx, rax; void *
0x140005ec9  call    memset
0x140005ece  lea     rcx, [rbx+1E0h]; SpinLock
0x140005ed5  mov     byte ptr [rbx+1B9h], 1
0x140005edc  call    cs:__imp_KeInitializeSpinLock
0x140005ee3  nop     dword ptr [rax+rax+00h]
0x140005ee8  lea     r8, [rbx+38h]
0x140005eec  mov     rdx, r15
0x140005eef  mov     rcx, rbp
0x140005ef2  call    SqospBuildFlowName
0x140005ef7  test    eax, eax
0x140005ef9  js      loc_140006004
0x140005eff  lea     r12, [rbp+340h]
0x140005f06  xor     r15b, r15b
0x140005f09  mov     rcx, r12; SpinLock
0x140005f0c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005f13  nop     dword ptr [rax+rax+00h]
0x140005f18  mov     rcx, rdi; SpinLock
0x140005f1b  mov     [rbp+348h], al
0x140005f21  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005f28  nop     dword ptr [rax+rax+00h]
0x140005f2d  mov     rdx, rbp
0x140005f30  mov     rcx, rdi
0x140005f33  mov     [rdi+8], al
0x140005f36  call    SqospFindFlow
0x140005f3b  mov     rsi, rax
0x140005f3e  test    rax, rax
0x140005f41  jnz     short loc_140005F92
0x140005f43  lea     rcx, [rdi+68h]
0x140005f47  mov     [rbx+8], rdi
0x140005f4b  mov     rdx, [rcx+8]
0x140005f4f  cmp     [rdx], rcx
0x140005f52  jz      short loc_140005F59
0x140005f54  lea     ecx, [rax+3]
0x140005f57  int     29h; Win8: RtlFailFast(ecx)
0x140005f59  mov     rsi, rbx
0x140005f5c  mov     r15b, 1
0x140005f5f  xor     ebx, ebx
0x140005f61  lea     rax, [rsi+28h]
0x140005f65  mov     [rax], rcx
0x140005f68  mov     [rax+8], rdx
0x140005f6c  mov     [rdx], rax
0x140005f6f  mov     rdx, rbp
0x140005f72  mov     [rcx+8], rax
0x140005f76  mov     rcx, rsi
0x140005f79  inc     dword ptr [rdi+78h]
0x140005f7c  call    BalanceInitializeFlow
0x140005f81  cmp     dword ptr [rdi+84h], 1
0x140005f88  jnz     short loc_140005F92
0x140005f8a  mov     rcx, rdi
0x140005f8d  call    SqospAssignClientIoRates
0x140005f92  mov     dl, [rdi+8]; NewIrql
0x140005f95  mov     rcx, rdi; SpinLock
0x140005f98  call    cs:__imp_KeReleaseSpinLock
0x140005f9f  nop     dword ptr [rax+rax+00h]
0x140005fa4  mov     dl, [rbp+348h]; NewIrql
0x140005faa  mov     rcx, r12; SpinLock
0x140005fad  call    cs:__imp_KeReleaseSpinLock
0x140005fb4  nop     dword ptr [rax+rax+00h]
0x140005fb9  test    r15b, r15b
0x140005fbc  jz      short loc_140005FFF
0x140005fbe  cmp     byte ptr cs:word_14000D2A8+1, 0
0x140005fc5  jz      short loc_140005FFF
0x140005fc7  mov     rdx, cs:SqosPcFlowCounterSet; Registration
0x140005fce  lea     rax, [rsp+78h+var_48]
0x140005fd3  lea     r8, [rsi+38h]; Name
0x140005fd7  mov     [rsp+78h+Data], rax; Data
0x140005fdc  lea     rcx, [rsi+10h]; Instance
0x140005fe0  mov     [rsp+78h+var_48.Data], rsi
0x140005fe5  mov     r9d, 1; Count
0x140005feb  mov     [rsp+78h+var_48.Size], 240h
0x140005ff3  call    cs:__imp_PcwCreateInstance
0x140005ffa  nop     dword ptr [rax+rax+00h]
0x140005fff  test    rbx, rbx
0x140006002  jz      short loc_140006020
0x140006004  lea     rcx, [rbx+38h]
0x140006008  call    SqospFreeUnicodeString
0x14000600d  mov     rdx, rbx; Entry
0x140006010  lea     rcx, [rbp+30h]; Lookaside
0x140006014  call    cs:__imp_ExFreeToLookasideListEx
0x14000601b  nop     dword ptr [rax+rax+00h]
0x140006020  mov     rax, rsi
0x140006023  add     rsp, 40h
0x140006027  pop     r15
0x140006029  pop     r14
0x14000602b  pop     r12
0x14000602d  pop     rdi
0x14000602e  pop     rsi
0x14000602f  pop     rbp
0x140006030  pop     rbx
0x140006031  retn
```
