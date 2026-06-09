# SpCommonAcquireCredentialsHandle(_UNICODE_STRING *,ulong,_LUID *,void *,unsigned __int64 *,_LARGE_INTEGER *)

- ea: `0x18002b800`
- end: `0x18002c0bc`
- name: `?SpCommonAcquireCredentialsHandle@@YAJPEAU_UNICODE_STRING@@KPEAU_LUID@@PEAXPEA_KPEAT_LARGE_INTEGER@@@Z`
- size: `2236`
- prototype: `int(struct _UNICODE_STRING *, unsigned int, struct _LUID *, void *, unsigned __int64 *, union _LARGE_INTEGER *)`
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002b5f0`

## callees

- `0x180005d60`
- `0x1800106e0`
- `0x1800110b0`
- `0x1800110e4`
- `0x1800112c0`
- `0x180011e0c`
- `0x180012d10`
- `0x180021da8`
- `0x180021e64`
- `0x180021eb0`
- `0x180025c38`
- `0x18002ac60`
- `0x18002acc0`
- `0x18002adf4`
- `0x18002b800`
- `0x18002ce4c`
- `0x180052c10`
- `0x180057c8c`
- `0x180057cb4`
- `0x1800597b0`
- `0x18005a154`
- `0x18005a160`
- `0x18005c3a0`
- `0x18005c8f4`
- `0x18005ca90`
- `0x18005cf90`
- `0x180091010`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x18002bf0a`
- `ntdll!RtlEnterCriticalSection` at `0x18002bf0a`
- `ntdll!RtlLeaveCriticalSection` at `0x18002bf3a`
- `ntdll!RtlLeaveCriticalSection` at `0x18002bf3a`
- `ntdll!NtClose` at `0x18002bfd0`
- `ntdll!NtClose` at `0x18002bfd0`
- `ntdll!NtDuplicateObject` at `0x18002ba88`
- `ntdll!NtDuplicateObject` at `0x18002ba88`
- `ntdll!RtlNtStatusToDosError` at `0x18002bfb7`
- `ntdll!RtlNtStatusToDosError` at `0x18002bfb7`

## pseudocode

