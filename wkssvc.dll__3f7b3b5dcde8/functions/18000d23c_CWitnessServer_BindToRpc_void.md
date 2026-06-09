# CWitnessServer::BindToRpc(void)

- ea: `0x18000d23c`
- end: `0x18000d4f8`
- name: `?BindToRpc@CWitnessServer@@QEAAKXZ`
- size: `700`
- prototype: `__int64 __fastcall(LPCWSTR ServiceName)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d610`

## callees

- `0x18000b76c`
- `0x18000d23c`
- `0x18000dd68`
- `0x18001c6dc`
- `0x18001e420`
- `0x180022b54`

## import_xrefs

- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18000d4a1`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18000d4a1`
- `RPCRT4!RpcEpResolveBinding` at `0x18000d374`
- `RPCRT4!RpcEpResolveBinding` at `0x18000d374`
- `RPCRT4!RpcStringFreeW` at `0x18000d4bb`
- `RPCRT4!RpcStringFreeW` at `0x18000d4bb`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000d329`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000d329`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000d312`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000d312`
- `RPCRT4!RpcBindingSetOption` at `0x18000d35a`
- `RPCRT4!RpcBindingSetOption` at `0x18000d35a`
- `RPCRT4!RpcMgmtSetComTimeout` at `0x18000d33e`
- `RPCRT4!RpcMgmtSetComTimeout` at `0x18000d33e`
- `DSPARSE!DsMakeSpnW` at `0x18000d3d2`
- `DSPARSE!DsMakeSpnW` at `0x18000d440`
- `DSPARSE!DsMakeSpnW` at `0x18000d3d2`
- `DSPARSE!DsMakeSpnW` at `0x18000d440`

## pseudocode

```c
__int64 __fastcall CWitnessServer::BindToRpc(LPCWSTR ServiceName)
{
  LPCWSTR v1; // rdi
  WCHAR *pszSpn; // r15
  unsigned int v3; // r13d
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  RPC_BINDING_HANDLE *v6; // r14
  DWORD SpnW; // ebx
  LPCWSTR v8; // rsi
  const WCHAR *v9; // rdx
  DWORD pcSpnLength; // [rsp+40h] [rbp-38h] BYREF
  RPC_WSTR String; // [rsp+48h] [rbp-30h] BYREF
  RPC_SECURITY_QOS SecurityQOS; // [rsp+50h] [rbp-28h] BYREF

  SecurityQOS.ImpersonationType = 3;
  v1 = ServiceName;
  String = 0;
  pszSpn = 0;
  pcSpnLength = 0;
  SecurityQOS.Version = 1;
  *(_QWORD *)&SecurityQOS.Capabilities = 1;
  if ( (ServiceName[56] & 1) != 0 )
  {
    v3 = 6;
    v4 = WPP_witness_GLOBAL_Control;
    if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
      && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) >= 3u )
    {
      v5 = 16;
LABEL_10:
      WPP_SF_(v4[2], v5, WPP_7115a9cd1c5631a724b7ecc4a30ddb5a_Traceguids);
    }
  }
  else
  {
    v3 = 5;
    v4 = WPP_witness_GLOBAL_Control;
    if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
      && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) >= 3u )
    {
      v5 = 17;
      goto LABEL_10;
    }
  }
  v6 = (RPC_BINDING_HANDLE *)(v1 + 48);
  if ( *((_QWORD *)v1 + 12) )
  {
    SpnW = 183;
  }
  else
  {
    SpnW = RpcStringBindingComposeW(
             (RPC_WSTR)L"ccd8c074-d0e5-4a40-92b4-d074faa6ba28",
             (RPC_WSTR)L"ncacn_ip_tcp",
             (RPC_WSTR)v1 + 60,
             0,
             0,
             &String);
    if ( !SpnW )
    {
      SpnW = RpcBindingFromStringBindingW(String, (RPC_BINDING_HANDLE *)v1 + 12);
      if ( !SpnW )
      {
        SpnW = RpcMgmtSetComTimeout(*v6, 0);
        if ( !SpnW )
        {
          SpnW = RpcBindingSetOption(*v6, 0xCu, 0x7530u);
          if ( !SpnW )
          {
            SpnW = RpcEpResolveBinding(*v6, qword_180035060);
            if ( !SpnW )
            {
              if ( (v1[58] & 2) != 0 )
              {
                v8 = v1 + 16;
                v9 = *((_QWORD *)v1 + 7) <= 7u ? v1 + 16 : *(const WCHAR **)v8;
              }
              else
              {
                v9 = *((_QWORD *)v1 + 3) <= 7u ? v1 : *(const WCHAR **)v1;
                v8 = v1 + 16;
              }
              SpnW = DsMakeSpnW(L"CIFS", v9, 0, 0, 0, &pcSpnLength, 0);
              if ( SpnW == 111 )
              {
                pszSpn = (WCHAR *)MemoryAlloc(2LL * pcSpnLength);
                if ( pszSpn )
                {
                  if ( (v1[58] & 2) != 0 )
                  {
                    if ( *((_QWORD *)v8 + 3) > 7u )
                      v8 = *(LPCWSTR *)v8;
                  }
                  else
                  {
                    if ( *((_QWORD *)v1 + 3) > 7u )
                      v1 = *(LPCWSTR *)v1;
                    v8 = v1;
                  }
                  SpnW = DsMakeSpnW(L"CIFS", v8, 0, 0, 0, &pcSpnLength, pszSpn);
                  if ( !SpnW )
                  {
                    if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
                      && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
                      && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) >= 3u )
                    {
                      WPP_SF_S(
                        *((_QWORD *)WPP_witness_GLOBAL_Control + 2),
                        18,
                        WPP_7115a9cd1c5631a724b7ecc4a30ddb5a_Traceguids,
                        pszSpn);
                    }
                    SpnW = RpcBindingSetAuthInfoExW(*v6, pszSpn, v3, 9u, 0, 0xFFFFFFFF, &SecurityQOS);
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
    }
  }
  if ( String )
    RpcStringFreeW(&String);
  if ( pszSpn )
    MemoryFree(pszSpn);
  if ( SpnW )
    *v6 = 0;
  return SpnW;
}

```

