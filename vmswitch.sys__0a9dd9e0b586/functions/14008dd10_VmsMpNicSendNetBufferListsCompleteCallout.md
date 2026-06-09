# VmsMpNicSendNetBufferListsCompleteCallout

- ea: `0x14008dd10`
- end: `0x14008dfea`
- name: `VmsMpNicSendNetBufferListsCompleteCallout`
- size: `730`
- prototype: `EXPAND_STACK_CALLOUT`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140010940`
- `0x140012a90`
- `0x140014330`
- `0x140017a7c`
- `0x140046f1c`
- `0x14008dd10`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x14008dfaf`
- `ntoskrnl!KeBugCheckEx` at `0x14008dfdd`
- `ntoskrnl!KeBugCheckEx` at `0x14008dfaf`
- `ntoskrnl!KeBugCheckEx` at `0x14008dfdd`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14008dde6`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14008de11`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14008dead`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14008df57`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14008df8c`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14008dfbe`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14008dde6`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14008de11`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14008dead`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14008df57`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14008df8c`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14008dfbe`
- `ntoskrnl!KeLowerIrql` at `0x14008de8f`
- `ntoskrnl!KeLowerIrql` at `0x14008de8f`
- `ntoskrnl!KfRaiseIrql` at `0x14008ddbd`
- `ntoskrnl!KfRaiseIrql` at `0x14008ddbd`
- `ntoskrnl!KeGetCurrentIrql` at `0x14008dd83`
- `ntoskrnl!KeGetCurrentIrql` at `0x14008de9b`
- `ntoskrnl!KeGetCurrentIrql` at `0x14008dd83`
- `ntoskrnl!KeGetCurrentIrql` at `0x14008de9b`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x14008de6f`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x14008de6f`

## string_xrefs

- `0x14008dd61`: `VmsMpNicSendNetBufferListsCompleteInternal`

## pseudocode

