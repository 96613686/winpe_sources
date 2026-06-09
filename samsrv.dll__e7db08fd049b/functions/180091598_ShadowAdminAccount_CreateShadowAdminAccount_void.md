# ShadowAdminAccount::CreateShadowAdminAccount(void)

- ea: `0x180091598`
- end: `0x180091c79`
- name: `?CreateShadowAdminAccount@ShadowAdminAccount@@AEAAJXZ`
- size: `1761`
- prototype: `__int64 __fastcall(PCWSTR *this)`
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180091e7c`

## callees

- `0x1800028e0`
- `0x1800066f0`
- `0x180011810`
- `0x180022440`
- `0x180022678`
- `0x1800270e0`
- `0x180027d08`
- `0x180027e24`
- `0x180027e70`
- `0x18002cd80`
- `0x18002d720`
- `0x1800372ac`
- `0x1800573f0`
- `0x1800616ec`
- `0x180065b60`
- `0x18009109c`
- `0x180091598`
- `0x180092040`
- `0x180092290`
- `0x18009236c`
- `0x1800930f8`
- `0x1800a5620`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800918a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800918a3`
- `ntdll!RtlAddAttributeActionToRXact` at `0x180091b19`
- `ntdll!RtlAddAttributeActionToRXact` at `0x180091b19`
- `ntdll!RtlLengthSid` at `0x1800918ed`
- `ntdll!RtlLengthSid` at `0x180091a2b`
- `ntdll!RtlLengthSid` at `0x1800918ed`
- `ntdll!RtlLengthSid` at `0x180091a2b`
- `ntdll!RtlInitUnicodeString` at `0x180091739`
- `ntdll!RtlInitUnicodeString` at `0x180091abf`
- `ntdll!RtlInitUnicodeString` at `0x180091acd`
- `ntdll!RtlInitUnicodeString` at `0x180091739`
- `ntdll!RtlInitUnicodeString` at `0x180091abf`
- `ntdll!RtlInitUnicodeString` at `0x180091acd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180091c01`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180091c0b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180091c14`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180091c01`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180091c0b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180091c14`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180091899`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180091899`

## string_xrefs

- `0x180091ab4`: `ShadowAccountSid`

## pseudocode

```c
__int64 __fastcall ShadowAdminAccount::CreateShadowAdminAccount(PCWSTR *this)
{
  int v2; // r12d
  WCHAR *v3; // r15
  void *v4; // rsi
  struct _SAMP_OBJECT *v5; // r14
  int v6; // eax
  int v7; // ebx
  unsigned int v8; // edx
  int AvailableSamAccountName; // eax
  unsigned int v10; // edx
  PUNICODE_STRING v11; // rcx
  __int64 v12; // rdx
  unsigned int v13; // edx
  __int64 v14; // r8
  __int64 v15; // r9
  int AccountSid; // eax
  DWORD LastError; // eax
  int AccountContext; // eax
  ULONG v19; // eax
  __int64 v20; // rcx
  __int64 v21; // rax
  int v22; // eax
  ShadowAdminAccount *v23; // rcx
  PUNICODE_STRING v24; // rcx
  __int64 v25; // rdx
  int v26; // eax
  PVOID HandleId; // [rsp+60h] [rbp-A0h] BYREF
  int v29; // [rsp+68h] [rbp-98h] BYREF
  _DWORD v30[3]; // [rsp+6Ch] [rbp-94h] BYREF
  struct _SAMP_OBJECT *v31; // [rsp+78h] [rbp-88h]
  __int64 v32; // [rsp+80h] [rbp-80h] BYREF
  LPWSTR StringSid; // [rsp+88h] [rbp-78h] BYREF
  __int128 v34; // [rsp+90h] [rbp-70h] BYREF
  PCWSTR SourceString; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v36; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 *v37; // [rsp+B0h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+B8h] [rbp-48h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+C8h] [rbp-38h] BYREF
  struct _UNICODE_STRING KeyName; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v41[56]; // [rsp+F0h] [rbp-10h] BYREF
  int v42; // [rsp+128h] [rbp+28h]

  v29 = 0;
  LODWORD(v32) = 0;
  memset(v30, 0, sizeof(v30));
  SourceString = 0;
  StringSid = 0;
  v2 = 0;
  v36 = 0;
  DestinationString = 0;
  v3 = 0;
  v37 = 0;
  v34 = 0;
  v4 = 0;
  KeyName = 0;
  HandleId = 0;
  v5 = 0;
  ValueName = 0;
  v31 = 0;
  memset_0(v41, 0, 0x50u);
  v6 = SampAcquireWriteLock(*((_QWORD *)SampDefinedDomains + 170));
  v7 = v6;
  if ( v6 < 0 )
  {
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) != 0
      && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 63, WPP_99473abb2ee73b6c7cc9b39fb0106789_Traceguids, (unsigned int)v6);
    }
    goto LABEL_85;
  }
  SampSetTransactionDomain(1);
  AvailableSamAccountName = ShadowAdminAccount::FindAvailableSamAccountName(
                              (ShadowAdminAccount *)this,
                              v8,
                              (unsigned __int16 **)&SourceString);
  v3 = (WCHAR *)SourceString;
  v7 = AvailableSamAccountName;
  if ( AvailableSamAccountName < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) == 0
      || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
    {
      goto LABEL_72;
    }
    v12 = 64;
