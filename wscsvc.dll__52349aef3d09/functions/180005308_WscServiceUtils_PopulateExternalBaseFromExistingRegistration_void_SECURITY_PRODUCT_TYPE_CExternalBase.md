# WscServiceUtils::PopulateExternalBaseFromExistingRegistration(void *,_SECURITY_PRODUCT_TYPE,CExternalBase * *)

- ea: `0x180005308`
- end: `0x18000563e`
- name: `?PopulateExternalBaseFromExistingRegistration@WscServiceUtils@@YAJPEAXW4_SECURITY_PRODUCT_TYPE@@PEAPEAVCExternalBase@@@Z`
- size: `822`
- prototype: `__int64 __fastcall(WscServiceUtils *this, void *, struct CExternalBase **, struct CExternalBase **)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180003f80`

## callees

- `0x180005220`
- `0x180005308`
- `0x180005650`
- `0x180005710`
- `0x1800070f0`
- `0x180008e48`
- `0x18001abb0`
- `0x18001c780`
- `0x1800202e8`
- `0x180029e74`
- `0x180042010`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x1800053fc`
- `RPCRT4!RpcRevertToSelf` at `0x1800053fc`
- `RPCRT4!RpcImpersonateClient` at `0x180005383`
- `RPCRT4!RpcImpersonateClient` at `0x180005383`
- `RPCRT4!RpcRaiseException` at `0x1800055a7`
- `RPCRT4!RpcRaiseException` at `0x1800055a7`

## pseudocode

```c
__int64 __fastcall WscServiceUtils::PopulateExternalBaseFromExistingRegistration(
        WscServiceUtils *this,
        void *a2,
        struct CExternalBase **a3,
        struct CExternalBase **a4)
{
  CThirdPartyManager *v6; // r12
  CSecurityVerificationManager *v7; // r15
  unsigned int v8; // eax
  CRpcImpersonateClient *v9; // rcx
  int CallerProcessPath; // ebp
  signed int v11; // ebx
  unsigned int v12; // eax
  CThirdPartyManager *v13; // rcx
  bool v14; // sf
  int v15; // eax
  struct CExternalBase *v17; // rcx
  CThirdPartyManager *v18; // rcx
  void *Block; // [rsp+20h] [rbp-48h] BYREF
  struct CExternalBase *v20; // [rsp+88h] [rbp+20h] BYREF

  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi>::GetImpl'::`2'::impl,
    a2);
  if ( !a3 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids);
      v18 = WPP_GLOBAL_Control;
    }
    v11 = -2147024809;
    if ( v18 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)v18 + 2), 16, WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids, 2147942487LL);
    return (unsigned int)v11;
  }
  v20 = 0;
  *a3 = 0;
  v6 = WscServiceUtils::g_pAntiVirusManager;
  v7 = WscServiceUtils::g_pAntiVirusVerificationManager;
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids);
  Block = 0;
  v8 = RpcImpersonateClient(this);
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_58c7d8ca840131a6c20521327163655c_Traceguids, v8);
    }
    RpcRaiseException(5);
  }
  if ( (unsigned int)CRpcImpersonateClient::IsDefender(v9) )
  {
    v11 = (*(__int64 (__fastcall **)(CThirdPartyManager *, struct CExternalBase **))(*(_QWORD *)v6 + 8LL))(v6, &v20);
  }
  else if ( (unsigned int)RunningAsAdministrator() )
  {
    CallerProcessPath = CSecurityVerificationManager::GetCallerProcessPath(this, (unsigned __int16 **)&Block);
    if ( CallerProcessPath >= 0 )
    {
      CallerProcessPath = CSecurityVerificationManager::CreateExternalBaseFromPESettings(
                            v7,
                            (unsigned __int16 *)Block,
                            &v20);
      operator delete(Block);
    }
    v11 = (unsigned __int16)CallerProcessPath;
    if ( CallerProcessPath >= 0 )
      v11 = 0;
  }
  else
  {
    v11 = 5;
  }
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids,
      (unsigned int)v11);
  v12 = RpcRevertToSelf();
  if ( !v12 )
    goto LABEL_14;
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_58c7d8ca840131a6c20521327163655c_Traceguids, v12);
LABEL_14:
    v13 = WPP_GLOBAL_Control;
  }
  v14 = v11 < 0;
  if ( v11 > 0 )
  {
    v11 = (unsigned __int16)v11 | 0x80070000;
    v14 = v11 < 0;
  }
  if ( v14 )
  {
    if ( v13 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)v13 + 2), 18, WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids, (unsigned int)v11);
    v17 = v20;
    if ( v20 )
      goto LABEL_26;
  }
  else
  {
    v15 = CThirdPartyManager::PopulateProductRegistrationInformation(v6, v20);
    v11 = v15;
    if ( v15 >= 0 )
    {
      *a3 = v20;
      return (unsigned int)v11;
    }
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids,
        (unsigned int)v15);
    }
    v17 = v20;
    if ( v20 )
LABEL_26:
      (**(void (__fastcall ***)(struct CExternalBase *, __int64))v20)(v17, 1);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180005308  push    rbx
