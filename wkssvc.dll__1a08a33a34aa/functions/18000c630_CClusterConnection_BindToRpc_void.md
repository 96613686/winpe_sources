# CClusterConnection::BindToRpc(void)

- ea: `0x18000c630`
- end: `0x18000c972`
- name: `?BindToRpc@CClusterConnection@@AEAAJXZ`
- size: `834`
- prototype: `__int64 __fastcall(CClusterConnection *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001e720`

## callees

- `0x18000c1b4`
- `0x18000c630`
- `0x18000ea98`
- `0x180010b90`
- `0x18001dcac`
- `0x18001fbd0`
- `0x180035490`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000c81d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000c86a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000c81d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000c86a`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18000c94c`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18000c94c`
- `RPCRT4!RpcEpResolveBinding` at `0x18000c722`
- `RPCRT4!RpcEpResolveBinding` at `0x18000c722`
- `RPCRT4!RpcStringFreeW` at `0x18000c7a6`
- `RPCRT4!RpcStringFreeW` at `0x18000c7a6`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000c6e5`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000c6e5`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000c6c0`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000c6c0`
- `RPCRT4!RpcMgmtSetComTimeout` at `0x18000c701`
- `RPCRT4!RpcMgmtSetComTimeout` at `0x18000c701`
- `DSPARSE!DsMakeSpnW` at `0x18000c767`
- `DSPARSE!DsMakeSpnW` at `0x18000c8d2`
- `DSPARSE!DsMakeSpnW` at `0x18000c767`
- `DSPARSE!DsMakeSpnW` at `0x18000c8d2`

## pseudocode

```c
__int64 __fastcall CClusterConnection::BindToRpc(CClusterConnection *this)
{
  int v1; // r13d
  char *v2; // r14
  WCHAR *pszSpn; // r15
  bool v4; // cc
  unsigned __int16 *v6; // r8
  DWORD SpnW; // ebx
  int v8; // r8d
  const WCHAR *v9; // rsi
  const WCHAR *v10; // rdx
  PVOID v11; // rcx
  _QWORD *v12; // r9
  __int64 v13; // rsi
  ULONGLONG TickCount64; // rax
  int v16; // r13d
  DWORD pcSpnLength; // [rsp+40h] [rbp-30h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+48h] [rbp-28h] BYREF
  RPC_WSTR String; // [rsp+50h] [rbp-20h] BYREF
  RPC_SECURITY_QOS SecurityQOS; // [rsp+58h] [rbp-18h] BYREF

  v1 = *((_DWORD *)this + 112);
  v2 = (char *)this + 88;
  pszSpn = 0;
  Binding = 0;
  v4 = *((_QWORD *)this + 14) <= 7u;
  String = 0;
  SecurityQOS.Version = 1;
  *(_QWORD *)&SecurityQOS.Capabilities = 1;
  SecurityQOS.ImpersonationType = 3;
  pcSpnLength = 0;
  if ( v4 )
    v6 = (unsigned __int16 *)((char *)this + 88);
  else
    v6 = *(unsigned __int16 **)v2;
  SpnW = RpcStringBindingComposeW(
           (RPC_WSTR)L"ccd8c074-d0e5-4a40-92b4-d074faa6ba28",
           (RPC_WSTR)L"ncacn_ip_tcp",
           v6,
           0,
           0,
           &String);
  if ( !SpnW )
  {
    SpnW = RpcBindingFromStringBindingW(String, &Binding);
    if ( !SpnW )
    {
      SpnW = RpcMgmtSetComTimeout(Binding, 0);
      if ( !SpnW )
      {
        SpnW = RpcEpResolveBinding(Binding, qword_180038060);
        if ( !SpnW )
        {
          v9 = (const WCHAR *)((char *)this + 24);
          v10 = *((_QWORD *)this + 6) <= 7u ? (const WCHAR *)((char *)this + 24) : *(const WCHAR **)v9;
          SpnW = DsMakeSpnW(L"CIFS", v10, 0, 0, 0, &pcSpnLength, 0);
          if ( SpnW == 111 )
          {
            pszSpn = (WCHAR *)MemoryAlloc(2LL * pcSpnLength);
            if ( pszSpn )
            {
              if ( *((_QWORD *)this + 6) > 7u )
                v9 = *(const WCHAR **)v9;
              SpnW = DsMakeSpnW(L"CIFS", v9, 0, 0, 0, &pcSpnLength, pszSpn);
              if ( !SpnW )
              {
                v16 = v1 & 1;
                if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
                  && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) >= 3u )
                {
                  WPP_SF_S(
                    *((_QWORD *)WPP_witness_GLOBAL_Control + 2),
                    17,
                    &WPP_05a199c97cb13ffb21b1b8c24cf946fe_Traceguids,
                    pszSpn);
                }
                SpnW = RpcBindingSetAuthInfoExW(Binding, pszSpn, v16 + 5, 9u, 0, 0xFFFFFFFF, &SecurityQOS);
                if ( !SpnW )
                  *((_QWORD *)this + 34) = Binding;
              }
            }
            else
            {
              SpnW = 14;
            }
          }
        }
      }
    }
  }
  if ( String )
    RpcStringFreeW(&String);
  if ( pszSpn )
    MemoryFree(pszSpn);
  v11 = WPP_witness_GLOBAL_Control;
  if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
    && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) >= 3u )
  {
    v12 = (_QWORD *)((char *)this + 24);
    if ( *((_QWORD *)this + 6) > 7u )
      v12 = (_QWORD *)*v12;
    WPP_SF_Sdq(*((_QWORD *)WPP_witness_GLOBAL_Control + 2), 18, v8, (_DWORD)v12, SpnW, (char)this);
  }
  if ( SpnW )
  {
    if ( *((_DWORD *)this + 118) != 1
      || *((_DWORD *)this + 119) != SpnW
      || (v13 = *((_QWORD *)this + 60)) == 0
      || (TickCount64 = GetTickCount64(), v11 = (PVOID)(v13 + 43200000), TickCount64 > v13 + 43200000) )
    {
      if ( (Microsoft_Windows_SMBWitnessClientEnableBits & 1) != 0 )
      {
        if ( *((_QWORD *)v2 + 3) > 7u )
          v2 = *(char **)v2;
        McTemplateU0zq_EventWriteTransfer(v11, "*", v2, SpnW);
      }
      *((_DWORD *)this + 118) = 1;
      *((_DWORD *)this + 119) = SpnW;
      *((_QWORD *)this + 60) = GetTickCount64();
    }
  }
  return SpnW;
}