```c
void __fastcall VmsMpNicSendNetBufferListsCompleteCallout(_DWORD *Parameter)
{
  int v1; // r12d
  int v2; // r13d
  int v3; // edi
  struct _NET_BUFFER_LIST *v4; // r14
  __int64 v5; // rbp
  _QWORD *v6; // rax
  __int64 v7; // rax
  int v8; // r15d
  KIRQL CurrentIrql; // si
  __int64 NicHeaderAtIndex; // rbx
  ULONG CurrentProcessorNumber; // eax
  ULONG_PTR v12; // rbx
  char *v13; // rcx
  ULONG v14; // eax
  ULONG_PTR v15; // rbx
  char *v16; // rcx
  __int64 v17; // rbx
  ULONG v18; // eax
  ULONG v19; // eax
  _UNKNOWN *retaddr; // [rsp+88h] [rbp+0h]
  NDIS_HANDLE MiniportAdapterHandle; // [rsp+90h] [rbp+8h]

  v1 = Parameter[6];
  v2 = Parameter[5];
  v3 = Parameter[4];
  v4 = (struct _NET_BUFFER_LIST *)*((_QWORD *)Parameter + 1);
  v5 = *(_QWORD *)Parameter;
  if ( (VmsDiagnosticFlags & 1) != 0 )
  {
    if ( v4 )
    {
      v6 = v4->NetBufferListInfo[18];
      if ( v6 )
      {
        v7 = v6[2];
        if ( v7 )
        {
          *(_DWORD *)(v7 + 184) = 588;
          *(_QWORD *)(v7 + 176) = "VmsMpNicSendNetBufferListsCompleteInternal";
          *(_QWORD *)(v7 + 168) = retaddr;
        }
      }
    }
  }
  v8 = 0;
  CurrentIrql = KeGetCurrentIrql();
  MiniportAdapterHandle = *(NDIS_HANDLE *)(*(_QWORD *)(v5 + 3312) + 24LL);
  if ( !CurrentIrql && (VmsExecutionMode & 8) == 0 )
  {
    v8 = 1;
    CurrentIrql = KfRaiseIrql(2u);
  }
  if ( (v1 & 2) != 0 )
  {
    NicHeaderAtIndex = VmsPtGetNicHeaderAtIndex(v5, 0);
    if ( NicHeaderAtIndex )
      _InterlockedAdd64(
        (volatile signed __int64 *)(((unsigned __int64)KeGetCurrentProcessorNumberEx(0) << 6)
                                  + *(_QWORD *)(NicHeaderAtIndex + 24)
                                  + 16),
        -v3);
  }
  if ( CurrentIrql == 2 )
  {
    CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
    v12 = CurrentProcessorNumber;
    if ( CurrentProcessorNumber == -1
      || !(unsigned __int8)VmsCpuSetContainsProcessor(VmsKnownProcessors, CurrentProcessorNumber)
      || (v13 = (char *)VmsPlanCpuTable + 5440 * v12) == 0 )
    {
      v18 = KeGetCurrentProcessorNumberEx(0);
      KeBugCheckEx(0x121u, v12, v18, 0, 0);
    }
    NetDispatchProfilerLeave(v13 + 1152);
  }
  NdisMSendNetBufferListsComplete(MiniportAdapterHandle, v4, v8 | v2);
  if ( !CurrentIrql && (VmsExecutionMode & 8) == 0 )
    KeLowerIrql(0);
  if ( KeGetCurrentIrql() == 2 )
  {
    v14 = KeGetCurrentProcessorNumberEx(0);
    v15 = v14;
    if ( v14 == -1
      || !(unsigned __int8)VmsCpuSetContainsProcessor(VmsKnownProcessors, v14)
      || (v16 = (char *)VmsPlanCpuTable + 5440 * v15) == 0 )
    {
      v19 = KeGetCurrentProcessorNumberEx(0);
      KeBugCheckEx(0x121u, v15, v19, 0, 0);
    }
    NetDispatchProfilerEnter(v16 + 1152, 1);
  }
  if ( (v1 & 1) != 0 )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) > 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
      WPP_RECORDER_SF_id(
        WPP_GLOBAL_Control->DeviceExtension,
        0,
        22,
        12,
        (__int64)WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids,
        v5,
        v3);
    v17 = VmsPtGetNicHeaderAtIndex(v5, 0);
    if ( v17 )
      _InterlockedAdd64(
        (volatile signed __int64 *)(((unsigned __int64)KeGetCurrentProcessorNumberEx(0) << 6) + *(_QWORD *)(v17 + 24) + 8),
        -v3);
  }
}

```

## disassembly

