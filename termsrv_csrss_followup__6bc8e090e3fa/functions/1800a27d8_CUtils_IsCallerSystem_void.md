# CUtils::IsCallerSystem(void)

- ea: `0x1800a27d8`
- end: `0x1800a2b65`
- name: `?IsCallerSystem@CUtils@@SAJXZ`
- size: `909`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18003a660`
- `0x18005d790`
- `0x180061fd0`

## callees

- `0x180009940`
- `0x18003028c`
- `0x180033f60`
- `0x1800a27d8`
- `0x1800a3808`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a28c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a28c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a284f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a28e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2932`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a29d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2a7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2aa3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a284f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a28e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2932`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a29d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2a7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2aa3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a281f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a281f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800a283c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800a283c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a2b03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a2b03`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a2a18`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a2a18`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a2b28`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a2b3c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a2b28`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a2b3c`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x1800a2969`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x1800a2969`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800a29bc`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800a2a6d`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800a29bc`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800a2a6d`
- `api-ms-win-security-base-l1-1-0!IsTokenRestricted` at `0x1800a28d0`
- `api-ms-win-security-base-l1-1-0!IsTokenRestricted` at `0x1800a28d0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800a2922`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800a2922`

## string_xrefs

- `0x1800a286a`: `IsCallerSystem: Could not open thread token %x`
- `0x1800a2ae8`: `IsCallerSystem: Token is restricted %x`
- `0x1800a2904`: `IsCallerSystem: IsTokenRestricted failed %x`
- `0x1800a29ef`: `IsCallerSystem: Token access check probe failed %x`
- `0x1800a2949`: `IsCallerSystem: Could not convert security descriptor string %x`
- `0x1800a2a31`: `IsCallerSystem: Failed to allocate privilege set %x`
- `0x1800a2a07`: `IsCallerSystem: AccessCheck probe returned privilege set size of 0 unexpectedly %x`
- `0x1800a2aba`: `IsCallerSystem: Token access denied %x`
- `0x1800a2a94`: `IsCallerSystem: Token access check failed %x`
- `0x1800a2ac9`: `IsCallerSystem: Token missing required right`
- `0x1800a28aa`: `IsTokenSid( System ) failed: 0x%x in %s`

## pseudocode

