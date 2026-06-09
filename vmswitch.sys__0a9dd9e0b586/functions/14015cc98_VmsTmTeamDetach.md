# VmsTmTeamDetach

- ea: `0x14015cc98`
- end: `0x14015cf97`
- name: `VmsTmTeamDetach`
- size: `767`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14008f2d0`
- `0x14015cfa0`
- `0x14015dab0`

## callees

- `0x140027a64`
- `0x14008497c`
- `0x14015b0f4`
- `0x14015baec`
- `0x14015cc98`
- `0x14015d814`
- `0x140188860`
- `0x14018adfc`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14015ce16`
- `ntoskrnl!KeWaitForSingleObject` at `0x14015ce16`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015cf12`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015cf2a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015cf12`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015cf2a`
- `NDIS!NdisFreeNetBufferListPool` at `0x14015cef1`
- `NDIS!NdisFreeNetBufferListPool` at `0x14015cef1`
- `NDIS!NdisReleaseRWLock` at `0x14015cdab`
- `NDIS!NdisReleaseRWLock` at `0x14015cdf6`
- `NDIS!NdisReleaseRWLock` at `0x14015ce87`
- `NDIS!NdisReleaseRWLock` at `0x14015cdab`
- `NDIS!NdisReleaseRWLock` at `0x14015cdf6`
- `NDIS!NdisReleaseRWLock` at `0x14015ce87`
- `NDIS!NdisAcquireRWLockWrite` at `0x14015ccf6`
- `NDIS!NdisAcquireRWLockWrite` at `0x14015cdcd`
- `NDIS!NdisAcquireRWLockWrite` at `0x14015ce30`
- `NDIS!NdisAcquireRWLockWrite` at `0x14015ccf6`
- `NDIS!NdisAcquireRWLockWrite` at `0x14015cdcd`
- `NDIS!NdisAcquireRWLockWrite` at `0x14015ce30`

## pseudocode

```c
__int64 __fastcall VmsTmTeamDetach(__int64 a1, int a2, __int64 a3)
{
  __int64 v3; // rbx
  __int64 result; // rax
  __int64 v6; // rdi
  bool v7; // r14
  int v8; // ecx
  bool v9; // zf
  int v10; // edx
  void *v11; // rcx
  void *v12; // rcx
  int v13; // [rsp+48h] [rbp-8h]
  struct _LOCK_STATE_EX LockState; // [rsp+98h] [rbp+48h] BYREF
  __int64 v15; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v16; // [rsp+A8h] [rbp+58h] BYREF

  v3 = *(_QWORD *)(a1 + 9000);
  result = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  LODWORD(v16) = 0;
  LODWORD(v15) = 0;
  if ( v3 )
  {
    v6 = *(_QWORD *)(v3 + 16);
    v7 = (*(_BYTE *)(v3 + 204) & 2) != 0;
    if ( v6 )
      NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(v6 + 1584), &LockState, 0);
    if ( *(_DWORD *)(v3 + 256) > 2u )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        a2,
        19,
        20,
        (__int64)WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids,
        (__int64)"(FilterContext->FilterState == FilterPaused) || (FilterContext->FilterState == FilterAttaching) || (Fil"
                 "terContext->FilterState == FilterAttached)");
      if ( *(_DWORD *)(v3 + 256) > 2u )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    if ( (Microsoft_Windows_Hyper_V_VmSwitchEnableBits & 0x200000) != 0 )
      McTemplateK0pd_EtwWriteTransfer(a1, RemovingTeamNicInfo, a3, v3, 0);
    v8 = *(_DWORD *)(v3 + 256);
    *(_DWORD *)(v3 + 256) = 5;
    if ( v6 )
    {
      LODWORD(v16) = *(_DWORD *)(v6 + 1520);
      LODWORD(v15) = *(_DWORD *)(v6 + 1516);
      if ( (unsigned int)(v8 - 1) <= 1 && (*(_BYTE *)(v3 + 204) & 4) == 0 )
      {
        NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v6 + 1584), &LockState);
        VmsTmTeamPreDetach(a1);
        NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(v6 + 1584), &LockState, 0);
      }
      v9 = (*(_WORD *)(v3 + 206))-- == 1;
      if ( !v9 )
      {
        NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v6 + 1584), &LockState);
        KeWaitForSingleObject((PVOID)(v3 + 208), Executive, 0, 0, 0);
        NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(v6 + 1584), &LockState, 0);
        if ( *(_WORD *)(v3 + 206) )
        {
          WPP_RECORDER_SF_s(
            VmsIfrLog,
            v10,
            19,
            21,
            (__int64)WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids,
            (__int64)"FilterContext->RefCount == 0");
          if ( *(_WORD *)(v3 + 206) )
            MicrosoftTelemetryAssertTriggeredNoArgsKM();
        }
      }
      NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v6 + 1584), &LockState);
      VmsTmDestroyTeam((int *)v6);
      *(_QWORD *)(v3 + 16) = 0;
    }
    else
    {
      v9 = (*(_WORD *)(v3 + 206))-- == 1;
      if ( !v9 )
      {
        WPP_RECORDER_SF_s(
          VmsIfrLog,
          a2,
          19,
          22,
          (__int64)WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids,
          (__int64)"FilterContext->RefCount == 0");
        if ( *(_WORD *)(v3 + 206) )
          MicrosoftTelemetryAssertTriggeredNoArgsKM();
      }
    }
    v11 = *(void **)(v3 + 264);
    if ( v11 )
    {
      NdisFreeNetBufferListPool(v11);
      *(_QWORD *)(v3 + 264) = 0;
    }
    v12 = *(void **)(v3 + 272);
    if ( v12 )
    {
      ExFreePoolWithTag(v12, 0);
      *(_QWORD *)(v3 + 272) = 0;
    }
    ExFreePoolWithTag((PVOID)v3, 0);
    LOBYTE(v13) = v7;
    *(_QWORD *)(a1 + 9000) = 0;
    VmsEtwTraceEmbeddedTeaming(
      &VM_EMBEDDED_TEAMING_TEAM_DETACHED,
      0,
      a1 + 72,
      a1 + 616,
      (__int64)&v16,
      (__int64)&v15,
      v13);
    return VmsTraceLoggingTraceEmbeddedTeamingTeamOperation(0, a1, 0);
  }
  return result;
}

