# ForceLogoffOtherUsers(void * const,ulong,CandidateUserPhase,int *)

- ea: `0x140089f28`
- end: `0x14008a389`
- name: `?ForceLogoffOtherUsers@@YAXQEAXKW4CandidateUserPhase@@PEAH@Z`
- size: `1121`
- prototype: ``
- caller_count: `4`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140010e90`
- `0x1400129f0`
- `0x1400608f0`
- `0x140072200`

## callees

- `0x1400057f4`
- `0x14003cb6c`
- `0x14003ddec`
- `0x140041c34`
- `0x14004bb00`
- `0x140053720`
- `0x1400544e0`
- `0x140056230`
- `0x1400568f0`
- `0x1400897e8`
- `0x140089f28`
- `0x14008cc34`
- `0x14009b6c8`
- `0x14009b880`
- `0x14009ba20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140089ff7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008a10f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140089ff7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008a10f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14008a154`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14008a154`
- `ntdll!RtlEqualSid` at `0x14008a16a`
- `ntdll!RtlEqualSid` at `0x14008a16a`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamIsCandidateUser` at `0x14008a1b9`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamIsCandidateUser` at `0x14008a1b9`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x14008a35a`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x14008a35a`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x14008a0e2`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x14008a0e2`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x140089fb3`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x140089fb3`

## pseudocode

```c
void __fastcall ForceLogoffOtherUsers(void *a1, int a2, int a3, _DWORD *a4)
{
  int v5; // r14d
  BOOL v6; // ebx
  DWORD LastError; // eax
  unsigned int v8; // r12d
  const char *v9; // r9
  DWORD v10; // eax
  CUser *v11; // rcx
  __int64 v12; // rdx
  int IsCandidateUser; // eax
  unsigned int *v14; // rcx
  __int64 v15; // r9
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r8
  int v19; // r14d
  PVOID v20; // rcx
  PVOID pMemory; // [rsp+30h] [rbp-89h] BYREF
  int v22; // [rsp+38h] [rbp-81h]
  DWORD pCount; // [rsp+3Ch] [rbp-7Dh] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+40h] [rbp-79h] BYREF
  void *phToken; // [rsp+48h] [rbp-71h] BYREF
  int v26; // [rsp+50h] [rbp-69h]
  DWORD ReturnLength; // [rsp+54h] [rbp-65h] BYREF
  PSID Sid2; // [rsp+58h] [rbp-61h]
  PVOID *p_pMemory; // [rsp+60h] [rbp-59h] BYREF
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+68h] [rbp-51h] BYREF
  char v31; // [rsp+70h] [rbp-49h]
  PSID TokenInformation[12]; // [rsp+80h] [rbp-39h] BYREF

  v26 = a3;
  pMemory = 0;
  pCount = 0;
  v5 = a2;
  v22 = a2;
  Sid2 = a1;
  if ( (unsigned __int8)IsWTSEnumerateSessionsWPresent() && (unsigned __int8)IsWTSEnumerateSessionsWPresent() )
  {
    ppSessionInfo = 0;
    p_pMemory = &pMemory;
    v31 = 1;
    v6 = WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &pCount);
    wil::details::out_param_t<wistd::unique_ptr<_WTS_SESSION_INFOW [0],wil::function_deleter<void (*)(void *),&void WTSFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<_WTS_SESSION_INFOW [0],wil::function_deleter<void (*)(void *),&void WTSFreeMemory(void *)>>>(&p_pMemory);
    if ( !v6 )
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 120, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids, LastError);
      }
      goto LABEL_63;
    }
    v8 = 0;
    if ( !pCount )
      goto LABEL_63;
    while ( 1 )
    {
      phToken = 0;
      memset_0(TokenInformation, 0, 0x54u);
      ReturnLength = 0;
      if ( *((_DWORD *)pMemory + 6 * v8) )
      {
        if ( v5 == *((_DWORD *)pMemory + 6 * v8) && (unsigned int)(v26 - 1) <= 1 )
        {
          if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            v9 = "NeverHostedWebContent";
            if ( v26 != 1 )
              v9 = "HasHostedWebContent";
            WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 121, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids, v9);
          }
          goto LABEL_57;
        }
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          &phToken,
          0);
        if ( !WTSQueryUserToken(*((_DWORD *)pMemory + 6 * v8), &phToken) )
        {
          if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            v10 = GetLastError();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 122, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids, v10);
          }
          goto LABEL_57;
        }
        if ( GetTokenInformation(phToken, TokenUser, TokenInformation, 0x54u, &ReturnLength) )
        {
          if ( RtlEqualSid(TokenInformation[0], Sid2) )
          {
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
            {
              goto LABEL_57;
            }
            v12 = 123;
            goto LABEL_45;
          }
          if ( (unsigned __int8)IsCamCleanupDisardedCandidateAccountsPresent() )
          {
            LODWORD(Binding) = 0;
            IsCandidateUser = CamIsCandidateUser(TokenInformation[0], &Binding);
            if ( (IsCandidateUser & 0x1FFF0000) == 0x70000 )
              IsCandidateUser = (unsigned __int16)IsCandidateUser;
            if ( !IsCandidateUser && (_DWORD)Binding )
            {
              v11 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
                || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
              {
                goto LABEL_57;
              }
              v12 = 124;
              goto LABEL_45;
            }
          }
          v14 = (unsigned int *)pMemory;
          v15 = *((unsigned int *)pMemory + 6 * v8);
          if ( (_DWORD)v15 != v5 )
          {
            if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 126, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids, v15);
              v14 = (unsigned int *)pMemory;
            }
            v16 = v14[6 * v8];
            Binding = 0;
            v19 = WmsgpConnect(v16, &Binding);
            if ( v19 || (v19 = WmsgpPostMessage(Binding), WmsgpDisconnect(&Binding), v19) )
            {
              if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, v18, *((unsigned int *)pMemory + 6 * v8), v19);
              }
            }
            v5 = v22;
            goto LABEL_57;
          }
          if ( a4 )
            *a4 = 1;
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            v12 = 125;
LABEL_45:
            WPP_SF_(*((_QWORD *)v11 + 2), v12, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids);
          }
        }
      }
LABEL_57:
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phToken);
      if ( ++v8 >= pCount )
        goto LABEL_63;
    }
  }
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 119, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids);
  }
LABEL_63:
  v20 = pMemory;
  pMemory = 0;
  if ( v20 )
    WTSFreeMemory(v20);
}

```

