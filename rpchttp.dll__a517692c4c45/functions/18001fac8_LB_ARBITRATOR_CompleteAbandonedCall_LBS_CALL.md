# LB_ARBITRATOR::CompleteAbandonedCall(LBS_CALL *)

- ea: `0x18001fac8`
- end: `0x18001fbd4`
- name: `?CompleteAbandonedCall@LB_ARBITRATOR@@AEAAHPEAVLBS_CALL@@@Z`
- size: `268`
- prototype: `int(LB_ARBITRATOR *__hidden this, struct LBS_CALL *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180023d58`

## callees

- `0x18001f9f4`
- `0x18001fac8`
- `0x1800214a4`

## import_xrefs

- `RPCRT4!I_RpcFree` at `0x18001fb1f`
- `RPCRT4!I_RpcFree` at `0x18001fb1f`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001fb03`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001fb70`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001fb03`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001fb70`
- `RPCRT4!RpcSsDestroyClientContext` at `0x18001fb3f`
- `RPCRT4!RpcSsDestroyClientContext` at `0x18001fb98`
- `RPCRT4!RpcSsDestroyClientContext` at `0x18001fbac`
- `RPCRT4!RpcSsDestroyClientContext` at `0x18001fb3f`
- `RPCRT4!RpcSsDestroyClientContext` at `0x18001fb98`
- `RPCRT4!RpcSsDestroyClientContext` at `0x18001fbac`

## pseudocode

```c
__int64 __fastcall LB_ARBITRATOR::CompleteAbandonedCall(LB_ARBITRATOR *this, struct LBS_CALL *a2)
{
  unsigned int v2; // edi
  bool v3; // zf
  struct _RPC_ASYNC_STATE *v4; // rcx
  unsigned int v6; // esi
  void *v7; // rcx
  __int64 v8; // r8
  __int64 v9; // rdx
  unsigned int v11; // [rsp+30h] [rbp+8h] BYREF
  int v12; // [rsp+34h] [rbp+Ch]

  v12 = HIDWORD(this);
  v2 = 0;
  v11 = 0;
  v3 = *((_DWORD *)a2 + 37) == 1;
  v4 = (struct _RPC_ASYNC_STATE *)((char *)a2 + 8);
  *((_DWORD *)a2 + 38) = 2;
  if ( v3 )
  {
    v6 = RpcAsyncCompleteCall(v4, &v11);
    if ( !v6 )
    {
      v7 = (void *)*((_QWORD *)a2 + 16);
      if ( v7 )
      {
        I_RpcFree(v7);
        *((_QWORD *)a2 + 16) = 0;
      }
      if ( !*((_QWORD *)a2 + 17) )
      {
        v8 = 0;
        v9 = 5;
LABEL_19:
        LBS_CALL::ChangeCallState(a2, v9, v8);
        return v2;
      }
      if ( v11 > 1 )
      {
        RpcSsDestroyClientContext((void **)a2 + 17);
        v8 = 1818;
LABEL_18:
        v9 = 6;
        goto LABEL_19;
      }
      goto LABEL_8;
    }
LABEL_15:
    if ( *((_QWORD *)a2 + 17) )
      RpcSsDestroyClientContext((void **)a2 + 17);
    v8 = v6;
    goto LABEL_18;
  }
  v6 = RpcAsyncCompleteCall(v4, 0);
  if ( v6 )
    goto LABEL_15;
  if ( ((*((_DWORD *)a2 + 37) - 3) & 0xFFFFFFFD) != 0 )
  {
LABEL_8:
    LBS_CALL::SubmitClose(a2);
    if ( *((_DWORD *)a2 + 38) == 1 )
      return 1;
    return v2;
  }
  if ( *((_QWORD *)a2 + 17) )
    RpcSsDestroyClientContext((void **)a2 + 17);
  return v2;
}

```

## disassembly

