# WxGetAdjustedCallerToken(int,int *,ulong *,void * *)

- ea: `0x18002aad8`
- end: `0x18002afa4`
- name: `?WxGetAdjustedCallerToken@@YAJHPEAHPEAKPEAPEAX@Z`
- size: `1228`
- prototype: `__int64 __fastcall(int, int *, unsigned int *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002a210`

## callees

- `0x18002aad8`
- `0x180080fb0`
- `0x180081b40`
- `0x18008cb20`
- `0x18008cb94`
- `0x1800c519c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002ab87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002ad80`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002ab87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002ad80`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002ab9b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002ad94`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002ab9b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002ad94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ad0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002adb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ade4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ae05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ae26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ae47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ad0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002adb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ade4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ae05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ae26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ae47`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002ac07`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002ac8d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002aee6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002ac07`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002ac8d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002aee6`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002ae63`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002ae63`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002ac20`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002ac20`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18002af5b`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18002af5b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002ac31`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002ac31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002acd2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ad72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002acd2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ad72`
- `RPCRT4!RpcRevertToSelf` at `0x18002abac`
- `RPCRT4!RpcRevertToSelf` at `0x18002add4`
- `RPCRT4!RpcRevertToSelf` at `0x18002abac`
- `RPCRT4!RpcRevertToSelf` at `0x18002add4`
- `RPCRT4!RpcImpersonateClient` at `0x18002ab6a`
- `RPCRT4!RpcImpersonateClient` at `0x18002ab6a`
- `srpapi!SrpGetEnterpriseIds` at `0x18002ae8f`
- `srpapi!SrpGetEnterpriseIds` at `0x18002ae8f`

## pseudocode

```c
__int64 __fastcall WxGetAdjustedCallerToken(int a1, int *a2, unsigned int *a3, void **a4)
{
  void **v4; // r14
  RPC_STATUS v8; // eax
  signed int EnterpriseIds; // ebx
  HANDLE CurrentThread; // rax
  int v11; // r15d
  void *v12; // rbx
  PUCHAR SidSubAuthorityCount; // rax
  DWORD v14; // edi
  int v15; // edi
  int v16; // r14d
  signed int v18; // eax
  HANDLE v19; // rax
  signed int v20; // eax
  signed int LastError; // eax
  signed int v22; // eax
  signed int v23; // eax
  signed int v24; // eax
  unsigned int v25; // edi
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // r8
  unsigned int v29; // [rsp+30h] [rbp-99h] BYREF
  int v30; // [rsp+34h] [rbp-95h]
  void **v31; // [rsp+38h] [rbp-91h]
  HANDLE v32; // [rsp+40h] [rbp-89h]
  DWORD ReturnLength; // [rsp+48h] [rbp-81h] BYREF
  int v34; // [rsp+4Ch] [rbp-7Dh]
  unsigned int v35; // [rsp+50h] [rbp-79h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp-71h] BYREF
  int v37; // [rsp+60h] [rbp-69h] BYREF
  int v38; // [rsp+64h] [rbp-65h] BYREF
  DWORD v39; // [rsp+68h] [rbp-61h] BYREF
  PSID TokenInformation[14]; // [rsp+70h] [rbp-59h] BYREF

  v31 = a4;
  v4 = a4;
  v34 = 0;
  TokenHandle = 0;
  v35 = 0;
  v29 = 0;
  v39 = 0;
  v37 = 0;
  v38 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a2 )
    *a2 = 0;
  v8 = RpcImpersonateClient(0);
  EnterpriseIds = v8;
  if ( v8 > 0 )
    EnterpriseIds = (unsigned __int16)v8 | 0x80070000;
  if ( EnterpriseIds < 0 )
  {
    v34 = 216;
    goto LABEL_24;
  }
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
  {
    v11 = 0;
    RpcRevertToSelf();
    if ( a1 )
    {
      EnterpriseIds = SrpGetEnterpriseIds(TokenHandle, 0, 0, &v37);
      if ( EnterpriseIds < 0 )
      {
        v34 = 238;
        goto LABEL_24;
      }
      LOBYTE(v11) = v37 != 0;
    }
    v12 = TokenHandle;
    v30 = 0;
    v32 = TokenHandle;
    v34 = 0;
    memset_0(TokenInformation, 0, 0x6Cu);
    ReturnLength = 108;
    if ( GetTokenInformation(v12, TokenIntegrityLevel, TokenInformation, 0x6Cu, &ReturnLength) )
    {
      EnterpriseIds = 0;
      SidSubAuthorityCount = GetSidSubAuthorityCount(TokenInformation[0]);
      v14 = *GetSidSubAuthority(TokenInformation[0], (unsigned __int8)(*SidSubAuthorityCount - 1));
    }
    else
    {
      v14 = 4096;
      LastError = GetLastError();
      EnterpriseIds = LastError;
      if ( LastError > 0 )
        EnterpriseIds = (unsigned __int16)LastError | 0x80070000;
      v34 = 307;
      if ( EnterpriseIds >= 0 )
        EnterpriseIds = -2147418113;
    }
    if ( EnterpriseIds < 0 )
    {
      v15 = 0;
      v34 = 344;
      goto LABEL_22;
    }
    if ( v14 < 0x2000 )
    {
      v34 = 0;
      ReturnLength = 0;
      v35 = 0;
      v15 = v14 >= 0x1000 ? 2 : 0;
      v16 = 0;
      if ( GetTokenInformation(v32, TokenIsAppContainer, &v35, 4u, &ReturnLength) )
      {
        EnterpriseIds = 0;
        LOBYTE(v16) = v35 != 0;
      }
      else
      {
        v18 = GetLastError();
        EnterpriseIds = v18;
        if ( v18 > 0 )
          EnterpriseIds = (unsigned __int16)v18 | 0x80070000;
        v34 = 158;
        if ( EnterpriseIds >= 0 )
          EnterpriseIds = -2147418113;
      }
      if ( EnterpriseIds < 0 )
      {
        v34 = 357;
      }
      else if ( v16 )
      {
        v15 = 1;
      }
      v4 = v31;
LABEL_22:
      if ( EnterpriseIds < 0 )
      {
        v34 = 243;
        goto LABEL_24;
      }
LABEL_35:
      *v4 = TokenHandle;
      *a3 = v15;
      *a2 = v11;
      TokenHandle = 0;
      if ( !v30 )
        goto LABEL_24;
      goto LABEL_66;
    }
    if ( GetTokenInformation(TokenHandle, TokenImpersonationLevel, &v38, 4u, &v39) )
    {
      EnterpriseIds = 0;
      if ( v38 != 1 )
        goto LABEL_41;
      EnterpriseIds = WxGetProcessSessionId(&v35);
      if ( EnterpriseIds < 0 )
      {
        v34 = 261;
        goto LABEL_24;
      }
      EnterpriseIds = WxGetTokenSessionId(TokenHandle, &v29);
      if ( EnterpriseIds < 0 )
      {
        v34 = 264;
        goto LABEL_24;
      }
      v25 = v29;
      if ( v35 == v29 )
      {
LABEL_41:
        v15 = 3;
        goto LABEL_35;
      }
      if ( ImpersonateSelf(SecurityImpersonation) )
      {
        if ( (BYTE3(xmmword_180113B20) & 0x20) != 0 )
          WPP_SF_DD(v27, v26, v28, v35, v25);
        if ( TokenHandle )
        {
          CloseHandle(TokenHandle);
          TokenHandle = 0;
        }
        v19 = GetCurrentThread();
        if ( !OpenThreadToken(v19, 8u, 0, &TokenHandle) )
        {
          v24 = GetLastError();
          EnterpriseIds = v24;
          if ( v24 > 0 )
            EnterpriseIds = (unsigned __int16)v24 | 0x80070000;
          v34 = 283;
          if ( EnterpriseIds >= 0 )
            EnterpriseIds = -2147418113;
LABEL_66:
          RevertToSelf();
          goto LABEL_24;
        }
        v30 = 1;
        EnterpriseIds = 0;
        goto LABEL_41;
      }
      v23 = GetLastError();
      EnterpriseIds = v23;
      if ( v23 > 0 )
        EnterpriseIds = (unsigned __int16)v23 | 0x80070000;
      v34 = 271;
      if ( EnterpriseIds >= 0 )
        EnterpriseIds = -2147418113;
    }
    else
    {
      v22 = GetLastError();
      EnterpriseIds = v22;
      if ( v22 > 0 )
        EnterpriseIds = (unsigned __int16)v22 | 0x80070000;
      v34 = 254;
      if ( EnterpriseIds >= 0 )
        EnterpriseIds = -2147418113;
    }
  }
  else
  {
    v20 = GetLastError();
    EnterpriseIds = v20;
    if ( v20 > 0 )
      EnterpriseIds = (unsigned __int16)v20 | 0x80070000;
    v34 = 222;
    if ( EnterpriseIds >= 0 )
      EnterpriseIds = -2147418113;
    RpcRevertToSelf();
  }
