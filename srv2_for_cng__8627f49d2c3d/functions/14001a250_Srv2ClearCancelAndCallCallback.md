# Srv2ClearCancelAndCallCallback

- ea: `0x14001a250`
- end: `0x14001a3b5`
- name: `Srv2ClearCancelAndCallCallback`
- size: `357`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140004020`
- `0x140004960`
- `0x140005070`
- `0x1400051dc`
- `0x14001a250`
- `0x1400384d0`

## import_xrefs

- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14001a2f2`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14001a2f2`
- `ntoskrnl!RtlInitAnsiString` at `0x14001a370`
- `ntoskrnl!RtlInitAnsiString` at `0x14001a370`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14001a30e`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14001a30e`
- `HAL!KeQueryPerformanceCounter` at `0x14001a33d`
- `HAL!KeQueryPerformanceCounter` at `0x14001a33d`

## string_xrefs

- `0x14001a2d9`: `Srv2PostToThreadPool`

## pseudocode

```c
__int64 __fastcall Srv2ClearCancelAndCallCallback(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rax
  __int64 v5; // rbx
  bool v7; // zf
  __int64 v8; // rbx
  __int64 v9; // rbx
  LARGE_INTEGER PerformanceCounter; // rax
  __int64 v11; // rax
  int v12; // edx
  int v13; // ecx
  char v14; // [rsp+20h] [rbp-38h]
  struct _STRING DestinationString; // [rsp+40h] [rbp-18h] BYREF

  if ( _InterlockedCompareExchange((volatile signed __int32 *)(a3 + 476), 0, 1) == 1 )
  {
    v4 = *(_QWORD *)(a3 + 120);
    v5 = a3 + 584;
    DestinationString = 0;
    *(_BYTE *)(v4 + 68) = 0;
    if ( *(_BYTE *)(a3 + 600) )
    {
      PerformanceCounter = KeQueryPerformanceCounter(0);
      v11 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))SRV2_PERF_UPDATE_PERF_COUNTER)(
              v5,
              0,
              (LARGE_INTEGER)PerformanceCounter.QuadPart);
      *(_BYTE *)(v5 + 128) = 0;
      *(_QWORD *)(v5 + 136) = v11;
      RtlInitAnsiString(&DestinationString, "Srv2ClearCancelAndCallCallback");
      if ( (Microsoft_Windows_SMBServerEnableBits & 4) != 0 )
        McTemplateK0qqhsr2_EtwWriteTransfer(
          v13,
          v12,
          v5,
          0,
          56,
          DestinationString.Length,
          (__int64)DestinationString.Buffer);
    }
    (*(void (__fastcall **)(__int64))(a3 + 48))(a3);
  }
  else
  {
    v7 = *(_DWORD *)(a3 + 8) == 5;
    *(_QWORD *)(a3 + 88) = *(_QWORD *)(a3 + 48);
    *(_QWORD *)(a3 + 48) = Srv2PostOnCompletionAndClearCancelCallback;
    *(_DWORD *)(a3 + 72) = 0;
    if ( v7 )
    {
      v14 = 1;
      LOBYTE(a2) = 1;
      SRV2_PERF_ENTER_EX(a3 + 584, a2, 391, "Srv2PostToThreadPool", v14);
    }
    v8 = *(_QWORD *)(*(_QWORD *)(a3 + 64) + 136LL);
    v9 = *(_QWORD *)(v8 + 8LL * KeGetCurrentNodeNumber() + 8);
    if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)(v9 + 16), (PSLIST_ENTRY)(a3 + 32)) && *(_WORD *)(v9 + 66) )
      RfspThreadPoolNodeWakeIdleWorker((struct _KEVENT *)v9);
  }
  return 3221225494LL;
}

