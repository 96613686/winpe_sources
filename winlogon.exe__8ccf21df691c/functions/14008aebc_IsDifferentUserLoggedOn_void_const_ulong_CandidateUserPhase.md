# IsDifferentUserLoggedOn(void * const,ulong,CandidateUserPhase)

- ea: `0x14008aebc`
- end: `0x14008b23c`
- name: `?IsDifferentUserLoggedOn@@YA_NQEAXKW4CandidateUserPhase@@@Z`
- size: `896`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
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
- `0x14008aebc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008af86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008b0a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008af86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008b0a5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14008b0ec`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14008b0ec`
- `ntdll!RtlEqualSid` at `0x14008b101`
- `ntdll!RtlEqualSid` at `0x14008b101`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamIsCandidateUser` at `0x14008b143`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamIsCandidateUser` at `0x14008b143`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x14008b1bf`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x14008b214`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x14008b1bf`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x14008b214`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x14008b078`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x14008b078`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x14008af42`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x14008af42`

## pseudocode

```c
char __fastcall IsDifferentUserLoggedOn(void *a1, int a2, int a3)
{
  BOOL v6; // ebx
  DWORD v7; // eax
  __int64 i; // r14
  const char *v9; // r9
  DWORD LastError; // eax
  CUser *v11; // rcx
  __int64 v12; // rdx
  int IsCandidateUser; // eax
  PVOID v14; // rcx
  PVOID v16; // rcx
  PVOID pMemory; // [rsp+30h] [rbp-99h] BYREF
  void *phToken; // [rsp+38h] [rbp-91h] BYREF
  DWORD pCount; // [rsp+40h] [rbp-89h] BYREF
  int v20; // [rsp+44h] [rbp-85h] BYREF
  DWORD ReturnLength; // [rsp+48h] [rbp-81h] BYREF
  PVOID *p_pMemory; // [rsp+50h] [rbp-79h] BYREF
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+58h] [rbp-71h] BYREF
  char v24; // [rsp+60h] [rbp-69h]
  PSID TokenInformation[12]; // [rsp+70h] [rbp-59h] BYREF

  pMemory = 0;
  pCount = 0;
  if ( !(unsigned __int8)IsWTSEnumerateSessionsWPresent() || !(unsigned __int8)IsWTSEnumerateSessionsWPresent() )
  {
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 113, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids);
    }
    goto LABEL_48;
  }
  ppSessionInfo = 0;
  v24 = 1;
  p_pMemory = &pMemory;
  v6 = WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &pCount);
  wil::details::out_param_t<wistd::unique_ptr<_WTS_SESSION_INFOW [0],wil::function_deleter<void (*)(void *),&void WTSFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<_WTS_SESSION_INFOW [0],wil::function_deleter<void (*)(void *),&void WTSFreeMemory(void *)>>>(&p_pMemory);
  if ( v6 )
  {
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)i >= pCount )
        goto LABEL_48;
      phToken = 0;
      memset_0(TokenInformation, 0, 0x54u);
      ReturnLength = 0;
      if ( *((_DWORD *)pMemory + 6 * i) )
      {
        if ( a2 == *((_DWORD *)pMemory + 6 * i) && (unsigned int)(a3 - 1) <= 1 )
        {
          if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            v9 = "NeverHostedWebContent";
            if ( a3 != 1 )
              v9 = "HasHostedWebContent";
            WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 115, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids, v9);
          }
        }
        else
        {
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
            &phToken,
            0);
          if ( WTSQueryUserToken(*((_DWORD *)pMemory + 6 * i), &phToken) )
          {
            if ( !GetTokenInformation(phToken, TokenUser, TokenInformation, 0x54u, &ReturnLength) )
              goto LABEL_40;
            if ( RtlEqualSid(TokenInformation[0], a1) )
            {
              v11 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                v12 = 117;
LABEL_39:
                WPP_SF_(*((_QWORD *)v11 + 2), v12, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids);
              }
            }
            else
            {
              if ( !(unsigned __int8)IsCamCleanupDisardedCandidateAccountsPresent() )
                goto LABEL_41;
              v20 = 0;
              IsCandidateUser = CamIsCandidateUser(TokenInformation[0], &v20);
              if ( (IsCandidateUser & 0x1FFF0000) == 0x70000 )
                IsCandidateUser = (unsigned __int16)IsCandidateUser;
              if ( IsCandidateUser || !v20 )
              {
LABEL_41:
                wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phToken);
                v14 = pMemory;
                pMemory = 0;
                if ( v14 )
                  WTSFreeMemory(v14);
                return 1;
              }
              v11 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                v12 = 118;
                goto LABEL_39;
              }
            }
          }
          else if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                 && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            LastError = GetLastError();
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              116,
              WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids,
              LastError);
          }
        }
      }
