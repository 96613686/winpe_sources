# UbpmParams::Init(JobMoniker const &,ushort const *)

- ea: `0x18002c1b0`
- end: `0x18002c895`
- name: `?Init@UbpmParams@@QEAAJAEBVJobMoniker@@PEBG@Z`
- size: `1765`
- prototype: `__int64 __fastcall(LPWSTR *this, const struct JobMoniker *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18002b900`

## callees

- `0x18000b4e0`
- `0x18000dc30`
- `0x18000f630`
- `0x18001351c`
- `0x18001a260`
- `0x180028ce0`
- `0x18002ab20`
- `0x18002ab90`
- `0x18002c1b0`
- `0x18002d390`
- `0x18002d3d0`
- `0x18002d6c0`
- `0x18002e23c`
- `0x18002e2ac`
- `0x180030f80`
- `0x180042950`
- `0x180043ac8`
- `0x1800449c8`
- `0x180044e44`
- `0x18004a630`
- `0x18004ef48`
- `0x180052e90`
- `0x180056794`
- `0x1800679e0`
- `0x18006f500`
- `0x18006f5d0`
- `0x180079ae4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c2ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c2ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c32b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c32b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c309`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c309`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002c3f9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002c507`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002c3f9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002c507`
- `api-ms-win-security-credentials-l1-1-0!CredMarshalCredentialW` at `0x18002c2a1`
- `api-ms-win-security-credentials-l1-1-0!CredMarshalCredentialW` at `0x18002c2a1`

## string_xrefs

- `0x18002c6cc`: `NT TASK`

## pseudocode

```c
__int64 __fastcall UbpmParams::Init(LPWSTR *this, const struct JobMoniker *a2, const unsigned __int16 *a3)
{
  const unsigned __int16 *v3; // rdi
  __int64 v6; // r15
  int v7; // eax
  int v8; // r13d
  _BYTE *v9; // rbx
  unsigned __int16 ***Account; // rax
  unsigned __int16 *v11; // rcx
  signed int AliasCredId; // r15d
  void *v13; // rdi
  signed int LastError; // eax
  CredStore *v15; // r12
  struct _RTL_CRITICAL_SECTION *v16; // rdi
  __int64 v17; // rbx
  __int64 v18; // rax
  _QWORD *v19; // rbx
  const unsigned __int16 *v20; // rdx
  void *v21; // rbx
  _QWORD *v22; // rbx
  _OWORD *v23; // rax
  _OWORD *v24; // rcx
  WCHAR *v25; // rax
  __int64 v26; // rdi
  __int64 v27; // rax
  int v28; // edx
  int v29; // ecx
  WCHAR *v30; // rax
  __int64 v31; // rcx
  int v32; // eax
  int v33; // ecx
  int v34; // edx
  _QWORD *v35; // rcx
  _QWORD *v36; // rcx
  const unsigned __int16 *v37; // r8
  __int64 v38; // rax
  WCHAR *v39; // rax
  _WORD *v40; // rcx
  LPWSTR v41; // rbx
  _QWORD *v42; // rcx
  int v43; // edx
  __int64 v44; // rax
  int v45; // eax
  LPWSTR v46; // rcx
  __int64 v48; // [rsp+30h] [rbp-20h] BYREF
  __int128 v49; // [rsp+38h] [rbp-18h] BYREF
  _BYTE *v50; // [rsp+98h] [rbp+48h] BYREF
  const unsigned __int16 *v51; // [rsp+A0h] [rbp+50h]
  void *Credential; // [rsp+A8h] [rbp+58h] BYREF

  v51 = a3;
  v3 = a3;
  v50 = 0;
  v6 = *((_QWORD *)a2 + 4);
  v7 = *(_DWORD *)(v6 + 16);
  v8 = 2;
  if ( ((v7 & 0x40000) != 0 || (v7 & 0x80000) != 0)
    && v7 >= 0
    && UbpmParams::GetUbpmLogonType((UbpmParams *)this, a2) == 4 )
  {
    Credential = 0;
    wmi::AutoRef<User::UserEntry>::operator=(&v50, *(_QWORD *)(v6 + 64));
    v9 = v50;
    if ( v50 && *v50 )
    {
      Account = (unsigned __int16 ***)User::GetAccount(&v50, &v49);
      if ( *Account )
        v11 = **Account;
      else
        v11 = 0;
      AliasCredId = CredStore::GetAliasCredId(v11);
      _bstr_t::~_bstr_t((_bstr_t *)&v49);
    }
    else
    {
      AliasCredId = CredStore::GetCredId((User *)&v50);
      v9 = v50;
    }
    if ( AliasCredId < 0 )
    {
      operator delete(Credential);
      goto LABEL_100;
    }
    v13 = Credential;
    if ( !CredMarshalCredentialW(UsernameTargetCredential, &Credential, this + 70) )
    {
      LastError = GetLastError();
      AliasCredId = LastError;
      if ( LastError > 0 )
        AliasCredId = (unsigned __int16)LastError | 0x80070000;
      if ( AliasCredId < 0 )
      {
        operator delete(v13);
        goto LABEL_100;
      }
    }
    operator delete(v13);
    v3 = v51;
    goto LABEL_33;
  }
  v9 = *(_BYTE **)(v6 + 64);
  if ( !v9 )
  {
LABEL_32:
    wmi::AutoRef<User::UserEntry>::Release(&v50);
    v50 = v9;
    goto LABEL_33;
  }
  if ( !*v9 )
  {
    User::UserEntry::AddRef(*(User::UserEntry **)(v6 + 64));
    goto LABEL_32;
  }
  v15 = (CredStore *)CredStore::g_pCommonStore;
  v16 = User::s_cs;
  EnterCriticalSection(User::s_cs);
  v17 = *(_QWORD *)(v6 + 64);
  v18 = *(_QWORD *)(v17 + 16);
  if ( v18 )
    _InterlockedIncrement((volatile signed __int32 *)(v18 + 16));
  v19 = *(_QWORD **)(v17 + 16);
  Credential = v19;
  LeaveCriticalSection(v16);
  if ( v19 )
    v20 = (const unsigned __int16 *)*v19;
  else
    v20 = 0;
  AliasCredId = CredStore::ResolveAlias(v15, v20, (struct User *)&v50);
  if ( v19 )
    _bstr_t::Data_t::Release((_bstr_t::Data_t *)v19);
  if ( AliasCredId < 0 )
    goto LABEL_100;
  v9 = v50;
  v3 = v51;
LABEL_33:
  if ( !v9 )
  {
    AliasCredId = -2147418113;
    goto LABEL_100;
  }
  if ( *v9 )
  {
    AliasCredId = -2147418113;
    goto LABEL_100;
  }
  if ( !*((_QWORD *)v9 + 4) )
  {
    AliasCredId = User::UpdateEntry((User *)&v50);
    if ( AliasCredId < 0 )
    {
LABEL_100:
      v42 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v43 = 15;
LABEL_114:
        WPP_SF_Sd(
          v42[2],
          v43,
          (unsigned int)WPP_f0f7296807f33a7e423f6d049324e537_Traceguids,
          *((_QWORD *)a2 + 3),
          AliasCredId);
        goto LABEL_115;
      }
      goto LABEL_115;
    }
  }
  v21 = (void *)*((_QWORD *)v9 + 4);
  *((_DWORD *)this + 142) = 1;
  if ( (*(_DWORD *)(*((_QWORD *)a2 + 4) + 16LL) & 0xFC000) == 0x8000 )
  {
    *((_DWORD *)this + 112) = 2;
    DWORD1(v49) = 0;
    *((_QWORD *)&v49 + 1) = v21;
    LODWORD(v49) = GetLengthSid(v21);
    v22 = this + 21;
    v23 = operator new(0x10u);
    v24 = v23;
    if ( v23 )
      *v23 = v49;
    else
      v24 = 0;
    v48 = (__int64)v24;
    *(_QWORD *)&v49 = &v48;
    BYTE8(v49) = 1;
    v25 = this[22];
    if ( &v48 >= (__int64 *)v25 || *v22 > (unsigned __int64)&v48 )
    {
      if ( v25 == this[23] )
      {
        std::vector<unsigned short *>::_Reserve(this + 21);
        v24 = (_OWORD *)v48;
      }
      *(_QWORD *)this[22] = v24;
    }
    else
    {
      v26 = ((__int64)&v48 - *v22) >> 3;
      if ( v25 == this[23] )
        std::vector<unsigned short *>::_Reserve(this + 21);
      *(_QWORD *)this[22] = *(_QWORD *)(*v22 + 8 * v26);
      v3 = v51;
    }
    AliasCredId = 0;
    this[22] += 4;
    v27 = v48;
    *((_DWORD *)this + 120) = 2;
  }
  else
  {
    *((_DWORD *)this + 112) = 1;
    v28 = *(_DWORD *)(*((_QWORD *)a2 + 4) + 16LL);
    if ( (v28 & 0x10000) != 0 )
    {
      v29 = 2;
    }
    else if ( (v28 & 0x20000) != 0 )
    {
      v29 = 5;
    }
    else
    {
      v29 = 4;
      if ( v28 < 0 )
        v29 = 5;
    }
    *((_DWORD *)this + 120) = v29;
    if ( User::IsLocalSystem((User *)(*((_QWORD *)a2 + 4) + 64LL)) )
    {
      v27 = 0;
    }
    else
    {
      DWORD1(v49) = 0;
      *((_QWORD *)&v49 + 1) = v21;
      LODWORD(v49) = GetLengthSid(v21);
      v27 = UbpmParams::NewHostedObject<std::vector<_DAB_SID_INFO *>,_DAB_SID_INFO>(this + 21, &v49);
    }
    AliasCredId = 0;
  }
  this[57] = (LPWSTR)v27;
  v30 = this[70];
  this[58] = v30;
  if ( !v30 )
    this[59] = (LPWSTR)v3;
  v31 = *((_QWORD *)a2 + 4);
  v32 = *(_DWORD *)(v31 + 16);
  if ( (v32 & 0x10000) != 0 || (v32 & 0x80000) != 0 || (v32 & 0x8000) != 0 )
  {
    if ( (v32 & 0x1000000) != 0 || User::IsLocalAdmin((User *)(v31 + 64)) )
      v8 = 1;
  }
  else
  {
    v8 = 0;
  }
  *((_DWORD *)this + 121) = v8;
  v33 = *(_DWORD *)(*((_QWORD *)a2 + 4) + 16LL);
  v34 = ((unsigned int)v33 >> 14) & 1;
  if ( v33 < 0 )
    v34 = (*(_DWORD *)(*((_QWORD *)a2 + 4) + 16LL) >> 14) & 1 | 2;
  if ( (v33 & 0x80000) != 0 )
    v34 |= 4u;
  *((_DWORD *)this + 131) = v34;
  if ( User::IsLocalService((User *)&v50) || User::IsNetworkService((User *)&v50) )
  {
    v38 = *(_QWORD *)(*((_QWORD *)a2 + 4) + 208LL);
    if ( !v38 || (v39 = *(WCHAR **)(v38 + 48)) == 0 )
    {
      *((_BYTE *)this + 496) = 1;
      v39 = 0;
    }
    this[61] = v39;
    if ( (*(_DWORD *)(*((_QWORD *)a2 + 4) + 16LL) & 0x8000000) != 0 )
    {
      *((_BYTE *)this + 497) = 0;
    }
    else
    {
      *((_BYTE *)this + 497) = 1;
      this[63] = (LPWSTR)L"NT TASK";
      this[64] = UbpmParams::CreateHostedVirtualUserName((UbpmParams *)this, a2);
      *((_DWORD *)this + 130) = 87;
    }
  }
  else
  {
    this[61] = 0;
    *((_BYTE *)this + 497) = 0;
    v35 = *(_QWORD **)(*((_QWORD *)a2 + 4) + 176LL);
    if ( v35 && *v35 )
    {
      this[66] = (LPWSTR)UbpmParams::CreateHostedPackageSid((UbpmParams *)this, a2);
      v36 = *(_QWORD **)(*((_QWORD *)a2 + 4) + 176LL);
      v37 = v36 ? (const unsigned __int16 *)*v36 : 0LL;
      this[67] = UbpmParams::NewHostedString((__int64)v36, this + 15, v37, 0x7FFFFFFFu);
      if ( (unsigned int)((__int64)(*(_QWORD *)(*((_QWORD *)a2 + 4) + 192LL) - *(_QWORD *)(*((_QWORD *)a2 + 4) + 184LL)) >> 3) )
      {
        this[69] = (LPWSTR)UbpmParams::CreateHostedCapabilitiesSidArray((UbpmParams *)this, a2);
        *((_DWORD *)this + 136) = (__int64)(*(_QWORD *)(*((_QWORD *)a2 + 4) + 192LL)
                                          - *(_QWORD *)(*((_QWORD *)a2 + 4) + 184LL)) >> 3;
      }
    }
  }
  v40 = *(_WORD **)(*((_QWORD *)a2 + 4) + 208LL);
  if ( v40 && (v40[28] || v40[29] || v40[30] || v40[31] || v40[32] || v40[33] || v40[34]) )
  {
    v41 = (LPWSTR)operator new(0x1Eu);
    if ( !v41 )
    {
      AliasCredId = -2147024882;
      goto LABEL_100;
    }
    JobBucket::GetPeriodicity(*((_QWORD *)a2 + 4), &v49);
    *(_QWORD *)v41 = v49;
    *((_DWORD *)v41 + 2) = DWORD2(v49);
    v41[6] = WORD6(v49);
    JobBucket::GetDeadline(*((_QWORD *)a2 + 4), &v49);
    *(_QWORD *)(v41 + 7) = v49;
    *(_DWORD *)(v41 + 11) = DWORD2(v49);
    v41[13] = WORD6(v49);
    v44 = *(_QWORD *)(*((_QWORD *)a2 + 4) + 208LL);
    if ( v44 )
      v45 = *(_DWORD *)(v44 + 84);
    else
      v45 = 0;
    *((_BYTE *)v41 + 28) = v45 != 0;
    v46 = this[115];
    if ( v41 != v46 )
      operator delete(v46);
    this[115] = v41;
  }
  v42 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v43 = 16;
    goto LABEL_114;
  }