LABEL_24:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)EnterpriseIds;
}

```

## disassembly

```asm
0x18002aad8  mov     [rsp-8+arg_0], rbx
0x18002aadd  push    rbp
0x18002aade  push    rsi
0x18002aadf  push    rdi
0x18002aae0  push    r12
0x18002aae2  push    r13
0x18002aae4  push    r14
0x18002aae6  push    r15
0x18002aae8  lea     rbp, [rsp-27h]
0x18002aaed  sub     rsp, 0F0h
0x18002aaf4  mov     rax, cs:__security_cookie
0x18002aafb  xor     rax, rsp
0x18002aafe  mov     [rbp+57h+var_40], rax
0x18002ab02  mov     [rsp+120h+var_E8], r9
0x18002ab07  mov     r14, r9
0x18002ab0a  mov     [rbp+57h+var_D4], 0
0x18002ab11  mov     r13, r8
0x18002ab14  mov     [rbp+57h+TokenHandle], 0
0x18002ab1c  mov     r12, rdx
0x18002ab1f  mov     [rbp+57h+var_D0], 0
0x18002ab26  mov     edi, ecx
0x18002ab28  mov     [rsp+120h+var_F0], 0
0x18002ab30  mov     [rbp+57h+var_B8], 0
0x18002ab37  mov     [rbp+57h+var_C0], 0
0x18002ab3e  mov     [rbp+57h+var_BC], 0
0x18002ab45  test    r9, r9
0x18002ab48  jz      short loc_18002AB51
0x18002ab4a  mov     qword ptr [r9], 0
0x18002ab51  test    r13, r13
0x18002ab54  jz      short loc_18002AB5D
0x18002ab56  mov     dword ptr [r8], 0
0x18002ab5d  test    r12, r12
0x18002ab60  jz      short loc_18002AB68
0x18002ab62  mov     dword ptr [rdx], 0
0x18002ab68  xor     ecx, ecx; BindingHandle
0x18002ab6a  call    cs:__imp_RpcImpersonateClient
0x18002ab70  mov     ebx, eax
0x18002ab72  mov     esi, 80070000h
0x18002ab77  test    eax, eax
0x18002ab79  jg      loc_18002AE6E
0x18002ab7f  test    ebx, ebx
0x18002ab81  js      loc_18002AD01
0x18002ab87  call    cs:__imp_GetCurrentThread
0x18002ab8d  xor     r8d, r8d; OpenAsSelf
0x18002ab90  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18002ab94  mov     rcx, rax; ThreadHandle
0x18002ab97  lea     edx, [r8+8]; DesiredAccess
0x18002ab9b  call    cs:__imp_OpenThreadToken
0x18002aba1  test    eax, eax
0x18002aba3  jz      loc_18002ADB3
0x18002aba9  xor     r15d, r15d
0x18002abac  call    cs:__imp_RpcRevertToSelf
0x18002abb2  test    edi, edi
0x18002abb4  jnz     loc_18002AE82
0x18002abba  mov     rbx, [rbp+57h+TokenHandle]
0x18002abbe  lea     rcx, [rbp+57h+TokenInformation]; void *
0x18002abc2  mov     edi, 6Ch ; 'l'
0x18002abc7  mov     [rbp+57h+var_D4], 0
0x18002abce  mov     r8d, edi; Size
0x18002abd1  mov     [rsp+120h+var_EC], 0
0x18002abd9  xor     edx, edx; Val
0x18002abdb  mov     [rsp+120h+var_E0], rbx
0x18002abe0  mov     [rbp+57h+var_D4], 0
0x18002abe7  call    memset_0
0x18002abec  lea     rax, [rsp+120h+var_D8]
0x18002abf1  mov     [rsp+120h+var_D8], edi
0x18002abf5  mov     r9d, edi; TokenInformationLength
0x18002abf8  mov     [rsp+120h+ReturnLength], rax; ReturnLength
0x18002abfd  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18002ac01  mov     rcx, rbx; TokenHandle
0x18002ac04  lea     edx, [rdi-53h]; TokenInformationClass
0x18002ac07  call    cs:__imp_GetTokenInformation
0x18002ac0d  mov     esi, 8000FFFFh
0x18002ac12  test    eax, eax
0x18002ac14  jz      loc_18002ADDF
0x18002ac1a  mov     rcx, [rbp+57h+TokenInformation]; pSid
0x18002ac1e  xor     ebx, ebx
0x18002ac20  call    cs:__imp_GetSidSubAuthorityCount
0x18002ac26  mov     cl, [rax]
0x18002ac28  dec     cl
0x18002ac2a  movzx   edx, cl; nSubAuthority
0x18002ac2d  mov     rcx, [rbp+57h+TokenInformation]; pSid
0x18002ac31  call    cs:__imp_GetSidSubAuthority
0x18002ac37  mov     edi, [rax]
0x18002ac39  test    ebx, ebx
0x18002ac3b  js      loc_18002AD2B
0x18002ac41  mov     r9d, 4; TokenInformationLength
0x18002ac47  cmp     edi, 2000h
0x18002ac4d  jnb     loc_18002AED0
0x18002ac53  mov     rcx, [rsp+120h+var_E0]; TokenHandle
0x18002ac58  lea     rax, [rsp+120h+var_D8]
0x18002ac5d  cmp     edi, 1000h
0x18002ac63  mov     [rbp+57h+var_D4], 0
0x18002ac6a  lea     r8, [rbp+57h+var_D0]; TokenInformation
0x18002ac6e  mov     [rsp+120h+var_D8], 0
0x18002ac76  sbb     edi, edi
0x18002ac78  mov     [rbp+57h+var_D0], 0
0x18002ac7f  not     edi
0x18002ac81  mov     [rsp+120h+ReturnLength], rax; ReturnLength
0x18002ac86  lea     edx, [r9+19h]; TokenInformationClass
0x18002ac8a  and     edi, 2
0x18002ac8d  call    cs:__imp_GetTokenInformation
0x18002ac93  xor     r14d, r14d
0x18002ac96  test    eax, eax
0x18002ac98  jz      short loc_18002AD0A
0x18002ac9a  xor     ebx, ebx
0x18002ac9c  cmp     [rbp+57h+var_D0], ebx
0x18002ac9f  setnz   r14b
0x18002aca3  test    ebx, ebx
0x18002aca5  js      loc_18002AD36
0x18002acab  test    r14d, r14d
0x18002acae  jz      short loc_18002ACB5
0x18002acb0  mov     edi, 1
0x18002acb5  mov     r14, [rsp+120h+var_E8]
0x18002acba  test    ebx, ebx
0x18002acbc  jns     loc_18002AD42
0x18002acc2  mov     [rbp+57h+var_D4], 0F3h
0x18002acc9  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18002accd  test    rcx, rcx
0x18002acd0  jz      short loc_18002ACD8
0x18002acd2  call    cs:__imp_CloseHandle
0x18002acd8  mov     eax, ebx
0x18002acda  mov     rcx, [rbp+57h+var_40]
0x18002acde  xor     rcx, rsp; StackCookie
0x18002ace1  call    __security_check_cookie
0x18002ace6  mov     rbx, [rsp+120h+arg_0]
0x18002acee  add     rsp, 0F0h
0x18002acf5  pop     r15
0x18002acf7  pop     r14
0x18002acf9  pop     r13
0x18002acfb  pop     r12
0x18002acfd  pop     rdi
0x18002acfe  pop     rsi
0x18002acff  pop     rbp
0x18002ad00  retn
0x18002ad01  mov     [rbp+57h+var_D4], 0D8h
0x18002ad08  jmp     short loc_18002ACC9
0x18002ad0a  call    cs:__imp_GetLastError
0x18002ad10  mov     ebx, eax
0x18002ad12  test    eax, eax
0x18002ad14  jg      loc_18002AEC2
0x18002ad1a  test    ebx, ebx
0x18002ad1c  mov     [rbp+57h+var_D4], 9Eh
0x18002ad23  cmovns  ebx, esi
0x18002ad26  jmp     loc_18002ACA3
0x18002ad2b  xor     edi, edi
0x18002ad2d  mov     [rbp+57h+var_D4], 158h
0x18002ad34  jmp     short loc_18002ACBA
0x18002ad36  mov     [rbp+57h+var_D4], 165h
0x18002ad3d  jmp     loc_18002ACB5
0x18002ad42  mov     rax, [rbp+57h+TokenHandle]
0x18002ad46  mov     [r14], rax
0x18002ad49  mov     [r13+0], edi
0x18002ad4d  mov     [r12], r15d
0x18002ad51  mov     [rbp+57h+TokenHandle], 0
0x18002ad59  cmp     [rsp+120h+var_EC], 0
0x18002ad5e  jz      loc_18002ACC9
0x18002ad64  jmp     loc_18002AE63
0x18002ad69  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18002ad6d  test    rcx, rcx
0x18002ad70  jz      short loc_18002AD80
0x18002ad72  call    cs:__imp_CloseHandle
0x18002ad78  mov     [rbp+57h+TokenHandle], 0
0x18002ad80  call    cs:__imp_GetCurrentThread
0x18002ad86  xor     r8d, r8d; OpenAsSelf
0x18002ad89  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18002ad8d  mov     rcx, rax; ThreadHandle
0x18002ad90  lea     edx, [r8+8]; DesiredAccess
0x18002ad94  call    cs:__imp_OpenThreadToken
0x18002ad9a  test    eax, eax
0x18002ad9c  jz      loc_18002AE47
0x18002ada2  mov     [rsp+120h+var_EC], 1
0x18002adaa  xor     ebx, ebx
0x18002adac  mov     edi, 3
0x18002adb1  jmp     short loc_18002AD42
0x18002adb3  call    cs:__imp_GetLastError
0x18002adb9  mov     ebx, eax
0x18002adbb  test    eax, eax
0x18002adbd  jg      loc_18002AE78
0x18002adc3  test    ebx, ebx
0x18002adc5  mov     [rbp+57h+var_D4], 0DEh
0x18002adcc  mov     esi, 8000FFFFh
0x18002add1  cmovns  ebx, esi
0x18002add4  call    cs:__imp_RpcRevertToSelf
0x18002adda  jmp     loc_18002ACC9
0x18002addf  mov     edi, 1000h
0x18002ade4  call    cs:__imp_GetLastError
0x18002adea  mov     ebx, eax
0x18002adec  test    eax, eax
0x18002adee  jg      loc_18002AEB4
0x18002adf4  test    ebx, ebx
0x18002adf6  mov     [rbp+57h+var_D4], 133h
0x18002adfd  cmovns  ebx, esi
0x18002ae00  jmp     loc_18002AC39
0x18002ae05  call    cs:__imp_GetLastError
0x18002ae0b  mov     ebx, eax
0x18002ae0d  test    eax, eax
0x18002ae0f  jg      loc_18002AF1B
0x18002ae15  test    ebx, ebx
0x18002ae17  mov     [rbp+57h+var_D4], 0FEh
0x18002ae1e  cmovns  ebx, esi
0x18002ae21  jmp     loc_18002ACC9
0x18002ae26  call    cs:__imp_GetLastError
0x18002ae2c  mov     ebx, eax
0x18002ae2e  test    eax, eax
0x18002ae30  jg      loc_18002AF88
0x18002ae36  test    ebx, ebx
0x18002ae38  mov     [rbp+57h+var_D4], 10Fh
0x18002ae3f  cmovns  ebx, esi
0x18002ae42  jmp     loc_18002ACC9
0x18002ae47  call    cs:__imp_GetLastError
0x18002ae4d  mov     ebx, eax
0x18002ae4f  test    eax, eax
0x18002ae51  jg      loc_18002AF96
0x18002ae57  test    ebx, ebx
0x18002ae59  mov     [rbp+57h+var_D4], 11Bh
0x18002ae60  cmovns  ebx, esi
0x18002ae63  call    cs:__imp_RevertToSelf
0x18002ae69  jmp     loc_18002ACC9
0x18002ae6e  movzx   ebx, ax
0x18002ae71  or      ebx, esi
0x18002ae73  jmp     loc_18002AB7F
0x18002ae78  movzx   ebx, ax
0x18002ae7b  or      ebx, esi
0x18002ae7d  jmp     loc_18002ADC3
0x18002ae82  mov     rcx, [rbp+57h+TokenHandle]
0x18002ae86  lea     r9, [rbp+57h+var_C0]
0x18002ae8a  xor     r8d, r8d
0x18002ae8d  xor     edx, edx
0x18002ae8f  call    cs:__imp_SrpGetEnterpriseIds
0x18002ae95  mov     ebx, eax
0x18002ae97  test    eax, eax
0x18002ae99  jns     short loc_18002AEA7
0x18002ae9b  mov     [rbp+57h+var_D4], 0EEh
0x18002aea2  jmp     loc_18002ACC9
0x18002aea7  cmp     [rbp+57h+var_C0], r15d
0x18002aeab  setnbe  r15b
0x18002aeaf  jmp     loc_18002ABBA
0x18002aeb4  movzx   ebx, ax
0x18002aeb7  or      ebx, 80070000h
0x18002aebd  jmp     loc_18002ADF4
0x18002aec2  movzx   ebx, ax
0x18002aec5  or      ebx, 80070000h
0x18002aecb  jmp     loc_18002AD1A
0x18002aed0  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18002aed4  lea     rax, [rbp+57h+var_B8]
0x18002aed8  lea     r8, [rbp+57h+var_BC]; TokenInformation
0x18002aedc  mov     [rsp+120h+ReturnLength], rax; ReturnLength
0x18002aee1  mov     edx, 9; TokenInformationClass
0x18002aee6  call    cs:__imp_GetTokenInformation
0x18002aeec  test    eax, eax
0x18002aeee  jz      loc_18002AE05
0x18002aef4  xor     ebx, ebx
0x18002aef6  cmp     [rbp+57h+var_BC], 1
0x18002aefa  jnz     loc_18002ADAC
0x18002af00  lea     rcx, [rbp+57h+var_D0]; unsigned int *
0x18002af04  call    ?WxGetProcessSessionId@@YAJPEAK@Z; WxGetProcessSessionId(ulong *)
0x18002af09  mov     ebx, eax
0x18002af0b  test    eax, eax
0x18002af0d  jns     short loc_18002AF29
0x18002af0f  mov     [rbp+57h+var_D4], 105h
0x18002af16  jmp     loc_18002ACC9
0x18002af1b  movzx   ebx, ax
0x18002af1e  or      ebx, 80070000h
0x18002af24  jmp     loc_18002AE15
0x18002af29  mov     rcx, [rbp+57h+TokenHandle]; void *
0x18002af2d  lea     rdx, [rsp+120h+var_F0]; unsigned int *
0x18002af32  call    ?WxGetTokenSessionId@@YAJPEAXPEAK@Z; WxGetTokenSessionId(void *,ulong *)
0x18002af37  mov     ebx, eax
0x18002af39  test    eax, eax
0x18002af3b  jns     short loc_18002AF49
0x18002af3d  mov     [rbp+57h+var_D4], 108h
0x18002af44  jmp     loc_18002ACC9
0x18002af49  mov     edi, [rsp+120h+var_F0]
0x18002af4d  cmp     [rbp+57h+var_D0], edi
0x18002af50  jz      loc_18002ADAC
0x18002af56  mov     ecx, 2; ImpersonationLevel
0x18002af5b  call    cs:__imp_ImpersonateSelf
0x18002af61  test    eax, eax
0x18002af63  jz      loc_18002AE26
0x18002af69  test    byte ptr cs:xmmword_180113B20+3, 20h
0x18002af70  jz      loc_18002AD69
0x18002af76  mov     r9d, [rbp+57h+var_D0]
0x18002af7a  mov     dword ptr [rsp+120h+ReturnLength], edi
0x18002af7e  call    WPP_SF_DD
0x18002af83  jmp     loc_18002AD69
0x18002af88  movzx   ebx, ax
0x18002af8b  or      ebx, 80070000h
0x18002af91  jmp     loc_18002AE36
0x18002af96  movzx   ebx, ax
0x18002af99  or      ebx, 80070000h
0x18002af9f  jmp     loc_18002AE57
```
