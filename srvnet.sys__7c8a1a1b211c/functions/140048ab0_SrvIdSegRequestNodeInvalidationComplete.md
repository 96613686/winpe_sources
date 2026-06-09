# SrvIdSegRequestNodeInvalidationComplete

- ea: `0x140048ab0`
- end: `0x140048bf3`
- name: `SrvIdSegRequestNodeInvalidationComplete`
- size: `323`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140016c84`
- `0x14001bc00`
- `0x14001bc5c`
- `0x140048ab0`
- `0x14004adf0`

## import_xrefs

- `ntoskrnl!IoQueueWorkItem` at `0x140048bdb`
- `ntoskrnl!IoQueueWorkItem` at `0x140048bdb`
- `msrpc!RpcAsyncCompleteCall` at `0x140048ad0`
- `msrpc!RpcAsyncCompleteCall` at `0x140048ad0`

## pseudocode

```c
void __fastcall SrvIdSegRequestNodeInvalidationComplete(PVOID Context, __int64 a2, int a3)
{
  unsigned int v4; // eax
  unsigned int v5; // edi
  int Reply; // [rsp+50h] [rbp+18h] BYREF

  if ( !a3 )
  {
    Reply = 0;
    v4 = RpcAsyncCompleteCall((PRPC_ASYNC_STATE)Context, &Reply);
    v5 = v4;
    if ( v4 != 259 )
    {
      RfsRpcBindingEndRpcCall(&SrvIdSegRpcBinding, v4);
      if ( v5 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
        {
          if ( BYTE1(WPP_GLOBAL_Control->Timer) )
            WPP_SF_dq(
              WPP_GLOBAL_Control->AttachedDevice,
              17,
              WPP_3bb578cf2b8e3f8c9711c1265018cc4d_Traceguids,
              v5,
              Context);
        }
        *((_DWORD *)Context + 28) = v5;
      }
      else if ( Reply )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_Dq(WPP_GLOBAL_Control->AttachedDevice);
        }
        *((_DWORD *)Context + 28) = -1073610685;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_3bb578cf2b8e3f8c9711c1265018cc4d_Traceguids, Context);
        }
        *((_DWORD *)Context + 28) = 0;
      }
      IoQueueWorkItem(*((PIO_WORKITEM *)Context + 15), InvalidationCompleteThread, CriticalWorkQueue, Context);
    }
  }
}

```

## disassembly

```asm
0x140048ab0  test    r8d, r8d
0x140048ab3  jnz     locret_140048BF1
0x140048ab9  mov     [rsp+arg_0], rbx
0x140048abe  push    rdi
0x140048abf  sub     rsp, 30h
0x140048ac3  lea     rdx, [rsp+38h+Reply]; Reply
0x140048ac8  mov     [rsp+38h+Reply], r8d
0x140048acd  mov     rbx, rcx
0x140048ad0  call    cs:__imp_RpcAsyncCompleteCall
0x140048ad7  nop     dword ptr [rax+rax+00h]
0x140048adc  mov     edi, eax
0x140048ade  cmp     eax, 103h
0x140048ae3  jz      loc_140048BE7
0x140048ae9  mov     edx, eax
0x140048aeb  lea     rcx, SrvIdSegRpcBinding
0x140048af2  call    RfsRpcBindingEndRpcCall
0x140048af7  test    edi, edi
0x140048af9  jz      short loc_140048B44
0x140048afb  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140048b02  lea     rcx, WPP_GLOBAL_Control
0x140048b09  cmp     r10, rcx
0x140048b0c  jz      short loc_140048B3C
0x140048b0e  test    dword ptr [r10+2Ch], 40000h
0x140048b16  jz      short loc_140048B3C
0x140048b18  cmp     byte ptr [r10+29h], 1
0x140048b1d  jb      short loc_140048B3C
0x140048b1f  mov     rcx, [r10+18h]
0x140048b23  lea     r8, WPP_3bb578cf2b8e3f8c9711c1265018cc4d_Traceguids
0x140048b2a  mov     edx, 11h
0x140048b2f  mov     [rsp+38h+var_18], rbx
0x140048b34  mov     r9d, edi
0x140048b37  call    WPP_SF_dq
0x140048b3c  mov     [rbx+70h], edi
0x140048b3f  jmp     loc_140048BCA
0x140048b44  mov     r9d, [rsp+38h+Reply]
0x140048b49  test    r9d, r9d
0x140048b4c  jz      short loc_140048B87
0x140048b4e  mov     rdx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140048b55  lea     rcx, WPP_GLOBAL_Control
0x140048b5c  cmp     rdx, rcx
0x140048b5f  jz      short loc_140048B7E
0x140048b61  test    dword ptr [rdx+2Ch], 40000h
0x140048b68  jz      short loc_140048B7E
0x140048b6a  cmp     byte ptr [rdx+29h], 1
0x140048b6e  jb      short loc_140048B7E
0x140048b70  mov     rcx, [rdx+18h]
0x140048b74  mov     [rsp+38h+var_18], rbx
0x140048b79  call    WPP_SF_Dq
0x140048b7e  mov     dword ptr [rbx+70h], 0C0020043h
0x140048b85  jmp     short loc_140048BCA
0x140048b87  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140048b8e  lea     rcx, WPP_GLOBAL_Control
0x140048b95  cmp     r10, rcx
0x140048b98  jz      short loc_140048BC3
0x140048b9a  test    dword ptr [r10+2Ch], 40000h
0x140048ba2  jz      short loc_140048BC3
0x140048ba4  cmp     byte ptr [r10+29h], 4
0x140048ba9  jb      short loc_140048BC3
0x140048bab  mov     rcx, [r10+18h]
0x140048baf  lea     r8, WPP_3bb578cf2b8e3f8c9711c1265018cc4d_Traceguids
0x140048bb6  mov     edx, 13h
0x140048bbb  mov     r9, rbx
0x140048bbe  call    WPP_SF_q
0x140048bc3  mov     dword ptr [rbx+70h], 0
0x140048bca  mov     rcx, [rbx+78h]; IoWorkItem
0x140048bce  lea     rdx, InvalidationCompleteThread; WorkerRoutine
0x140048bd5  mov     r9, rbx; Context
0x140048bd8  xor     r8d, r8d; QueueType
0x140048bdb  call    cs:__imp_IoQueueWorkItem
0x140048be2  nop     dword ptr [rax+rax+00h]
0x140048be7  mov     rbx, [rsp+38h+arg_0]
0x140048bec  add     rsp, 30h
0x140048bf0  pop     rdi
0x140048bf1  retn
```
