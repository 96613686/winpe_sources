# WscServiceUtils::CreateExternalBaseFromCaller(void *,CThirdPartyManager *,CSecurityVerificationManager *,CExternalBase * *)

- ea: `0x180019850`
- end: `0x180019dfa`
- name: `?CreateExternalBaseFromCaller@WscServiceUtils@@YAJPEAXPEAVCThirdPartyManager@@PEAVCSecurityVerificationManager@@PEAPEAVCExternalBase@@@Z`
- size: `1450`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE ClientBinding, void *, struct CThirdPartyManager *, struct CExternalBase **)`
- caller_count: `7`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180024630`
- `0x180024b40`
- `0x1800250c0`
- `0x180025520`
- `0x180026450`
- `0x1800337d0`
- `0x180033c60`

## callees

- `0x180005710`
- `0x180008e48`
- `0x180019850`
- `0x1800202e8`
- `0x180029e74`
- `0x18002b1ac`
- `0x18002fbb4`
- `0x18003fc30`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019ab0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019ccd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019ab0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019ccd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019b83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019c21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019b83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019c21`
- `RPCRT4!RpcRevertToSelf` at `0x180019a45`
- `RPCRT4!RpcRevertToSelf` at `0x180019a45`
- `RPCRT4!RpcImpersonateClient` at `0x1800198b7`
- `RPCRT4!RpcImpersonateClient` at `0x1800198b7`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x1800199ea`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x1800199ea`
- `RPCRT4!RpcRaiseException` at `0x180019c8c`
- `RPCRT4!RpcRaiseException` at `0x180019c8c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019907`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019907`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180019966`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180019966`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800198f5`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001997c`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800198f5`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001997c`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180019990`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180019990`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180019bb7`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180019bb7`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180019be0`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180019be0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800198dc`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800198dc`

## pseudocode

```c
__int64 __fastcall WscServiceUtils::CreateExternalBaseFromCaller(
        RPC_BINDING_HANDLE ClientBinding,
        void *a2,
        struct CThirdPartyManager *a3,
        struct CExternalBase **a4)
{
  CSecurityVerificationManager *v5; // r12
  unsigned int v8; // eax
  unsigned int v9; // r14d
  unsigned __int16 *v10; // rsi
  int ExternalBaseFromPESettings; // edi
  bool v12; // sf
  unsigned int v14; // eax
  DWORD v15; // eax
  unsigned __int64 v16; // rax
  unsigned __int64 v17; // rbx
  unsigned __int64 v18; // rax
  unsigned __int16 *v19; // rax
  unsigned __int16 *v20; // r12
  __int64 v21; // rcx
  WCHAR *v22; // rdx
  WCHAR *v23; // r8
  WCHAR v24; // ax
  WCHAR *v25; // rcx
  HANDLE v26; // rax
  void *v27; // r13
  __int64 v28; // rax
  DWORD v29; // eax
  DWORD LastError; // eax
  WINBOOL IsMember; // [rsp+60h] [rbp-A0h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-98h] BYREF
  struct CThirdPartyManager *v33; // [rsp+70h] [rbp-90h]
  int RpcCallAttributes; // [rsp+80h] [rbp-80h] BYREF
  __int64 v35; // [rsp+84h] [rbp-7Ch]
  int v36; // [rsp+8Ch] [rbp-74h]
  __int128 v37; // [rsp+90h] [rbp-70h]
  __int128 v38; // [rsp+A0h] [rbp-60h]
  __int128 v39; // [rsp+B0h] [rbp-50h]
  DWORD dwProcessId[4]; // [rsp+C0h] [rbp-40h]
  __int128 v41; // [rsp+D0h] [rbp-30h]
  __int128 v42; // [rsp+E0h] [rbp-20h]
  __int64 v43; // [rsp+F0h] [rbp-10h]
  PSID Sid[2]; // [rsp+100h] [rbp+0h] BYREF
  WCHAR ExeName[268]; // [rsp+110h] [rbp+10h] BYREF