```asm
0x18001fac8  mov     rax, rsp
0x18001facb  mov     [rax+10h], rbx
0x18001facf  mov     [rax+18h], rsi
0x18001fad3  mov     [rax+8], rcx
0x18001fad7  push    rdi
0x18001fad8  sub     rsp, 20h
0x18001fadc  xor     edi, edi
0x18001fade  mov     dword ptr [rax+8], 0
0x18001fae5  cmp     dword ptr [rdx+94h], 1
0x18001faec  lea     rcx, [rdx+8]; pAsync
0x18001faf0  mov     rbx, rdx
0x18001faf3  mov     dword ptr [rdx+98h], 2
0x18001fafd  jnz     short loc_18001FB6E
0x18001faff  lea     rdx, [rax+8]; Reply
0x18001fb03  call    cs:__imp_RpcAsyncCompleteCall
0x18001fb09  mov     esi, eax
0x18001fb0b  test    eax, eax
0x18001fb0d  jnz     loc_18001FBA0
0x18001fb13  mov     rcx, [rbx+80h]; Object
0x18001fb1a  test    rcx, rcx
0x18001fb1d  jz      short loc_18001FB2C
0x18001fb1f  call    cs:__imp_I_RpcFree
0x18001fb25  mov     [rbx+80h], rdi
0x18001fb2c  lea     rcx, [rbx+88h]; ContextHandle
0x18001fb33  cmp     [rcx], rdi
0x18001fb36  jz      short loc_18001FB65
0x18001fb38  cmp     [rsp+28h+arg_0], 1
0x18001fb3d  jbe     short loc_18001FB4D
0x18001fb3f  call    cs:__imp_RpcSsDestroyClientContext
0x18001fb45  mov     r8d, 71Ah
0x18001fb4b  jmp     short loc_18001FBB5
0x18001fb4d  mov     rcx, rbx; this
0x18001fb50  call    ?SubmitClose@LBS_CALL@@QEAAXXZ; LBS_CALL::SubmitClose(void)
0x18001fb55  cmp     dword ptr [rbx+98h], 1
0x18001fb5c  jnz     short loc_18001FBC2
0x18001fb5e  mov     edi, 1
0x18001fb63  jmp     short loc_18001FBC2
0x18001fb65  xor     r8d, r8d
0x18001fb68  lea     edx, [r8+5]
0x18001fb6c  jmp     short loc_18001FBBA
0x18001fb6e  xor     edx, edx; Reply
0x18001fb70  call    cs:__imp_RpcAsyncCompleteCall
0x18001fb76  mov     esi, eax
0x18001fb78  test    eax, eax
0x18001fb7a  jnz     short loc_18001FBA0
0x18001fb7c  mov     eax, [rbx+94h]
0x18001fb82  sub     eax, 3
0x18001fb85  test    eax, 0FFFFFFFDh
0x18001fb8a  jnz     short loc_18001FB4D
0x18001fb8c  lea     rcx, [rbx+88h]; ContextHandle
0x18001fb93  cmp     [rcx], rdi
0x18001fb96  jz      short loc_18001FBC2
0x18001fb98  call    cs:__imp_RpcSsDestroyClientContext
0x18001fb9e  jmp     short loc_18001FBC2
0x18001fba0  lea     rcx, [rbx+88h]; ContextHandle
0x18001fba7  cmp     [rcx], rdi
0x18001fbaa  jz      short loc_18001FBB2
0x18001fbac  call    cs:__imp_RpcSsDestroyClientContext
0x18001fbb2  mov     r8d, esi
0x18001fbb5  mov     edx, 6
0x18001fbba  mov     rcx, rbx
0x18001fbbd  call    ?ChangeCallState@LBS_CALL@@QEAAXW4_CallStates@@J@Z; LBS_CALL::ChangeCallState(_CallStates,long)
0x18001fbc2  mov     rbx, [rsp+28h+arg_8]
0x18001fbc7  mov     eax, edi
0x18001fbc9  mov     rsi, [rsp+28h+arg_10]
0x18001fbce  add     rsp, 20h
0x18001fbd2  pop     rdi
0x18001fbd3  retn
```