```

## disassembly

```asm
0x18000c630  mov     [rsp-28h+arg_8], rbx
0x18000c635  mov     [rsp-28h+arg_10], rsi
0x18000c63a  push    rbp
0x18000c63b  push    rdi
0x18000c63c  push    r13
0x18000c63e  push    r14
0x18000c640  push    r15
0x18000c642  mov     rbp, rsp
0x18000c645  sub     rsp, 70h
0x18000c649  mov     rax, cs:__security_cookie
0x18000c650  xor     rax, rsp
0x18000c653  mov     [rbp+var_8], rax
0x18000c657  mov     r13d, [rcx+1C0h]
0x18000c65e  lea     r14, [rcx+58h]
0x18000c662  xor     r15d, r15d
0x18000c665  mov     [rbp+Binding], 0
0x18000c66d  cmp     qword ptr [r14+18h], 7
0x18000c672  mov     rdi, rcx
0x18000c675  mov     [rbp+String], 0
0x18000c67d  mov     [rbp+SecurityQOS.Version], 1
0x18000c684  mov     qword ptr [rbp+SecurityQOS.Capabilities], 1
0x18000c68c  mov     [rbp+SecurityQOS.ImpersonationType], 3
0x18000c693  mov     [rbp+pcSpnLength], r15d
0x18000c697  jbe     short loc_18000C69E
0x18000c699  mov     r8, [r14]
0x18000c69c  jmp     short loc_18000C6A1
0x18000c69e  mov     r8, r14; NetworkAddr
0x18000c6a1  lea     rax, [rbp+String]
0x18000c6a5  xor     r9d, r9d; Endpoint
0x18000c6a8  mov     [rsp+70h+StringBinding], rax; StringBinding
0x18000c6ad  lea     rdx, ProtSeq; "ncacn_ip_tcp"
0x18000c6b4  lea     rcx, ObjUuid; "ccd8c074-d0e5-4a40-92b4-d074faa6ba28"
0x18000c6bb  mov     [rsp+70h+Options], r15; Options
0x18000c6c0  call    cs:__imp_RpcStringBindingComposeW
0x18000c6c7  nop     dword ptr [rax+rax+00h]
0x18000c6cc  lea     rsi, WPP_witness_GLOBAL_Control
0x18000c6d3  mov     ebx, eax
0x18000c6d5  test    eax, eax
0x18000c6d7  jnz     loc_18000C79B
0x18000c6dd  mov     rcx, [rbp+String]; StringBinding
0x18000c6e1  lea     rdx, [rbp+Binding]; Binding
0x18000c6e5  call    cs:__imp_RpcBindingFromStringBindingW
0x18000c6ec  nop     dword ptr [rax+rax+00h]
0x18000c6f1  mov     ebx, eax
0x18000c6f3  test    eax, eax
0x18000c6f5  jnz     loc_18000C79B
0x18000c6fb  mov     rcx, [rbp+Binding]; Binding
0x18000c6ff  xor     edx, edx; Timeout
0x18000c701  call    cs:__imp_RpcMgmtSetComTimeout
0x18000c708  nop     dword ptr [rax+rax+00h]
0x18000c70d  mov     ebx, eax
0x18000c70f  test    eax, eax
0x18000c711  jnz     loc_18000C79B
0x18000c717  mov     rcx, [rbp+Binding]; Binding
0x18000c71b  lea     rdx, qword_180038060; IfSpec
0x18000c722  call    cs:__imp_RpcEpResolveBinding
0x18000c729  nop     dword ptr [rax+rax+00h]
0x18000c72e  mov     ebx, eax
0x18000c730  test    eax, eax
0x18000c732  jnz     short loc_18000C79B
0x18000c734  lea     rsi, [rdi+18h]
0x18000c738  cmp     qword ptr [rsi+18h], 7
0x18000c73d  jbe     short loc_18000C744
0x18000c73f  mov     rdx, [rsi]
0x18000c742  jmp     short loc_18000C747
0x18000c744  mov     rdx, rsi; ServiceName
0x18000c747  xor     r9d, r9d; InstancePort
0x18000c74a  lea     rax, [rbp+pcSpnLength]
0x18000c74e  mov     [rsp+70h+pszSpn], r9; pszSpn
0x18000c753  lea     rcx, ServiceClass; "CIFS"
0x18000c75a  mov     [rsp+70h+StringBinding], rax; pcSpnLength
0x18000c75f  xor     r8d, r8d; InstanceName
0x18000c762  mov     [rsp+70h+Options], r9; Referrer
0x18000c767  call    cs:__imp_DsMakeSpnW
0x18000c76e  nop     dword ptr [rax+rax+00h]
0x18000c773  mov     ebx, eax
0x18000c775  cmp     eax, 6Fh ; 'o'
0x18000c778  jnz     short loc_18000C794
0x18000c77a  mov     ecx, [rbp+pcSpnLength]
0x18000c77d  add     rcx, rcx; unsigned __int64
0x18000c780  call    ?MemoryAlloc@@YAPEAX_K@Z; MemoryAlloc(unsigned __int64)
0x18000c785  mov     r15, rax
0x18000c788  test    rax, rax
0x18000c78b  jnz     loc_18000C8A5
0x18000c791  lea     ebx, [rax+0Eh]
0x18000c794  lea     rsi, WPP_witness_GLOBAL_Control
0x18000c79b  cmp     [rbp+String], 0
0x18000c7a0  jz      short loc_18000C7B2
0x18000c7a2  lea     rcx, [rbp+String]; String
0x18000c7a6  call    cs:__imp_RpcStringFreeW
0x18000c7ad  nop     dword ptr [rax+rax+00h]
0x18000c7b2  test    r15, r15
0x18000c7b5  jz      short loc_18000C7BF
0x18000c7b7  mov     rcx, r15; void *
0x18000c7ba  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18000c7bf  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000c7c6  cmp     rcx, rsi
0x18000c7c9  jz      short loc_18000C7FC
0x18000c7cb  test    byte ptr [rcx+1Ch], 1
0x18000c7cf  jz      short loc_18000C7FC
0x18000c7d1  cmp     byte ptr [rcx+19h], 3
0x18000c7d5  jb      short loc_18000C7FC
0x18000c7d7  lea     r9, [rdi+18h]
0x18000c7db  cmp     qword ptr [r9+18h], 7
0x18000c7e0  jbe     short loc_18000C7E5
0x18000c7e2  mov     r9, [r9]
0x18000c7e5  mov     rcx, [rcx+10h]
0x18000c7e9  mov     edx, 12h
0x18000c7ee  mov     [rsp+70h+StringBinding], rdi
0x18000c7f3  mov     dword ptr [rsp+70h+Options], ebx
0x18000c7f7  call    WPP_SF_Sdq
0x18000c7fc  test    ebx, ebx
0x18000c7fe  jz      short loc_18000C87D
0x18000c800  cmp     dword ptr [rdi+1D8h], 1
0x18000c807  jnz     short loc_18000C835
0x18000c809  cmp     [rdi+1DCh], ebx
0x18000c80f  jnz     short loc_18000C835
0x18000c811  mov     rsi, [rdi+1E0h]
0x18000c818  test    rsi, rsi
0x18000c81b  jz      short loc_18000C835
0x18000c81d  call    cs:__imp_GetTickCount64
0x18000c824  nop     dword ptr [rax+rax+00h]
0x18000c829  lea     rcx, [rsi+2932E00h]
0x18000c830  cmp     rax, rcx
0x18000c833  jbe     short loc_18000C87D
0x18000c835  test    cs:Microsoft_Windows_SMBWitnessClientEnableBits, 1
0x18000c83c  jz      short loc_18000C85A
0x18000c83e  cmp     qword ptr [r14+18h], 7
0x18000c843  jbe     short loc_18000C848
0x18000c845  mov     r14, [r14]
0x18000c848  mov     r9d, ebx
0x18000c84b  lea     rdx, WitnessClientInitialRpcBindFailed; "*"
0x18000c852  mov     r8, r14
0x18000c855  call    McTemplateU0zq_EventWriteTransfer
0x18000c85a  mov     dword ptr [rdi+1D8h], 1
0x18000c864  mov     [rdi+1DCh], ebx
0x18000c86a  call    cs:__imp_GetTickCount64
0x18000c871  nop     dword ptr [rax+rax+00h]
0x18000c876  mov     [rdi+1E0h], rax
0x18000c87d  mov     eax, ebx
0x18000c87f  mov     rcx, [rbp+var_8]
0x18000c883  xor     rcx, rsp; StackCookie
0x18000c886  call    __security_check_cookie
0x18000c88b  lea     r11, [rsp+70h+var_s0]
0x18000c890  mov     rbx, [r11+38h]
0x18000c894  mov     rsi, [r11+40h]
0x18000c898  mov     rsp, r11
0x18000c89b  pop     r15
0x18000c89d  pop     r14
0x18000c89f  pop     r13
0x18000c8a1  pop     rdi
0x18000c8a2  pop     rbp
0x18000c8a3  retn
0x18000c8a5  cmp     qword ptr [rsi+18h], 7
0x18000c8aa  jbe     short loc_18000C8AF
0x18000c8ac  mov     rsi, [rsi]
0x18000c8af  lea     rax, [rbp+pcSpnLength]
0x18000c8b3  mov     [rsp+70h+pszSpn], r15; pszSpn
0x18000c8b8  xor     r9d, r9d; InstancePort
0x18000c8bb  mov     [rsp+70h+StringBinding], rax; pcSpnLength
0x18000c8c0  xor     r8d, r8d; InstanceName
0x18000c8c3  mov     [rsp+70h+Options], r9; Referrer
0x18000c8c8  mov     rdx, rsi; ServiceName
0x18000c8cb  lea     rcx, ServiceClass; "CIFS"
0x18000c8d2  call    cs:__imp_DsMakeSpnW
0x18000c8d9  nop     dword ptr [rax+rax+00h]
0x18000c8de  mov     ebx, eax
0x18000c8e0  test    eax, eax
0x18000c8e2  jnz     loc_18000C794
0x18000c8e8  and     r13d, 1
0x18000c8ec  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000c8f3  lea     rsi, WPP_witness_GLOBAL_Control
0x18000c8fa  cmp     rcx, rsi
0x18000c8fd  jz      short loc_18000C921
0x18000c8ff  test    byte ptr [rcx+1Ch], 1
0x18000c903  jz      short loc_18000C921
0x18000c905  cmp     byte ptr [rcx+19h], 3
0x18000c909  jb      short loc_18000C921
0x18000c90b  mov     rcx, [rcx+10h]
0x18000c90f  lea     edx, [rax+11h]
0x18000c912  mov     r9, r15
0x18000c915  lea     r8, WPP_05a199c97cb13ffb21b1b8c24cf946fe_Traceguids
0x18000c91c  call    WPP_SF_S
0x18000c921  mov     rcx, [rbp+Binding]; Binding
0x18000c925  lea     rax, [rbp+SecurityQOS]
0x18000c929  mov     [rsp+70h+pszSpn], rax; SecurityQOS
0x18000c92e  lea     r8d, [r13+5]; AuthnLevel
0x18000c932  mov     dword ptr [rsp+70h+StringBinding], 0FFFFFFFFh; AuthzSvc
0x18000c93a  mov     r9d, 9; AuthnSvc
0x18000c940  mov     rdx, r15; ServerPrincName
0x18000c943  mov     [rsp+70h+Options], 0; AuthIdentity
0x18000c94c  call    cs:__imp_RpcBindingSetAuthInfoExW
0x18000c953  nop     dword ptr [rax+rax+00h]
0x18000c958  mov     ebx, eax
0x18000c95a  test    eax, eax
0x18000c95c  jnz     loc_18000C79B
0x18000c962  mov     rax, [rbp+Binding]
0x18000c966  mov     [rdi+110h], rax
0x18000c96d  jmp     loc_18000C79B
```
