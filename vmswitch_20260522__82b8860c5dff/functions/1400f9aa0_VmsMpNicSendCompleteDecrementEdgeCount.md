# VmsMpNicSendCompleteDecrementEdgeCount

- ea: `0x1400f9aa0`
- end: `0x1400f9ce6`
- name: `VmsMpNicSendCompleteDecrementEdgeCount`
- size: `582`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140010940`
- `0x140012a90`
- `0x140014330`
- `0x140017a7c`
- `0x1400f9aa0`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x1400f9ca7`
- `ntoskrnl!KeBugCheckEx` at `0x1400f9cd9`
- `ntoskrnl!KeBugCheckEx` at `0x1400f9ca7`
- `ntoskrnl!KeBugCheckEx` at `0x1400f9cd9`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400f9b61`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400f9b8b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400f9c2c`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400f9c84`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400f9cb6`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400f9b61`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400f9b8b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400f9c2c`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400f9c84`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400f9cb6`
- `ntoskrnl!KeLowerIrql` at `0x1400f9c0e`
- `ntoskrnl!KeLowerIrql` at `0x1400f9c0e`
- `ntoskrnl!KfRaiseIrql` at `0x1400f9b3e`
- `ntoskrnl!KfRaiseIrql` at `0x1400f9b3e`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400f9b0e`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400f9c1a`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400f9b0e`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400f9c1a`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x1400f9bf1`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x1400f9bf1`

## string_xrefs

- `0x1400f9aed`: `VmsMpNicSendNetBufferListsCompleteInternal`

## pseudocode

```c
KIRQL __fastcall VmsMpNicSendCompleteDecrementEdgeCount(__int64 a1, char a2)
{
  int v3; // r13d
  int v4; // r14d
  struct _NET_BUFFER_LIST *v5; // rbp
  __int64 v6; // rbx
  _QWORD *v7; // rax
  __int64 v8; // rax
  int v9; // edi
  KIRQL CurrentIrql; // si
  void *v11; // r15
  __int64 NicHeaderAtIndex; // rbx
  ULONG CurrentProcessorNumber; // eax
  ULONG_PTR v14; // rbx
  char *v15; // rcx
  KIRQL result; // al
  ULONG v17; // eax
  ULONG_PTR v18; // rbx
  char *v19; // rcx
  ULONG v20; // eax
  ULONG v21; // eax
  _UNKNOWN *retaddr; // [rsp+78h] [rbp+0h]

  v3 = *(_DWORD *)(a1 + 52);
  v4 = *(_DWORD *)(a1 + 48);
  v5 = *(struct _NET_BUFFER_LIST **)(a1 + 24);
  v6 = *(_QWORD *)(a1 + 40);
  if ( (VmsDiagnosticFlags & 1) != 0 )
  {
    if ( v5 )
    {
      v7 = v5->NetBufferListInfo[18];
      if ( v7 )
      {
        v8 = v7[2];
        if ( v8 )
        {
          *(_DWORD *)(v8 + 184) = 588;
          *(_QWORD *)(v8 + 176) = "VmsMpNicSendNetBufferListsCompleteInternal";
          *(_QWORD *)(v8 + 168) = retaddr;
        }
      }
    }
  }
  v9 = 0;
  CurrentIrql = KeGetCurrentIrql();
  v11 = *(void **)(*(_QWORD *)(v6 + 3312) + 24LL);
  if ( !CurrentIrql && (VmsExecutionMode & 8) == 0 )
  {
    v9 = 1;
    CurrentIrql = KfRaiseIrql(2u);
  }
  NicHeaderAtIndex = VmsPtGetNicHeaderAtIndex(v6, 0);
  if ( NicHeaderAtIndex )
    _InterlockedAdd64(
      (volatile signed __int64 *)(((unsigned __int64)KeGetCurrentProcessorNumberEx(0) << 6)
                                + *(_QWORD *)(NicHeaderAtIndex + 24)
                                + 16),
      -v4);
  if ( CurrentIrql == 2 )
  {
    CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
    v14 = CurrentProcessorNumber;
    if ( CurrentProcessorNumber == -1
      || !(unsigned __int8)VmsCpuSetContainsProcessor(VmsKnownProcessors, CurrentProcessorNumber)
      || (v15 = (char *)VmsPlanCpuTable + 5440 * v14) == 0 )
    {
      v20 = KeGetCurrentProcessorNumberEx(0);
      KeBugCheckEx(0x121u, v14, v20, 0, 0);
    }
    NetDispatchProfilerLeave(v15 + 1152);
  }
  if ( a2 )
    v9 = 1;
  NdisMSendNetBufferListsComplete(v11, v5, v3 | v9);
  if ( !CurrentIrql && (VmsExecutionMode & 8) == 0 )
    KeLowerIrql(0);
  result = KeGetCurrentIrql();
  if ( result == 2 )
  {
    v17 = KeGetCurrentProcessorNumberEx(0);
    v18 = v17;
    if ( v17 == -1
      || !(unsigned __int8)VmsCpuSetContainsProcessor(VmsKnownProcessors, v17)
      || (v19 = (char *)VmsPlanCpuTable + 5440 * v18) == 0 )
    {
      v21 = KeGetCurrentProcessorNumberEx(0);
      KeBugCheckEx(0x121u, v18, v21, 0, 0);
    }
    return NetDispatchProfilerEnter(v19 + 1152, 1);
  }
  return result;
}

```

