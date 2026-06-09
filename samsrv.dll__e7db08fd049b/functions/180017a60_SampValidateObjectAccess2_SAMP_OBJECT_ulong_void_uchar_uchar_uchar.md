# SampValidateObjectAccess2(_SAMP_OBJECT *,ulong,void *,uchar,uchar,uchar)

- ea: `0x180017a60`
- end: `0x1800184ad`
- name: `?SampValidateObjectAccess2@@YAJPEAU_SAMP_OBJECT@@KPEAXEEE@Z`
- size: `2637`
- prototype: `__int64 __fastcall(struct _SAMP_OBJECT *, DWORD, void *, __int64, unsigned __int8, unsigned __int8)`
- caller_count: `7`
- callee_count: `17`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180007bd0`
- `0x1800096c0`
- `0x180012d60`
- `0x180015c50`
- `0x180015e90`
- `0x1800a3440`
- `0x1800a3d10`

## callees

- `0x180012a28`
- `0x180017a60`
- `0x180018620`
- `0x180019100`
- `0x180027e24`
- `0x18002cd80`
- `0x1800372ac`
- `0x18003c010`
- `0x18003c920`
- `0x180076cbc`
- `0x180076ff0`
- `0x180077790`
- `0x18008acf0`
- `0x18008db68`
- `0x18008ec80`
- `0x18008ecd0`
- `0x1800bb788`

## import_xrefs

- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180018385`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180018385`
- `ntdll!RtlMapGenericMask` at `0x180017ae4`
- `ntdll!RtlMapGenericMask` at `0x180017ae4`
- `ntdll!NtClose` at `0x180018449`
- `ntdll!NtClose` at `0x180018449`
- `ntdll!NtAccessCheckAndAuditAlarm` at `0x180017e06`
- `ntdll!NtAccessCheckAndAuditAlarm` at `0x180017e06`
- `ntdll!NtAccessCheck` at `0x18001831d`
- `ntdll!NtAccessCheck` at `0x18001831d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180017c11`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180017c11`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017bb6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017bb6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800180a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800181e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001843e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800180a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800181e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001843e`
- `RPCRT4!I_RpcMapWin32Status` at `0x180017d70`
- `RPCRT4!I_RpcMapWin32Status` at `0x18001838d`
- `RPCRT4!I_RpcMapWin32Status` at `0x180017d70`
- `RPCRT4!I_RpcMapWin32Status` at `0x18001838d`
- `RPCRT4!RpcRevertToSelf` at `0x180017e20`
- `RPCRT4!RpcRevertToSelf` at `0x180017e20`
- `RPCRT4!RpcImpersonateClient` at `0x180017d68`
- `RPCRT4!RpcImpersonateClient` at `0x180017d68`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtImpersonateAnyClient` at `0x180018373`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtImpersonateAnyClient` at `0x180018373`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtUnImpersonateAnyClient` at `0x180018429`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtUnImpersonateAnyClient` at `0x180018429`

## pseudocode

```c
__int64 __fastcall SampValidateObjectAccess2(
        struct _SAMP_OBJECT *a1,
        DWORD a2,
        void *a3,
        __int64 a4,
        unsigned __int8 a5,
        unsigned __int8 a6)
{
  __int64 v6; // rsi
  char v7; // di
  __int64 v8; // r14
  struct _UNICODE_STRING *v10; // r12
  DWORD v11; // r15d
  struct _SAMP_OBJECT_INFORMATION near **GenericMapping; // r13
  int v13; // ecx
  ULONG v14; // r14d
  bool v15; // zf
  NTSTATUS v16; // eax
  unsigned int *v17; // r8
  NTSTATUS v18; // edi
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // rdx
  __int64 v22; // r12
  unsigned int v23; // r14d
  const void *v24; // r12
  SIZE_T v25; // rdi
  HLOCAL v26; // rax
  bool v28; // di
  RPC_STATUS v29; // eax
  int v30; // eax
  int v31; // esi
  ACCESS_MASK DesiredAccess; // ecx
  char v33; // r15
  _DWORD *v34; // r14
  NTSTATUS v35; // eax
  int v36; // ecx
  __int64 v37; // rsi
  __int64 v38; // r11
  unsigned int v39; // edx
  PUNICODE_STRING v40; // rcx
  __int64 v41; // rcx
  DWORD v42; // eax
  __int64 v43; // rdx
  unsigned int CachedObjectSDDs; // eax
  void *v45; // rcx
  __int64 v46; // rax
  int v47; // eax
  ULONG v48; // eax
  NTSTATUS v49; // ecx
  int v50; // esi
  ULONG ReturnLength; // [rsp+60h] [rbp-A0h] BYREF
  DWORD AccessMask; // [rsp+64h] [rbp-9Ch] BYREF
  int AccessStatus; // [rsp+68h] [rbp-98h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+70h] [rbp-90h] BYREF
  unsigned int SecurityDescriptorLength; // [rsp+78h] [rbp-88h] BYREF
  PUNICODE_STRING ObjectName; // [rsp+80h] [rbp-80h]
  HANDLE ClientToken; // [rsp+88h] [rbp-78h] BYREF
  HANDLE TokenHandle; // [rsp+90h] [rbp-70h]
  _PRIVILEGE_SET PrivilegeSet; // [rsp+A0h] [rbp-60h] BYREF

  v6 = *((int *)a1 + 4);
  v7 = *((_BYTE *)a1 + 20);
  v8 = *((unsigned int *)a1 + 50);
  v10 = 0;
  AccessMask = a2;
  v11 = a2;
  TokenHandle = a3;
  GenericMapping = &SampObjectInformation + 11 * v6;
  AccessStatus = 0;
  SecurityDescriptorLength = 0;
  pSecurityDescriptor = 0;
  ClientToken = (HANDLE)-1LL;
  RtlMapGenericMask(&AccessMask, (PGENERIC_MAPPING)GenericMapping);
  if ( (_DWORD)v6 )
  {
    switch ( (_DWORD)v6 )
    {
      case 1:
        v41 = 1360 * v8;
        v14 = 257;
        v10 = (struct _UNICODE_STRING *)((char *)SampDefinedDomains + v41 + 16);
        v13 = 985087;
        break;
      case 2:
        v10 = (struct _UNICODE_STRING *)((char *)a1 + 160);
        v13 = 983071;
        v14 = 16;
        break;
      case 3:
        v10 = (struct _UNICODE_STRING *)((char *)a1 + 160);
        v13 = 983071;
        v14 = 4;
        break;
      case 4:
        v10 = (struct _UNICODE_STRING *)((char *)a1 + 160);
        v13 = 985087;
        v14 = 256;
        break;
      default:
        v14 = 0;
        v13 = 0;
        break;
    }
  }
  else
  {
    v10 = &SampServerObjectName;
    v13 = 983103;
    v14 = 0;
  }
  ReturnLength = v14;
  ObjectName = v10;
  if ( (v7 & 0x20) != 0 )
  {
    v42 = AccessMask;
    *((_BYTE *)a1 + 208) = 0;
    if ( v7 < 0 )
      v42 = v13;
    *((_DWORD *)a1 + 37) = v42;
    v40 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
      return 0;
    v43 = 19;
    goto LABEL_85;
  }
  if ( v7 < 0 && !a5 && !a6 )
  {
    *((_DWORD *)a1 + 37) = v13;
    *((_BYTE *)a1 + 208) = 0;
    v40 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
      return 0;
    v43 = 20;
LABEL_85:
    WPP_SF_Dd(v40[3].Buffer, v43, WPP_5505de3e48bd33375e96ca021b170945_Traceguids, 0, 0);
    return 0;
  }
  v15 = (*((_BYTE *)a1 + 192) & 2) == 0;
  SecurityDescriptorLength = 0;
  if ( v15 )
    goto LABEL_6;
  if ( *((_DWORD *)a1 + 4) > 1u
    || (CachedObjectSDDs = SampExtGetCachedObjectSDDs(a1, &SecurityDescriptorLength, &pSecurityDescriptor),
        v18 = CachedObjectSDDs,
        CachedObjectSDDs == -1073741823) )
  {
    if ( (*((_BYTE *)a1 + 192) & 2) != 0 )
    {
      if ( *((_QWORD *)a1 + 14) )
      {
        if ( _bittest64(*((const signed __int64 **)a1 + 8), 0) )
        {
          v45 = (void *)*((_QWORD *)a1 + 17);
          if ( v45 )
            LocalFree(v45);
          v46 = *((_QWORD *)a1 + 14);
          *((_BYTE *)a1 + 20) &= 0xF0u;
          *((_QWORD *)a1 + 17) = v46;
          *((_QWORD *)a1 + 14) = 0;
          *((_QWORD *)a1 + 15) = 0;
          *((_DWORD *)a1 + 32) = 0;
          v18 = SampValidateDsAttributes(a1, 0);
          if ( v18 >= 0 )
          {
            v18 = SampValidateDsAttributes(a1, 1u);
            if ( v18 >= 0 )
            {
              SampMarkPerAttributeInvalidFromWhichFields(a1, 0);
              *((_BYTE *)a1 + 29) &= ~1u;
            }
          }
          goto LABEL_8;
        }
      }
      else
      {
        v18 = SampValidateDsAttributes(a1, 0);
        if ( v18 < 0 )
          goto LABEL_8;
      }
      v16 = SampValidateDsAttributes(a1, 1u);
LABEL_7:
      v18 = v16;
LABEL_8:
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
        WPP_SF_Dd(
          WPP_GLOBAL_Control[3].Buffer,
          110,
          WPP_ec9974b3367635591c8fff3dd01cd200_Traceguids,
          (unsigned int)v18,
          v18);
      if ( v18 < 0 )
      {
        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
          WPP_SF_Dd(
            WPP_GLOBAL_Control[3].Buffer,
            42,
            WPP_ec9974b3367635591c8fff3dd01cd200_Traceguids,
            (unsigned int)v18,
            v18);
      }
      else
      {
        v19 = *((_QWORD *)a1 + 14);
        v20 = 22LL * *((int *)a1 + 4);
        if ( (*((_BYTE *)a1 + 192) & 2) != 0 )
        {
          v21 = (unsigned int)dword_1800EEC4C[v20];
          v22 = (unsigned int)(dword_1800EEC48[v20] + *(_DWORD *)(v21 + v19));
        }
        else
        {
          v21 = (unsigned int)dword_1800EEC34[v20];
          v22 = (unsigned int)(dword_1800EEC38[v20] + *(_DWORD *)(v21 + v19));
        }
        v23 = *(_DWORD *)(v21 + v19 + 8);
        v24 = (const void *)(v19 + v22);
        v25 = *(unsigned int *)(v19 + v21 + 4);
        v26 = LocalAlloc(0x40u, v25);
        pSecurityDescriptor = v26;
        if ( v26 )
        {
          memcpy_0(v26, v24, (unsigned int)v25);
          if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
            WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 45, WPP_ec9974b3367635591c8fff3dd01cd200_Traceguids, 0, 0);
          if ( (v23 & 0xFFFF0000) > 0x10000 || v23 > 0x10009 )
          {
            v18 = -1073741736;
            LocalFree(pSecurityDescriptor);
            pSecurityDescriptor = 0;
          }
          else
          {
            SecurityDescriptorLength = GetSecurityDescriptorLength(pSecurityDescriptor);
            v18 = 0;
          }
        }
        else
        {
          v18 = -1073741801;
          if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
            WPP_SF_Dd(
              WPP_GLOBAL_Control[3].Buffer,
              44,
              WPP_ec9974b3367635591c8fff3dd01cd200_Traceguids,
              3221225495LL,
              -1073741801);
        }
        v14 = ReturnLength;
        v10 = ObjectName;
      }
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
        WPP_SF_Dd(
          WPP_GLOBAL_Control[3].Buffer,
          37,
          WPP_18fb10c206133c98d7a2b000be93359d_Traceguids,
          (unsigned int)v18,
          v18);
      goto LABEL_22;
    }
LABEL_6:
    v16 = SampValidateRegAttributes(a1, 1u);
    goto LABEL_7;
  }
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control[3].Buffer,
      36,
      WPP_18fb10c206133c98d7a2b000be93359d_Traceguids,
      CachedObjectSDDs,
      CachedObjectSDDs);
