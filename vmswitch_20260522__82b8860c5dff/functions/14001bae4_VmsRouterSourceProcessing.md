# VmsRouterSourceProcessing

- ea: `0x14001bae4`
- end: `0x14001bf16`
- name: `VmsRouterSourceProcessing`
- size: `1074`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14001b270`

## callees

- `0x14001b9fc`
- `0x14001bae4`
- `0x14001c850`
- `0x14001d1b8`
- `0x140027a64`
- `0x14002af04`
- `0x14006b084`
- `0x14008497c`
- `0x14008d5ac`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14001bb6d`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001bb98`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001bdee`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001be3a`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001bb6d`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001bb98`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001bdee`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001be3a`
- `NDIS!NdisAcquireRWLockRead` at `0x14001bb8c`
- `NDIS!NdisAcquireRWLockRead` at `0x14001bbb7`
- `NDIS!NdisAcquireRWLockRead` at `0x14001bb8c`
- `NDIS!NdisAcquireRWLockRead` at `0x14001bbb7`
- `NDIS!NdisReleaseRWLock` at `0x14001bcc5`
- `NDIS!NdisReleaseRWLock` at `0x14001bcd9`
- `NDIS!NdisReleaseRWLock` at `0x14001bf05`
- `NDIS!NdisReleaseRWLock` at `0x14001bcc5`
- `NDIS!NdisReleaseRWLock` at `0x14001bcd9`
- `NDIS!NdisReleaseRWLock` at `0x14001bf05`

## pseudocode

```c
_QWORD *__fastcall VmsRouterSourceProcessing(__int64 a1, __int64 a2, __int64 a3, char a4, _QWORD *a5, _QWORD *a6)
{
  UCHAR v7; // r8
  __int64 v11; // r12
  bool v12; // r15
  __int64 v13; // rbx
  int v14; // edx
  int v15; // edx
  int v16; // edx
  __int64 v17; // rcx
  __int64 v18; // r8
  _QWORD *result; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // [rsp+60h] [rbp-19h] BYREF
  __int64 v25; // [rsp+68h] [rbp-11h] BYREF
  __int64 *v26; // [rsp+70h] [rbp-9h] BYREF
  _UNKNOWN *retaddr; // [rsp+C8h] [rbp+4Fh]
  struct _LOCK_STATE_EX LockState; // [rsp+D0h] [rbp+57h] BYREF
  struct _LOCK_STATE_EX v29; // [rsp+D8h] [rbp+5Fh] BYREF
  __int64 v30; // [rsp+E0h] [rbp+67h] BYREF
  char v31; // [rsp+E8h] [rbp+6Fh]

  v7 = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  *(_WORD *)&v29.OldIrql = 0;
  v29.Flags = 0;
  v11 = 0;
  v24 = 0;
  v12 = 0;
  v25 = 0;
  v30 = 0;
  *a6 = 0;
  *a5 = 0;
  v13 = *(_QWORD *)(a2 + 1240);
  v31 = *(_DWORD *)(a1 + 1872) == 2;
  v26 = &v30;
  if ( (VmsDiagnosticFlags & 1) != 0 )
  {
    if ( a3 )
    {
      v20 = *(_QWORD *)(a3 + 288);
      if ( v20 )
      {
        v21 = *(_QWORD *)(v20 + 16);
        if ( v21 )
        {
          *(_DWORD *)(v21 + 184) = 2651;
          *(_QWORD *)(v21 + 176) = "VmsRouterSourceProcessing";
          *(_QWORD *)(v21 + 168) = retaddr;
        }
      }
    }
  }
  if ( a4 )
  {
    if ( KeGetCurrentIrql() != 2 )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        v14,
        19,
        24,
        (__int64)WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids,
        (__int64)"KeGetCurrentIrql() == DISPATCH_LEVEL");
      if ( KeGetCurrentIrql() != 2 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    v7 = 1;
  }
  NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(v13 + 56), &LockState, v7);
  if ( KeGetCurrentIrql() != 2 )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      v15,
      19,
      24,
      (__int64)WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids,
      (__int64)"KeGetCurrentIrql() == DISPATCH_LEVEL");
    if ( KeGetCurrentIrql() != 2 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(a2 + 56), &v29, 1u);
  if ( *(_DWORD *)(v13 + 68) != 1 || *(_DWORD *)(a2 + 68) != 1 )
  {
    VmsPktReportDroppedNblChain(a1, (__int16 *)a3, 1, 4, 17, -536862693);
LABEL_28:
    v30 = a3;
    goto LABEL_20;
  }
  if ( *(_DWORD *)(a1 + 1880) != 1 || *(_QWORD *)(a2 + 1256) != a1 )
  {
    VmsPktReportDroppedNblChain(a1, (__int16 *)a3, 1, 5, 31, -536862692);
    goto LABEL_28;
  }
  if ( !a3 )
  {
    if ( v13 )
      v22 = *(_QWORD *)(v13 + 9096);
    else
      LODWORD(v22) = VmsIfrLog;
    WPP_RECORDER_SF_s(
      v22,
      (unsigned int)WPP_f18700f63de43472e386b6bf020f8882_Traceguids,
      19,
      44,
      (__int64)WPP_f18700f63de43472e386b6bf020f8882_Traceguids,
      (__int64)"nblsToProcess != NULL");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  if ( *(_DWORD *)(a1 + 1872) == 5 )
  {
    v11 = a3;
  }
  else
  {
    VmsPlcApplyPolicy(v13, a3, a1, 0, a2, 0, a4, 1, v31, (__int64)&v25, (__int64)&v26);
    v11 = v25;
  }
  if ( v11 && *(_BYTE *)(a2 + 1249) )
  {
    if ( (int)VmsNblGetBasicHeaderInfo(v11, 0, 0, (unsigned int)&v24, 0) >= 0 )
    {
      if ( (v24 & 1) != 0 )
      {
        if ( v13 )
          v23 = *(_QWORD *)(v13 + 9096);
        else
          LODWORD(v23) = VmsIfrLog;
        WPP_RECORDER_SF_s(
          v23,
          v16,
          19,
          45,
          (__int64)WPP_f18700f63de43472e386b6bf020f8882_Traceguids,
          (__int64)"!ETH_IS_MULTICAST(sourceRoutingKey.MacAddress8)");
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
      }
      NvspRoutingObjLearn(*(_QWORD *)(v13 + 1504), *(_QWORD *)(a2 + 1296), v24, 0);
    }
    v17 = *(_QWORD *)(v13 + 1504);
    if ( *(_BYTE *)(*(_QWORD *)(v17 + 56) + 24LL) )
      v12 = _InterlockedExchange((volatile __int32 *)(v17 + 48), 1) == 0;
  }
LABEL_20:
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a2 + 56), &v29);
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v13 + 56), &LockState);
  if ( v12 )
  {
    LOBYTE(v18) = a4;
    VmsOmObjectLockExclusive(v13, &LockState, v18);
    NvspRoutingObjPerformRehash(*(_QWORD *)(v13 + 1504));
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v13 + 56), &LockState);
  }
  *a6 = v30;
  result = a5;
  *a5 = v11;
  return result;
}

