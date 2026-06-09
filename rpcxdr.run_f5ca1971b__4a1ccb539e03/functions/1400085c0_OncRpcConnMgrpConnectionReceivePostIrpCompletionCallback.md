# OncRpcConnMgrpConnectionReceivePostIrpCompletionCallback

- ea: `0x1400085c0`
- end: `0x140008755`
- name: `OncRpcConnMgrpConnectionReceivePostIrpCompletionCallback`
- size: `405`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x140001340`
- `0x140002104`
- `0x140002230`
- `0x140008034`
- `0x1400085c0`
- `0x140008878`
- `0x1400088f0`
- `0x14000f770`
- `0x14000fabc`

## import_xrefs

- `ntoskrnl!IoReuseIrp` at `0x1400086cb`
- `ntoskrnl!IoReuseIrp` at `0x1400086cb`

## pseudocode

```c
void __fastcall OncRpcConnMgrpConnectionReceivePostIrpCompletionCallback(__int64 a1)
{
  __int64 v1; // rax
  __int64 v3; // rbx
  int v4; // esi
  unsigned __int64 v5; // rsi
  __int64 v6; // r8
  __int64 v7; // rbp
  __int64 v8; // r14
  unsigned __int64 DescriptorAllocationLengthRemaining; // r8
  __int64 NextBufferDescriptor; // rax
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // r8

  v1 = *(_QWORD *)(a1 + 40);
  v3 = *(_QWORD *)(a1 + 56);
  v4 = *(_DWORD *)(v1 + 48);
  if ( v4 < 0 )
    goto LABEL_4;
  v5 = *(_QWORD *)(v1 + 56);
  if ( v5 != *(_QWORD *)(a1 + 24) )
  {
    v4 = -1073741300;
LABEL_4:
    OncRpcWiMgrSrvWorkItemFree(*(_QWORD *)(v3 + 160));
    *(_QWORD *)(v3 + 160) = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
      WPP_SF_qdLd(WPP_GLOBAL_Control->AttachedDevice, 31, v6, v3, *(_DWORD *)(v3 + 4), *(_DWORD *)(v3 + 80), v4);
    OncRpcConnMgrpConnectionDisconnectBySystem(v3);
    return;
  }
  v7 = *(_QWORD *)(a1 + 8);
  v8 = *(_QWORD *)(a1 + 16);
  LogOncrpcEvent(&ONCRPC_EVENT_PKT_RECEIVE_COMPLETION, (LPCGUID)(*(_QWORD *)(v3 + 160) + 2444LL));
  if ( v5 >= (unsigned int)OncRpcBufMgrGetDescriptorAllocationLengthRemaining(v7) )
    DescriptorAllocationLengthRemaining = (unsigned int)OncRpcBufMgrGetDescriptorAllocationLengthRemaining(v7);
  else
    DescriptorAllocationLengthRemaining = v5;
  *(_QWORD *)(v7 + 64) += DescriptorAllocationLengthRemaining;
  if ( DescriptorAllocationLengthRemaining < v5 )
  {
    NextBufferDescriptor = OncRpcBufMgrGetNextBufferDescriptor(v8, v7);
    *(_QWORD *)(NextBufferDescriptor + 64) += v5 - v11;
  }
  *(_QWORD *)(v3 + 144) += v5;
  IoReuseIrp(*(PIRP *)(a1 + 40), 259);
  if ( *(_BYTE *)(a1 + 32) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
      WPP_SF_qdLq(
        WPP_GLOBAL_Control->AttachedDevice,
        v12,
        v13,
        v3,
        *(_DWORD *)(v3 + 4),
        *(_DWORD *)(v3 + 80),
        *(_QWORD *)(v3 + 160));
    OncRpcWiMgrProcessSrvWorkItem(*(_QWORD *)(v3 + 160), v3, 0);
    *(_QWORD *)(v3 + 144) = 0;
    *(_QWORD *)(v3 + 160) = 0;
  }
}

