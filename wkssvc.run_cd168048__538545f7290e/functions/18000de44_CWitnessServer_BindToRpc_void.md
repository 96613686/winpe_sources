# CWitnessServer::BindToRpc(void)

- ea: `0x18000de44`
- end: `0x18000e137`
- name: `?BindToRpc@CWitnessServer@@QEAAKXZ`
- size: `755`
- prototype: `unsigned int __fastcall(LPCWSTR ServiceName)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e25c`

## callees

- `0x18000c1b4`
- `0x18000de44`
- `0x18000ea98`
- `0x18001dcac`
- `0x18001fbd0`
- `0x180024520`

## import_xrefs

- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18000e0d3`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18000e0d3`
- `RPCRT4!RpcEpResolveBinding` at `0x18000df94`
- `RPCRT4!RpcEpResolveBinding` at `0x18000df94`
- `RPCRT4!RpcStringFreeW` at `0x18000e0f3`
- `RPCRT4!RpcStringFreeW` at `0x18000e0f3`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000df37`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000df37`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000df1a`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000df1a`
- `RPCRT4!RpcBindingSetOption` at `0x18000df74`
- `RPCRT4!RpcBindingSetOption` at `0x18000df74`
- `RPCRT4!RpcMgmtSetComTimeout` at `0x18000df52`
- `RPCRT4!RpcMgmtSetComTimeout` at `0x18000df52`
- `DSPARSE!DsMakeSpnW` at `0x18000dff8`
- `DSPARSE!DsMakeSpnW` at `0x18000e06c`
- `DSPARSE!DsMakeSpnW` at `0x18000dff8`
- `DSPARSE!DsMakeSpnW` at `0x18000e06c`

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
            SpnW = RpcEpResolveBinding(*v6, qword_180038060);
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
0x18000de44  push    rbp
0x18000de46  push    rbx
0x18000de47  push    rsi
0x18000de48  push    rdi
0x18000de49  push    r12
0x18000de4b  push    r13
0x18000de4d  push    r14
0x18000de4f  push    r15
0x18000de51  mov     rbp, rsp
0x18000de54  sub     rsp, 78h
0x18000de58  mov     rax, cs:__security_cookie
0x18000de5f  xor     rax, rsp
0x18000de62  mov     [rbp+var_18], rax
0x18000de66  xor     esi, esi
0x18000de68  mov     [rbp+SecurityQOS.ImpersonationType], 3
0x18000de6f  mov     rdi, rcx
0x18000de72  mov     [rbp+String], rsi
0x18000de76  mov     r15d, esi
0x18000de79  mov     [rbp+pcSpnLength], esi
0x18000de7c  lea     eax, [rsi+1]
0x18000de7f  mov     [rbp+SecurityQOS.Version], eax
0x18000de82  mov     qword ptr [rbp+SecurityQOS.Capabilities], rax
0x18000de86  test    [rcx+70h], al
0x18000de89  jz      short loc_18000DEB2
0x18000de8b  lea     r13d, [rsi+6]
0x18000de8f  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000de96  lea     r12, WPP_witness_GLOBAL_Control
0x18000de9d  cmp     rcx, r12
0x18000dea0  jz      short loc_18000DEEA
0x18000dea2  test    [rcx+1Ch], al
0x18000dea5  jz      short loc_18000DEEA
0x18000dea7  cmp     byte ptr [rcx+19h], 3
0x18000deab  jb      short loc_18000DEEA
0x18000dead  lea     edx, [rsi+10h]
0x18000deb0  jmp     short loc_18000DEDA
0x18000deb2  mov     r13d, 5
0x18000deb8  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000debf  lea     r12, WPP_witness_GLOBAL_Control
0x18000dec6  cmp     rcx, r12
0x18000dec9  jz      short loc_18000DEEA
0x18000decb  test    [rcx+1Ch], al
0x18000dece  jz      short loc_18000DEEA
0x18000ded0  cmp     byte ptr [rcx+19h], 3
0x18000ded4  jb      short loc_18000DEEA
0x18000ded6  lea     edx, [r13+0Ch]
0x18000deda  mov     rcx, [rcx+10h]
0x18000dede  lea     r8, WPP_7115a9cd1c5631a724b7ecc4a30ddb5a_Traceguids
0x18000dee5  call    WPP_SF_
0x18000deea  lea     r14, [rdi+60h]
0x18000deee  cmp     [r14], rsi
0x18000def1  jnz     loc_18000E0E3
0x18000def7  lea     rax, [rbp+String]
0x18000defb  xor     r9d, r9d; Endpoint
0x18000defe  mov     [rsp+78h+StringBinding], rax; StringBinding
0x18000df03  lea     r8, [rdi+78h]; NetworkAddr
0x18000df07  lea     rdx, ProtSeq; "ncacn_ip_tcp"
0x18000df0e  mov     [rsp+78h+Options], rsi; Options
0x18000df13  lea     rcx, ObjUuid; "ccd8c074-d0e5-4a40-92b4-d074faa6ba28"
0x18000df1a  call    cs:__imp_RpcStringBindingComposeW
0x18000df21  nop     dword ptr [rax+rax+00h]
0x18000df26  mov     ebx, eax
0x18000df28  test    eax, eax
0x18000df2a  jnz     loc_18000E0E8
0x18000df30  mov     rcx, [rbp+String]; StringBinding
0x18000df34  mov     rdx, r14; Binding
0x18000df37  call    cs:__imp_RpcBindingFromStringBindingW
0x18000df3e  nop     dword ptr [rax+rax+00h]
0x18000df43  mov     ebx, eax
0x18000df45  test    eax, eax
0x18000df47  jnz     loc_18000E0E8
0x18000df4d  mov     rcx, [r14]; Binding
0x18000df50  xor     edx, edx; Timeout
0x18000df52  call    cs:__imp_RpcMgmtSetComTimeout
0x18000df59  nop     dword ptr [rax+rax+00h]
0x18000df5e  mov     ebx, eax
0x18000df60  test    eax, eax
0x18000df62  jnz     loc_18000E0E8
0x18000df68  mov     rcx, [r14]; hBinding
0x18000df6b  lea     edx, [rax+0Ch]; option
0x18000df6e  mov     r8d, 7530h; optionValue
0x18000df74  call    cs:__imp_RpcBindingSetOption
0x18000df7b  nop     dword ptr [rax+rax+00h]
0x18000df80  mov     ebx, eax
0x18000df82  test    eax, eax
0x18000df84  jnz     loc_18000E0E8
0x18000df8a  mov     rcx, [r14]; Binding
0x18000df8d  lea     rdx, qword_180038060; IfSpec
0x18000df94  call    cs:__imp_RpcEpResolveBinding
0x18000df9b  nop     dword ptr [rax+rax+00h]
0x18000dfa0  mov     ebx, eax
0x18000dfa2  test    eax, eax
0x18000dfa4  jnz     loc_18000E0E8
0x18000dfaa  test    byte ptr [rdi+74h], 2
0x18000dfae  jz      short loc_18000DFC5
0x18000dfb0  lea     rsi, [rdi+20h]
0x18000dfb4  cmp     qword ptr [rsi+18h], 7
0x18000dfb9  jbe     short loc_18000DFC0
0x18000dfbb  mov     rdx, [rsi]
0x18000dfbe  jmp     short loc_18000DFD8
0x18000dfc0  mov     rdx, rsi
0x18000dfc3  jmp     short loc_18000DFD8
0x18000dfc5  cmp     qword ptr [rdi+18h], 7
0x18000dfca  jbe     short loc_18000DFD1
0x18000dfcc  mov     rdx, [rdi]
0x18000dfcf  jmp     short loc_18000DFD4
0x18000dfd1  mov     rdx, rdi; ServiceName
0x18000dfd4  lea     rsi, [rdi+20h]
0x18000dfd8  xor     r9d, r9d; InstancePort
0x18000dfdb  lea     rax, [rbp+pcSpnLength]
0x18000dfdf  mov     [rsp+78h+pszSpn], r9; pszSpn
0x18000dfe4  lea     rcx, ServiceClass; "CIFS"
0x18000dfeb  mov     [rsp+78h+StringBinding], rax; pcSpnLength
0x18000dff0  xor     r8d, r8d; InstanceName
0x18000dff3  mov     [rsp+78h+Options], r9; Referrer
0x18000dff8  call    cs:__imp_DsMakeSpnW
0x18000dfff  nop     dword ptr [rax+rax+00h]
0x18000e004  mov     ebx, eax
0x18000e006  cmp     eax, 6Fh ; 'o'
0x18000e009  jnz     loc_18000E0E8
0x18000e00f  mov     ecx, [rbp+pcSpnLength]
0x18000e012  add     rcx, rcx; unsigned __int64
0x18000e015  call    ?MemoryAlloc@@YAPEAX_K@Z; MemoryAlloc(unsigned __int64)
0x18000e01a  mov     r15, rax
0x18000e01d  test    rax, rax
0x18000e020  jnz     short loc_18000E02A
0x18000e022  lea     ebx, [rax+0Eh]
0x18000e025  jmp     loc_18000E0E8
0x18000e02a  test    byte ptr [rdi+74h], 2
0x18000e02e  jz      short loc_18000E03C
0x18000e030  cmp     qword ptr [rsi+18h], 7
0x18000e035  jbe     short loc_18000E049
0x18000e037  mov     rsi, [rsi]
0x18000e03a  jmp     short loc_18000E049
0x18000e03c  cmp     qword ptr [rdi+18h], 7
0x18000e041  jbe     short loc_18000E046
0x18000e043  mov     rdi, [rdi]
0x18000e046  mov     rsi, rdi
0x18000e049  lea     rax, [rbp+pcSpnLength]
0x18000e04d  mov     [rsp+78h+pszSpn], r15; pszSpn
0x18000e052  xor     r9d, r9d; InstancePort
0x18000e055  mov     [rsp+78h+StringBinding], rax; pcSpnLength
0x18000e05a  xor     r8d, r8d; InstanceName
0x18000e05d  mov     [rsp+78h+Options], r9; Referrer
0x18000e062  mov     rdx, rsi; ServiceName
0x18000e065  lea     rcx, ServiceClass; "CIFS"
0x18000e06c  call    cs:__imp_DsMakeSpnW
0x18000e073  nop     dword ptr [rax+rax+00h]
0x18000e078  xor     esi, esi
0x18000e07a  mov     ebx, eax
0x18000e07c  test    eax, eax
0x18000e07e  jnz     short loc_18000E0E8
0x18000e080  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000e087  cmp     rcx, r12
0x18000e08a  jz      short loc_18000E0AE
0x18000e08c  test    byte ptr [rcx+1Ch], 1
0x18000e090  jz      short loc_18000E0AE
0x18000e092  cmp     byte ptr [rcx+19h], 3
0x18000e096  jb      short loc_18000E0AE
0x18000e098  mov     rcx, [rcx+10h]
0x18000e09c  lea     edx, [rax+12h]
0x18000e09f  mov     r9, r15
0x18000e0a2  lea     r8, WPP_7115a9cd1c5631a724b7ecc4a30ddb5a_Traceguids
0x18000e0a9  call    WPP_SF_S
0x18000e0ae  mov     rcx, [r14]; Binding
0x18000e0b1  lea     rax, [rbp+SecurityQOS]
0x18000e0b5  mov     [rsp+78h+pszSpn], rax; SecurityQOS
0x18000e0ba  mov     r9d, 9; AuthnSvc
0x18000e0c0  mov     dword ptr [rsp+78h+StringBinding], 0FFFFFFFFh; AuthzSvc
0x18000e0c8  mov     r8d, r13d; AuthnLevel
0x18000e0cb  mov     rdx, r15; ServerPrincName
0x18000e0ce  mov     [rsp+78h+Options], rsi; AuthIdentity
0x18000e0d3  call    cs:__imp_RpcBindingSetAuthInfoExW
0x18000e0da  nop     dword ptr [rax+rax+00h]
0x18000e0df  mov     ebx, eax
0x18000e0e1  jmp     short loc_18000E0E8
0x18000e0e3  mov     ebx, 0B7h
0x18000e0e8  cmp     [rbp+String], 0
0x18000e0ed  jz      short loc_18000E0FF
0x18000e0ef  lea     rcx, [rbp+String]; String
0x18000e0f3  call    cs:__imp_RpcStringFreeW
0x18000e0fa  nop     dword ptr [rax+rax+00h]
0x18000e0ff  test    r15, r15
0x18000e102  jz      short loc_18000E10C
0x18000e104  mov     rcx, r15; void *
0x18000e107  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18000e10c  test    ebx, ebx
0x18000e10e  jz      short loc_18000E117
0x18000e110  mov     qword ptr [r14], 0
0x18000e117  mov     eax, ebx
0x18000e119  mov     rcx, [rbp+var_18]
0x18000e11d  xor     rcx, rsp; StackCookie
0x18000e120  call    __security_check_cookie
0x18000e125  add     rsp, 78h
0x18000e129  pop     r15
0x18000e12b  pop     r14
0x18000e12d  pop     r13
0x18000e12f  pop     r12
0x18000e131  pop     rdi
0x18000e132  pop     rsi
0x18000e133  pop     rbx
0x18000e134  pop     rbp
0x18000e135  retn
```