```c
__int64 CUtils::IsCallerSystem(void)
{
  struct _PRIVILEGE_SET *v0; // rsi
  HANDLE CurrentThread; // rax
  signed int v2; // eax
  unsigned int v3; // ebx
  int IsTokenSid; // eax
  signed int LastError; // eax
  signed int v6; // eax
  signed int v7; // eax
  signed int v8; // eax
  signed int v9; // eax
  DWORD PrivilegeSetLength; // [rsp+40h] [rbp-19h] BYREF
  WINBOOL AccessStatus; // [rsp+44h] [rbp-15h] BYREF
  DWORD AccessMask; // [rsp+48h] [rbp-11h] BYREF
  DWORD GrantedAccess; // [rsp+4Ch] [rbp-Dh] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-9h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+58h] [rbp-1h] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+60h] [rbp+7h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+70h] [rbp+17h] BYREF

  v0 = 0;
  TokenHandle = 0;
  PrivilegeSetLength = 0;
  GrantedAccess = 0;
  SecurityDescriptor = 0;
  AccessMask = 0x40000000;
  CurrentThread = GetCurrentThread();
  AccessStatus = OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle);
  if ( AccessStatus )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_IsCallerSystemAccessCheck>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_IsCallerSystemAccessCheck>::GetImpl'::`2'::impl) )
    {
      SetLastError(0);
      if ( IsTokenRestricted(TokenHandle) )
      {
        v3 = -2147024891;
        _DbgPrintMessage(8, "IsCallerSystem: Token is restricted %x", 2147942405LL);
      }
      else
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
        if ( v3 )
        {
          _DbgPrintMessage(8, "IsCallerSystem: IsTokenRestricted failed %x", v3);
          goto LABEL_38;
        }
        if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
               L"O:SYG:BAD:(A;;0x1;;;SY)",
               1u,
               &SecurityDescriptor,
               0) )
        {
          GenericMapping = (struct _GENERIC_MAPPING)xmmword_180105DB0;
          MapGenericMask(&AccessMask, &GenericMapping);
          memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
          PrivilegeSetLength = 20;
          if ( AccessCheck(
                 SecurityDescriptor,
                 TokenHandle,
                 AccessMask,
                 &GenericMapping,
                 &PrivilegeSet,
                 &PrivilegeSetLength,
                 &GrantedAccess,
                 &AccessStatus) )
          {
            goto LABEL_30;
          }
          v7 = GetLastError();
          v3 = v7;
          if ( v7 > 0 )
            v3 = (unsigned __int16)v7 | 0x80070000;
          if ( v3 != -2147024774 )
          {
            _DbgPrintMessage(8, "IsCallerSystem: Token access check probe failed %x", v3);
            goto LABEL_38;
          }
          if ( !PrivilegeSetLength )
          {
            v3 = -2147418113;
            _DbgPrintMessage(
              8,
              "IsCallerSystem: AccessCheck probe returned privilege set size of 0 unexpectedly %x",
              2147549183LL);
            goto LABEL_38;
          }
          v0 = (struct _PRIVILEGE_SET *)LocalAlloc(0, PrivilegeSetLength);
          if ( !v0 )
          {
            v3 = -2147024882;
            _DbgPrintMessage(8, "IsCallerSystem: Failed to allocate privilege set %x", 2147942414LL);
            goto LABEL_38;
          }
          if ( AccessCheck(
                 SecurityDescriptor,
                 TokenHandle,
                 AccessMask,
                 &GenericMapping,
                 v0,
                 &PrivilegeSetLength,
                 &GrantedAccess,
                 &AccessStatus) )
          {
LABEL_30:
            if ( AccessStatus )
            {
              if ( (GrantedAccess & 1) != 0 )
              {
                v3 = 0;
              }
              else
              {
                v3 = 1;
                _DbgPrintMessage(8, "IsCallerSystem: Token missing required right");
              }
            }
            else
            {
              v9 = GetLastError();
              v3 = v9;
              if ( v9 > 0 )
                v3 = (unsigned __int16)v9 | 0x80070000;
              _DbgPrintMessage(8, "IsCallerSystem: Token access denied %x", v3);
            }
          }
          else
          {
            v8 = GetLastError();
            v3 = v8;
            if ( v8 > 0 )
              v3 = (unsigned __int16)v8 | 0x80070000;
            _DbgPrintMessage(8, "IsCallerSystem: Token access check failed %x", v3);
          }
        }
        else
        {
          v6 = GetLastError();
          v3 = v6;
          if ( v6 > 0 )
            v3 = (unsigned __int16)v6 | 0x80070000;
          _DbgPrintMessage(8, "IsCallerSystem: Could not convert security descriptor string %x", v3);
        }
      }
    }
    else
    {
      IsTokenSid = CUtils::IsTokenSid(TokenHandle, CUtils::pSystemSid);
      v3 = IsTokenSid;
      if ( IsTokenSid < 0 )
        _DbgPrintMessage(8, "IsTokenSid( System ) failed: 0x%x in %s", IsTokenSid, "CUtils::IsCallerSystem");
    }
  }
  else
  {
    v2 = GetLastError();
    v3 = v2;
    if ( v2 > 0 )
      v3 = (unsigned __int16)v2 | 0x80070000;
    _DbgPrintMessage(8, "IsCallerSystem: Could not open thread token %x", v3);
  }
LABEL_38:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_IsCallerSystemAccessCheck>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_IsCallerSystemAccessCheck>::GetImpl'::`2'::impl) )
  {
    if ( SecurityDescriptor )
      LocalFree(SecurityDescriptor);
    if ( v0 )
      LocalFree(v0);
  }
  return v3;
}

