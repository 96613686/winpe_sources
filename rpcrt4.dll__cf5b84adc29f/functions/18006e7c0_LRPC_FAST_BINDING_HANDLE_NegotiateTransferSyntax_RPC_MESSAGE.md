# LRPC_FAST_BINDING_HANDLE::NegotiateTransferSyntax(_RPC_MESSAGE *)

- ea: `0x18006e7c0`
- end: `0x18006eae4`
- name: `?NegotiateTransferSyntax@LRPC_FAST_BINDING_HANDLE@@UEAAJPEAU_RPC_MESSAGE@@@Z`
- size: `804`
- prototype: `__int64 __fastcall(LRPC_CASSOCIATION **this, struct _RPC_MESSAGE *, __int64, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001c008`
- `0x180022fb8`
- `0x180026df0`
- `0x18002af84`
- `0x18006e7c0`
- `0x18006eaec`
- `0x18006eba8`
- `0x1800ceda0`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x18006eaa8`
- `ntdll!EtwEventActivityIdControl` at `0x18006eaa8`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18006ea76`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18006ea76`

## pseudocode

```c
__int64 __fastcall LRPC_FAST_BINDING_HANDLE::NegotiateTransferSyntax(
        LRPC_CASSOCIATION **this,
        struct _RPC_MESSAGE *a2,
        __int64 a3,
        __int64 a4)
{
  unsigned int i; // ecx
  LRPC_CASSOCIATION *v7; // rax
  __int64 v8; // rax
  struct LRPC_FAST_CAUSAL_FLOW *v9; // r12
  unsigned int v10; // esi
  unsigned __int64 v11; // r14
  struct LRPC_FAST_CCALL *v12; // rbx
  signed __int32 v13; // edx
  LRPC_CASSOCIATION *v14; // rax
  LRPC_CASSOCIATION *v16; // rax
  union _SLIST_HEADER *v17; // rcx
  PSLIST_ENTRY v18; // rax
  char v19; // [rsp+30h] [rbp-79h] BYREF
  char v20; // [rsp+38h] [rbp-71h] BYREF
  struct LRPC_FAST_CCALL *v21; // [rsp+40h] [rbp-69h] BYREF
  __int64 v22; // [rsp+48h] [rbp-61h] BYREF
  __int64 v23; // [rsp+50h] [rbp-59h] BYREF
  char v24[16]; // [rsp+60h] [rbp-49h] BYREF
  char *v25; // [rsp+70h] [rbp-39h]
  __int64 v26; // [rsp+78h] [rbp-31h]
  char *v27; // [rsp+80h] [rbp-29h]
  __int64 v28; // [rsp+88h] [rbp-21h]
  struct LRPC_FAST_CCALL **v29; // [rsp+90h] [rbp-19h]
  __int64 v30; // [rsp+98h] [rbp-11h]
  __int64 *v31; // [rsp+A0h] [rbp-9h]
  __int64 v32; // [rsp+A8h] [rbp-1h]
  __int64 *v33; // [rsp+B0h] [rbp+7h]
  __int64 v34; // [rsp+B8h] [rbp+Fh]

  if ( dword_1800FE624 )
  {
    for ( i = 0; i < 4; ++i )
    {
      if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[i] == 104 )
        goto LABEL_8;
    }
    if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
    {
      v30 = 8;
      v25 = &v19;
      v32 = 8;
      v27 = &v20;
      v34 = 8;
      v29 = &v21;
      v22 = 0;
      v31 = &v23;
      v33 = &v22;
      v23 = 0;
      v21 = (struct LRPC_FAST_CCALL *)this;
      v20 = 112;
      v19 = 104;
      v26 = 1;
      v28 = 1;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&RpcEtwGuid_Context,
        (unsigned int)RPCLogEvent,
        a3,
        6,
        (__int64)v24);
    }
  }
