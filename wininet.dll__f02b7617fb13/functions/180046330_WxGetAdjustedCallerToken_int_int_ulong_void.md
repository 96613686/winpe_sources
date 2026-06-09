# WxGetAdjustedCallerToken(int,int *,ulong *,void * *)

- ea: `0x180046330`
- end: `0x18004665f`
- name: `?WxGetAdjustedCallerToken@@YAJHPEAHPEAKPEAPEAX@Z`
- size: `815`
- prototype: `__int64 __fastcall(int, int *, unsigned int *, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180045de8`

## callees

- `0x1800447b8`
- `0x180046330`
- `0x1800701d0`
- `0x180119bf4`
- `0x1801296f8`
- `0x18014a7a0`
- `0x1801e41b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800463bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180046545`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800463bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180046545`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800463d0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180046559`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800463d0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180046559`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046439`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004653b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046439`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004653b`
- `srpapi!SrpGetEnterpriseIds` at `0x1800465b9`
- `srpapi!SrpGetEnterpriseIds` at `0x1800465b9`
- `RPCRT4!RpcRevertToSelf` at `0x1800463e1`
- `RPCRT4!RpcRevertToSelf` at `0x1800464d0`
- `RPCRT4!RpcRevertToSelf` at `0x1800463e1`
- `RPCRT4!RpcRevertToSelf` at `0x1800464d0`
- `RPCRT4!RpcImpersonateClient` at `0x18004639e`
- `RPCRT4!RpcImpersonateClient` at `0x18004639e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180046595`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180046595`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180046618`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180046618`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180046480`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180046480`

## pseudocode

```c
__int64 __fastcall WxGetAdjustedCallerToken(int a1, int *a2, unsigned int *a3, void **a4)
{
  RPC_STATUS v7; // eax
  signed int EnterpriseIds; // ebx
  HANDLE CurrentThread; // rax
  __int64 v10; // rdx
  __int64 v11; // rcx
  int v12; // edi
  unsigned int v13; // r13d
  int v14; // esi
  void *v15; // rax
  __int64 v17; // rdx
  __int64 v18; // rcx
  int v19; // eax
  int v20; // eax
  int v21; // eax
  HANDLE v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rcx
  int LastError; // eax
  unsigned int v26; // r12d
  __int64 v27; // rdx
  __int64 v28; // rcx
  unsigned int v29; // [rsp+30h] [rbp-40h] BYREF
  int v30; // [rsp+34h] [rbp-3Ch]
  unsigned int v31; // [rsp+38h] [rbp-38h] BYREF
  unsigned int v32; // [rsp+3Ch] [rbp-34h] BYREF
  void **v33; // [rsp+40h] [rbp-30h]
  void *TokenHandle; // [rsp+48h] [rbp-28h] BYREF
  int v35; // [rsp+50h] [rbp-20h] BYREF
  int TokenInformation; // [rsp+54h] [rbp-1Ch] BYREF
  DWORD ReturnLength; // [rsp+58h] [rbp-18h] BYREF

  v33 = a4;
  v30 = 0;
  TokenHandle = 0;
  v31 = 0;
  v29 = 0;
  ReturnLength = 0;
  v32 = 0;
  v35 = 0;
  TokenInformation = 0;
  if ( a4 )
    *a4 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a2 )
    *a2 = 0;
  v7 = RpcImpersonateClient(0);
  EnterpriseIds = v7;
  if ( v7 > 0 )
    EnterpriseIds = (unsigned __int16)v7 | 0x80070000;
  if ( EnterpriseIds < 0 )
  {
    v30 = 216;
    goto LABEL_15;
  }
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
  {
    v12 = 0;
    RpcRevertToSelf();
    if ( a1 )
    {
      EnterpriseIds = SrpGetEnterpriseIds(TokenHandle, 0, 0, &v35);
      if ( EnterpriseIds < 0 )
      {
        v30 = 238;
        goto LABEL_15;
      }
      LOBYTE(v12) = v35 != 0;
    }
    EnterpriseIds = WxGetTokenInternalIntegrityLevel(TokenHandle, &v32);
    if ( EnterpriseIds < 0 )
    {
      v30 = 243;
      goto LABEL_15;
    }
    v13 = v32;
    v14 = 0;
    if ( v32 != 3 )
      goto LABEL_14;
    if ( GetTokenInformation(TokenHandle, TokenImpersonationLevel, &TokenInformation, 4u, &ReturnLength) )
    {
      EnterpriseIds = 0;
      if ( TokenInformation != 1 )
        goto LABEL_14;
      EnterpriseIds = WxGetProcessSessionId(&v31);
      if ( EnterpriseIds < 0 )
      {
        v30 = 261;
        goto LABEL_15;
      }
      EnterpriseIds = WxGetTokenSessionId(TokenHandle, &v29);
      if ( EnterpriseIds < 0 )
      {
        v30 = 264;
        goto LABEL_15;
      }
      v26 = v29;
      if ( v31 == v29 )
      {
LABEL_14:
        v15 = TokenHandle;
        TokenHandle = 0;
        *v33 = v15;
        *a3 = v13;
        *a2 = v12;
        if ( !v14 )
          goto LABEL_15;
        goto LABEL_45;
      }
      if ( ImpersonateSelf(SecurityImpersonation) )
      {
        if ( (BYTE3(xmmword_180266B60) & 0x20) != 0 )
          WPP_SF_dd(1053, 10, WPP_f1ca5156dd39373ce438d8bd3c0a11eb_Traceguids, v31, v26);
        if ( TokenHandle )
        {
          CloseHandle(TokenHandle);
          TokenHandle = 0;
        }
        v22 = GetCurrentThread();
        if ( !OpenThreadToken(v22, 8u, 0, &TokenHandle) )
        {
          LastError = WxGetLastError(v24, v23);
          EnterpriseIds = LastError;
          if ( LastError > 0 )
            EnterpriseIds = (unsigned __int16)LastError | 0x80070000;
          v30 = 283;
          if ( EnterpriseIds >= 0 )
            EnterpriseIds = -2147418113;
LABEL_45:
          RevertToSelf();
          goto LABEL_15;
        }
        v14 = 1;
        EnterpriseIds = 0;
        goto LABEL_14;
      }
      v21 = WxGetLastError(v28, v27);
      EnterpriseIds = v21;
      if ( v21 > 0 )
        EnterpriseIds = (unsigned __int16)v21 | 0x80070000;
      v30 = 271;
      if ( EnterpriseIds >= 0 )
        EnterpriseIds = -2147418113;
    }
    else
    {
      v20 = WxGetLastError(v18, v17);
      EnterpriseIds = v20;
      if ( v20 > 0 )
        EnterpriseIds = (unsigned __int16)v20 | 0x80070000;
      v30 = 254;
      if ( EnterpriseIds >= 0 )
        EnterpriseIds = -2147418113;
    }
  }
  else
  {
    v19 = WxGetLastError(v11, v10);
    EnterpriseIds = v19;
    if ( v19 > 0 )
      EnterpriseIds = (unsigned __int16)v19 | 0x80070000;
    v30 = 222;
    if ( EnterpriseIds >= 0 )
      EnterpriseIds = -2147418113;
    RpcRevertToSelf();
  }