LABEL_71:
    WPP_SF_d(v11[3].Buffer, v12, WPP_99473abb2ee73b6c7cc9b39fb0106789_Traceguids, (unsigned int)AvailableSamAccountName);
LABEL_72:
    SampReleaseWriteLock(0);
    goto LABEL_83;
  }
  AvailableSamAccountName = ShadowAdminAccount::GetShadowAccountFullName((ShadowAdminAccount *)this, v10, &v36);
  v7 = AvailableSamAccountName;
  if ( AvailableSamAccountName < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) == 0
      || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
    {
      goto LABEL_72;
    }
    v12 = 65;
    goto LABEL_71;
  }
  AvailableSamAccountName = ShadowAdminAccount::GetShadowAccountDescription((ShadowAdminAccount *)this, v13, &v37);
  v7 = AvailableSamAccountName;
  if ( AvailableSamAccountName < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) == 0
      || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
    {
      goto LABEL_72;
    }
    v12 = 66;
    goto LABEL_71;
  }
  RtlInitUnicodeString(&DestinationString, v3);
  AvailableSamAccountName = SampCreateUserInDomain(
                              *((struct _SAMP_OBJECT **)SampDefinedDomains + 170),
                              &DestinationString,
                              1,
                              0,
                              (__int64)&HandleId,
                              (__int64)&v32,
                              (__int64)v30,
                              0,
                              0);
  v7 = AvailableSamAccountName;
  if ( AvailableSamAccountName < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) == 0
      || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
    {
      goto LABEL_72;
    }
    v12 = 67;
    goto LABEL_71;
  }
  AvailableSamAccountName = SampRetrieveUserV1aFixed(HandleId, v41, v14, v15);
  v7 = AvailableSamAccountName;
  if ( AvailableSamAccountName < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) == 0
      || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
    {
      goto LABEL_72;
    }
    v12 = 68;
    goto LABEL_71;
  }
  v42 = 532;
  AvailableSamAccountName = SampReplaceUserV1aFixed(HandleId, v41);
  v7 = AvailableSamAccountName;
  if ( AvailableSamAccountName < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) == 0
      || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
    {
      goto LABEL_72;
    }
    v12 = 69;
    goto LABEL_71;
  }
  AccountSid = SampCreateAccountSid((struct _SAMP_OBJECT *)HandleId, (void **)&v30[1]);
  v7 = AccountSid;
  if ( AccountSid < 0 )
  {
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) != 0
      && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control[3].Buffer,
        70,
        WPP_99473abb2ee73b6c7cc9b39fb0106789_Traceguids,
        (unsigned int)AccountSid);
    }
    v4 = *(void **)&v30[1];
    goto LABEL_72;
  }
  v4 = *(void **)&v30[1];
  if ( !ConvertSidToStringSidW(*(PSID *)&v30[1], &StringSid) )
  {
    LastError = GetLastError();
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) != 0
      && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 71, WPP_99473abb2ee73b6c7cc9b39fb0106789_Traceguids, LastError, LastError);
    }
    v7 = -1073741801;
    goto LABEL_72;
  }
  *((_QWORD *)&v34 + 1) = this[2];
  LODWORD(v34) = RtlLengthSid(*((PSID *)&v34 + 1));
  AvailableSamAccountName = SampSetExtendedAttribute((struct _SAMP_OBJECT *)HandleId, 39, &v34);
  v7 = AvailableSamAccountName;
  if ( AvailableSamAccountName < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) == 0
      || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
    {
      goto LABEL_72;
    }
    v12 = 72;
    goto LABEL_71;
  }
  v29 = 1;
  AvailableSamAccountName = SampSetExtendedAttribute((struct _SAMP_OBJECT *)HandleId, 19, &v29);
  v7 = AvailableSamAccountName;
  if ( AvailableSamAccountName < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) == 0
      || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
    {
      goto LABEL_72;
    }
    v12 = 73;
    goto LABEL_71;
  }
  AvailableSamAccountName = SampStoreObjectAttributes((struct _SAMP_OBJECT *)HandleId);
  v7 = AvailableSamAccountName;
  if ( AvailableSamAccountName < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) == 0
      || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
    {
      goto LABEL_72;
    }
    v12 = 74;
    goto LABEL_71;
  }
  if ( *((_DWORD *)this + 16) )
  {
    AccountContext = SampCreateAccountContext(4, *((unsigned int *)this + 8));
    v7 = AccountContext;
    if ( AccountContext < 0 )
    {
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) != 0
        && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
      {
        WPP_SF_DdD(
          WPP_GLOBAL_Control[3].Buffer,
          75,
          WPP_99473abb2ee73b6c7cc9b39fb0106789_Traceguids,
          *((unsigned int *)this + 8),
          *((_DWORD *)this + 8),
          AccountContext);
      }
      v5 = v31;
      goto LABEL_72;
    }
    *((_QWORD *)&v34 + 1) = v4;
    v19 = RtlLengthSid(v4);
    v5 = v31;
    LODWORD(v34) = v19;
    AvailableSamAccountName = SampSetExtendedAttribute(v31, 38, &v34);
    v7 = AvailableSamAccountName;
    if ( AvailableSamAccountName < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) == 0
        || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
      {
        goto LABEL_72;
      }
      v12 = 76;
      goto LABEL_71;
    }
    AvailableSamAccountName = SampStoreObjectAttributes(v5);
    v7 = AvailableSamAccountName;
    if ( AvailableSamAccountName < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) == 0
        || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
      {
        goto LABEL_72;
      }
      v12 = 77;
      goto LABEL_71;
    }
  }
  else
  {
    RtlInitUnicodeString(&ValueName, L"ShadowAccountSid");
    RtlInitUnicodeString(&KeyName, this[12]);
    v21 = -1;
    do
      ++v21;
    while ( StringSid[v21] );
    AvailableSamAccountName = RtlAddAttributeActionToRXact(
                                SampRXactContext,
                                2u,
                                &KeyName,
                                (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                                &ValueName,
                                1u,
                                StringSid,
                                2 * v21 + 2);
    v7 = AvailableSamAccountName;
    if ( AvailableSamAccountName < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) == 0
        || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
      {
        goto LABEL_72;
      }
      v12 = 78;
      goto LABEL_71;
    }
  }
  LOBYTE(v20) = 1;
  v22 = SampReleaseWriteLock(v20);
  v7 = v22;
  if ( v22 >= 0 )
  {
    v2 = 1;
    v22 = ShadowAdminAccount::AddAccountToLocalAdministratorsGroup(v23, v4);
    v7 = v22;
    if ( v22 >= 0 )
    {
      v26 = v30[0];
      this[9] = (PCWSTR)v4;
      v4 = 0;
      this[10] = v3;
      v3 = 0;
      *((_DWORD *)this + 8) = v26;
    }
    else
    {
      v24 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) != 0
        && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
      {
        v25 = 80;
        goto LABEL_77;
      }
    }
  }
  else
  {
    v24 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) != 0
      && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      v25 = 79;
