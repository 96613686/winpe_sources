# LRPC_CCALL::HandleCallbackSequence(_RPC_MESSAGE *)

- ea: `0x18006f860`
- end: `0x18006fc0f`
- name: `?HandleCallbackSequence@LRPC_CCALL@@EEAAJPEAU_RPC_MESSAGE@@@Z`
- size: `943`
- prototype: `__int64 __fastcall(LRPC_BINDING_HANDLE **this, struct _RPC_MESSAGE *)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, loader_planting, installer_update`

## callees

- `0x18000fd70`
- `0x180016600`
- `0x180026500`
- `0x180027e20`
- `0x1800283b0`
- `0x1800295d8`
- `0x18006eaec`
- `0x18006f860`
- `0x1800703c0`
- `0x180070458`
- `0x180070c74`
- `0x180070dbc`
- `0x1800711f0`
- `0x18009fb90`
- `0x1800a2440`
- `0x1800d7010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18006fad0`
- `ntdll!RtlLeaveCriticalSection` at `0x18006fb92`
- `ntdll!RtlLeaveCriticalSection` at `0x18006fad0`
- `ntdll!RtlLeaveCriticalSection` at `0x18006fb92`
- `ntdll!RtlEnterCriticalSection` at `0x18006fab2`
- `ntdll!RtlEnterCriticalSection` at `0x18006fb77`
- `ntdll!RtlEnterCriticalSection` at `0x18006fab2`
- `ntdll!RtlEnterCriticalSection` at `0x18006fb77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006f8c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006f8c1`

## pseudocode

