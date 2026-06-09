# LRPC_CCALL::HandleCallbackSequence(_RPC_MESSAGE *)

- ea: `0x180070b10`
- end: `0x180070ea0`
- name: `?HandleCallbackSequence@LRPC_CCALL@@EEAAJPEAU_RPC_MESSAGE@@@Z`
- size: `912`
- prototype: `__int64 __fastcall(LRPC_BINDING_HANDLE **this, struct _RPC_MESSAGE *)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, loader_planting, installer_update`

## callees

- `0x180025280`
- `0x180026ca0`
- `0x180027220`
- `0x1800283bc`
- `0x18004cc10`
- `0x18004f480`
- `0x18005e400`
- `0x180070aac`
- `0x180070b10`
- `0x180071640`
- `0x1800716d8`
- `0x1800721f8`
- `0x180072360`
- `0x1800723f0`
- `0x18009eb40`
- `0x1800d2010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180070d73`
- `ntdll!RtlLeaveCriticalSection` at `0x180070e29`
- `ntdll!RtlLeaveCriticalSection` at `0x180070d73`
- `ntdll!RtlLeaveCriticalSection` at `0x180070e29`
- `ntdll!RtlEnterCriticalSection` at `0x180070d5b`
- `ntdll!RtlEnterCriticalSection` at `0x180070e14`
- `ntdll!RtlEnterCriticalSection` at `0x180070d5b`
- `ntdll!RtlEnterCriticalSection` at `0x180070e14`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180070b71`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180070b71`

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
  union _LARGE_INTEGER *v22; // [rsp+38h] [rbp-80h]
  _DWORD v23[26]; // [rsp+50h] [rbp-68h] BYREF
  unsigned __int64 v24; // [rsp+C0h] [rbp+8h] BYREF

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
  RpcpAlpcInitializeMessageAttribute(0xA0000000, v2, 0x40u, &v24);
  if ( *((_QWORD *)v9 + 5) == 7 )
    *(_QWORD *)((char *)v2 + RpcpAlpcpGetHeaderSize(*(_DWORD *)v2 & 0xC0000000) + 8) = this;
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
    v15 = LRPC_CASSOCIATION::AlpcSendWaitReceivePort(v13, 0, v14, v2, 0, 0, 0, v22);
  }
  else
  {
    v24 = 4096;
    v15 = LRPC_CASSOCIATION::AlpcSendWaitReceivePort(v13, 0x20000u, v14, v2, v14, &v24, v2, v22);
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
    v23[2] = v15;
    v23[0] = 3;
    RpcpErrorAddRecord(2u, v7, 0x50Au, 1, (struct tagParam *)v23);
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
0x180070b10  push    rbx
0x180070b12  push    rbp
0x180070b13  push    rsi
0x180070b14  push    rdi
0x180070b15  push    r12
0x180070b17  push    r13
0x180070b19  push    r14
0x180070b1b  push    r15
0x180070b1d  sub     rsp, 78h
0x180070b21  or      eax, 0FFFFFFFFh
0x180070b24  lea     r15, [rcx+128h]
0x180070b2b  cmp     cs:?LrpcAsyncInitialized@@3HA, 0; int LrpcAsyncInitialized
0x180070b32  mov     rbp, rdx
0x180070b35  mov     rsi, rcx
0x180070b38  mov     r13d, eax
0x180070b3b  mov     r12d, eax
0x180070b3e  jnz     loc_180070D1E
0x180070b44  call    ?InitializeAsyncLrpc@@YAJXZ; InitializeAsyncLrpc(void)
0x180070b49  mov     edi, eax
0x180070b4b  test    eax, eax
0x180070b4d  jz      loc_180070D1E
0x180070b53  lea     r14, [rsi+110h]
0x180070b5a  mov     rbx, [rsi+1F8h]
0x180070b61  test    edi, edi
0x180070b63  jnz     loc_180070DF5
0x180070b69  mov     qword ptr [rbx+28h], 7
0x180070b71  call    cs:__imp_GetCurrentThreadId
0x180070b77  mov     rcx, [rsi+250h]
0x180070b7e  mov     [rcx+0C8h], eax
0x180070b84  lea     r9, [rsp+0B8h+arg_0]; unsigned __int64 *
0x180070b8c  mov     r8d, 40h ; '@'; unsigned __int64
0x180070b92  mov     rdx, r15; struct RPCP_ALPC_MESSAGE_ATTRIBUTES *
0x180070b95  mov     ecx, 0A0000000h; unsigned int
0x180070b9a  call    ?RpcpAlpcInitializeMessageAttribute@@YAJKPEAVRPCP_ALPC_MESSAGE_ATTRIBUTES@@_KPEA_K@Z; RpcpAlpcInitializeMessageAttribute(ulong,RPCP_ALPC_MESSAGE_ATTRIBUTES *,unsigned __int64,unsigned __int64 *)
0x180070b9f  cmp     qword ptr [rbx+28h], 7
0x180070ba4  jnz     short loc_180070BBC
0x180070ba6  mov     ecx, [r15]
0x180070ba9  and     ecx, 0C0000000h; unsigned int
0x180070baf  call    ?RpcpAlpcpGetHeaderSize@@YAKK@Z; RpcpAlpcpGetHeaderSize(ulong)
0x180070bb4  mov     r9d, eax
0x180070bb7  mov     [r9+r15+8], rsi
0x180070bbc  mov     rax, [r14]
0x180070bbf  xor     ecx, ecx; unsigned int
0x180070bc1  mov     r10, [rax+1B0h]
0x180070bc8  call    ?RpcpAlpcpGetHeaderSize@@YAKK@Z; RpcpAlpcpGetHeaderSize(ulong)
0x180070bcd  movups  xmm0, xmmword ptr [r10]
0x180070bd1  mov     r9d, eax
0x180070bd4  xor     eax, eax
0x180070bd6  movups  xmmword ptr [r9+r15], xmm0
0x180070bdb  movsd   xmm1, qword ptr [r10+10h]
0x180070be1  xorps   xmm0, xmm0
0x180070be4  movsd   qword ptr [r9+r15+10h], xmm1
0x180070beb  mov     r9, r15; struct _ALPC_MESSAGE_ATTRIBUTES *
0x180070bee  mov     dword ptr [r15+4], 0A0000000h
0x180070bf6  movups  xmmword ptr [rbx], xmm0
0x180070bf9  movups  xmmword ptr [rbx+10h], xmm0
0x180070bfd  mov     [rbx+20h], rax
0x180070c01  cmp     qword ptr [rbx+28h], 7
0x180070c06  mov     dword ptr [rbx], 380010h
0x180070c0c  mov     [rbx+30h], eax
0x180070c0f  mov     eax, [rsi+124h]
0x180070c15  mov     [rbx+34h], eax
0x180070c18  mov     rcx, [rsi+118h]; this
0x180070c1f  mov     r8, [rsi+1F8h]; struct _PORT_MESSAGE *
0x180070c26  jnz     loc_180070DB7
0x180070c2c  xor     ebx, ebx
0x180070c2e  xor     edx, edx; unsigned int
0x180070c30  mov     [rsp+0B8h+var_88], rbx; struct _ALPC_MESSAGE_ATTRIBUTES *
0x180070c35  mov     [rsp+0B8h+var_90], rbx; unsigned int
0x180070c3a  mov     [rsp+0B8h+var_98], rbx; struct _PORT_MESSAGE *
0x180070c3f  call    ?AlpcSendWaitReceivePort@LRPC_CASSOCIATION@@QEAAJKPEAU_PORT_MESSAGE@@PEAU_ALPC_MESSAGE_ATTRIBUTES@@0PEA_K1PEAT_LARGE_INTEGER@@@Z; LRPC_CASSOCIATION::AlpcSendWaitReceivePort(ulong,_PORT_MESSAGE *,_ALPC_MESSAGE_ATTRIBUTES *,_PORT_MESSAGE *,unsigned __int64 *,_ALPC_MESSAGE_ATTRIBUTES *,_LARGE_INTEGER *)
0x180070c44  cmp     eax, 0C0000017h
0x180070c49  jz      loc_180070E42
0x180070c4f  cmp     eax, 0C0000037h
0x180070c54  jz      loc_180070E3B
0x180070c5a  cmp     eax, 0C0000044h
0x180070c5f  jz      loc_180070E42
0x180070c65  cmp     eax, 0C000009Ah
0x180070c6a  jz      loc_180070E42
0x180070c70  cmp     eax, 0C0000701h
0x180070c75  jz      loc_180070E34
0x180070c7b  test    eax, eax
0x180070c7d  jnz     loc_180070E3B
0x180070c83  test    edi, edi
0x180070c85  jnz     loc_180070E47
0x180070c8b  mov     rax, [rsi+250h]
0x180070c92  lea     edx, [rdi+1]; int
0x180070c95  mov     [rsp+0B8h+var_78], rbx; struct LRPC_SBINDING *
0x180070c9a  mov     [rsp+0B8h+var_80], rbx; struct RPC_UUID *
0x180070c9f  mov     dword ptr [rsp+0B8h+var_88], ebx; int
0x180070ca3  inc     dword ptr [rax+8]
0x180070ca6  mov     r8, [rbp+20h]; struct _RPC_SYNTAX_IDENTIFIER *
0x180070caa  mov     dword ptr [rbp+8], 10h
0x180070cb1  mov     r9, [rsi+278h]
0x180070cb8  mov     rcx, [rsi+250h]; this
0x180070cbf  mov     [rsp+0B8h+var_98], rbp; struct _RPC_MESSAGE *
0x180070cc4  mov     r9, [r9+30h]; struct RPC_DISPATCH_TABLE *
0x180070cc8  call    ?SendReceiveLoop@LRPC_CALLBACK@@QEAAJHPEAU_RPC_SYNTAX_IDENTIFIER@@PEAURPC_DISPATCH_TABLE@@PEAU_RPC_MESSAGE@@KHPEAVRPC_UUID@@PEAVLRPC_SBINDING@@@Z; LRPC_CALLBACK::SendReceiveLoop(int,_RPC_SYNTAX_IDENTIFIER *,RPC_DISPATCH_TABLE *,_RPC_MESSAGE *,ulong,int,RPC_UUID *,LRPC_SBINDING *)
0x180070ccd  mov     edi, eax
0x180070ccf  test    eax, eax
0x180070cd1  jnz     short loc_180070CF7
0x180070cd3  mov     rcx, [rsi+1F8h]; void *
0x180070cda  test    rcx, rcx
0x180070cdd  jnz     loc_180070DAD
0x180070ce3  mov     rcx, [rbp+10h]
0x180070ce7  mov     [rsi+1F8h], rcx
0x180070cee  mov     ecx, [rbp+18h]
0x180070cf1  mov     [rsi+210h], ecx
0x180070cf7  cmp     r13d, 0FFFFFFFFh
0x180070cfb  jnz     loc_180070E02
0x180070d01  cmp     r12d, 0FFFFFFFFh
0x180070d05  jnz     loc_180070E90
0x180070d0b  mov     eax, edi
0x180070d0d  add     rsp, 78h
0x180070d11  pop     r15
0x180070d13  pop     r14
0x180070d15  pop     r13
0x180070d17  pop     r12
0x180070d19  pop     rdi
0x180070d1a  pop     rsi
0x180070d1b  pop     rbp
0x180070d1c  pop     rbx
0x180070d1d  retn
0x180070d1e  lea     r14, [rsi+110h]
0x180070d25  mov     rcx, [r14]; this
0x180070d28  call    ?EnableCallbackIfNecessary@LRPC_BINDING_HANDLE@@QEAAJXZ; LRPC_BINDING_HANDLE::EnableCallbackIfNecessary(void)
0x180070d2d  mov     edi, eax
0x180070d2f  test    eax, eax
0x180070d31  jnz     loc_180070B5A
0x180070d37  mov     rcx, rsi; this
0x180070d3a  call    ?PrepareForCallbackIfNecessary@LRPC_CCALL@@AEAAJXZ; LRPC_CCALL::PrepareForCallbackIfNecessary(void)
0x180070d3f  mov     edi, eax
0x180070d41  test    eax, eax
0x180070d43  jnz     loc_180070B5A
0x180070d49  mov     rax, [rsi+118h]
0x180070d50  mov     rbx, [rax+230h]
0x180070d57  mov     rcx, [rbx+30h]; CriticalSection
0x180070d5b  call    cs:__imp_RtlEnterCriticalSection
0x180070d61  mov     rdx, rsi; void *
0x180070d64  mov     rcx, rbx; this
0x180070d67  call    ?Insert@SIMPLE_DICT@@QEAAIPEAX@Z; SIMPLE_DICT::Insert(void *)
0x180070d6c  mov     rcx, [rbx+30h]; CriticalSection
0x180070d70  mov     r13d, eax
0x180070d73  call    cs:__imp_RtlLeaveCriticalSection
0x180070d79  cmp     r13d, 0FFFFFFFFh
0x180070d7d  jz      short loc_180070DEB
0x180070d7f  mov     rcx, [r14]; this
0x180070d82  call    ?PrepareForCallbackIfNecessary@LRPC_BINDING_HANDLE@@QEAAJXZ; LRPC_BINDING_HANDLE::PrepareForCallbackIfNecessary(void)
0x180070d87  mov     edi, eax
0x180070d89  test    eax, eax
0x180070d8b  jnz     loc_180070B5A
0x180070d91  mov     rcx, [r14]; this
0x180070d94  mov     rdx, rsi; struct LRPC_CCALL *
0x180070d97  call    ?AddRecursiveCall@LRPC_BINDING_HANDLE@@QEAAHPEAVLRPC_CCALL@@@Z; LRPC_BINDING_HANDLE::AddRecursiveCall(LRPC_CCALL *)
0x180070d9c  cmp     eax, 0FFFFFFFFh
0x180070d9f  mov     r12d, eax
0x180070da2  lea     eax, [rdi+0Eh]
0x180070da5  cmovz   edi, eax
0x180070da8  jmp     loc_180070B5A
0x180070dad  call    I_RpcBCacheFree
0x180070db2  jmp     loc_180070CE3
0x180070db7  lea     rax, [rsp+0B8h+arg_0]
0x180070dbf  mov     [rsp+0B8h+var_88], r15; struct _ALPC_MESSAGE_ATTRIBUTES *
0x180070dc4  mov     [rsp+0B8h+var_90], rax; unsigned __int64 *
0x180070dc9  mov     edx, 20000h; unsigned int
0x180070dce  mov     [rsp+0B8h+var_98], r8; struct _PORT_MESSAGE *
0x180070dd3  mov     [rsp+0B8h+arg_0], 1000h
0x180070ddf  call    ?AlpcSendWaitReceivePort@LRPC_CASSOCIATION@@QEAAJKPEAU_PORT_MESSAGE@@PEAU_ALPC_MESSAGE_ATTRIBUTES@@0PEA_K1PEAT_LARGE_INTEGER@@@Z; LRPC_CASSOCIATION::AlpcSendWaitReceivePort(ulong,_PORT_MESSAGE *,_ALPC_MESSAGE_ATTRIBUTES *,_PORT_MESSAGE *,unsigned __int64 *,_ALPC_MESSAGE_ATTRIBUTES *,_LARGE_INTEGER *)
0x180070de4  xor     ebx, ebx
0x180070de6  jmp     loc_180070C44
0x180070deb  mov     edi, 0Eh
0x180070df0  jmp     loc_180070B5A
0x180070df5  mov     qword ptr [rbx+28h], 8
0x180070dfd  jmp     loc_180070B84
0x180070e02  mov     rax, [rsi+118h]
0x180070e09  mov     rbx, [rax+230h]
0x180070e10  mov     rcx, [rbx+30h]; CriticalSection
0x180070e14  call    cs:__imp_RtlEnterCriticalSection
0x180070e1a  mov     edx, r13d; unsigned int
0x180070e1d  mov     rcx, rbx; this
0x180070e20  call    ?Delete@SIMPLE_DICT@@QEAAPEAXI@Z; SIMPLE_DICT::Delete(uint)
0x180070e25  mov     rcx, [rbx+30h]; CriticalSection
0x180070e29  call    cs:__imp_RtlLeaveCriticalSection
0x180070e2f  jmp     loc_180070D01
0x180070e34  mov     edi, 71Ah
0x180070e39  jmp     short loc_180070E47
0x180070e3b  mov     edi, 6BEh
0x180070e40  jmp     short loc_180070E47
0x180070e42  mov     edi, 0Eh
0x180070e47  mov     r9d, 1; int
0x180070e4d  mov     [rsp+0B8h+var_60], eax
0x180070e51  lea     rax, [rsp+0B8h+var_68]
0x180070e56  mov     [rsp+0B8h+var_68], 3
0x180070e5e  mov     r8d, 50Ah; unsigned __int16
0x180070e64  mov     [rsp+0B8h+var_98], rax; struct tagParam *
0x180070e69  mov     edx, edi; int
0x180070e6b  lea     ecx, [r9+1]; unsigned int
0x180070e6f  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x180070e74  mov     rcx, [r14]
0x180070e77  mov     r8, rsi
0x180070e7a  mov     edx, edi
0x180070e7c  mov     rax, [rcx]
0x180070e7f  mov     rax, [rax+1E0h]
0x180070e86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070e8b  jmp     loc_180070CF7
0x180070e90  mov     rcx, [r14]; this
0x180070e93  mov     edx, r12d; int
0x180070e96  call    ?RemoveRecursiveCall@LRPC_BINDING_HANDLE@@QEAAXH@Z; LRPC_BINDING_HANDLE::RemoveRecursiveCall(int)
0x180070e9b  jmp     loc_180070D0B
```
