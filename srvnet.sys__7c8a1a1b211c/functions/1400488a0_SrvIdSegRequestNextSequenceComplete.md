# SrvIdSegRequestNextSequenceComplete

- ea: `0x1400488a0`
- end: `0x140048943`
- name: `SrvIdSegRequestNextSequenceComplete`
- size: `163`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140014a00`
- `0x1400488a0`
- `0x14004adf0`
- `0x14004d520`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140048919`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140048919`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400488df`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400488df`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004892d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004892d`
- `msrpc!RpcAsyncCompleteCall` at `0x1400488b6`
- `msrpc!RpcAsyncCompleteCall` at `0x1400488b6`

## pseudocode

```c
void __fastcall SrvIdSegRequestNextSequenceComplete(struct _RPC_ASYNC_STATE *P, __int64 a2, int a3)
{
  unsigned int v4; // eax
  int v5; // ebx
  unsigned int Signature; // esi
  unsigned int Size; // ebp
  __int64 v8; // rcx

  if ( !a3 )
  {
    v4 = RpcAsyncCompleteCall(P, 0);
    v5 = v4;
    if ( v4 != 259 )
    {
      RfsRpcBindingEndRpcCall(&SrvIdSegRpcBinding, v4);
      Signature = P[1].Signature;
      Size = P[1].Size;
      KeEnterCriticalRegion();
      if ( v5 < 0 && (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x8000) != 0 )
        McTemplateK0t_EtwWriteTransfer(v8, SRVNET_EVENT_GET_NEXT_ID_FAILURE, 0, (unsigned int)v5);
      SrvAdminNodeReserveNextSequenceComplete(Size, Signature, (unsigned int)v5, 0);
      KeLeaveCriticalRegion();
      ExFreePoolWithTag(P, 0x6662534Cu);
    }
  }
}

```

## disassembly

```asm
0x1400488a0  test    r8d, r8d
0x1400488a3  jnz     locret_140048941
0x1400488a9  push    rbx
0x1400488aa  push    rbp
0x1400488ab  push    rsi
0x1400488ac  push    rdi
0x1400488ad  sub     rsp, 28h
0x1400488b1  xor     edx, edx; Reply
0x1400488b3  mov     rdi, rcx
0x1400488b6  call    cs:__imp_RpcAsyncCompleteCall
0x1400488bd  nop     dword ptr [rax+rax+00h]
0x1400488c2  mov     ebx, eax
0x1400488c4  cmp     eax, 103h
0x1400488c9  jz      short loc_140048939
0x1400488cb  mov     edx, eax
0x1400488cd  lea     rcx, SrvIdSegRpcBinding
0x1400488d4  call    RfsRpcBindingEndRpcCall
0x1400488d9  mov     esi, [rdi+5Ch]
0x1400488dc  mov     ebp, [rdi+58h]
0x1400488df  call    cs:__imp_KeEnterCriticalRegion
0x1400488e6  nop     dword ptr [rax+rax+00h]
0x1400488eb  test    ebx, ebx
0x1400488ed  jns     short loc_14004890A
0x1400488ef  cmp     byte ptr cs:WPP_MAIN_CB.Queue+11h, 0
0x1400488f6  jge     short loc_14004890A
0x1400488f8  mov     r9d, ebx
0x1400488fb  lea     rdx, SRVNET_EVENT_GET_NEXT_ID_FAILURE
0x140048902  xor     r8d, r8d
0x140048905  call    McTemplateK0t_EtwWriteTransfer
0x14004890a  xor     r9d, r9d
0x14004890d  mov     r8d, ebx
0x140048910  mov     edx, esi
0x140048912  mov     ecx, ebp
0x140048914  call    SrvAdminNodeReserveNextSequenceComplete
0x140048919  call    cs:__imp_KeLeaveCriticalRegion
0x140048920  nop     dword ptr [rax+rax+00h]
0x140048925  mov     edx, 6662534Ch; Tag
0x14004892a  mov     rcx, rdi; P
0x14004892d  call    cs:__imp_ExFreePoolWithTag
0x140048934  nop     dword ptr [rax+rax+00h]
0x140048939  add     rsp, 28h
0x14004893d  pop     rdi
0x14004893e  pop     rsi
0x14004893f  pop     rbp
0x140048940  pop     rbx
0x140048941  retn
```