```

## disassembly

```asm
0x1400085c0  push    rbx
0x1400085c2  push    rbp
0x1400085c3  push    rsi
0x1400085c4  push    rdi
0x1400085c5  push    r14
0x1400085c7  sub     rsp, 40h
0x1400085cb  mov     rax, [rcx+28h]
0x1400085cf  mov     rdi, rcx
0x1400085d2  mov     rbx, [rcx+38h]
0x1400085d6  mov     esi, [rax+30h]
0x1400085d9  test    esi, esi
0x1400085db  js      short loc_1400085EC
0x1400085dd  mov     rsi, [rax+38h]
0x1400085e1  cmp     rsi, [rcx+18h]
0x1400085e5  jz      short loc_14000865B
0x1400085e7  mov     esi, 0C000020Ch
0x1400085ec  mov     rcx, [rbx+0A0h]
0x1400085f3  call    OncRpcWiMgrSrvWorkItemFree
0x1400085f8  mov     qword ptr [rbx+0A0h], 0
0x140008603  mov     rcx, cs:WPP_GLOBAL_Control
0x14000860a  lea     rax, WPP_GLOBAL_Control
0x140008611  cmp     rcx, rax
0x140008614  jz      short loc_140008647
0x140008616  mov     eax, [rcx+2Ch]
0x140008619  test    al, 8
0x14000861b  jz      short loc_140008647
0x14000861d  mov     ecx, [rbx+4]
0x140008620  mov     edx, 1Fh
0x140008625  mov     eax, [rbx+50h]
0x140008628  mov     r9, rbx
0x14000862b  mov     dword ptr [rsp+68h+var_38], esi
0x14000862f  mov     [rsp+68h+var_40], eax
0x140008633  mov     [rsp+68h+var_48], ecx
0x140008637  mov     rcx, cs:WPP_GLOBAL_Control
0x14000863e  mov     rcx, [rcx+18h]
0x140008642  call    WPP_SF_qdLd
0x140008647  mov     rcx, rbx
0x14000864a  call    OncRpcConnMgrpConnectionDisconnectBySystem
0x14000864f  add     rsp, 40h
0x140008653  pop     r14
0x140008655  pop     rdi
0x140008656  pop     rsi
0x140008657  pop     rbp
0x140008658  pop     rbx
0x140008659  retn
0x14000865b  mov     rdx, [rbx+0A0h]
0x140008662  mov     rbp, [rcx+8]
0x140008666  add     rdx, 98Ch; ActivityId
0x14000866d  mov     r14, [rcx+10h]
0x140008671  lea     rcx, ONCRPC_EVENT_PKT_RECEIVE_COMPLETION; EventDescriptor
0x140008678  call    LogOncrpcEvent
0x14000867d  mov     rcx, rbp
0x140008680  call    OncRpcBufMgrGetDescriptorAllocationLengthRemaining
0x140008685  mov     r9d, eax
0x140008688  cmp     rsi, r9
0x14000868b  jnb     short loc_140008692
0x14000868d  mov     r8, rsi
0x140008690  jmp     short loc_14000869D
0x140008692  mov     rcx, rbp
0x140008695  call    OncRpcBufMgrGetDescriptorAllocationLengthRemaining
0x14000869a  mov     r8d, eax
0x14000869d  add     [rbp+40h], r8
0x1400086a1  cmp     r8, rsi
0x1400086a4  jnb     short loc_1400086BB
0x1400086a6  mov     rdx, rbp
0x1400086a9  mov     rcx, r14
0x1400086ac  call    OncRpcBufMgrGetNextBufferDescriptor
0x1400086b1  mov     rcx, rsi
0x1400086b4  sub     rcx, r8
0x1400086b7  add     [rax+40h], rcx
0x1400086bb  add     [rbx+90h], rsi
0x1400086c2  mov     edx, 103h; Iostatus
0x1400086c7  mov     rcx, [rdi+28h]; Irp
0x1400086cb  call    cs:__imp_IoReuseIrp
0x1400086d2  nop     dword ptr [rax+rax+00h]
0x1400086d7  cmp     byte ptr [rdi+20h], 0
0x1400086db  jz      loc_14000864F
0x1400086e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400086e8  lea     rax, WPP_GLOBAL_Control
0x1400086ef  cmp     rcx, rax
0x1400086f2  jz      short loc_140008728
0x1400086f4  mov     eax, [rcx+2Ch]
0x1400086f7  test    al, 8
0x1400086f9  jz      short loc_140008728
0x1400086fb  mov     ecx, [rbx+4]
0x1400086fe  mov     r9, rbx
0x140008701  mov     rax, [rbx+0A0h]
0x140008708  mov     [rsp+68h+var_38], rax
0x14000870d  mov     eax, [rbx+50h]
0x140008710  mov     [rsp+68h+var_40], eax
0x140008714  mov     [rsp+68h+var_48], ecx
0x140008718  mov     rcx, cs:WPP_GLOBAL_Control
0x14000871f  mov     rcx, [rcx+18h]
0x140008723  call    WPP_SF_qdLq
0x140008728  mov     rcx, [rbx+0A0h]
0x14000872f  xor     r8d, r8d
0x140008732  mov     rdx, rbx
0x140008735  call    OncRpcWiMgrProcessSrvWorkItem
0x14000873a  mov     qword ptr [rbx+90h], 0
0x140008745  mov     qword ptr [rbx+0A0h], 0
0x140008750  jmp     loc_14000864F
```
