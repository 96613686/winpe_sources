# IsRPCClientIKEEXTService(void)

- ea: `0x18006361c`
- end: `0x180063895`
- name: `?IsRPCClientIKEEXTService@@YAHXZ`
- size: `633`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800638a0`

## callees

- `0x18006361c`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063776`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800637c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063776`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800637c9`
- `RPCRT4!RpcImpersonateClient` at `0x1800636c2`
- `RPCRT4!RpcImpersonateClient` at `0x1800636c2`
- `RPCRT4!RpcRevertToSelf` at `0x180063816`
- `RPCRT4!RpcRevertToSelf` at `0x180063816`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180063768`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180063768`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18006374e`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18006374e`

## string_xrefs

- `0x1800636af`: `IsRPCClientIKEEXTService`
- `0x1800636e3`: `RpcImpersonateClient failed: %d`
- `0x180063742`: `NT SERVICE\IKEEXT`
- `0x18006378f`: `CheckTokenMembership failed: %d`
- `0x18006382a`: `IsRPCClientIKEEXTService returns: %d`

## pseudocode

```c
__int64 IsRPCClientIKEEXTService(void)
{
  unsigned int v0; // eax
  DWORD LastError; // eax
  DWORD v2; // eax
  unsigned int v3; // ebx
  WINBOOL IsMember; // [rsp+40h] [rbp-C0h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cchReferencedDomainName; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cbSid; // [rsp+4Ch] [rbp-B4h] BYREF
  __int64 v9; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v10; // [rsp+58h] [rbp-A8h]
  __int128 v11; // [rsp+68h] [rbp-98h]
  __int64 v12; // [rsp+78h] [rbp-88h]
  int v13; // [rsp+80h] [rbp-80h]
  int v14; // [rsp+84h] [rbp-7Ch]
  _BYTE Sid[256]; // [rsp+90h] [rbp-70h] BYREF
  int v16; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v17[2044]; // [rsp+194h] [rbp+94h] BYREF
  WCHAR ReferencedDomainName[104]; // [rsp+990h] [rbp+890h] BYREF

  cbSid = 256;
  IsMember = 0;
  peUse = 0;
  v16 = 0;
  cchReferencedDomainName = 100;
  memset_0(v17, 0, sizeof(v17));
  v9 = 0;
  v10 = 0;
  v12 = 0;
  v11 = 0;
  v13 = -1;
  v14 = 0;
  if ( *((_QWORD *)&xmmword_1800AAC20 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v9,
      L"IsRPCClientIKEEXTService",
      0,
      VpnIkeRpcTraceFunction);
  v0 = RpcImpersonateClient(0);
  if ( v0 )
  {
    if ( (_QWORD)xmmword_1800AAC20 )
    {
      LOWORD(v16) = 0;
      FormatRRASErrorString(&v16, L"RpcImpersonateClient failed: %d", v0);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gVpnIkeRpcTemplateFunc)(
        gVpnIkeRpcEtwContext,
        xmmword_1800AAC20,
        &v16);
    }
  }
  else
  {
    if ( LookupAccountNameW(
           0,
           L"NT SERVICE\\IKEEXT",
           Sid,
           &cbSid,
           ReferencedDomainName,
           &cchReferencedDomainName,
           &peUse) )
    {
      if ( !CheckTokenMembership((HANDLE)0xFFFFFFFFFFFFFFFBLL, Sid, &IsMember) )
      {
        LastError = GetLastError();
        if ( (_QWORD)xmmword_1800AAC20 )
        {
          LOWORD(v16) = 0;
          FormatRRASErrorString(&v16, L"CheckTokenMembership failed: %d", LastError);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gVpnIkeRpcTemplateFunc)(
            gVpnIkeRpcEtwContext,
            xmmword_1800AAC20,
            &v16);
        }
        IsMember = 0;
      }
    }
    else
    {
      v2 = GetLastError();
      if ( (_QWORD)xmmword_1800AAC20 )
      {
        LOWORD(v16) = 0;
        FormatRRASErrorString(&v16, L"LookupAccountName failed: %d", v2);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gVpnIkeRpcTemplateFunc)(
          gVpnIkeRpcEtwContext,
          xmmword_1800AAC20,
          &v16);
      }
    }
    RpcRevertToSelf();
  }
  if ( *((_QWORD *)&xmmword_1800AAC20 + 1) )
  {
    LOWORD(v16) = 0;
    FormatRRASErrorString(&v16, L"IsRPCClientIKEEXTService returns: %d", (unsigned int)IsMember);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gVpnIkeRpcTemplateFunc)(
      gVpnIkeRpcEtwContext,
      *((_QWORD *)&xmmword_1800AAC20 + 1),
      &v16);
  }
  v3 = IsMember;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v9);
  return v3;
}

```

