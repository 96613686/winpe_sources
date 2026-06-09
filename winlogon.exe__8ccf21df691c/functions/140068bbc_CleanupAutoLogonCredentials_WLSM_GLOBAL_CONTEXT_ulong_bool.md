# CleanupAutoLogonCredentials(_WLSM_GLOBAL_CONTEXT *,ulong,bool)

- ea: `0x140068bbc`
- end: `0x140069055`
- name: `?CleanupAutoLogonCredentials@@YAXPEAU_WLSM_GLOBAL_CONTEXT@@K_N@Z`
- size: `1177`
- prototype: `void __fastcall(struct _WLSM_GLOBAL_CONTEXT *, unsigned int, bool)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14006cf20`

## callees

- `0x140002564`
- `0x1400057f4`
- `0x140039458`
- `0x14003ba50`
- `0x14003f584`
- `0x140041c34`
- `0x140044800`
- `0x14004c124`
- `0x14004eb98`
- `0x1400514ac`
- `0x140053720`
- `0x140068bbc`
- `0x14007cc30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140068ed0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140068ee2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140068ef4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140068f06`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140068fba`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140068ed0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140068ee2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140068ef4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140068f06`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140068fba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140068e76`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140068e76`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140069021`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009f562`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140069021`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009f562`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x140068f21`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x140068f21`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x140068f54`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x140068f54`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x140069031`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x14009f571`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x140069031`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x14009f571`
- `ntdll!RtlInitUnicodeString` at `0x140068f3e`
- `ntdll!RtlInitUnicodeString` at `0x140068f3e`

## pseudocode

```c
void __fastcall CleanupAutoLogonCredentials(struct _WLSM_GLOBAL_CONTEXT *a1, int a2, char a3)
{
  unsigned int v5; // esi
  int v6; // r14d
  CSession *v7; // rcx
  HKEY v8; // rcx
  unsigned int v9; // r14d
  CUser *v10; // rcx
  unsigned int v11; // eax
  NTSTATUS v12; // eax
  CUser *v13; // rcx
  __int64 v14; // rdx
  _BYTE v15[8]; // [rsp+50h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-C0h] BYREF
  unsigned int v17; // [rsp+60h] [rbp-B8h] BYREF
  PVOID PolicyHandle; // [rsp+68h] [rbp-B0h] BYREF
  int v19; // [rsp+70h] [rbp-A8h] BYREF
  int v20; // [rsp+74h] [rbp-A4h] BYREF
  int v21; // [rsp+78h] [rbp-A0h] BYREF
  __int64 v22; // [rsp+80h] [rbp-98h] BYREF
  __int128 *v23; // [rsp+88h] [rbp-90h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-88h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-78h] BYREF
  __int128 v26; // [rsp+D0h] [rbp-48h] BYREF

  hKey = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  PolicyHandle = 0;
  DestinationString = 0;
  v5 = 0;
  *(_DWORD *)(*((_QWORD *)a1 + 2) + 396LL) = 0;
  if ( *((int *)a1 + 13) >= 0 && *((_DWORD *)a1 + 14) == -1073741232 )
  {
    a3 = 1;
    v5 = 1;
    v21 = 1;
    *((_DWORD *)a1 + 14) = 0;
  }
  if ( !a3 )
  {
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids);
    }
    goto LABEL_49;
  }
  wil::srwlock::lock_shared(*(_QWORD *)a1 + 64LL, &v21);
  *(_QWORD *)&v26 = 0;
  if ( (int)CGlobalStore::GetGlobalTraceLoggingActivity(*(_QWORD *)a1, &v26) >= 0 )
  {
    v6 = v26;
    if ( (_QWORD)v26 )
    {
      v26 = 0;
      WLGetTSActivityId(&v26);
      if ( (unsigned int)dword_1400CF778 > 5 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_1400CF778, 0x800000000000LL) )
        {
          v19 = *(_DWORD *)(*((_QWORD *)a1 + 2) + 88LL);
          v15[0] = v5;
          v20 = a2;
          v22 = 0x1000000;
          v23 = &v26;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
            v19,
            (unsigned int)qword_1400BC240,
            v6 + 8,
            (unsigned int)&v26,
            (__int64)&v23,
            (__int64)&v22,
            (__int64)&v20,
            (__int64)v15,
            (__int64)&v19);
        }
      }
    }
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v21);
  if ( a2 )
  {
    *(_DWORD *)(*((_QWORD *)a1 + 2) + 396LL) = 1;
  }
  else if ( CSession::isDeviceCTAEnabled(v7) )
  {
    v17 = 0;
    v9 = 0;
    if ( (int)SHRegGetDWORD(
                v8,
                L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
                L"AutologinAfterRestart",
                &v17) >= 0 )
      v9 = v17;
    if ( v9 != 2 )
    {
      CSession::SetAutoLock(*((_QWORD *)a1 + 2), 1, v5);
      goto LABEL_20;
    }
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
LABEL_21:
        if ( v10 != (CUser *)&WPP_GLOBAL_Control && (*((_DWORD *)v10 + 7) & 0x1000) != 0 && *((_BYTE *)v10 + 25) >= 4u )
          WPP_SF_d(*((_QWORD *)v10 + 2), 50, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v9);
        goto LABEL_27;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, 2);
LABEL_20:
      v10 = WPP_GLOBAL_Control;
      goto LABEL_21;
    }
  }
  else
  {
    CSession::SetAutoLock(*((_QWORD *)a1 + 2), 1, v5);
  }
LABEL_27:
  v11 = RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
          0,
          0x2001Fu,
          &hKey);
  if ( !v11 )
  {
    RegDeleteValueW(hKey, L"AutoAdminLogon");
    RegDeleteValueW(hKey, L"DefaultUserName");
    RegDeleteValueW(hKey, L"DefaultDomainName");
    RegDeleteValueW(hKey, L"AutoLogonCount");
    v12 = LsaOpenPolicy(0, &ObjectAttributes, 0x20u, &PolicyHandle);
    if ( v12 < 0 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_49;
      }
      v14 = 53;
    }
    else
    {
      RtlInitUnicodeString(&DestinationString, L"DefaultPassword");
      v12 = LsaStorePrivateData(PolicyHandle, (PLSA_UNICODE_STRING)&DestinationString, 0);
      if ( (int)(v12 + 0x80000000) < 0 || v12 == -1073741772 )
      {
        RegDeleteValueW(hKey, L"ForceAutoLockOnLogon");
        goto LABEL_49;
      }
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_49;
      }
      v14 = 52;
    }
    WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, (unsigned int)v12);
    goto LABEL_49;
  }
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v11);
  }
LABEL_49:
  RegCloseKey(hKey);
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
}

```