  v5 = a3;
  v33 = a3;
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids);
  if ( !a4 )
    return 2147942487LL;
  v8 = RpcImpersonateClient(ClientBinding);
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_58c7d8ca840131a6c20521327163655c_Traceguids, v8);
    }
    RpcRaiseException(5);
  }
  IsMember = 0;
  Sid[0] = 0;
  if ( ConvertStringSidToSidW(L"S-1-5-80-1913148863-3492339771-4165695881-2087618961-4109116736", Sid) )
  {
    if ( !CheckTokenMembership(0, Sid[0], &IsMember) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_58c7d8ca840131a6c20521327163655c_Traceguids, LastError);
      }
      IsMember = 0;
    }
    LocalFree(Sid[0]);
  }
  else
  {
    v15 = GetLastError();
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_58c7d8ca840131a6c20521327163655c_Traceguids, v15);
    }
  }
  if ( IsMember )
  {
    v9 = (*(__int64 (__fastcall **)(void *, struct CExternalBase **))(*(_QWORD *)a2 + 8LL))(a2, a4);
  }
  else
  {
    IsMember = 0;
    LODWORD(Sid[0]) = 0;
    WORD2(Sid[0]) = 1280;
    SidToCheck = 0;
    if ( AllocateAndInitializeSid((PSID_IDENTIFIER_AUTHORITY)Sid, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck) )
    {
      if ( !CheckTokenMembership(0, SidToCheck, &IsMember) )
        IsMember = 0;
      FreeSid(SidToCheck);
    }
    if ( IsMember )
    {
      if ( !ClientBinding )
      {
        LOWORD(ExternalBaseFromPESettings) = 87;
LABEL_24:
        v9 = (unsigned __int16)ExternalBaseFromPESettings;
        goto LABEL_25;
      }
      v9 = 0;
      v10 = 0;
      RpcCallAttributes = 2;
      v35 = 16;
      v36 = 0;
      v37 = 0;
      v38 = 0;
      v39 = 0;
      *(_OWORD *)dwProcessId = 0;
      v41 = 0;
      v42 = 0;
      v43 = 0;
      ExternalBaseFromPESettings = RpcServerInqCallAttributesW(ClientBinding, &RpcCallAttributes);
      if ( !ExternalBaseFromPESettings )
      {
        v26 = OpenProcess(0x1000u, 0, dwProcessId[0]);
        v27 = v26;
        if ( v26 )
        {
          v17 = 260;
          IsMember = 260;
          if ( QueryFullProcessImageNameW(v26, 0, ExeName, (PDWORD)&IsMember) )
          {
            if ( !IsMember )
            {
              ExternalBaseFromPESettings = 3;
              CloseHandle(v27);
              goto LABEL_17;
            }
            if ( (unsigned int)IsMember > 0x103 )
            {
              ExternalBaseFromPESettings = 111;
            }
            else
            {
              v28 = -1;
              do
                ++v28;
              while ( ExeName[v28] );
              v16 = v28 + 1;
              if ( v16 >= 0x104 )
              {
                if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                {
                  WPP_SF_dd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    10,
                    WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids,
                    (unsigned int)v16,
                    260);
                }
              }
              else
              {
                v17 = v16;
              }
              v18 = 2 * v17;
              if ( !is_mul_ok(v17, 2u) )
                v18 = -1;
              v19 = (unsigned __int16 *)operator new[](v18, (const struct std::nothrow_t *)&std::nothrow);
              v20 = v19;
              if ( v19 )
              {
                if ( v17 )
                {
                  v21 = 2147483646;
                  v22 = ExeName;
                  v23 = v19;
                  do
                  {
                    if ( !v21 )
                      break;
                    v24 = *v22;
                    if ( !*v22 )
                      break;
                    ++v22;
                    *v23++ = v24;
                    --v21;
                    --v17;
                  }
                  while ( v17 );
                  v25 = v23 - 1;
                  if ( v17 )
                    v25 = v23;
                  *v25 = 0;
                  v10 = v20;
                  LOWORD(ExternalBaseFromPESettings) = 0;
                }
                else
                {
                  LOWORD(ExternalBaseFromPESettings) = 87;
                  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      11,
                      WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids,
                      2147942487LL);
                  }
                  operator delete(v20);
                }
              }
              else
              {
                if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids);
                }
                LOWORD(ExternalBaseFromPESettings) = 14;
              }
              ExternalBaseFromPESettings = (unsigned __int16)ExternalBaseFromPESettings;
              v5 = v33;
            }
          }
          else
          {
            v29 = GetLastError();
            if ( !v29 )
              v29 = 3;
            ExternalBaseFromPESettings = v29;
          }
          CloseHandle(v27);
          goto LABEL_17;
        }
        ExternalBaseFromPESettings = GetLastError();
        if ( !ExternalBaseFromPESettings )
        {
          LOWORD(ExternalBaseFromPESettings) = 110;
LABEL_72:
          ExternalBaseFromPESettings = (unsigned __int16)ExternalBaseFromPESettings | 0x80070000;
          v12 = ExternalBaseFromPESettings < 0;
LABEL_18:
          if ( !v12 )
          {
            ExternalBaseFromPESettings = CSecurityVerificationManager::CreateExternalBaseFromPESettings(v5, v10, a4);
            operator delete(v10);
          }
          if ( ExternalBaseFromPESettings >= 0 )
            goto LABEL_25;
          goto LABEL_24;
        }
      }