LABEL_15:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)EnterpriseIds;
}

```

## disassembly

```asm
0x180046330  mov     [rsp-38h+arg_0], rbx
0x180046335  push    rbp
0x180046336  push    rsi
0x180046337  push    rdi
0x180046338  push    r12
0x18004633a  push    r13
0x18004633c  push    r14
0x18004633e  push    r15
0x180046340  mov     rbp, rsp
0x180046343  sub     rsp, 70h
0x180046347  mov     rax, cs:__security_cookie
0x18004634e  xor     rax, rsp
0x180046351  mov     [rbp+var_10], rax
0x180046355  xor     r12d, r12d
0x180046358  mov     [rbp+var_30], r9
0x18004635c  mov     [rbp+var_3C], r12d
0x180046360  mov     r15, r8
0x180046363  mov     [rbp+TokenHandle], r12
0x180046367  mov     r14, rdx
0x18004636a  mov     [rbp+var_38], r12d
0x18004636e  mov     esi, ecx
0x180046370  mov     [rbp+var_40], r12d
0x180046374  mov     [rbp+var_18], r12d
0x180046378  mov     [rbp+var_34], r12d
0x18004637c  mov     [rbp+var_20], r12d
0x180046380  mov     [rbp+TokenInformation], r12d
0x180046384  test    r9, r9
0x180046387  jz      short loc_18004638C
0x180046389  mov     [r9], r12
0x18004638c  test    r15, r15
0x18004638f  jz      short loc_180046394
0x180046391  mov     [r8], r12d
0x180046394  test    r14, r14
0x180046397  jz      short loc_18004639C
0x180046399  mov     [rdx], r12d
0x18004639c  xor     ecx, ecx; BindingHandle
0x18004639e  call    cs:__imp_RpcImpersonateClient
0x1800463a4  mov     ebx, eax
0x1800463a6  mov     edi, 80070000h
0x1800463ab  test    eax, eax
0x1800463ad  jle     short loc_1800463B4
0x1800463af  movzx   ebx, ax
0x1800463b2  or      ebx, edi
0x1800463b4  test    ebx, ebx
0x1800463b6  js      loc_1800465A0
0x1800463bc  call    cs:__imp_GetCurrentThread
0x1800463c2  xor     r8d, r8d; OpenAsSelf
0x1800463c5  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800463c9  mov     rcx, rax; ThreadHandle
0x1800463cc  lea     edx, [r8+8]; DesiredAccess
0x1800463d0  call    cs:__imp_OpenThreadToken
0x1800463d6  test    eax, eax
0x1800463d8  jz      loc_1800464AF
0x1800463de  mov     edi, r12d
0x1800463e1  call    cs:__imp_RpcRevertToSelf
0x1800463e7  test    esi, esi
0x1800463e9  jnz     loc_1800465AC
0x1800463ef  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800463f3  lea     rdx, [rbp+var_34]; unsigned int *
0x1800463f7  call    ?WxGetTokenInternalIntegrityLevel@@YAJPEAXPEAK@Z; WxGetTokenInternalIntegrityLevel(void *,ulong *)
0x1800463fc  mov     ebx, eax
0x1800463fe  test    eax, eax
0x180046400  js      loc_1800465DE
0x180046406  mov     r13d, [rbp+var_34]
0x18004640a  mov     esi, r12d
0x18004640d  cmp     r13d, 3
0x180046411  jz      short loc_180046465
0x180046413  mov     rax, [rbp+TokenHandle]
0x180046417  mov     rcx, [rbp+var_30]
0x18004641b  mov     [rbp+TokenHandle], r12
0x18004641f  mov     [rcx], rax
0x180046422  mov     [r15], r13d
0x180046425  mov     [r14], edi
0x180046428  test    esi, esi
0x18004642a  jnz     loc_180046595
0x180046430  mov     rcx, [rbp+TokenHandle]; hObject
0x180046434  test    rcx, rcx
0x180046437  jz      short loc_18004643F
0x180046439  call    cs:__imp_CloseHandle
0x18004643f  mov     eax, ebx
0x180046441  mov     rcx, [rbp+var_10]
0x180046445  xor     rcx, rsp; StackCookie
0x180046448  call    __security_check_cookie
0x18004644d  mov     rbx, [rsp+70h+arg_0]
0x180046455  add     rsp, 70h
0x180046459  pop     r15
0x18004645b  pop     r14
0x18004645d  pop     r13
0x18004645f  pop     r12
0x180046461  pop     rdi
0x180046462  pop     rsi
0x180046463  pop     rbp
0x180046464  retn
0x180046465  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180046469  lea     rax, [rbp+var_18]
0x18004646d  mov     r9d, 4; TokenInformationLength
0x180046473  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x180046478  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18004647c  lea     edx, [r9+5]; TokenInformationClass
0x180046480  call    cs:__imp_GetTokenInformation
0x180046486  test    eax, eax
0x180046488  jz      short loc_1800464DB
0x18004648a  cmp     [rbp+TokenInformation], 1
0x18004648e  mov     ebx, r12d
0x180046491  jnz     short loc_180046413
0x180046493  lea     rcx, [rbp+var_38]; unsigned int *
0x180046497  call    ?WxGetProcessSessionId@@YAJPEAK@Z; WxGetProcessSessionId(ulong *)
0x18004649c  mov     ebx, eax
0x18004649e  test    eax, eax
0x1800464a0  jns     loc_1800465EA
0x1800464a6  mov     [rbp+var_3C], 105h
0x1800464ad  jmp     short loc_180046430
0x1800464af  call    WxGetLastError
0x1800464b4  mov     ebx, eax
0x1800464b6  test    eax, eax
0x1800464b8  jle     short loc_1800464BF
0x1800464ba  movzx   ebx, ax
0x1800464bd  or      ebx, edi
0x1800464bf  test    ebx, ebx
0x1800464c1  mov     [rbp+var_3C], 0DEh
0x1800464c8  mov     eax, 8000FFFFh
0x1800464cd  cmovns  ebx, eax
0x1800464d0  call    cs:__imp_RpcRevertToSelf
0x1800464d6  jmp     loc_180046430
0x1800464db  call    WxGetLastError
0x1800464e0  mov     ebx, eax
0x1800464e2  test    eax, eax
0x1800464e4  jle     short loc_1800464EF
0x1800464e6  movzx   ebx, ax
0x1800464e9  or      ebx, 80070000h
0x1800464ef  test    ebx, ebx
0x1800464f1  mov     [rbp+var_3C], 0FEh
0x1800464f8  mov     eax, 8000FFFFh
0x1800464fd  cmovns  ebx, eax
0x180046500  jmp     loc_180046430
0x180046505  call    WxGetLastError
0x18004650a  mov     ebx, eax
0x18004650c  test    eax, eax
0x18004650e  jle     short loc_180046519
0x180046510  movzx   ebx, ax
0x180046513  or      ebx, 80070000h
0x180046519  test    ebx, ebx
0x18004651b  mov     [rbp+var_3C], 10Fh
0x180046522  mov     eax, 8000FFFFh
0x180046527  cmovns  ebx, eax
0x18004652a  jmp     loc_180046430
0x18004652f  mov     rcx, [rbp+TokenHandle]; hObject
0x180046533  xor     r12d, r12d
0x180046536  test    rcx, rcx
0x180046539  jz      short loc_180046545
0x18004653b  call    cs:__imp_CloseHandle
0x180046541  mov     [rbp+TokenHandle], r12
0x180046545  call    cs:__imp_GetCurrentThread
0x18004654b  xor     r8d, r8d; OpenAsSelf
0x18004654e  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180046552  mov     rcx, rax; ThreadHandle
0x180046555  lea     edx, [r8+8]; DesiredAccess
0x180046559  call    cs:__imp_OpenThreadToken
0x18004655f  test    eax, eax
0x180046561  jz      short loc_180046570
0x180046563  mov     esi, 1
0x180046568  mov     ebx, r12d
0x18004656b  jmp     loc_180046413
0x180046570  call    WxGetLastError
0x180046575  mov     ebx, eax
0x180046577  test    eax, eax
0x180046579  jle     short loc_180046584
0x18004657b  movzx   ebx, ax
0x18004657e  or      ebx, 80070000h
0x180046584  test    ebx, ebx
0x180046586  mov     [rbp+var_3C], 11Bh
0x18004658d  mov     eax, 8000FFFFh
0x180046592  cmovns  ebx, eax
0x180046595  call    cs:__imp_RevertToSelf
0x18004659b  jmp     loc_180046430
0x1800465a0  mov     [rbp+var_3C], 0D8h
0x1800465a7  jmp     loc_180046430
0x1800465ac  mov     rcx, [rbp+TokenHandle]
0x1800465b0  lea     r9, [rbp+var_20]
0x1800465b4  xor     r8d, r8d
0x1800465b7  xor     edx, edx
0x1800465b9  call    cs:__imp_SrpGetEnterpriseIds
0x1800465bf  mov     ebx, eax
0x1800465c1  test    eax, eax
0x1800465c3  jns     short loc_1800465D1
0x1800465c5  mov     [rbp+var_3C], 0EEh
0x1800465cc  jmp     loc_180046430
0x1800465d1  cmp     [rbp+var_20], r12d
0x1800465d5  setnbe  dil
0x1800465d9  jmp     loc_1800463EF
0x1800465de  mov     [rbp+var_3C], 0F3h
0x1800465e5  jmp     loc_180046430
0x1800465ea  mov     rcx, [rbp+TokenHandle]; void *
0x1800465ee  lea     rdx, [rbp+var_40]; unsigned int *
0x1800465f2  call    ?WxGetTokenSessionId@@YAJPEAXPEAK@Z; WxGetTokenSessionId(void *,ulong *)
0x1800465f7  mov     ebx, eax
0x1800465f9  test    eax, eax
0x1800465fb  jns     short loc_180046609
0x1800465fd  mov     [rbp+var_3C], 108h
0x180046604  jmp     loc_180046430
0x180046609  mov     r12d, [rbp+var_40]
0x18004660d  cmp     [rbp+var_38], r12d
0x180046611  jz      short loc_180046657
0x180046613  mov     ecx, 2; ImpersonationLevel
0x180046618  call    cs:__imp_ImpersonateSelf
0x18004661e  test    eax, eax
0x180046620  jz      loc_180046505
0x180046626  test    byte ptr cs:xmmword_180266B60+3, 20h
0x18004662d  jz      loc_18004652F
0x180046633  mov     r9d, [rbp+var_38]
0x180046637  lea     r8, WPP_f1ca5156dd39373ce438d8bd3c0a11eb_Traceguids
0x18004663e  mov     edx, 0Ah
0x180046643  mov     dword ptr [rsp+70h+ReturnLength], r12d
0x180046648  mov     ecx, 41Dh
0x18004664d  call    WPP_SF_dd
0x180046652  jmp     loc_18004652F
0x180046657  xor     r12d, r12d
0x18004665a  jmp     loc_180046413
```
