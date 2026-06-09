# VmsTmTeamDetach

- ea: `0x14015cc28`
- end: `0x14015cf27`
- name: `VmsTmTeamDetach`
- size: `767`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14008f2d0`
- `0x14015cf30`
- `0x14015da40`

## callees

- `0x140027a64`
- `0x14008497c`
- `0x14015b084`
- `0x14015ba7c`
- `0x14015cc28`
- `0x14015d7a4`
- `0x1401887f0`
- `0x14018ad8c`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14015cda6`
- `ntoskrnl!KeWaitForSingleObject` at `0x14015cda6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015cea2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015ceba`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015cea2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015ceba`
- `NDIS!NdisFreeNetBufferListPool` at `0x14015ce81`
- `NDIS!NdisFreeNetBufferListPool` at `0x14015ce81`
- `NDIS!NdisReleaseRWLock` at `0x14015cd3b`
- `NDIS!NdisReleaseRWLock` at `0x14015cd86`
- `NDIS!NdisReleaseRWLock` at `0x14015ce17`
- `NDIS!NdisReleaseRWLock` at `0x14015cd3b`
- `NDIS!NdisReleaseRWLock` at `0x14015cd86`
- `NDIS!NdisReleaseRWLock` at `0x14015ce17`
- `NDIS!NdisAcquireRWLockWrite` at `0x14015cc86`
- `NDIS!NdisAcquireRWLockWrite` at `0x14015cd5d`
- `NDIS!NdisAcquireRWLockWrite` at `0x14015cdc0`
- `NDIS!NdisAcquireRWLockWrite` at `0x14015cc86`
- `NDIS!NdisAcquireRWLockWrite` at `0x14015cd5d`
- `NDIS!NdisAcquireRWLockWrite` at `0x14015cdc0`

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
0x14015cc28  push    rbp
0x14015cc2a  push    rbx
0x14015cc2b  push    rsi
0x14015cc2c  push    rdi
0x14015cc2d  push    r13
0x14015cc2f  push    r14
0x14015cc31  push    r15
0x14015cc33  mov     rbp, rsp
0x14015cc36  sub     rsp, 50h
0x14015cc3a  mov     rbx, [rcx+2328h]
0x14015cc41  xor     eax, eax
0x14015cc43  xor     r15d, r15d
0x14015cc46  mov     word ptr [rbp+LockState.OldIrql], ax
0x14015cc4a  mov     [rbp+LockState.Flags], al
0x14015cc4d  mov     rsi, rcx
0x14015cc50  mov     dword ptr [rbp+arg_18], r15d
0x14015cc54  mov     dword ptr [rbp+arg_10], r15d
0x14015cc58  test    rbx, rbx
0x14015cc5b  jz      loc_14015CF17
0x14015cc61  mov     r14b, [rbx+0CCh]
0x14015cc68  mov     rdi, [rbx+10h]
0x14015cc6c  shr     r14b, 1
0x14015cc6f  and     r14b, 1
0x14015cc73  test    rdi, rdi
0x14015cc76  jz      short loc_14015CC92
0x14015cc78  mov     rcx, [rdi+630h]; Lock
0x14015cc7f  lea     rdx, [rbp+LockState]; LockState
0x14015cc83  xor     r8d, r8d; Flags
0x14015cc86  call    cs:__imp_NdisAcquireRWLockWrite
0x14015cc8d  nop     dword ptr [rax+rax+00h]
0x14015cc92  cmp     dword ptr [rbx+100h], 2
0x14015cc99  lea     r13, WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids
0x14015cca0  jbe     short loc_14015CCD7
0x14015cca2  mov     rcx, cs:VmsIfrLog
0x14015cca9  lea     rax, aFiltercontextF_0; "(FilterContext->FilterState == FilterPa"...
0x14015ccb0  mov     r9d, 14h
0x14015ccb6  mov     [rsp+50h+var_28], rax
0x14015ccbb  mov     [rsp+50h+Timeout], r13
0x14015ccc0  lea     r8d, [r9-1]
0x14015ccc4  call    WPP_RECORDER_SF_s
0x14015ccc9  cmp     dword ptr [rbx+100h], 2
0x14015ccd0  jbe     short loc_14015CCD7
0x14015ccd2  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "(FilterContext->FilterState == FilterPaused) || (FilterContext->FilterState == FilterAttaching) || (FilterContext->FilterState == FilterAttached)")
0x14015ccd7  test    byte ptr cs:Microsoft_Windows_Hyper_V_VmSwitchEnableBits+2, 20h
0x14015ccde  jz      short loc_14015CCF4
0x14015cce0  mov     r9, rbx
0x14015cce3  mov     dword ptr [rsp+50h+Timeout], r15d
0x14015cce8  lea     rdx, RemovingTeamNicInfo
0x14015ccef  call    McTemplateK0pd_EtwWriteTransfer
0x14015ccf4  mov     ecx, [rbx+100h]
0x14015ccfa  mov     dword ptr [rbx+100h], 5
0x14015cd04  test    rdi, rdi
0x14015cd07  jz      loc_14015CE31
0x14015cd0d  mov     eax, [rdi+5F0h]
0x14015cd13  mov     dword ptr [rbp+arg_18], eax
0x14015cd16  mov     eax, [rdi+5ECh]
0x14015cd1c  mov     dword ptr [rbp+arg_10], eax
0x14015cd1f  lea     eax, [rcx-1]
0x14015cd22  cmp     eax, 1
0x14015cd25  ja      short loc_14015CD69
0x14015cd27  test    byte ptr [rbx+0CCh], 4
0x14015cd2e  jnz     short loc_14015CD69
0x14015cd30  mov     rcx, [rdi+630h]; Lock
0x14015cd37  lea     rdx, [rbp+LockState]; LockState
0x14015cd3b  call    cs:__imp_NdisReleaseRWLock
0x14015cd42  nop     dword ptr [rax+rax+00h]
0x14015cd47  mov     rcx, rsi
0x14015cd4a  call    VmsTmTeamPreDetach
0x14015cd4f  mov     rcx, [rdi+630h]; Lock
0x14015cd56  lea     rdx, [rbp+LockState]; LockState
0x14015cd5a  xor     r8d, r8d; Flags
0x14015cd5d  call    cs:__imp_NdisAcquireRWLockWrite
0x14015cd64  nop     dword ptr [rax+rax+00h]
0x14015cd69  mov     eax, 0FFFFh
0x14015cd6e  add     [rbx+0CEh], ax
0x14015cd75  jz      loc_14015CE0C
0x14015cd7b  mov     rcx, [rdi+630h]; Lock
0x14015cd82  lea     rdx, [rbp+LockState]; LockState
0x14015cd86  call    cs:__imp_NdisReleaseRWLock
0x14015cd8d  nop     dword ptr [rax+rax+00h]
0x14015cd92  lea     rcx, [rbx+0D0h]; Object
0x14015cd99  mov     [rsp+50h+Timeout], r15; Timeout
0x14015cd9e  xor     r9d, r9d; Alertable
0x14015cda1  xor     r8d, r8d; WaitMode
0x14015cda4  xor     edx, edx; WaitReason
0x14015cda6  call    cs:__imp_KeWaitForSingleObject
0x14015cdad  nop     dword ptr [rax+rax+00h]
0x14015cdb2  mov     rcx, [rdi+630h]; Lock
0x14015cdb9  lea     rdx, [rbp+LockState]; LockState
0x14015cdbd  xor     r8d, r8d; Flags
0x14015cdc0  call    cs:__imp_NdisAcquireRWLockWrite
0x14015cdc7  nop     dword ptr [rax+rax+00h]
0x14015cdcc  cmp     [rbx+0CEh], r15w
0x14015cdd4  jz      short loc_14015CE0C
0x14015cdd6  mov     rcx, cs:VmsIfrLog
0x14015cddd  lea     rax, aFiltercontextR; "FilterContext->RefCount == 0"
0x14015cde4  mov     r9d, 15h
0x14015cdea  mov     [rsp+50h+var_28], rax
0x14015cdef  mov     [rsp+50h+Timeout], r13
0x14015cdf4  lea     r8d, [r9-2]
0x14015cdf8  call    WPP_RECORDER_SF_s
0x14015cdfd  cmp     [rbx+0CEh], r15w
0x14015ce05  jz      short loc_14015CE0C
0x14015ce07  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "FilterContext->RefCount == 0")
0x14015ce0c  mov     rcx, [rdi+630h]; Lock
0x14015ce13  lea     rdx, [rbp+LockState]; LockState
0x14015ce17  call    cs:__imp_NdisReleaseRWLock
0x14015ce1e  nop     dword ptr [rax+rax+00h]
0x14015ce23  mov     rcx, rdi; P
0x14015ce26  call    VmsTmDestroyTeam
0x14015ce2b  mov     [rbx+10h], r15
0x14015ce2f  jmp     short loc_14015CE75
0x14015ce31  mov     eax, 0FFFFh
0x14015ce36  add     [rbx+0CEh], ax
0x14015ce3d  jz      short loc_14015CE75
0x14015ce3f  mov     rcx, cs:VmsIfrLog
0x14015ce46  lea     rax, aFiltercontextR; "FilterContext->RefCount == 0"
0x14015ce4d  mov     r9d, 16h
0x14015ce53  mov     [rsp+50h+var_28], rax
0x14015ce58  mov     [rsp+50h+Timeout], r13
0x14015ce5d  lea     r8d, [r9-3]
0x14015ce61  call    WPP_RECORDER_SF_s
0x14015ce66  cmp     [rbx+0CEh], r15w
0x14015ce6e  jz      short loc_14015CE75
0x14015ce70  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "FilterContext->RefCount == 0")
0x14015ce75  mov     rcx, [rbx+108h]; PoolHandle
0x14015ce7c  test    rcx, rcx
0x14015ce7f  jz      short loc_14015CE94
0x14015ce81  call    cs:__imp_NdisFreeNetBufferListPool
0x14015ce88  nop     dword ptr [rax+rax+00h]
0x14015ce8d  mov     [rbx+108h], r15
0x14015ce94  mov     rcx, [rbx+110h]; P
0x14015ce9b  test    rcx, rcx
0x14015ce9e  jz      short loc_14015CEB5
0x14015cea0  xor     edx, edx; Tag
0x14015cea2  call    cs:__imp_ExFreePoolWithTag
0x14015cea9  nop     dword ptr [rax+rax+00h]
0x14015ceae  mov     [rbx+110h], r15
0x14015ceb5  xor     edx, edx; Tag
0x14015ceb7  mov     rcx, rbx; P
0x14015ceba  call    cs:__imp_ExFreePoolWithTag
0x14015cec1  nop     dword ptr [rax+rax+00h]
0x14015cec6  mov     byte ptr [rsp+50h+var_8], r14b; int
0x14015cecb  lea     rdx, [rbp+arg_10]
0x14015cecf  mov     [rsp+50h+var_10], rdx; __int64
0x14015ced4  lea     rax, [rsi+268h]
0x14015cedb  lea     rdx, [rbp+arg_18]
0x14015cedf  mov     [rsi+2328h], r15
0x14015cee6  mov     [rsp+50h+var_18], rdx; __int64
0x14015ceeb  lea     rcx, [rsi+48h]
0x14015ceef  mov     [rsp+50h+var_20], rax; __int64
0x14015cef4  mov     [rsp+50h+var_28], rcx; __int64
0x14015cef9  lea     rcx, VM_EMBEDDED_TEAMING_TEAM_DETACHED; EventDescriptor
0x14015cf00  mov     [rsp+50h+Timeout], r15; __int64
0x14015cf05  call    VmsEtwTraceEmbeddedTeaming
0x14015cf0a  xor     r8d, r8d
0x14015cf0d  mov     rdx, rsi
0x14015cf10  xor     ecx, ecx
0x14015cf12  call    VmsTraceLoggingTraceEmbeddedTeamingTeamOperation
0x14015cf17  add     rsp, 50h
0x14015cf1b  pop     r15
0x14015cf1d  pop     r14
0x14015cf1f  pop     r13
0x14015cf21  pop     rdi
0x14015cf22  pop     rsi
0x14015cf23  pop     rbx
0x14015cf24  pop     rbp
0x14015cf25  retn
```