## disassembly

```asm
0x1400f9aa0  push    rbx
0x1400f9aa2  push    rbp
0x1400f9aa3  push    rsi
0x1400f9aa4  push    rdi
0x1400f9aa5  push    r12
0x1400f9aa7  push    r13
0x1400f9aa9  push    r14
0x1400f9aab  push    r15
0x1400f9aad  sub     rsp, 38h
0x1400f9ab1  mov     eax, cs:VmsDiagnosticFlags
0x1400f9ab7  mov     r12b, dl
0x1400f9aba  mov     r13d, [rcx+34h]
0x1400f9abe  mov     r14d, [rcx+30h]
0x1400f9ac2  mov     rbp, [rcx+18h]
0x1400f9ac6  mov     rbx, [rcx+28h]
0x1400f9aca  mov     rcx, [rsp+78h]
0x1400f9acf  test    al, 1
0x1400f9ad1  jz      short loc_1400F9B0C
0x1400f9ad3  test    rbp, rbp
0x1400f9ad6  jz      short loc_1400F9B0C
0x1400f9ad8  mov     rax, [rbp+120h]
0x1400f9adf  test    rax, rax
0x1400f9ae2  jz      short loc_1400F9B0C
0x1400f9ae4  mov     rax, [rax+10h]
0x1400f9ae8  test    rax, rax
0x1400f9aeb  jz      short loc_1400F9B0C
0x1400f9aed  lea     rdx, aVmsmpnicsendne_0; "VmsMpNicSendNetBufferListsCompleteInter"...
0x1400f9af4  mov     dword ptr [rax+0B8h], 24Ch
0x1400f9afe  mov     [rax+0B0h], rdx
0x1400f9b05  mov     [rax+0A8h], rcx
0x1400f9b0c  xor     edi, edi
0x1400f9b0e  call    cs:__imp_KeGetCurrentIrql
0x1400f9b15  nop     dword ptr [rax+rax+00h]
0x1400f9b1a  mov     rcx, [rbx+0CF0h]
0x1400f9b21  mov     sil, al
0x1400f9b24  mov     r15, [rcx+18h]
0x1400f9b28  test    al, al
0x1400f9b2a  jnz     short loc_1400F9B4D
0x1400f9b2c  mov     edx, cs:VmsExecutionMode
0x1400f9b32  test    dl, 8
0x1400f9b35  jnz     short loc_1400F9B4D
0x1400f9b37  mov     cl, 2; NewIrql
0x1400f9b39  mov     edi, 1
0x1400f9b3e  call    cs:__imp_KfRaiseIrql
0x1400f9b45  nop     dword ptr [rax+rax+00h]
0x1400f9b4a  mov     sil, al
0x1400f9b4d  xor     edx, edx
0x1400f9b4f  mov     rcx, rbx
0x1400f9b52  call    VmsPtGetNicHeaderAtIndex
0x1400f9b57  mov     rbx, rax
0x1400f9b5a  test    rax, rax
0x1400f9b5d  jz      short loc_1400F9B83
0x1400f9b5f  xor     ecx, ecx; ProcNumber
0x1400f9b61  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400f9b68  nop     dword ptr [rax+rax+00h]
0x1400f9b6d  mov     ecx, eax
0x1400f9b6f  neg     r14d
0x1400f9b72  mov     rax, [rbx+18h]
0x1400f9b76  shl     rcx, 6
0x1400f9b7a  movsxd  rdx, r14d
0x1400f9b7d  lock add [rcx+rax+10h], rdx
0x1400f9b83  cmp     sil, 2
0x1400f9b87  jnz     short loc_1400F9BD8
0x1400f9b89  xor     ecx, ecx; ProcNumber
0x1400f9b8b  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400f9b92  nop     dword ptr [rax+rax+00h]
0x1400f9b97  mov     ebx, eax
0x1400f9b99  cmp     eax, 0FFFFFFFFh
0x1400f9b9c  jz      loc_1400F9C82
0x1400f9ba2  mov     edx, ebx
0x1400f9ba4  lea     rcx, VmsKnownProcessors
0x1400f9bab  call    VmsCpuSetContainsProcessor
0x1400f9bb0  test    al, al
0x1400f9bb2  jz      loc_1400F9C82
0x1400f9bb8  imul    rcx, rbx, 1540h
0x1400f9bbf  add     rcx, cs:VmsPlanCpuTable
0x1400f9bc6  jz      loc_1400F9C82
0x1400f9bcc  add     rcx, 480h
0x1400f9bd3  call    NetDispatchProfilerLeave
0x1400f9bd8  test    r12b, r12b
0x1400f9bdb  mov     r14d, 1
0x1400f9be1  mov     rdx, rbp; NetBufferList
0x1400f9be4  mov     rcx, r15; MiniportAdapterHandle
0x1400f9be7  cmovnz  edi, r14d
0x1400f9beb  or      edi, r13d
0x1400f9bee  mov     r8d, edi; SendCompleteFlags
0x1400f9bf1  call    cs:__imp_NdisMSendNetBufferListsComplete
0x1400f9bf8  nop     dword ptr [rax+rax+00h]
0x1400f9bfd  test    sil, sil
0x1400f9c00  jnz     short loc_1400F9C1A
0x1400f9c02  mov     eax, cs:VmsExecutionMode
0x1400f9c08  test    al, 8
0x1400f9c0a  jnz     short loc_1400F9C1A
0x1400f9c0c  xor     ecx, ecx; NewIrql
0x1400f9c0e  call    cs:__imp_KeLowerIrql
0x1400f9c15  nop     dword ptr [rax+rax+00h]
0x1400f9c1a  call    cs:__imp_KeGetCurrentIrql
0x1400f9c21  nop     dword ptr [rax+rax+00h]
0x1400f9c26  cmp     al, 2
0x1400f9c28  jnz     short loc_1400F9C70
0x1400f9c2a  xor     ecx, ecx; ProcNumber
0x1400f9c2c  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400f9c33  nop     dword ptr [rax+rax+00h]
0x1400f9c38  mov     ebx, eax
0x1400f9c3a  cmp     eax, 0FFFFFFFFh
0x1400f9c3d  jz      short loc_1400F9CB4
0x1400f9c3f  mov     edx, ebx
0x1400f9c41  lea     rcx, VmsKnownProcessors
0x1400f9c48  call    VmsCpuSetContainsProcessor
0x1400f9c4d  test    al, al
0x1400f9c4f  jz      short loc_1400F9CB4
0x1400f9c51  imul    rcx, rbx, 1540h
0x1400f9c58  add     rcx, cs:VmsPlanCpuTable
0x1400f9c5f  jz      short loc_1400F9CB4
0x1400f9c61  add     rcx, 480h
0x1400f9c68  mov     edx, r14d
0x1400f9c6b  call    NetDispatchProfilerEnter
0x1400f9c70  add     rsp, 38h
0x1400f9c74  pop     r15
0x1400f9c76  pop     r14
0x1400f9c78  pop     r13
0x1400f9c7a  pop     r12
0x1400f9c7c  pop     rdi
0x1400f9c7d  pop     rsi
0x1400f9c7e  pop     rbp
0x1400f9c7f  pop     rbx
0x1400f9c80  retn
0x1400f9c82  xor     ecx, ecx; ProcNumber
0x1400f9c84  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400f9c8b  nop     dword ptr [rax+rax+00h]
0x1400f9c90  xor     r9d, r9d; BugCheckParameter3
0x1400f9c93  mov     [rsp+78h+BugCheckParameter4], 0; BugCheckParameter4
0x1400f9c9c  mov     r8d, eax; BugCheckParameter2
0x1400f9c9f  mov     rdx, rbx; BugCheckParameter1
0x1400f9ca2  mov     ecx, 121h; BugCheckCode
0x1400f9ca7  call    cs:__imp_KeBugCheckEx
0x1400f9cb4  xor     ecx, ecx; ProcNumber
0x1400f9cb6  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400f9cbd  nop     dword ptr [rax+rax+00h]
0x1400f9cc2  xor     r9d, r9d; BugCheckParameter3
0x1400f9cc5  mov     [rsp+78h+BugCheckParameter4], 0; BugCheckParameter4
0x1400f9cce  mov     r8d, eax; BugCheckParameter2
0x1400f9cd1  mov     rdx, rbx; BugCheckParameter1
0x1400f9cd4  mov     ecx, 121h; BugCheckCode
0x1400f9cd9  call    cs:__imp_KeBugCheckEx
```
