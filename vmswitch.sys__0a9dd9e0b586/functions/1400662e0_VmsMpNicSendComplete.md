# VmsMpNicSendComplete

- ea: `0x1400662e0`
- end: `0x140066523`
- name: `VmsMpNicSendComplete`
- size: `579`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140010940`
- `0x140012a90`
- `0x140014330`
- `0x1400662e0`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x140066398`
- `ntoskrnl!KeBugCheckEx` at `0x140066483`
- `ntoskrnl!KeBugCheckEx` at `0x140066398`
- `ntoskrnl!KeBugCheckEx` at `0x140066483`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14006634a`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140066375`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140066439`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140066460`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14006634a`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140066375`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140066439`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140066460`
- `ntoskrnl!KeLowerIrql` at `0x140066512`
- `ntoskrnl!KeLowerIrql` at `0x140066512`
- `ntoskrnl!KfRaiseIrql` at `0x1400664ee`
- `ntoskrnl!KfRaiseIrql` at `0x1400664ee`
- `ntoskrnl!KeGetCurrentIrql` at `0x14006631c`
- `ntoskrnl!KeGetCurrentIrql` at `0x140066423`
- `ntoskrnl!KeGetCurrentIrql` at `0x14006631c`
- `ntoskrnl!KeGetCurrentIrql` at `0x140066423`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x14006640e`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x14006640e`

## string_xrefs

- `0x1400663cb`: `VmsMpNicSendNetBufferListsCompleteInternal`

## pseudocode

```c
KIRQL __fastcall VmsMpNicSendComplete(__int64 a1, char a2)
{
  int v2; // r12d
  struct _NET_BUFFER_LIST *v4; // rdi
  __int64 v5; // rbx
  int v6; // ebp
  KIRQL CurrentIrql; // si
  void *v8; // r14
  ULONG CurrentProcessorNumber; // eax
  ULONG_PTR v10; // rbx
  ULONG v11; // eax
  _QWORD *v12; // rax
  __int64 v13; // rax
  KIRQL result; // al
  ULONG v15; // eax
  ULONG_PTR v16; // rbx
  ULONG v17; // eax
  char *v18; // rcx
  char *v19; // rcx
  _UNKNOWN *retaddr; // [rsp+78h] [rbp+0h]

  v2 = *(_DWORD *)(a1 + 52);
  v4 = *(struct _NET_BUFFER_LIST **)(a1 + 24);
  v5 = *(_QWORD *)(a1 + 40);
  if ( (VmsDiagnosticFlags & 1) != 0 )
  {
    if ( v4 )
    {
      v12 = v4->NetBufferListInfo[18];
      if ( v12 )
      {
        v13 = v12[2];
        if ( v13 )
        {
          *(_DWORD *)(v13 + 184) = 588;
          *(_QWORD *)(v13 + 176) = "VmsMpNicSendNetBufferListsCompleteInternal";
          *(_QWORD *)(v13 + 168) = retaddr;
        }
      }
    }
  }
  v6 = 0;
  CurrentIrql = KeGetCurrentIrql();
  v8 = *(void **)(*(_QWORD *)(v5 + 3312) + 24LL);
  if ( !CurrentIrql )
  {
    if ( (VmsExecutionMode & 8) != 0 )
      goto LABEL_11;
    v6 = 1;
    CurrentIrql = KfRaiseIrql(2u);
  }
  if ( CurrentIrql == 2 )
  {
    CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
    v10 = CurrentProcessorNumber;
    if ( CurrentProcessorNumber == -1
      || !(unsigned __int8)VmsCpuSetContainsProcessor(VmsKnownProcessors, CurrentProcessorNumber)
      || (v18 = (char *)VmsPlanCpuTable + 5440 * v10) == 0 )
    {
      v11 = KeGetCurrentProcessorNumberEx(0);
      KeBugCheckEx(0x121u, v10, v11, 0, 0);
    }
    NetDispatchProfilerLeave(v18 + 1152);
  }
LABEL_11:
  if ( a2 )
    v6 = 1;
  NdisMSendNetBufferListsComplete(v8, v4, v2 | v6);
  if ( !CurrentIrql && (VmsExecutionMode & 8) == 0 )
    KeLowerIrql(0);
  result = KeGetCurrentIrql();
  if ( result == 2 )
  {
    v15 = KeGetCurrentProcessorNumberEx(0);
    v16 = v15;
    if ( v15 == -1
      || !(unsigned __int8)VmsCpuSetContainsProcessor(VmsKnownProcessors, v15)
      || (v19 = (char *)VmsPlanCpuTable + 5440 * v16) == 0 )
    {
      v17 = KeGetCurrentProcessorNumberEx(0);
      KeBugCheckEx(0x121u, v16, v17, 0, 0);
    }
    return NetDispatchProfilerEnter(v19 + 1152, 1);
  }
  return result;
}

```

