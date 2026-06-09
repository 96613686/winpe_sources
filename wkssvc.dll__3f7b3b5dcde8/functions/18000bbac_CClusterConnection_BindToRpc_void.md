# CClusterConnection::BindToRpc(void)

- ea: `0x18000bbac`
- end: `0x18000bead`
- name: `?BindToRpc@CClusterConnection@@AEAAJXZ`
- size: `769`
- prototype: `__int64 __fastcall(CClusterConnection *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001d0f4`

## callees

- `0x18000b76c`
- `0x18000bbac`
- `0x18000dd68`
- `0x18000fda8`
- `0x18001c6dc`
- `0x18001e420`
- `0x180032594`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000bd71`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000bdb8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000bd71`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000bdb8`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18000be8d`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18000be8d`
- `RPCRT4!RpcEpResolveBinding` at `0x18000bc88`
- `RPCRT4!RpcEpResolveBinding` at `0x18000bc88`
- `RPCRT4!RpcStringFreeW` at `0x18000bd00`
- `RPCRT4!RpcStringFreeW` at `0x18000bd00`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000bc5b`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000bc5b`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000bc3c`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000bc3c`
- `RPCRT4!RpcMgmtSetComTimeout` at `0x18000bc71`
- `RPCRT4!RpcMgmtSetComTimeout` at `0x18000bc71`
- `DSPARSE!DsMakeSpnW` at `0x18000bcc7`
- `DSPARSE!DsMakeSpnW` at `0x18000be19`
- `DSPARSE!DsMakeSpnW` at `0x18000bcc7`
- `DSPARSE!DsMakeSpnW` at `0x18000be19`

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
        SpnW = RpcEpResolveBinding(Binding, qword_180035060);
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
0x18000bbac  mov     [rsp-28h+arg_8], rbx
0x18000bbb1  mov     [rsp-28h+arg_10], rsi
0x18000bbb6  push    rbp
0x18000bbb7  push    rdi
0x18000bbb8  push    r13
0x18000bbba  push    r14
0x18000bbbc  push    r15
0x18000bbbe  mov     rbp, rsp
0x18000bbc1  sub     rsp, 70h
0x18000bbc5  mov     rax, cs:__security_cookie
0x18000bbcc  xor     rax, rsp
0x18000bbcf  mov     [rbp+var_8], rax
0x18000bbd3  mov     r13d, [rcx+1C0h]
0x18000bbda  lea     r14, [rcx+58h]
0x18000bbde  xor     r15d, r15d
0x18000bbe1  mov     [rbp+Binding], 0
0x18000bbe9  cmp     qword ptr [r14+18h], 7
0x18000bbee  mov     rdi, rcx
0x18000bbf1  mov     [rbp+String], 0
0x18000bbf9  mov     [rbp+SecurityQOS.Version], 1
0x18000bc00  mov     qword ptr [rbp+SecurityQOS.Capabilities], 1
0x18000bc08  mov     [rbp+SecurityQOS.ImpersonationType], 3
0x18000bc0f  mov     [rbp+pcSpnLength], r15d
0x18000bc13  jbe     short loc_18000BC1A
0x18000bc15  mov     r8, [r14]
0x18000bc18  jmp     short loc_18000BC1D
0x18000bc1a  mov     r8, r14; NetworkAddr
0x18000bc1d  lea     rax, [rbp+String]
0x18000bc21  xor     r9d, r9d; Endpoint
0x18000bc24  mov     [rsp+70h+StringBinding], rax; StringBinding
0x18000bc29  lea     rdx, ProtSeq; "ncacn_ip_tcp"
0x18000bc30  lea     rcx, ObjUuid; "ccd8c074-d0e5-4a40-92b4-d074faa6ba28"
0x18000bc37  mov     [rsp+70h+Options], r15; Options
0x18000bc3c  call    cs:__imp_RpcStringBindingComposeW
0x18000bc42  lea     rsi, WPP_witness_GLOBAL_Control
0x18000bc49  mov     ebx, eax
0x18000bc4b  test    eax, eax
0x18000bc4d  jnz     loc_18000BCF5
0x18000bc53  mov     rcx, [rbp+String]; StringBinding
0x18000bc57  lea     rdx, [rbp+Binding]; Binding
0x18000bc5b  call    cs:__imp_RpcBindingFromStringBindingW
0x18000bc61  mov     ebx, eax
0x18000bc63  test    eax, eax
0x18000bc65  jnz     loc_18000BCF5
0x18000bc6b  mov     rcx, [rbp+Binding]; Binding
0x18000bc6f  xor     edx, edx; Timeout
0x18000bc71  call    cs:__imp_RpcMgmtSetComTimeout
0x18000bc77  mov     ebx, eax
0x18000bc79  test    eax, eax
0x18000bc7b  jnz     short loc_18000BCF5
0x18000bc7d  mov     rcx, [rbp+Binding]; Binding
0x18000bc81  lea     rdx, qword_180035060; IfSpec
0x18000bc88  call    cs:__imp_RpcEpResolveBinding
0x18000bc8e  mov     ebx, eax
0x18000bc90  test    eax, eax
0x18000bc92  jnz     short loc_18000BCF5
0x18000bc94  lea     rsi, [rdi+18h]
0x18000bc98  cmp     qword ptr [rsi+18h], 7
0x18000bc9d  jbe     short loc_18000BCA4
0x18000bc9f  mov     rdx, [rsi]
0x18000bca2  jmp     short loc_18000BCA7
0x18000bca4  mov     rdx, rsi; ServiceName
0x18000bca7  xor     r9d, r9d; InstancePort
0x18000bcaa  lea     rax, [rbp+pcSpnLength]
0x18000bcae  mov     [rsp+70h+pszSpn], r9; pszSpn
0x18000bcb3  lea     rcx, ServiceClass; "CIFS"
0x18000bcba  mov     [rsp+70h+StringBinding], rax; pcSpnLength
0x18000bcbf  xor     r8d, r8d; InstanceName
0x18000bcc2  mov     [rsp+70h+Options], r9; Referrer
0x18000bcc7  call    cs:__imp_DsMakeSpnW
0x18000bccd  mov     ebx, eax
0x18000bccf  cmp     eax, 6Fh ; 'o'
0x18000bcd2  jnz     short loc_18000BCEE
0x18000bcd4  mov     ecx, [rbp+pcSpnLength]
0x18000bcd7  add     rcx, rcx; unsigned __int64
0x18000bcda  call    ?MemoryAlloc@@YAPEAX_K@Z; MemoryAlloc(unsigned __int64)
0x18000bcdf  mov     r15, rax
0x18000bce2  test    rax, rax
0x18000bce5  jnz     loc_18000BDEC
0x18000bceb  lea     ebx, [rax+0Eh]
0x18000bcee  lea     rsi, WPP_witness_GLOBAL_Control
0x18000bcf5  cmp     [rbp+String], 0
0x18000bcfa  jz      short loc_18000BD06
0x18000bcfc  lea     rcx, [rbp+String]; String
0x18000bd00  call    cs:__imp_RpcStringFreeW
0x18000bd06  test    r15, r15
0x18000bd09  jz      short loc_18000BD13
0x18000bd0b  mov     rcx, r15; void *
0x18000bd0e  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18000bd13  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000bd1a  cmp     rcx, rsi
0x18000bd1d  jz      short loc_18000BD50
0x18000bd1f  test    byte ptr [rcx+1Ch], 1
0x18000bd23  jz      short loc_18000BD50
0x18000bd25  cmp     byte ptr [rcx+19h], 3
0x18000bd29  jb      short loc_18000BD50
0x18000bd2b  lea     r9, [rdi+18h]
0x18000bd2f  cmp     qword ptr [r9+18h], 7
0x18000bd34  jbe     short loc_18000BD39
0x18000bd36  mov     r9, [r9]
0x18000bd39  mov     rcx, [rcx+10h]
0x18000bd3d  mov     edx, 12h
0x18000bd42  mov     [rsp+70h+StringBinding], rdi
0x18000bd47  mov     dword ptr [rsp+70h+Options], ebx
0x18000bd4b  call    WPP_SF_Sdq
0x18000bd50  test    ebx, ebx
0x18000bd52  jz      short loc_18000BDC5
0x18000bd54  cmp     dword ptr [rdi+1D8h], 1
0x18000bd5b  jnz     short loc_18000BD83
0x18000bd5d  cmp     [rdi+1DCh], ebx
0x18000bd63  jnz     short loc_18000BD83
0x18000bd65  mov     rsi, [rdi+1E0h]
0x18000bd6c  test    rsi, rsi
0x18000bd6f  jz      short loc_18000BD83
0x18000bd71  call    cs:__imp_GetTickCount64
0x18000bd77  lea     rcx, [rsi+2932E00h]
0x18000bd7e  cmp     rax, rcx
0x18000bd81  jbe     short loc_18000BDC5
0x18000bd83  test    cs:Microsoft_Windows_SMBWitnessClientEnableBits, 1
0x18000bd8a  jz      short loc_18000BDA8
0x18000bd8c  cmp     qword ptr [r14+18h], 7
0x18000bd91  jbe     short loc_18000BD96
0x18000bd93  mov     r14, [r14]
0x18000bd96  mov     r9d, ebx
0x18000bd99  lea     rdx, WitnessClientInitialRpcBindFailed; "*"
0x18000bda0  mov     r8, r14
0x18000bda3  call    McTemplateU0zq_EventWriteTransfer
0x18000bda8  mov     dword ptr [rdi+1D8h], 1
0x18000bdb2  mov     [rdi+1DCh], ebx
0x18000bdb8  call    cs:__imp_GetTickCount64
0x18000bdbe  mov     [rdi+1E0h], rax
0x18000bdc5  mov     eax, ebx
0x18000bdc7  mov     rcx, [rbp+var_8]
0x18000bdcb  xor     rcx, rsp; StackCookie
0x18000bdce  call    __security_check_cookie
0x18000bdd3  lea     r11, [rsp+70h+var_s0]
0x18000bdd8  mov     rbx, [r11+38h]
0x18000bddc  mov     rsi, [r11+40h]
0x18000bde0  mov     rsp, r11
0x18000bde3  pop     r15
0x18000bde5  pop     r14
0x18000bde7  pop     r13
0x18000bde9  pop     rdi
0x18000bdea  pop     rbp
0x18000bdeb  retn
0x18000bdec  cmp     qword ptr [rsi+18h], 7
0x18000bdf1  jbe     short loc_18000BDF6
0x18000bdf3  mov     rsi, [rsi]
0x18000bdf6  lea     rax, [rbp+pcSpnLength]
0x18000bdfa  mov     [rsp+70h+pszSpn], r15; pszSpn
0x18000bdff  xor     r9d, r9d; InstancePort
0x18000be02  mov     [rsp+70h+StringBinding], rax; pcSpnLength
0x18000be07  xor     r8d, r8d; InstanceName
0x18000be0a  mov     [rsp+70h+Options], r9; Referrer
0x18000be0f  mov     rdx, rsi; ServiceName
0x18000be12  lea     rcx, ServiceClass; "CIFS"
0x18000be19  call    cs:__imp_DsMakeSpnW
0x18000be1f  mov     ebx, eax
0x18000be21  test    eax, eax
0x18000be23  jnz     loc_18000BCEE
0x18000be29  and     r13d, 1
0x18000be2d  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000be34  lea     rsi, WPP_witness_GLOBAL_Control
0x18000be3b  cmp     rcx, rsi
0x18000be3e  jz      short loc_18000BE62
0x18000be40  test    byte ptr [rcx+1Ch], 1
0x18000be44  jz      short loc_18000BE62
0x18000be46  cmp     byte ptr [rcx+19h], 3
0x18000be4a  jb      short loc_18000BE62
0x18000be4c  mov     rcx, [rcx+10h]
0x18000be50  lea     edx, [rax+11h]
0x18000be53  mov     r9, r15
0x18000be56  lea     r8, WPP_05a199c97cb13ffb21b1b8c24cf946fe_Traceguids
0x18000be5d  call    WPP_SF_S
0x18000be62  mov     rcx, [rbp+Binding]; Binding
0x18000be66  lea     rax, [rbp+SecurityQOS]
0x18000be6a  mov     [rsp+70h+pszSpn], rax; SecurityQOS
0x18000be6f  lea     r8d, [r13+5]; AuthnLevel
0x18000be73  mov     dword ptr [rsp+70h+StringBinding], 0FFFFFFFFh; AuthzSvc
0x18000be7b  mov     r9d, 9; AuthnSvc
0x18000be81  mov     rdx, r15; ServerPrincName
0x18000be84  mov     [rsp+70h+Options], 0; AuthIdentity
0x18000be8d  call    cs:__imp_RpcBindingSetAuthInfoExW
0x18000be93  mov     ebx, eax
0x18000be95  test    eax, eax
0x18000be97  jnz     loc_18000BCF5
0x18000be9d  mov     rax, [rbp+Binding]
0x18000bea1  mov     [rdi+110h], rax
0x18000bea8  jmp     loc_18000BCF5
```