```

## disassembly

```asm
0x14001bae4  push    rbp
0x14001bae6  push    rbx
0x14001bae7  push    rsi
0x14001bae8  push    rdi
0x14001bae9  push    r12
0x14001baeb  push    r13
0x14001baed  push    r14
0x14001baef  push    r15
0x14001baf1  lea     rbp, [rsp-0Fh]
0x14001baf6  sub     rsp, 88h
0x14001bafd  xor     eax, eax
0x14001baff  mov     rdi, r8
0x14001bb02  xor     r8d, r8d
0x14001bb05  mov     word ptr [rbp+47h+LockState.OldIrql], ax
0x14001bb09  mov     [rbp+47h+LockState.Flags], al
0x14001bb0c  mov     r14, rcx
0x14001bb0f  mov     word ptr [rbp+47h+arg_8.OldIrql], ax
0x14001bb13  mov     r13b, r9b
0x14001bb16  mov     [rbp+47h+arg_8.Flags], al
0x14001bb19  mov     rsi, rdx
0x14001bb1c  mov     rax, [rbp+47h+arg_28]
0x14001bb20  mov     r12d, r8d
0x14001bb23  mov     [rbp+47h+var_60], r8
0x14001bb27  mov     r15b, r8b
0x14001bb2a  mov     [rbp+47h+var_58], r8
0x14001bb2e  mov     [rbp+47h+arg_10], r8
0x14001bb32  mov     [rax], r8
0x14001bb35  mov     rax, [rbp+47h+arg_20]
0x14001bb39  mov     [rax], r8
0x14001bb3c  lea     rax, [rbp+47h+arg_10]
0x14001bb40  cmp     dword ptr [rcx+750h], 2
0x14001bb47  mov     rbx, [rdx+4D8h]
0x14001bb4e  mov     rcx, [rbp+4Fh]
0x14001bb52  setz    [rbp+47h+arg_18]
0x14001bb56  mov     [rbp+47h+var_50], rax
0x14001bb5a  mov     eax, cs:VmsDiagnosticFlags
0x14001bb60  test    al, 1
0x14001bb62  jnz     loc_14001BD15
0x14001bb68  test    r13b, r13b
0x14001bb6b  jz      short loc_14001BB84
0x14001bb6d  call    cs:__imp_KeGetCurrentIrql
0x14001bb74  nop     dword ptr [rax+rax+00h]
0x14001bb79  cmp     al, 2
0x14001bb7b  jnz     loc_14001BDC0
0x14001bb81  mov     r8b, 1; Flags
0x14001bb84  mov     rcx, [rbx+38h]; Lock
0x14001bb88  lea     rdx, [rbp+47h+LockState]; LockState
0x14001bb8c  call    cs:__imp_NdisAcquireRWLockRead
0x14001bb93  nop     dword ptr [rax+rax+00h]
0x14001bb98  call    cs:__imp_KeGetCurrentIrql
0x14001bb9f  nop     dword ptr [rax+rax+00h]
0x14001bba4  cmp     al, 2
0x14001bba6  jnz     loc_14001BE0C
0x14001bbac  mov     rcx, [rsi+38h]; Lock
0x14001bbb0  lea     rdx, [rbp+47h+arg_8]; LockState
0x14001bbb4  mov     r8b, 1; Flags
0x14001bbb7  call    cs:__imp_NdisAcquireRWLockRead
0x14001bbbe  nop     dword ptr [rax+rax+00h]
0x14001bbc3  mov     ecx, 1
0x14001bbc8  cmp     [rbx+44h], ecx
0x14001bbcb  jnz     loc_14001BD5F
0x14001bbd1  cmp     [rsi+44h], ecx
0x14001bbd4  jnz     loc_14001BD5F
0x14001bbda  cmp     [r14+758h], ecx
0x14001bbe1  jnz     loc_14001BD94
0x14001bbe7  cmp     [rsi+4E8h], r14
0x14001bbee  jnz     loc_14001BD94
0x14001bbf4  lea     rdx, WPP_f18700f63de43472e386b6bf020f8882_Traceguids
0x14001bbfb  test    rdi, rdi
0x14001bbfe  jz      loc_14001BE58
0x14001bc04  cmp     dword ptr [r14+750h], 5
0x14001bc0c  jz      loc_14001BD8C
0x14001bc12  lea     rax, [rbp+47h+var_50]
0x14001bc16  xor     r9d, r9d
0x14001bc19  mov     [rsp+0C0h+var_70], rax
0x14001bc1e  mov     r8, r14
0x14001bc21  lea     rax, [rbp+47h+var_58]
0x14001bc25  mov     rdx, rdi
0x14001bc28  mov     [rsp+0C0h+var_78], rax
0x14001bc2d  mov     al, [rbp+47h+arg_18]
0x14001bc30  mov     [rsp+0C0h+var_80], al
0x14001bc34  mov     [rsp+0C0h+var_88], cl
0x14001bc38  mov     rcx, rbx
0x14001bc3b  mov     [rsp+0C0h+var_90], r13b
0x14001bc40  mov     [rsp+0C0h+var_98], r12
0x14001bc45  mov     [rsp+0C0h+var_A0], rsi
0x14001bc4a  call    VmsPlcApplyPolicy
0x14001bc4f  mov     r12, [rbp+47h+var_58]
0x14001bc53  test    r12, r12
0x14001bc56  jz      short loc_14001BCBD
0x14001bc58  cmp     [rsi+4E1h], r15b
0x14001bc5f  jz      short loc_14001BCBD
0x14001bc61  lea     r9, [rbp+47h+var_60]
0x14001bc65  mov     [rsp+0C0h+var_A0], 0
0x14001bc6e  xor     r8d, r8d
0x14001bc71  xor     edx, edx
0x14001bc73  mov     rcx, r12
0x14001bc76  call    VmsNblGetBasicHeaderInfo
0x14001bc7b  mov     edi, 1
0x14001bc80  test    eax, eax
0x14001bc82  js      short loc_14001BCA8
0x14001bc84  test    byte ptr [rbp+47h+var_60], dil
0x14001bc88  jnz     loc_14001BE9C
0x14001bc8e  mov     r8, [rbp+47h+var_60]
0x14001bc92  xor     r9d, r9d
0x14001bc95  mov     rdx, [rsi+510h]
0x14001bc9c  mov     rcx, [rbx+5E0h]
0x14001bca3  call    NvspRoutingObjLearn
0x14001bca8  mov     rcx, [rbx+5E0h]
0x14001bcaf  mov     rax, [rcx+38h]
0x14001bcb3  cmp     [rax+18h], r15b
0x14001bcb7  jnz     loc_14001BDAC
0x14001bcbd  mov     rcx, [rsi+38h]; Lock
0x14001bcc1  lea     rdx, [rbp+47h+arg_8]; LockState
0x14001bcc5  call    cs:__imp_NdisReleaseRWLock
0x14001bccc  nop     dword ptr [rax+rax+00h]
0x14001bcd1  mov     rcx, [rbx+38h]; Lock
0x14001bcd5  lea     rdx, [rbp+47h+LockState]; LockState
0x14001bcd9  call    cs:__imp_NdisReleaseRWLock
0x14001bce0  nop     dword ptr [rax+rax+00h]
0x14001bce5  test    r15b, r15b
0x14001bce8  jnz     loc_14001BEE2
0x14001bcee  mov     rax, [rbp+47h+arg_10]
0x14001bcf2  mov     rcx, [rbp+47h+arg_28]
0x14001bcf6  mov     [rcx], rax
0x14001bcf9  mov     rax, [rbp+47h+arg_20]
0x14001bcfd  mov     [rax], r12
0x14001bd00  add     rsp, 88h
0x14001bd07  pop     r15
0x14001bd09  pop     r14
0x14001bd0b  pop     r13
0x14001bd0d  pop     r12
0x14001bd0f  pop     rdi
0x14001bd10  pop     rsi
0x14001bd11  pop     rbx
0x14001bd12  pop     rbp
0x14001bd13  retn
0x14001bd15  test    rdi, rdi
0x14001bd18  jz      loc_14001BB68
0x14001bd1e  mov     rax, [rdi+120h]
0x14001bd25  test    rax, rax
0x14001bd28  jz      loc_14001BB68
0x14001bd2e  mov     rax, [rax+10h]
0x14001bd32  test    rax, rax
0x14001bd35  jz      loc_14001BB68
0x14001bd3b  lea     rdx, aVmsroutersourc; "VmsRouterSourceProcessing"
0x14001bd42  mov     dword ptr [rax+0B8h], 0A5Bh
0x14001bd4c  mov     [rax+0B0h], rdx
0x14001bd53  mov     [rax+0A8h], rcx
0x14001bd5a  jmp     loc_14001BB68
0x14001bd5f  mov     dword ptr [rsp+0C0h+var_98], 0E000201Bh
0x14001bd67  mov     r9d, 4
0x14001bd6d  mov     dword ptr [rsp+0C0h+var_A0], 0C0010011h
0x14001bd75  mov     r8b, cl
0x14001bd78  mov     rdx, rdi
0x14001bd7b  mov     rcx, r14
0x14001bd7e  call    VmsPktReportDroppedNblChain
0x14001bd83  mov     [rbp+47h+arg_10], rdi
0x14001bd87  jmp     loc_14001BCBD
0x14001bd8c  mov     r12, rdi
0x14001bd8f  jmp     loc_14001BC53
0x14001bd94  mov     dword ptr [rsp+0C0h+var_98], 0E000201Ch
0x14001bd9c  mov     r9d, 5
0x14001bda2  mov     dword ptr [rsp+0C0h+var_A0], 0C023001Fh
0x14001bdaa  jmp     short loc_14001BD75
0x14001bdac  mov     eax, edi
0x14001bdae  movzx   r15d, r15b
0x14001bdb2  xchg    eax, [rcx+30h]
0x14001bdb5  test    eax, eax
0x14001bdb7  cmovz   r15d, edi
0x14001bdbb  jmp     loc_14001BCBD
0x14001bdc0  mov     rcx, cs:VmsIfrLog
0x14001bdc7  lea     rax, aKegetcurrentir; "KeGetCurrentIrql() == DISPATCH_LEVEL"
0x14001bdce  mov     [rsp+0C0h+var_98], rax
0x14001bdd3  mov     r9d, 18h
0x14001bdd9  lea     rax, WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids
0x14001bde0  mov     [rsp+0C0h+var_A0], rax
0x14001bde5  lea     r8d, [r9-5]
0x14001bde9  call    WPP_RECORDER_SF_s
0x14001bdee  call    cs:__imp_KeGetCurrentIrql
0x14001bdf5  nop     dword ptr [rax+rax+00h]
0x14001bdfa  cmp     al, 2
0x14001bdfc  jz      loc_14001BB81
0x14001be02  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "KeGetCurrentIrql() == 2")
0x14001be07  jmp     loc_14001BB81
0x14001be0c  mov     rcx, cs:VmsIfrLog
0x14001be13  lea     rax, aKegetcurrentir; "KeGetCurrentIrql() == DISPATCH_LEVEL"
0x14001be1a  mov     [rsp+0C0h+var_98], rax
0x14001be1f  mov     r9d, 18h
0x14001be25  lea     rax, WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids
0x14001be2c  mov     [rsp+0C0h+var_A0], rax
0x14001be31  lea     r8d, [r9-5]
0x14001be35  call    WPP_RECORDER_SF_s
0x14001be3a  call    cs:__imp_KeGetCurrentIrql
0x14001be41  nop     dword ptr [rax+rax+00h]
0x14001be46  cmp     al, 2
0x14001be48  jz      loc_14001BBAC
0x14001be4e  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "KeGetCurrentIrql() == 2")
0x14001be53  jmp     loc_14001BBAC
0x14001be58  test    rbx, rbx
0x14001be5b  jz      short loc_14001BE66
0x14001be5d  mov     rcx, [rbx+2388h]
0x14001be64  jmp     short loc_14001BE6D
0x14001be66  mov     rcx, cs:VmsIfrLog
0x14001be6d  mov     r9d, 2Ch ; ','
0x14001be73  lea     rax, aNblstoprocessN; "nblsToProcess != NULL"
0x14001be7a  mov     [rsp+0C0h+var_98], rax
0x14001be7f  mov     [rsp+0C0h+var_A0], rdx
0x14001be84  lea     r8d, [r9-19h]
0x14001be88  call    WPP_RECORDER_SF_s
0x14001be8d  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "nblsToProcess != ((void *)0)")
0x14001be92  mov     ecx, 1
0x14001be97  jmp     loc_14001BC04
0x14001be9c  test    rbx, rbx
0x14001be9f  jz      short loc_14001BEAA
0x14001bea1  mov     rcx, [rbx+2388h]
0x14001bea8  jmp     short loc_14001BEB1
0x14001beaa  mov     rcx, cs:VmsIfrLog
0x14001beb1  mov     r9d, 2Dh ; '-'
0x14001beb7  lea     rax, aEthIsMulticast; "!ETH_IS_MULTICAST(sourceRoutingKey.MacA"...
0x14001bebe  mov     [rsp+0C0h+var_98], rax
0x14001bec3  lea     rax, WPP_f18700f63de43472e386b6bf020f8882_Traceguids
0x14001beca  mov     [rsp+0C0h+var_A0], rax
0x14001becf  lea     r8d, [r9-1Ah]
0x14001bed3  call    WPP_RECORDER_SF_s
0x14001bed8  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "!(BOOLEAN)(((PUCHAR)(sourceRoutingKey.MacAddress8))[0] & ((UCHAR)0x01))")
0x14001bedd  jmp     loc_14001BC8E
0x14001bee2  mov     r8b, r13b
0x14001bee5  lea     rdx, [rbp+47h+LockState]
0x14001bee9  mov     rcx, rbx
0x14001beec  call    VmsOmObjectLockExclusive
0x14001bef1  mov     rcx, [rbx+5E0h]
0x14001bef8  call    NvspRoutingObjPerformRehash
0x14001befd  mov     rcx, [rbx+38h]; Lock
0x14001bf01  lea     rdx, [rbp+47h+LockState]; LockState
0x14001bf05  call    cs:__imp_NdisReleaseRWLock
0x14001bf0c  nop     dword ptr [rax+rax+00h]
0x14001bf11  jmp     loc_14001BCEE
```