LABEL_22:
  if ( v18 >= 0 )
  {
    if ( a5 )
    {
      v18 = SampGrantChangePasswordIfForcePasswordEnabled(a1, &pSecurityDescriptor, v17);
      if ( v18 < 0 )
        goto LABEL_30;
      v18 = SampCreateUserToken(a1, TokenHandle, &ClientToken);
      if ( v18 < 0 )
        goto LABEL_30;
    }
    else if ( (_DWORD)v6 == 4 )
    {
      v11 &= ~0x40u;
      AccessMask &= ~0x40u;
    }
    if ( (*((_BYTE *)a1 + 28) & 0x40) == 0 || v11 )
    {
      if ( (*((_BYTE *)a1 + 192) & 2) != 0 )
      {
        v18 = SampExtDoNt5SdBasedAccessCheckDs(
                a1,
                pSecurityDescriptor,
                GenericMapping + 3,
                (unsigned int)v6,
                GenericMapping + 3,
                v11);
      }
      else if ( !SampRestrictNullSessions
             || (v18 = SampRemoveAnonymousAccess(&pSecurityDescriptor, &SecurityDescriptorLength, v14, (unsigned int)v6),
                 v18 >= 0) )
      {
        if ( ClientToken == (HANDLE)-1LL )
        {
          v28 = SampUseDsData && !SampDsStopped;
          if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
            WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 74, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, v28);
          if ( v28 && (unsigned int)SampExtThreadStateQueryDs() )
          {
            v47 = SampShouldCallNtdsaApiSet();
            if ( v47 < 0 )
            {
              v49 = 0;
              if ( v47 != -1073741637 )
                v49 = v47;
              v48 = RtlNtStatusToDosErrorNoTeb(v49);
            }
            else
            {
              v48 = NtdsaExtImpersonateAnyClient();
            }
            v30 = I_RpcMapWin32Status(v48);
            v31 = 3;
          }
          else
          {
            v29 = RpcImpersonateClient(0);
            v30 = I_RpcMapWin32Status(v29);
            v31 = 2;
          }
          v18 = v30;
          if ( v30 == -1073610687 )
          {
            v18 = SamIImpersonateNullSession();
            v31 = 1;
          }
          if ( v18 < 0 )
            v31 = 0;
          if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
            WPP_SF_Dd(
              WPP_GLOBAL_Control[3].Buffer,
              66,
              WPP_5505de3e48bd33375e96ca021b170945_Traceguids,
              (unsigned int)v18,
              v18);
          if ( v18 < 0 )
            goto LABEL_30;
          DesiredAccess = AccessMask;
          v33 = 0;
          if ( !AccessMask )
          {
            DesiredAccess = 0x2000000;
            v33 = 1;
            AccessMask = 0x2000000;
          }
          v34 = (_DWORD *)((char *)a1 + 148);
          v35 = NtAccessCheckAndAuditAlarm(
                  &SampSamSubsystem,
                  a1,
                  (PUNICODE_STRING)(GenericMapping + 3),
                  v10,
                  pSecurityDescriptor,
                  DesiredAccess,
                  (PGENERIC_MAPPING)GenericMapping,
                  0,
                  (PACCESS_MASK)a1 + 37,
                  &AccessStatus,
                  (PBOOLEAN)a1 + 208);
          v18 = v35;
          if ( v33 )
          {
            AccessMask = 0;
            if ( v35 >= 0 && AccessStatus >= 0 )
              *v34 = 0;
          }
          if ( v31 == 2 )
          {
            RpcRevertToSelf();
          }
          else
          {
            v50 = v31 - 1;
            if ( v50 )
            {
              if ( v50 == 2 && (int)SampShouldCallNtdsaApiSet() >= 0 )
                NtdsaExtUnImpersonateAnyClient();
            }
            else
            {
              SamIRevertNullSession();
            }
          }
        }
        else
        {
          v34 = (_DWORD *)((char *)a1 + 148);
          ReturnLength = 256;
          v18 = NtAccessCheck(
                  pSecurityDescriptor,
                  ClientToken,
                  AccessMask,
                  (PGENERIC_MAPPING)(&SampObjectInformation + 11 * v6),
                  &PrivilegeSet,
                  &ReturnLength,
                  (PACCESS_MASK)a1 + 37,
                  &AccessStatus);
        }
        if ( v18 >= 0 )
        {
          v36 = *((_DWORD *)a1 + 4);
          if ( dword_1800BD008[4 * v36] )
          {
            v37 = *((_QWORD *)&SampObjectExtendedAttributesProperties + 2 * *((int *)a1 + 4));
            v38 = 0;
            do
            {
              v39 = dword_1800BD00C[4 * v36];
              if ( v39 + (unsigned int)v38 >= v39 && v39 + (unsigned int)v38 < v39 + dword_1800BD008[4 * v36] )
                *((_BYTE *)a1 + 24 * v38 + 864) = ((*v34 & *(_DWORD *)(32LL * (unsigned int)v38 + v37 + 28)) != 0 ? 8 : 0)
                                                | *((_BYTE *)a1 + 24 * v38 + 864) & 0xF3
                                                | ((*v34 & *(_DWORD *)(32LL * (unsigned int)v38 + v37 + 24)) != 0 ? 4 : 0);
              v36 = *((_DWORD *)a1 + 4);
              v38 = (unsigned int)(v38 + 1);
            }
            while ( (unsigned int)v38 < dword_1800BD008[4 * v36] );
          }
        }
      }
    }
    else
    {
      v18 = 0;
      *((_DWORD *)a1 + 37) = 0;
      AccessStatus = 0;
      *((_BYTE *)a1 + 208) = 0;
    }
  }
