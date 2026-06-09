# RPC_THREAD_POOL::CreateAlpc(void *,void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_ALPC *,void *),void *,RPC_THREAD_POOL_ALPC * *)

- ea: `0x18006e2dc`
- end: `0x18006e396`
- name: `?CreateAlpc@RPC_THREAD_POOL@@SAJPEAXP6AXPEAU_TP_CALLBACK_INSTANCE@@0PEAU_TP_ALPC@@0@Z0PEAPEAVRPC_THREAD_POOL_ALPC@@@Z`
- size: `186`
- prototype: `__int64 __fastcall(void *, void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_ALPC *, void *), void *, struct RPC_THREAD_POOL_ALPC **)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006e1e4`
- `0x18006e650`

## callees

- `0x180023020`
- `0x18006e2dc`
- `0x18006e4c0`
- `0x180088d9c`

## import_xrefs

- `ntdll!TpAllocAlpcCompletionEx` at `0x18006e33e`
- `ntdll!TpAllocAlpcCompletionEx` at `0x18006e33e`
- `ntdll!RtlNtStatusToDosError` at `0x18006e34e`
- `ntdll!RtlNtStatusToDosError` at `0x18006e34e`

## pseudocode

```c
__int64 __fastcall RPC_THREAD_POOL::CreateAlpc(
        void *a1,
        void (*a2)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_ALPC *, void *),
        void *a3,
        struct RPC_THREAD_POOL_ALPC **a4)
{
  unsigned int v7; // ebx
  struct RPC_THREAD_POOL_ALPC *v8; // rax
  NTSTATUS v9; // ebx
  unsigned int v10; // edx
  RPC_THREAD_POOL_ALPC *v11; // rcx
  __int64 v13; // [rsp+68h] [rbp+10h] BYREF

  v13 = 0;
  v7 = RPC_THREAD_POOL::InitializeCallbackEnvironmentIfNecessary();
  if ( !v7 )
  {
    v8 = (struct RPC_THREAD_POOL_ALPC *)AllocWrapper(0x10u);
    if ( v8 )
    {
      *(_QWORD *)v8 = 0;
      *((_BYTE *)v8 + 8) = v7;
      *a4 = v8;
      v9 = TpAllocAlpcCompletionEx(&v13, a1, LrpcIoComplete, a3, RPC_THREAD_POOL::CallbackEnvironment);
      RtlNtStatusToDosError(v9);
      v11 = *a4;
      if ( v9 >= 0 )
      {
        v7 = 0;
        *(_QWORD *)v11 = v13;
        return v7;
      }
      v7 = 14;
      if ( v11 )
        RPC_THREAD_POOL_ALPC::`scalar deleting destructor'(v11, v10);
    }
    else
    {
      v7 = 14;
    }
    *a4 = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x18006e2dc  mov     [rsp+arg_8], rdx
0x18006e2e1  push    rbx
0x18006e2e2  push    rbp
0x18006e2e3  push    rsi
0x18006e2e4  push    rdi
0x18006e2e5  sub     rsp, 38h
0x18006e2e9  mov     rdi, r9
0x18006e2ec  mov     [rsp+58h+arg_8], 0
0x18006e2f5  mov     rsi, r8
0x18006e2f8  mov     rbp, rcx
0x18006e2fb  call    ?InitializeCallbackEnvironmentIfNecessary@RPC_THREAD_POOL@@CAJXZ; RPC_THREAD_POOL::InitializeCallbackEnvironmentIfNecessary(void)
0x18006e300  mov     ebx, eax
0x18006e302  test    eax, eax
0x18006e304  jnz     short loc_18006E36B
0x18006e306  lea     ecx, [rax+10h]; dwBytes
0x18006e309  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x18006e30e  test    rax, rax
0x18006e311  jz      short loc_18006E377
0x18006e313  mov     qword ptr [rax], 0
0x18006e31a  lea     r8, ?LrpcIoComplete@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_ALPC@@1@Z; LrpcIoComplete(_TP_CALLBACK_INSTANCE *,void *,_TP_ALPC *,void *)
0x18006e321  mov     [rax+8], bl
0x18006e324  lea     rcx, [rsp+58h+arg_8]
0x18006e329  mov     [rdi], rax
0x18006e32c  mov     r9, rsi
0x18006e32f  mov     rax, cs:?CallbackEnvironment@RPC_THREAD_POOL@@0REAU_TP_CALLBACK_ENVIRON_V3@@EA; _TP_CALLBACK_ENVIRON_V3 * RPC_THREAD_POOL::CallbackEnvironment
0x18006e336  mov     rdx, rbp
0x18006e339  mov     [rsp+58h+var_38], rax
0x18006e33e  call    cs:__imp_TpAllocAlpcCompletionEx
0x18006e345  nop     dword ptr [rax+rax+00h]
0x18006e34a  mov     ecx, eax; Status
0x18006e34c  mov     ebx, eax
0x18006e34e  call    cs:__imp_RtlNtStatusToDosError
0x18006e355  nop     dword ptr [rax+rax+00h]
0x18006e35a  mov     rcx, [rdi]; this
0x18006e35d  test    ebx, ebx
0x18006e35f  js      short loc_18006E385
0x18006e361  mov     rax, [rsp+58h+arg_8]
0x18006e366  xor     ebx, ebx
0x18006e368  mov     [rcx], rax
0x18006e36b  mov     eax, ebx
0x18006e36d  add     rsp, 38h
0x18006e371  pop     rdi
0x18006e372  pop     rsi
0x18006e373  pop     rbp
0x18006e374  pop     rbx
0x18006e375  retn
0x18006e377  mov     ebx, 0Eh
0x18006e37c  mov     qword ptr [rdi], 0
0x18006e383  jmp     short loc_18006E36B
0x18006e385  mov     ebx, 0Eh
0x18006e38a  test    rcx, rcx
0x18006e38d  jz      short loc_18006E37C
0x18006e38f  call    ??_GRPC_THREAD_POOL_ALPC@@QEAAPEAXI@Z; RPC_THREAD_POOL_ALPC::`scalar deleting destructor'(uint)
0x18006e394  jmp     short loc_18006E37C
```
