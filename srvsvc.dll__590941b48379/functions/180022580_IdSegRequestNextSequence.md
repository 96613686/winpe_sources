# IdSegRequestNextSequence

- ea: `0x180022580`
- end: `0x18002269e`
- name: `IdSegRequestNextSequence`
- size: `286`
- prototype: `unsigned int __fastcall(PRPC_ASYNC_STATE pAsync, RPC_BINDING_HANDLE BindingHandle, __int64, __int64, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180020dc0`
- `0x180020de8`
- `0x180022580`
- `0x18002282c`

## import_xrefs

- `ntdll!RtlAcquireResourceShared` at `0x180022607`
- `ntdll!RtlAcquireResourceShared` at `0x180022607`
- `ntdll!RtlReleaseResource` at `0x180022668`
- `ntdll!RtlReleaseResource` at `0x180022668`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18002267e`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18002267e`
- `RPCRT4!RpcAsyncAbortCall` at `0x1800225ad`
- `RPCRT4!RpcAsyncAbortCall` at `0x180022688`
- `RPCRT4!RpcAsyncAbortCall` at `0x1800225ad`
- `RPCRT4!RpcAsyncAbortCall` at `0x180022688`
- `RPCRT4!RpcServerTestCancel` at `0x18002259b`
- `RPCRT4!RpcServerTestCancel` at `0x18002259b`

## pseudocode

```c
unsigned int __fastcall IdSegRequestNextSequence(
        PRPC_ASYNC_STATE pAsync,
        RPC_BINDING_HANDLE BindingHandle,
        __int64 a3,
        __int64 a4,
        unsigned int *a5)
{
  unsigned int result; // eax
  unsigned int Sequence; // ebx

  if ( RpcServerTestCancel(BindingHandle) )
  {
    RtlAcquireResourceShared(&stru_18005E448, 1u);
    if ( dword_18005E440 )
    {
      Sequence = RequestNextSequence(a3, a4);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_ba4cc97350ca3b6f3c632e36d119eafc_Traceguids);
      }
      Sequence = 5;
    }
    RtlReleaseResource(&stru_18005E448);
    *a5 = Sequence;
    if ( Sequence )
      return RpcAsyncAbortCall(pAsync, Sequence);
    else
      return RpcAsyncCompleteCall(pAsync, 0);
  }
  else
  {
    result = RpcAsyncAbortCall(pAsync, 0x71Au);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
        return WPP_SF_d(
                 *((_QWORD *)WPP_GLOBAL_Control + 2),
                 13,
                 WPP_ba4cc97350ca3b6f3c632e36d119eafc_Traceguids,
                 result);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180022580  mov     [rsp+arg_0], rbx
0x180022585  mov     [rsp+arg_8], rsi
0x18002258a  push    rdi
0x18002258b  sub     rsp, 20h
0x18002258f  mov     rdi, rcx
0x180022592  mov     rbx, r9
0x180022595  mov     rcx, rdx; BindingHandle
0x180022598  mov     rsi, r8
0x18002259b  call    cs:__imp_RpcServerTestCancel
0x1800225a1  test    eax, eax
0x1800225a3  jnz     short loc_1800225FE
0x1800225a5  mov     edx, 71Ah; ExceptionCode
0x1800225aa  mov     rcx, rdi; pAsync
0x1800225ad  call    cs:__imp_RpcAsyncAbortCall
0x1800225b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800225ba  lea     rdx, WPP_GLOBAL_Control
0x1800225c1  cmp     rcx, rdx
0x1800225c4  jz      loc_18002268E
0x1800225ca  test    dword ptr [rcx+1Ch], 400h
0x1800225d1  jz      loc_18002268E
0x1800225d7  cmp     byte ptr [rcx+19h], 1
0x1800225db  jb      loc_18002268E
0x1800225e1  mov     rcx, [rcx+10h]
0x1800225e5  lea     r8, WPP_ba4cc97350ca3b6f3c632e36d119eafc_Traceguids
0x1800225ec  mov     edx, 0Dh
0x1800225f1  mov     r9d, eax
0x1800225f4  call    WPP_SF_d
0x1800225f9  jmp     loc_18002268E
0x1800225fe  mov     dl, 1; Wait
0x180022600  lea     rcx, stru_18005E448; Resource
0x180022607  call    cs:__imp_RtlAcquireResourceShared
0x18002260d  cmp     cs:dword_18005E440, 0
0x180022614  jnz     short loc_180022654
0x180022616  mov     rcx, cs:WPP_GLOBAL_Control
0x18002261d  lea     rdx, WPP_GLOBAL_Control
0x180022624  cmp     rcx, rdx
0x180022627  jz      short loc_18002264D
0x180022629  test    dword ptr [rcx+1Ch], 400h
0x180022630  jz      short loc_18002264D
0x180022632  cmp     byte ptr [rcx+19h], 1
0x180022636  jb      short loc_18002264D
0x180022638  mov     rcx, [rcx+10h]
0x18002263c  lea     r8, WPP_ba4cc97350ca3b6f3c632e36d119eafc_Traceguids
0x180022643  mov     edx, 0Eh
0x180022648  call    WPP_SF_
0x18002264d  mov     ebx, 5
0x180022652  jmp     short loc_180022661
0x180022654  mov     rdx, rbx
0x180022657  mov     rcx, rsi
0x18002265a  call    RequestNextSequence
0x18002265f  mov     ebx, eax
0x180022661  lea     rcx, stru_18005E448; Resource
0x180022668  call    cs:__imp_RtlReleaseResource
0x18002266e  mov     rcx, [rsp+28h+arg_20]
0x180022673  mov     [rcx], ebx
0x180022675  mov     rcx, rdi; pAsync
0x180022678  test    ebx, ebx
0x18002267a  jnz     short loc_180022686
0x18002267c  xor     edx, edx; Reply
0x18002267e  call    cs:__imp_RpcAsyncCompleteCall
0x180022684  jmp     short loc_18002268E
0x180022686  mov     edx, ebx; ExceptionCode
0x180022688  call    cs:__imp_RpcAsyncAbortCall
0x18002268e  mov     rbx, [rsp+28h+arg_0]
0x180022693  mov     rsi, [rsp+28h+arg_8]
0x180022698  add     rsp, 20h
0x18002269c  pop     rdi
0x18002269d  retn
```