```c
__int64 __fastcall SpCommonAcquireCredentialsHandle(
        struct _UNICODE_STRING *a1,
        unsigned int a2,
        struct _LUID *a3,
        struct _SCHANNEL_CRED *a4,
        unsigned __int64 *a5,
        union _LARGE_INTEGER *a6)
{
  CCipherMill *v9; // rcx
  int v10; // r12d
  char v11; // si
  int v12; // r14d
  unsigned int v13; // ebx
  int ProcessImageName; // eax
  NTSTATUS v15; // ecx
  NTSTATUS v16; // eax
  CSslCredManager *v17; // rcx
  CCipherMill *v18; // rax
  __int64 v19; // rdx
  bool v20; // al
  char v21; // bl
  signed int v22; // eax
  bool v23; // si
  unsigned int v24; // ecx
  char v25; // r8
  signed int v26; // eax
  char v27; // r12
  unsigned int v28; // r13d
  _DWORD *v29; // rax
  struct _SCHANNEL_CRED **v30; // rax
  unsigned int DefaultMachineCred; // edi
  CSslCredManager *v32; // r14
  void *v33; // rdi
  CCredentialGroup *v34; // rax
  CCredentialGroup *v35; // rbx
  CSslCredManager **v36; // r8
  CCredentialGroup *v37; // rax
  int DesiredAccess; // [rsp+20h] [rbp-E0h]
  char v40; // [rsp+40h] [rbp-C0h]
  bool v41; // [rsp+41h] [rbp-BFh]
  void *TargetHandle; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v43; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v44; // [rsp+54h] [rbp-ACh] BYREF
  struct _SecBuffer v45; // [rsp+58h] [rbp-A8h] BYREF
  CCredentialGroup *v46; // [rsp+68h] [rbp-98h] BYREF
  struct _LUID v47; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING *v48; // [rsp+78h] [rbp-88h]
  unsigned __int64 *v49; // [rsp+80h] [rbp-80h]
  union _LARGE_INTEGER *v50; // [rsp+88h] [rbp-78h]
  DWORD dwProcessId[4]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v52; // [rsp+A0h] [rbp-60h]
  __int128 v53; // [rsp+A8h] [rbp-58h] BYREF
  HANDLE SourceHandle[2]; // [rsp+B8h] [rbp-48h]
  _DWORD v55[18]; // [rsp+D0h] [rbp-30h] BYREF
  int v56; // [rsp+118h] [rbp+18h]
  unsigned __int16 v57[2]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v58[524]; // [rsp+144h] [rbp+44h] BYREF

  v49 = a5;
  v48 = a1;
  v50 = a6;
  v46 = 0;
  memset_0(v55, 0, 0x70u);
  v44 = 0;
  v47 = 0;
  TargetHandle = 0;
  v52 = 0;
  v53 = 0;
  v43 = 0;
  *(_OWORD *)SourceHandle = 0;
  *(_OWORD *)dwProcessId = 0;
  v45 = 0;
  if ( !(unsigned int)SchannelInit(0)
    || !LsaTable
    || !(*(unsigned __int8 (__fastcall **)(DWORD *))(LsaTable + 192))(dwProcessId) )
  {
    return 2148074244LL;
  }
  *(_DWORD *)v57 = 0;
  memset_0(v58, 0, 0x204u);
  if ( (dwProcessId[2] & 0x2000) != 0 )
  {
    o_wcsncpy_s_0(v57, 260, L"SYSTEM", -1);
    goto LABEL_6;
  }
  ProcessImageName = GetProcessImageName(v57, dwProcessId[0]);
  if ( ProcessImageName >= 0 )
  {
LABEL_6:
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          51,
          WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids,
          dwProcessId[0]);
        v9 = WPP_GLOBAL_Control;
      }
      if ( v9 != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 4) != 0 )
        WPP_SF_S(*((_QWORD *)v9 + 2), 52, WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids, v57);
    }
    goto LABEL_12;
  }
  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      50,
      WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids,
      (unsigned int)ProcessImageName,
      dwProcessId[0]);
LABEL_12:
  v10 = dwProcessId[2] & 0x40;
  v11 = dwProcessId[2] & 1;
  v12 = dwProcessId[2] & 0x11;
  if ( (*(int (__fastcall **)(__int128 *))(LsaTable + 128))(&v53) < 0 )
  {
LABEL_13:
    v13 = -2146893052;
    goto LABEL_120;
  }
  if ( a3 && (a3->LowPart || a3->HighPart) )
  {
    if ( !LOBYTE(SourceHandle[0]) )
    {
      v15 = -1073741727;
LABEL_118:
      v22 = RtlNtStatusToDosError(v15);
      goto LABEL_119;
    }
    v47 = *a3;
    v16 = (*(__int64 (__fastcall **)(struct _LUID *, void **))(LsaTable + 368))(a3, &TargetHandle);
    if ( v16 < 0 )
    {
LABEL_24:
      v15 = v16;
      goto LABEL_118;
    }
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v19 = 53;
LABEL_33:
      WPP_SF_q(*((_QWORD *)v18 + 2), v19, WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids, TargetHandle);
    }
  }
  else
  {
    if ( (unsigned __int64)SourceHandle[1] - 1 > 0xFFFFFFFFFFFFFFFDuLL )
    {
      v15 = -1073741670;
      goto LABEL_118;
    }
    v47 = (struct _LUID)v53;
    v16 = NtDuplicateObject(
            (HANDLE)0xFFFFFFFFFFFFFFFFLL,
            SourceHandle[1],
            (HANDLE)0xFFFFFFFFFFFFFFFFLL,
            &TargetHandle,
            0,
            0,
            2u);
    if ( v16 < 0 )
      goto LABEL_24;
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v19 = 54;
      goto LABEL_33;
    }
  }
  if ( SHIDWORD(SourceHandle[0]) <= 1 )
  {
    v13 = -2146893042;
    goto LABEL_120;
  }
  v20 = 0;
  v55[0] = 4;
  v21 = 0;
  v41 = 0;
  v40 = 0;
  if ( !a4 )
    goto LABEL_91;
  if ( !v11 )
  {
    v22 = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned int *, struct _SCHANNEL_CRED *))(LsaTable + 80))(
            0,
            4,
            &v44,
            a4);
    if ( v22 < 0 )
      goto LABEL_119;
    if ( v12 )
    {
      v23 = 0;
    }
    else
    {
      if ( (*(int (__fastcall **)(unsigned int *, _QWORD, _QWORD, struct _SecBuffer *, _QWORD))(LsaTable + 488))(
             &v43,
             0,
             0,
             &v45,
             0) < 0 )
        goto LABEL_13;
      v21 = 1;
      v40 = 1;
      v23 = v45.pvBuffer != 0;
      v41 = v45.pvBuffer != 0;
      if ( v43 && (!v45.pvBuffer || !v45.cbBuffer) )
      {
        v13 = -2146893043;
LABEL_116:
        CleanupAppModeInfo(!v23, &v45);
        goto LABEL_120;
      }
    }
    v24 = v44;
    if ( v44 != 3 && v44 != 4 && v44 != 5 )
    {
      if ( v44 != 512 )
      {
        if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids, v44);
        v13 = -2146893043;
        goto LABEL_72;
      }
      if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids, 512);
      v25 = (a2 & 0x800A2AAA) != 0 && !v12;
      v26 = SpMapAuthIdentity(a4, &v45, v25, v10 != 0, (struct LSA_SCHANNEL_CRED *)v55, TargetHandle);
      if ( v26 == 590610 )
      {
LABEL_69:
        v13 = 590610;
        goto LABEL_120;
      }
      if ( v26 )
        goto LABEL_71;
      goto LABEL_90;
    }
    if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids, v44);
      v24 = v44;
    }
    if ( v10 )
      v26 = SpWow64MapVersion3Certificate(a4, v24, &v45, (struct LSA_SCHANNEL_CRED *)v55);
    else
      v26 = SpMapVersion3Certificate(a4, v24, &v45, (struct LSA_SCHANNEL_CRED *)v55);
    if ( v26 == 590610 )
    {
      if ( !v12 )
      {
        v43 = 10;
        v28 = -(a2 & 0x800A2AAA);
        if ( v10 )
        {
          v45.cbBuffer = 4;
          v29 = (_DWORD *)(*(__int64 (__fastcall **)(__int64))(LsaTable + 384))(4);
          v45.pvBuffer = v29;
          if ( !v29 )
          {
LABEL_83:
            v13 = -2146893056;
            goto LABEL_72;
          }
          *v29 = (_DWORD)a4;
        }
        else
        {
          v45.cbBuffer = 8;
          v30 = (struct _SCHANNEL_CRED **)(*(__int64 (**)(void))(LsaTable + 384))();
          v45.pvBuffer = v30;
          if ( !v30 )
            goto LABEL_83;
          *v30 = a4;
        }
        v45.BufferType = 1;
        LOBYTE(DesiredAccess) = 1;
        v26 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, struct _SecBuffer *, int))(LsaTable + 496))(
                v43,
                0,
                v28 != 0 ? 12LL : 8LL,
                &v45,
                DesiredAccess);
        if ( v26 >= 0 )
          goto LABEL_69;
LABEL_71:
        v13 = TranslateToSecurityStatus(v26);
LABEL_72:
        v27 = v40;
        goto LABEL_115;
      }
    }
    else if ( v26 < 0 )
    {
      goto LABEL_71;
    }
LABEL_90:
    v20 = v41;
LABEL_91:
    if ( (v56 & 0xF0000) != 0 && (v56 & 0xFFF0FFFF) != 0 )
    {
      v27 = v40;
      v13 = -2146893007;
    }
    else
    {
      if ( a4 || (a2 & 0x40051555) == 0 )
      {
        if ( v21 )
        {
          CleanupAppModeInfo(!v20, &v45);
          v27 = 0;
        }
        else
        {
          v27 = v40;
        }
        v32 = CSslCredManager::m_pCredManager;
        v33 = TargetHandle;
        CSslCredManager::DbgDumpSchannelCred(v17, (struct LSA_SCHANNEL_CRED *)v55);
        v34 = (CCredentialGroup *)SPExternalAlloc(0x3D0u);
        if ( v34 && (v35 = CCredentialGroup::CCredentialGroup(v34)) != 0 )
        {
          DefaultMachineCred = CCredentialGroup::InitializeCredentialGroup(
                                 v35,
                                 a2,
                                 &v47,
                                 v33,
                                 (struct LSA_SCHANNEL_CRED *)v55,
                                 v57);
          if ( DefaultMachineCred )
          {
            (*(void (__fastcall **)(CCredentialGroup *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 1);
          }
          else
          {
            RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)v32 + 8));
            v36 = (CSslCredManager **)*((_QWORD *)v32 + 7);
            if ( *v36 != (CSslCredManager *)((char *)v32 + 48) )
              __fastfail(3u);
            *((_QWORD *)v35 + 9) = (char *)v32 + 48;
            *((_QWORD *)v35 + 10) = v36;
            *v36 = (CCredentialGroup *)((char *)v35 + 72);
            *((_QWORD *)v32 + 7) = (char *)v35 + 72;
            RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)v32 + 8));
            _InterlockedIncrement((volatile signed __int32 *)v35 + 22);
            v46 = v35;
          }
        }
        else
        {
          DefaultMachineCred = 14;
        }
        FreeSchannelCred((struct LSA_SCHANNEL_CRED *)v55, 0);
      }
      else
      {
        if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids);
        v27 = v40;
        DefaultMachineCred = FindDefaultMachineCred(&v46, a2, &v47, TargetHandle, dwProcessId[0], v57);
      }
      v13 = TranslateToSecurityStatus(DefaultMachineCred);
      if ( !v13 )
      {
        CCredentialGroup::GetCredentialExpirationTime(v46, v50);
        v37 = v46;
        v46 = 0;
        TargetHandle = 0;
        *v49 = (unsigned __int64)v37;
      }
    }
    v23 = v41;
LABEL_115:
    if ( !v27 )
      goto LABEL_120;
    goto LABEL_116;
  }
  if ( a4->dwVersion == 4 )
  {
    v22 = MapKernelAuthDataV4(a4, v48, TargetHandle, (struct LSA_SCHANNEL_CRED *)v55);
    goto LABEL_43;
  }
  if ( a4->dwVersion == 5 )
  {
    v22 = MapKernelAuthDataV5(a4, v48, TargetHandle, (struct LSA_SCHANNEL_CRED *)v55);
LABEL_43:
    if ( v22 )
      goto LABEL_119;
    v20 = 0;
    goto LABEL_91;
  }
  v22 = 87;
LABEL_119:
  v13 = TranslateToSecurityStatus(v22);
LABEL_120:
  if ( TargetHandle )
  {
    NtClose(TargetHandle);
    if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids, TargetHandle);
  }
  if ( v46 )
    CSslCredManager::DereferenceCredentialGroup(CSslCredManager::m_pCredManager, v46);
  if ( v13 )
  {
    FreeSchannelCred((struct LSA_SCHANNEL_CRED *)v55, 1u);
    if ( v49 )
      *v49 = 0;
    if ( v50 )
      v50->QuadPart = 0;
    if ( v13 == 590610 )
      v13 = -2146893055;
  }
  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
    && ((*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && v13 || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0) )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids, v13, v13);
  }
  return v13;
}

```

