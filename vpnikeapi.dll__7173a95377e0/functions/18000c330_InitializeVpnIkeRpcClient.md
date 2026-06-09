# InitializeVpnIkeRpcClient

- ea: `0x18000c330`
- end: `0x18000c625`
- name: `InitializeVpnIkeRpcClient`
- size: `757`
- prototype: `__int64()`
- caller_count: `18`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800013c0`
- `0x180002b70`
- `0x180003620`
- `0x1800038d0`
- `0x180003b80`
- `0x180003e30`
- `0x180004110`
- `0x1800044a0`
- `0x180004780`
- `0x180004a20`
- `0x180004cd0`
- `0x180004f80`
- `0x1800052f0`
- `0x1800055b0`
- `0x180005880`
- `0x180005b30`
- `0x180005de0`
- `0x1800060c0`

## callees

- `0x180001670`
- `0x18000c330`
- `0x18000cd44`
- `0x18000ce1c`
- `0x18000cfbe`
- `0x18000cff0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c49f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c49f`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000c495`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000c495`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000c596`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000c596`
- `RPCRT4!RpcBindingSetOption` at `0x18000c542`
- `RPCRT4!RpcBindingSetOption` at `0x18000c542`
- `RPCRT4!RpcStringFreeA` at `0x18000c43a`
- `RPCRT4!RpcStringFreeA` at `0x18000c43a`
- `RPCRT4!RpcStringBindingComposeA` at `0x18000c3fc`
- `RPCRT4!RpcStringBindingComposeA` at `0x18000c3fc`
- `RPCRT4!RpcBindingFromStringBindingA` at `0x18000c42d`
- `RPCRT4!RpcBindingFromStringBindingA` at `0x18000c42d`
- `RPCRT4!RpcBindingFree` at `0x18000c5b4`
- `RPCRT4!RpcBindingFree` at `0x18000c5b4`
- `RPCRT4!RpcBindingSetAuthInfoExA` at `0x18000c515`
- `RPCRT4!RpcBindingSetAuthInfoExA` at `0x18000c515`

## string_xrefs

- `0x18000c3e2`: `Security=Impersonation Dynamic True`
- `0x18000c415`: `RpcStringBindingCompose Failed with error %d`
- `0x18000c4b4`: `AllocateAndInitializeSid Failed with error %d`

## pseudocode

```c
__int64 InitializeVpnIkeRpcClient()
{
  unsigned int v0; // ebx
  unsigned __int16 *v1; // rdx
  unsigned int *v2; // r8
  void (*v3)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  int v4; // edi
  DWORD LastError; // eax
  const wchar_t *v6; // rdx
  __int64 v7; // r8
  RPC_CSTR String; // [rsp+60h] [rbp-A0h] BYREF
  PSID pSid; // [rsp+68h] [rbp-98h] BYREF
  RPC_SECURITY_QOS SecurityQos; // [rsp+70h] [rbp-90h] BYREF
  __int128 v12; // [rsp+80h] [rbp-80h]
  __int128 v13; // [rsp+90h] [rbp-70h]
  __int64 v14; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v15; // [rsp+A8h] [rbp-58h]
  __int128 v16; // [rsp+B8h] [rbp-48h]
  __int64 v17; // [rsp+C8h] [rbp-38h]
  int v18; // [rsp+D0h] [rbp-30h]
  int v19; // [rsp+D4h] [rbp-2Ch]
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+D8h] [rbp-28h] BYREF
  int v21; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v22[2044]; // [rsp+E4h] [rbp-1Ch] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  pSid = 0;
  v21 = 0;
  v0 = 0;
  SecurityQos = 0;
  v12 = 0;
  v13 = 0;
  memset_0(v22, 0, sizeof(v22));
  v14 = 0;
  v15 = 0;
  v17 = 0;
  v16 = 0;
  v18 = -1;
  v19 = 0;
  if ( *((_QWORD *)&xmmword_180016840 + 1) )
    EtwFuncEntryExitTracer::Initialize((EtwFuncEntryExitTracer *)&v14, v1, v2, v3);
  if ( !Binding )
  {
    String = 0;
    v4 = 0;
    LastError = RpcStringBindingComposeA(
                  0,
                  (RPC_CSTR)"ncalrpc",
                  0,
                  (RPC_CSTR)"VpnikeRpc",
                  (RPC_CSTR)"Security=Impersonation Dynamic True",
                  &String);
    v0 = LastError;
    if ( LastError )
    {
      if ( (_QWORD)xmmword_180016840 )
      {
        v6 = L"RpcStringBindingCompose Failed with error %d";
LABEL_19:
        v7 = LastError;
        goto LABEL_20;
      }
    }
    else
    {
      v0 = RpcBindingFromStringBindingA(String, &Binding);
      RpcStringFreeA(&String);
      if ( v0 )
      {
        if ( (_QWORD)xmmword_180016840 )
        {
          v7 = v0;
          v6 = L"RpcBindingFromStringBinding Failed with error %d";
LABEL_20:
          LOWORD(v21) = 0;
          FormatRRASErrorString(&v21, v6, v7);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gVpnIkeRpcTemplateFunc)(
            gVpnIkeRpcEtwContext,
            xmmword_180016840,
            &v21);
        }
      }
      else
      {
        v4 = 1;
        if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
        {
          *(_QWORD *)&v13 = pSid;
          v12 = 0;
          *((_QWORD *)&v13 + 1) = 1;
          SecurityQos.Version = 4;
          SecurityQos.Capabilities = 17;
          SecurityQos.IdentityTracking = 1;
          SecurityQos.ImpersonationType = 3;
          LastError = RpcBindingSetAuthInfoExA(Binding, 0, 6u, 0xAu, 0, 0, &SecurityQos);
          v0 = LastError;
          if ( !LastError )
          {
            LastError = RpcBindingSetOption(Binding, 9u, 1u);
            v0 = LastError;
            if ( !LastError || !(_QWORD)xmmword_180016840 )
              goto LABEL_21;
            v6 = L"RpcBindingSetOption Failed with error %d";
            goto LABEL_19;
          }
          if ( (_QWORD)xmmword_180016840 )
          {
            v6 = L"RpcBindingSetAuthInfoExW Failed with error %d ";
            goto LABEL_19;
          }
        }
        else
        {
          LastError = GetLastError();
          v0 = LastError;
          if ( (_QWORD)xmmword_180016840 )
          {
            v6 = L"AllocateAndInitializeSid Failed with error %d";
            goto LABEL_19;
          }
        }
      }
    }