LABEL_77:
      WPP_SF_d(v24[3].Buffer, v25, WPP_99473abb2ee73b6c7cc9b39fb0106789_Traceguids, (unsigned int)v22);
    }
  }
LABEL_83:
  if ( v5 )
    SampDeleteContext(v5);
LABEL_85:
  if ( HandleId )
    SampDeleteContext(HandleId);
  LocalFree(v4);
  LocalFree(StringSid);
  LocalFree(v3);
  if ( v7 < 0 && v2 )
    SampDeleteLocalSamAccount(v4);
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 81, WPP_99473abb2ee73b6c7cc9b39fb0106789_Traceguids, (unsigned int)v7, v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180091598  push    rbp
0x18009159a  push    rbx
0x18009159b  push    rsi
0x18009159c  push    rdi
0x18009159d  push    r12
0x18009159f  push    r13
0x1800915a1  push    r14
0x1800915a3  push    r15
0x1800915a5  lea     rbp, [rsp-58h]
0x1800915aa  sub     rsp, 158h
0x1800915b1  mov     rax, cs:__security_cookie
0x1800915b8  xor     rax, rsp
0x1800915bb  mov     [rbp+90h+var_50], rax
0x1800915bf  xor     r13d, r13d
0x1800915c2  xorps   xmm0, xmm0
0x1800915c5  mov     rdi, rcx
0x1800915c8  mov     [rsp+190h+var_128], r13d
0x1800915cd  xorps   xmm1, xmm1
0x1800915d0  mov     dword ptr [rbp+90h+var_110], r13d
0x1800915d4  xor     edx, edx; Val
0x1800915d6  mov     dword ptr [rsp+190h+var_124], r13d
0x1800915db  lea     r8d, [r13+50h]; Size
0x1800915df  mov     [rbp+90h+SourceString], r13
0x1800915e3  lea     rcx, [rbp+90h+var_A0]; void *
0x1800915e7  mov     [rbp+90h+StringSid], r13
0x1800915eb  mov     r12d, r13d
0x1800915ee  mov     [rbp+90h+var_E8], r13
0x1800915f2  movups  xmmword ptr [rbp+90h+DestinationString.Length], xmm0
0x1800915f6  mov     r15d, r13d
0x1800915f9  mov     [rbp+90h+var_E0], r13
0x1800915fd  movups  [rbp+90h+var_100], xmm0
0x180091601  mov     esi, r13d
0x180091604  mov     qword ptr [rsp+190h+var_124+4], r13
0x180091609  movups  xmmword ptr [rbp+90h+KeyName.Length], xmm1
0x18009160d  mov     [rsp+190h+HandleId], r13
0x180091612  mov     r14d, r13d
0x180091615  movups  xmmword ptr [rbp+90h+var_C8.Length], xmm0
0x180091619  mov     [rsp+190h+var_118], r13
0x18009161e  call    memset_0
0x180091623  mov     rcx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x18009162a  mov     rcx, [rcx+550h]
0x180091631  call    SampAcquireWriteLock
0x180091636  mov     ebx, eax
0x180091638  test    eax, eax
0x18009163a  jns     short loc_180091676
0x18009163c  mov     rcx, cs:WPP_GLOBAL_Control
0x180091643  test    dword ptr [rcx+44h], 400h
0x18009164a  jz      loc_180091BEF
0x180091650  cmp     byte ptr [rcx+41h], 2
0x180091654  jb      loc_180091BEF
0x18009165a  mov     rcx, [rcx+38h]
0x18009165e  lea     edx, [r13+3Fh]
0x180091662  mov     r9d, eax
0x180091665  lea     r8, WPP_99473abb2ee73b6c7cc9b39fb0106789_Traceguids
0x18009166c  call    WPP_SF_d
0x180091671  jmp     loc_180091BEF
0x180091676  mov     ecx, 1
0x18009167b  call    SampSetTransactionDomain
0x180091680  lea     r8, [rbp+90h+SourceString]; unsigned __int16 **
0x180091684  mov     rcx, rdi; this
0x180091687  call    ?FindAvailableSamAccountName@ShadowAdminAccount@@AEAAJKPEAPEAG@Z; ShadowAdminAccount::FindAvailableSamAccountName(ulong,ushort * *)
0x18009168c  mov     r15, [rbp+90h+SourceString]
0x180091690  mov     ebx, eax
0x180091692  test    eax, eax
0x180091694  jns     short loc_1800916BE
0x180091696  mov     rcx, cs:WPP_GLOBAL_Control
0x18009169d  test    dword ptr [rcx+44h], 400h
0x1800916a4  jz      loc_180091B53
0x1800916aa  cmp     byte ptr [rcx+41h], 2
0x1800916ae  jb      loc_180091B53
0x1800916b4  mov     edx, 40h ; '@'
0x1800916b9  jmp     loc_180091B40
0x1800916be  lea     r8, [rbp+90h+var_E8]; unsigned __int16 **
0x1800916c2  mov     rcx, rdi; this
0x1800916c5  call    ?GetShadowAccountFullName@ShadowAdminAccount@@AEAAJKPEAPEAG@Z; ShadowAdminAccount::GetShadowAccountFullName(ulong,ushort * *)
0x1800916ca  mov     ebx, eax
0x1800916cc  test    eax, eax
0x1800916ce  jns     short loc_1800916F8
0x1800916d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800916d7  test    dword ptr [rcx+44h], 400h
0x1800916de  jz      loc_180091B53
0x1800916e4  cmp     byte ptr [rcx+41h], 2
0x1800916e8  jb      loc_180091B53
0x1800916ee  mov     edx, 41h ; 'A'
0x1800916f3  jmp     loc_180091B40
0x1800916f8  lea     r8, [rbp+90h+var_E0]; unsigned __int16 **
0x1800916fc  mov     rcx, rdi; this
0x1800916ff  call    ?GetShadowAccountDescription@ShadowAdminAccount@@AEAAJKPEAPEAG@Z; ShadowAdminAccount::GetShadowAccountDescription(ulong,ushort * *)
0x180091704  mov     ebx, eax
0x180091706  test    eax, eax
0x180091708  jns     short loc_180091732
0x18009170a  mov     rcx, cs:WPP_GLOBAL_Control
0x180091711  test    dword ptr [rcx+44h], 400h
0x180091718  jz      loc_180091B53
0x18009171e  cmp     byte ptr [rcx+41h], 2
0x180091722  jb      loc_180091B53
0x180091728  mov     edx, 42h ; 'B'
0x18009172d  jmp     loc_180091B40
0x180091732  mov     rdx, r15; SourceString
0x180091735  lea     rcx, [rbp+90h+DestinationString]; DestinationString
0x180091739  call    cs:__imp_RtlInitUnicodeString
0x18009173f  mov     rcx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180091746  lea     rax, [rsp+190h+var_124]
0x18009174b  mov     [rsp+190h+var_140], r13b; char
0x180091750  lea     rdx, [rbp+90h+DestinationString]; DestinationString
0x180091754  mov     [rsp+190h+var_148], r13b; unsigned __int8
0x180091759  mov     r9d, 0F07FFh
0x18009175f  mov     [rsp+190h+var_150], rax; __int64
0x180091764  mov     r8d, 10h
0x18009176a  mov     rcx, [rcx+550h]; struct _SAMP_OBJECT *
0x180091771  lea     rax, [rbp+90h+var_110]
0x180091775  mov     qword ptr [rsp+190h+ValueDataSize], rax; __int64
0x18009177a  lea     rax, [rsp+190h+HandleId]
0x18009177f  mov     [rsp+190h+ValueData], rax; __int64
0x180091784  mov     byte ptr [rsp+190h+ValueType], r13b; char
0x180091789  mov     byte ptr [rsp+190h+ValueName], 1; char
0x18009178e  call    SampCreateUserInDomain
0x180091793  mov     ebx, eax
0x180091795  test    eax, eax
0x180091797  jns     short loc_1800917C1
0x180091799  mov     rcx, cs:WPP_GLOBAL_Control
0x1800917a0  test    dword ptr [rcx+44h], 400h
0x1800917a7  jz      loc_180091B53
0x1800917ad  cmp     byte ptr [rcx+41h], 2
0x1800917b1  jb      loc_180091B53
0x1800917b7  mov     edx, 43h ; 'C'
0x1800917bc  jmp     loc_180091B40
0x1800917c1  mov     rcx, [rsp+190h+HandleId]
0x1800917c6  lea     rdx, [rbp+90h+var_A0]
0x1800917ca  call    SampRetrieveUserV1aFixed
0x1800917cf  mov     ebx, eax
0x1800917d1  test    eax, eax
0x1800917d3  jns     short loc_1800917FD
0x1800917d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800917dc  test    dword ptr [rcx+44h], 400h
0x1800917e3  jz      loc_180091B53
0x1800917e9  cmp     byte ptr [rcx+41h], 2
0x1800917ed  jb      loc_180091B53
0x1800917f3  mov     edx, 44h ; 'D'
0x1800917f8  jmp     loc_180091B40
0x1800917fd  mov     rcx, [rsp+190h+HandleId]
0x180091802  lea     rdx, [rbp+90h+var_A0]
0x180091806  mov     [rbp+90h+var_68], 214h
0x18009180d  call    SampReplaceUserV1aFixed
0x180091812  mov     ebx, eax
0x180091814  test    eax, eax
0x180091816  jns     short loc_180091840
0x180091818  mov     rcx, cs:WPP_GLOBAL_Control
0x18009181f  test    dword ptr [rcx+44h], 400h
0x180091826  jz      loc_180091B53
0x18009182c  cmp     byte ptr [rcx+41h], 2
0x180091830  jb      loc_180091B53
0x180091836  mov     edx, 45h ; 'E'
0x18009183b  jmp     loc_180091B40
0x180091840  mov     rcx, [rsp+190h+HandleId]; struct _SAMP_OBJECT *
0x180091845  lea     rdx, [rsp+190h+var_124+4]; void **
0x18009184a  call    ?SampCreateAccountSid@@YAJPEAU_SAMP_OBJECT@@PEAPEAX@Z; SampCreateAccountSid(_SAMP_OBJECT *,void * *)
0x18009184f  mov     ebx, eax
0x180091851  test    eax, eax
0x180091853  jns     short loc_18009188D
0x180091855  mov     rcx, cs:WPP_GLOBAL_Control
0x18009185c  test    dword ptr [rcx+44h], 400h
0x180091863  jz      short loc_180091883
0x180091865  cmp     byte ptr [rcx+41h], 2
0x180091869  jb      short loc_180091883
0x18009186b  mov     rcx, [rcx+38h]
0x18009186f  lea     r8, WPP_99473abb2ee73b6c7cc9b39fb0106789_Traceguids
0x180091876  mov     edx, 46h ; 'F'
0x18009187b  mov     r9d, eax
0x18009187e  call    WPP_SF_d
0x180091883  mov     rsi, qword ptr [rsp+190h+var_124+4]
0x180091888  jmp     loc_180091B53
0x18009188d  mov     rsi, qword ptr [rsp+190h+var_124+4]
0x180091892  lea     rdx, [rbp+90h+StringSid]; StringSid
0x180091896  mov     rcx, rsi; Sid
0x180091899  call    cs:__imp_ConvertSidToStringSidW
0x18009189f  test    eax, eax
0x1800918a1  jnz     short loc_1800918E5
0x1800918a3  call    cs:__imp_GetLastError
0x1800918a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800918b0  test    dword ptr [rcx+44h], 400h
0x1800918b7  jz      short loc_1800918DB
0x1800918b9  cmp     byte ptr [rcx+41h], 2
0x1800918bd  jb      short loc_1800918DB
0x1800918bf  mov     rcx, [rcx+38h]
0x1800918c3  lea     r8, WPP_99473abb2ee73b6c7cc9b39fb0106789_Traceguids
0x1800918ca  mov     edx, 47h ; 'G'
0x1800918cf  mov     dword ptr [rsp+190h+ValueName], eax
0x1800918d3  mov     r9d, eax
0x1800918d6  call    WPP_SF_Dd
0x1800918db  mov     ebx, 0C0000017h
0x1800918e0  jmp     loc_180091B53
0x1800918e5  mov     rcx, [rdi+10h]; Sid
0x1800918e9  mov     qword ptr [rbp+90h+var_100+8], rcx
0x1800918ed  call    cs:__imp_RtlLengthSid
0x1800918f3  mov     rcx, [rsp+190h+HandleId]; struct _SAMP_OBJECT *
0x1800918f8  lea     r8, [rbp+90h+var_100]; void *
0x1800918fc  mov     edx, 27h ; '''; unsigned int
0x180091901  mov     dword ptr [rbp+90h+var_100], eax
0x180091904  call    ?SampSetExtendedAttribute@@YAJPEAU_SAMP_OBJECT@@KPEAX@Z; SampSetExtendedAttribute(_SAMP_OBJECT *,ulong,void *)
0x180091909  mov     ebx, eax
0x18009190b  test    eax, eax
0x18009190d  jns     short loc_180091937
0x18009190f  mov     rcx, cs:WPP_GLOBAL_Control
0x180091916  test    dword ptr [rcx+44h], 400h
0x18009191d  jz      loc_180091B53
0x180091923  cmp     byte ptr [rcx+41h], 2
0x180091927  jb      loc_180091B53
0x18009192d  mov     edx, 48h ; 'H'
0x180091932  jmp     loc_180091B40
0x180091937  mov     rcx, [rsp+190h+HandleId]; struct _SAMP_OBJECT *
0x18009193c  lea     r8, [rsp+190h+var_128]; void *
0x180091941  mov     edx, 13h; unsigned int
0x180091946  mov     [rsp+190h+var_128], 1
0x18009194e  call    ?SampSetExtendedAttribute@@YAJPEAU_SAMP_OBJECT@@KPEAX@Z; SampSetExtendedAttribute(_SAMP_OBJECT *,ulong,void *)
0x180091953  mov     ebx, eax
0x180091955  test    eax, eax
0x180091957  jns     short loc_180091981
0x180091959  mov     rcx, cs:WPP_GLOBAL_Control
0x180091960  test    dword ptr [rcx+44h], 400h
0x180091967  jz      loc_180091B53
0x18009196d  cmp     byte ptr [rcx+41h], 2
0x180091971  jb      loc_180091B53
0x180091977  mov     edx, 49h ; 'I'
0x18009197c  jmp     loc_180091B40
0x180091981  mov     rcx, [rsp+190h+HandleId]; struct _SAMP_OBJECT *
0x180091986  mov     dl, 1
0x180091988  call    SampStoreObjectAttributes
0x18009198d  mov     ebx, eax
0x18009198f  test    eax, eax
0x180091991  jns     short loc_1800919BB
0x180091993  mov     rcx, cs:WPP_GLOBAL_Control
0x18009199a  test    dword ptr [rcx+44h], 400h
0x1800919a1  jz      loc_180091B53
0x1800919a7  cmp     byte ptr [rcx+41h], 2
0x1800919ab  jb      loc_180091B53
0x1800919b1  mov     edx, 4Ah ; 'J'
0x1800919b6  jmp     loc_180091B40
0x1800919bb  cmp     [rdi+40h], r13d
0x1800919bf  jz      loc_180091AB4
0x1800919c5  mov     edx, [rdi+20h]
0x1800919c8  lea     rax, [rsp+190h+var_118]
0x1800919cd  mov     ecx, 4
0x1800919d2  mov     qword ptr [rsp+190h+ValueType], rax
0x1800919d7  call    ?SampCreateAccountContext@@YAJW4_SAMP_OBJECT_TYPE@@KEEEPEAPEAU_SAMP_OBJECT@@@Z; SampCreateAccountContext(_SAMP_OBJECT_TYPE,ulong,uchar,uchar,uchar,_SAMP_OBJECT * *)
0x1800919dc  mov     ebx, eax
0x1800919de  test    eax, eax
0x1800919e0  jns     short loc_180091A24
0x1800919e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800919e9  test    dword ptr [rcx+44h], 400h
0x1800919f0  jz      short loc_180091A1A
0x1800919f2  cmp     byte ptr [rcx+41h], 2
0x1800919f6  jb      short loc_180091A1A
0x1800919f8  mov     r9d, [rdi+20h]
0x1800919fc  lea     r8, WPP_99473abb2ee73b6c7cc9b39fb0106789_Traceguids
0x180091a03  mov     rcx, [rcx+38h]
0x180091a07  mov     edx, 4Bh ; 'K'
0x180091a0c  mov     [rsp+190h+ValueType], eax
0x180091a10  mov     dword ptr [rsp+190h+ValueName], r9d
0x180091a15  call    WPP_SF_DdD
0x180091a1a  mov     r14, [rsp+190h+var_118]
0x180091a1f  jmp     loc_180091B53
0x180091a24  mov     rcx, rsi; Sid
0x180091a27  mov     qword ptr [rbp+90h+var_100+8], rsi
0x180091a2b  call    cs:__imp_RtlLengthSid
0x180091a31  mov     r14, [rsp+190h+var_118]
0x180091a36  lea     r8, [rbp+90h+var_100]; void *
0x180091a3a  mov     rcx, r14; struct _SAMP_OBJECT *
0x180091a3d  mov     dword ptr [rbp+90h+var_100], eax
0x180091a40  mov     edx, 26h ; '&'; unsigned int
0x180091a45  call    ?SampSetExtendedAttribute@@YAJPEAU_SAMP_OBJECT@@KPEAX@Z; SampSetExtendedAttribute(_SAMP_OBJECT *,ulong,void *)
0x180091a4a  mov     ebx, eax
0x180091a4c  test    eax, eax
0x180091a4e  jns     short loc_180091A78
0x180091a50  mov     rcx, cs:WPP_GLOBAL_Control
0x180091a57  test    dword ptr [rcx+44h], 400h
0x180091a5e  jz      loc_180091B53
0x180091a64  cmp     byte ptr [rcx+41h], 2
0x180091a68  jb      loc_180091B53
0x180091a6e  mov     edx, 4Ch ; 'L'
0x180091a73  jmp     loc_180091B40
0x180091a78  mov     dl, 1
0x180091a7a  mov     rcx, r14; struct _SAMP_OBJECT *
0x180091a7d  call    SampStoreObjectAttributes
0x180091a82  mov     ebx, eax
0x180091a84  test    eax, eax
0x180091a86  jns     loc_180091B5F
0x180091a8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180091a93  test    dword ptr [rcx+44h], 400h
0x180091a9a  jz      loc_180091B53
0x180091aa0  cmp     byte ptr [rcx+41h], 2
0x180091aa4  jb      loc_180091B53
0x180091aaa  mov     edx, 4Dh ; 'M'
0x180091aaf  jmp     loc_180091B40
0x180091ab4  lea     rdx, aShadowaccounts; "ShadowAccountSid"
0x180091abb  lea     rcx, [rbp+90h+var_C8]; DestinationString
0x180091abf  call    cs:__imp_RtlInitUnicodeString
0x180091ac5  mov     rdx, [rdi+60h]; SourceString
0x180091ac9  lea     rcx, [rbp+90h+KeyName]; DestinationString
0x180091acd  call    cs:__imp_RtlInitUnicodeString
  ... truncated ...
```