## disassembly

```asm
0x1400662e0  push    rbx
0x1400662e2  push    rbp
0x1400662e3  push    rsi
0x1400662e4  push    rdi
0x1400662e5  push    r12
0x1400662e7  push    r13
0x1400662e9  push    r14
0x1400662eb  push    r15
0x1400662ed  sub     rsp, 38h
0x1400662f1  mov     eax, cs:VmsDiagnosticFlags
0x1400662f7  mov     r13d, 1
0x1400662fd  mov     r12d, [rcx+34h]
0x140066301  mov     r15b, dl
0x140066304  mov     rdi, [rcx+18h]
0x140066308  mov     rbx, [rcx+28h]
0x14006630c  mov     rcx, [rsp+78h]
0x140066311  test    r13b, al
0x140066314  jnz     loc_1400663A5
0x14006631a  xor     ebp, ebp
0x14006631c  call    cs:__imp_KeGetCurrentIrql
0x140066323  nop     dword ptr [rax+rax+00h]
0x140066328  mov     rcx, [rbx+0CF0h]
0x14006632f  mov     sil, al
0x140066332  mov     r14, [rcx+18h]
0x140066336  test    al, al
0x140066338  jz      loc_1400664DA
0x14006633e  cmp     sil, 2
0x140066342  jnz     loc_1400663FB
0x140066348  xor     ecx, ecx; ProcNumber
0x14006634a  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140066351  nop     dword ptr [rax+rax+00h]
0x140066356  mov     ebx, eax
0x140066358  cmp     eax, 0FFFFFFFFh
0x14006635b  jz      short loc_140066373
0x14006635d  mov     edx, ebx
0x14006635f  lea     rcx, VmsKnownProcessors
0x140066366  call    VmsCpuSetContainsProcessor
0x14006636b  test    al, al
0x14006636d  jnz     loc_140066490
0x140066373  xor     ecx, ecx; ProcNumber
0x140066375  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14006637c  nop     dword ptr [rax+rax+00h]
0x140066381  xor     r9d, r9d; BugCheckParameter3
0x140066384  mov     [rsp+78h+BugCheckParameter4], 0; BugCheckParameter4
0x14006638d  mov     r8d, eax; BugCheckParameter2
0x140066390  mov     rdx, rbx; BugCheckParameter1
0x140066393  mov     ecx, 121h; BugCheckCode
0x140066398  call    cs:__imp_KeBugCheckEx
0x1400663a5  test    rdi, rdi
0x1400663a8  jz      loc_14006631A
0x1400663ae  mov     rax, [rdi+120h]
0x1400663b5  test    rax, rax
0x1400663b8  jz      loc_14006631A
0x1400663be  mov     rax, [rax+10h]
0x1400663c2  test    rax, rax
0x1400663c5  jz      loc_14006631A
0x1400663cb  lea     rdx, aVmsmpnicsendne_0; "VmsMpNicSendNetBufferListsCompleteInter"...
0x1400663d2  mov     dword ptr [rax+0B8h], 24Ch
0x1400663dc  mov     [rax+0B0h], rdx
0x1400663e3  mov     [rax+0A8h], rcx
0x1400663ea  jmp     loc_14006631A
0x1400663ef  add     rcx, 480h
0x1400663f6  call    NetDispatchProfilerLeave
0x1400663fb  test    r15b, r15b
0x1400663fe  mov     rdx, rdi; NetBufferList
0x140066401  mov     rcx, r14; MiniportAdapterHandle
0x140066404  cmovnz  ebp, r13d
0x140066408  or      ebp, r12d
0x14006640b  mov     r8d, ebp; SendCompleteFlags
0x14006640e  call    cs:__imp_NdisMSendNetBufferListsComplete
0x140066415  nop     dword ptr [rax+rax+00h]
0x14006641a  test    sil, sil
0x14006641d  jz      loc_140066502
0x140066423  call    cs:__imp_KeGetCurrentIrql
0x14006642a  nop     dword ptr [rax+rax+00h]
0x14006642f  cmp     al, 2
0x140066431  jnz     loc_1400664C8
0x140066437  xor     ecx, ecx; ProcNumber
0x140066439  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140066440  nop     dword ptr [rax+rax+00h]
0x140066445  mov     ebx, eax
0x140066447  cmp     eax, 0FFFFFFFFh
0x14006644a  jz      short loc_14006645E
0x14006644c  mov     edx, ebx
0x14006644e  lea     rcx, VmsKnownProcessors
0x140066455  call    VmsCpuSetContainsProcessor
0x14006645a  test    al, al
0x14006645c  jnz     short loc_1400664A9
0x14006645e  xor     ecx, ecx; ProcNumber
0x140066460  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140066467  nop     dword ptr [rax+rax+00h]
0x14006646c  xor     r9d, r9d; BugCheckParameter3
0x14006646f  mov     [rsp+78h+BugCheckParameter4], 0; BugCheckParameter4
0x140066478  mov     r8d, eax; BugCheckParameter2
0x14006647b  mov     rdx, rbx; BugCheckParameter1
0x14006647e  mov     ecx, 121h; BugCheckCode
0x140066483  call    cs:__imp_KeBugCheckEx
0x140066490  imul    rcx, rbx, 1540h
0x140066497  add     rcx, cs:VmsPlanCpuTable
0x14006649e  jz      loc_140066373
0x1400664a4  jmp     loc_1400663EF
0x1400664a9  imul    rcx, rbx, 1540h
0x1400664b0  add     rcx, cs:VmsPlanCpuTable
0x1400664b7  jz      short loc_14006645E
0x1400664b9  add     rcx, 480h
0x1400664c0  mov     edx, r13d
0x1400664c3  call    NetDispatchProfilerEnter
0x1400664c8  add     rsp, 38h
0x1400664cc  pop     r15
0x1400664ce  pop     r14
0x1400664d0  pop     r13
0x1400664d2  pop     r12
0x1400664d4  pop     rdi
0x1400664d5  pop     rsi
0x1400664d6  pop     rbp
0x1400664d7  pop     rbx
0x1400664d8  retn
0x1400664da  mov     ecx, cs:VmsExecutionMode
0x1400664e0  test    cl, 8
0x1400664e3  jnz     loc_1400663FB
0x1400664e9  mov     cl, 2; NewIrql
0x1400664eb  mov     ebp, r13d
0x1400664ee  call    cs:__imp_KfRaiseIrql
0x1400664f5  nop     dword ptr [rax+rax+00h]
0x1400664fa  mov     sil, al
0x1400664fd  jmp     loc_14006633E
0x140066502  mov     eax, cs:VmsExecutionMode
0x140066508  test    al, 8
0x14006650a  jnz     loc_140066423
0x140066510  xor     ecx, ecx; NewIrql
0x140066512  call    cs:__imp_KeLowerIrql
0x140066519  nop     dword ptr [rax+rax+00h]
0x14006651e  jmp     loc_140066423
```