## disassembly

```asm
0x18002b800  push    rbp
0x18002b802  push    rbx
0x18002b803  push    rsi
0x18002b804  push    rdi
0x18002b805  push    r12
0x18002b807  push    r13
0x18002b809  push    r14
0x18002b80b  push    r15
0x18002b80d  lea     rbp, [rsp-268h]
0x18002b815  sub     rsp, 368h
0x18002b81c  mov     rax, cs:__security_cookie
0x18002b823  xor     rax, rsp
0x18002b826  mov     [rbp+2A0h+var_50], rax
0x18002b82d  mov     rax, [rbp+2A0h+arg_20]
0x18002b834  xor     esi, esi
0x18002b836  mov     [rbp+2A0h+var_320], rax
0x18002b83a  mov     rbx, r8
0x18002b83d  mov     rax, [rbp+2A0h+arg_28]
0x18002b844  mov     r13d, edx
0x18002b847  mov     [rsp+3A0h+var_328], rcx
0x18002b84c  xor     edx, edx; Val
0x18002b84e  lea     r8d, [rsi+70h]; Size
0x18002b852  mov     [rbp+2A0h+var_318], rax
0x18002b856  lea     rcx, [rbp+2A0h+var_2D0]; void *
0x18002b85a  mov     [rsp+3A0h+var_338], rsi
0x18002b85f  mov     rdi, r9
0x18002b862  call    memset_0
0x18002b867  xorps   xmm0, xmm0
0x18002b86a  mov     [rsp+3A0h+var_34C], esi
0x18002b86e  xorps   xmm1, xmm1
0x18002b871  mov     qword ptr [rsp+3A0h+var_330.LowPart], rsi
0x18002b876  xor     eax, eax
0x18002b878  mov     [rsp+3A0h+TargetHandle], rsi
0x18002b87d  xor     ecx, ecx; int
0x18002b87f  mov     [rbp+2A0h+var_300], rax
0x18002b883  movups  [rbp+2A0h+var_2F8], xmm0
0x18002b887  mov     [rsp+3A0h+var_350], esi
0x18002b88b  movups  xmmword ptr [rbp+2A0h+SourceHandle], xmm0
0x18002b88f  movups  xmmword ptr [rbp+2A0h+dwProcessId], xmm1
0x18002b893  movups  xmmword ptr [rsp+3A0h+var_348.cbBuffer], xmm0
0x18002b898  call    ?SchannelInit@@YAHH@Z; SchannelInit(int)
0x18002b89d  test    eax, eax
0x18002b89f  jz      loc_18002C094
0x18002b8a5  mov     rax, cs:LsaTable
0x18002b8ac  test    rax, rax
0x18002b8af  jz      loc_18002C094
0x18002b8b5  mov     rax, [rax+0C0h]
0x18002b8bc  lea     rcx, [rbp+2A0h+dwProcessId]
0x18002b8c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b8c5  test    al, al
0x18002b8c7  jz      loc_18002C094
0x18002b8cd  xor     edx, edx; Val
0x18002b8cf  mov     dword ptr [rbp+2A0h+var_260], esi
0x18002b8d2  mov     r8d, 204h; Size
0x18002b8d8  lea     rcx, [rbp+2A0h+var_25C]; void *
0x18002b8dc  call    memset_0
0x18002b8e1  test    [rbp+2A0h+dwProcessId+8], 2000h
0x18002b8e8  lea     r14, WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids
0x18002b8ef  lea     rcx, [rbp+2A0h+var_260]; unsigned __int16 *
0x18002b8f3  jz      loc_18002B9A4
0x18002b8f9  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002b8fd  lea     r8, aSystem; "SYSTEM"
0x18002b904  mov     edx, 104h
0x18002b909  call    _o_wcsncpy_s_0
0x18002b90e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b915  lea     r15, WPP_GLOBAL_Control
0x18002b91c  cmp     rcx, r15
0x18002b91f  jz      short loc_18002B963
0x18002b921  test    byte ptr [rcx+1Ch], 4
0x18002b925  jz      short loc_18002B943
0x18002b927  mov     r9d, [rbp+2A0h+dwProcessId]
0x18002b92b  mov     edx, 33h ; '3'
0x18002b930  mov     rcx, [rcx+10h]
0x18002b934  mov     r8, r14
0x18002b937  call    WPP_SF_d
0x18002b93c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b943  cmp     rcx, r15
0x18002b946  jz      short loc_18002B963
0x18002b948  test    byte ptr [rcx+1Ch], 4
0x18002b94c  jz      short loc_18002B963
0x18002b94e  mov     rcx, [rcx+10h]
0x18002b952  lea     r9, [rbp+2A0h+var_260]
0x18002b956  mov     edx, 34h ; '4'
0x18002b95b  mov     r8, r14
0x18002b95e  call    WPP_SF_S
0x18002b963  mov     r14, qword ptr [rbp+2A0h+dwProcessId+8]
0x18002b967  lea     rcx, [rbp+2A0h+var_2F8]
0x18002b96b  mov     rax, cs:LsaTable
0x18002b972  mov     r12d, r14d
0x18002b975  mov     esi, r14d
0x18002b978  and     r12d, 40h
0x18002b97c  setnz   [rsp+3A0h+var_35E]
0x18002b981  and     esi, 1
0x18002b984  mov     rax, [rax+80h]
0x18002b98b  and     r14d, 11h
0x18002b98f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b994  xor     ecx, ecx
0x18002b996  test    eax, eax
0x18002b998  jns     short loc_18002B9ED
0x18002b99a  mov     ebx, 80090304h
0x18002b99f  jmp     loc_18002BFC6
0x18002b9a4  mov     edx, [rbp+2A0h+dwProcessId]; dwProcessId
0x18002b9a7  call    ?GetProcessImageName@@YAKPEAGK@Z; GetProcessImageName(ushort *,ulong)
0x18002b9ac  mov     r9d, eax
0x18002b9af  test    eax, eax
0x18002b9b1  jns     loc_18002B90E
0x18002b9b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b9be  lea     r15, WPP_GLOBAL_Control
0x18002b9c5  cmp     rcx, r15
0x18002b9c8  jz      short loc_18002B963
0x18002b9ca  test    byte ptr [rcx+1Ch], 1
0x18002b9ce  jz      short loc_18002B963
0x18002b9d0  mov     eax, [rbp+2A0h+dwProcessId]
0x18002b9d3  mov     edx, 32h ; '2'
0x18002b9d8  mov     rcx, [rcx+10h]
0x18002b9dc  mov     r8, r14
0x18002b9df  mov     [rsp+3A0h+DesiredAccess], eax
0x18002b9e3  call    WPP_SF_dd
0x18002b9e8  jmp     loc_18002B963
0x18002b9ed  test    rbx, rbx
0x18002b9f0  jz      short loc_18002BA51
0x18002b9f2  cmp     [rbx], ecx
0x18002b9f4  jnz     short loc_18002B9FB
0x18002b9f6  cmp     [rbx+4], ecx
0x18002b9f9  jz      short loc_18002BA51
0x18002b9fb  cmp     byte ptr [rbp+2A0h+SourceHandle], cl
0x18002b9fe  jnz     short loc_18002BA0A
0x18002ba00  mov     ecx, 0C0000061h
0x18002ba05  jmp     loc_18002BFB7
0x18002ba0a  mov     rax, [rbx]
0x18002ba0d  lea     rdx, [rsp+3A0h+TargetHandle]
0x18002ba12  mov     qword ptr [rsp+3A0h+var_330.LowPart], rax
0x18002ba17  mov     rcx, rbx
0x18002ba1a  mov     rax, cs:LsaTable
0x18002ba21  mov     rax, [rax+170h]
0x18002ba28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba2d  test    eax, eax
0x18002ba2f  jns     short loc_18002BA38
0x18002ba31  mov     ecx, eax
0x18002ba33  jmp     loc_18002BFB7
0x18002ba38  mov     rax, cs:WPP_GLOBAL_Control
0x18002ba3f  cmp     rax, r15
0x18002ba42  jz      short loc_18002BABE
0x18002ba44  test    byte ptr [rax+1Ch], 4
0x18002ba48  jz      short loc_18002BABE
0x18002ba4a  mov     edx, 35h ; '5'
0x18002ba4f  jmp     short loc_18002BAA9
0x18002ba51  mov     rdx, [rbp+2A0h+SourceHandle+8]; SourceHandle
0x18002ba55  lea     rax, [rdx-1]
0x18002ba59  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002ba5d  ja      loc_18002BFB2
0x18002ba63  mov     rax, qword ptr [rbp+2A0h+var_2F8]
0x18002ba67  lea     r9, [rsp+3A0h+TargetHandle]; TargetHandle
0x18002ba6c  mov     [rsp+3A0h+Options], 2; Options
0x18002ba74  mov     [rsp+3A0h+HandleAttributes], ecx; HandleAttributes
0x18002ba78  mov     [rsp+3A0h+DesiredAccess], ecx; DesiredAccess
0x18002ba7c  or      rcx, 0FFFFFFFFFFFFFFFFh; SourceProcessHandle
0x18002ba80  mov     r8, rcx; TargetProcessHandle
0x18002ba83  mov     qword ptr [rsp+3A0h+var_330.LowPart], rax
0x18002ba88  call    cs:__imp_NtDuplicateObject
0x18002ba8e  test    eax, eax
0x18002ba90  js      short loc_18002BA31
0x18002ba92  mov     rax, cs:WPP_GLOBAL_Control
0x18002ba99  cmp     rax, r15
0x18002ba9c  jz      short loc_18002BABE
0x18002ba9e  test    byte ptr [rax+1Ch], 4
0x18002baa2  jz      short loc_18002BABE
0x18002baa4  mov     edx, 36h ; '6'
0x18002baa9  mov     r9, [rsp+3A0h+TargetHandle]
0x18002baae  lea     r8, WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids
0x18002bab5  mov     rcx, [rax+10h]
0x18002bab9  call    WPP_SF_q
0x18002babe  cmp     dword ptr [rbp+2A0h+SourceHandle+4], 1
0x18002bac2  jg      short loc_18002BACE
0x18002bac4  mov     ebx, 8009030Eh
0x18002bac9  jmp     loc_18002BFC6
0x18002bace  xor     al, al
0x18002bad0  mov     [rbp+2A0h+var_2D0], 4
0x18002bad7  xor     bl, bl
0x18002bad9  mov     [rsp+3A0h+var_35F], al
0x18002badd  mov     [rsp+3A0h+var_360], bl
0x18002bae1  test    rdi, rdi
0x18002bae4  jz      loc_18002BDE3
0x18002baea  test    sil, sil
0x18002baed  jz      short loc_18002BB3D
0x18002baef  mov     ecx, [rdi]
0x18002baf1  mov     r8, [rsp+3A0h+TargetHandle]; void *
0x18002baf6  sub     ecx, 4
0x18002baf9  jz      short loc_18002BB1D
0x18002bafb  cmp     ecx, 1
0x18002bafe  jz      short loc_18002BB0A
0x18002bb00  mov     eax, 57h ; 'W'
0x18002bb05  jmp     loc_18002BFBD
0x18002bb0a  mov     rdx, [rsp+3A0h+var_328]; struct _UNICODE_STRING *
0x18002bb0f  lea     r9, [rbp+2A0h+var_2D0]; struct LSA_SCHANNEL_CRED *
0x18002bb13  mov     rcx, rdi; struct _SCHANNEL_CRED *
0x18002bb16  call    ?MapKernelAuthDataV5@@YAKPEAU_SCHANNEL_CRED@@PEAU_UNICODE_STRING@@PEAXPEAULSA_SCHANNEL_CRED@@@Z; MapKernelAuthDataV5(_SCHANNEL_CRED *,_UNICODE_STRING *,void *,LSA_SCHANNEL_CRED *)
0x18002bb1b  jmp     short loc_18002BB2E
0x18002bb1d  mov     rdx, [rsp+3A0h+var_328]; struct _UNICODE_STRING *
0x18002bb22  lea     r9, [rbp+2A0h+var_2D0]; struct LSA_SCHANNEL_CRED *
0x18002bb26  mov     rcx, rdi; struct _SCHANNEL_CRED *
0x18002bb29  call    ?MapKernelAuthDataV4@@YAKPEAU_SCHANNEL_CRED@@PEAU_UNICODE_STRING@@PEAXPEAULSA_SCHANNEL_CRED@@@Z; MapKernelAuthDataV4(_SCHANNEL_CRED *,_UNICODE_STRING *,void *,LSA_SCHANNEL_CRED *)
0x18002bb2e  test    eax, eax
0x18002bb30  jnz     loc_18002BFBD
0x18002bb36  mov     al, bl
0x18002bb38  jmp     loc_18002BDE3
0x18002bb3d  mov     rax, cs:LsaTable
0x18002bb44  lea     r8, [rsp+3A0h+var_34C]
0x18002bb49  mov     r9, rdi
0x18002bb4c  mov     edx, 4
0x18002bb51  xor     ecx, ecx
0x18002bb53  mov     rax, [rax+50h]
0x18002bb57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb5c  test    eax, eax
0x18002bb5e  js      loc_18002BFBD
0x18002bb64  test    r14d, r14d
0x18002bb67  jnz     short loc_18002BBD0
0x18002bb69  mov     rax, cs:LsaTable
0x18002bb70  lea     r9, [rsp+3A0h+var_348]
0x18002bb75  xor     r8d, r8d
0x18002bb78  mov     qword ptr [rsp+3A0h+DesiredAccess], 0
0x18002bb81  xor     edx, edx
0x18002bb83  lea     rcx, [rsp+3A0h+var_350]
0x18002bb88  mov     rax, [rax+1E8h]
0x18002bb8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb94  test    eax, eax
0x18002bb96  js      loc_18002B99A
0x18002bb9c  mov     rax, [rsp+3A0h+var_348.pvBuffer]
0x18002bba1  mov     bl, 1
0x18002bba3  test    rax, rax
0x18002bba6  mov     [rsp+3A0h+var_360], bl
0x18002bbaa  setnz   sil
0x18002bbae  mov     [rsp+3A0h+var_35F], sil
0x18002bbb3  cmp     [rsp+3A0h+var_350], r14d
0x18002bbb8  jz      short loc_18002BBD3
0x18002bbba  test    rax, rax
0x18002bbbd  jz      short loc_18002BBC6
0x18002bbbf  cmp     [rsp+3A0h+var_348.cbBuffer], r14d
0x18002bbc4  jnz     short loc_18002BBD3
0x18002bbc6  mov     ebx, 8009030Dh
0x18002bbcb  jmp     loc_18002BF9E
0x18002bbd0  mov     sil, bl
0x18002bbd3  mov     ecx, [rsp+3A0h+var_34C]
0x18002bbd7  mov     eax, ecx
0x18002bbd9  sub     eax, 3
0x18002bbdc  jz      loc_18002BCC3
0x18002bbe2  sub     eax, 1
0x18002bbe5  jz      loc_18002BCC3
0x18002bbeb  sub     eax, 1
0x18002bbee  jz      loc_18002BCC3
0x18002bbf4  cmp     eax, 1FBh
0x18002bbf9  jz      short loc_18002BC2F
0x18002bbfb  mov     rax, cs:WPP_GLOBAL_Control
0x18002bc02  cmp     rax, r15
0x18002bc05  jz      short loc_18002BC25
0x18002bc07  test    byte ptr [rax+1Ch], 1
0x18002bc0b  jz      short loc_18002BC25
0x18002bc0d  mov     r9d, ecx
0x18002bc10  lea     r8, WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids
0x18002bc17  mov     rcx, [rax+10h]
0x18002bc1b  mov     edx, 39h ; '9'
0x18002bc20  call    WPP_SF_d
0x18002bc25  mov     ebx, 8009030Dh
0x18002bc2a  jmp     loc_18002BCB9
0x18002bc2f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bc36  cmp     rcx, r15
0x18002bc39  jz      short loc_18002BC5C
0x18002bc3b  test    byte ptr [rcx+1Ch], 4
0x18002bc3f  jz      short loc_18002BC5C
0x18002bc41  mov     rcx, [rcx+10h]
0x18002bc45  lea     r8, WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids
0x18002bc4c  mov     edx, 37h ; '7'
0x18002bc51  mov     r9d, 200h
0x18002bc57  call    WPP_SF_d
0x18002bc5c  test    r13d, 800A2AAAh
0x18002bc63  jz      short loc_18002BC6F
0x18002bc65  test    r14d, r14d
0x18002bc68  jnz     short loc_18002BC6F
0x18002bc6a  mov     r8b, 1
0x18002bc6d  jmp     short loc_18002BC72
0x18002bc6f  xor     r8d, r8d; unsigned __int8
0x18002bc72  mov     rax, [rsp+3A0h+TargetHandle]
0x18002bc77  lea     rdx, [rsp+3A0h+var_348]; struct _SecBuffer *
0x18002bc7c  mov     r9b, [rsp+3A0h+var_35E]; unsigned __int8
0x18002bc81  mov     rcx, rdi; void *
0x18002bc84  mov     qword ptr [rsp+3A0h+HandleAttributes], rax; void *
0x18002bc89  lea     rax, [rbp+2A0h+var_2D0]
0x18002bc8d  mov     qword ptr [rsp+3A0h+DesiredAccess], rax; struct LSA_SCHANNEL_CRED *
0x18002bc92  call    ?SpMapAuthIdentity@@YAKPEAXPEAU_SecBuffer@@EEPEAULSA_SCHANNEL_CRED@@0@Z; SpMapAuthIdentity(void *,_SecBuffer *,uchar,uchar,LSA_SCHANNEL_CRED *,void *)
0x18002bc97  cmp     eax, 90312h
0x18002bc9c  jnz     short loc_18002BCA8
0x18002bc9e  mov     ebx, 90312h
0x18002bca3  jmp     loc_18002BFC6
0x18002bca8  test    eax, eax
0x18002bcaa  jz      loc_18002BDDF
0x18002bcb0  mov     ecx, eax; unsigned int
0x18002bcb2  call    ?TranslateToSecurityStatus@@YAJK@Z; TranslateToSecurityStatus(ulong)
0x18002bcb7  mov     ebx, eax
0x18002bcb9  mov     r12b, [rsp+3A0h+var_360]
0x18002bcbe  jmp     loc_18002BF99
  ... truncated ...
```