## disassembly

```asm
0x140068bbc  mov     r11, rsp
0x140068bbf  push    rbx
0x140068bc0  push    rsi
0x140068bc1  push    r14
0x140068bc3  push    r15
0x140068bc5  sub     rsp, 0F8h
0x140068bcc  mov     rax, cs:__security_cookie
0x140068bd3  xor     rax, rsp
0x140068bd6  mov     [rsp+118h+var_38], rax
0x140068bde  mov     r15d, edx
0x140068be1  mov     rbx, rcx
0x140068be4  mov     [rsp+118h+hKey], 0
0x140068bed  xorps   xmm0, xmm0
0x140068bf0  movups  xmmword ptr [r11-78h], xmm0
0x140068bf5  movups  xmmword ptr [r11-68h], xmm0
0x140068bfa  movups  xmmword ptr [r11-58h], xmm0
0x140068bff  mov     [rsp+118h+PolicyHandle], 0
0x140068c08  movups  xmmword ptr [rsp+118h+DestinationString.Length], xmm0
0x140068c10  xor     esi, esi
0x140068c12  mov     rax, [rcx+10h]
0x140068c16  mov     [rax+18Ch], esi
0x140068c1c  cmp     [rcx+34h], esi
0x140068c1f  jl      short loc_140068C3D
0x140068c21  cmp     dword ptr [rcx+38h], 0C0000250h
0x140068c28  jnz     short loc_140068C3D
0x140068c2a  mov     r8b, 1
0x140068c2d  mov     esi, 1
0x140068c32  mov     [rsp+118h+var_A0], esi
0x140068c36  mov     dword ptr [rcx+38h], 0
0x140068c3d  test    r8b, r8b
0x140068c40  jz      loc_140068FE4
0x140068c46  mov     rcx, [rcx]
0x140068c49  add     rcx, 40h ; '@'
0x140068c4d  lea     rdx, [rsp+118h+var_A0]
0x140068c52  call    ?lock_shared@srwlock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::srwlock::lock_shared(void)
0x140068c57  mov     qword ptr [rsp+118h+var_48], 0
0x140068c63  lea     rdx, [rsp+118h+var_48]
0x140068c6b  mov     rcx, [rbx]
0x140068c6e  call    ?GetGlobalTraceLoggingActivity@CGlobalStore@@QEAAJPEAPEAV?$TraceLoggingActivity@$1?g_WinlogonProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@@Z; CGlobalStore::GetGlobalTraceLoggingActivity(TraceLoggingActivity<&_tlgProvider_t const * const g_WinlogonProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider> * *)
0x140068c73  test    eax, eax
0x140068c75  js      loc_140068D52
0x140068c7b  mov     r14, qword ptr [rsp+118h+var_48]
0x140068c83  test    r14, r14
0x140068c86  jz      loc_140068D52
0x140068c8c  xorps   xmm0, xmm0
0x140068c8f  movups  [rsp+118h+var_48], xmm0
0x140068c97  lea     rcx, [rsp+118h+var_48]
0x140068c9f  call    WLGetTSActivityId
0x140068ca4  mov     eax, cs:dword_1400CF778
0x140068caa  cmp     eax, 5
0x140068cad  jbe     loc_140068D52
0x140068cb3  mov     rdx, 800000000000h
0x140068cbd  lea     rcx, dword_1400CF778
0x140068cc4  call    _tlgKeywordOn
0x140068cc9  test    al, al
0x140068ccb  jz      loc_140068D52
0x140068cd1  mov     rax, [rbx+10h]
0x140068cd5  mov     ecx, [rax+58h]
0x140068cd8  mov     [rsp+118h+var_A8], ecx
0x140068cdc  mov     [rsp+118h+var_C8], sil
0x140068ce1  mov     [rsp+118h+var_A4], r15d
0x140068ce6  mov     [rsp+118h+var_98], 1000000h
0x140068cf2  lea     rax, [rsp+118h+var_48]
0x140068cfa  mov     [rsp+118h+var_90], rax
0x140068d02  lea     r8, [r14+8]
0x140068d06  lea     rax, [rsp+118h+var_A8]
0x140068d0b  mov     [rsp+118h+var_D8], rax
0x140068d10  lea     rax, [rsp+118h+var_C8]
0x140068d15  mov     [rsp+118h+var_E0], rax
0x140068d1a  lea     rax, [rsp+118h+var_A4]
0x140068d1f  mov     [rsp+118h+var_E8], rax
0x140068d24  lea     rax, [rsp+118h+var_98]
0x140068d2c  mov     [rsp+118h+var_F0], rax
0x140068d31  lea     rax, [rsp+118h+var_90]
0x140068d39  mov     [rsp+118h+phkResult], rax
0x140068d3e  lea     r9, [rsp+118h+var_48]
0x140068d46  lea     rdx, qword_1400BC240
0x140068d4d  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$00@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$00@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &)
0x140068d52  lea     rcx, [rsp+118h+var_A0]
0x140068d57  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x140068d5c  test    r15d, r15d
0x140068d5f  jnz     loc_140068E40
0x140068d65  call    ?isDeviceCTAEnabled@CSession@@QEAA_NXZ; CSession::isDeviceCTAEnabled(void)
0x140068d6a  test    al, al
0x140068d6c  jz      loc_140068E2D
0x140068d72  mov     [rsp+118h+var_B8], r15d
0x140068d77  xor     r14d, r14d
0x140068d7a  lea     r9, [rsp+118h+var_B8]; unsigned int *
0x140068d7f  lea     r8, aAutologinafter; "AutologinAfterRestart"
0x140068d86  lea     rdx, aSoftwareMicros_48; "Software\\Microsoft\\Windows NT\\Curren"...
0x140068d8d  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x140068d92  test    eax, eax
0x140068d94  cmovns  r14d, [rsp+118h+var_B8]
0x140068d9a  cmp     r14d, 2
0x140068d9e  jz      short loc_140068DB9
0x140068da0  mov     r8d, esi
0x140068da3  lea     edx, [r15+1]
0x140068da7  mov     rcx, [rbx+10h]
0x140068dab  call    ?SetAutoLock@CSession@@QEAAXW4AutoLockType@1@W4AutoLockStartReason@1@@Z; CSession::SetAutoLock(CSession::AutoLockType,CSession::AutoLockStartReason)
0x140068db0  lea     rbx, WPP_GLOBAL_Control
0x140068db7  jmp     short loc_140068DF8
0x140068db9  lea     rbx, WPP_GLOBAL_Control
0x140068dc0  mov     rcx, cs:WPP_GLOBAL_Control
0x140068dc7  cmp     rcx, rbx
0x140068dca  jz      loc_140068E55
0x140068dd0  test    dword ptr [rcx+1Ch], 1000h
0x140068dd7  jz      short loc_140068DFF
0x140068dd9  cmp     byte ptr [rcx+19h], 4
0x140068ddd  jb      short loc_140068DFF
0x140068ddf  mov     edx, 31h ; '1'
0x140068de4  lea     r9d, [rdx-2Fh]
0x140068de8  lea     r8, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids
0x140068def  mov     rcx, [rcx+10h]
0x140068df3  call    WPP_SF_d
0x140068df8  mov     rcx, cs:WPP_GLOBAL_Control
0x140068dff  cmp     rcx, rbx
0x140068e02  jz      short loc_140068E55
0x140068e04  test    dword ptr [rcx+1Ch], 1000h
0x140068e0b  jz      short loc_140068E55
0x140068e0d  cmp     byte ptr [rcx+19h], 4
0x140068e11  jb      short loc_140068E55
0x140068e13  mov     edx, 32h ; '2'
0x140068e18  mov     r9d, r14d
0x140068e1b  lea     r8, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids
0x140068e22  mov     rcx, [rcx+10h]
0x140068e26  call    WPP_SF_d
0x140068e2b  jmp     short loc_140068E55
0x140068e2d  mov     r8d, esi
0x140068e30  mov     edx, 1
0x140068e35  mov     rcx, [rbx+10h]
0x140068e39  call    ?SetAutoLock@CSession@@QEAAXW4AutoLockType@1@W4AutoLockStartReason@1@@Z; CSession::SetAutoLock(CSession::AutoLockType,CSession::AutoLockStartReason)
0x140068e3e  jmp     short loc_140068E4E
0x140068e40  mov     rax, [rbx+10h]
0x140068e44  mov     dword ptr [rax+18Ch], 1
0x140068e4e  lea     rbx, WPP_GLOBAL_Control
0x140068e55  lea     rax, [rsp+118h+hKey]
0x140068e5a  mov     [rsp+118h+phkResult], rax; phkResult
0x140068e5f  mov     r9d, 2001Fh; samDesired
0x140068e65  xor     r8d, r8d; ulOptions
0x140068e68  lea     rdx, aSoftwareMicros_48; "Software\\Microsoft\\Windows NT\\Curren"...
0x140068e6f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140068e76  call    cs:__imp_RegOpenKeyExW
0x140068e7c  test    eax, eax
0x140068e7e  jz      short loc_140068EC4
0x140068e80  mov     rcx, cs:WPP_GLOBAL_Control
0x140068e87  cmp     rcx, rbx
0x140068e8a  jz      loc_14006901C
0x140068e90  test    dword ptr [rcx+1Ch], 1000h
0x140068e97  jz      loc_14006901C
0x140068e9d  cmp     byte ptr [rcx+19h], 2
0x140068ea1  jb      loc_14006901C
0x140068ea7  mov     edx, 33h ; '3'
0x140068eac  mov     r9d, eax
0x140068eaf  lea     r8, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids
0x140068eb6  mov     rcx, [rcx+10h]
0x140068eba  call    WPP_SF_d
0x140068ebf  jmp     loc_14006901C
0x140068ec4  lea     rdx, aAutoadminlogon; "AutoAdminLogon"
0x140068ecb  mov     rcx, [rsp+118h+hKey]; hKey
0x140068ed0  call    cs:__imp_RegDeleteValueW
0x140068ed6  lea     rdx, aDefaultusernam; "DefaultUserName"
0x140068edd  mov     rcx, [rsp+118h+hKey]; hKey
0x140068ee2  call    cs:__imp_RegDeleteValueW
0x140068ee8  lea     rdx, aDefaultdomainn; "DefaultDomainName"
0x140068eef  mov     rcx, [rsp+118h+hKey]; hKey
0x140068ef4  call    cs:__imp_RegDeleteValueW
0x140068efa  lea     rdx, aAutologoncount; "AutoLogonCount"
0x140068f01  mov     rcx, [rsp+118h+hKey]; hKey
0x140068f06  call    cs:__imp_RegDeleteValueW
0x140068f0c  lea     r9, [rsp+118h+PolicyHandle]; PolicyHandle
0x140068f11  mov     r8d, 20h ; ' '; DesiredAccess
0x140068f17  lea     rdx, [rsp+118h+ObjectAttributes]; ObjectAttributes
0x140068f1f  xor     ecx, ecx; SystemName
0x140068f21  call    cs:__imp_LsaOpenPolicy
0x140068f27  test    eax, eax
0x140068f29  js      loc_140068FC2
0x140068f2f  lea     rdx, aDefaultpasswor; "DefaultPassword"
0x140068f36  lea     rcx, [rsp+118h+DestinationString]; DestinationString
0x140068f3e  call    cs:__imp_RtlInitUnicodeString
0x140068f44  xor     r8d, r8d; PrivateData
0x140068f47  lea     rdx, [rsp+118h+DestinationString]; KeyName
0x140068f4f  mov     rcx, [rsp+118h+PolicyHandle]; PolicyHandle
0x140068f54  call    cs:__imp_LsaStorePrivateData
0x140068f5a  mov     edx, 80000000h
0x140068f5f  lea     ecx, [rax+rdx]
0x140068f62  test    edx, ecx
0x140068f64  jnz     short loc_140068FAE
0x140068f66  cmp     eax, 0C0000034h
0x140068f6b  jz      short loc_140068FAE
0x140068f6d  mov     rcx, cs:WPP_GLOBAL_Control
0x140068f74  cmp     rcx, rbx
0x140068f77  jz      loc_14006901C
0x140068f7d  test    dword ptr [rcx+1Ch], 1000h
0x140068f84  jz      loc_14006901C
0x140068f8a  cmp     byte ptr [rcx+19h], 2
0x140068f8e  jb      loc_14006901C
0x140068f94  mov     edx, 34h ; '4'
0x140068f99  mov     r9d, eax
0x140068f9c  lea     r8, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids
0x140068fa3  mov     rcx, [rcx+10h]
0x140068fa7  call    WPP_SF_d
0x140068fac  jmp     short loc_14006901C
0x140068fae  lea     rdx, aForceautolocko; "ForceAutoLockOnLogon"
0x140068fb5  mov     rcx, [rsp+118h+hKey]; hKey
0x140068fba  call    cs:__imp_RegDeleteValueW
0x140068fc0  jmp     short loc_14006901C
0x140068fc2  mov     rcx, cs:WPP_GLOBAL_Control
0x140068fc9  cmp     rcx, rbx
0x140068fcc  jz      short loc_14006901C
0x140068fce  test    dword ptr [rcx+1Ch], 1000h
0x140068fd5  jz      short loc_14006901C
0x140068fd7  cmp     byte ptr [rcx+19h], 2
0x140068fdb  jb      short loc_14006901C
0x140068fdd  mov     edx, 35h ; '5'
0x140068fe2  jmp     short loc_140068F99
0x140068fe4  lea     rbx, WPP_GLOBAL_Control
0x140068feb  mov     rcx, cs:WPP_GLOBAL_Control
0x140068ff2  cmp     rcx, rbx
0x140068ff5  jz      short loc_14006901C
0x140068ff7  test    dword ptr [rcx+1Ch], 1000h
0x140068ffe  jz      short loc_14006901C
0x140069000  cmp     byte ptr [rcx+19h], 5
0x140069004  jb      short loc_14006901C
0x140069006  mov     edx, 36h ; '6'
0x14006900b  lea     r8, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids
0x140069012  mov     rcx, [rcx+10h]
0x140069016  call    WPP_SF_
0x14006901b  nop
0x14006901c  mov     rcx, [rsp+118h+hKey]; hKey
0x140069021  call    cs:__imp_RegCloseKey
0x140069027  mov     rcx, [rsp+118h+PolicyHandle]; ObjectHandle
0x14006902c  test    rcx, rcx
0x14006902f  jz      short loc_140069037
0x140069031  call    cs:__imp_LsaClose
0x140069037  mov     rcx, [rsp+118h+var_38]
0x14006903f  xor     rcx, rsp; StackCookie
0x140069042  call    __security_check_cookie
0x140069047  add     rsp, 0F8h
0x14006904e  pop     r15
0x140069050  pop     r14
0x140069052  pop     rsi
0x140069053  pop     rbx
0x140069054  retn
0x14009f555  push    rbp
0x14009f557  sub     rsp, 50h
0x14009f55b  mov     rbp, rdx
0x14009f55e  mov     rcx, [rbp+58h]; hKey
0x14009f562  call    cs:__imp_RegCloseKey
0x14009f568  mov     rcx, [rbp+68h]; ObjectHandle
0x14009f56c  test    rcx, rcx
0x14009f56f  jz      short loc_14009F578
0x14009f571  call    cs:__imp_LsaClose
0x14009f577  nop
0x14009f578  add     rsp, 50h
0x14009f57c  pop     rbp
0x14009f57d  retn
```
