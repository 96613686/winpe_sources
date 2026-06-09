# VmsMpNicSendCompleteDecrementRoutedCount

- ea: `0x1400f9d60`
- end: `0x1400f9fe8`
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
- `0x1400f9d60`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x1400f9fab`
- `ntoskrnl!KeBugCheckEx` at `0x1400f9fdb`
- `ntoskrnl!KeBugCheckEx` at `0x1400f9fab`
- `ntoskrnl!KeBugCheckEx` at `0x1400f9fdb`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400f9e18`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400f9eae`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400f9f53`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400f9f88`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400f9fbc`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400f9e18`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400f9eae`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400f9f53`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400f9f88`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400f9fbc`
- `ntoskrnl!KeLowerIrql` at `0x1400f9e90`
- `ntoskrnl!KeLowerIrql` at `0x1400f9e90`
- `ntoskrnl!KfRaiseIrql` at `0x1400f9e01`
- `ntoskrnl!KfRaiseIrql` at `0x1400f9e01`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400f9dd0`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400f9e9c`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400f9dd0`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400f9e9c`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x1400f9e73`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x1400f9e73`

## string_xrefs

- `0x1400f9dae`: `VmsMpNicSendNetBufferListsCompleteInternal`

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
0x1400f9d60  push    rbx
0x1400f9d62  push    rbp
0x1400f9d63  push    rsi
0x1400f9d64  push    rdi
0x1400f9d65  push    r12
0x1400f9d67  push    r13
0x1400f9d69  push    r14
0x1400f9d6b  push    r15
0x1400f9d6d  sub     rsp, 48h
0x1400f9d71  mov     eax, cs:VmsDiagnosticFlags
0x1400f9d77  xor     ebx, ebx
0x1400f9d79  mov     r12d, [rcx+34h]
0x1400f9d7d  mov     edi, [rcx+30h]
0x1400f9d80  mov     rsi, [rcx+18h]
0x1400f9d84  mov     r14, [rcx+28h]
0x1400f9d88  mov     rcx, [rsp+88h]
0x1400f9d90  test    al, 1
0x1400f9d92  jz      short loc_1400F9DCD
0x1400f9d94  test    rsi, rsi
0x1400f9d97  jz      short loc_1400F9DCD
0x1400f9d99  mov     rax, [rsi+120h]
0x1400f9da0  test    rax, rax
0x1400f9da3  jz      short loc_1400F9DCD
0x1400f9da5  mov     rax, [rax+10h]
0x1400f9da9  test    rax, rax
0x1400f9dac  jz      short loc_1400F9DCD
0x1400f9dae  lea     rdx, aVmsmpnicsendne_0; "VmsMpNicSendNetBufferListsCompleteInter"...
0x1400f9db5  mov     dword ptr [rax+0B8h], 24Ch
0x1400f9dbf  mov     [rax+0B0h], rdx
0x1400f9dc6  mov     [rax+0A8h], rcx
0x1400f9dcd  mov     r15d, ebx
0x1400f9dd0  call    cs:__imp_KeGetCurrentIrql
0x1400f9dd7  nop     dword ptr [rax+rax+00h]
0x1400f9ddc  mov     rcx, [r14+0CF0h]
0x1400f9de3  mov     bpl, al
0x1400f9de6  mov     r13, [rcx+18h]
0x1400f9dea  test    al, al
0x1400f9dec  jnz     short loc_1400F9E10
0x1400f9dee  mov     ecx, cs:VmsExecutionMode
0x1400f9df4  test    cl, 8
0x1400f9df7  jnz     short loc_1400F9E67
0x1400f9df9  mov     cl, 2; NewIrql
0x1400f9dfb  mov     r15d, 1
0x1400f9e01  call    cs:__imp_KfRaiseIrql
0x1400f9e08  nop     dword ptr [rax+rax+00h]
0x1400f9e0d  mov     bpl, al
0x1400f9e10  cmp     bpl, 2
0x1400f9e14  jnz     short loc_1400F9E67
0x1400f9e16  xor     ecx, ecx; ProcNumber
0x1400f9e18  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400f9e1f  nop     dword ptr [rax+rax+00h]
0x1400f9e24  mov     ebx, eax
0x1400f9e26  cmp     eax, 0FFFFFFFFh
0x1400f9e29  jz      loc_1400F9F86
0x1400f9e2f  mov     edx, ebx
0x1400f9e31  lea     rcx, VmsKnownProcessors
0x1400f9e38  call    VmsCpuSetContainsProcessor
0x1400f9e3d  test    al, al
0x1400f9e3f  jz      loc_1400F9F86
0x1400f9e45  imul    rcx, rbx, 1540h
0x1400f9e4c  add     rcx, cs:VmsPlanCpuTable
0x1400f9e53  jz      loc_1400F9F86
0x1400f9e59  add     rcx, 480h
0x1400f9e60  call    NetDispatchProfilerLeave
0x1400f9e65  xor     ebx, ebx
0x1400f9e67  or      r12d, r15d
0x1400f9e6a  mov     rdx, rsi; NetBufferList
0x1400f9e6d  mov     r8d, r12d; SendCompleteFlags
0x1400f9e70  mov     rcx, r13; MiniportAdapterHandle
0x1400f9e73  call    cs:__imp_NdisMSendNetBufferListsComplete
0x1400f9e7a  nop     dword ptr [rax+rax+00h]
0x1400f9e7f  test    bpl, bpl
0x1400f9e82  jnz     short loc_1400F9E9C
0x1400f9e84  mov     eax, cs:VmsExecutionMode
0x1400f9e8a  test    al, 8
0x1400f9e8c  jnz     short loc_1400F9E9C
0x1400f9e8e  xor     ecx, ecx; NewIrql
0x1400f9e90  call    cs:__imp_KeLowerIrql
0x1400f9e97  nop     dword ptr [rax+rax+00h]
0x1400f9e9c  call    cs:__imp_KeGetCurrentIrql
0x1400f9ea3  nop     dword ptr [rax+rax+00h]
0x1400f9ea8  cmp     al, 2
0x1400f9eaa  jnz     short loc_1400F9F02
0x1400f9eac  xor     ecx, ecx; ProcNumber
0x1400f9eae  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400f9eb5  nop     dword ptr [rax+rax+00h]
0x1400f9eba  mov     ebx, eax
0x1400f9ebc  cmp     eax, 0FFFFFFFFh
0x1400f9ebf  jz      loc_1400F9FB8
0x1400f9ec5  mov     edx, ebx
0x1400f9ec7  lea     rcx, VmsKnownProcessors
0x1400f9ece  call    VmsCpuSetContainsProcessor
0x1400f9ed3  xor     esi, esi
0x1400f9ed5  test    al, al
0x1400f9ed7  jz      loc_1400F9FBA
0x1400f9edd  imul    rcx, rbx, 1540h
0x1400f9ee4  add     rcx, cs:VmsPlanCpuTable
0x1400f9eeb  jz      loc_1400F9FBA
0x1400f9ef1  add     rcx, 480h
0x1400f9ef8  lea     edx, [rsi+1]
0x1400f9efb  call    NetDispatchProfilerEnter
0x1400f9f00  xor     ebx, ebx
0x1400f9f02  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f9f09  cmp     byte ptr [rcx+29h], 5
0x1400f9f0d  ja      short loc_1400F9F15
0x1400f9f0f  cmp     [rcx+48h], bx
0x1400f9f13  jz      short loc_1400F9F3F
0x1400f9f15  mov     rcx, [rcx+40h]
0x1400f9f19  lea     rax, WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids
0x1400f9f20  mov     r9d, 0Ch
0x1400f9f26  mov     [rsp+88h+var_58], edi
0x1400f9f2a  mov     [rsp+88h+var_60], r14
0x1400f9f2f  xor     edx, edx
0x1400f9f31  mov     [rsp+88h+BugCheckParameter4], rax
0x1400f9f36  lea     r8d, [r9+0Ah]
0x1400f9f3a  call    WPP_RECORDER_SF_id
0x1400f9f3f  xor     edx, edx
0x1400f9f41  mov     rcx, r14
0x1400f9f44  call    VmsPtGetNicHeaderAtIndex
0x1400f9f49  mov     rbx, rax
0x1400f9f4c  test    rax, rax
0x1400f9f4f  jz      short loc_1400F9F74
0x1400f9f51  xor     ecx, ecx; ProcNumber
0x1400f9f53  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400f9f5a  nop     dword ptr [rax+rax+00h]
0x1400f9f5f  mov     ecx, eax
0x1400f9f61  neg     edi
0x1400f9f63  mov     rax, [rbx+18h]
0x1400f9f67  shl     rcx, 6
0x1400f9f6b  movsxd  rdx, edi
0x1400f9f6e  lock add [rcx+rax+8], rdx
0x1400f9f74  add     rsp, 48h
0x1400f9f78  pop     r15
0x1400f9f7a  pop     r14
0x1400f9f7c  pop     r13
0x1400f9f7e  pop     r12
0x1400f9f80  pop     rdi
0x1400f9f81  pop     rsi
0x1400f9f82  pop     rbp
0x1400f9f83  pop     rbx
0x1400f9f84  retn
0x1400f9f86  xor     ecx, ecx; ProcNumber
0x1400f9f88  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400f9f8f  nop     dword ptr [rax+rax+00h]
0x1400f9f94  xor     r9d, r9d; BugCheckParameter3
0x1400f9f97  mov     [rsp+88h+BugCheckParameter4], 0; BugCheckParameter4
0x1400f9fa0  mov     r8d, eax; BugCheckParameter2
0x1400f9fa3  mov     rdx, rbx; BugCheckParameter1
0x1400f9fa6  mov     ecx, 121h; BugCheckCode
0x1400f9fab  call    cs:__imp_KeBugCheckEx
0x1400f9fb8  xor     esi, esi
0x1400f9fba  xor     ecx, ecx; ProcNumber
0x1400f9fbc  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400f9fc3  nop     dword ptr [rax+rax+00h]
0x1400f9fc8  xor     r9d, r9d; BugCheckParameter3
0x1400f9fcb  mov     [rsp+88h+BugCheckParameter4], rsi; BugCheckParameter4
0x1400f9fd0  mov     r8d, eax; BugCheckParameter2
0x1400f9fd3  mov     rdx, rbx; BugCheckParameter1
0x1400f9fd6  mov     ecx, 121h; BugCheckCode
0x1400f9fdb  call    cs:__imp_KeBugCheckEx
```
