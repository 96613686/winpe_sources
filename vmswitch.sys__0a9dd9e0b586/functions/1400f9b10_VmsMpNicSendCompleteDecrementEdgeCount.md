# VmsMpNicSendCompleteDecrementEdgeCount

- ea: `0x1400f9b10`
- end: `0x1400f9d56`
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
- `0x1400f9b10`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x1400f9d17`
- `ntoskrnl!KeBugCheckEx` at `0x1400f9d49`
- `ntoskrnl!KeBugCheckEx` at `0x1400f9d17`
- `ntoskrnl!KeBugCheckEx` at `0x1400f9d49`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400f9bd1`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400f9bfb`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400f9c9c`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400f9cf4`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400f9d26`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400f9bd1`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400f9bfb`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400f9c9c`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400f9cf4`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400f9d26`
- `ntoskrnl!KeLowerIrql` at `0x1400f9c7e`
- `ntoskrnl!KeLowerIrql` at `0x1400f9c7e`
- `ntoskrnl!KfRaiseIrql` at `0x1400f9bae`
- `ntoskrnl!KfRaiseIrql` at `0x1400f9bae`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400f9b7e`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400f9c8a`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400f9b7e`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400f9c8a`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x1400f9c61`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x1400f9c61`

## string_xrefs

- `0x1400f9b5d`: `VmsMpNicSendNetBufferListsCompleteInternal`

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
0x1400f9b10  push    rbx
0x1400f9b12  push    rbp
0x1400f9b13  push    rsi
0x1400f9b14  push    rdi
0x1400f9b15  push    r12
0x1400f9b17  push    r13
0x1400f9b19  push    r14
0x1400f9b1b  push    r15
0x1400f9b1d  sub     rsp, 38h
0x1400f9b21  mov     eax, cs:VmsDiagnosticFlags
0x1400f9b27  mov     r12b, dl
0x1400f9b2a  mov     r13d, [rcx+34h]
0x1400f9b2e  mov     r14d, [rcx+30h]
0x1400f9b32  mov     rbp, [rcx+18h]
0x1400f9b36  mov     rbx, [rcx+28h]
0x1400f9b3a  mov     rcx, [rsp+78h]
0x1400f9b3f  test    al, 1
0x1400f9b41  jz      short loc_1400F9B7C
0x1400f9b43  test    rbp, rbp
0x1400f9b46  jz      short loc_1400F9B7C
0x1400f9b48  mov     rax, [rbp+120h]
0x1400f9b4f  test    rax, rax
0x1400f9b52  jz      short loc_1400F9B7C
0x1400f9b54  mov     rax, [rax+10h]
0x1400f9b58  test    rax, rax
0x1400f9b5b  jz      short loc_1400F9B7C
0x1400f9b5d  lea     rdx, aVmsmpnicsendne_0; "VmsMpNicSendNetBufferListsCompleteInter"...
0x1400f9b64  mov     dword ptr [rax+0B8h], 24Ch
0x1400f9b6e  mov     [rax+0B0h], rdx
0x1400f9b75  mov     [rax+0A8h], rcx
0x1400f9b7c  xor     edi, edi
0x1400f9b7e  call    cs:__imp_KeGetCurrentIrql
0x1400f9b85  nop     dword ptr [rax+rax+00h]
0x1400f9b8a  mov     rcx, [rbx+0CF0h]
0x1400f9b91  mov     sil, al
0x1400f9b94  mov     r15, [rcx+18h]
0x1400f9b98  test    al, al
0x1400f9b9a  jnz     short loc_1400F9BBD
0x1400f9b9c  mov     edx, cs:VmsExecutionMode
0x1400f9ba2  test    dl, 8
0x1400f9ba5  jnz     short loc_1400F9BBD
0x1400f9ba7  mov     cl, 2; NewIrql
0x1400f9ba9  mov     edi, 1
0x1400f9bae  call    cs:__imp_KfRaiseIrql
0x1400f9bb5  nop     dword ptr [rax+rax+00h]
0x1400f9bba  mov     sil, al
0x1400f9bbd  xor     edx, edx
0x1400f9bbf  mov     rcx, rbx
0x1400f9bc2  call    VmsPtGetNicHeaderAtIndex
0x1400f9bc7  mov     rbx, rax
0x1400f9bca  test    rax, rax
0x1400f9bcd  jz      short loc_1400F9BF3
0x1400f9bcf  xor     ecx, ecx; ProcNumber
0x1400f9bd1  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400f9bd8  nop     dword ptr [rax+rax+00h]
0x1400f9bdd  mov     ecx, eax
0x1400f9bdf  neg     r14d
0x1400f9be2  mov     rax, [rbx+18h]
0x1400f9be6  shl     rcx, 6
0x1400f9bea  movsxd  rdx, r14d
0x1400f9bed  lock add [rcx+rax+10h], rdx
0x1400f9bf3  cmp     sil, 2
0x1400f9bf7  jnz     short loc_1400F9C48
0x1400f9bf9  xor     ecx, ecx; ProcNumber
0x1400f9bfb  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400f9c02  nop     dword ptr [rax+rax+00h]
0x1400f9c07  mov     ebx, eax
0x1400f9c09  cmp     eax, 0FFFFFFFFh
0x1400f9c0c  jz      loc_1400F9CF2
0x1400f9c12  mov     edx, ebx
0x1400f9c14  lea     rcx, VmsKnownProcessors
0x1400f9c1b  call    VmsCpuSetContainsProcessor
0x1400f9c20  test    al, al
0x1400f9c22  jz      loc_1400F9CF2
0x1400f9c28  imul    rcx, rbx, 1540h
0x1400f9c2f  add     rcx, cs:VmsPlanCpuTable
0x1400f9c36  jz      loc_1400F9CF2
0x1400f9c3c  add     rcx, 480h
0x1400f9c43  call    NetDispatchProfilerLeave
0x1400f9c48  test    r12b, r12b
0x1400f9c4b  mov     r14d, 1
0x1400f9c51  mov     rdx, rbp; NetBufferList
0x1400f9c54  mov     rcx, r15; MiniportAdapterHandle
0x1400f9c57  cmovnz  edi, r14d
0x1400f9c5b  or      edi, r13d
0x1400f9c5e  mov     r8d, edi; SendCompleteFlags
0x1400f9c61  call    cs:__imp_NdisMSendNetBufferListsComplete
0x1400f9c68  nop     dword ptr [rax+rax+00h]
0x1400f9c6d  test    sil, sil
0x1400f9c70  jnz     short loc_1400F9C8A
0x1400f9c72  mov     eax, cs:VmsExecutionMode
0x1400f9c78  test    al, 8
0x1400f9c7a  jnz     short loc_1400F9C8A
0x1400f9c7c  xor     ecx, ecx; NewIrql
0x1400f9c7e  call    cs:__imp_KeLowerIrql
0x1400f9c85  nop     dword ptr [rax+rax+00h]
0x1400f9c8a  call    cs:__imp_KeGetCurrentIrql
0x1400f9c91  nop     dword ptr [rax+rax+00h]
0x1400f9c96  cmp     al, 2
0x1400f9c98  jnz     short loc_1400F9CE0
0x1400f9c9a  xor     ecx, ecx; ProcNumber
0x1400f9c9c  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400f9ca3  nop     dword ptr [rax+rax+00h]
0x1400f9ca8  mov     ebx, eax
0x1400f9caa  cmp     eax, 0FFFFFFFFh
0x1400f9cad  jz      short loc_1400F9D24
0x1400f9caf  mov     edx, ebx
0x1400f9cb1  lea     rcx, VmsKnownProcessors
0x1400f9cb8  call    VmsCpuSetContainsProcessor
0x1400f9cbd  test    al, al
0x1400f9cbf  jz      short loc_1400F9D24
0x1400f9cc1  imul    rcx, rbx, 1540h
0x1400f9cc8  add     rcx, cs:VmsPlanCpuTable
0x1400f9ccf  jz      short loc_1400F9D24
0x1400f9cd1  add     rcx, 480h
0x1400f9cd8  mov     edx, r14d
0x1400f9cdb  call    NetDispatchProfilerEnter
0x1400f9ce0  add     rsp, 38h
0x1400f9ce4  pop     r15
0x1400f9ce6  pop     r14
0x1400f9ce8  pop     r13
0x1400f9cea  pop     r12
0x1400f9cec  pop     rdi
0x1400f9ced  pop     rsi
0x1400f9cee  pop     rbp
0x1400f9cef  pop     rbx
0x1400f9cf0  retn
0x1400f9cf2  xor     ecx, ecx; ProcNumber
0x1400f9cf4  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400f9cfb  nop     dword ptr [rax+rax+00h]
0x1400f9d00  xor     r9d, r9d; BugCheckParameter3
0x1400f9d03  mov     [rsp+78h+BugCheckParameter4], 0; BugCheckParameter4
0x1400f9d0c  mov     r8d, eax; BugCheckParameter2
0x1400f9d0f  mov     rdx, rbx; BugCheckParameter1
0x1400f9d12  mov     ecx, 121h; BugCheckCode
0x1400f9d17  call    cs:__imp_KeBugCheckEx
0x1400f9d24  xor     ecx, ecx; ProcNumber
0x1400f9d26  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400f9d2d  nop     dword ptr [rax+rax+00h]
0x1400f9d32  xor     r9d, r9d; BugCheckParameter3
0x1400f9d35  mov     [rsp+78h+BugCheckParameter4], 0; BugCheckParameter4
0x1400f9d3e  mov     r8d, eax; BugCheckParameter2
0x1400f9d41  mov     rdx, rbx; BugCheckParameter1
0x1400f9d44  mov     ecx, 121h; BugCheckCode
0x1400f9d49  call    cs:__imp_KeBugCheckEx
```