LABEL_30:
  if ( pSecurityDescriptor )
    LocalFree(pSecurityDescriptor);
  if ( ClientToken != (HANDLE)-1LL )
    NtClose(ClientToken);
  if ( v18 >= 0 )
  {
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      WPP_SF_Dd(
        WPP_GLOBAL_Control[3].Buffer,
        22,
        WPP_5505de3e48bd33375e96ca021b170945_Traceguids,
        (unsigned int)AccessStatus,
        AccessStatus);
    return (unsigned int)AccessStatus;
  }
  else
  {
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      WPP_SF_Dd(
        WPP_GLOBAL_Control[3].Buffer,
        21,
        WPP_5505de3e48bd33375e96ca021b170945_Traceguids,
        (unsigned int)v18,
        v18);
    return (unsigned int)v18;
  }
}

```

## disassembly

```asm
0x180017a60  mov     [rsp-8+arg_18], rbx
0x180017a65  push    rbp
0x180017a66  push    rsi
0x180017a67  push    rdi
0x180017a68  push    r12
0x180017a6a  push    r13
0x180017a6c  push    r14
0x180017a6e  push    r15
0x180017a70  lea     rbp, [rsp-0B0h]
0x180017a78  sub     rsp, 1B0h
0x180017a7f  mov     rax, cs:__security_cookie
0x180017a86  xor     rax, rsp
0x180017a89  mov     [rbp+0E0h+var_40], rax
0x180017a90  movsxd  rsi, dword ptr [rcx+10h]
0x180017a94  lea     rax, __ImageBase
0x180017a9b  movzx   edi, byte ptr [rcx+14h]
0x180017a9f  lea     r13, rva ?SampObjectInformation@@3PAU_SAMP_OBJECT_INFORMATION@@A[rax]; _SAMP_OBJECT_INFORMATION near * SampObjectInformation ...
0x180017aa6  mov     r14d, [rcx+0C8h]
0x180017aad  mov     rbx, rcx
0x180017ab0  xor     r12d, r12d
0x180017ab3  mov     [rsp+1E0h+AccessMask], edx
0x180017ab7  imul    rcx, rsi, 58h ; 'X'
0x180017abb  mov     r15d, edx
0x180017abe  mov     [rbp+0E0h+TokenHandle], r8
0x180017ac2  add     r13, rcx
0x180017ac5  mov     [rsp+1E0h+var_178], r12d
0x180017aca  mov     rdx, r13; GenericMapping
0x180017acd  mov     [rsp+1E0h+var_168], r12d
0x180017ad2  lea     rcx, [rsp+1E0h+AccessMask]; AccessMask
0x180017ad7  mov     [rsp+1E0h+pSecurityDescriptor], r12
0x180017adc  mov     [rbp+0E0h+ClientToken], 0FFFFFFFFFFFFFFFFh
0x180017ae4  call    cs:__imp_RtlMapGenericMask
0x180017aea  test    esi, esi
0x180017aec  jnz     loc_180017CFB
0x180017af2  lea     r12, ?SampServerObjectName@@3U_UNICODE_STRING@@A; _UNICODE_STRING SampServerObjectName
0x180017af9  mov     ecx, 0F003Fh
0x180017afe  xor     r14d, r14d
0x180017b01  mov     [rsp+1E0h+ReturnLength], r14d
0x180017b06  mov     [rbp+0E0h+ObjectName], r12
0x180017b0a  test    dil, 20h
0x180017b0e  jnz     loc_180017FA5
0x180017b14  test    dil, dil
0x180017b17  js      loc_180017F27
0x180017b1d  test    byte ptr [rbx+0C0h], 2
0x180017b24  mov     [rsp+1E0h+var_168], 0
0x180017b2c  jnz     loc_180018026
0x180017b32  mov     edx, 1; unsigned int
0x180017b37  mov     rcx, rbx; struct _SAMP_OBJECT *
0x180017b3a  call    SampValidateRegAttributes
0x180017b3f  mov     edi, eax
0x180017b41  mov     rcx, cs:WPP_GLOBAL_Control
0x180017b48  test    dword ptr [rcx+44h], 20000h
0x180017b4f  jnz     loc_180018137
0x180017b55  test    edi, edi
0x180017b57  js      loc_180018158
0x180017b5d  movsxd  rax, dword ptr [rbx+10h]
0x180017b61  lea     r9, __ImageBase
0x180017b68  mov     rcx, [rbx+70h]
0x180017b6c  imul    r8, rax, 58h ; 'X'
0x180017b70  test    byte ptr [rbx+0C0h], 2
0x180017b77  jnz     loc_18001818D
0x180017b7d  mov     eax, [r8+r9+0EEC34h]
0x180017b85  mov     edx, [r8+r9+0EEC34h]
0x180017b8d  mov     r12d, [rax+rcx]
0x180017b91  add     r12d, [r8+r9+0EEC38h]
0x180017b99  mov     eax, [r8+r9+0EEC34h]
0x180017ba1  mov     r14d, [rax+rcx+8]
0x180017ba6  add     rdx, rcx
0x180017ba9  add     r12, rcx
0x180017bac  mov     ecx, 40h ; '@'; uFlags
0x180017bb1  mov     edi, [rdx+4]
0x180017bb4  mov     edx, edi; uBytes
0x180017bb6  call    cs:__imp_LocalAlloc
0x180017bbc  mov     [rsp+1E0h+pSecurityDescriptor], rax
0x180017bc1  test    rax, rax
0x180017bc4  jz      loc_180017EEA
0x180017bca  mov     r8d, edi; Size
0x180017bcd  mov     rdx, r12; Src
0x180017bd0  mov     rcx, rax; void *
0x180017bd3  call    memcpy_0
0x180017bd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180017bdf  test    dword ptr [rcx+44h], 20000h
0x180017be6  jnz     loc_1800181B6
0x180017bec  mov     eax, r14d
0x180017bef  and     eax, 0FFFF0000h
0x180017bf4  cmp     eax, 10000h
0x180017bf9  ja      loc_1800181DB
0x180017bff  cmp     r14d, 10009h
0x180017c06  ja      loc_1800181DB
0x180017c0c  mov     rcx, [rsp+1E0h+pSecurityDescriptor]; pSecurityDescriptor
0x180017c11  call    cs:__imp_GetSecurityDescriptorLength
0x180017c17  mov     [rsp+1E0h+var_168], eax
0x180017c1b  xor     edi, edi
0x180017c1d  mov     r14d, [rsp+1E0h+ReturnLength]
0x180017c22  mov     r12, [rbp+0E0h+ObjectName]
0x180017c26  mov     rcx, cs:WPP_GLOBAL_Control
0x180017c2d  test    dword ptr [rcx+44h], 20000h
0x180017c34  jnz     loc_1800181F9
0x180017c3a  test    edi, edi
0x180017c3c  js      short loc_180017C97
0x180017c3e  cmp     [rbp+0E0h+arg_20], 0
0x180017c45  jnz     loc_18001821A
0x180017c4b  cmp     esi, 4
0x180017c4e  jz      loc_180018250
0x180017c54  test    byte ptr [rbx+1Ch], 40h
0x180017c58  jnz     loc_18001825E
0x180017c5e  test    byte ptr [rbx+0C0h], 2
0x180017c65  jnz     loc_180018280
0x180017c6b  cmp     cs:?SampRestrictNullSessions@@3EA, 0; uchar SampRestrictNullSessions
0x180017c72  jz      loc_180017D2B
0x180017c78  mov     r9d, esi
0x180017c7b  lea     rdx, [rsp+1E0h+var_168]
0x180017c80  mov     r8d, r14d
0x180017c83  lea     rcx, [rsp+1E0h+pSecurityDescriptor]
0x180017c88  call    ?SampRemoveAnonymousAccess@@YAJPEAPEAXPEAKKW4_SAMP_OBJECT_TYPE@@@Z; SampRemoveAnonymousAccess(void * *,ulong *,ulong,_SAMP_OBJECT_TYPE)
0x180017c8d  mov     edi, eax
0x180017c8f  test    eax, eax
0x180017c91  jns     loc_180017D2B
0x180017c97  mov     rcx, [rsp+1E0h+pSecurityDescriptor]; hMem
0x180017c9c  test    rcx, rcx
0x180017c9f  jnz     loc_18001843E
0x180017ca5  mov     rcx, [rbp+0E0h+ClientToken]; Handle
0x180017ca9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180017cad  jnz     loc_180018449
0x180017cb3  test    edi, edi
0x180017cb5  jns     loc_180018475
0x180017cbb  mov     rcx, cs:WPP_GLOBAL_Control
0x180017cc2  test    dword ptr [rcx+44h], 20000h
0x180017cc9  jnz     loc_180018454
0x180017ccf  mov     eax, edi
0x180017cd1  mov     rcx, [rbp+0E0h+var_40]
0x180017cd8  xor     rcx, rsp; StackCookie
0x180017cdb  call    __security_check_cookie
0x180017ce0  mov     rbx, [rsp+1E0h+arg_18]
0x180017ce8  add     rsp, 1B0h
0x180017cef  pop     r15
0x180017cf1  pop     r14
0x180017cf3  pop     r13
0x180017cf5  pop     r12
0x180017cf7  pop     rdi
0x180017cf8  pop     rsi
0x180017cf9  pop     rbp
0x180017cfa  retn
0x180017cfb  mov     ecx, esi
0x180017cfd  sub     ecx, 1
0x180017d00  jz      loc_180017F69
0x180017d06  sub     ecx, 1
0x180017d09  jz      loc_180017FEA
0x180017d0f  sub     ecx, 1
0x180017d12  jz      loc_180017FD3
0x180017d18  cmp     ecx, 1
0x180017d1b  jz      loc_180017F8E
0x180017d21  xor     r14d, r14d
0x180017d24  xor     ecx, ecx
0x180017d26  jmp     loc_180017B01
0x180017d2b  mov     rdx, [rbp+0E0h+ClientToken]; ClientToken
0x180017d2f  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180017d33  jnz     loc_1800182DF
0x180017d39  cmp     cs:?SampUseDsData@@3EA, 0; uchar SampUseDsData
0x180017d40  jnz     loc_18001832A
0x180017d46  xor     dil, dil
0x180017d49  mov     rcx, cs:WPP_GLOBAL_Control
0x180017d50  test    dword ptr [rcx+44h], 20000h
0x180017d57  jnz     loc_18001833F
0x180017d5d  test    dil, dil
0x180017d60  jnz     loc_18001835D
0x180017d66  xor     ecx, ecx; BindingHandle
0x180017d68  call    cs:__imp_RpcImpersonateClient
0x180017d6e  mov     ecx, eax; Status
0x180017d70  call    cs:__imp_I_RpcMapWin32Status
0x180017d76  mov     esi, 2
0x180017d7b  mov     edi, eax
0x180017d7d  cmp     eax, 0C0020041h
0x180017d82  jz      loc_18001839D
0x180017d88  test    edi, edi
0x180017d8a  js      loc_1800183AE
0x180017d90  mov     rcx, cs:WPP_GLOBAL_Control
0x180017d97  test    dword ptr [rcx+44h], 20000h
0x180017d9e  jnz     loc_1800183B5
0x180017da4  test    edi, edi
0x180017da6  js      loc_180017C97
0x180017dac  mov     ecx, [rsp+1E0h+AccessMask]
0x180017db0  xor     r15b, r15b
0x180017db3  test    ecx, ecx
0x180017db5  jz      loc_1800183D6
0x180017dbb  lea     rax, [rbx+0D0h]
0x180017dc2  mov     r9, r12; ObjectName
0x180017dc5  mov     [rsp+1E0h+GenerateOnClose], rax; GenerateOnClose
0x180017dca  lea     r14, [rbx+94h]
0x180017dd1  lea     rax, [rsp+1E0h+var_178]
0x180017dd6  mov     rdx, rbx; HandleId
0x180017dd9  mov     [rsp+1E0h+AccessStatus], rax; AccessStatus
0x180017dde  lea     r8, [r13+18h]; ObjectTypeName
0x180017de2  mov     rax, [rsp+1E0h+pSecurityDescriptor]
0x180017de7  mov     [rsp+1E0h+GrantedAccess], r14; GrantedAccess
0x180017dec  mov     [rsp+1E0h+ObjectCreation], 0; ObjectCreation
0x180017df1  mov     [rsp+1E0h+GenericMapping], r13; GenericMapping
0x180017df6  mov     [rsp+1E0h+DesiredAccess], ecx; DesiredAccess
0x180017dfa  lea     rcx, ?SampSamSubsystem@@3U_UNICODE_STRING@@A; SubsystemName
0x180017e01  mov     [rsp+1E0h+SecurityDescriptor], rax; SecurityDescriptor
0x180017e06  call    cs:__imp_NtAccessCheckAndAuditAlarm
0x180017e0c  mov     edi, eax
0x180017e0e  test    r15b, r15b
0x180017e11  jnz     loc_1800183E7
0x180017e17  cmp     esi, 2
0x180017e1a  jnz     loc_18001840E
0x180017e20  call    cs:__imp_RpcRevertToSelf
0x180017e26  test    edi, edi
0x180017e28  js      loc_180017C97
0x180017e2e  movsxd  rcx, dword ptr [rbx+10h]
0x180017e32  lea     r15, __ImageBase
0x180017e39  mov     rsi, rcx
0x180017e3c  add     rsi, rsi
0x180017e3f  cmp     ds:rva dword_1800BD008[r15+rsi*8], 0
0x180017e48  jbe     loc_180017C97
0x180017e4e  mov     rsi, ds:rva ?SampObjectExtendedAttributesProperties@@3QBU_SAMP_OBJECT_EXTENDED_ATTRIBUTES@@B[r15+rsi*8]; _SAMP_OBJECT_EXTENDED_ATTRIBUTES const near * const SampObjectExtendedAttributesProperties ...
0x180017e56  xor     r11d, r11d
0x180017e59  nop     dword ptr [rax+00000000h]
0x180017e60  movsxd  rax, ecx
0x180017e63  add     rax, rax
0x180017e66  mov     edx, ds:rva dword_1800BD00C[r15+rax*8]
0x180017e6e  lea     r8d, [rdx+r11]
0x180017e72  cmp     r8d, edx
0x180017e75  jb      short loc_180017ECA
0x180017e77  mov     eax, ds:rva dword_1800BD008[r15+rax*8]
0x180017e7f  add     eax, edx
0x180017e81  cmp     r8d, eax
0x180017e84  jnb     short loc_180017ECA
0x180017e86  mov     edx, r11d
0x180017e89  lea     rax, [r11+24h]
0x180017e8d  lea     rax, [rax+rax*2]
0x180017e91  shl     rdx, 5
0x180017e95  lea     r10, [rbx+rax*8]
0x180017e99  mov     eax, [rdx+rsi+18h]
0x180017e9d  and     eax, [r14]
0x180017ea0  neg     eax
0x180017ea2  movzx   eax, byte ptr [r10]
0x180017ea6  sbb     r8b, r8b
0x180017ea9  and     al, 0FBh
0x180017eab  and     r8b, 4
0x180017eaf  or      r8b, al
0x180017eb2  mov     eax, [rdx+rsi+1Ch]
0x180017eb6  and     eax, [r14]
0x180017eb9  and     r8b, 0F7h
0x180017ebd  neg     eax
0x180017ebf  sbb     cl, cl
0x180017ec1  and     cl, 8
0x180017ec4  or      r8b, cl
0x180017ec7  mov     [r10], r8b
0x180017eca  movsxd  rcx, dword ptr [rbx+10h]
0x180017ece  inc     r11d
0x180017ed1  mov     rax, rcx
0x180017ed4  add     rax, rax
0x180017ed7  cmp     r11d, ds:rva dword_1800BD008[r15+rax*8]
0x180017edf  jb      loc_180017E60
0x180017ee5  jmp     loc_180017C97
0x180017eea  mov     rcx, cs:WPP_GLOBAL_Control
0x180017ef1  mov     edi, 0C0000017h
0x180017ef6  test    dword ptr [rcx+44h], 20000h
0x180017efd  jz      loc_180017C1D
0x180017f03  mov     rcx, [rcx+38h]
0x180017f07  lea     r8, WPP_ec9974b3367635591c8fff3dd01cd200_Traceguids
0x180017f0e  mov     edx, 2Ch ; ','
0x180017f13  mov     dword ptr [rsp+1E0h+SecurityDescriptor], edi
0x180017f17  mov     r9d, 0C0000017h
0x180017f1d  call    WPP_SF_Dd
0x180017f22  jmp     loc_180017C1D
0x180017f27  cmp     [rbp+0E0h+arg_20], 0
0x180017f2e  jnz     loc_180017B1D
0x180017f34  cmp     [rbp+0E0h+arg_28], 0
0x180017f3b  jnz     loc_180017B1D
0x180017f41  mov     [rbx+94h], ecx
0x180017f47  mov     byte ptr [rbx+0D0h], 0
0x180017f4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180017f55  test    dword ptr [rcx+44h], 20000h
0x180017f5c  jnz     loc_180018001
0x180017f62  xor     eax, eax
0x180017f64  jmp     loc_180017CD1
0x180017f69  mov     r12, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180017f70  imul    rcx, r14, 550h
0x180017f77  add     r12, 10h
0x180017f7b  mov     r14d, 101h
0x180017f81  add     r12, rcx
0x180017f84  mov     ecx, 0F07FFh
0x180017f89  jmp     loc_180017B01
0x180017f8e  lea     r12, [rbx+0A0h]
0x180017f95  mov     ecx, 0F07FFh
0x180017f9a  mov     r14d, 100h
0x180017fa0  jmp     loc_180017B01
0x180017fa5  mov     eax, [rsp+1E0h+AccessMask]
0x180017fa9  test    dil, dil
0x180017fac  mov     byte ptr [rbx+0D0h], 0
0x180017fb3  cmovs   eax, ecx
0x180017fb6  mov     [rbx+94h], eax
0x180017fbc  mov     rcx, cs:WPP_GLOBAL_Control
0x180017fc3  test    dword ptr [rcx+44h], 20000h
0x180017fca  jz      short loc_180017F62
0x180017fcc  mov     edx, 13h
0x180017fd1  jmp     short loc_180018006
0x180017fd3  lea     r12, [rbx+0A0h]
  ... truncated ...
```
