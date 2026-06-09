# VmsOmNicPvtCancelLinkChangeIrp

- ea: `0x140089fd0`
- end: `0x14008a250`
- name: `VmsOmNicPvtCancelLinkChangeIrp`
- size: `640`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140027a64`
- `0x140037820`
- `0x14003c378`
- `0x140040c40`
- `0x140043a58`
- `0x140046e5c`
- `0x14006b084`
- `0x14008497c`
- `0x140089fd0`
- `0x14008a258`
- `0x1400f2a6c`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14008a067`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14008a067`
- `ntoskrnl!IofCompleteRequest` at `0x14008a1f2`
- `ntoskrnl!IofCompleteRequest` at `0x14008a1f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008a11d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008a1b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008a11d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008a1b3`
- `NDIS!NdisReleaseRWLock` at `0x14008a193`
- `NDIS!NdisReleaseRWLock` at `0x14008a193`

## string_xrefs

- `0x14008a006`: `VmsOmNicPvtCancelLinkChangeIrp`
- `0x14008a04c`: `VmsOmNicPvtCancelLinkChangeIrp`
- `0x14008a20f`: `VmsOmNicPvtCancelLinkChangeIrp`

## pseudocode

```c
__int64 __fastcall VmsOmNicPvtCancelLinkChangeIrp(__int64 a1, IRP *a2)
{
  _LIST_ENTRY *Flink; // r15
  char v3; // r14
  _LIST_ENTRY *v5; // rbp
  int v6; // edx
  _LIST_ENTRY *v7; // rbx
  _LIST_ENTRY *v8; // rcx
  _LIST_ENTRY *Blink; // rax
  int v10; // edx
  int v11; // edx
  struct _LOCK_STATE_EX LockState; // [rsp+88h] [rbp+10h] BYREF
  _LIST_ENTRY *v14; // [rsp+90h] [rbp+18h] BYREF

  Flink = a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink;
  v14 = 0;
  v3 = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v14 = Flink[1].Flink;
  VmsWppTraceApi(
    (unsigned int)&v14,
    (unsigned int)"VmsOmNicPvtCancelLinkChangeIrp",
    (unsigned int)"onecore\\vm\\dv\\net\\nvsp\\driver\\ob\\vmsobnic.c",
    5763,
    4,
    0,
    0,
    1,
    0);
  v5 = Flink->Flink;
  VmsIfrInfoParamsObjNicSafe(
    (_DWORD)Flink + 16,
    Flink->Flink,
    (unsigned int)"VmsOmNicPvtCancelLinkChangeIrp",
    (unsigned int)"onecore\\vm\\dv\\net\\nvsp\\driver\\ob\\vmsobnic.c",
    5766,
    1);
  IoReleaseCancelSpinLock(a2->CancelIrql);
  VmsOmObjectLockExclusive(v5, &LockState, 0);
  v7 = v5[119].Flink;
  if ( v7 == &v5[119] )
  {
    LOBYTE(v6) = 2;
    WPP_RECORDER_SF_(VmsIfrLog, v6, 20, 111, (__int64)WPP_bda91bcb57e433144f485e69e8239e42_Traceguids);
  }
  else
  {
    while ( (IRP *)v7[1].Flink != a2 )
    {
      v7 = v7->Flink;
      if ( v7 == &v5[119] )
      {
        LOBYTE(v6) = 2;
        WPP_RECORDER_SF_I(VmsIfrLog, v6, 20, 113, (__int64)WPP_bda91bcb57e433144f485e69e8239e42_Traceguids, (char)a2);
        WPP_RECORDER_SF_s(
          VmsIfrNicLog,
          v10,
          19,
          114,
          (__int64)WPP_bda91bcb57e433144f485e69e8239e42_Traceguids,
          "pendingIrpFound == TRUE");
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
        goto LABEL_11;
      }
    }
    LOBYTE(v6) = 4;
    WPP_RECORDER_SF_qq(
      VmsIfrNicLog,
      v6,
      18,
      112,
      (__int64)WPP_bda91bcb57e433144f485e69e8239e42_Traceguids,
      (char)a2,
      (char)v5);
    v8 = v7->Flink;
    if ( v7->Flink->Blink != v7 || (Blink = v7->Blink, Blink->Flink != v7) )
      __fastfail(3u);
    Blink->Flink = v8;
    v8->Blink = Blink;
    v3 = 1;
    ExFreePoolWithTag(v7, 0);
  }
LABEL_11:
  NdisReleaseRWLock((PNDIS_RW_LOCK_EX)v5[3].Blink, &LockState);
  if ( v3 == 1 )
  {
    LibIoctlDeinitializeOperation(Flink->Blink);
    ExFreePoolWithTag(Flink, 0);
    a2->IoStatus.Status = -1073741536;
    LOBYTE(v11) = 4;
    WPP_RECORDER_SF_dq(
      VmsIfrNicLog,
      v11,
      18,
      115,
      (__int64)WPP_bda91bcb57e433144f485e69e8239e42_Traceguids,
      32,
      (char)v5);
    IofCompleteRequest(a2, 0);
  }
  return VmsWppTraceApi(
           (unsigned int)&v14,
           (unsigned int)"VmsOmNicPvtCancelLinkChangeIrp",
           (unsigned int)"onecore\\vm\\dv\\net\\nvsp\\driver\\ob\\vmsobnic.c",
           5828,
           4,
           0,
           0,
           0,
           0);
}