LABEL_21:
    if ( pSid )
      FreeSid(pSid);
    if ( v0 )
    {
      if ( v4 && Binding )
        RpcBindingFree(&Binding);
      Binding = 0;
    }
    if ( *((_QWORD *)&xmmword_180016840 + 1) )
    {
      LOWORD(v21) = 0;
      FormatRRASErrorString(&v21, L"VpnIkeRPCBindLocal returned: %d", v0);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gVpnIkeRpcTemplateFunc)(
        gVpnIkeRpcEtwContext,
        *((_QWORD *)&xmmword_180016840 + 1),
        &v21);
    }
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v14);
  return v0;
}

```

## disassembly

```asm
0x18000c330  push    rbp
0x18000c332  push    rbx
0x18000c333  push    rsi
0x18000c334  push    rdi
0x18000c335  lea     rbp, [rsp-7F8h]
0x18000c33d  sub     rsp, 8F8h
0x18000c344  mov     rax, cs:__security_cookie
0x18000c34b  xor     rax, rsp
0x18000c34e  mov     [rbp+810h+var_30], rax
0x18000c355  xor     esi, esi
0x18000c357  mov     word ptr [rbp+810h+pIdentifierAuthority.Value+4], 500h
0x18000c35d  xorps   xmm0, xmm0
0x18000c360  mov     dword ptr [rbp+810h+pIdentifierAuthority.Value], esi
0x18000c363  xor     edx, edx; Val
0x18000c365  mov     [rsp+910h+var_8A8], rsi
0x18000c36a  mov     r8d, 7FCh; Size
0x18000c370  mov     [rbp+810h+var_830], esi
0x18000c373  lea     rcx, [rbp+810h+var_82C]; void *
0x18000c377  mov     ebx, esi
0x18000c379  movups  xmmword ptr [rsp+910h+SecurityQos.Version], xmm0
0x18000c37e  movups  [rbp+810h+var_890], xmm0
0x18000c382  movups  [rbp+810h+var_880], xmm0
0x18000c386  call    memset_0
0x18000c38b  cmp     qword ptr cs:xmmword_180016840+8, rsi
0x18000c392  xorps   xmm0, xmm0
0x18000c395  xorps   xmm1, xmm1
0x18000c398  mov     [rbp+810h+var_870], rsi
0x18000c39c  movdqu  [rbp+810h+var_868], xmm0
0x18000c3a1  mov     [rbp+810h+var_848], rsi
0x18000c3a5  movdqu  [rbp+810h+var_858], xmm1
0x18000c3aa  mov     [rbp+810h+var_840], 0FFFFFFFFh
0x18000c3b1  mov     [rbp+810h+var_83C], esi
0x18000c3b4  jz      short loc_18000C3BF
0x18000c3b6  lea     rcx, [rbp+810h+var_870]; this
0x18000c3ba  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x18000c3bf  cmp     cs:Binding, rsi
0x18000c3c6  jnz     loc_18000C5FF
0x18000c3cc  lea     rax, [rsp+910h+String]
0x18000c3d1  mov     [rsp+910h+String], rsi
0x18000c3d6  mov     [rsp+910h+StringBinding], rax; StringBinding
0x18000c3db  lea     r9, Endpoint; "VpnikeRpc"
0x18000c3e2  lea     rax, Options; "Security=Impersonation Dynamic True"
0x18000c3e9  xor     r8d, r8d; NetworkAddr
0x18000c3ec  lea     rdx, ProtSeq; "ncalrpc"
0x18000c3f3  mov     [rsp+910h+Options], rax; Options
0x18000c3f8  xor     ecx, ecx; ObjUuid
0x18000c3fa  mov     edi, esi
0x18000c3fc  call    cs:__imp_RpcStringBindingComposeA
0x18000c402  mov     ebx, eax
0x18000c404  test    eax, eax
0x18000c406  jz      short loc_18000C421
0x18000c408  cmp     qword ptr cs:xmmword_180016840, rsi
0x18000c40f  jz      loc_18000C58C
0x18000c415  lea     rdx, aRpcstringbindi_0; "RpcStringBindingCompose Failed with err"...
0x18000c41c  jmp     loc_18000C55E
0x18000c421  mov     rcx, [rsp+910h+String]; StringBinding
0x18000c426  lea     rdx, Binding; Binding
0x18000c42d  call    cs:__imp_RpcBindingFromStringBindingA
0x18000c433  lea     rcx, [rsp+910h+String]; String
0x18000c438  mov     ebx, eax
0x18000c43a  call    cs:__imp_RpcStringFreeA
0x18000c440  test    ebx, ebx
0x18000c442  jz      short loc_18000C460
0x18000c444  cmp     qword ptr cs:xmmword_180016840, rsi
0x18000c44b  jz      loc_18000C58C
0x18000c451  mov     r8d, ebx
0x18000c454  lea     rdx, aRpcbindingfrom_0; "RpcBindingFromStringBinding Failed with"...
0x18000c45b  jmp     loc_18000C561
0x18000c460  mov     edi, 1
0x18000c465  lea     rax, [rsp+910h+var_8A8]
0x18000c46a  xor     r9d, r9d; nSubAuthority1
0x18000c46d  mov     [rsp+910h+pSid], rax; pSid
0x18000c472  lea     r8d, [rdi+11h]; nSubAuthority0
0x18000c476  mov     [rsp+910h+nSubAuthority7], esi; nSubAuthority7
0x18000c47a  lea     rcx, [rbp+810h+pIdentifierAuthority]; pIdentifierAuthority
0x18000c47e  mov     [rsp+910h+nSubAuthority6], esi; nSubAuthority6
0x18000c482  mov     dl, dil; nSubAuthorityCount
0x18000c485  mov     [rsp+910h+nSubAuthority5], esi; nSubAuthority5
0x18000c489  mov     [rsp+910h+nSubAuthority4], esi; nSubAuthority4
0x18000c48d  mov     dword ptr [rsp+910h+StringBinding], esi; nSubAuthority3
0x18000c491  mov     dword ptr [rsp+910h+Options], esi; nSubAuthority2
0x18000c495  call    cs:__imp_AllocateAndInitializeSid
0x18000c49b  test    eax, eax
0x18000c49d  jnz     short loc_18000C4C0
0x18000c49f  call    cs:__imp_GetLastError
0x18000c4a5  cmp     qword ptr cs:xmmword_180016840, rsi
0x18000c4ac  mov     ebx, eax
0x18000c4ae  jz      loc_18000C58C
0x18000c4b4  lea     rdx, aAllocateandini; "AllocateAndInitializeSid Failed with er"...
0x18000c4bb  jmp     loc_18000C55E
0x18000c4c0  mov     rax, [rsp+910h+var_8A8]
0x18000c4c5  xor     edx, edx; ServerPrincName
0x18000c4c7  mov     rcx, cs:Binding; Binding
0x18000c4ce  xorps   xmm0, xmm0
0x18000c4d1  mov     qword ptr [rbp+810h+var_880], rax
0x18000c4d5  lea     rax, [rsp+910h+SecurityQos]
0x18000c4da  mov     qword ptr [rsp+910h+nSubAuthority4], rax; SecurityQos
0x18000c4df  mov     dword ptr [rsp+910h+StringBinding], esi; AuthzSvc
0x18000c4e3  lea     r9d, [rdx+0Ah]; AuthnSvc
0x18000c4e7  lea     r8d, [rdx+6]; AuthnLevel
0x18000c4eb  mov     [rsp+910h+Options], rsi; AuthIdentity
0x18000c4f0  movdqu  [rbp+810h+var_890], xmm0
0x18000c4f5  mov     qword ptr [rbp+810h+var_880+8], rdi
0x18000c4f9  mov     [rsp+910h+SecurityQos.Version], 4
0x18000c501  mov     [rsp+910h+SecurityQos.Capabilities], 11h
0x18000c509  mov     [rsp+910h+SecurityQos.IdentityTracking], edi
0x18000c50d  mov     [rsp+910h+SecurityQos.ImpersonationType], 3
0x18000c515  call    cs:__imp_RpcBindingSetAuthInfoExA
0x18000c51b  mov     ebx, eax
0x18000c51d  test    eax, eax
0x18000c51f  jz      short loc_18000C533
0x18000c521  cmp     qword ptr cs:xmmword_180016840, rsi
0x18000c528  jz      short loc_18000C58C
0x18000c52a  lea     rdx, aRpcbindingseta_0; "RpcBindingSetAuthInfoExW Failed with er"...
0x18000c531  jmp     short loc_18000C55E
0x18000c533  mov     rcx, cs:Binding; hBinding
0x18000c53a  mov     r8, rdi; optionValue
0x18000c53d  mov     edx, 9; option
0x18000c542  call    cs:__imp_RpcBindingSetOption
0x18000c548  mov     ebx, eax
0x18000c54a  test    eax, eax
0x18000c54c  jz      short loc_18000C58C
0x18000c54e  cmp     qword ptr cs:xmmword_180016840, rsi
0x18000c555  jz      short loc_18000C58C
0x18000c557  lea     rdx, aRpcbindingseto_0; "RpcBindingSetOption Failed with error %"...
0x18000c55e  mov     r8d, eax
0x18000c561  lea     rcx, [rbp+810h+var_830]
0x18000c565  mov     word ptr [rbp+810h+var_830], si
0x18000c569  call    FormatRRASErrorString
0x18000c56e  mov     rdx, qword ptr cs:xmmword_180016840
0x18000c575  lea     r8, [rbp+810h+var_830]
0x18000c579  mov     rcx, cs:?gVpnIkeRpcEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gVpnIkeRpcEtwContext
0x18000c580  mov     rax, cs:?gVpnIkeRpcTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gVpnIkeRpcTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18000c587  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c58c  mov     rcx, [rsp+910h+var_8A8]; pSid
0x18000c591  test    rcx, rcx
0x18000c594  jz      short loc_18000C59C
0x18000c596  call    cs:__imp_FreeSid
0x18000c59c  test    ebx, ebx
0x18000c59e  jz      short loc_18000C5C1
0x18000c5a0  test    edi, edi
0x18000c5a2  jz      short loc_18000C5BA
0x18000c5a4  cmp     cs:Binding, rsi
0x18000c5ab  jz      short loc_18000C5BA
0x18000c5ad  lea     rcx, Binding; Binding
0x18000c5b4  call    cs:__imp_RpcBindingFree
0x18000c5ba  mov     cs:Binding, rsi
0x18000c5c1  cmp     qword ptr cs:xmmword_180016840+8, rsi
0x18000c5c8  jz      short loc_18000C5FF
0x18000c5ca  mov     r8d, ebx
0x18000c5cd  mov     word ptr [rbp+810h+var_830], si
0x18000c5d1  lea     rdx, aVpnikerpcbindl; "VpnIkeRPCBindLocal returned: %d"
0x18000c5d8  lea     rcx, [rbp+810h+var_830]
0x18000c5dc  call    FormatRRASErrorString
0x18000c5e1  mov     rdx, qword ptr cs:xmmword_180016840+8
0x18000c5e8  lea     r8, [rbp+810h+var_830]
0x18000c5ec  mov     rcx, cs:?gVpnIkeRpcEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gVpnIkeRpcEtwContext
0x18000c5f3  mov     rax, cs:?gVpnIkeRpcTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gVpnIkeRpcTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18000c5fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5ff  lea     rcx, [rbp+810h+var_870]; this
0x18000c603  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18000c608  mov     eax, ebx
0x18000c60a  mov     rcx, [rbp+810h+var_30]
0x18000c611  xor     rcx, rsp; StackCookie
0x18000c614  call    __security_check_cookie
0x18000c619  add     rsp, 8F8h
0x18000c620  pop     rdi
0x18000c621  pop     rsi
0x18000c622  pop     rbx
0x18000c623  pop     rbp
0x18000c624  retn
```