LABEL_115:
  wmi::AutoRef<User::UserEntry>::Release(&v50);
  return (unsigned int)AliasCredId;
}

```

## disassembly

```asm
0x18002c1b0  mov     [rsp-38h+arg_0], rbx
0x18002c1b5  mov     [rsp-38h+arg_10], r8
0x18002c1ba  push    rbp
0x18002c1bb  push    rsi
0x18002c1bc  push    rdi
0x18002c1bd  push    r12
0x18002c1bf  push    r13
0x18002c1c1  push    r14
0x18002c1c3  push    r15
0x18002c1c5  mov     rbp, rsp
0x18002c1c8  sub     rsp, 50h
0x18002c1cc  mov     rdi, r8
0x18002c1cf  mov     r14, rdx
0x18002c1d2  mov     rsi, rcx
0x18002c1d5  xor     r12d, r12d
0x18002c1d8  mov     [rbp+arg_8], r12
0x18002c1dc  mov     r15, [rdx+20h]
0x18002c1e0  mov     eax, [r15+10h]
0x18002c1e4  mov     r13d, 2
0x18002c1ea  bt      eax, 12h
0x18002c1ee  jb      short loc_18002C1FA
0x18002c1f0  bt      eax, 13h
0x18002c1f4  jnb     loc_18002C2E6
0x18002c1fa  test    eax, eax
0x18002c1fc  js      loc_18002C2E6
0x18002c202  call    ?GetUbpmLogonType@UbpmParams@@AEBAKAEBVJobMoniker@@@Z; UbpmParams::GetUbpmLogonType(JobMoniker const &)
0x18002c207  cmp     eax, 4
0x18002c20a  jnz     loc_18002C2E6
0x18002c210  mov     [rbp+Credential], r12
0x18002c214  mov     rdx, [r15+40h]
0x18002c218  lea     rcx, [rbp+arg_8]
0x18002c21c  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x18002c221  mov     rbx, [rbp+arg_8]
0x18002c225  test    rbx, rbx
0x18002c228  jz      short loc_18002C264
0x18002c22a  cmp     byte ptr [rbx], 0
0x18002c22d  jz      short loc_18002C264
0x18002c22f  lea     rdx, [rbp+var_18]
0x18002c233  lea     rcx, [rbp+arg_8]
0x18002c237  call    ?GetAccount@User@@QEBA?BV_bstr_t@@XZ; User::GetAccount(void)
0x18002c23c  nop
0x18002c23d  mov     rcx, [rax]
0x18002c240  test    rcx, rcx
0x18002c243  jz      short loc_18002C24A
0x18002c245  mov     rcx, [rcx]
0x18002c248  jmp     short loc_18002C24D
0x18002c24a  mov     rcx, r12; unsigned __int16 *
0x18002c24d  lea     rdx, [rbp+Credential]
0x18002c251  call    ?GetAliasCredId@CredStore@@SAJPEBGAEAV?$AutoVectorPtr@G@wmi@@@Z; CredStore::GetAliasCredId(ushort const *,wmi::AutoVectorPtr<ushort> &)
0x18002c256  mov     r15d, eax
0x18002c259  lea     rcx, [rbp+var_18]; this
0x18002c25d  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18002c262  jmp     short loc_18002C278
0x18002c264  lea     rdx, [rbp+Credential]
0x18002c268  lea     rcx, [rbp+arg_8]; this
0x18002c26c  call    ?GetCredId@CredStore@@SAJAEBVUser@@AEAV?$AutoVectorPtr@G@wmi@@@Z; CredStore::GetCredId(User const &,wmi::AutoVectorPtr<ushort> &)
0x18002c271  mov     r15d, eax
0x18002c274  mov     rbx, [rbp+arg_8]
0x18002c278  test    r15d, r15d
0x18002c27b  jns     short loc_18002C28B
0x18002c27d  mov     rcx, [rbp+Credential]; void *
0x18002c281  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002c286  jmp     loc_18002C757
0x18002c28b  mov     rdi, [rbp+Credential]
0x18002c28f  mov     [rbp+Credential], rdi
0x18002c293  lea     r8, [rsi+230h]; MarshaledCredential
0x18002c29a  lea     rdx, [rbp+Credential]; Credential
0x18002c29e  mov     ecx, r13d; CredType
0x18002c2a1  call    cs:__imp_CredMarshalCredentialW
0x18002c2a7  test    eax, eax
0x18002c2a9  jnz     short loc_18002C2D5
0x18002c2ab  call    cs:__imp_GetLastError
0x18002c2b1  mov     r15d, eax
0x18002c2b4  test    eax, eax
0x18002c2b6  jle     short loc_18002C2C3
0x18002c2b8  movzx   r15d, ax
0x18002c2bc  or      r15d, 80070000h
0x18002c2c3  test    r15d, r15d
0x18002c2c6  jns     short loc_18002C2D5
0x18002c2c8  mov     rcx, rdi; void *
0x18002c2cb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002c2d0  jmp     loc_18002C757
0x18002c2d5  mov     rcx, rdi; void *
0x18002c2d8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002c2dd  mov     rdi, [rbp+arg_10]
0x18002c2e1  jmp     loc_18002C385
0x18002c2e6  mov     rbx, [r15+40h]
0x18002c2ea  test    rbx, rbx
0x18002c2ed  jz      loc_18002C378
0x18002c2f3  cmp     byte ptr [rbx], 0
0x18002c2f6  jz      short loc_18002C370
0x18002c2f8  mov     r12, cs:?g_pCommonStore@CredStore@@0PEAV1@EA; CredStore * CredStore::g_pCommonStore
0x18002c2ff  mov     rdi, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18002c306  mov     rcx, rdi; lpCriticalSection
0x18002c309  call    cs:__imp_EnterCriticalSection
0x18002c30f  mov     rbx, [r15+40h]
0x18002c313  mov     rax, [rbx+10h]
0x18002c317  test    rax, rax
0x18002c31a  jz      short loc_18002C320
0x18002c31c  lock inc dword ptr [rax+10h]
0x18002c320  mov     rbx, [rbx+10h]
0x18002c324  mov     [rbp+Credential], rbx
0x18002c328  mov     rcx, rdi; lpCriticalSection
0x18002c32b  call    cs:__imp_LeaveCriticalSection
0x18002c331  nop
0x18002c332  test    rbx, rbx
0x18002c335  jz      short loc_18002C33C
0x18002c337  mov     rdx, [rbx]
0x18002c33a  jmp     short loc_18002C33E
0x18002c33c  xor     edx, edx; unsigned __int16 *
0x18002c33e  lea     r8, [rbp+arg_8]; struct User *
0x18002c342  mov     rcx, r12; this
0x18002c345  call    ?ResolveAlias@CredStore@@QEAAJPEBGAEAVUser@@@Z; CredStore::ResolveAlias(ushort const *,User &)
0x18002c34a  mov     r15d, eax
0x18002c34d  test    rbx, rbx
0x18002c350  jz      short loc_18002C35A
0x18002c352  mov     rcx, rbx; this
0x18002c355  call    ?Release@Data_t@_bstr_t@@QEAAKXZ; _bstr_t::Data_t::Release(void)
0x18002c35a  test    r15d, r15d
0x18002c35d  js      loc_18002C757
0x18002c363  mov     rbx, [rbp+arg_8]
0x18002c367  mov     rdi, [rbp+arg_10]
0x18002c36b  xor     r12d, r12d
0x18002c36e  jmp     short loc_18002C385
0x18002c370  mov     rcx, rbx; this
0x18002c373  call    ?AddRef@UserEntry@User@@QEAAKXZ; User::UserEntry::AddRef(void)
0x18002c378  lea     rcx, [rbp+arg_8]
0x18002c37c  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18002c381  mov     [rbp+arg_8], rbx
0x18002c385  test    rbx, rbx
0x18002c388  jnz     short loc_18002C395
0x18002c38a  mov     r15d, 8000FFFFh
0x18002c390  jmp     loc_18002C757
0x18002c395  cmp     byte ptr [rbx], 0
0x18002c398  jz      short loc_18002C3A5
0x18002c39a  mov     r15d, 8000FFFFh
0x18002c3a0  jmp     loc_18002C757
0x18002c3a5  cmp     qword ptr [rbx+20h], 0
0x18002c3aa  jnz     short loc_18002C3C0
0x18002c3ac  lea     rcx, [rbp+arg_8]; this
0x18002c3b0  call    ?UpdateEntry@User@@AEBAJXZ; User::UpdateEntry(void)
0x18002c3b5  mov     r15d, eax
0x18002c3b8  test    eax, eax
0x18002c3ba  js      loc_18002C757
0x18002c3c0  mov     rbx, [rbx+20h]
0x18002c3c4  mov     dword ptr [rsi+238h], 1
0x18002c3ce  mov     rax, [r14+20h]
0x18002c3d2  mov     edx, [rax+10h]
0x18002c3d5  and     edx, 0FC000h
0x18002c3db  cmp     edx, 8000h
0x18002c3e1  jnz     loc_18002C4A8
0x18002c3e7  mov     [rsi+1C0h], r13d
0x18002c3ee  mov     dword ptr [rbp+var_18+4], r12d
0x18002c3f2  mov     qword ptr [rbp+var_18+8], rbx
0x18002c3f6  mov     rcx, rbx; pSid
0x18002c3f9  call    cs:__imp_GetLengthSid
0x18002c3ff  mov     dword ptr [rbp+var_18], eax
0x18002c402  lea     rbx, [rsi+0A8h]
0x18002c409  mov     ecx, 10h; dwBytes
0x18002c40e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002c413  mov     rcx, rax
0x18002c416  test    rax, rax
0x18002c419  jz      short loc_18002C424
0x18002c41b  movups  xmm0, [rbp+var_18]
0x18002c41f  movups  xmmword ptr [rax], xmm0
0x18002c422  jmp     short loc_18002C427
0x18002c424  mov     rcx, r12
0x18002c427  mov     [rbp+var_20], rcx
0x18002c42b  lea     rax, [rbp+var_20]
0x18002c42f  mov     qword ptr [rbp+var_18], rax
0x18002c433  mov     byte ptr [rbp+var_18+8], 1
0x18002c437  mov     rax, [rbx+8]
0x18002c43b  lea     rdx, [rbp+var_20]
0x18002c43f  cmp     rdx, rax
0x18002c442  jnb     short loc_18002C47A
0x18002c444  lea     rdx, [rbp+var_20]
0x18002c448  cmp     [rbx], rdx
0x18002c44b  ja      short loc_18002C47A
0x18002c44d  lea     rdi, [rbp+var_20]
0x18002c451  sub     rdi, [rbx]
0x18002c454  sar     rdi, 3
0x18002c458  cmp     rax, [rbx+10h]
0x18002c45c  jnz     short loc_18002C466
0x18002c45e  mov     rcx, rbx
0x18002c461  call    ?_Reserve@?$vector@PEAGV?$allocator@PEAG@std@@@std@@IEAAX_K@Z; std::vector<ushort *>::_Reserve(unsigned __int64)
0x18002c466  mov     rax, [rbx]
0x18002c469  mov     rcx, [rbx+8]
0x18002c46d  mov     rax, [rax+rdi*8]
0x18002c471  mov     [rcx], rax
0x18002c474  mov     rdi, [rbp+arg_10]
0x18002c478  jmp     short loc_18002C493
0x18002c47a  cmp     rax, [rbx+10h]
0x18002c47e  jnz     short loc_18002C48C
0x18002c480  mov     rcx, rbx
0x18002c483  call    ?_Reserve@?$vector@PEAGV?$allocator@PEAG@std@@@std@@IEAAX_K@Z; std::vector<ushort *>::_Reserve(unsigned __int64)
0x18002c488  mov     rcx, [rbp+var_20]
0x18002c48c  mov     rax, [rbx+8]
0x18002c490  mov     [rax], rcx
0x18002c493  mov     r15d, r12d
0x18002c496  add     qword ptr [rbx+8], 8
0x18002c49b  mov     rax, [rbp+var_20]
0x18002c49f  mov     [rsi+1E0h], r13d
0x18002c4a6  jmp     short loc_18002C523
0x18002c4a8  mov     dword ptr [rsi+1C0h], 1
0x18002c4b2  mov     rax, [r14+20h]
0x18002c4b6  mov     edx, [rax+10h]
0x18002c4b9  bt      edx, 10h
0x18002c4bd  jnb     short loc_18002C4C4
0x18002c4bf  mov     ecx, r13d
0x18002c4c2  jmp     short loc_18002C4E0
0x18002c4c4  bt      edx, 11h
0x18002c4c8  jnb     short loc_18002C4D1
0x18002c4ca  mov     ecx, 5
0x18002c4cf  jmp     short loc_18002C4E0
0x18002c4d1  mov     eax, 5
0x18002c4d6  mov     ecx, 4
0x18002c4db  test    edx, edx
0x18002c4dd  cmovs   ecx, eax
0x18002c4e0  mov     [rsi+1E0h], ecx
0x18002c4e6  mov     rcx, [r14+20h]
0x18002c4ea  add     rcx, 40h ; '@'; this
0x18002c4ee  call    ?IsLocalSystem@User@@QEBA_NXZ; User::IsLocalSystem(void)
0x18002c4f3  test    al, al
0x18002c4f5  jz      short loc_18002C4FC
0x18002c4f7  mov     rax, r12
0x18002c4fa  jmp     short loc_18002C520
0x18002c4fc  mov     dword ptr [rbp+var_18+4], r12d
0x18002c500  mov     qword ptr [rbp+var_18+8], rbx
0x18002c504  mov     rcx, rbx; pSid
0x18002c507  call    cs:__imp_GetLengthSid
0x18002c50d  mov     dword ptr [rbp+var_18], eax
0x18002c510  lea     rcx, [rsi+0A8h]
0x18002c517  lea     rdx, [rbp+var_18]
0x18002c51b  call    ??$NewHostedObject@V?$vector@PEAU_DAB_SID_INFO@@V?$allocator@PEAU_DAB_SID_INFO@@@std@@@std@@U_DAB_SID_INFO@@@UbpmParams@@CAPEAU_DAB_SID_INFO@@AEAV?$vector@PEAU_DAB_SID_INFO@@V?$allocator@PEAU_DAB_SID_INFO@@@std@@@std@@AEBU1@@Z; UbpmParams::NewHostedObject<std::vector<_DAB_SID_INFO *>,_DAB_SID_INFO>(std::vector<_DAB_SID_INFO *> &,_DAB_SID_INFO const &)
0x18002c520  mov     r15d, r12d
0x18002c523  mov     [rsi+1C8h], rax
0x18002c52a  mov     rax, [rsi+230h]
0x18002c531  mov     [rsi+1D0h], rax
0x18002c538  test    rax, rax
0x18002c53b  jnz     short loc_18002C544
0x18002c53d  mov     [rsi+1D8h], rdi
0x18002c544  mov     rcx, [r14+20h]
0x18002c548  mov     eax, [rcx+10h]
0x18002c54b  bt      eax, 10h
0x18002c54f  jb      short loc_18002C562
0x18002c551  bt      eax, 13h
0x18002c555  jb      short loc_18002C562
0x18002c557  bt      eax, 0Fh
0x18002c55b  jb      short loc_18002C562
0x18002c55d  mov     r13d, r12d
0x18002c560  jmp     short loc_18002C57B
0x18002c562  bt      eax, 18h
0x18002c566  jb      short loc_18002C575
0x18002c568  add     rcx, 40h ; '@'; this
0x18002c56c  call    ?IsLocalAdmin@User@@QEBA_NXZ; User::IsLocalAdmin(void)
0x18002c571  test    al, al
0x18002c573  jz      short loc_18002C57B
0x18002c575  mov     r13d, 1
0x18002c57b  mov     [rsi+1E4h], r13d
0x18002c582  mov     rax, [r14+20h]
0x18002c586  mov     ecx, [rax+10h]
0x18002c589  mov     edx, ecx
0x18002c58b  shr     edx, 0Eh
0x18002c58e  and     edx, 1
0x18002c591  mov     eax, edx
0x18002c593  or      eax, 2
0x18002c596  test    ecx, ecx
0x18002c598  cmovs   edx, eax
0x18002c59b  bt      ecx, 13h
0x18002c59f  jnb     short loc_18002C5A4
0x18002c5a1  or      edx, 4
0x18002c5a4  mov     [rsi+20Ch], edx
0x18002c5aa  lea     rcx, [rbp+arg_8]; this
0x18002c5ae  call    ?IsLocalService@User@@QEBA_NXZ; User::IsLocalService(void)
0x18002c5b3  test    al, al
0x18002c5b5  jnz     loc_18002C685
0x18002c5bb  lea     rcx, [rbp+arg_8]; this
0x18002c5bf  call    ?IsNetworkService@User@@QEBA_NXZ; User::IsNetworkService(void)
0x18002c5c4  test    al, al
0x18002c5c6  jnz     loc_18002C685
0x18002c5cc  mov     [rsi+1E8h], r12
0x18002c5d3  mov     [rsi+1F1h], al
0x18002c5d9  mov     rax, [r14+20h]
0x18002c5dd  mov     rcx, [rax+0B0h]
0x18002c5e4  test    rcx, rcx
0x18002c5e7  jz      loc_18002C6F6
0x18002c5ed  cmp     qword ptr [rcx], 0
0x18002c5f1  jz      loc_18002C6F6
0x18002c5f7  mov     rdx, r14; struct JobMoniker *
0x18002c5fa  mov     rcx, rsi; this
0x18002c5fd  call    ?CreateHostedPackageSid@UbpmParams@@AEAAPEAXAEBVJobMoniker@@@Z; UbpmParams::CreateHostedPackageSid(JobMoniker const &)
0x18002c602  mov     [rsi+210h], rax
0x18002c609  mov     rax, [r14+20h]
0x18002c60d  mov     rcx, [rax+0B0h]
0x18002c614  test    rcx, rcx
0x18002c617  jz      short loc_18002C61E
0x18002c619  mov     r8, [rcx]
0x18002c61c  jmp     short loc_18002C621
0x18002c61e  mov     r8, r12
0x18002c621  lea     rdx, [rsi+78h]
  ... truncated ...
```