```

## disassembly

```asm
0x140089fd0  mov     r11, rsp
0x140089fd3  mov     [r11+8], rbx
0x140089fd7  push    rbp
0x140089fd8  push    rsi
0x140089fd9  push    rdi
0x140089fda  push    r14
0x140089fdc  push    r15
0x140089fde  sub     rsp, 50h
0x140089fe2  mov     r15, [rdx+78h]
0x140089fe6  lea     r8, aOnecoreVmDvNet_5; "onecore\\vm\\dv\\net\\nvsp\\driver\\ob"...
0x140089fed  xor     eax, eax
0x140089fef  lea     rcx, [r11+18h]
0x140089ff3  mov     [r11+18h], rax
0x140089ff7  xor     r14b, r14b
0x140089ffa  mov     [r11-38h], r14b
0x140089ffe  mov     rsi, rdx
0x14008a001  mov     [rsp+78h+var_40], 1
0x14008a006  lea     rdx, aVmsomnicpvtcan_0; "VmsOmNicPvtCancelLinkChangeIrp"
0x14008a00d  mov     [r11-48h], r14b
0x14008a011  mov     r9d, 1683h
0x14008a017  mov     [r11+10h], ax
0x14008a01c  mov     [r11+12h], al
0x14008a020  mov     rax, [r15+10h]
0x14008a024  mov     dword ptr [rsp+78h+var_50], 0
0x14008a02c  mov     [r11+18h], rax
0x14008a030  mov     byte ptr [rsp+78h+var_58], 4
0x14008a035  call    VmsWppTraceApi
0x14008a03a  mov     rbp, [r15]
0x14008a03d  lea     r9, aOnecoreVmDvNet_5; "onecore\\vm\\dv\\net\\nvsp\\driver\\ob"...
0x14008a044  mov     rdx, rbp
0x14008a047  mov     byte ptr [rsp+78h+var_50], 1
0x14008a04c  lea     r8, aVmsomnicpvtcan_0; "VmsOmNicPvtCancelLinkChangeIrp"
0x14008a053  mov     dword ptr [rsp+78h+var_58], 1686h
0x14008a05b  lea     rcx, [r15+10h]
0x14008a05f  call    VmsIfrInfoParamsObjNicSafe
0x14008a064  mov     cl, [rsi+45h]; Irql
0x14008a067  call    cs:__imp_IoReleaseCancelSpinLock
0x14008a06e  nop     dword ptr [rax+rax+00h]
0x14008a073  xor     r8d, r8d
0x14008a076  lea     rdx, [rsp+78h+LockState]
0x14008a07e  mov     rcx, rbp
0x14008a081  call    VmsOmObjectLockExclusive
0x14008a086  lea     rax, [rbp+770h]
0x14008a08d  mov     rbx, [rax]
0x14008a090  cmp     rbx, rax
0x14008a093  jnz     short loc_14008A0C3
0x14008a095  mov     rcx, cs:VmsIfrLog
0x14008a09c  lea     rdi, WPP_bda91bcb57e433144f485e69e8239e42_Traceguids
0x14008a0a3  mov     r9d, 6Fh ; 'o'
0x14008a0a9  mov     [rsp+78h+var_58], rdi
0x14008a0ae  mov     dl, 2
0x14008a0b0  lea     r8d, [r9-5Bh]
0x14008a0b4  call    WPP_RECORDER_SF_
0x14008a0b9  jmp     loc_14008A187
0x14008a0be  cmp     rbx, rax
0x14008a0c1  jz      short loc_14008A132
0x14008a0c3  cmp     [rbx+10h], rsi
0x14008a0c7  jz      short loc_14008A0CE
0x14008a0c9  mov     rbx, [rbx]
0x14008a0cc  jmp     short loc_14008A0BE
0x14008a0ce  mov     rcx, cs:VmsIfrNicLog
0x14008a0d5  lea     rdi, WPP_bda91bcb57e433144f485e69e8239e42_Traceguids
0x14008a0dc  mov     r9d, 70h ; 'p'
0x14008a0e2  mov     [rsp+78h+var_48], rbp
0x14008a0e7  mov     [rsp+78h+var_50], rsi
0x14008a0ec  mov     dl, 4
0x14008a0ee  mov     [rsp+78h+var_58], rdi
0x14008a0f3  lea     r8d, [r9-5Eh]
0x14008a0f7  call    WPP_RECORDER_SF_qq
0x14008a0fc  mov     rcx, [rbx]
0x14008a0ff  cmp     [rcx+8], rbx
0x14008a103  jnz     short loc_14008A12B
0x14008a105  mov     rax, [rbx+8]
0x14008a109  cmp     [rax], rbx
0x14008a10c  jnz     short loc_14008A12B
0x14008a10e  mov     [rax], rcx
0x14008a111  xor     edx, edx; Tag
0x14008a113  mov     [rcx+8], rax
0x14008a117  mov     r14b, 1
0x14008a11a  mov     rcx, rbx; P
0x14008a11d  call    cs:__imp_ExFreePoolWithTag
0x14008a124  nop     dword ptr [rax+rax+00h]
0x14008a129  jmp     short loc_14008A187
0x14008a12b  mov     ecx, 3
0x14008a130  int     29h; Win8: RtlFailFast(ecx)
0x14008a132  mov     rcx, cs:VmsIfrLog
0x14008a139  lea     rdi, WPP_bda91bcb57e433144f485e69e8239e42_Traceguids
0x14008a140  mov     r9d, 71h ; 'q'
0x14008a146  mov     [rsp+78h+var_50], rsi
0x14008a14b  mov     dl, 2
0x14008a14d  mov     [rsp+78h+var_58], rdi
0x14008a152  lea     r8d, [r9-5Dh]
0x14008a156  call    WPP_RECORDER_SF_I
0x14008a15b  mov     rcx, cs:VmsIfrNicLog
0x14008a162  lea     rax, aPendingirpfoun; "pendingIrpFound == TRUE"
0x14008a169  mov     r9d, 72h ; 'r'
0x14008a16f  mov     [rsp+78h+var_50], rax
0x14008a174  mov     [rsp+78h+var_58], rdi
0x14008a179  lea     r8d, [r9-5Fh]
0x14008a17d  call    WPP_RECORDER_SF_s
0x14008a182  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "pendingIrpFound == 1")
0x14008a187  mov     rcx, [rbp+38h]; Lock
0x14008a18b  lea     rdx, [rsp+78h+LockState]; LockState
0x14008a193  call    cs:__imp_NdisReleaseRWLock
0x14008a19a  nop     dword ptr [rax+rax+00h]
0x14008a19f  cmp     r14b, 1
0x14008a1a3  jnz     short loc_14008A1FE
0x14008a1a5  mov     rcx, [r15+8]
0x14008a1a9  call    LibIoctlDeinitializeOperation
0x14008a1ae  xor     edx, edx; Tag
0x14008a1b0  mov     rcx, r15; P
0x14008a1b3  call    cs:__imp_ExFreePoolWithTag
0x14008a1ba  nop     dword ptr [rax+rax+00h]
0x14008a1bf  mov     eax, 0C0000120h
0x14008a1c4  mov     [rsi+30h], eax
0x14008a1c7  mov     rcx, cs:VmsIfrNicLog
0x14008a1ce  mov     r9d, 73h ; 's'
0x14008a1d4  mov     [rsp+78h+var_48], rbp
0x14008a1d9  mov     dl, 4
0x14008a1db  mov     dword ptr [rsp+78h+var_50], eax
0x14008a1df  mov     [rsp+78h+var_58], rdi
0x14008a1e4  lea     r8d, [r9-61h]
0x14008a1e8  call    WPP_RECORDER_SF_dq
0x14008a1ed  xor     edx, edx; PriorityBoost
0x14008a1ef  mov     rcx, rsi; Irp
0x14008a1f2  call    cs:__imp_IofCompleteRequest
0x14008a1f9  nop     dword ptr [rax+rax+00h]
0x14008a1fe  mov     [rsp+78h+var_38], 0
0x14008a203  lea     r8, aOnecoreVmDvNet_5; "onecore\\vm\\dv\\net\\nvsp\\driver\\ob"...
0x14008a20a  mov     [rsp+78h+var_40], 0
0x14008a20f  lea     rdx, aVmsomnicpvtcan_0; "VmsOmNicPvtCancelLinkChangeIrp"
0x14008a216  mov     byte ptr [rsp+78h+var_48], 0
0x14008a21b  lea     rcx, [rsp+78h+arg_10]
0x14008a223  mov     dword ptr [rsp+78h+var_50], 0
0x14008a22b  mov     r9d, 16C4h
0x14008a231  mov     byte ptr [rsp+78h+var_58], 4
0x14008a236  call    VmsWppTraceApi
0x14008a23b  mov     rbx, [rsp+78h+arg_0]
0x14008a243  add     rsp, 50h
0x14008a247  pop     r15
0x14008a249  pop     r14
0x14008a24b  pop     rdi
0x14008a24c  pop     rsi
0x14008a24d  pop     rbp
0x14008a24e  retn
```