LABEL_8:
  v7 = this[8];
  if ( v7 )
    v8 = *((_QWORD *)v7 + 12);
  else
    v8 = 0;
  if ( *((int *)this + 99) < 11 )
  {
    RpcpReportFatalError(7, this, a3, a4);
    __debugbreak();
  }
  v9 = 0;
  v10 = 0;
  if ( (a2->RpcFlags & 0x8000) == 0 )
  {
    if ( v8 )
      v11 = (MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24;
    else
      LODWORD(v11) = 0;
    v12 = this[66];
    if ( v12
      && v12 == (struct LRPC_FAST_CCALL *)_InterlockedCompareExchange64(
                                            (volatile signed __int64 *)this + 66,
                                            0,
                                            (signed __int64)v12) )
    {
      goto LABEL_16;
    }
    v17 = (union _SLIST_HEADER *)(this + 68);
LABEL_36:
    v18 = InterlockedPopEntrySList(v17);
    v12 = (struct LRPC_FAST_CCALL *)&v18[-37];
    if ( !v18 )
      v12 = 0;
    goto LABEL_16;
  }
  if ( ((_DWORD)this[62] & 1) == 0 )
  {
    if ( !LrpcAsyncInitialized )
    {
      v10 = InitializeAsyncLrpc();
      if ( v10 )
        return v10;
    }
    v10 = LRPC_BASE_BINDING_HANDLE::EnableAsyncIfNecessary((LRPC_BASE_BINDING_HANDLE *)this);
    if ( v10 )
      return v10;
  }
  if ( (a2->RpcFlags & 0x2000) == 0 )
  {
    v16 = this[8];
    v10 = 0;
    if ( !v16 || !*((_QWORD *)v16 + 9) )
      v9 = this[76];
  }
  v12 = this[70];
  LODWORD(v11) = 0;
  if ( !v12
    || v12 != (struct LRPC_FAST_CCALL *)_InterlockedCompareExchange64(
                                          (volatile signed __int64 *)this + 70,
                                          0,
                                          (signed __int64)v12) )
  {
    v17 = (union _SLIST_HEADER *)(this + 72);
    goto LABEL_36;
  }
LABEL_16:
  v21 = v12;
  if ( v12 )
  {
    v13 = _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)v12 + 35) + 188LL));
    *((_QWORD *)v12 + 74) = 0;
    *((_DWORD *)v12 + 73) = v13;
    *((_DWORD *)v12 + 75) = 0;
    REFERENCED_OBJECT::SingleThreadedAddReference(v12);
  }
  else
  {
    v10 = LRPC_CASSOCIATION::AllocateCall(this[61], a2, v11, (struct LRPC_FAST_BINDING_HANDLE *)this, v9, &v21);
    if ( v10 )
      return v10;
    v12 = v21;
  }
  *((_DWORD *)v12 + 67) = 1;
  if ( dword_1800FE624 )
    EtwEventActivityIdControl(1);
  else
    *((GUID *)v12 + 13) = g_NullActivityId;
  v14 = this[74];
  a2->Handle = v12;
  a2->TransferSyntax = (PRPC_SYNTAX_IDENTIFIER)((char *)v14 + 24);
  return v10;
}

