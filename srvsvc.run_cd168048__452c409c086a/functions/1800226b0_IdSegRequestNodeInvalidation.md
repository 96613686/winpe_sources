# IdSegRequestNodeInvalidation

- ea: `0x1800226b0`
- end: `0x180022826`
- name: `IdSegRequestNodeInvalidation`
- size: `374`
- prototype: `__int64 __usercall@<rax>(PRPC_ASYNC_STATE pAsync@<rcx>, RPC_BINDING_HANDLE BindingHandle@<rdx>, void *Reply)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180020dc0`
- `0x180020de8`
- `0x1800226b0`
- `0x180022a4c`

## import_xrefs

- `ntdll!RtlAcquireResourceShared` at `0x180022768`
- `ntdll!RtlAcquireResourceShared` at `0x180022768`
- `ntdll!RtlReleaseResource` at `0x1800227cd`
- `ntdll!RtlReleaseResource` at `0x1800227cd`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180022813`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180022813`
- `RPCRT4!RpcAsyncAbortCall` at `0x180022718`
- `RPCRT4!RpcAsyncAbortCall` at `0x180022718`
- `RPCRT4!RpcServerTestCancel` at `0x180022706`
- `RPCRT4!RpcServerTestCancel` at `0x180022706`

## pseudocode

```c
unsigned int __fastcall IdSegRequestNodeInvalidation(
        PRPC_ASYNC_STATE pAsync,
        RPC_BINDING_HANDLE BindingHandle,
        _DWORD *a3,
        int a4,
        unsigned int *Reply)
{
  unsigned int result; // eax
  unsigned int v10; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_ba4cc97350ca3b6f3c632e36d119eafc_Traceguids);
  }
  if ( RpcServerTestCancel(BindingHandle) )
  {
    RtlAcquireResourceShared(&stru_18005E448, 1u);
    if ( dword_18005E440 )
    {
      v10 = RequestNodeInvalidation(a3[2], *a3, (_DWORD)a3, a4, (__int64)a3, a4);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_ba4cc97350ca3b6f3c632e36d119eafc_Traceguids);
      }
      v10 = 5;
    }
    RtlReleaseResource(&stru_18005E448);
    *Reply = v10;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_ba4cc97350ca3b6f3c632e36d119eafc_Traceguids, v10);
    }
    return RpcAsyncCompleteCall(pAsync, Reply);
  }
  else
  {
    result = RpcAsyncAbortCall(pAsync, 0x71Au);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
        return WPP_SF_d(
                 *((_QWORD *)WPP_GLOBAL_Control + 2),
                 16,
                 WPP_ba4cc97350ca3b6f3c632e36d119eafc_Traceguids,
                 result);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800226b0  push    rbx
0x1800226b2  push    rbp
0x1800226b3  push    rsi
0x1800226b4  push    rdi
0x1800226b5  push    r12
0x1800226b7  push    r14
0x1800226b9  sub     rsp, 38h
0x1800226bd  mov     ebp, r9d
0x1800226c0  mov     rbx, r8
0x1800226c3  mov     rdi, rdx
0x1800226c6  mov     rsi, rcx
0x1800226c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800226d0  lea     r12, WPP_GLOBAL_Control
0x1800226d7  mov     r14d, 400h
0x1800226dd  cmp     rcx, r12
0x1800226e0  jz      short loc_180022703
0x1800226e2  test    [rcx+1Ch], r14d
0x1800226e6  jz      short loc_180022703
0x1800226e8  cmp     byte ptr [rcx+19h], 4
0x1800226ec  jb      short loc_180022703
0x1800226ee  mov     rcx, [rcx+10h]
0x1800226f2  lea     r8, WPP_ba4cc97350ca3b6f3c632e36d119eafc_Traceguids
0x1800226f9  mov     edx, 0Fh
0x1800226fe  call    WPP_SF_
0x180022703  mov     rcx, rdi; BindingHandle
0x180022706  call    cs:__imp_RpcServerTestCancel
0x18002270c  test    eax, eax
0x18002270e  jnz     short loc_18002275F
0x180022710  mov     edx, 71Ah; ExceptionCode
0x180022715  mov     rcx, rsi; pAsync
0x180022718  call    cs:__imp_RpcAsyncAbortCall
0x18002271e  mov     rcx, cs:WPP_GLOBAL_Control
0x180022725  cmp     rcx, r12
0x180022728  jz      loc_180022819
0x18002272e  test    [rcx+1Ch], r14d
0x180022732  jz      loc_180022819
0x180022738  cmp     byte ptr [rcx+19h], 1
0x18002273c  jb      loc_180022819
0x180022742  mov     rcx, [rcx+10h]
0x180022746  lea     r8, WPP_ba4cc97350ca3b6f3c632e36d119eafc_Traceguids
0x18002274d  mov     edx, 10h
0x180022752  mov     r9d, eax
0x180022755  call    WPP_SF_d
0x18002275a  jmp     loc_180022819
0x18002275f  mov     dl, 1; Wait
0x180022761  lea     rcx, stru_18005E448; Resource
0x180022768  call    cs:__imp_RtlAcquireResourceShared
0x18002276e  cmp     cs:dword_18005E440, 0
0x180022775  jnz     short loc_1800227AB
0x180022777  mov     rcx, cs:WPP_GLOBAL_Control
0x18002277e  cmp     rcx, r12
0x180022781  jz      short loc_1800227A4
0x180022783  test    [rcx+1Ch], r14d
0x180022787  jz      short loc_1800227A4
0x180022789  cmp     byte ptr [rcx+19h], 1
0x18002278d  jb      short loc_1800227A4
0x18002278f  mov     rcx, [rcx+10h]
0x180022793  lea     r8, WPP_ba4cc97350ca3b6f3c632e36d119eafc_Traceguids
0x18002279a  mov     edx, 11h
0x18002279f  call    WPP_SF_
0x1800227a4  mov     ebx, 5
0x1800227a9  jmp     short loc_1800227C6
0x1800227ab  mov     edx, [rbx]
0x1800227ad  mov     r9d, ebp
0x1800227b0  mov     ecx, [rbx+8]
0x1800227b3  mov     r8, rbx
0x1800227b6  mov     [rsp+68h+var_40], ebp
0x1800227ba  mov     [rsp+68h+var_48], rbx
0x1800227bf  call    RequestNodeInvalidation
0x1800227c4  mov     ebx, eax
0x1800227c6  lea     rcx, stru_18005E448; Resource
0x1800227cd  call    cs:__imp_RtlReleaseResource
0x1800227d3  mov     rdi, [rsp+68h+Reply]
0x1800227db  mov     [rdi], ebx
0x1800227dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800227e4  cmp     rcx, r12
0x1800227e7  jz      short loc_18002280D
0x1800227e9  test    [rcx+1Ch], r14d
0x1800227ed  jz      short loc_18002280D
0x1800227ef  cmp     byte ptr [rcx+19h], 4
0x1800227f3  jb      short loc_18002280D
0x1800227f5  mov     rcx, [rcx+10h]
0x1800227f9  lea     r8, WPP_ba4cc97350ca3b6f3c632e36d119eafc_Traceguids
0x180022800  mov     edx, 12h
0x180022805  mov     r9d, ebx
0x180022808  call    WPP_SF_d
0x18002280d  mov     rdx, rdi; Reply
0x180022810  mov     rcx, rsi; pAsync
0x180022813  call    cs:__imp_RpcAsyncCompleteCall
0x180022819  add     rsp, 38h
0x18002281d  pop     r14
0x18002281f  pop     r12
0x180022821  pop     rdi
0x180022822  pop     rsi
0x180022823  pop     rbp
0x180022824  pop     rbx
0x180022825  retn
```