LABEL_17:
      v12 = ExternalBaseFromPESettings < 0;
      if ( ExternalBaseFromPESettings <= 0 )
        goto LABEL_18;
      goto LABEL_72;
    }
    v9 = 5;
  }
LABEL_25:
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids, v9);
  v14 = RpcRevertToSelf();
  if ( v14
    && WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_58c7d8ca840131a6c20521327163655c_Traceguids, v14);
  }
  return v9;
}

```

## disassembly

```asm
0x180019850  push    rbp
0x180019852  push    rbx
0x180019853  push    rsi
0x180019854  push    rdi
0x180019855  push    r12
0x180019857  push    r13
0x180019859  push    r14
0x18001985b  push    r15
0x18001985d  lea     rbp, [rsp-238h]
0x180019865  sub     rsp, 338h
0x18001986c  mov     rax, cs:__security_cookie
0x180019873  xor     rax, rsp
0x180019876  mov     [rbp+270h+var_48], rax
0x18001987d  mov     r15, r9
0x180019880  mov     r12, r8
0x180019883  mov     [rsp+370h+var_300], r8
0x180019888  mov     rdi, rdx
0x18001988b  mov     rbx, rcx
0x18001988e  lea     rsi, WPP_GLOBAL_Control
0x180019895  mov     rcx, cs:WPP_GLOBAL_Control
0x18001989c  cmp     rcx, rsi
0x18001989f  jz      short loc_1800198AB
0x1800198a1  test    byte ptr [rcx+1Ch], 8
0x1800198a5  jnz     loc_180019C43
0x1800198ab  test    r15, r15
0x1800198ae  jz      loc_180019A29
0x1800198b4  mov     rcx, rbx; BindingHandle
0x1800198b7  call    cs:__imp_RpcImpersonateClient
0x1800198bd  test    eax, eax
0x1800198bf  jnz     loc_180019C5D
0x1800198c5  xor     r13d, r13d
0x1800198c8  mov     [rsp+370h+IsMember], r13d
0x1800198cd  mov     [rbp+270h+Sid], r13
0x1800198d1  lea     rdx, [rbp+270h+Sid]; Sid
0x1800198d5  lea     rcx, StringSid; "S-1-5-80-1913148863-3492339771-41656958"...
0x1800198dc  call    cs:__imp_ConvertStringSidToSidW
0x1800198e2  test    eax, eax
0x1800198e4  jz      loc_180019AB0
0x1800198ea  lea     r8, [rsp+370h+IsMember]; IsMember
0x1800198ef  mov     rdx, [rbp+270h+Sid]; SidToCheck
0x1800198f3  xor     ecx, ecx; TokenHandle
0x1800198f5  call    cs:__imp_CheckTokenMembership
0x1800198fb  test    eax, eax
0x1800198fd  jz      loc_180019C93
0x180019903  mov     rcx, [rbp+270h+Sid]; hMem
0x180019907  call    cs:__imp_LocalFree
0x18001990d  cmp     [rsp+370h+IsMember], r13d
0x180019912  jnz     loc_180019A79
0x180019918  mov     [rsp+370h+IsMember], r13d
0x18001991d  mov     dword ptr [rbp+270h+Sid], r13d
0x180019921  mov     word ptr [rbp+270h+Sid+4], 500h
0x180019927  mov     [rsp+370h+SidToCheck], r13
0x18001992c  lea     rax, [rsp+370h+SidToCheck]
0x180019931  mov     [rsp+370h+pSid], rax; pSid
0x180019936  mov     [rsp+370h+nSubAuthority7], r13d; nSubAuthority7
0x18001993b  mov     [rsp+370h+nSubAuthority6], r13d; nSubAuthority6
0x180019940  mov     [rsp+370h+nSubAuthority5], r13d; nSubAuthority5
0x180019945  mov     [rsp+370h+nSubAuthority4], r13d; nSubAuthority4
0x18001994a  mov     [rsp+370h+nSubAuthority3], r13d; nSubAuthority3
0x18001994f  mov     [rsp+370h+nSubAuthority2], r13d; nSubAuthority2
0x180019954  mov     r9d, 220h; nSubAuthority1
0x18001995a  mov     r8d, 20h ; ' '; nSubAuthority0
0x180019960  mov     dl, 2; nSubAuthorityCount
0x180019962  lea     rcx, [rbp+270h+Sid]; pIdentifierAuthority
0x180019966  call    cs:__imp_AllocateAndInitializeSid
0x18001996c  test    eax, eax
0x18001996e  jz      short loc_180019996
0x180019970  lea     r8, [rsp+370h+IsMember]; IsMember
0x180019975  mov     rdx, [rsp+370h+SidToCheck]; SidToCheck
0x18001997a  xor     ecx, ecx; TokenHandle
0x18001997c  call    cs:__imp_CheckTokenMembership
0x180019982  test    eax, eax
0x180019984  jnz     short loc_18001998B
0x180019986  mov     [rsp+370h+IsMember], r13d
0x18001998b  mov     rcx, [rsp+370h+SidToCheck]; pSid
0x180019990  call    cs:__imp_FreeSid
0x180019996  cmp     [rsp+370h+IsMember], r13d
0x18001999b  jz      loc_180019DB8
0x1800199a1  test    rbx, rbx
0x1800199a4  jz      loc_180019A30
0x1800199aa  mov     r14d, r13d
0x1800199ad  mov     rsi, r13
0x1800199b0  mov     [rbp+270h+RpcCallAttributes], 2
0x1800199b7  mov     [rbp+270h+var_2EC], 10h
0x1800199bf  xor     eax, eax
0x1800199c1  mov     [rbp+270h+var_2E4], eax
0x1800199c4  xorps   xmm0, xmm0
0x1800199c7  movups  [rbp+270h+var_2E0], xmm0
0x1800199cb  movups  [rbp+270h+var_2D0], xmm0
0x1800199cf  movups  [rbp+270h+var_2C0], xmm0
0x1800199d3  movups  xmmword ptr [rbp+270h+dwProcessId], xmm0
0x1800199d7  movups  [rbp+270h+var_2A0], xmm0
0x1800199db  movups  [rbp+270h+var_290], xmm0
0x1800199df  mov     [rbp+270h+var_280], rax
0x1800199e3  lea     rdx, [rbp+270h+RpcCallAttributes]; RpcCallAttributes
0x1800199e7  mov     rcx, rbx; ClientBinding
0x1800199ea  call    cs:__imp_RpcServerInqCallAttributesW
0x1800199f0  mov     edi, eax
0x1800199f2  test    eax, eax
0x1800199f4  jz      loc_180019BAC
0x1800199fa  test    edi, edi
0x1800199fc  jg      loc_180019CE2
0x180019a02  js      short loc_180019A1C
0x180019a04  mov     r8, r15; struct CExternalBase **
0x180019a07  mov     rdx, rsi; unsigned __int16 *
0x180019a0a  mov     rcx, r12; this
0x180019a0d  call    ?CreateExternalBaseFromPESettings@CSecurityVerificationManager@@QEAAJPEAGPEAPEAVCExternalBase@@@Z; CSecurityVerificationManager::CreateExternalBaseFromPESettings(ushort *,CExternalBase * *)
0x180019a12  mov     edi, eax
0x180019a14  mov     rcx, rsi; Block
0x180019a17  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180019a1c  lea     rsi, WPP_GLOBAL_Control
0x180019a23  test    edi, edi
0x180019a25  jns     short loc_180019A39
0x180019a27  jmp     short loc_180019A35
0x180019a29  mov     eax, 80070057h
0x180019a2e  jmp     short loc_180019A56
0x180019a30  mov     edi, 80070057h
0x180019a35  movzx   r14d, di
0x180019a39  mov     rcx, cs:WPP_GLOBAL_Control
0x180019a40  cmp     rcx, rsi
0x180019a43  jnz     short loc_180019A90
0x180019a45  call    cs:__imp_RpcRevertToSelf
0x180019a4b  test    eax, eax
0x180019a4d  jnz     loc_180019DC3
0x180019a53  mov     eax, r14d
0x180019a56  mov     rcx, [rbp+270h+var_48]
0x180019a5d  xor     rcx, rsp; StackCookie
0x180019a60  call    __security_check_cookie
0x180019a65  add     rsp, 338h
0x180019a6c  pop     r15
0x180019a6e  pop     r14
0x180019a70  pop     r13
0x180019a72  pop     r12
0x180019a74  pop     rdi
0x180019a75  pop     rsi
0x180019a76  pop     rbx
0x180019a77  pop     rbp
0x180019a78  retn
0x180019a79  mov     rax, [rdi]
0x180019a7c  mov     rdx, r15
0x180019a7f  mov     rcx, rdi
0x180019a82  mov     rax, [rax+8]
0x180019a86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a8b  mov     r14d, eax
0x180019a8e  jmp     short loc_180019A39
0x180019a90  test    byte ptr [rcx+1Ch], 8
0x180019a94  jz      short loc_180019A45
0x180019a96  mov     edx, 0Bh
0x180019a9b  mov     r9d, r14d
0x180019a9e  lea     r8, WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids
0x180019aa5  mov     rcx, [rcx+10h]
0x180019aa9  call    WPP_SF_d
0x180019aae  jmp     short loc_180019A45
0x180019ab0  call    cs:__imp_GetLastError
0x180019ab6  mov     rcx, cs:WPP_GLOBAL_Control
0x180019abd  cmp     rcx, rsi
0x180019ac0  jz      loc_18001990D
0x180019ac6  test    byte ptr [rcx+1Ch], 1
0x180019aca  jz      loc_18001990D
0x180019ad0  mov     edx, 1Eh
0x180019ad5  mov     r9d, eax
0x180019ad8  lea     r8, WPP_58c7d8ca840131a6c20521327163655c_Traceguids
0x180019adf  mov     rcx, [rcx+10h]
0x180019ae3  call    WPP_SF_d
0x180019ae8  jmp     loc_18001990D
0x180019aed  inc     rax
0x180019af0  cmp     rax, rbx
0x180019af3  jnb     loc_180019CFC
0x180019af9  mov     rbx, rax
0x180019afc  mov     eax, 2
0x180019b01  mul     rbx
0x180019b04  cmovb   rax, rdi
0x180019b08  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180019b0f  mov     rcx, rax; unsigned __int64
0x180019b12  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180019b17  mov     r12, rax
0x180019b1a  test    rax, rax
0x180019b1d  jz      short loc_180019B8E
0x180019b1f  test    rbx, rbx
0x180019b22  jz      loc_180019D45
0x180019b28  cmp     rbx, 7FFFFFFFh
0x180019b2f  ja      loc_180019D3E
0x180019b35  mov     ecx, 7FFFFFFEh
0x180019b3a  lea     rdx, [rbp+270h+ExeName]
0x180019b3e  mov     r8, rax
0x180019b41  test    rcx, rcx
0x180019b44  jz      short loc_180019B63
0x180019b46  movzx   eax, word ptr [rdx]
0x180019b49  test    ax, ax
0x180019b4c  jz      short loc_180019B63
0x180019b4e  add     rdx, 2
0x180019b52  mov     [r8], ax
0x180019b56  add     r8, 2
0x180019b5a  dec     rcx
0x180019b5d  sub     rbx, 1
0x180019b61  jnz     short loc_180019B41
0x180019b63  lea     rcx, [r8-2]
0x180019b67  test    rbx, rbx
0x180019b6a  cmovnz  rcx, r8
0x180019b6e  xor     eax, eax
0x180019b70  mov     [rcx], ax
0x180019b73  mov     rsi, r12
0x180019b76  xor     edi, edi
0x180019b78  movzx   edi, di
0x180019b7b  mov     r12, [rsp+370h+var_300]
0x180019b80  mov     rcx, r13; hObject
0x180019b83  call    cs:__imp_CloseHandle
0x180019b89  jmp     loc_1800199FA
0x180019b8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180019b95  lea     rax, WPP_GLOBAL_Control
0x180019b9c  cmp     rcx, rax
0x180019b9f  jnz     loc_180019D94
0x180019ba5  mov     edi, 8007000Eh
0x180019baa  jmp     short loc_180019B78
0x180019bac  mov     r8d, [rbp+270h+dwProcessId]; dwProcessId
0x180019bb0  xor     edx, edx; bInheritHandle
0x180019bb2  mov     ecx, 1000h; dwDesiredAccess
0x180019bb7  call    cs:__imp_OpenProcess
0x180019bbd  mov     r13, rax
0x180019bc0  test    rax, rax
0x180019bc3  jz      loc_180019CCD
0x180019bc9  mov     ebx, 104h
0x180019bce  mov     [rsp+370h+IsMember], ebx
0x180019bd2  lea     r9, [rsp+370h+IsMember]; lpdwSize
0x180019bd7  lea     r8, [rbp+270h+ExeName]; lpExeName
0x180019bdb  xor     edx, edx; dwFlags
0x180019bdd  mov     rcx, rax; hProcess
0x180019be0  call    cs:__imp_QueryFullProcessImageNameW
0x180019be6  test    eax, eax
0x180019be8  jz      short loc_180019C2C
0x180019bea  mov     eax, [rsp+370h+IsMember]
0x180019bee  test    eax, eax
0x180019bf0  jz      short loc_180019C19
0x180019bf2  cmp     eax, 103h
0x180019bf7  ja      loc_180019CF2
0x180019bfd  lea     rcx, [rbp+270h+ExeName]
0x180019c01  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180019c08  mov     rax, rdi
0x180019c0b  inc     rax
0x180019c0e  cmp     [rcx+rax*2], si
0x180019c12  jnz     short loc_180019C0B
0x180019c14  jmp     loc_180019AED
0x180019c19  mov     edi, 3
0x180019c1e  mov     rcx, r13; hObject
0x180019c21  call    cs:__imp_CloseHandle
0x180019c27  jmp     loc_1800199FA
0x180019c2c  call    cs:__imp_GetLastError
0x180019c32  mov     edi, 3
0x180019c37  test    eax, eax
0x180019c39  cmovz   eax, edi
0x180019c3c  mov     edi, eax
0x180019c3e  jmp     loc_180019B80
0x180019c43  mov     edx, 0Ah
0x180019c48  lea     r8, WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids
0x180019c4f  mov     rcx, [rcx+10h]
0x180019c53  call    WPP_SF_
0x180019c58  jmp     loc_1800198AB
0x180019c5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180019c64  cmp     rcx, rsi
0x180019c67  jz      short loc_180019C87
0x180019c69  test    byte ptr [rcx+1Ch], 1
0x180019c6d  jz      short loc_180019C87
0x180019c6f  mov     edx, 1Bh
0x180019c74  mov     r9d, eax
0x180019c77  lea     r8, WPP_58c7d8ca840131a6c20521327163655c_Traceguids
0x180019c7e  mov     rcx, [rcx+10h]
0x180019c82  call    WPP_SF_d
0x180019c87  mov     ecx, 5; exception
0x180019c8c  call    cs:__imp_RpcRaiseException
0x180019c92  nop
0x180019c93  call    cs:__imp_GetLastError
0x180019c99  mov     rcx, cs:WPP_GLOBAL_Control
0x180019ca0  cmp     rcx, rsi
0x180019ca3  jz      short loc_180019CC3
0x180019ca5  test    byte ptr [rcx+1Ch], 1
0x180019ca9  jz      short loc_180019CC3
0x180019cab  mov     edx, 1Dh
0x180019cb0  mov     r9d, eax
0x180019cb3  lea     r8, WPP_58c7d8ca840131a6c20521327163655c_Traceguids
0x180019cba  mov     rcx, [rcx+10h]
0x180019cbe  call    WPP_SF_d
0x180019cc3  mov     [rsp+370h+IsMember], r13d
0x180019cc8  jmp     loc_180019903
0x180019ccd  call    cs:__imp_GetLastError
0x180019cd3  mov     edi, eax
0x180019cd5  test    eax, eax
0x180019cd7  jnz     loc_1800199FA
0x180019cdd  mov     edi, 6Eh ; 'n'
0x180019ce2  movzx   edi, di
0x180019ce5  or      edi, 80070000h
0x180019ceb  test    edi, edi
0x180019ced  jmp     loc_180019A02
0x180019cf2  mov     edi, 6Fh ; 'o'
0x180019cf7  jmp     loc_180019B80
0x180019cfc  mov     rcx, cs:WPP_GLOBAL_Control
0x180019d03  lea     rdx, WPP_GLOBAL_Control
0x180019d0a  cmp     rcx, rdx
0x180019d0d  jz      loc_180019AFC
0x180019d13  test    byte ptr [rcx+1Ch], 4
0x180019d17  jz      loc_180019AFC
  ... truncated ...
```