## disassembly

```asm
0x140089f28  mov     [rsp-8+arg_8], rbx
0x140089f2d  mov     [rsp-8+arg_10], rdi
0x140089f32  push    rbp
0x140089f33  push    r12
0x140089f35  push    r13
0x140089f37  push    r14
0x140089f39  push    r15
0x140089f3b  lea     rbp, [rsp-37h]
0x140089f40  sub     rsp, 0F0h
0x140089f47  mov     rax, cs:__security_cookie
0x140089f4e  xor     rax, rsp
0x140089f51  mov     [rbp+57h+var_30], rax
0x140089f55  xor     r15d, r15d
0x140089f58  mov     [rbp+57h+var_C0], r8d
0x140089f5c  mov     [rsp+110h+pMemory], r15
0x140089f61  mov     r13, r9
0x140089f64  mov     [rbp+57h+var_D4], r15d
0x140089f68  mov     r14d, edx
0x140089f6b  mov     [rsp+110h+var_D8], edx
0x140089f6f  mov     [rbp+57h+Sid2], rcx
0x140089f73  call    IsWTSEnumerateSessionsWPresent
0x140089f78  test    al, al
0x140089f7a  jz      loc_14008A313
0x140089f80  call    IsWTSEnumerateSessionsWPresent
0x140089f85  test    al, al
0x140089f87  jz      loc_14008A313
0x140089f8d  lea     rax, [rsp+110h+pMemory]
0x140089f92  mov     [rbp+57h+ppSessionInfo], r15
0x140089f96  mov     [rbp+57h+var_B0], rax
0x140089f9a  lea     r9, [rbp+57h+ppSessionInfo]; ppSessionInfo
0x140089f9e  lea     rax, [rbp+57h+var_D4]
0x140089fa2  mov     [rbp+57h+var_A0], 1
0x140089fa6  xor     edx, edx; Reserved
0x140089fa8  mov     [rsp+110h+pCount], rax; pCount
0x140089fad  xor     ecx, ecx; hServer
0x140089faf  lea     r8d, [r15+1]; Version
0x140089fb3  call    cs:__imp_WTSEnumerateSessionsW
0x140089fb9  lea     rcx, [rbp+57h+var_B0]
0x140089fbd  mov     ebx, eax
0x140089fbf  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@U_WTS_SESSION_INFOW@@U?$function_deleter@P6AXPEAX@Z$1?WTSFreeMemory@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_WTS_SESSION_INFOW [0],wil::function_deleter<void (*)(void *),&WTSFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<_WTS_SESSION_INFOW [0],wil::function_deleter<void (*)(void *),&WTSFreeMemory(void *)>>>(void)
0x140089fc4  test    ebx, ebx
0x140089fc6  jnz     short loc_14008A020
0x140089fc8  mov     rax, cs:WPP_GLOBAL_Control
0x140089fcf  lea     rdi, WPP_GLOBAL_Control
0x140089fd6  cmp     rax, rdi
0x140089fd9  jz      loc_14008A34B
0x140089fdf  mov     ebx, 1000h
0x140089fe4  test    [rax+1Ch], ebx
0x140089fe7  jz      loc_14008A34B
0x140089fed  cmp     byte ptr [rax+19h], 2
0x140089ff1  jb      loc_14008A34B
0x140089ff7  call    cs:__imp_GetLastError
0x140089ffd  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a004  lea     edx, [r15+78h]
0x14008a008  mov     r9d, eax
0x14008a00b  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x14008a012  mov     rcx, [rcx+10h]
0x14008a016  call    WPP_SF_d
0x14008a01b  jmp     loc_14008A34B
0x14008a020  mov     r12d, r15d
0x14008a023  cmp     [rbp+57h+var_D4], r15d
0x14008a027  jbe     loc_14008A34B
0x14008a02d  lea     rdi, WPP_GLOBAL_Control
0x14008a034  mov     ebx, 1000h
0x14008a039  xor     edx, edx; Val
0x14008a03b  mov     [rbp+57h+phToken], r15
0x14008a03f  lea     rcx, [rbp+57h+TokenInformation]; void *
0x14008a043  lea     r8d, [rdx+54h]; Size
0x14008a047  call    memset_0
0x14008a04c  mov     eax, r12d
0x14008a04f  mov     [rbp+57h+ReturnLength], r15d
0x14008a053  lea     r15, [rax+rax*2]
0x14008a057  mov     rax, [rsp+110h+pMemory]
0x14008a05c  cmp     dword ptr [rax+r15*8], 0
0x14008a061  jz      loc_14008A2F5
0x14008a067  cmp     r14d, [rax+r15*8]
0x14008a06b  jnz     short loc_14008A0CA
0x14008a06d  mov     edx, [rbp+57h+var_C0]
0x14008a070  lea     eax, [rdx-1]
0x14008a073  cmp     eax, 1
0x14008a076  ja      short loc_14008A0CA
0x14008a078  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a07f  cmp     rcx, rdi
0x14008a082  jz      loc_14008A2F5
0x14008a088  test    [rcx+1Ch], ebx
0x14008a08b  jz      loc_14008A2F5
0x14008a091  cmp     byte ptr [rcx+19h], 5
0x14008a095  jb      loc_14008A2F5
0x14008a09b  mov     rcx, [rcx+10h]
0x14008a09f  lea     rax, aHashostedwebco; "HasHostedWebContent"
0x14008a0a6  cmp     edx, 1
0x14008a0a9  lea     r9, aNeverhostedweb; "NeverHostedWebContent"
0x14008a0b0  mov     edx, 79h ; 'y'
0x14008a0b5  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x14008a0bc  cmovnz  r9, rax
0x14008a0c0  call    WPP_SF_s
0x14008a0c5  jmp     loc_14008A2F5
0x14008a0ca  xor     edx, edx
0x14008a0cc  lea     rcx, [rbp+57h+phToken]
0x14008a0d0  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x14008a0d5  mov     rcx, [rsp+110h+pMemory]
0x14008a0da  lea     rdx, [rbp+57h+phToken]; phToken
0x14008a0de  mov     ecx, [rcx+r15*8]; SessionId
0x14008a0e2  call    cs:__imp_WTSQueryUserToken
0x14008a0e8  test    eax, eax
0x14008a0ea  jnz     short loc_14008A139
0x14008a0ec  mov     rax, cs:WPP_GLOBAL_Control
0x14008a0f3  cmp     rax, rdi
0x14008a0f6  jz      loc_14008A2F5
0x14008a0fc  test    [rax+1Ch], ebx
0x14008a0ff  jz      loc_14008A2F5
0x14008a105  cmp     byte ptr [rax+19h], 5
0x14008a109  jb      loc_14008A2F5
0x14008a10f  call    cs:__imp_GetLastError
0x14008a115  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a11c  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x14008a123  mov     edx, 7Ah ; 'z'
0x14008a128  mov     r9d, eax
0x14008a12b  mov     rcx, [rcx+10h]
0x14008a12f  call    WPP_SF_d
0x14008a134  jmp     loc_14008A2F5
0x14008a139  mov     rcx, [rbp+57h+phToken]; TokenHandle
0x14008a13d  lea     rax, [rbp+57h+ReturnLength]
0x14008a141  mov     r9d, 54h ; 'T'; TokenInformationLength
0x14008a147  mov     [rsp+110h+pCount], rax; ReturnLength
0x14008a14c  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x14008a150  lea     edx, [r9-53h]; TokenInformationClass
0x14008a154  call    cs:__imp_GetTokenInformation
0x14008a15a  test    eax, eax
0x14008a15c  jz      loc_14008A2F5
0x14008a162  mov     rdx, [rbp+57h+Sid2]; Sid2
0x14008a166  mov     rcx, [rbp+57h+TokenInformation]; Sid1
0x14008a16a  call    cs:__imp_RtlEqualSid
0x14008a170  test    al, al
0x14008a172  jz      short loc_14008A1A1
0x14008a174  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a17b  cmp     rcx, rdi
0x14008a17e  jz      loc_14008A2F5
0x14008a184  test    [rcx+1Ch], ebx
0x14008a187  jz      loc_14008A2F5
0x14008a18d  cmp     byte ptr [rcx+19h], 5
0x14008a191  jb      loc_14008A2F5
0x14008a197  mov     edx, 7Bh ; '{'
0x14008a19c  jmp     loc_14008A246
0x14008a1a1  call    IsCamCleanupDisardedCandidateAccountsPresent
0x14008a1a6  test    al, al
0x14008a1a8  jz      short loc_14008A203
0x14008a1aa  mov     rcx, [rbp+57h+TokenInformation]
0x14008a1ae  lea     rdx, [rbp+57h+Binding]
0x14008a1b2  mov     dword ptr [rbp+57h+Binding], 0
0x14008a1b9  call    cs:__imp_CamIsCandidateUser
0x14008a1bf  mov     ecx, eax
0x14008a1c1  and     ecx, 1FFF0000h
0x14008a1c7  cmp     ecx, 70000h
0x14008a1cd  jnz     short loc_14008A1D2
0x14008a1cf  movzx   eax, ax
0x14008a1d2  test    eax, eax
0x14008a1d4  jnz     short loc_14008A203
0x14008a1d6  cmp     dword ptr [rbp+57h+Binding], eax
0x14008a1d9  jz      short loc_14008A203
0x14008a1db  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a1e2  cmp     rcx, rdi
0x14008a1e5  jz      loc_14008A2F5
0x14008a1eb  test    [rcx+1Ch], ebx
0x14008a1ee  jz      loc_14008A2F5
0x14008a1f4  cmp     byte ptr [rcx+19h], 5
0x14008a1f8  jb      loc_14008A2F5
0x14008a1fe  lea     edx, [rax+7Ch]
0x14008a201  jmp     short loc_14008A246
0x14008a203  mov     rcx, [rsp+110h+pMemory]
0x14008a208  mov     r9d, [rcx+r15*8]
0x14008a20c  cmp     r9d, r14d
0x14008a20f  jnz     short loc_14008A25B
0x14008a211  test    r13, r13
0x14008a214  jz      short loc_14008A21E
0x14008a216  mov     dword ptr [r13+0], 1
0x14008a21e  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a225  cmp     rcx, rdi
0x14008a228  jz      loc_14008A2F5
0x14008a22e  test    [rcx+1Ch], ebx
0x14008a231  jz      loc_14008A2F5
0x14008a237  cmp     byte ptr [rcx+19h], 5
0x14008a23b  jb      loc_14008A2F5
0x14008a241  mov     edx, 7Dh ; '}'
0x14008a246  mov     rcx, [rcx+10h]
0x14008a24a  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x14008a251  call    WPP_SF_
0x14008a256  jmp     loc_14008A2F5
0x14008a25b  mov     rax, cs:WPP_GLOBAL_Control
0x14008a262  cmp     rax, rdi
0x14008a265  jz      short loc_14008A28C
0x14008a267  test    [rax+1Ch], ebx
0x14008a26a  jz      short loc_14008A28C
0x14008a26c  cmp     byte ptr [rax+19h], 5
0x14008a270  jb      short loc_14008A28C
0x14008a272  mov     rcx, [rax+10h]
0x14008a276  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x14008a27d  mov     edx, 7Eh ; '~'
0x14008a282  call    WPP_SF_d
0x14008a287  mov     rcx, [rsp+110h+pMemory]
0x14008a28c  mov     ecx, [rcx+r15*8]
0x14008a290  lea     rdx, [rbp+57h+Binding]
0x14008a294  mov     [rbp+57h+Binding], 0
0x14008a29c  call    WmsgpConnect
0x14008a2a1  mov     r14d, eax
0x14008a2a4  test    eax, eax
0x14008a2a6  jnz     short loc_14008A2C2
0x14008a2a8  mov     rcx, [rbp+57h+Binding]; SourceBinding
0x14008a2ac  call    WmsgpPostMessage
0x14008a2b1  lea     rcx, [rbp+57h+Binding]; Binding
0x14008a2b5  mov     r14d, eax
0x14008a2b8  call    WmsgpDisconnect
0x14008a2bd  test    r14d, r14d
0x14008a2c0  jz      short loc_14008A2F0
0x14008a2c2  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a2c9  cmp     rcx, rdi
0x14008a2cc  jz      short loc_14008A2F0
0x14008a2ce  test    [rcx+1Ch], ebx
0x14008a2d1  jz      short loc_14008A2F0
0x14008a2d3  cmp     byte ptr [rcx+19h], 2
0x14008a2d7  jb      short loc_14008A2F0
0x14008a2d9  mov     r9, [rsp+110h+pMemory]
0x14008a2de  mov     rcx, [rcx+10h]
0x14008a2e2  mov     dword ptr [rsp+110h+pCount], r14d
0x14008a2e7  mov     r9d, [r9+r15*8]
0x14008a2eb  call    WPP_SF_dD
0x14008a2f0  mov     r14d, [rsp+110h+var_D8]
0x14008a2f5  lea     rcx, [rbp+57h+phToken]
0x14008a2f9  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14008a2fe  inc     r12d
0x14008a301  mov     r15d, 0
0x14008a307  cmp     r12d, [rbp+57h+var_D4]
0x14008a30b  jb      loc_14008A039
0x14008a311  jmp     short loc_14008A34B
0x14008a313  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a31a  lea     rdi, WPP_GLOBAL_Control
0x14008a321  cmp     rcx, rdi
0x14008a324  jz      short loc_14008A34B
0x14008a326  mov     ebx, 1000h
0x14008a32b  test    [rcx+1Ch], ebx
0x14008a32e  jz      short loc_14008A34B
0x14008a330  cmp     byte ptr [rcx+19h], 2
0x14008a334  jb      short loc_14008A34B
0x14008a336  mov     rcx, [rcx+10h]
0x14008a33a  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x14008a341  mov     edx, 77h ; 'w'
0x14008a346  call    WPP_SF_
0x14008a34b  mov     rcx, [rsp+110h+pMemory]; pMemory
0x14008a350  mov     [rsp+110h+pMemory], r15
0x14008a355  test    rcx, rcx
0x14008a358  jz      short loc_14008A360
0x14008a35a  call    cs:__imp_WTSFreeMemory
0x14008a360  mov     rcx, [rbp+57h+var_30]
0x14008a364  xor     rcx, rsp; StackCookie
0x14008a367  call    __security_check_cookie
0x14008a36c  lea     r11, [rsp+110h+var_20]
0x14008a374  mov     rbx, [r11+38h]
0x14008a378  mov     rdi, [r11+40h]
0x14008a37c  mov     rsp, r11
0x14008a37f  pop     r15
0x14008a381  pop     r14
0x14008a383  pop     r13
0x14008a385  pop     r12
0x14008a387  pop     rbp
0x14008a388  retn
```