0x18000530a  push    rbp
0x18000530b  push    rdi
0x18000530c  push    r12
0x18000530e  push    r14
0x180005310  push    r15
0x180005312  sub     rsp, 38h
0x180005316  mov     r14, r8
0x180005319  mov     rbx, rcx
0x18000531c  mov     ebp, 1
0x180005321  mov     dl, bpl
0x180005324  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi>::GetImpl(void)'::`2'::impl
0x18000532b  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180005330  test    r14, r14
0x180005333  jz      loc_1800054F4
0x180005339  mov     [rsp+68h+arg_18], 0
0x180005345  mov     qword ptr [r14], 0
0x18000534c  mov     r12, cs:?g_pAntiVirusManager@WscServiceUtils@@3PEAVCAntiVirusManager@@EA; CAntiVirusManager * WscServiceUtils::g_pAntiVirusManager
0x180005353  mov     r15, cs:?g_pAntiVirusVerificationManager@WscServiceUtils@@3PEAVCSecurityVerificationManagerAv@@EA; CSecurityVerificationManagerAv * WscServiceUtils::g_pAntiVirusVerificationManager
0x18000535a  lea     rdi, WPP_GLOBAL_Control
0x180005361  mov     rcx, cs:WPP_GLOBAL_Control
0x180005368  cmp     rcx, rdi
0x18000536b  jz      short loc_180005377
0x18000536d  test    byte ptr [rcx+1Ch], 8
0x180005371  jnz     loc_18000555E
0x180005377  mov     [rsp+68h+Block], 0
0x180005380  mov     rcx, rbx; BindingHandle
0x180005383  call    cs:__imp_RpcImpersonateClient
0x180005389  test    eax, eax
0x18000538b  jnz     loc_180005578
0x180005391  call    ?IsDefender@CRpcImpersonateClient@@QEAAHXZ; CRpcImpersonateClient::IsDefender(void)
0x180005396  test    eax, eax
0x180005398  jnz     loc_18000545D
0x18000539e  call    RunningAsAdministrator
0x1800053a3  test    eax, eax
0x1800053a5  jz      loc_1800055AE
0x1800053ab  lea     rdx, [rsp+68h+Block]; unsigned __int16 **
0x1800053b0  mov     rcx, rbx; void *
0x1800053b3  call    ?GetCallerProcessPath@CSecurityVerificationManager@@SAJPEAXPEAPEAG@Z; CSecurityVerificationManager::GetCallerProcessPath(void *,ushort * *)
0x1800053b8  mov     ebp, eax
0x1800053ba  test    eax, eax
0x1800053bc  js      short loc_1800053DF
0x1800053be  lea     r8, [rsp+68h+arg_18]; struct CExternalBase **
0x1800053c6  mov     rdx, [rsp+68h+Block]; unsigned __int16 *
0x1800053cb  mov     rcx, r15; this
0x1800053ce  call    ?CreateExternalBaseFromPESettings@CSecurityVerificationManager@@QEAAJPEAGPEAPEAVCExternalBase@@@Z; CSecurityVerificationManager::CreateExternalBaseFromPESettings(ushort *,CExternalBase * *)
0x1800053d3  mov     ebp, eax
0x1800053d5  mov     rcx, [rsp+68h+Block]; Block
0x1800053da  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800053df  movzx   ebx, bp
0x1800053e2  xor     eax, eax
0x1800053e4  test    ebp, ebp
0x1800053e6  cmovns  ebx, eax
0x1800053e9  lea     ebp, [rax+1]
0x1800053ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800053f3  cmp     rcx, rdi
0x1800053f6  jnz     loc_18000547C
0x1800053fc  call    cs:__imp_RpcRevertToSelf
0x180005402  test    eax, eax
0x180005404  jnz     loc_1800055B8
0x18000540a  mov     rcx, cs:WPP_GLOBAL_Control
0x180005411  test    ebx, ebx
0x180005413  jg      short loc_180005450
0x180005415  js      loc_1800054A3
0x18000541b  mov     rdx, [rsp+68h+arg_18]; struct CExternalBase *
0x180005423  mov     rcx, r12; this
0x180005426  call    ?PopulateProductRegistrationInformation@CThirdPartyManager@@QEAAJPEAVCExternalBase@@@Z; CThirdPartyManager::PopulateProductRegistrationInformation(CExternalBase *)
0x18000542b  mov     ebx, eax
0x18000542d  test    eax, eax
0x18000542f  js      loc_1800054CB
0x180005435  mov     rax, [rsp+68h+arg_18]
0x18000543d  mov     [r14], rax
0x180005440  mov     eax, ebx
0x180005442  add     rsp, 38h
0x180005446  pop     r15
0x180005448  pop     r14
0x18000544a  pop     r12
0x18000544c  pop     rdi
0x18000544d  pop     rbp
0x18000544e  pop     rbx
0x18000544f  retn
0x180005450  movzx   ebx, bx
0x180005453  or      ebx, 80070000h
0x180005459  test    ebx, ebx
0x18000545b  jmp     short loc_180005415
0x18000545d  mov     rax, [r12]
0x180005461  lea     rdx, [rsp+68h+arg_18]
0x180005469  mov     rcx, r12
0x18000546c  mov     rax, [rax+8]
0x180005470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005475  mov     ebx, eax
0x180005477  jmp     loc_1800053EC
0x18000547c  test    byte ptr [rcx+1Ch], 8
0x180005480  jz      loc_1800053FC
0x180005486  mov     edx, 0Bh
0x18000548b  mov     r9d, ebx
0x18000548e  lea     r8, WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids
0x180005495  mov     rcx, [rcx+10h]
0x180005499  call    WPP_SF_d
0x18000549e  jmp     loc_1800053FC
0x1800054a3  cmp     rcx, rdi
0x1800054a6  jnz     loc_1800055EF
0x1800054ac  mov     rcx, [rsp+68h+arg_18]
0x1800054b4  test    rcx, rcx
0x1800054b7  jz      short loc_180005440
0x1800054b9  mov     r8, [rcx]
0x1800054bc  mov     rax, [r8]
0x1800054bf  mov     edx, ebp
0x1800054c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054c6  jmp     loc_180005440
0x1800054cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800054d2  cmp     rcx, rdi
0x1800054d5  jnz     loc_180005616
0x1800054db  mov     rcx, [rsp+68h+arg_18]
0x1800054e3  test    rcx, rcx
0x1800054e6  jz      loc_180005440
0x1800054ec  mov     rax, [rcx]
0x1800054ef  mov     rax, [rax]
0x1800054f2  jmp     short loc_1800054BF
0x1800054f4  lea     rdi, WPP_GLOBAL_Control
0x1800054fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180005502  cmp     rcx, rdi
0x180005505  jz      short loc_180005529
0x180005507  test    [rcx+1Ch], bpl
0x18000550b  jz      short loc_180005529
0x18000550d  mov     edx, 0Fh
0x180005512  lea     r8, WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids
0x180005519  mov     rcx, [rcx+10h]
0x18000551d  call    WPP_SF_
0x180005522  mov     rcx, cs:WPP_GLOBAL_Control
0x180005529  mov     ebx, 80070057h
0x18000552e  cmp     rcx, rdi
0x180005531  jz      loc_180005440
0x180005537  test    [rcx+1Ch], bpl
0x18000553b  jz      loc_180005440
0x180005541  mov     edx, 10h
0x180005546  mov     r9d, ebx
0x180005549  lea     r8, WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids
0x180005550  mov     rcx, [rcx+10h]
0x180005554  call    WPP_SF_d
0x180005559  jmp     loc_180005440
0x18000555e  mov     edx, 0Ah
0x180005563  lea     r8, WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids
0x18000556a  mov     rcx, [rcx+10h]
0x18000556e  call    WPP_SF_
0x180005573  jmp     loc_180005377
0x180005578  mov     rcx, cs:WPP_GLOBAL_Control
0x18000557f  cmp     rcx, rdi
0x180005582  jz      short loc_1800055A2
0x180005584  test    [rcx+1Ch], bpl
0x180005588  jz      short loc_1800055A2
0x18000558a  mov     edx, 1Bh
0x18000558f  mov     r9d, eax
0x180005592  lea     r8, WPP_58c7d8ca840131a6c20521327163655c_Traceguids
0x180005599  mov     rcx, [rcx+10h]
0x18000559d  call    WPP_SF_d
0x1800055a2  mov     ecx, 5; exception
0x1800055a7  call    cs:__imp_RpcRaiseException
0x1800055ad  nop
0x1800055ae  mov     ebx, 5
0x1800055b3  jmp     loc_1800053EC
0x1800055b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800055bf  cmp     rcx, rdi
0x1800055c2  jz      loc_180005411
0x1800055c8  test    [rcx+1Ch], bpl
0x1800055cc  jz      loc_180005411
0x1800055d2  mov     edx, 1Ch
0x1800055d7  mov     r9d, eax
0x1800055da  lea     r8, WPP_58c7d8ca840131a6c20521327163655c_Traceguids
0x1800055e1  mov     rcx, [rcx+10h]
0x1800055e5  call    WPP_SF_d
0x1800055ea  jmp     loc_18000540A
0x1800055ef  test    [rcx+1Ch], bpl
0x1800055f3  jz      loc_1800054AC
0x1800055f9  mov     edx, 12h
0x1800055fe  mov     r9d, ebx
0x180005601  lea     r8, WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids
0x180005608  mov     rcx, [rcx+10h]
0x18000560c  call    WPP_SF_d
0x180005611  jmp     loc_1800054AC
0x180005616  test    [rcx+1Ch], bpl
0x18000561a  jz      loc_1800054DB
0x180005620  mov     edx, 13h
0x180005625  mov     r9d, ebx
0x180005628  lea     r8, WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids
0x18000562f  mov     rcx, [rcx+10h]
0x180005633  call    WPP_SF_d
0x180005638  jmp     loc_1800054DB
```