```

## disassembly

```asm
0x14001a250  mov     [rsp+arg_0], rbx
0x14001a255  push    rdi
0x14001a256  sub     rsp, 50h
0x14001a25a  xor     ecx, ecx; PerformanceFrequency
0x14001a25c  mov     rdi, r8
0x14001a25f  lea     eax, [rcx+1]
0x14001a262  lock cmpxchg [r8+1DCh], ecx
0x14001a26b  jnz     short loc_14001A2A9
0x14001a26d  mov     rax, [r8+78h]
0x14001a271  lea     rbx, [r8+248h]
0x14001a278  xorps   xmm0, xmm0
0x14001a27b  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x14001a280  mov     [rax+44h], cl
0x14001a283  cmp     [rbx+10h], cl
0x14001a286  jnz     loc_14001A33D
0x14001a28c  mov     rax, [rdi+30h]
0x14001a290  mov     rcx, rdi
0x14001a293  call    _guard_dispatch_icall
0x14001a298  mov     rbx, [rsp+58h+arg_0]
0x14001a29d  mov     eax, 0C0000016h
0x14001a2a2  add     rsp, 50h
0x14001a2a6  pop     rdi
0x14001a2a7  retn
0x14001a2a9  cmp     dword ptr [r8+8], 5
0x14001a2ae  mov     rax, [r8+30h]
0x14001a2b2  mov     [r8+58h], rax
0x14001a2b6  lea     rax, Srv2PostOnCompletionAndClearCancelCallback
0x14001a2bd  mov     [r8+30h], rax
0x14001a2c1  mov     [r8+48h], ecx
0x14001a2c5  jnz     short loc_14001A2E7
0x14001a2c7  lea     rcx, [r8+248h]
0x14001a2ce  mov     [rsp+58h+var_38], 1
0x14001a2d3  mov     r8d, 187h
0x14001a2d9  lea     r9, SourceString; "Srv2PostToThreadPool"
0x14001a2e0  mov     dl, 1
0x14001a2e2  call    SRV2_PERF_ENTER_EX
0x14001a2e7  mov     rax, [rdi+40h]
0x14001a2eb  mov     rbx, [rax+88h]
0x14001a2f2  call    cs:__imp_KeGetCurrentNodeNumber
0x14001a2f9  nop     dword ptr [rax+rax+00h]
0x14001a2fe  movzx   eax, ax
0x14001a301  lea     rdx, [rdi+20h]; ListEntry
0x14001a305  mov     rbx, [rbx+rax*8+8]
0x14001a30a  lea     rcx, [rbx+10h]; ListHead
0x14001a30e  call    cs:__imp_ExpInterlockedPushEntrySList
0x14001a315  nop     dword ptr [rax+rax+00h]
0x14001a31a  test    rax, rax
0x14001a31d  jnz     loc_14001A298
0x14001a323  movzx   edx, word ptr [rbx+42h]
0x14001a327  cmp     ax, dx
0x14001a32a  jz      loc_14001A298
0x14001a330  mov     rcx, rbx
0x14001a333  call    RfspThreadPoolNodeWakeIdleWorker
0x14001a338  jmp     loc_14001A298
0x14001a33d  call    cs:__imp_KeQueryPerformanceCounter
0x14001a344  nop     dword ptr [rax+rax+00h]
0x14001a349  xor     edx, edx
0x14001a34b  mov     rcx, rbx
0x14001a34e  mov     r8, rax
0x14001a351  call    SRV2_PERF_UPDATE_PERF_COUNTER
0x14001a356  lea     rdx, aSrv2clearcance; "Srv2ClearCancelAndCallCallback"
0x14001a35d  mov     byte ptr [rbx+80h], 0
0x14001a364  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x14001a369  mov     [rbx+88h], rax
0x14001a370  call    cs:__imp_RtlInitAnsiString
0x14001a377  nop     dword ptr [rax+rax+00h]
0x14001a37c  test    cs:Microsoft_Windows_SMBServerEnableBits, 4
0x14001a383  jz      loc_14001A28C
0x14001a389  mov     rax, [rsp+58h+DestinationString.Buffer]
0x14001a38e  xor     r9d, r9d
0x14001a391  mov     [rsp+58h+var_28], rax
0x14001a396  mov     r8, rbx
0x14001a399  movzx   eax, [rsp+58h+DestinationString.Length]
0x14001a39e  mov     [rsp+58h+var_30], ax
0x14001a3a3  mov     dword ptr [rsp+58h+var_38], 938h
0x14001a3ab  call    McTemplateK0qqhsr2_EtwWriteTransfer
0x14001a3b0  jmp     loc_14001A28C
```