## disassembly

```asm
0x18000d23c  push    rbp
0x18000d23e  push    rbx
0x18000d23f  push    rsi
0x18000d240  push    rdi
0x18000d241  push    r12
0x18000d243  push    r13
0x18000d245  push    r14
0x18000d247  push    r15
0x18000d249  mov     rbp, rsp
0x18000d24c  sub     rsp, 78h
0x18000d250  mov     rax, cs:__security_cookie
0x18000d257  xor     rax, rsp
0x18000d25a  mov     [rbp+var_18], rax
0x18000d25e  xor     esi, esi
0x18000d260  mov     [rbp+SecurityQOS.ImpersonationType], 3
0x18000d267  mov     rdi, rcx
0x18000d26a  mov     [rbp+String], rsi
0x18000d26e  mov     r15d, esi
0x18000d271  mov     [rbp+pcSpnLength], esi
0x18000d274  lea     eax, [rsi+1]
0x18000d277  mov     [rbp+SecurityQOS.Version], eax
0x18000d27a  mov     qword ptr [rbp+SecurityQOS.Capabilities], rax
0x18000d27e  test    [rcx+70h], al
0x18000d281  jz      short loc_18000D2AA
0x18000d283  lea     r13d, [rsi+6]
0x18000d287  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000d28e  lea     r12, WPP_witness_GLOBAL_Control
0x18000d295  cmp     rcx, r12
0x18000d298  jz      short loc_18000D2E2
0x18000d29a  test    [rcx+1Ch], al
0x18000d29d  jz      short loc_18000D2E2
0x18000d29f  cmp     byte ptr [rcx+19h], 3
0x18000d2a3  jb      short loc_18000D2E2
0x18000d2a5  lea     edx, [rsi+10h]
0x18000d2a8  jmp     short loc_18000D2D2
0x18000d2aa  mov     r13d, 5
0x18000d2b0  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000d2b7  lea     r12, WPP_witness_GLOBAL_Control
0x18000d2be  cmp     rcx, r12
0x18000d2c1  jz      short loc_18000D2E2
0x18000d2c3  test    [rcx+1Ch], al
0x18000d2c6  jz      short loc_18000D2E2
0x18000d2c8  cmp     byte ptr [rcx+19h], 3
0x18000d2cc  jb      short loc_18000D2E2
0x18000d2ce  lea     edx, [r13+0Ch]
0x18000d2d2  mov     rcx, [rcx+10h]
0x18000d2d6  lea     r8, WPP_7115a9cd1c5631a724b7ecc4a30ddb5a_Traceguids
0x18000d2dd  call    WPP_SF_
0x18000d2e2  lea     r14, [rdi+60h]
0x18000d2e6  cmp     [r14], rsi
0x18000d2e9  jnz     loc_18000D4AB
0x18000d2ef  lea     rax, [rbp+String]
0x18000d2f3  xor     r9d, r9d; Endpoint
0x18000d2f6  mov     [rsp+78h+StringBinding], rax; StringBinding
0x18000d2fb  lea     r8, [rdi+78h]; NetworkAddr
0x18000d2ff  lea     rdx, ProtSeq; "ncacn_ip_tcp"
0x18000d306  mov     [rsp+78h+Options], rsi; Options
0x18000d30b  lea     rcx, ObjUuid; "ccd8c074-d0e5-4a40-92b4-d074faa6ba28"
0x18000d312  call    cs:__imp_RpcStringBindingComposeW
0x18000d318  mov     ebx, eax
0x18000d31a  test    eax, eax
0x18000d31c  jnz     loc_18000D4B0
0x18000d322  mov     rcx, [rbp+String]; StringBinding
0x18000d326  mov     rdx, r14; Binding
0x18000d329  call    cs:__imp_RpcBindingFromStringBindingW
0x18000d32f  mov     ebx, eax
0x18000d331  test    eax, eax
0x18000d333  jnz     loc_18000D4B0
0x18000d339  mov     rcx, [r14]; Binding
0x18000d33c  xor     edx, edx; Timeout
0x18000d33e  call    cs:__imp_RpcMgmtSetComTimeout
0x18000d344  mov     ebx, eax
0x18000d346  test    eax, eax
0x18000d348  jnz     loc_18000D4B0
0x18000d34e  mov     rcx, [r14]; hBinding
0x18000d351  lea     edx, [rax+0Ch]; option
0x18000d354  mov     r8d, 7530h; optionValue
0x18000d35a  call    cs:__imp_RpcBindingSetOption
0x18000d360  mov     ebx, eax
0x18000d362  test    eax, eax
0x18000d364  jnz     loc_18000D4B0
0x18000d36a  mov     rcx, [r14]; Binding
0x18000d36d  lea     rdx, qword_180035060; IfSpec
0x18000d374  call    cs:__imp_RpcEpResolveBinding
0x18000d37a  mov     ebx, eax
0x18000d37c  test    eax, eax
0x18000d37e  jnz     loc_18000D4B0
0x18000d384  test    byte ptr [rdi+74h], 2
0x18000d388  jz      short loc_18000D39F
0x18000d38a  lea     rsi, [rdi+20h]
0x18000d38e  cmp     qword ptr [rsi+18h], 7
0x18000d393  jbe     short loc_18000D39A
0x18000d395  mov     rdx, [rsi]
0x18000d398  jmp     short loc_18000D3B2
0x18000d39a  mov     rdx, rsi
0x18000d39d  jmp     short loc_18000D3B2
0x18000d39f  cmp     qword ptr [rdi+18h], 7
0x18000d3a4  jbe     short loc_18000D3AB
0x18000d3a6  mov     rdx, [rdi]
0x18000d3a9  jmp     short loc_18000D3AE
0x18000d3ab  mov     rdx, rdi; ServiceName
0x18000d3ae  lea     rsi, [rdi+20h]
0x18000d3b2  xor     r9d, r9d; InstancePort
0x18000d3b5  lea     rax, [rbp+pcSpnLength]
0x18000d3b9  mov     [rsp+78h+pszSpn], r9; pszSpn
0x18000d3be  lea     rcx, ServiceClass; "CIFS"
0x18000d3c5  mov     [rsp+78h+StringBinding], rax; pcSpnLength
0x18000d3ca  xor     r8d, r8d; InstanceName
0x18000d3cd  mov     [rsp+78h+Options], r9; Referrer
0x18000d3d2  call    cs:__imp_DsMakeSpnW
0x18000d3d8  mov     ebx, eax
0x18000d3da  cmp     eax, 6Fh ; 'o'
0x18000d3dd  jnz     loc_18000D4B0
0x18000d3e3  mov     ecx, [rbp+pcSpnLength]
0x18000d3e6  add     rcx, rcx; unsigned __int64
0x18000d3e9  call    ?MemoryAlloc@@YAPEAX_K@Z; MemoryAlloc(unsigned __int64)
0x18000d3ee  mov     r15, rax
0x18000d3f1  test    rax, rax
0x18000d3f4  jnz     short loc_18000D3FE
0x18000d3f6  lea     ebx, [rax+0Eh]
0x18000d3f9  jmp     loc_18000D4B0
0x18000d3fe  test    byte ptr [rdi+74h], 2
0x18000d402  jz      short loc_18000D410
0x18000d404  cmp     qword ptr [rsi+18h], 7
0x18000d409  jbe     short loc_18000D41D
0x18000d40b  mov     rsi, [rsi]
0x18000d40e  jmp     short loc_18000D41D
0x18000d410  cmp     qword ptr [rdi+18h], 7
0x18000d415  jbe     short loc_18000D41A
0x18000d417  mov     rdi, [rdi]
0x18000d41a  mov     rsi, rdi
0x18000d41d  lea     rax, [rbp+pcSpnLength]
0x18000d421  mov     [rsp+78h+pszSpn], r15; pszSpn
0x18000d426  xor     r9d, r9d; InstancePort
0x18000d429  mov     [rsp+78h+StringBinding], rax; pcSpnLength
0x18000d42e  xor     r8d, r8d; InstanceName
0x18000d431  mov     [rsp+78h+Options], r9; Referrer
0x18000d436  mov     rdx, rsi; ServiceName
0x18000d439  lea     rcx, ServiceClass; "CIFS"
0x18000d440  call    cs:__imp_DsMakeSpnW
0x18000d446  xor     esi, esi
0x18000d448  mov     ebx, eax
0x18000d44a  test    eax, eax
0x18000d44c  jnz     short loc_18000D4B0
0x18000d44e  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000d455  cmp     rcx, r12
0x18000d458  jz      short loc_18000D47C
0x18000d45a  test    byte ptr [rcx+1Ch], 1
0x18000d45e  jz      short loc_18000D47C
0x18000d460  cmp     byte ptr [rcx+19h], 3
0x18000d464  jb      short loc_18000D47C
0x18000d466  mov     rcx, [rcx+10h]
0x18000d46a  lea     edx, [rax+12h]
0x18000d46d  mov     r9, r15
0x18000d470  lea     r8, WPP_7115a9cd1c5631a724b7ecc4a30ddb5a_Traceguids
0x18000d477  call    WPP_SF_S
0x18000d47c  mov     rcx, [r14]; Binding
0x18000d47f  lea     rax, [rbp+SecurityQOS]
0x18000d483  mov     [rsp+78h+pszSpn], rax; SecurityQOS
0x18000d488  mov     r9d, 9; AuthnSvc
0x18000d48e  mov     dword ptr [rsp+78h+StringBinding], 0FFFFFFFFh; AuthzSvc
0x18000d496  mov     r8d, r13d; AuthnLevel
0x18000d499  mov     rdx, r15; ServerPrincName
0x18000d49c  mov     [rsp+78h+Options], rsi; AuthIdentity
0x18000d4a1  call    cs:__imp_RpcBindingSetAuthInfoExW
0x18000d4a7  mov     ebx, eax
0x18000d4a9  jmp     short loc_18000D4B0
0x18000d4ab  mov     ebx, 0B7h
0x18000d4b0  cmp     [rbp+String], 0
0x18000d4b5  jz      short loc_18000D4C1
0x18000d4b7  lea     rcx, [rbp+String]; String
0x18000d4bb  call    cs:__imp_RpcStringFreeW
0x18000d4c1  test    r15, r15
0x18000d4c4  jz      short loc_18000D4CE
0x18000d4c6  mov     rcx, r15; void *
0x18000d4c9  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18000d4ce  test    ebx, ebx
0x18000d4d0  jz      short loc_18000D4D9
0x18000d4d2  mov     qword ptr [r14], 0
0x18000d4d9  mov     eax, ebx
0x18000d4db  mov     rcx, [rbp+var_18]
0x18000d4df  xor     rcx, rsp; StackCookie
0x18000d4e2  call    __security_check_cookie
0x18000d4e7  add     rsp, 78h
0x18000d4eb  pop     r15
0x18000d4ed  pop     r14
0x18000d4ef  pop     r13
0x18000d4f1  pop     r12
0x18000d4f3  pop     rdi
0x18000d4f4  pop     rsi
0x18000d4f5  pop     rbx
0x18000d4f6  pop     rbp
0x18000d4f7  retn
```