```c
__int64 __fastcall LRPC_CCALL::HandleCallbackSequence(LRPC_BINDING_HANDLE **this, struct _RPC_MESSAGE *a2)
{
  struct RPCP_ALPC_MESSAGE_ATTRIBUTES *v2; // r15
  unsigned int v5; // r13d
  int v6; // r12d
  unsigned int v7; // edi
  LRPC_BINDING_HANDLE **v8; // r14
  LRPC_BINDING_HANDLE *v9; // rbx
  unsigned int HeaderSize; // eax
  __int64 v11; // r10
  bool v12; // zf
  LRPC_CASSOCIATION *v13; // rcx
  struct _PORT_MESSAGE *v14; // r8
  int v15; // eax
  struct _RPC_SYNTAX_IDENTIFIER *TransferSyntax; // r8
  LRPC_BINDING_HANDLE *v17; // rcx
  PRTL_CRITICAL_SECTION *v19; // rbx
  PRTL_CRITICAL_SECTION *v20; // rbx
  unsigned int v21; // [rsp+28h] [rbp-90h]
  _DWORD v22[26]; // [rsp+50h] [rbp-68h] BYREF
  unsigned __int64 v23; // [rsp+C0h] [rbp+8h] BYREF

  v2 = (struct RPCP_ALPC_MESSAGE_ATTRIBUTES *)(this + 37);
  v5 = -1;
  v6 = -1;
  if ( LrpcAsyncInitialized || (v7 = InitializeAsyncLrpc()) == 0 )
  {
    v8 = this + 34;
    v7 = LRPC_BINDING_HANDLE::EnableCallbackIfNecessary(this[34]);
    if ( !v7 )
    {
      v7 = LRPC_CCALL::PrepareForCallbackIfNecessary((LRPC_CCALL *)this);
      if ( !v7 )
      {
        v19 = (PRTL_CRITICAL_SECTION *)*((_QWORD *)this[35] + 70);
        RtlEnterCriticalSection(v19[6]);
        v5 = SIMPLE_DICT::Insert((SIMPLE_DICT *)v19, this);
        RtlLeaveCriticalSection(v19[6]);
        if ( v5 == -1 )
        {
          v7 = 14;
        }
        else
        {
          v7 = LRPC_BINDING_HANDLE::PrepareForCallbackIfNecessary(*v8);
          if ( !v7 )
          {
            v6 = LRPC_BINDING_HANDLE::AddRecursiveCall(*v8, (struct LRPC_CCALL *)this);
            if ( v6 == -1 )
              v7 = 14;
          }
        }
      }
    }
  }
  else
  {
    v8 = this + 34;
  }
  v9 = this[63];
  if ( v7 )
  {
    *((_QWORD *)v9 + 5) = 8;
  }
  else
  {
    *((_QWORD *)v9 + 5) = 7;
    *((_DWORD *)this[74] + 50) = GetCurrentThreadId();
  }
  RpcpAlpcInitializeMessageAttribute(0xA0000000, v2, 0x40u, &v23);
  if ( *((_QWORD *)v9 + 5) == 7 )
    *(_QWORD *)((char *)v2 + (unsigned int)RpcpAlpcpGetHeaderSize(*(_DWORD *)v2 & 0xC0000000) + 8) = this;
  HeaderSize = RpcpAlpcpGetHeaderSize(0);
  *(_OWORD *)((char *)v2 + HeaderSize) = *(_OWORD *)v11;
  *(_QWORD *)((char *)v2 + HeaderSize + 16) = *(_QWORD *)(v11 + 16);
  *((_DWORD *)v2 + 1) = -1610612736;
  *(_OWORD *)v9 = 0;
  *((_OWORD *)v9 + 1) = 0;
  *((_QWORD *)v9 + 4) = 0;
  v12 = *((_QWORD *)v9 + 5) == 7;
  *(_DWORD *)v9 = 3670032;
  *((_DWORD *)v9 + 12) = 0;
  *((_DWORD *)v9 + 13) = *((_DWORD *)this + 73);
  v13 = this[35];
  v14 = (struct _PORT_MESSAGE *)this[63];
  if ( v12 )
  {
    v15 = LRPC_CASSOCIATION::AlpcSendWaitReceivePort(v13, 0, v14, v2, 0, 0, 0);
  }
  else
  {
    v23 = 4096;
    v15 = LRPC_CASSOCIATION::AlpcSendWaitReceivePort(v13, 0x20000u, v14, v2, v14, &v23, v2);
  }
  switch ( v15 )
  {
    case -1073741801:
      goto LABEL_38;
    case -1073741769:
      goto LABEL_37;
    case -1073741756:
    case -1073741670:
LABEL_38:
      v7 = 14;
      goto LABEL_39;
    case -1073740031:
      v7 = 1818;
      goto LABEL_39;
  }
  if ( v15 )
  {
LABEL_37:
    v7 = 1726;
    goto LABEL_39;
  }
  if ( v7 )
  {
LABEL_39:
    v22[2] = v15;
    v22[0] = 3;
    RpcpErrorAddRecord(2u, v7, 0x50Au, 1, (struct tagParam *)v22);
    (*(void (__fastcall **)(LRPC_BINDING_HANDLE *, _QWORD, LRPC_BINDING_HANDLE **))(*(_QWORD *)*v8 + 480LL))(
      *v8,
      v7,
      this);
    goto LABEL_21;
  }
  ++*((_DWORD *)this[74] + 2);
  TransferSyntax = a2->TransferSyntax;
  a2->DataRepresentation = 16;
  v7 = LRPC_CALLBACK::SendReceiveLoop(
         this[74],
         1,
         TransferSyntax,
         *((struct RPC_DISPATCH_TABLE **)this[79] + 6),
         a2,
         v21,
         0,
         0,
         0);
  if ( !v7 )
  {
    v17 = this[63];
    if ( v17 )
      I_RpcBCacheFree(v17);
    this[63] = (LRPC_BINDING_HANDLE *)a2->Buffer;
    *((_DWORD *)this + 132) = a2->BufferLength;
  }
LABEL_21:
  if ( v5 != -1 )
  {
    v20 = (PRTL_CRITICAL_SECTION *)*((_QWORD *)this[35] + 70);
    RtlEnterCriticalSection(v20[6]);
    SIMPLE_DICT::Delete((SIMPLE_DICT *)v20, v5);
    RtlLeaveCriticalSection(v20[6]);
  }
  if ( v6 != -1 )
    LRPC_BINDING_HANDLE::RemoveRecursiveCall(*v8, v6);
  return v7;
}

```

