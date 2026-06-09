# VmsMpNicSendCompleteDecrementRoutedCount

- ea: `0x1400f9cf0`
- end: `0x1400f9f78`
- name: `VmsMpNicSendCompleteDecrementRoutedCount`
- size: `648`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140010940`
- `0x140012a90`
- `0x140014330`
- `0x140017a7c`
- `0x140046f1c`
- `0x1400f9cf0`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x1400f9f3b`
- `ntoskrnl!KeBugCheckEx` at `0x1400f9f6b`
- `ntoskrnl!KeBugCheckEx` at `0x1400f9f3b`
- `ntoskrnl!KeBugCheckEx` at `0x1400f9f6b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400f9da8`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400f9e3e`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400f9ee3`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400f9f18`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400f9f4c`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400f9da8`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400f9e3e`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400f9ee3`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400f9f18`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400f9f4c`
- `ntoskrnl!KeLowerIrql` at `0x1400f9e20`
- `ntoskrnl!KeLowerIrql` at `0x1400f9e20`
- `ntoskrnl!KfRaiseIrql` at `0x1400f9d91`
- `ntoskrnl!KfRaiseIrql` at `0x1400f9d91`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400f9d60`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400f9e2c`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400f9d60`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400f9e2c`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x1400f9e03`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x1400f9e03`

## string_xrefs

- `0x1400f9d3e`: `VmsMpNicSendNetBufferListsCompleteInternal`

## pseudocode

```c
__int64 __fastcall VmsMpNicSendCompleteDecrementRoutedCount(__int64 a1)
{
  int v1; // r12d
  int v2; // edi
  struct _NET_BUFFER_LIST *v3; // rsi
  __int64 v4; // r14
  _QWORD *v5; // rax
  __int64 v6; // rax
  int v7; // r15d
  KIRQL CurrentIrql; // bp
  void *v9; // r13
  ULONG CurrentProcessorNumber; // eax
  ULONG_PTR v11; // rbx
  char *v12; // rcx
  ULONG v13; // eax
  ULONG_PTR v14; // rbx
  char *v15; // rcx
  __int64 result; // rax
  __int64 v17; // rbx
  __int64 v18; // rcx
  ULONG v19; // eax
  ULONG v20; // eax
  _UNKNOWN *retaddr; // [rsp+88h] [rbp+0h]

  v1 = *(_DWORD *)(a1 + 52);
  v2 = *(_DWORD *)(a1 + 48);
  v3 = *(struct _NET_BUFFER_LIST **)(a1 + 24);
  v4 = *(_QWORD *)(a1 + 40);
  if ( (VmsDiagnosticFlags & 1) != 0 )
  {
    if ( v3 )
    {
      v5 = v3->NetBufferListInfo[18];
      if ( v5 )
      {
        v6 = v5[2];
        if ( v6 )
        {
          *(_DWORD *)(v6 + 184) = 588;
          *(_QWORD *)(v6 + 176) = "VmsMpNicSendNetBufferListsCompleteInternal";
          *(_QWORD *)(v6 + 168) = retaddr;
        }
      }
    }
  }
  v7 = 0;
  CurrentIrql = KeGetCurrentIrql();
  v9 = *(void **)(*(_QWORD *)(v4 + 3312) + 24LL);
  if ( !CurrentIrql )
  {
    if ( (VmsExecutionMode & 8) != 0 )
      goto LABEL_14;
    v7 = 1;
    CurrentIrql = KfRaiseIrql(2u);
  }
  if ( CurrentIrql == 2 )
  {
    CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
    v11 = CurrentProcessorNumber;
    if ( CurrentProcessorNumber == -1
      || !(unsigned __int8)VmsCpuSetContainsProcessor(VmsKnownProcessors, CurrentProcessorNumber)
      || (v12 = (char *)VmsPlanCpuTable + 5440 * v11) == 0 )
    {
      v19 = KeGetCurrentProcessorNumberEx(0);
      KeBugCheckEx(0x121u, v11, v19, 0, 0);
    }
    NetDispatchProfilerLeave(v12 + 1152);
  }
LABEL_14:
  NdisMSendNetBufferListsComplete(v9, v3, v7 | v1);
  if ( !CurrentIrql && (VmsExecutionMode & 8) == 0 )
    KeLowerIrql(0);
  if ( KeGetCurrentIrql() == 2 )
  {
    v13 = KeGetCurrentProcessorNumberEx(0);
    v14 = v13;
    if ( v13 == -1
      || !(unsigned __int8)VmsCpuSetContainsProcessor(VmsKnownProcessors, v13)
      || (v15 = (char *)VmsPlanCpuTable + 5440 * v14) == 0 )
    {
      v20 = KeGetCurrentProcessorNumberEx(0);
      KeBugCheckEx(0x121u, v14, v20, 0, 0);
    }
    NetDispatchProfilerEnter(v15 + 1152, 1);
  }
  if ( BYTE1(WPP_GLOBAL_Control->Timer) > 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_id(
      WPP_GLOBAL_Control->DeviceExtension,
      0,
      22,
      12,
      (__int64)WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids,
      v4,
      v2);
  result = VmsPtGetNicHeaderAtIndex(v4, 0);
  v17 = result;
  if ( result )
  {
    v18 = KeGetCurrentProcessorNumberEx(0);
    result = *(_QWORD *)(v17 + 24);
    _InterlockedAdd64((volatile signed __int64 *)((v18 << 6) + result + 8), -v2);
  }
  return result;
}

```

## disassembly

```asm
0x1400f9cf0  push    rbx
0x1400f9cf2  push    rbp
0x1400f9cf3  push    rsi
0x1400f9cf4  push    rdi
0x1400f9cf5  push    r12
0x1400f9cf7  push    r13
0x1400f9cf9  push    r14
0x1400f9cfb  push    r15
0x1400f9cfd  sub     rsp, 48h
0x1400f9d01  mov     eax, cs:VmsDiagnosticFlags
0x1400f9d07  xor     ebx, ebx
0x1400f9d09  mov     r12d, [rcx+34h]
0x1400f9d0d  mov     edi, [rcx+30h]
0x1400f9d10  mov     rsi, [rcx+18h]
0x1400f9d14  mov     r14, [rcx+28h]
0x1400f9d18  mov     rcx, [rsp+88h]
0x1400f9d20  test    al, 1
0x1400f9d22  jz      short loc_1400F9D5D
0x1400f9d24  test    rsi, rsi
0x1400f9d27  jz      short loc_1400F9D5D
0x1400f9d29  mov     rax, [rsi+120h]
0x1400f9d30  test    rax, rax
0x1400f9d33  jz      short loc_1400F9D5D
0x1400f9d35  mov     rax, [rax+10h]
0x1400f9d39  test    rax, rax
0x1400f9d3c  jz      short loc_1400F9D5D
0x1400f9d3e  lea     rdx, aVmsmpnicsendne_0; "VmsMpNicSendNetBufferListsCompleteInter"...
0x1400f9d45  mov     dword ptr [rax+0B8h], 24Ch
0x1400f9d4f  mov     [rax+0B0h], rdx
0x1400f9d56  mov     [rax+0A8h], rcx
0x1400f9d5d  mov     r15d, ebx
0x1400f9d60  call    cs:__imp_KeGetCurrentIrql
0x1400f9d67  nop     dword ptr [rax+rax+00h]
0x1400f9d6c  mov     rcx, [r14+0CF0h]
0x1400f9d73  mov     bpl, al
0x1400f9d76  mov     r13, [rcx+18h]
0x1400f9d7a  test    al, al
0x1400f9d7c  jnz     short loc_1400F9DA0
0x1400f9d7e  mov     ecx, cs:VmsExecutionMode
0x1400f9d84  test    cl, 8
0x1400f9d87  jnz     short loc_1400F9DF7
0x1400f9d89  mov     cl, 2; NewIrql
0x1400f9d8b  mov     r15d, 1
0x1400f9d91  call    cs:__imp_KfRaiseIrql
0x1400f9d98  nop     dword ptr [rax+rax+00h]
0x1400f9d9d  mov     bpl, al
0x1400f9da0  cmp     bpl, 2
0x1400f9da4  jnz     short loc_1400F9DF7
0x1400f9da6  xor     ecx, ecx; ProcNumber
0x1400f9da8  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400f9daf  nop     dword ptr [rax+rax+00h]
0x1400f9db4  mov     ebx, eax
0x1400f9db6  cmp     eax, 0FFFFFFFFh
0x1400f9db9  jz      loc_1400F9F16
0x1400f9dbf  mov     edx, ebx
0x1400f9dc1  lea     rcx, VmsKnownProcessors
0x1400f9dc8  call    VmsCpuSetContainsProcessor
0x1400f9dcd  test    al, al
0x1400f9dcf  jz      loc_1400F9F16
0x1400f9dd5  imul    rcx, rbx, 1540h
0x1400f9ddc  add     rcx, cs:VmsPlanCpuTable
0x1400f9de3  jz      loc_1400F9F16
0x1400f9de9  add     rcx, 480h
0x1400f9df0  call    NetDispatchProfilerLeave
0x1400f9df5  xor     ebx, ebx
0x1400f9df7  or      r12d, r15d
0x1400f9dfa  mov     rdx, rsi; NetBufferList
0x1400f9dfd  mov     r8d, r12d; SendCompleteFlags
0x1400f9e00  mov     rcx, r13; MiniportAdapterHandle
0x1400f9e03  call    cs:__imp_NdisMSendNetBufferListsComplete
0x1400f9e0a  nop     dword ptr [rax+rax+00h]
0x1400f9e0f  test    bpl, bpl
0x1400f9e12  jnz     short loc_1400F9E2C
0x1400f9e14  mov     eax, cs:VmsExecutionMode
0x1400f9e1a  test    al, 8
0x1400f9e1c  jnz     short loc_1400F9E2C
0x1400f9e1e  xor     ecx, ecx; NewIrql
0x1400f9e20  call    cs:__imp_KeLowerIrql
0x1400f9e27  nop     dword ptr [rax+rax+00h]
0x1400f9e2c  call    cs:__imp_KeGetCurrentIrql
0x1400f9e33  nop     dword ptr [rax+rax+00h]
0x1400f9e38  cmp     al, 2
0x1400f9e3a  jnz     short loc_1400F9E92
0x1400f9e3c  xor     ecx, ecx; ProcNumber
0x1400f9e3e  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400f9e45  nop     dword ptr [rax+rax+00h]
0x1400f9e4a  mov     ebx, eax
0x1400f9e4c  cmp     eax, 0FFFFFFFFh
0x1400f9e4f  jz      loc_1400F9F48
0x1400f9e55  mov     edx, ebx
0x1400f9e57  lea     rcx, VmsKnownProcessors
0x1400f9e5e  call    VmsCpuSetContainsProcessor
0x1400f9e63  xor     esi, esi
0x1400f9e65  test    al, al
0x1400f9e67  jz      loc_1400F9F4A
0x1400f9e6d  imul    rcx, rbx, 1540h
0x1400f9e74  add     rcx, cs:VmsPlanCpuTable
0x1400f9e7b  jz      loc_1400F9F4A
0x1400f9e81  add     rcx, 480h
0x1400f9e88  lea     edx, [rsi+1]
0x1400f9e8b  call    NetDispatchProfilerEnter
0x1400f9e90  xor     ebx, ebx
0x1400f9e92  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f9e99  cmp     byte ptr [rcx+29h], 5
0x1400f9e9d  ja      short loc_1400F9EA5
0x1400f9e9f  cmp     [rcx+48h], bx
0x1400f9ea3  jz      short loc_1400F9ECF
0x1400f9ea5  mov     rcx, [rcx+40h]
0x1400f9ea9  lea     rax, WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids
0x1400f9eb0  mov     r9d, 0Ch
0x1400f9eb6  mov     [rsp+88h+var_58], edi
0x1400f9eba  mov     [rsp+88h+var_60], r14
0x1400f9ebf  xor     edx, edx
0x1400f9ec1  mov     [rsp+88h+BugCheckParameter4], rax
0x1400f9ec6  lea     r8d, [r9+0Ah]
0x1400f9eca  call    WPP_RECORDER_SF_id
0x1400f9ecf  xor     edx, edx
0x1400f9ed1  mov     rcx, r14
0x1400f9ed4  call    VmsPtGetNicHeaderAtIndex
0x1400f9ed9  mov     rbx, rax
0x1400f9edc  test    rax, rax
0x1400f9edf  jz      short loc_1400F9F04
0x1400f9ee1  xor     ecx, ecx; ProcNumber
0x1400f9ee3  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400f9eea  nop     dword ptr [rax+rax+00h]
0x1400f9eef  mov     ecx, eax
0x1400f9ef1  neg     edi
0x1400f9ef3  mov     rax, [rbx+18h]
0x1400f9ef7  shl     rcx, 6
0x1400f9efb  movsxd  rdx, edi
0x1400f9efe  lock add [rcx+rax+8], rdx
0x1400f9f04  add     rsp, 48h
0x1400f9f08  pop     r15
0x1400f9f0a  pop     r14
0x1400f9f0c  pop     r13
0x1400f9f0e  pop     r12
0x1400f9f10  pop     rdi
0x1400f9f11  pop     rsi
0x1400f9f12  pop     rbp
0x1400f9f13  pop     rbx
0x1400f9f14  retn
0x1400f9f16  xor     ecx, ecx; ProcNumber
0x1400f9f18  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400f9f1f  nop     dword ptr [rax+rax+00h]
0x1400f9f24  xor     r9d, r9d; BugCheckParameter3
0x1400f9f27  mov     [rsp+88h+BugCheckParameter4], 0; BugCheckParameter4
0x1400f9f30  mov     r8d, eax; BugCheckParameter2
0x1400f9f33  mov     rdx, rbx; BugCheckParameter1
0x1400f9f36  mov     ecx, 121h; BugCheckCode
0x1400f9f3b  call    cs:__imp_KeBugCheckEx
0x1400f9f48  xor     esi, esi
0x1400f9f4a  xor     ecx, ecx; ProcNumber
0x1400f9f4c  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400f9f53  nop     dword ptr [rax+rax+00h]
0x1400f9f58  xor     r9d, r9d; BugCheckParameter3
0x1400f9f5b  mov     [rsp+88h+BugCheckParameter4], rsi; BugCheckParameter4
0x1400f9f60  mov     r8d, eax; BugCheckParameter2
0x1400f9f63  mov     rdx, rbx; BugCheckParameter1
0x1400f9f66  mov     ecx, 121h; BugCheckCode
0x1400f9f6b  call    cs:__imp_KeBugCheckEx
```
