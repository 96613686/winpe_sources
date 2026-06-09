# VpnIkeIKEEXTRpcRemoteAccessCheck(void * *,void *)

- ea: `0x1800638a0`
- end: `0x1800639c7`
- name: `?VpnIkeIKEEXTRpcRemoteAccessCheck@@YAJPEAPEAXPEAX@Z`
- size: `295`
- prototype: `__int64 __fastcall(RPC_IF_HANDLE InterfaceUuid, void *Context)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, service_task`

## callees

- `0x18006361c`
- `0x1800638a0`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180063935`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180063935`

## string_xrefs

- `0x18006391d`: `VpnIkeIKEEXTRpcRemoteAccessCheck`

## pseudocode

```c
__int64 __fastcall VpnIkeIKEEXTRpcRemoteAccessCheck(RPC_IF_HANDLE InterfaceUuid, void *Context)
{
  unsigned int IsClientLocal; // eax
  unsigned int v3; // ebx
  unsigned int ClientLocalFlag; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v6; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v7; // [rsp+30h] [rbp-D0h]
  __int128 v8; // [rsp+40h] [rbp-C0h]
  __int64 v9; // [rsp+50h] [rbp-B0h]
  int v10; // [rsp+58h] [rbp-A8h]
  int v11; // [rsp+5Ch] [rbp-A4h]
  int v12; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v13[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  ClientLocalFlag = 0;
  v12 = 0;
  memset_0(v13, 0, sizeof(v13));
  v6 = 0;
  v7 = 0;
  v9 = 0;
  v8 = 0;
  v10 = -1;
  v11 = 0;
  if ( *((_QWORD *)&xmmword_1800AAC20 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v6,
      L"VpnIkeIKEEXTRpcRemoteAccessCheck",
      0,
      VpnIkeRpcTraceFunction);
  IsClientLocal = I_RpcBindingIsClientLocal(0, &ClientLocalFlag);
  if ( IsClientLocal || !ClientLocalFlag )
  {
    if ( (_QWORD)xmmword_1800AAC20 )
    {
      LOWORD(v12) = 0;
      FormatRRASErrorString(&v12, L"I_RpcBindingIsClientLocal returned: %d", IsClientLocal);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gVpnIkeRpcTemplateFunc)(
        gVpnIkeRpcEtwContext,
        xmmword_1800AAC20,
        &v12);
    }
    v3 = 5;
  }
  else
  {
    v3 = (unsigned int)IsRPCClientIKEEXTService() == 0 ? 5 : 0;
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v6);
  return v3;
}

```

## disassembly

```asm
0x1800638a0  mov     [rsp-8+arg_0], rbx
0x1800638a5  push    rbp
0x1800638a6  lea     rbp, [rsp-770h]
0x1800638ae  sub     rsp, 870h
0x1800638b5  mov     rax, cs:__security_cookie
0x1800638bc  xor     rax, rsp
0x1800638bf  mov     [rbp+770h+var_10], rax
0x1800638c6  xor     ebx, ebx
0x1800638c8  lea     rcx, [rsp+870h+var_80C]; void *
0x1800638cd  xor     edx, edx; Val
0x1800638cf  mov     [rsp+870h+ClientLocalFlag], ebx
0x1800638d3  mov     r8d, 7FCh; Size
0x1800638d9  mov     [rsp+870h+var_810], ebx
0x1800638dd  call    memset_0
0x1800638e2  cmp     qword ptr cs:xmmword_1800AAC20+8, rbx
0x1800638e9  xorps   xmm0, xmm0
0x1800638ec  xorps   xmm1, xmm1
0x1800638ef  mov     [rsp+870h+var_848], rbx
0x1800638f4  movdqu  [rsp+870h+var_840], xmm0
0x1800638fa  mov     [rsp+870h+var_820], rbx
0x1800638ff  movdqu  [rsp+870h+var_830], xmm1
0x180063905  mov     [rsp+870h+var_818], 0FFFFFFFFh
0x18006390d  mov     [rsp+870h+var_814], ebx
0x180063911  jz      short loc_18006392E
0x180063913  lea     r9, VpnIkeRpcTraceFunction; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18006391a  xor     r8d, r8d; unsigned int *
0x18006391d  lea     rdx, aVpnikeikeextrp; "VpnIkeIKEEXTRpcRemoteAccessCheck"
0x180063924  lea     rcx, [rsp+870h+var_848]; this
0x180063929  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x18006392e  lea     rdx, [rsp+870h+ClientLocalFlag]; ClientLocalFlag
0x180063933  xor     ecx, ecx; BindingHandle
0x180063935  call    cs:__imp_I_RpcBindingIsClientLocal
0x18006393b  mov     r8d, eax
0x18006393e  test    eax, eax
0x180063940  jnz     short loc_180063958
0x180063942  cmp     [rsp+870h+ClientLocalFlag], ebx
0x180063946  jz      short loc_180063958
0x180063948  call    ?IsRPCClientIKEEXTService@@YAHXZ; IsRPCClientIKEEXTService(void)
0x18006394d  neg     eax
0x18006394f  sbb     ebx, ebx
0x180063951  not     ebx
0x180063953  and     ebx, 5
0x180063956  jmp     short loc_18006399B
0x180063958  cmp     qword ptr cs:xmmword_1800AAC20, rbx
0x18006395f  jz      short loc_180063996
0x180063961  lea     rdx, aIRpcbindingisc; "I_RpcBindingIsClientLocal returned: %d"
0x180063968  mov     word ptr [rsp+870h+var_810], bx
0x18006396d  lea     rcx, [rsp+870h+var_810]
0x180063972  call    FormatRRASErrorString
0x180063977  mov     rdx, qword ptr cs:xmmword_1800AAC20
0x18006397e  lea     r8, [rsp+870h+var_810]
0x180063983  mov     rcx, cs:?gVpnIkeRpcEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gVpnIkeRpcEtwContext
0x18006398a  mov     rax, cs:?gVpnIkeRpcTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gVpnIkeRpcTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180063991  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063996  mov     ebx, 5
0x18006399b  lea     rcx, [rsp+870h+var_848]; this
0x1800639a0  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x1800639a5  mov     eax, ebx
0x1800639a7  mov     rcx, [rbp+770h+var_10]
0x1800639ae  xor     rcx, rsp; StackCookie
0x1800639b1  call    __security_check_cookie
0x1800639b6  mov     rbx, [rsp+870h+arg_0]
0x1800639be  add     rsp, 870h
0x1800639c5  pop     rbp
0x1800639c6  retn
```