## disassembly

```asm
0x18006f860  push    rbx
0x18006f862  push    rbp
0x18006f863  push    rsi
0x18006f864  push    rdi
0x18006f865  push    r12
0x18006f867  push    r13
0x18006f869  push    r14
0x18006f86b  push    r15
0x18006f86d  sub     rsp, 78h
0x18006f871  or      eax, 0FFFFFFFFh
0x18006f874  lea     r15, [rcx+128h]
0x18006f87b  cmp     cs:?LrpcAsyncInitialized@@3HA, 0; int LrpcAsyncInitialized
0x18006f882  mov     rbp, rdx
0x18006f885  mov     rsi, rcx
0x18006f888  mov     r13d, eax
0x18006f88b  mov     r12d, eax
0x18006f88e  jnz     loc_18006FA75
0x18006f894  call    ?InitializeAsyncLrpc@@YAJXZ; InitializeAsyncLrpc(void)
0x18006f899  mov     edi, eax
0x18006f89b  test    eax, eax
0x18006f89d  jz      loc_18006FA75
0x18006f8a3  lea     r14, [rsi+110h]
0x18006f8aa  mov     rbx, [rsi+1F8h]
0x18006f8b1  test    edi, edi
0x18006f8b3  jnz     loc_18006FB58
0x18006f8b9  mov     qword ptr [rbx+28h], 7
0x18006f8c1  call    cs:__imp_GetCurrentThreadId
0x18006f8c8  nop     dword ptr [rax+rax+00h]
0x18006f8cd  mov     rcx, [rsi+250h]
0x18006f8d4  mov     [rcx+0C8h], eax
0x18006f8da  lea     r9, [rsp+0B8h+arg_0]; unsigned __int64 *
0x18006f8e2  mov     r8d, 40h ; '@'; unsigned __int64
0x18006f8e8  mov     rdx, r15; struct RPCP_ALPC_MESSAGE_ATTRIBUTES *
0x18006f8eb  mov     ecx, 0A0000000h; unsigned int
0x18006f8f0  call    ?RpcpAlpcInitializeMessageAttribute@@YAJKPEAVRPCP_ALPC_MESSAGE_ATTRIBUTES@@_KPEA_K@Z; RpcpAlpcInitializeMessageAttribute(ulong,RPCP_ALPC_MESSAGE_ATTRIBUTES *,unsigned __int64,unsigned __int64 *)
0x18006f8f5  cmp     qword ptr [rbx+28h], 7
0x18006f8fa  jnz     short loc_18006F912
0x18006f8fc  mov     ecx, [r15]
0x18006f8ff  and     ecx, 0C0000000h; unsigned int
0x18006f905  call    ?RpcpAlpcpGetHeaderSize@@YAKK@Z; RpcpAlpcpGetHeaderSize(ulong)
0x18006f90a  mov     r9d, eax
0x18006f90d  mov     [r9+r15+8], rsi
0x18006f912  mov     rax, [r14]
0x18006f915  xor     ecx, ecx; unsigned int
0x18006f917  mov     r10, [rax+1B0h]
0x18006f91e  call    ?RpcpAlpcpGetHeaderSize@@YAKK@Z; RpcpAlpcpGetHeaderSize(ulong)
0x18006f923  movups  xmm0, xmmword ptr [r10]
0x18006f927  mov     r9d, eax
0x18006f92a  xor     eax, eax
0x18006f92c  movups  xmmword ptr [r9+r15], xmm0
0x18006f931  movsd   xmm1, qword ptr [r10+10h]
0x18006f937  xorps   xmm0, xmm0
0x18006f93a  movsd   qword ptr [r9+r15+10h], xmm1
0x18006f941  mov     r9, r15; struct _ALPC_MESSAGE_ATTRIBUTES *
0x18006f944  mov     dword ptr [r15+4], 0A0000000h
0x18006f94c  movups  xmmword ptr [rbx], xmm0
0x18006f94f  movups  xmmword ptr [rbx+10h], xmm0
0x18006f953  mov     [rbx+20h], rax
0x18006f957  cmp     qword ptr [rbx+28h], 7
0x18006f95c  mov     dword ptr [rbx], 380010h
0x18006f962  mov     [rbx+30h], eax
0x18006f965  mov     eax, [rsi+124h]
0x18006f96b  mov     [rbx+34h], eax
0x18006f96e  mov     rcx, [rsi+118h]; this
0x18006f975  mov     r8, [rsi+1F8h]; struct _PORT_MESSAGE *
0x18006f97c  jnz     loc_18006FB1A
0x18006f982  xor     ebx, ebx
0x18006f984  xor     edx, edx; unsigned int
0x18006f986  mov     [rsp+0B8h+var_88], rbx; struct _ALPC_MESSAGE_ATTRIBUTES *
0x18006f98b  mov     [rsp+0B8h+var_90], rbx; unsigned int
0x18006f990  mov     [rsp+0B8h+var_98], rbx; struct _PORT_MESSAGE *
0x18006f995  call    ?AlpcSendWaitReceivePort@LRPC_CASSOCIATION@@QEAAJKPEAU_PORT_MESSAGE@@PEAU_ALPC_MESSAGE_ATTRIBUTES@@0PEA_K1PEAT_LARGE_INTEGER@@@Z; LRPC_CASSOCIATION::AlpcSendWaitReceivePort(ulong,_PORT_MESSAGE *,_ALPC_MESSAGE_ATTRIBUTES *,_PORT_MESSAGE *,unsigned __int64 *,_ALPC_MESSAGE_ATTRIBUTES *,_LARGE_INTEGER *)
0x18006f99a  cmp     eax, 0C0000017h
0x18006f99f  jz      loc_18006FBB1
0x18006f9a5  cmp     eax, 0C0000037h
0x18006f9aa  jz      loc_18006FBAA
0x18006f9b0  cmp     eax, 0C0000044h
0x18006f9b5  jz      loc_18006FBB1
0x18006f9bb  cmp     eax, 0C000009Ah
0x18006f9c0  jz      loc_18006FBB1
0x18006f9c6  cmp     eax, 0C0000701h
0x18006f9cb  jz      loc_18006FBA3
0x18006f9d1  test    eax, eax
0x18006f9d3  jnz     loc_18006FBAA
0x18006f9d9  test    edi, edi
0x18006f9db  jnz     loc_18006FBB6
0x18006f9e1  mov     rax, [rsi+250h]
0x18006f9e8  lea     edx, [rdi+1]; int
0x18006f9eb  mov     [rsp+0B8h+var_78], rbx; struct LRPC_SBINDING *
0x18006f9f0  mov     [rsp+0B8h+var_80], rbx; struct RPC_UUID *
0x18006f9f5  mov     dword ptr [rsp+0B8h+var_88], ebx; int
0x18006f9f9  inc     dword ptr [rax+8]
0x18006f9fc  mov     r8, [rbp+20h]; struct _RPC_SYNTAX_IDENTIFIER *
0x18006fa00  mov     dword ptr [rbp+8], 10h
0x18006fa07  mov     r9, [rsi+278h]
0x18006fa0e  mov     rcx, [rsi+250h]; this
0x18006fa15  mov     [rsp+0B8h+var_98], rbp; struct _RPC_MESSAGE *
0x18006fa1a  mov     r9, [r9+30h]; struct RPC_DISPATCH_TABLE *
0x18006fa1e  call    ?SendReceiveLoop@LRPC_CALLBACK@@QEAAJHPEAU_RPC_SYNTAX_IDENTIFIER@@PEAURPC_DISPATCH_TABLE@@PEAU_RPC_MESSAGE@@KHPEAVRPC_UUID@@PEAVLRPC_SBINDING@@@Z; LRPC_CALLBACK::SendReceiveLoop(int,_RPC_SYNTAX_IDENTIFIER *,RPC_DISPATCH_TABLE *,_RPC_MESSAGE *,ulong,int,RPC_UUID *,LRPC_SBINDING *)
0x18006fa23  mov     edi, eax
0x18006fa25  test    eax, eax
0x18006fa27  jnz     short loc_18006FA4D
0x18006fa29  mov     rcx, [rsi+1F8h]; void *
0x18006fa30  test    rcx, rcx
0x18006fa33  jnz     loc_18006FB10
0x18006fa39  mov     rcx, [rbp+10h]
0x18006fa3d  mov     [rsi+1F8h], rcx
0x18006fa44  mov     ecx, [rbp+18h]
0x18006fa47  mov     [rsi+210h], ecx
0x18006fa4d  cmp     r13d, 0FFFFFFFFh
0x18006fa51  jnz     loc_18006FB65
0x18006fa57  cmp     r12d, 0FFFFFFFFh
0x18006fa5b  jnz     loc_18006FBFF
0x18006fa61  mov     eax, edi
0x18006fa63  add     rsp, 78h
0x18006fa67  pop     r15
0x18006fa69  pop     r14
0x18006fa6b  pop     r13
0x18006fa6d  pop     r12
0x18006fa6f  pop     rdi
0x18006fa70  pop     rsi
0x18006fa71  pop     rbp
0x18006fa72  pop     rbx
0x18006fa73  retn
0x18006fa75  lea     r14, [rsi+110h]
0x18006fa7c  mov     rcx, [r14]; this
0x18006fa7f  call    ?EnableCallbackIfNecessary@LRPC_BINDING_HANDLE@@QEAAJXZ; LRPC_BINDING_HANDLE::EnableCallbackIfNecessary(void)
0x18006fa84  mov     edi, eax
0x18006fa86  test    eax, eax
0x18006fa88  jnz     loc_18006F8AA
0x18006fa8e  mov     rcx, rsi; this
0x18006fa91  call    ?PrepareForCallbackIfNecessary@LRPC_CCALL@@AEAAJXZ; LRPC_CCALL::PrepareForCallbackIfNecessary(void)
0x18006fa96  mov     edi, eax
0x18006fa98  test    eax, eax
0x18006fa9a  jnz     loc_18006F8AA
0x18006faa0  mov     rax, [rsi+118h]
0x18006faa7  mov     rbx, [rax+230h]
0x18006faae  mov     rcx, [rbx+30h]; CriticalSection
0x18006fab2  call    cs:__imp_RtlEnterCriticalSection
0x18006fab9  nop     dword ptr [rax+rax+00h]
0x18006fabe  mov     rdx, rsi; void *
0x18006fac1  mov     rcx, rbx; this
0x18006fac4  call    ?Insert@SIMPLE_DICT@@QEAAIPEAX@Z; SIMPLE_DICT::Insert(void *)
0x18006fac9  mov     rcx, [rbx+30h]; CriticalSection
0x18006facd  mov     r13d, eax
0x18006fad0  call    cs:__imp_RtlLeaveCriticalSection
0x18006fad7  nop     dword ptr [rax+rax+00h]
0x18006fadc  cmp     r13d, 0FFFFFFFFh
0x18006fae0  jz      short loc_18006FB4E
0x18006fae2  mov     rcx, [r14]; this
0x18006fae5  call    ?PrepareForCallbackIfNecessary@LRPC_BINDING_HANDLE@@QEAAJXZ; LRPC_BINDING_HANDLE::PrepareForCallbackIfNecessary(void)
0x18006faea  mov     edi, eax
0x18006faec  test    eax, eax
0x18006faee  jnz     loc_18006F8AA
0x18006faf4  mov     rcx, [r14]; this
0x18006faf7  mov     rdx, rsi; struct LRPC_CCALL *
0x18006fafa  call    ?AddRecursiveCall@LRPC_BINDING_HANDLE@@QEAAHPEAVLRPC_CCALL@@@Z; LRPC_BINDING_HANDLE::AddRecursiveCall(LRPC_CCALL *)
0x18006faff  cmp     eax, 0FFFFFFFFh
0x18006fb02  mov     r12d, eax
0x18006fb05  lea     eax, [rdi+0Eh]
0x18006fb08  cmovz   edi, eax
0x18006fb0b  jmp     loc_18006F8AA
0x18006fb10  call    I_RpcBCacheFree
0x18006fb15  jmp     loc_18006FA39
0x18006fb1a  lea     rax, [rsp+0B8h+arg_0]
0x18006fb22  mov     [rsp+0B8h+var_88], r15; struct _ALPC_MESSAGE_ATTRIBUTES *
0x18006fb27  mov     [rsp+0B8h+var_90], rax; unsigned __int64 *
0x18006fb2c  mov     edx, 20000h; unsigned int
0x18006fb31  mov     [rsp+0B8h+var_98], r8; struct _PORT_MESSAGE *
0x18006fb36  mov     [rsp+0B8h+arg_0], 1000h
0x18006fb42  call    ?AlpcSendWaitReceivePort@LRPC_CASSOCIATION@@QEAAJKPEAU_PORT_MESSAGE@@PEAU_ALPC_MESSAGE_ATTRIBUTES@@0PEA_K1PEAT_LARGE_INTEGER@@@Z; LRPC_CASSOCIATION::AlpcSendWaitReceivePort(ulong,_PORT_MESSAGE *,_ALPC_MESSAGE_ATTRIBUTES *,_PORT_MESSAGE *,unsigned __int64 *,_ALPC_MESSAGE_ATTRIBUTES *,_LARGE_INTEGER *)
0x18006fb47  xor     ebx, ebx
0x18006fb49  jmp     loc_18006F99A
0x18006fb4e  mov     edi, 0Eh
0x18006fb53  jmp     loc_18006F8AA
0x18006fb58  mov     qword ptr [rbx+28h], 8
0x18006fb60  jmp     loc_18006F8DA
0x18006fb65  mov     rax, [rsi+118h]
0x18006fb6c  mov     rbx, [rax+230h]
0x18006fb73  mov     rcx, [rbx+30h]; CriticalSection
0x18006fb77  call    cs:__imp_RtlEnterCriticalSection
0x18006fb7e  nop     dword ptr [rax+rax+00h]
0x18006fb83  mov     edx, r13d; unsigned int
0x18006fb86  mov     rcx, rbx; this
0x18006fb89  call    ?Delete@SIMPLE_DICT@@QEAAPEAXI@Z; SIMPLE_DICT::Delete(uint)
0x18006fb8e  mov     rcx, [rbx+30h]; CriticalSection
0x18006fb92  call    cs:__imp_RtlLeaveCriticalSection
0x18006fb99  nop     dword ptr [rax+rax+00h]
0x18006fb9e  jmp     loc_18006FA57
0x18006fba3  mov     edi, 71Ah
0x18006fba8  jmp     short loc_18006FBB6
0x18006fbaa  mov     edi, 6BEh
0x18006fbaf  jmp     short loc_18006FBB6
0x18006fbb1  mov     edi, 0Eh
0x18006fbb6  mov     r9d, 1; int
0x18006fbbc  mov     [rsp+0B8h+var_60], eax
0x18006fbc0  lea     rax, [rsp+0B8h+var_68]
0x18006fbc5  mov     [rsp+0B8h+var_68], 3
0x18006fbcd  mov     r8d, 50Ah; unsigned __int16
0x18006fbd3  mov     [rsp+0B8h+var_98], rax; struct tagParam *
0x18006fbd8  mov     edx, edi; int
0x18006fbda  lea     ecx, [r9+1]; unsigned int
0x18006fbde  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x18006fbe3  mov     rcx, [r14]
0x18006fbe6  mov     r8, rsi
0x18006fbe9  mov     edx, edi
0x18006fbeb  mov     rax, [rcx]
0x18006fbee  mov     rax, [rax+1E0h]
0x18006fbf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fbfa  jmp     loc_18006FA4D
0x18006fbff  mov     rcx, [r14]; this
0x18006fc02  mov     edx, r12d; int
0x18006fc05  call    ?RemoveRecursiveCall@LRPC_BINDING_HANDLE@@QEAAXH@Z; LRPC_BINDING_HANDLE::RemoveRecursiveCall(int)
0x18006fc0a  jmp     loc_18006FA61
```