```

## disassembly

```asm
0x1800a27d8  push    rbp
0x1800a27da  push    rbx
0x1800a27db  push    rsi
0x1800a27dc  push    rdi
0x1800a27dd  push    r15
0x1800a27df  lea     rbp, [rsp-37h]
0x1800a27e4  sub     rsp, 90h
0x1800a27eb  mov     rax, cs:__security_cookie
0x1800a27f2  xor     rax, rsp
0x1800a27f5  mov     [rbp+57h+var_28], rax
0x1800a27f9  xor     esi, esi
0x1800a27fb  mov     [rbp+57h+TokenHandle], 0
0x1800a2803  mov     [rbp+57h+var_70], esi
0x1800a2806  mov     [rbp+57h+var_64], esi
0x1800a2809  mov     [rbp+57h+var_6C], 0
0x1800a2810  mov     [rbp+57h+SecurityDescriptor], 0
0x1800a2818  mov     [rbp+57h+AccessMask], 40000000h
0x1800a281f  call    cs:__imp_GetCurrentThread
0x1800a2826  nop     dword ptr [rax+rax+00h]
0x1800a282b  lea     r15d, [rsi+8]
0x1800a282f  xor     r8d, r8d; OpenAsSelf
0x1800a2832  mov     rcx, rax; ThreadHandle
0x1800a2835  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1800a2839  mov     edx, r15d; DesiredAccess
0x1800a283c  call    cs:__imp_OpenThreadToken
0x1800a2843  nop     dword ptr [rax+rax+00h]
0x1800a2848  mov     [rbp+57h+var_6C], eax
0x1800a284b  test    eax, eax
0x1800a284d  jnz     short loc_1800A2876
0x1800a284f  call    cs:__imp_GetLastError
0x1800a2856  nop     dword ptr [rax+rax+00h]
0x1800a285b  mov     ebx, eax
0x1800a285d  test    eax, eax
0x1800a285f  jle     short loc_1800A286A
0x1800a2861  movzx   ebx, ax
0x1800a2864  or      ebx, 80070000h
0x1800a286a  lea     rdx, aIscallersystem_1; "IsCallerSystem: Could not open thread t"...
0x1800a2871  jmp     loc_1800A2AEF
0x1800a2876  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_IsCallerSystemAccessCheck@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_IsCallerSystemAccessCheck@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IsCallerSystemAccessCheck> `wil::Feature<__WilFeatureTraits_Feature_IsCallerSystemAccessCheck>::GetImpl(void)'::`2'::impl
0x1800a287d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_IsCallerSystemAccessCheck@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IsCallerSystemAccessCheck>::__private_IsEnabled(void)
0x1800a2882  test    al, al
0x1800a2884  jnz     short loc_1800A28BE
0x1800a2886  mov     rdx, cs:?pSystemSid@CUtils@@0PEAXEA; Sid2
0x1800a288d  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800a2891  call    ?IsTokenSid@CUtils@@CAJPEAX0@Z; CUtils::IsTokenSid(void *,void *)
0x1800a2896  mov     ebx, eax
0x1800a2898  test    eax, eax
0x1800a289a  jns     loc_1800A2AFA
0x1800a28a0  lea     r9, aCutilsIscaller; "CUtils::IsCallerSystem"
0x1800a28a7  mov     r8d, eax
0x1800a28aa  lea     rdx, aIstokensidSyst; "IsTokenSid( System ) failed: 0x%x in %s"
0x1800a28b1  mov     ecx, r15d; int
0x1800a28b4  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800a28b9  jmp     loc_1800A2AFA
0x1800a28be  xor     ecx, ecx; dwErrCode
0x1800a28c0  call    cs:__imp_SetLastError
0x1800a28c7  nop     dword ptr [rax+rax+00h]
0x1800a28cc  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800a28d0  call    cs:__imp_IsTokenRestricted
0x1800a28d7  nop     dword ptr [rax+rax+00h]
0x1800a28dc  test    eax, eax
0x1800a28de  jnz     loc_1800A2AE3
0x1800a28e4  call    cs:__imp_GetLastError
0x1800a28eb  nop     dword ptr [rax+rax+00h]
0x1800a28f0  mov     ebx, eax
0x1800a28f2  mov     edi, 80070000h
0x1800a28f7  test    eax, eax
0x1800a28f9  jle     short loc_1800A2900
0x1800a28fb  movzx   ebx, ax
0x1800a28fe  or      ebx, edi
0x1800a2900  test    ebx, ebx
0x1800a2902  jz      short loc_1800A2910
0x1800a2904  lea     rdx, aIscallersystem_6; "IsCallerSystem: IsTokenRestricted faile"...
0x1800a290b  jmp     loc_1800A2AEF
0x1800a2910  xor     r9d, r9d; SecurityDescriptorSize
0x1800a2913  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1800a2917  lea     rcx, StringSecurityDescriptor; "O:SYG:BAD:(A;;0x1;;;SY)"
0x1800a291e  lea     edx, [r9+1]; StringSDRevision
0x1800a2922  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800a2929  nop     dword ptr [rax+rax+00h]
0x1800a292e  test    eax, eax
0x1800a2930  jnz     short loc_1800A2955
0x1800a2932  call    cs:__imp_GetLastError
0x1800a2939  nop     dword ptr [rax+rax+00h]
0x1800a293e  mov     ebx, eax
0x1800a2940  test    eax, eax
0x1800a2942  jle     short loc_1800A2949
0x1800a2944  movzx   ebx, ax
0x1800a2947  or      ebx, edi
0x1800a2949  lea     rdx, aIscallersystem_3; "IsCallerSystem: Could not convert secur"...
0x1800a2950  jmp     loc_1800A2AEF
0x1800a2955  movups  xmm0, cs:xmmword_180105DB0
0x1800a295c  lea     rdx, [rbp+57h+GenericMapping]; GenericMapping
0x1800a2960  lea     rcx, [rbp+57h+AccessMask]; AccessMask
0x1800a2964  movdqu  xmmword ptr [rbp+57h+GenericMapping.GenericRead], xmm0
0x1800a2969  call    cs:__imp_MapGenericMask
0x1800a2970  nop     dword ptr [rax+rax+00h]
0x1800a2975  mov     r8d, [rbp+57h+AccessMask]; DesiredAccess
0x1800a2979  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x1800a297d  mov     rdx, [rbp+57h+TokenHandle]; ClientToken
0x1800a2981  xor     eax, eax
0x1800a2983  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x1800a2987  xorps   xmm0, xmm0
0x1800a298a  mov     [rbp+57h+var_40.Privilege.Attributes], eax
0x1800a298d  lea     rax, [rbp+57h+var_6C]
0x1800a2991  mov     [rsp+0B0h+AccessStatus], rax; AccessStatus
0x1800a2996  lea     rax, [rbp+57h+var_64]
0x1800a299a  mov     [rsp+0B0h+GrantedAccess], rax; GrantedAccess
0x1800a299f  lea     rax, [rbp+57h+var_70]
0x1800a29a3  mov     [rsp+0B0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x1800a29a8  lea     rax, [rbp+57h+var_40]
0x1800a29ac  mov     [rsp+0B0h+PrivilegeSet], rax; PrivilegeSet
0x1800a29b1  movups  xmmword ptr [rbp+57h+var_40.PrivilegeCount], xmm0
0x1800a29b5  mov     [rbp+57h+var_70], 14h
0x1800a29bc  call    cs:__imp_AccessCheck
0x1800a29c3  nop     dword ptr [rax+rax+00h]
0x1800a29c8  test    eax, eax
0x1800a29ca  jnz     loc_1800A2A9D
0x1800a29d0  call    cs:__imp_GetLastError
0x1800a29d7  nop     dword ptr [rax+rax+00h]
0x1800a29dc  mov     ebx, eax
0x1800a29de  test    eax, eax
0x1800a29e0  jle     short loc_1800A29E7
0x1800a29e2  movzx   ebx, ax
0x1800a29e5  or      ebx, edi
0x1800a29e7  cmp     ebx, 8007007Ah
0x1800a29ed  jz      short loc_1800A29FB
0x1800a29ef  lea     rdx, aIscallersystem_2; "IsCallerSystem: Token access check prob"...
0x1800a29f6  jmp     loc_1800A2AEF
0x1800a29fb  mov     eax, [rbp+57h+var_70]
0x1800a29fe  test    eax, eax
0x1800a2a00  jnz     short loc_1800A2A13
0x1800a2a02  mov     ebx, 8000FFFFh
0x1800a2a07  lea     rdx, aIscallersystem_8; "IsCallerSystem: AccessCheck probe retur"...
0x1800a2a0e  jmp     loc_1800A2AEF
0x1800a2a13  mov     rdx, rax; uBytes
0x1800a2a16  xor     ecx, ecx; uFlags
0x1800a2a18  call    cs:__imp_LocalAlloc
0x1800a2a1f  nop     dword ptr [rax+rax+00h]
0x1800a2a24  mov     rsi, rax
0x1800a2a27  test    rax, rax
0x1800a2a2a  jnz     short loc_1800A2A3D
0x1800a2a2c  mov     ebx, 8007000Eh
0x1800a2a31  lea     rdx, aIscallersystem_7; "IsCallerSystem: Failed to allocate priv"...
0x1800a2a38  jmp     loc_1800A2AEF
0x1800a2a3d  mov     r8d, [rbp+57h+AccessMask]; DesiredAccess
0x1800a2a41  lea     rax, [rbp+57h+var_6C]
0x1800a2a45  mov     rdx, [rbp+57h+TokenHandle]; ClientToken
0x1800a2a49  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x1800a2a4d  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x1800a2a51  mov     [rsp+0B0h+AccessStatus], rax; AccessStatus
0x1800a2a56  lea     rax, [rbp+57h+var_64]
0x1800a2a5a  mov     [rsp+0B0h+GrantedAccess], rax; GrantedAccess
0x1800a2a5f  lea     rax, [rbp+57h+var_70]
0x1800a2a63  mov     [rsp+0B0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x1800a2a68  mov     [rsp+0B0h+PrivilegeSet], rsi; PrivilegeSet
0x1800a2a6d  call    cs:__imp_AccessCheck
0x1800a2a74  nop     dword ptr [rax+rax+00h]
0x1800a2a79  test    eax, eax
0x1800a2a7b  jnz     short loc_1800A2A9D
0x1800a2a7d  call    cs:__imp_GetLastError
0x1800a2a84  nop     dword ptr [rax+rax+00h]
0x1800a2a89  mov     ebx, eax
0x1800a2a8b  test    eax, eax
0x1800a2a8d  jle     short loc_1800A2A94
0x1800a2a8f  movzx   ebx, ax
0x1800a2a92  or      ebx, edi
0x1800a2a94  lea     rdx, aIscallersystem_5; "IsCallerSystem: Token access check fail"...
0x1800a2a9b  jmp     short loc_1800A2AEF
0x1800a2a9d  cmp     [rbp+57h+var_6C], 0
0x1800a2aa1  jnz     short loc_1800A2AC3
0x1800a2aa3  call    cs:__imp_GetLastError
0x1800a2aaa  nop     dword ptr [rax+rax+00h]
0x1800a2aaf  mov     ebx, eax
0x1800a2ab1  test    eax, eax
0x1800a2ab3  jle     short loc_1800A2ABA
0x1800a2ab5  movzx   ebx, ax
0x1800a2ab8  or      ebx, edi
0x1800a2aba  lea     rdx, aIscallersystem_0; "IsCallerSystem: Token access denied %x"
0x1800a2ac1  jmp     short loc_1800A2AEF
0x1800a2ac3  test    byte ptr [rbp+57h+var_64], 1
0x1800a2ac7  jnz     short loc_1800A2ADF
0x1800a2ac9  lea     rdx, aIscallersystem_4; "IsCallerSystem: Token missing required "...
0x1800a2ad0  mov     ecx, r15d; int
0x1800a2ad3  mov     ebx, 1
0x1800a2ad8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800a2add  jmp     short loc_1800A2AFA
0x1800a2adf  xor     ebx, ebx
0x1800a2ae1  jmp     short loc_1800A2AFA
0x1800a2ae3  mov     ebx, 80070005h
0x1800a2ae8  lea     rdx, aIscallersystem; "IsCallerSystem: Token is restricted %x"
0x1800a2aef  mov     r8d, ebx
0x1800a2af2  mov     ecx, r15d; int
0x1800a2af5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800a2afa  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x1800a2afe  test    rcx, rcx
0x1800a2b01  jz      short loc_1800A2B0F
0x1800a2b03  call    cs:__imp_CloseHandle
0x1800a2b0a  nop     dword ptr [rax+rax+00h]
0x1800a2b0f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_IsCallerSystemAccessCheck@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_IsCallerSystemAccessCheck@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IsCallerSystemAccessCheck> `wil::Feature<__WilFeatureTraits_Feature_IsCallerSystemAccessCheck>::GetImpl(void)'::`2'::impl
0x1800a2b16  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_IsCallerSystemAccessCheck@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IsCallerSystemAccessCheck>::__private_IsEnabled(void)
0x1800a2b1b  test    al, al
0x1800a2b1d  jz      short loc_1800A2B48
0x1800a2b1f  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x1800a2b23  test    rcx, rcx
0x1800a2b26  jz      short loc_1800A2B34
0x1800a2b28  call    cs:__imp_LocalFree
0x1800a2b2f  nop     dword ptr [rax+rax+00h]
0x1800a2b34  test    rsi, rsi
0x1800a2b37  jz      short loc_1800A2B48
0x1800a2b39  mov     rcx, rsi; hMem
0x1800a2b3c  call    cs:__imp_LocalFree
0x1800a2b43  nop     dword ptr [rax+rax+00h]
0x1800a2b48  mov     eax, ebx
0x1800a2b4a  mov     rcx, [rbp+57h+var_28]
0x1800a2b4e  xor     rcx, rsp; StackCookie
0x1800a2b51  call    __security_check_cookie
0x1800a2b56  add     rsp, 90h
0x1800a2b5d  pop     r15
0x1800a2b5f  pop     rdi
0x1800a2b60  pop     rsi
0x1800a2b61  pop     rbx
0x1800a2b62  pop     rbp
0x1800a2b63  retn
```
