# VmsMpNicSendCompleteDecrementAllCount

- ea: `0x140014020`
- end: `0x140014320`
- name: `VmsMpNicSendCompleteDecrementAllCount`
- size: `768`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140010940`
- `0x140012a90`
- `0x140014020`
- `0x140014330`
- `0x140046f1c`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x140014105`
- `ntoskrnl!KeBugCheckEx` at `0x1400141dc`
- `ntoskrnl!KeBugCheckEx` at `0x140014105`
- `ntoskrnl!KeBugCheckEx` at `0x1400141dc`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140014089`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400140b7`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400140e2`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001418e`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400141b9`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001421d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140014089`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400140b7`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400140e2`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001418e`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400141b9`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001421d`
- `ntoskrnl!KeLowerIrql` at `0x1400142de`
- `ntoskrnl!KeLowerIrql` at `0x1400142de`
- `ntoskrnl!KfRaiseIrql` at `0x1400142ba`
- `ntoskrnl!KfRaiseIrql` at `0x1400142ba`
- `ntoskrnl!KeGetCurrentIrql` at `0x140014059`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001417c`
- `ntoskrnl!KeGetCurrentIrql` at `0x140014059`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001417c`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x140014168`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x140014292`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x140014168`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x140014292`

## string_xrefs

- `0x140014138`: `VmsMpNicSendNetBufferListsCompleteInternal`

## pseudocode

```c
char __fastcall VmsMpNicSendCompleteDecrementAllCount(__int64 a1)
{
  int v1; // r14d
  int v2; // ebp
  struct _NET_BUFFER_LIST *v3; // rsi
  __int64 v4; // r15
  int v5; // r12d
  KIRQL CurrentIrql; // bl
  void *v7; // r13
  ULONG CurrentProcessorNumber; // eax
  ULONG_PTR v9; // rbx
  ULONG v10; // eax
  _QWORD *v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  ULONG v14; // eax
  ULONG_PTR v15; // rbx
  ULONG v16; // eax
  __int64 v17; // rcx
  char *v18; // rcx
  char *v19; // rcx
  _UNKNOWN *retaddr; // [rsp+88h] [rbp+0h]

  v1 = *(_DWORD *)(a1 + 52);
  v2 = *(_DWORD *)(a1 + 48);
  v3 = *(struct _NET_BUFFER_LIST **)(a1 + 24);
  v4 = *(_QWORD *)(a1 + 40);
  if ( (VmsDiagnosticFlags & 1) != 0 )
  {
    if ( v3 )
    {
      v11 = v3->NetBufferListInfo[18];
      if ( v11 )
      {
        v12 = v11[2];
        if ( v12 )
        {
          *(_DWORD *)(v12 + 184) = 588;
          *(_QWORD *)(v12 + 176) = "VmsMpNicSendNetBufferListsCompleteInternal";
          *(_QWORD *)(v12 + 168) = retaddr;
        }
      }
    }
  }
  v5 = 0;
  CurrentIrql = KeGetCurrentIrql();
  v7 = *(void **)(*(_QWORD *)(v4 + 3312) + 24LL);
  if ( !CurrentIrql && (VmsExecutionMode & 8) == 0 )
  {
    v5 = 1;
    CurrentIrql = KfRaiseIrql(2u);
  }
  if ( v4 != -1232 )
    _InterlockedAdd64(
      (volatile signed __int64 *)(((unsigned __int64)KeGetCurrentProcessorNumberEx(0) << 6) + *(_QWORD *)(v4 + 1256) + 16),
      -v2);
  if ( CurrentIrql == 2 )
  {
    CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
    v9 = CurrentProcessorNumber;
    if ( CurrentProcessorNumber == -1
      || !(unsigned __int8)VmsCpuSetContainsProcessor(VmsKnownProcessors, CurrentProcessorNumber)
      || (v19 = (char *)VmsPlanCpuTable + 5440 * v9) == 0 )
    {
      v10 = KeGetCurrentProcessorNumberEx(0);
      KeBugCheckEx(0x121u, v9, v10, 0, 0);
    }
    NetDispatchProfilerLeave(v19 + 1152);
    NdisMSendNetBufferListsComplete(v7, v3, v5 | v1);
  }
  else
  {
    NdisMSendNetBufferListsComplete(v7, v3, v5 | v1);
    if ( !CurrentIrql && (VmsExecutionMode & 8) == 0 )
      KeLowerIrql(0);
  }
  LOBYTE(v13) = KeGetCurrentIrql();
  if ( (_BYTE)v13 == 2 )
  {
    v14 = KeGetCurrentProcessorNumberEx(0);
    v15 = v14;
    if ( v14 == -1
      || !(unsigned __int8)VmsCpuSetContainsProcessor(VmsKnownProcessors, v14)
      || (v18 = (char *)VmsPlanCpuTable + 5440 * v15) == 0 )
    {
      v16 = KeGetCurrentProcessorNumberEx(0);
      KeBugCheckEx(0x121u, v15, v16, 0, 0);
    }
    LOBYTE(v13) = NetDispatchProfilerEnter(v18 + 1152, 1);
  }
  if ( BYTE1(WPP_GLOBAL_Control->Timer) > 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    LOBYTE(v13) = WPP_RECORDER_SF_id(
                    WPP_GLOBAL_Control->DeviceExtension,
                    0,
                    22,
                    12,
                    (__int64)WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids,
                    v4,
                    v2);
  if ( v4 != -1232 )
  {
    v17 = KeGetCurrentProcessorNumberEx(0);
    v13 = *(_QWORD *)(v4 + 1256);
    _InterlockedAdd64((volatile signed __int64 *)((v17 << 6) + v13 + 8), -v2);
  }
  return v13;
}

```

## disassembly

```asm
0x140014020  push    rbx
0x140014022  push    rbp
0x140014023  push    rsi
0x140014024  push    rdi
0x140014025  push    r12
0x140014027  push    r13
0x140014029  push    r14
0x14001402b  push    r15
0x14001402d  sub     rsp, 48h
0x140014031  mov     eax, cs:VmsDiagnosticFlags
0x140014037  mov     r14d, [rcx+34h]
0x14001403b  mov     ebp, [rcx+30h]
0x14001403e  mov     rsi, [rcx+18h]
0x140014042  mov     r15, [rcx+28h]
0x140014046  mov     rcx, [rsp+88h]
0x14001404e  test    al, 1
0x140014050  jnz     loc_140014112
0x140014056  xor     r12d, r12d
0x140014059  call    cs:__imp_KeGetCurrentIrql
0x140014060  nop     dword ptr [rax+rax+00h]
0x140014065  mov     rcx, [r15+0CF0h]
0x14001406c  movzx   ebx, al
0x14001406f  mov     r13, [rcx+18h]
0x140014073  test    al, al
0x140014075  jz      loc_1400142A3
0x14001407b  lea     rdi, [r15+4D0h]
0x140014082  test    rdi, rdi
0x140014085  jz      short loc_1400140AC
0x140014087  xor     ecx, ecx; ProcNumber
0x140014089  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140014090  nop     dword ptr [rax+rax+00h]
0x140014095  mov     ecx, ebp
0x140014097  neg     ecx
0x140014099  movsxd  rdx, ecx
0x14001409c  mov     ecx, eax
0x14001409e  mov     rax, [rdi+18h]
0x1400140a2  shl     rcx, 6
0x1400140a6  lock add [rcx+rax+10h], rdx
0x1400140ac  cmp     bl, 2
0x1400140af  jnz     loc_14001415C
0x1400140b5  xor     ecx, ecx; ProcNumber
0x1400140b7  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400140be  nop     dword ptr [rax+rax+00h]
0x1400140c3  mov     ebx, eax
0x1400140c5  cmp     eax, 0FFFFFFFFh
0x1400140c8  jz      short loc_1400140E0
0x1400140ca  mov     edx, ebx
0x1400140cc  lea     rcx, VmsKnownProcessors
0x1400140d3  call    VmsCpuSetContainsProcessor
0x1400140d8  test    al, al
0x1400140da  jnz     loc_140014266
0x1400140e0  xor     ecx, ecx; ProcNumber
0x1400140e2  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400140e9  nop     dword ptr [rax+rax+00h]
0x1400140ee  xor     r9d, r9d; BugCheckParameter3
0x1400140f1  mov     [rsp+88h+BugCheckParameter4], 0; BugCheckParameter4
0x1400140fa  mov     r8d, eax; BugCheckParameter2
0x1400140fd  mov     rdx, rbx; BugCheckParameter1
0x140014100  mov     ecx, 121h; BugCheckCode
0x140014105  call    cs:__imp_KeBugCheckEx
0x140014112  test    rsi, rsi
0x140014115  jz      loc_140014056
0x14001411b  mov     rax, [rsi+120h]
0x140014122  test    rax, rax
0x140014125  jz      loc_140014056
0x14001412b  mov     rax, [rax+10h]
0x14001412f  test    rax, rax
0x140014132  jz      loc_140014056
0x140014138  lea     rdx, aVmsmpnicsendne_0; "VmsMpNicSendNetBufferListsCompleteInter"...
0x14001413f  mov     dword ptr [rax+0B8h], 24Ch
0x140014149  mov     [rax+0B0h], rdx
0x140014150  mov     [rax+0A8h], rcx
0x140014157  jmp     loc_140014056
0x14001415c  or      r14d, r12d
0x14001415f  mov     rdx, rsi; NetBufferList
0x140014162  mov     r8d, r14d; SendCompleteFlags
0x140014165  mov     rcx, r13; MiniportAdapterHandle
0x140014168  call    cs:__imp_NdisMSendNetBufferListsComplete
0x14001416f  nop     dword ptr [rax+rax+00h]
0x140014174  test    bl, bl
0x140014176  jz      loc_1400142CE
0x14001417c  call    cs:__imp_KeGetCurrentIrql
0x140014183  nop     dword ptr [rax+rax+00h]
0x140014188  cmp     al, 2
0x14001418a  jnz     short loc_1400141FA
0x14001418c  xor     ecx, ecx; ProcNumber
0x14001418e  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140014195  nop     dword ptr [rax+rax+00h]
0x14001419a  mov     ebx, eax
0x14001419c  cmp     eax, 0FFFFFFFFh
0x14001419f  jz      short loc_1400141B7
0x1400141a1  mov     edx, ebx
0x1400141a3  lea     rcx, VmsKnownProcessors
0x1400141aa  call    VmsCpuSetContainsProcessor
0x1400141af  test    al, al
0x1400141b1  jnz     loc_140014250
0x1400141b7  xor     ecx, ecx; ProcNumber
0x1400141b9  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400141c0  nop     dword ptr [rax+rax+00h]
0x1400141c5  xor     r9d, r9d; BugCheckParameter3
0x1400141c8  mov     [rsp+88h+BugCheckParameter4], 0; BugCheckParameter4
0x1400141d1  mov     r8d, eax; BugCheckParameter2
0x1400141d4  mov     rdx, rbx; BugCheckParameter1
0x1400141d7  mov     ecx, 121h; BugCheckCode
0x1400141dc  call    cs:__imp_KeBugCheckEx
0x1400141e9  add     rcx, 480h
0x1400141f0  mov     edx, 1
0x1400141f5  call    NetDispatchProfilerEnter
0x1400141fa  mov     rcx, cs:WPP_GLOBAL_Control
0x140014201  cmp     byte ptr [rcx+29h], 5
0x140014205  ja      loc_1400142EF
0x14001420b  cmp     word ptr [rcx+48h], 0
0x140014210  jnz     loc_1400142EF
0x140014216  test    rdi, rdi
0x140014219  jz      short loc_14001423E
0x14001421b  xor     ecx, ecx; ProcNumber
0x14001421d  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140014224  nop     dword ptr [rax+rax+00h]
0x140014229  mov     ecx, eax
0x14001422b  neg     ebp
0x14001422d  mov     rax, [rdi+18h]
0x140014231  shl     rcx, 6
0x140014235  movsxd  rdx, ebp
0x140014238  lock add [rcx+rax+8], rdx
0x14001423e  add     rsp, 48h
0x140014242  pop     r15
0x140014244  pop     r14
0x140014246  pop     r13
0x140014248  pop     r12
0x14001424a  pop     rdi
0x14001424b  pop     rsi
0x14001424c  pop     rbp
0x14001424d  pop     rbx
0x14001424e  retn
0x140014250  imul    rcx, rbx, 1540h
0x140014257  add     rcx, cs:VmsPlanCpuTable
0x14001425e  jz      loc_1400141B7
0x140014264  jmp     short loc_1400141E9
0x140014266  imul    rcx, rbx, 1540h
0x14001426d  add     rcx, cs:VmsPlanCpuTable
0x140014274  jz      loc_1400140E0
0x14001427a  add     rcx, 480h
0x140014281  call    NetDispatchProfilerLeave
0x140014286  or      r14d, r12d
0x140014289  mov     rdx, rsi; NetBufferList
0x14001428c  mov     r8d, r14d; SendCompleteFlags
0x14001428f  mov     rcx, r13; MiniportAdapterHandle
0x140014292  call    cs:__imp_NdisMSendNetBufferListsComplete
0x140014299  nop     dword ptr [rax+rax+00h]
0x14001429e  jmp     loc_14001417C
0x1400142a3  mov     ecx, cs:VmsExecutionMode
0x1400142a9  test    cl, 8
0x1400142ac  jnz     loc_14001407B
0x1400142b2  mov     cl, 2; NewIrql
0x1400142b4  mov     r12d, 1
0x1400142ba  call    cs:__imp_KfRaiseIrql
0x1400142c1  nop     dword ptr [rax+rax+00h]
0x1400142c6  movzx   ebx, al
0x1400142c9  jmp     loc_14001407B
0x1400142ce  mov     eax, cs:VmsExecutionMode
0x1400142d4  test    al, 8
0x1400142d6  jnz     loc_14001417C
0x1400142dc  xor     ecx, ecx; NewIrql
0x1400142de  call    cs:__imp_KeLowerIrql
0x1400142e5  nop     dword ptr [rax+rax+00h]
0x1400142ea  jmp     loc_14001417C
0x1400142ef  mov     rcx, [rcx+40h]
0x1400142f3  lea     rax, WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids
0x1400142fa  mov     [rsp+88h+var_58], ebp
0x1400142fe  mov     r9d, 0Ch
0x140014304  mov     [rsp+88h+var_60], r15
0x140014309  xor     edx, edx
0x14001430b  mov     r8d, 16h
0x140014311  mov     [rsp+88h+BugCheckParameter4], rax
0x140014316  call    WPP_RECORDER_SF_id
0x14001431b  jmp     loc_140014216
```