## disassembly

```asm
0x18006361c  mov     [rsp-8+arg_0], rbx
0x180063621  push    rbp
0x180063622  lea     rbp, [rsp-970h]
0x18006362a  sub     rsp, 0A70h
0x180063631  mov     rax, cs:__security_cookie
0x180063638  xor     rax, rsp
0x18006363b  mov     [rbp+970h+var_10], rax
0x180063642  xor     ebx, ebx
0x180063644  mov     [rsp+0A70h+cbSid], 100h
0x18006364c  xor     edx, edx; Val
0x18006364e  mov     [rsp+0A70h+IsMember], ebx
0x180063652  mov     r8d, 7FCh; Size
0x180063658  mov     [rsp+0A70h+var_A2C], ebx
0x18006365c  lea     rcx, [rbp+970h+var_8DC]; void *
0x180063663  mov     [rbp+970h+var_8E0], ebx
0x180063669  mov     [rsp+0A70h+var_A28], 64h ; 'd'
0x180063671  call    memset_0
0x180063676  cmp     qword ptr cs:xmmword_1800AAC20+8, rbx
0x18006367d  xorps   xmm0, xmm0
0x180063680  xorps   xmm1, xmm1
0x180063683  mov     [rsp+0A70h+var_A20], rbx
0x180063688  movdqu  [rsp+0A70h+var_A18], xmm0
0x18006368e  mov     [rsp+0A70h+var_9F8], rbx
0x180063693  movdqu  [rsp+0A70h+var_A08], xmm1
0x180063699  mov     [rbp+970h+var_9F0], 0FFFFFFFFh
0x1800636a0  mov     [rbp+970h+var_9EC], ebx
0x1800636a3  jz      short loc_1800636C0
0x1800636a5  lea     r9, VpnIkeRpcTraceFunction; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x1800636ac  xor     r8d, r8d; unsigned int *
0x1800636af  lea     rdx, aIsrpcclientike; "IsRPCClientIKEEXTService"
0x1800636b6  lea     rcx, [rsp+0A70h+var_A20]; this
0x1800636bb  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x1800636c0  xor     ecx, ecx; BindingHandle
0x1800636c2  call    cs:__imp_RpcImpersonateClient
0x1800636c8  test    eax, eax
0x1800636ca  jz      short loc_18006371C
0x1800636cc  cmp     qword ptr cs:xmmword_1800AAC20, rbx
0x1800636d3  jz      loc_18006381C
0x1800636d9  mov     r8d, eax
0x1800636dc  mov     word ptr [rbp+970h+var_8E0], bx
0x1800636e3  lea     rdx, aRpcimpersonate; "RpcImpersonateClient failed: %d"
0x1800636ea  lea     rcx, [rbp+970h+var_8E0]
0x1800636f1  call    FormatRRASErrorString
0x1800636f6  mov     rdx, qword ptr cs:xmmword_1800AAC20
0x1800636fd  lea     r8, [rbp+970h+var_8E0]
0x180063704  mov     rcx, cs:?gVpnIkeRpcEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gVpnIkeRpcEtwContext
0x18006370b  mov     rax, cs:?gVpnIkeRpcTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gVpnIkeRpcTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180063712  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063717  jmp     loc_18006381C
0x18006371c  lea     rax, [rsp+0A70h+var_A2C]
0x180063721  xor     ecx, ecx; lpSystemName
0x180063723  mov     [rsp+0A70h+peUse], rax; peUse
0x180063728  lea     r9, [rsp+0A70h+cbSid]; cbSid
0x18006372d  lea     rax, [rsp+0A70h+var_A28]
0x180063732  mov     [rsp+0A70h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180063737  lea     r8, [rbp+970h+Sid]; Sid
0x18006373b  lea     rax, [rbp+970h+var_E0]
0x180063742  lea     rdx, AccountName; "NT SERVICE\\IKEEXT"
0x180063749  mov     [rsp+0A70h+ReferencedDomainName], rax; ReferencedDomainName
0x18006374e  call    cs:__imp_LookupAccountNameW
0x180063754  test    eax, eax
0x180063756  jz      short loc_1800637C9
0x180063758  lea     r8, [rsp+0A70h+IsMember]; IsMember
0x18006375d  mov     rcx, 0FFFFFFFFFFFFFFFBh; TokenHandle
0x180063764  lea     rdx, [rbp+970h+Sid]; SidToCheck
0x180063768  call    cs:__imp_CheckTokenMembership
0x18006376e  test    eax, eax
0x180063770  jnz     loc_180063816
0x180063776  call    cs:__imp_GetLastError
0x18006377c  cmp     qword ptr cs:xmmword_1800AAC20, rbx
0x180063783  jz      short loc_1800637C3
0x180063785  mov     r8d, eax
0x180063788  mov     word ptr [rbp+970h+var_8E0], bx
0x18006378f  lea     rdx, aChecktokenmemb; "CheckTokenMembership failed: %d"
0x180063796  lea     rcx, [rbp+970h+var_8E0]
0x18006379d  call    FormatRRASErrorString
0x1800637a2  mov     rdx, qword ptr cs:xmmword_1800AAC20
0x1800637a9  lea     r8, [rbp+970h+var_8E0]
0x1800637b0  mov     rcx, cs:?gVpnIkeRpcEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gVpnIkeRpcEtwContext
0x1800637b7  mov     rax, cs:?gVpnIkeRpcTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gVpnIkeRpcTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800637be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800637c3  mov     [rsp+0A70h+IsMember], ebx
0x1800637c7  jmp     short loc_180063816
0x1800637c9  call    cs:__imp_GetLastError
0x1800637cf  cmp     qword ptr cs:xmmword_1800AAC20, rbx
0x1800637d6  jz      short loc_180063816
0x1800637d8  mov     r8d, eax
0x1800637db  mov     word ptr [rbp+970h+var_8E0], bx
0x1800637e2  lea     rdx, aLookupaccountn; "LookupAccountName failed: %d"
0x1800637e9  lea     rcx, [rbp+970h+var_8E0]
0x1800637f0  call    FormatRRASErrorString
0x1800637f5  mov     rdx, qword ptr cs:xmmword_1800AAC20
0x1800637fc  lea     r8, [rbp+970h+var_8E0]
0x180063803  mov     rcx, cs:?gVpnIkeRpcEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gVpnIkeRpcEtwContext
0x18006380a  mov     rax, cs:?gVpnIkeRpcTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gVpnIkeRpcTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180063811  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063816  call    cs:__imp_RpcRevertToSelf
0x18006381c  cmp     qword ptr cs:xmmword_1800AAC20+8, rbx
0x180063823  jz      short loc_180063865
0x180063825  mov     r8d, [rsp+0A70h+IsMember]
0x18006382a  lea     rdx, aIsrpcclientike_0; "IsRPCClientIKEEXTService returns: %d"
0x180063831  lea     rcx, [rbp+970h+var_8E0]
0x180063838  mov     word ptr [rbp+970h+var_8E0], bx
0x18006383f  call    FormatRRASErrorString
0x180063844  mov     rdx, qword ptr cs:xmmword_1800AAC20+8
0x18006384b  lea     r8, [rbp+970h+var_8E0]
0x180063852  mov     rcx, cs:?gVpnIkeRpcEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gVpnIkeRpcEtwContext
0x180063859  mov     rax, cs:?gVpnIkeRpcTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gVpnIkeRpcTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180063860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063865  mov     ebx, [rsp+0A70h+IsMember]
0x180063869  lea     rcx, [rsp+0A70h+var_A20]; this
0x18006386e  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180063873  mov     eax, ebx
0x180063875  mov     rcx, [rbp+970h+var_10]
0x18006387c  xor     rcx, rsp; StackCookie
0x18006387f  call    __security_check_cookie
0x180063884  mov     rbx, [rsp+0A70h+arg_0]
0x18006388c  add     rsp, 0A70h
0x180063893  pop     rbp
0x180063894  retn
```