```

## disassembly

```asm
0x14015cc98  push    rbp
0x14015cc9a  push    rbx
0x14015cc9b  push    rsi
0x14015cc9c  push    rdi
0x14015cc9d  push    r13
0x14015cc9f  push    r14
0x14015cca1  push    r15
0x14015cca3  mov     rbp, rsp
0x14015cca6  sub     rsp, 50h
0x14015ccaa  mov     rbx, [rcx+2328h]
0x14015ccb1  xor     eax, eax
0x14015ccb3  xor     r15d, r15d
0x14015ccb6  mov     word ptr [rbp+LockState.OldIrql], ax
0x14015ccba  mov     [rbp+LockState.Flags], al
0x14015ccbd  mov     rsi, rcx
0x14015ccc0  mov     dword ptr [rbp+arg_18], r15d
0x14015ccc4  mov     dword ptr [rbp+arg_10], r15d
0x14015ccc8  test    rbx, rbx
0x14015cccb  jz      loc_14015CF87
0x14015ccd1  mov     r14b, [rbx+0CCh]
0x14015ccd8  mov     rdi, [rbx+10h]
0x14015ccdc  shr     r14b, 1
0x14015ccdf  and     r14b, 1
0x14015cce3  test    rdi, rdi
0x14015cce6  jz      short loc_14015CD02
0x14015cce8  mov     rcx, [rdi+630h]; Lock
0x14015ccef  lea     rdx, [rbp+LockState]; LockState
0x14015ccf3  xor     r8d, r8d; Flags
0x14015ccf6  call    cs:__imp_NdisAcquireRWLockWrite
0x14015ccfd  nop     dword ptr [rax+rax+00h]
0x14015cd02  cmp     dword ptr [rbx+100h], 2
0x14015cd09  lea     r13, WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids
0x14015cd10  jbe     short loc_14015CD47
0x14015cd12  mov     rcx, cs:VmsIfrLog
0x14015cd19  lea     rax, aFiltercontextF_0; "(FilterContext->FilterState == FilterPa"...
0x14015cd20  mov     r9d, 14h
0x14015cd26  mov     [rsp+50h+var_28], rax
0x14015cd2b  mov     [rsp+50h+Timeout], r13
0x14015cd30  lea     r8d, [r9-1]
0x14015cd34  call    WPP_RECORDER_SF_s
0x14015cd39  cmp     dword ptr [rbx+100h], 2
0x14015cd40  jbe     short loc_14015CD47
0x14015cd42  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "(FilterContext->FilterState == FilterPaused) || (FilterContext->FilterState == FilterAttaching) || (FilterContext->FilterState == FilterAttached)")
0x14015cd47  test    byte ptr cs:Microsoft_Windows_Hyper_V_VmSwitchEnableBits+2, 20h
0x14015cd4e  jz      short loc_14015CD64
0x14015cd50  mov     r9, rbx
0x14015cd53  mov     dword ptr [rsp+50h+Timeout], r15d
0x14015cd58  lea     rdx, RemovingTeamNicInfo
0x14015cd5f  call    McTemplateK0pd_EtwWriteTransfer
0x14015cd64  mov     ecx, [rbx+100h]
0x14015cd6a  mov     dword ptr [rbx+100h], 5
0x14015cd74  test    rdi, rdi
0x14015cd77  jz      loc_14015CEA1
0x14015cd7d  mov     eax, [rdi+5F0h]
0x14015cd83  mov     dword ptr [rbp+arg_18], eax
0x14015cd86  mov     eax, [rdi+5ECh]
0x14015cd8c  mov     dword ptr [rbp+arg_10], eax
0x14015cd8f  lea     eax, [rcx-1]
0x14015cd92  cmp     eax, 1
0x14015cd95  ja      short loc_14015CDD9
0x14015cd97  test    byte ptr [rbx+0CCh], 4
0x14015cd9e  jnz     short loc_14015CDD9
0x14015cda0  mov     rcx, [rdi+630h]; Lock
0x14015cda7  lea     rdx, [rbp+LockState]; LockState
0x14015cdab  call    cs:__imp_NdisReleaseRWLock
0x14015cdb2  nop     dword ptr [rax+rax+00h]
0x14015cdb7  mov     rcx, rsi
0x14015cdba  call    VmsTmTeamPreDetach
0x14015cdbf  mov     rcx, [rdi+630h]; Lock
0x14015cdc6  lea     rdx, [rbp+LockState]; LockState
0x14015cdca  xor     r8d, r8d; Flags
0x14015cdcd  call    cs:__imp_NdisAcquireRWLockWrite
0x14015cdd4  nop     dword ptr [rax+rax+00h]
0x14015cdd9  mov     eax, 0FFFFh
0x14015cdde  add     [rbx+0CEh], ax
0x14015cde5  jz      loc_14015CE7C
0x14015cdeb  mov     rcx, [rdi+630h]; Lock
0x14015cdf2  lea     rdx, [rbp+LockState]; LockState
0x14015cdf6  call    cs:__imp_NdisReleaseRWLock
0x14015cdfd  nop     dword ptr [rax+rax+00h]
0x14015ce02  lea     rcx, [rbx+0D0h]; Object
0x14015ce09  mov     [rsp+50h+Timeout], r15; Timeout
0x14015ce0e  xor     r9d, r9d; Alertable
0x14015ce11  xor     r8d, r8d; WaitMode
0x14015ce14  xor     edx, edx; WaitReason
0x14015ce16  call    cs:__imp_KeWaitForSingleObject
0x14015ce1d  nop     dword ptr [rax+rax+00h]
0x14015ce22  mov     rcx, [rdi+630h]; Lock
0x14015ce29  lea     rdx, [rbp+LockState]; LockState
0x14015ce2d  xor     r8d, r8d; Flags
0x14015ce30  call    cs:__imp_NdisAcquireRWLockWrite
0x14015ce37  nop     dword ptr [rax+rax+00h]
0x14015ce3c  cmp     [rbx+0CEh], r15w
0x14015ce44  jz      short loc_14015CE7C
0x14015ce46  mov     rcx, cs:VmsIfrLog
0x14015ce4d  lea     rax, aFiltercontextR; "FilterContext->RefCount == 0"
0x14015ce54  mov     r9d, 15h
0x14015ce5a  mov     [rsp+50h+var_28], rax
0x14015ce5f  mov     [rsp+50h+Timeout], r13
0x14015ce64  lea     r8d, [r9-2]
0x14015ce68  call    WPP_RECORDER_SF_s
0x14015ce6d  cmp     [rbx+0CEh], r15w
0x14015ce75  jz      short loc_14015CE7C
0x14015ce77  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "FilterContext->RefCount == 0")
0x14015ce7c  mov     rcx, [rdi+630h]; Lock
0x14015ce83  lea     rdx, [rbp+LockState]; LockState
0x14015ce87  call    cs:__imp_NdisReleaseRWLock
0x14015ce8e  nop     dword ptr [rax+rax+00h]
0x14015ce93  mov     rcx, rdi; P
0x14015ce96  call    VmsTmDestroyTeam
0x14015ce9b  mov     [rbx+10h], r15
0x14015ce9f  jmp     short loc_14015CEE5
0x14015cea1  mov     eax, 0FFFFh
0x14015cea6  add     [rbx+0CEh], ax
0x14015cead  jz      short loc_14015CEE5
0x14015ceaf  mov     rcx, cs:VmsIfrLog
0x14015ceb6  lea     rax, aFiltercontextR; "FilterContext->RefCount == 0"
0x14015cebd  mov     r9d, 16h
0x14015cec3  mov     [rsp+50h+var_28], rax
0x14015cec8  mov     [rsp+50h+Timeout], r13
0x14015cecd  lea     r8d, [r9-3]
0x14015ced1  call    WPP_RECORDER_SF_s
0x14015ced6  cmp     [rbx+0CEh], r15w
0x14015cede  jz      short loc_14015CEE5
0x14015cee0  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "FilterContext->RefCount == 0")
0x14015cee5  mov     rcx, [rbx+108h]; PoolHandle
0x14015ceec  test    rcx, rcx
0x14015ceef  jz      short loc_14015CF04
0x14015cef1  call    cs:__imp_NdisFreeNetBufferListPool
0x14015cef8  nop     dword ptr [rax+rax+00h]
0x14015cefd  mov     [rbx+108h], r15
0x14015cf04  mov     rcx, [rbx+110h]; P
0x14015cf0b  test    rcx, rcx
0x14015cf0e  jz      short loc_14015CF25
0x14015cf10  xor     edx, edx; Tag
0x14015cf12  call    cs:__imp_ExFreePoolWithTag
0x14015cf19  nop     dword ptr [rax+rax+00h]
0x14015cf1e  mov     [rbx+110h], r15
0x14015cf25  xor     edx, edx; Tag
0x14015cf27  mov     rcx, rbx; P
0x14015cf2a  call    cs:__imp_ExFreePoolWithTag
0x14015cf31  nop     dword ptr [rax+rax+00h]
0x14015cf36  mov     byte ptr [rsp+50h+var_8], r14b; int
0x14015cf3b  lea     rdx, [rbp+arg_10]
0x14015cf3f  mov     [rsp+50h+var_10], rdx; __int64
0x14015cf44  lea     rax, [rsi+268h]
0x14015cf4b  lea     rdx, [rbp+arg_18]
0x14015cf4f  mov     [rsi+2328h], r15
0x14015cf56  mov     [rsp+50h+var_18], rdx; __int64
0x14015cf5b  lea     rcx, [rsi+48h]
0x14015cf5f  mov     [rsp+50h+var_20], rax; __int64
0x14015cf64  mov     [rsp+50h+var_28], rcx; __int64
0x14015cf69  lea     rcx, VM_EMBEDDED_TEAMING_TEAM_DETACHED; EventDescriptor
0x14015cf70  mov     [rsp+50h+Timeout], r15; __int64
0x14015cf75  call    VmsEtwTraceEmbeddedTeaming
0x14015cf7a  xor     r8d, r8d
0x14015cf7d  mov     rdx, rsi
0x14015cf80  xor     ecx, ecx
0x14015cf82  call    VmsTraceLoggingTraceEmbeddedTeamingTeamOperation
0x14015cf87  add     rsp, 50h
0x14015cf8b  pop     r15
0x14015cf8d  pop     r14
0x14015cf8f  pop     r13
0x14015cf91  pop     rdi
0x14015cf92  pop     rsi
0x14015cf93  pop     rbx
0x14015cf94  pop     rbp
0x14015cf95  retn
```