LABEL_40:
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phToken);
    }
  }
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v7 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 114, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids, v7);
  }
LABEL_48:
  v16 = pMemory;
  pMemory = 0;
  if ( v16 )
    WTSFreeMemory(v16);
  return 0;
}

```

## disassembly

```asm
0x14008aebc  push    rbp
0x14008aebe  push    rbx
0x14008aebf  push    rsi
0x14008aec0  push    rdi
0x14008aec1  push    r12
0x14008aec3  push    r13
0x14008aec5  push    r14
0x14008aec7  push    r15
0x14008aec9  lea     rbp, [rsp-1Fh]
0x14008aece  sub     rsp, 0E8h
0x14008aed5  mov     rax, cs:__security_cookie
0x14008aedc  xor     rax, rsp
0x14008aedf  mov     [rbp+57h+var_50], rax
0x14008aee3  mov     r15d, r8d
0x14008aee6  mov     [rsp+120h+pMemory], 0
0x14008aeef  mov     r12d, edx
0x14008aef2  mov     [rsp+120h+var_E0], 0
0x14008aefa  mov     r13, rcx
0x14008aefd  call    IsWTSEnumerateSessionsWPresent
0x14008af02  test    al, al
0x14008af04  jz      loc_14008B1C9
0x14008af0a  call    IsWTSEnumerateSessionsWPresent
0x14008af0f  test    al, al
0x14008af11  jz      loc_14008B1C9
0x14008af17  xor     edx, edx; Reserved
0x14008af19  mov     [rbp+57h+ppSessionInfo], 0
0x14008af21  lea     rax, [rsp+120h+pMemory]
0x14008af26  mov     [rbp+57h+var_C0], 1
0x14008af2a  mov     [rbp+57h+var_D0], rax
0x14008af2e  lea     r9, [rbp+57h+ppSessionInfo]; ppSessionInfo
0x14008af32  lea     rax, [rsp+120h+var_E0]
0x14008af37  xor     ecx, ecx; hServer
0x14008af39  lea     r8d, [rdx+1]; Version
0x14008af3d  mov     [rsp+120h+pCount], rax; pCount
0x14008af42  call    cs:__imp_WTSEnumerateSessionsW
0x14008af48  lea     rcx, [rbp+57h+var_D0]
0x14008af4c  mov     ebx, eax
0x14008af4e  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@U_WTS_SESSION_INFOW@@U?$function_deleter@P6AXPEAX@Z$1?WTSFreeMemory@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_WTS_SESSION_INFOW [0],wil::function_deleter<void (*)(void *),&WTSFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<_WTS_SESSION_INFOW [0],wil::function_deleter<void (*)(void *),&WTSFreeMemory(void *)>>>(void)
0x14008af53  test    ebx, ebx
0x14008af55  jnz     short loc_14008AFB0
0x14008af57  mov     rax, cs:WPP_GLOBAL_Control
0x14008af5e  lea     rdi, WPP_GLOBAL_Control
0x14008af65  cmp     rax, rdi
0x14008af68  jz      loc_14008B201
0x14008af6e  mov     ebx, 1000h
0x14008af73  test    [rax+1Ch], ebx
0x14008af76  jz      loc_14008B201
0x14008af7c  cmp     byte ptr [rax+19h], 2
0x14008af80  jb      loc_14008B201
0x14008af86  call    cs:__imp_GetLastError
0x14008af8c  mov     rcx, cs:WPP_GLOBAL_Control
0x14008af93  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x14008af9a  mov     edx, 72h ; 'r'
0x14008af9f  mov     r9d, eax
0x14008afa2  mov     rcx, [rcx+10h]
0x14008afa6  call    WPP_SF_d
0x14008afab  jmp     loc_14008B201
0x14008afb0  xor     r14d, r14d
0x14008afb3  lea     rdi, WPP_GLOBAL_Control
0x14008afba  mov     ebx, 1000h
0x14008afbf  cmp     r14d, [rsp+120h+var_E0]
0x14008afc4  jnb     loc_14008B201
0x14008afca  xor     edx, edx; Val
0x14008afcc  mov     [rsp+120h+phToken], 0
0x14008afd5  lea     rcx, [rbp+57h+TokenInformation]; void *
0x14008afd9  lea     r8d, [rdx+54h]; Size
0x14008afdd  call    memset_0
0x14008afe2  mov     rax, [rsp+120h+pMemory]
0x14008afe7  lea     rsi, [r14+r14*2]
0x14008afeb  mov     [rsp+120h+ReturnLength], 0
0x14008aff3  cmp     dword ptr [rax+rsi*8], 0
0x14008aff7  jz      loc_14008B190
0x14008affd  cmp     r12d, [rax+rsi*8]
0x14008b001  jnz     short loc_14008B05F
0x14008b003  lea     eax, [r15-1]
0x14008b007  cmp     eax, 1
0x14008b00a  ja      short loc_14008B05F
0x14008b00c  mov     rcx, cs:WPP_GLOBAL_Control
0x14008b013  cmp     rcx, rdi
0x14008b016  jz      loc_14008B190
0x14008b01c  test    [rcx+1Ch], ebx
0x14008b01f  jz      loc_14008B190
0x14008b025  cmp     byte ptr [rcx+19h], 5
0x14008b029  jb      loc_14008B190
0x14008b02f  mov     rcx, [rcx+10h]
0x14008b033  lea     rax, aHashostedwebco; "HasHostedWebContent"
0x14008b03a  cmp     r15d, 1
0x14008b03e  lea     r9, aNeverhostedweb; "NeverHostedWebContent"
0x14008b045  mov     edx, 73h ; 's'
0x14008b04a  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x14008b051  cmovnz  r9, rax
0x14008b055  call    WPP_SF_s
0x14008b05a  jmp     loc_14008B190
0x14008b05f  xor     edx, edx
0x14008b061  lea     rcx, [rsp+120h+phToken]
0x14008b066  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x14008b06b  mov     rcx, [rsp+120h+pMemory]
0x14008b070  lea     rdx, [rsp+120h+phToken]; phToken
0x14008b075  mov     ecx, [rcx+rsi*8]; SessionId
0x14008b078  call    cs:__imp_WTSQueryUserToken
0x14008b07e  test    eax, eax
0x14008b080  jnz     short loc_14008B0CF
0x14008b082  mov     rax, cs:WPP_GLOBAL_Control
0x14008b089  cmp     rax, rdi
0x14008b08c  jz      loc_14008B190
0x14008b092  test    [rax+1Ch], ebx
0x14008b095  jz      loc_14008B190
0x14008b09b  cmp     byte ptr [rax+19h], 5
0x14008b09f  jb      loc_14008B190
0x14008b0a5  call    cs:__imp_GetLastError
0x14008b0ab  mov     rcx, cs:WPP_GLOBAL_Control
0x14008b0b2  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x14008b0b9  mov     edx, 74h ; 't'
0x14008b0be  mov     r9d, eax
0x14008b0c1  mov     rcx, [rcx+10h]
0x14008b0c5  call    WPP_SF_d
0x14008b0ca  jmp     loc_14008B190
0x14008b0cf  mov     rcx, [rsp+120h+phToken]; TokenHandle
0x14008b0d4  lea     rax, [rsp+120h+ReturnLength]
0x14008b0d9  mov     r9d, 54h ; 'T'; TokenInformationLength
0x14008b0df  mov     [rsp+120h+pCount], rax; ReturnLength
0x14008b0e4  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x14008b0e8  lea     edx, [r9-53h]; TokenInformationClass
0x14008b0ec  call    cs:__imp_GetTokenInformation
0x14008b0f2  test    eax, eax
0x14008b0f4  jz      loc_14008B190
0x14008b0fa  mov     rcx, [rbp+57h+TokenInformation]; Sid1
0x14008b0fe  mov     rdx, r13; Sid2
0x14008b101  call    cs:__imp_RtlEqualSid
0x14008b107  test    al, al
0x14008b109  jz      short loc_14008B129
0x14008b10b  mov     rcx, cs:WPP_GLOBAL_Control
0x14008b112  cmp     rcx, rdi
0x14008b115  jz      short loc_14008B190
0x14008b117  test    [rcx+1Ch], ebx
0x14008b11a  jz      short loc_14008B190
0x14008b11c  cmp     byte ptr [rcx+19h], 5
0x14008b120  jb      short loc_14008B190
0x14008b122  mov     edx, 75h ; 'u'
0x14008b127  jmp     short loc_14008B180
0x14008b129  call    IsCamCleanupDisardedCandidateAccountsPresent
0x14008b12e  test    al, al
0x14008b130  jz      short loc_14008B1A2
0x14008b132  mov     rcx, [rbp+57h+TokenInformation]
0x14008b136  lea     rdx, [rsp+120h+var_DC]
0x14008b13b  mov     [rsp+120h+var_DC], 0
0x14008b143  call    cs:__imp_CamIsCandidateUser
0x14008b149  mov     ecx, eax
0x14008b14b  and     ecx, 1FFF0000h
0x14008b151  cmp     ecx, 70000h
0x14008b157  jnz     short loc_14008B15C
0x14008b159  movzx   eax, ax
0x14008b15c  test    eax, eax
0x14008b15e  jnz     short loc_14008B1A2
0x14008b160  cmp     [rsp+120h+var_DC], eax
0x14008b164  jz      short loc_14008B1A2
0x14008b166  mov     rcx, cs:WPP_GLOBAL_Control
0x14008b16d  cmp     rcx, rdi
0x14008b170  jz      short loc_14008B190
0x14008b172  test    [rcx+1Ch], ebx
0x14008b175  jz      short loc_14008B190
0x14008b177  cmp     byte ptr [rcx+19h], 5
0x14008b17b  jb      short loc_14008B190
0x14008b17d  lea     edx, [rax+76h]
0x14008b180  mov     rcx, [rcx+10h]
0x14008b184  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x14008b18b  call    WPP_SF_
0x14008b190  lea     rcx, [rsp+120h+phToken]
0x14008b195  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14008b19a  inc     r14d
0x14008b19d  jmp     loc_14008AFBF
0x14008b1a2  lea     rcx, [rsp+120h+phToken]
0x14008b1a7  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14008b1ac  mov     rcx, [rsp+120h+pMemory]; pMemory
0x14008b1b1  mov     [rsp+120h+pMemory], 0
0x14008b1ba  test    rcx, rcx
0x14008b1bd  jz      short loc_14008B1C5
0x14008b1bf  call    cs:__imp_WTSFreeMemory
0x14008b1c5  mov     al, 1
0x14008b1c7  jmp     short loc_14008B21C
0x14008b1c9  mov     rcx, cs:WPP_GLOBAL_Control
0x14008b1d0  lea     rdi, WPP_GLOBAL_Control
0x14008b1d7  cmp     rcx, rdi
0x14008b1da  jz      short loc_14008B201
0x14008b1dc  mov     ebx, 1000h
0x14008b1e1  test    [rcx+1Ch], ebx
0x14008b1e4  jz      short loc_14008B201
0x14008b1e6  cmp     byte ptr [rcx+19h], 2
0x14008b1ea  jb      short loc_14008B201
0x14008b1ec  mov     rcx, [rcx+10h]
0x14008b1f0  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x14008b1f7  mov     edx, 71h ; 'q'
0x14008b1fc  call    WPP_SF_
0x14008b201  mov     rcx, [rsp+120h+pMemory]; pMemory
0x14008b206  mov     [rsp+120h+pMemory], 0
0x14008b20f  test    rcx, rcx
0x14008b212  jz      short loc_14008B21A
0x14008b214  call    cs:__imp_WTSFreeMemory
0x14008b21a  xor     al, al
0x14008b21c  mov     rcx, [rbp+57h+var_50]
0x14008b220  xor     rcx, rsp; StackCookie
0x14008b223  call    __security_check_cookie
0x14008b228  add     rsp, 0E8h
0x14008b22f  pop     r15
0x14008b231  pop     r14
0x14008b233  pop     r13
0x14008b235  pop     r12
0x14008b237  pop     rdi
0x14008b238  pop     rsi
0x14008b239  pop     rbx
0x14008b23a  pop     rbp
0x14008b23b  retn
```