```

## disassembly

```asm
0x18006e7c0  mov     [rsp-8+arg_10], rbx
0x18006e7c5  push    rbp
0x18006e7c6  push    rsi
0x18006e7c7  push    rdi
0x18006e7c8  push    r12
0x18006e7ca  push    r13
0x18006e7cc  push    r14
0x18006e7ce  push    r15
0x18006e7d0  lea     rbp, [rsp-27h]
0x18006e7d5  sub     rsp, 0D0h
0x18006e7dc  mov     rax, cs:__security_cookie
0x18006e7e3  xor     rax, rsp
0x18006e7e6  mov     [rbp+57h+var_40], rax
0x18006e7ea  xor     r13d, r13d
0x18006e7ed  mov     r15, rdx
0x18006e7f0  cmp     cs:dword_1800FE624, r13d
0x18006e7f7  mov     rdi, rcx
0x18006e7fa  jz      short loc_18006E829
0x18006e7fc  mov     ecx, r13d
0x18006e7ff  cmp     ecx, 4
0x18006e802  jnb     short loc_18006E818
0x18006e804  movsxd  rax, ecx
0x18006e807  lea     rdx, ?EtwEventSubjectFilter@?1??LogEventToEtw@@YAXEE_J00@Z@4QBEB; "HbBr"
0x18006e80e  cmp     byte ptr [rax+rdx], 68h ; 'h'
0x18006e812  jz      short loc_18006E829
0x18006e814  inc     ecx
0x18006e816  jmp     short loc_18006E7FF
0x18006e818  mov     ecx, 8
0x18006e81d  test    cs:Microsoft_Windows_RPCEnableBits, cl
0x18006e823  jnz     loc_18006E932
0x18006e829  mov     rax, [rdi+40h]
0x18006e82d  test    rax, rax
0x18006e830  jz      loc_18006EA9A
0x18006e836  mov     rax, [rax+60h]
0x18006e83a  cmp     dword ptr [rdi+18Ch], 0Bh
0x18006e841  jl      loc_18006EAB9
0x18006e847  test    dword ptr [r15+48h], 8000h
0x18006e84f  mov     r12, r13
0x18006e852  mov     esi, r13d
0x18006e855  jnz     loc_18006E9EB
0x18006e85b  test    rax, rax
0x18006e85e  jnz     loc_18006EAC7
0x18006e864  mov     r14d, r13d
0x18006e867  mov     rbx, [rdi+210h]
0x18006e86e  test    rbx, rbx
0x18006e871  jz      loc_18006EA6F
0x18006e877  mov     rcx, r13
0x18006e87a  mov     rax, rbx
0x18006e87d  lock cmpxchg [rdi+210h], rcx
0x18006e886  jnz     loc_18006EA6F
0x18006e88c  mov     [rbp+57h+var_C0], rbx
0x18006e890  test    rbx, rbx
0x18006e893  jz      loc_18006E9B1
0x18006e899  mov     rax, [rbx+118h]
0x18006e8a0  mov     r14d, 1
0x18006e8a6  mov     edx, r14d
0x18006e8a9  lock xadd [rax+0BCh], edx
0x18006e8b1  add     edx, r14d
0x18006e8b4  mov     [rbx+250h], r13
0x18006e8bb  mov     rcx, rbx; this
0x18006e8be  mov     [rbx+124h], edx
0x18006e8c4  mov     [rbx+12Ch], r13d
0x18006e8cb  call    ?SingleThreadedAddReference@REFERENCED_OBJECT@@QEAAXXZ; REFERENCED_OBJECT::SingleThreadedAddReference(void)
0x18006e8d0  mov     [rbx+10Ch], r14d
0x18006e8d7  lea     rax, [rbx+0D0h]
0x18006e8de  cmp     cs:dword_1800FE624, r13d
0x18006e8e5  jnz     loc_18006EAA2
0x18006e8eb  movups  xmm0, xmmword ptr cs:?g_NullActivityId@@3U_GUID@@B.Data1; _GUID const g_NullActivityId ...
0x18006e8f2  movdqu  xmmword ptr [rax], xmm0
0x18006e8f6  mov     rax, [rdi+250h]
0x18006e8fd  add     rax, 18h
0x18006e901  mov     [r15], rbx
0x18006e904  mov     [r15+20h], rax
0x18006e908  mov     eax, esi
0x18006e90a  mov     rcx, [rbp+57h+var_40]
0x18006e90e  xor     rcx, rsp; StackCookie
0x18006e911  call    __security_check_cookie
0x18006e916  mov     rbx, [rsp+100h+arg_10]
0x18006e91e  add     rsp, 0D0h
0x18006e925  pop     r15
0x18006e927  pop     r14
0x18006e929  pop     r13
0x18006e92b  pop     r12
0x18006e92d  pop     rdi
0x18006e92e  pop     rsi
0x18006e92f  pop     rbp
0x18006e930  retn
0x18006e932  lea     rax, [rbp+57h+var_D0]
0x18006e936  mov     [rbp+57h+var_68], rcx
0x18006e93a  mov     [rbp+57h+var_90], rax
0x18006e93e  lea     rdx, RPCLogEvent
0x18006e945  lea     rax, [rbp+57h+var_C8]
0x18006e949  mov     [rbp+57h+var_58], rcx
0x18006e94d  mov     [rbp+57h+var_80], rax
0x18006e951  mov     r9d, 6
0x18006e957  lea     rax, [rbp+57h+var_C0]
0x18006e95b  mov     [rbp+57h+var_48], rcx
0x18006e95f  mov     [rbp+57h+var_70], rax
0x18006e963  lea     rcx, RpcEtwGuid_Context
0x18006e96a  lea     rax, [rbp+57h+var_B0]
0x18006e96e  mov     [rbp+57h+var_B8], r13
0x18006e972  mov     [rbp+57h+var_60], rax
0x18006e976  lea     rax, [rbp+57h+var_B8]
0x18006e97a  mov     [rbp+57h+var_50], rax
0x18006e97e  lea     rax, [rbp+57h+var_A0]
0x18006e982  mov     [rsp+100h+var_E0], rax
0x18006e987  mov     [rbp+57h+var_B0], r13
0x18006e98b  mov     [rbp+57h+var_C0], rdi
0x18006e98f  mov     [rbp+57h+var_C8], 70h ; 'p'
0x18006e993  mov     [rbp+57h+var_D0], 68h ; 'h'
0x18006e997  mov     [rbp+57h+var_88], 1
0x18006e99f  mov     [rbp+57h+var_78], 1
0x18006e9a7  call    McGenEventWrite_EtwEventWriteTransfer
0x18006e9ac  jmp     loc_18006E829
0x18006e9b1  mov     rcx, [rdi+1E8h]; this
0x18006e9b8  lea     rax, [rbp+57h+var_C0]
0x18006e9bc  mov     [rsp+100h+var_D8], rax; struct LRPC_FAST_CCALL **
0x18006e9c1  mov     r9, rdi; struct LRPC_FAST_BINDING_HANDLE *
0x18006e9c4  mov     r8d, r14d; unsigned int
0x18006e9c7  mov     [rsp+100h+var_E0], r12; struct LRPC_FAST_CAUSAL_FLOW *
0x18006e9cc  mov     rdx, r15; struct _RPC_MESSAGE *
0x18006e9cf  call    ?AllocateCall@LRPC_CASSOCIATION@@QEAAJPEAU_RPC_MESSAGE@@KPEAVLRPC_FAST_BINDING_HANDLE@@PEAVLRPC_FAST_CAUSAL_FLOW@@PEAPEAVLRPC_FAST_CCALL@@@Z; LRPC_CASSOCIATION::AllocateCall(_RPC_MESSAGE *,ulong,LRPC_FAST_BINDING_HANDLE *,LRPC_FAST_CAUSAL_FLOW *,LRPC_FAST_CCALL * *)
0x18006e9d4  mov     esi, eax
0x18006e9d6  test    eax, eax
0x18006e9d8  jnz     loc_18006E908
0x18006e9de  mov     rbx, [rbp+57h+var_C0]
0x18006e9e2  lea     r14d, [rax+1]
0x18006e9e6  jmp     loc_18006E8D0
0x18006e9eb  mov     eax, [rdi+1F0h]
0x18006e9f1  test    al, 1
0x18006e9f3  jnz     short loc_18006EA1F
0x18006e9f5  cmp     cs:?LrpcAsyncInitialized@@3HA, r13d; int LrpcAsyncInitialized
0x18006e9fc  jnz     short loc_18006EA0D
0x18006e9fe  call    ?InitializeAsyncLrpc@@YAJXZ; InitializeAsyncLrpc(void)
0x18006ea03  mov     esi, eax
0x18006ea05  test    eax, eax
0x18006ea07  jnz     loc_18006E908
0x18006ea0d  mov     rcx, rdi; this
0x18006ea10  call    ?EnableAsyncIfNecessary@LRPC_BASE_BINDING_HANDLE@@QEAAJXZ; LRPC_BASE_BINDING_HANDLE::EnableAsyncIfNecessary(void)
0x18006ea15  mov     esi, eax
0x18006ea17  test    eax, eax
0x18006ea19  jnz     loc_18006E908
0x18006ea1f  test    dword ptr [r15+48h], 2000h
0x18006ea27  jnz     short loc_18006EA42
0x18006ea29  mov     rax, [rdi+40h]
0x18006ea2d  mov     esi, r13d
0x18006ea30  test    rax, rax
0x18006ea33  jz      short loc_18006EA3B
0x18006ea35  cmp     [rax+48h], r13
0x18006ea39  jnz     short loc_18006EA42
0x18006ea3b  mov     r12, [rdi+260h]
0x18006ea42  mov     rbx, [rdi+230h]
0x18006ea49  mov     r14d, r13d
0x18006ea4c  test    rbx, rbx
0x18006ea4f  jz      short loc_18006EA66
0x18006ea51  mov     rcx, r13
0x18006ea54  mov     rax, rbx
0x18006ea57  lock cmpxchg [rdi+230h], rcx
0x18006ea60  jz      loc_18006E88C
0x18006ea66  lea     rcx, [rdi+240h]
0x18006ea6d  jmp     short loc_18006EA76
0x18006ea6f  lea     rcx, [rdi+220h]; ListHead
0x18006ea76  call    cs:__imp_InterlockedPopEntrySList
0x18006ea7d  nop     dword ptr [rax+rax+00h]
0x18006ea82  lea     rbx, [rax-250h]
0x18006ea89  test    rax, rax
0x18006ea8c  jnz     loc_18006E88C
0x18006ea92  mov     rbx, r13
0x18006ea95  jmp     loc_18006E88C
0x18006ea9a  mov     rax, r13
0x18006ea9d  jmp     loc_18006E83A
0x18006eaa2  mov     rdx, rax
0x18006eaa5  mov     ecx, r14d
0x18006eaa8  call    cs:__imp_EtwEventActivityIdControl
0x18006eaaf  nop     dword ptr [rax+rax+00h]
0x18006eab4  jmp     loc_18006E8F6
0x18006eab9  mov     rdx, rdi
0x18006eabc  mov     ecx, 7
0x18006eac1  call    RpcpReportFatalError
0x18006eac6  int     3; Trap to Debugger
0x18006eac7  mov     eax, 7FFE0320h
0x18006eacc  mov     rax, [rax]
0x18006eacf  mov     r14d, ds:7FFE0004h
0x18006ead7  imul    r14, rax
0x18006eadb  shr     r14, 18h
0x18006eadf  jmp     loc_18006E867
```