```asm
0x14008dd10  push    rbx
0x14008dd12  push    rbp
0x14008dd13  push    rsi
0x14008dd14  push    rdi
0x14008dd15  push    r12
0x14008dd17  push    r13
0x14008dd19  push    r14
0x14008dd1b  push    r15
0x14008dd1d  sub     rsp, 48h
0x14008dd21  mov     eax, cs:VmsDiagnosticFlags
0x14008dd27  xor     ebx, ebx
0x14008dd29  mov     r12d, [rcx+18h]
0x14008dd2d  mov     r13d, [rcx+14h]
0x14008dd31  mov     edi, [rcx+10h]
0x14008dd34  mov     r14, [rcx+8]
0x14008dd38  mov     rbp, [rcx]
0x14008dd3b  mov     rcx, [rsp+88h]
0x14008dd43  test    al, 1
0x14008dd45  jz      short loc_14008DD80
0x14008dd47  test    r14, r14
0x14008dd4a  jz      short loc_14008DD80
0x14008dd4c  mov     rax, [r14+120h]
0x14008dd53  test    rax, rax
0x14008dd56  jz      short loc_14008DD80
0x14008dd58  mov     rax, [rax+10h]
0x14008dd5c  test    rax, rax
0x14008dd5f  jz      short loc_14008DD80
0x14008dd61  lea     rdx, aVmsmpnicsendne_0; "VmsMpNicSendNetBufferListsCompleteInter"...
0x14008dd68  mov     dword ptr [rax+0B8h], 24Ch
0x14008dd72  mov     [rax+0B0h], rdx
0x14008dd79  mov     [rax+0A8h], rcx
0x14008dd80  mov     r15d, ebx
0x14008dd83  call    cs:__imp_KeGetCurrentIrql
0x14008dd8a  nop     dword ptr [rax+rax+00h]
0x14008dd8f  mov     rcx, [rbp+0CF0h]
0x14008dd96  mov     sil, al
0x14008dd99  mov     rax, [rcx+18h]
0x14008dd9d  mov     [rsp+88h+MiniportAdapterHandle], rax
0x14008dda5  test    sil, sil
0x14008dda8  jnz     short loc_14008DDCC
0x14008ddaa  mov     ecx, cs:VmsExecutionMode
0x14008ddb0  test    cl, 8
0x14008ddb3  jnz     short loc_14008DDCC
0x14008ddb5  mov     cl, 2; NewIrql
0x14008ddb7  mov     r15d, 1
0x14008ddbd  call    cs:__imp_KfRaiseIrql
0x14008ddc4  nop     dword ptr [rax+rax+00h]
0x14008ddc9  mov     sil, al
0x14008ddcc  test    r12b, 2
0x14008ddd0  jz      short loc_14008DE09
0x14008ddd2  xor     edx, edx
0x14008ddd4  mov     rcx, rbp
0x14008ddd7  call    VmsPtGetNicHeaderAtIndex
0x14008dddc  mov     rbx, rax
0x14008dddf  test    rax, rax
0x14008dde2  jz      short loc_14008DE09
0x14008dde4  xor     ecx, ecx; ProcNumber
0x14008dde6  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14008dded  nop     dword ptr [rax+rax+00h]
0x14008ddf2  mov     ecx, edi
0x14008ddf4  neg     ecx
0x14008ddf6  movsxd  rdx, ecx
0x14008ddf9  mov     ecx, eax
0x14008ddfb  mov     rax, [rbx+18h]
0x14008ddff  shl     rcx, 6
0x14008de03  lock add [rcx+rax+10h], rdx
0x14008de09  cmp     sil, 2
0x14008de0d  jnz     short loc_14008DE5E
0x14008de0f  xor     ecx, ecx; ProcNumber
0x14008de11  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14008de18  nop     dword ptr [rax+rax+00h]
0x14008de1d  mov     ebx, eax
0x14008de1f  cmp     eax, 0FFFFFFFFh
0x14008de22  jz      loc_14008DF8A
0x14008de28  mov     edx, ebx
0x14008de2a  lea     rcx, VmsKnownProcessors
0x14008de31  call    VmsCpuSetContainsProcessor
0x14008de36  test    al, al
0x14008de38  jz      loc_14008DF8A
0x14008de3e  imul    rcx, rbx, 1540h
0x14008de45  add     rcx, cs:VmsPlanCpuTable
0x14008de4c  jz      loc_14008DF8A
0x14008de52  add     rcx, 480h
0x14008de59  call    NetDispatchProfilerLeave
0x14008de5e  mov     rcx, [rsp+88h+MiniportAdapterHandle]; MiniportAdapterHandle
0x14008de66  or      r13d, r15d
0x14008de69  mov     r8d, r13d; SendCompleteFlags
0x14008de6c  mov     rdx, r14; NetBufferList
0x14008de6f  call    cs:__imp_NdisMSendNetBufferListsComplete
0x14008de76  nop     dword ptr [rax+rax+00h]
0x14008de7b  xor     r14d, r14d
0x14008de7e  test    sil, sil
0x14008de81  jnz     short loc_14008DE9B
0x14008de83  mov     eax, cs:VmsExecutionMode
0x14008de89  test    al, 8
0x14008de8b  jnz     short loc_14008DE9B
0x14008de8d  xor     ecx, ecx; NewIrql
0x14008de8f  call    cs:__imp_KeLowerIrql
0x14008de96  nop     dword ptr [rax+rax+00h]
0x14008de9b  call    cs:__imp_KeGetCurrentIrql
0x14008dea2  nop     dword ptr [rax+rax+00h]
0x14008dea7  cmp     al, 2
0x14008dea9  jnz     short loc_14008DEFF
0x14008deab  xor     ecx, ecx; ProcNumber
0x14008dead  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14008deb4  nop     dword ptr [rax+rax+00h]
0x14008deb9  mov     ebx, eax
0x14008debb  cmp     eax, 0FFFFFFFFh
0x14008debe  jz      loc_14008DFBC
0x14008dec4  mov     edx, ebx
0x14008dec6  lea     rcx, VmsKnownProcessors
0x14008decd  call    VmsCpuSetContainsProcessor
0x14008ded2  test    al, al
0x14008ded4  jz      loc_14008DFBC
0x14008deda  imul    rcx, rbx, 1540h
0x14008dee1  add     rcx, cs:VmsPlanCpuTable
0x14008dee8  jz      loc_14008DFBC
0x14008deee  add     rcx, 480h
0x14008def5  mov     edx, 1
0x14008defa  call    NetDispatchProfilerEnter
0x14008deff  test    r12b, 1
0x14008df03  jz      short loc_14008DF78
0x14008df05  mov     rcx, cs:WPP_GLOBAL_Control
0x14008df0c  cmp     byte ptr [rcx+29h], 5
0x14008df10  ja      short loc_14008DF19
0x14008df12  cmp     [rcx+48h], r14w
0x14008df17  jz      short loc_14008DF43
0x14008df19  mov     rcx, [rcx+40h]
0x14008df1d  lea     rax, WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids
0x14008df24  mov     r9d, 0Ch
0x14008df2a  mov     [rsp+88h+var_58], edi
0x14008df2e  mov     [rsp+88h+var_60], rbp
0x14008df33  xor     edx, edx
0x14008df35  mov     [rsp+88h+BugCheckParameter4], rax
0x14008df3a  lea     r8d, [r9+0Ah]
0x14008df3e  call    WPP_RECORDER_SF_id
0x14008df43  xor     edx, edx
0x14008df45  mov     rcx, rbp
0x14008df48  call    VmsPtGetNicHeaderAtIndex
0x14008df4d  mov     rbx, rax
0x14008df50  test    rax, rax
0x14008df53  jz      short loc_14008DF78
0x14008df55  xor     ecx, ecx; ProcNumber
0x14008df57  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14008df5e  nop     dword ptr [rax+rax+00h]
0x14008df63  mov     ecx, eax
0x14008df65  neg     edi
0x14008df67  mov     rax, [rbx+18h]
0x14008df6b  shl     rcx, 6
0x14008df6f  movsxd  rdx, edi
0x14008df72  lock add [rcx+rax+8], rdx
0x14008df78  add     rsp, 48h
0x14008df7c  pop     r15
0x14008df7e  pop     r14
0x14008df80  pop     r13
0x14008df82  pop     r12
0x14008df84  pop     rdi
0x14008df85  pop     rsi
0x14008df86  pop     rbp
0x14008df87  pop     rbx
0x14008df88  retn
0x14008df8a  xor     ecx, ecx; ProcNumber
0x14008df8c  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14008df93  nop     dword ptr [rax+rax+00h]
0x14008df98  xor     r9d, r9d; BugCheckParameter3
0x14008df9b  mov     [rsp+88h+BugCheckParameter4], 0; BugCheckParameter4
0x14008dfa4  mov     r8d, eax; BugCheckParameter2
0x14008dfa7  mov     rdx, rbx; BugCheckParameter1
0x14008dfaa  mov     ecx, 121h; BugCheckCode
0x14008dfaf  call    cs:__imp_KeBugCheckEx
0x14008dfbc  xor     ecx, ecx; ProcNumber
0x14008dfbe  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14008dfc5  nop     dword ptr [rax+rax+00h]
0x14008dfca  xor     r9d, r9d; BugCheckParameter3
0x14008dfcd  mov     [rsp+88h+BugCheckParameter4], r14; BugCheckParameter4
0x14008dfd2  mov     r8d, eax; BugCheckParameter2
0x14008dfd5  mov     rdx, rbx; BugCheckParameter1
0x14008dfd8  mov     ecx, 121h; BugCheckCode
0x14008dfdd  call    cs:__imp_KeBugCheckEx
```
