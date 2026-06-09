# CUserPropertyStore::GetValue(_tagpropertykey const &,tagPROPVARIANT *)

- ea: `0x18000a4e0`
- end: `0x18000aa6a`
- name: `?GetValue@CUserPropertyStore@@UEAAJAEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z`
- size: `1418`
- prototype: `int(CUserPropertyStore *__hidden this, const struct _tagpropertykey *, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000a4e0`
- `0x18000c240`
- `0x180017010`

## import_xrefs

- `SHCORE!__imp_SHWindowsPolicy` at `0x18000a6df`
- `SHCORE!__imp_SHWindowsPolicy` at `0x18000a7e4`
- `SHCORE!__imp_SHWindowsPolicy` at `0x18000a6df`
- `SHCORE!__imp_SHWindowsPolicy` at `0x18000a7e4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000a95f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000a95f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000a64e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000a64e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a729`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a7b3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a729`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a7b3`
- `ntdll!RtlNtStatusToDosError` at `0x18000a656`
- `ntdll!RtlNtStatusToDosError` at `0x18000a656`
- `PROPSYS!PropVariantToUInt32` at `0x18000a832`
- `PROPSYS!PropVariantToUInt32` at `0x18000a832`
- `PROPSYS!PropVariantToBoolean` at `0x18000a58f`
- `PROPSYS!PropVariantToBoolean` at `0x18000aa45`
- `PROPSYS!PropVariantToBoolean` at `0x18000a58f`
- `PROPSYS!PropVariantToBoolean` at `0x18000aa45`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a599`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a83e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a855`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a599`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a83e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a855`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18000a630`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18000a630`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18000a6b7`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18000a741`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18000a6b7`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18000a741`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18000a684`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18000a684`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18000a6ae`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18000a6ae`
- `dsreg!DsrIsDeviceJoined` at `0x18000a5c0`
- `dsreg!DsrIsDeviceJoined` at `0x18000a5c0`

## pseudocode

```c
__int64 __fastcall CUserPropertyStore::GetValue(
        CUserPropertyStore *this,
        const struct _tagpropertykey *a2,
        const PROPVARIANT *a3)
{
  __int64 v6; // rax
  char v7; // r13
  int v8; // eax
  int v9; // ebx
  NTSTATUS v10; // ecx
  signed int v11; // eax
  bool v12; // sf
  PVOID v13; // r14
  bool v14; // bl
  bool v15; // r14
  __int64 v16; // rax
  HRESULT v17; // ebx
  char v18; // dl
  unsigned int v19; // ebx
  int i; // ebx
  __int64 v22; // rax
  int v23; // ecx
  __int64 v24; // rcx
  _DWORD *v25; // rax
  int v26; // eax
  BOOL pfRet[2]; // [rsp+48h] [rbp-49h] BYREF
  char v28; // [rsp+50h] [rbp-41h]
  PVOID PolicyHandle; // [rsp+58h] [rbp-39h] BYREF
  PROPVARIANT propvarIn[2]; // [rsp+60h] [rbp-31h] BYREF
  __int64 v31; // [rsp+70h] [rbp-21h]
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-19h] BYREF

  if ( !a3 )
    return 2147942487LL;
  if ( a2->pid != 3 || *(_OWORD *)&a2->fmtid != PKEY_SAM_DontEnumerateForLogon )
    goto LABEL_58;
  v31 = 0;
  v6 = *(_QWORD *)this;
  pfRet[0] = 0;
  *(_OWORD *)propvarIn = 0;
  if ( (*(int (__fastcall **)(CUserPropertyStore *, __int128 *, PROPVARIANT *))(v6 + 40))(
         this,
         &PKEY_SAM_DontShowInLogonUI,
         propvarIn) >= 0 )
  {
    if ( LOWORD(propvarIn[0]) )
      PropVariantToBoolean(propvarIn, pfRet);
    PropVariantClear(propvarIn);
  }
  if ( !pfRet[0] )
  {
    v7 = *((_BYTE *)this + 33);
    v28 = *((_BYTE *)this + 32);
    if ( (int)DsrIsDeviceJoined(&dword_1800204B8, 0) < 0 )
      dword_1800204B8 = 0;
    v8 = `IsDomainMemberMode'::`2'::s_tbDomainMemberMode;
    if ( !`IsDomainMemberMode'::`2'::s_tbDomainMemberMode )
    {
      LODWORD(propvarIn[1]) = 1;
      ObjectAttributes.SecurityQualityOfService = propvarIn;
      v9 = 0;
      propvarIn[0] = (PROPVARIANT)0x20000000CLL;
      *(_QWORD *)&ObjectAttributes.Length = 48;
      memset(&ObjectAttributes.RootDirectory, 0, 32);
      PolicyHandle = 0;
      while ( 1 )
      {
        v10 = LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle);
        if ( (unsigned int)(v10 + 1073610729) > 1 )
          break;
        if ( ++v9 >= 10 )
          break;
        Sleep(0xAu);
      }
      v11 = RtlNtStatusToDosError(v10);
      v12 = v11 < 0;
      if ( v11 > 0 )
        v12 = 1;
      if ( !v12 )
      {
        v13 = PolicyHandle;
        *(_QWORD *)pfRet = 0;
        if ( LsaQueryInformationPolicy(PolicyHandle, PolicyDnsDomainInformation, (PVOID *)pfRet) < 0 )
        {
          LsaClose(v13);
        }
        else
        {
          v14 = *(_WORD *)(*(_QWORD *)pfRet + 16LL)
             || *(_WORD *)(*(_QWORD *)pfRet + 32LL)
             || *(_QWORD *)(*(_QWORD *)pfRet + 64LL);
          LsaFreeMemory(*(PVOID *)pfRet);
          LsaClose(v13);
          if ( v14 )
          {
            `IsDomainMemberMode'::`2'::s_tbDomainMemberMode = 1;
            goto LABEL_27;
          }
        }
        `IsDomainMemberMode'::`2'::s_tbDomainMemberMode = 2;
LABEL_35:
        if ( !dword_1800204B8 )
        {
          if ( v7 )
          {
            pfRet[0] = 0;
            LODWORD(PolicyHandle) = 4;
            RegGetValueW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
              L"NoConnectedUser",
              0x10u,
              0,
              pfRet,
              (LPDWORD)&PolicyHandle);
            v15 = (pfRet[0] & 2) != 0;
            if ( (pfRet[0] & 2) != 0 )
              goto LABEL_42;
          }
          goto LABEL_58;
        }
LABEL_27:
        if ( v7 )
        {
          if ( (unsigned int)SHWindowsPolicy(POLID_DontEnumerateConnectedUsers)
            || (pfRet[0] = 0,
                LODWORD(PolicyHandle) = 4,
                RegGetValueW(
                  HKEY_LOCAL_MACHINE,
                  L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
                  L"NoConnectedUser",
                  0x10u,
                  0,
                  pfRet,
                  (LPDWORD)&PolicyHandle),
                (pfRet[0] & 2) != 0) )
          {
LABEL_41:
            v15 = 1;
LABEL_42:
            pfRet[0] = 0;
            v31 = 0;
            v16 = *(_QWORD *)this;
            *(_OWORD *)propvarIn = 0;
            if ( (*(int (__fastcall **)(CUserPropertyStore *, __int128 *, PROPVARIANT *))(v16 + 40))(
                   this,
                   &PKEY_LOGON_Status,
                   propvarIn) >= 0 )
            {
              if ( LOWORD(propvarIn[0]) )
              {
                v17 = PropVariantToUInt32(propvarIn, (ULONG *)pfRet);
                PropVariantClear(propvarIn);
                if ( v17 >= 0 )
                  v15 = (pfRet[0] & 0xFFFFFFFB) != 0;
              }
              else
              {
                PropVariantClear(propvarIn);
              }
            }
            *(_WORD *)a3 = 11;
            *((_WORD *)a3 + 4) = !v15 - 1;
            goto LABEL_48;
          }
        }
        else if ( v28 && !(unsigned int)SHWindowsPolicy(POLID_EnumerateLocalUsers) )
        {
          goto LABEL_41;
        }
LABEL_58:
        for ( i = 0; ; ++i )
        {
          v22 = *((_QWORD *)this + 3);
          v23 = v22 ? *(_DWORD *)v22 : 0;
          v18 = 0;
          if ( i >= v23 )
            break;
          v24 = *(_QWORD *)(*(_QWORD *)(v22 + 8) + 8LL * i);
          if ( (*(int (__fastcall **)(__int64, const struct _tagpropertykey *, const PROPVARIANT *))(*(_QWORD *)v24 + 40LL))(
                 v24,
                 a2,
                 a3) >= 0 )
          {
            if ( a2->pid != 3 || *(_OWORD *)&a2->fmtid != PKEY_SAM_DontEnumerateForLogon )
              goto LABEL_48;
            v25 = (_DWORD *)*((_QWORD *)this + 3);
            v26 = v25 ? *v25 : 0;
            if ( i == v26 - 1 )
              goto LABEL_48;
            pfRet[0] = 0;
            if ( *(_WORD *)a3 )
            {
              if ( PropVariantToBoolean(a3, pfRet) >= 0 && !pfRet[0] )
                goto LABEL_48;
            }
          }
        }
        goto LABEL_49;
      }
      v8 = `IsDomainMemberMode'::`2'::s_tbDomainMemberMode;
    }
    if ( v8 != 2 )
      goto LABEL_27;
    goto LABEL_35;
  }
  *(_WORD *)a3 = 11;
  *((_WORD *)a3 + 4) = -1;
LABEL_48:
  v18 = 1;
LABEL_49:
  v19 = 0;
  if ( !v18 )
    v19 = -2147024809;
  if ( a2->pid == PKEY_Identity_ProviderID.pid
    && *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)&PKEY_Identity_ProviderID.fmtid.Data1
    && *(_QWORD *)a2->fmtid.Data4 == *(_QWORD *)PKEY_Identity_ProviderID.fmtid.Data4
    && (unsigned int)dword_18001F000 > 4 )
  {
    LODWORD(PolicyHandle) = v19;
    ObjectAttributes.SecurityDescriptor = &PolicyHandle;
    *(_QWORD *)&ObjectAttributes.Length = off_18001F008;
    ObjectAttributes.SecurityQualityOfService = (PVOID)4;
    propvarIn[0] = (PROPVARIANT)0x40B000000LL;
    propvarIn[1] = 0;
    ObjectAttributes.RootDirectory = (HANDLE)(*(unsigned __int16 *)off_18001F008 | 0x200000000LL);
    ObjectAttributes.ObjectName = (PLSA_UNICODE_STRING)&dword_18001B53C;
    ObjectAttributes.Attributes = 39;
    *(&ObjectAttributes.Attributes + 1) = 1;
    pfRet[0] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, (PCEVENT_DESCRIPTOR)propvarIn, 0, 0, 3u, (PEVENT_DATA_DESCRIPTOR)&ObjectAttributes);
  }
  return v19;
}

```

## disassembly

```asm
0x18000a4e0  mov     r11, rsp
0x18000a4e3  push    rbp
0x18000a4e4  push    rsi
0x18000a4e5  push    r12
0x18000a4e7  push    r15
0x18000a4e9  lea     rbp, [r11-5Fh]
0x18000a4ed  sub     rsp, 0C8h
0x18000a4f4  mov     rax, cs:__security_cookie
0x18000a4fb  xor     rax, rsp
0x18000a4fe  mov     [rbp+57h+var_40], rax
0x18000a502  mov     r15, r8
0x18000a505  mov     rsi, rdx
0x18000a508  mov     r12, rcx
0x18000a50b  test    r8, r8
0x18000a50e  jz      loc_18000AA60
0x18000a514  mov     eax, cs:dword_18001AA50
0x18000a51a  mov     [r11+20h], rbx
0x18000a51e  mov     [r11-28h], rdi
0x18000a522  mov     [r11-30h], r13
0x18000a526  mov     [r11-38h], r14
0x18000a52a  cmp     [rdx+10h], eax
0x18000a52d  jnz     loc_18000A9A3
0x18000a533  mov     rax, [rdx]
0x18000a536  cmp     rax, qword ptr cs:PKEY_SAM_DontEnumerateForLogon
0x18000a53d  jnz     loc_18000A9A3
0x18000a543  mov     rax, [rdx+8]
0x18000a547  cmp     rax, qword ptr cs:PKEY_SAM_DontEnumerateForLogon+8
0x18000a54e  jnz     loc_18000A9A3
0x18000a554  xor     eax, eax
0x18000a556  lea     r8, [rbp+57h+propvarIn]
0x18000a55a  mov     [rbp+57h+var_78], rax
0x18000a55e  lea     rdx, PKEY_SAM_DontShowInLogonUI
0x18000a565  mov     rax, [rcx]
0x18000a568  xorps   xmm0, xmm0
0x18000a56b  xor     edi, edi
0x18000a56d  mov     [rbp+57h+pfRet], edi
0x18000a570  movups  xmmword ptr [rbp+57h+propvarIn], xmm0
0x18000a574  mov     rax, [rax+28h]
0x18000a578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a57d  test    eax, eax
0x18000a57f  js      short loc_18000A59F
0x18000a581  cmp     di, word ptr [rbp+57h+propvarIn]
0x18000a585  jz      short loc_18000A595
0x18000a587  lea     rdx, [rbp+57h+pfRet]; pfRet
0x18000a58b  lea     rcx, [rbp+57h+propvarIn]; propvarIn
0x18000a58f  call    cs:__imp_PropVariantToBoolean
0x18000a595  lea     rcx, [rbp+57h+propvarIn]; pvar
0x18000a599  call    cs:__imp_PropVariantClear
0x18000a59f  cmp     [rbp+57h+pfRet], edi
0x18000a5a2  jnz     loc_18000A991
0x18000a5a8  movzx   eax, byte ptr [r12+20h]
0x18000a5ae  lea     rcx, dword_1800204B8
0x18000a5b5  movzx   r13d, byte ptr [r12+21h]
0x18000a5bb  xor     edx, edx
0x18000a5bd  mov     [rbp+57h+var_98], al
0x18000a5c0  call    cs:__imp_DsrIsDeviceJoined
0x18000a5c6  test    eax, eax
0x18000a5c8  jns     short loc_18000A5D0
0x18000a5ca  mov     cs:dword_1800204B8, edi
0x18000a5d0  mov     eax, cs:?s_tbDomainMemberMode@?1??IsDomainMemberMode@@YA_NXZ@4W4TRIBIT@@A; TRIBIT `IsDomainMemberMode(void)'::`2'::s_tbDomainMemberMode
0x18000a5d6  test    eax, eax
0x18000a5d8  jnz     loc_18000A759
0x18000a5de  lea     rax, [rbp+57h+propvarIn]
0x18000a5e2  mov     dword ptr [rbp+57h+propvarIn+8], 1
0x18000a5e9  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], rax
0x18000a5ed  mov     ebx, edi
0x18000a5ef  mov     dword ptr [rbp+57h+propvarIn], 0Ch
0x18000a5f6  mov     dword ptr [rbp+57h+propvarIn+4], 2
0x18000a5fd  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18000a605  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], rdi
0x18000a609  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x18000a60d  mov     [rbp+57h+ObjectAttributes.ObjectName], rdi
0x18000a611  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rdi
0x18000a615  mov     [rbp+57h+PolicyHandle], rdi
0x18000a619  nop     dword ptr [rax+00000000h]
0x18000a620  lea     r9, [rbp+57h+PolicyHandle]; PolicyHandle
0x18000a624  mov     r8d, 1; DesiredAccess
0x18000a62a  lea     rdx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000a62e  xor     ecx, ecx; SystemName
0x18000a630  call    cs:__imp_LsaOpenPolicy
0x18000a636  mov     ecx, eax; Status
0x18000a638  add     eax, 3FFDFFE9h
0x18000a63d  cmp     eax, 1
0x18000a640  ja      short loc_18000A656
0x18000a642  inc     ebx
0x18000a644  cmp     ebx, 0Ah
0x18000a647  jge     short loc_18000A656
0x18000a649  mov     ecx, 0Ah; dwMilliseconds
0x18000a64e  call    cs:__imp_Sleep
0x18000a654  jmp     short loc_18000A620
0x18000a656  call    cs:__imp_RtlNtStatusToDosError
0x18000a65c  test    eax, eax
0x18000a65e  jle     short loc_18000A66A
0x18000a660  movzx   eax, ax
0x18000a663  or      eax, 80070000h
0x18000a668  test    eax, eax
0x18000a66a  js      loc_18000A753
0x18000a670  mov     r14, [rbp+57h+PolicyHandle]
0x18000a674  lea     r8, [rbp+57h+pfRet]; Buffer
0x18000a678  mov     rcx, r14; PolicyHandle
0x18000a67b  mov     qword ptr [rbp+57h+pfRet], rdi
0x18000a67f  mov     edx, 0Ch; InformationClass
0x18000a684  call    cs:__imp_LsaQueryInformationPolicy
0x18000a68a  test    eax, eax
0x18000a68c  js      loc_18000A73E
0x18000a692  mov     rcx, qword ptr [rbp+57h+pfRet]; Buffer
0x18000a696  cmp     [rcx+10h], di
0x18000a69a  jnz     short loc_18000A6AC
0x18000a69c  cmp     [rcx+20h], di
0x18000a6a0  jnz     short loc_18000A6AC
0x18000a6a2  cmp     [rcx+40h], rdi
0x18000a6a6  jnz     short loc_18000A6AC
0x18000a6a8  xor     bl, bl
0x18000a6aa  jmp     short loc_18000A6AE
0x18000a6ac  mov     bl, 1
0x18000a6ae  call    cs:__imp_LsaFreeMemory
0x18000a6b4  mov     rcx, r14; ObjectHandle
0x18000a6b7  call    cs:__imp_LsaClose
0x18000a6bd  test    bl, bl
0x18000a6bf  jz      loc_18000A747
0x18000a6c5  mov     cs:?s_tbDomainMemberMode@?1??IsDomainMemberMode@@YA_NXZ@4W4TRIBIT@@A, 1; TRIBIT `IsDomainMemberMode(void)'::`2'::s_tbDomainMemberMode
0x18000a6cf  test    r13b, r13b
0x18000a6d2  jz      loc_18000A7D3
0x18000a6d8  lea     rcx, POLID_DontEnumerateConnectedUsers
0x18000a6df  call    cs:__imp_SHWindowsPolicy
0x18000a6e5  test    eax, eax
0x18000a6e7  jnz     loc_18000A7F2
0x18000a6ed  lea     rax, [rbp+57h+PolicyHandle]
0x18000a6f1  mov     [rbp+57h+pfRet], edi
0x18000a6f4  mov     [rsp+30h], rax; pcbData
0x18000a6f9  lea     r8, aNoconnecteduse; "NoConnectedUser"
0x18000a700  lea     rax, [rbp+57h+pfRet]
0x18000a704  mov     dword ptr [rbp+57h+PolicyHandle], 4
0x18000a70b  mov     [rsp+0E0h+pvData], rax; pvData
0x18000a710  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000a717  mov     r9d, 10h; dwFlags
0x18000a71d  mov     [rsp+0E0h+pdwType], rdi; pdwType
0x18000a722  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000a729  call    cs:__imp_RegGetValueW
0x18000a72f  test    byte ptr [rbp+57h+pfRet], 2
0x18000a733  jz      loc_18000A9A5
0x18000a739  jmp     loc_18000A7F2
0x18000a73e  mov     rcx, r14; ObjectHandle
0x18000a741  call    cs:__imp_LsaClose
0x18000a747  mov     cs:?s_tbDomainMemberMode@?1??IsDomainMemberMode@@YA_NXZ@4W4TRIBIT@@A, 2; TRIBIT `IsDomainMemberMode(void)'::`2'::s_tbDomainMemberMode
0x18000a751  jmp     short loc_18000A762
0x18000a753  mov     eax, cs:?s_tbDomainMemberMode@?1??IsDomainMemberMode@@YA_NXZ@4W4TRIBIT@@A; TRIBIT `IsDomainMemberMode(void)'::`2'::s_tbDomainMemberMode
0x18000a759  cmp     eax, 2
0x18000a75c  jnz     loc_18000A6CF
0x18000a762  cmp     cs:dword_1800204B8, edi
0x18000a768  jnz     loc_18000A6CF
0x18000a76e  test    r13b, r13b
0x18000a771  jz      loc_18000A9A5
0x18000a777  lea     rax, [rbp+57h+PolicyHandle]
0x18000a77b  mov     [rbp+57h+pfRet], edi
0x18000a77e  mov     [rsp+30h], rax; pcbData
0x18000a783  lea     r8, aNoconnecteduse; "NoConnectedUser"
0x18000a78a  lea     rax, [rbp+57h+pfRet]
0x18000a78e  mov     dword ptr [rbp+57h+PolicyHandle], 4
0x18000a795  mov     [rsp+0E0h+pvData], rax; pvData
0x18000a79a  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000a7a1  mov     r9d, 10h; dwFlags
0x18000a7a7  mov     [rsp+0E0h+pdwType], rdi; pdwType
0x18000a7ac  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000a7b3  call    cs:__imp_RegGetValueW
0x18000a7b9  test    [rbp+57h+pfRet], 2
0x18000a7c0  setnz   r14b
0x18000a7c4  test    [rbp+57h+pfRet], 2
0x18000a7cb  jz      loc_18000A9A5
0x18000a7d1  jmp     short loc_18000A7F5
0x18000a7d3  cmp     [rbp+57h+var_98], dil
0x18000a7d7  jz      loc_18000A9A5
0x18000a7dd  lea     rcx, POLID_EnumerateLocalUsers
0x18000a7e4  call    cs:__imp_SHWindowsPolicy
0x18000a7ea  test    eax, eax
0x18000a7ec  jnz     loc_18000A9A5
0x18000a7f2  mov     r14b, 1
0x18000a7f5  xor     eax, eax
0x18000a7f7  mov     [rbp+57h+pfRet], edi
0x18000a7fa  mov     [rbp+57h+var_78], rax
0x18000a7fe  lea     r8, [rbp+57h+propvarIn]
0x18000a802  mov     rax, [r12]
0x18000a806  lea     rdx, PKEY_LOGON_Status
0x18000a80d  xorps   xmm0, xmm0
0x18000a810  mov     rcx, r12
0x18000a813  movups  xmmword ptr [rbp+57h+propvarIn], xmm0
0x18000a817  mov     rax, [rax+28h]
0x18000a81b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a820  test    eax, eax
0x18000a822  js      short loc_18000A85B
0x18000a824  lea     rcx, [rbp+57h+propvarIn]; pvar
0x18000a828  cmp     di, word ptr [rbp+57h+propvarIn]
0x18000a82c  jz      short loc_18000A855
0x18000a82e  lea     rdx, [rbp+57h+pfRet]; pulRet
0x18000a832  call    cs:__imp_PropVariantToUInt32
0x18000a838  lea     rcx, [rbp+57h+propvarIn]; pvar
0x18000a83c  mov     ebx, eax
0x18000a83e  call    cs:__imp_PropVariantClear
0x18000a844  test    ebx, ebx
0x18000a846  js      short loc_18000A85B
0x18000a848  test    [rbp+57h+pfRet], 0FFFFFFFBh
0x18000a84f  setnz   r14b
0x18000a853  jmp     short loc_18000A85B
0x18000a855  call    cs:__imp_PropVariantClear
0x18000a85b  xor     r14b, 1
0x18000a85f  mov     word ptr [r15], 0Bh
0x18000a865  movzx   eax, r14b
0x18000a869  dec     ax
0x18000a86c  mov     [r15+8], ax
0x18000a871  mov     dl, 1
0x18000a873  mov     r14, [rsp+0E0h+var_30]
0x18000a87b  test    dl, dl
0x18000a87d  mov     r13, [rsp+0E0h+var_28]
0x18000a885  mov     eax, 80070057h
0x18000a88a  mov     ebx, edi
0x18000a88c  cmovz   ebx, eax
0x18000a88f  mov     eax, cs:PKEY_Identity_ProviderID.pid
0x18000a895  cmp     [rsi+10h], eax
0x18000a898  jnz     loc_18000A965
0x18000a89e  mov     rax, [rsi]
0x18000a8a1  cmp     rax, qword ptr cs:PKEY_Identity_ProviderID.fmtid.Data1
0x18000a8a8  jnz     loc_18000A965
0x18000a8ae  mov     rax, [rsi+8]
0x18000a8b2  cmp     rax, qword ptr cs:PKEY_Identity_ProviderID.fmtid.Data4
0x18000a8b9  jnz     loc_18000A965
0x18000a8bf  mov     eax, cs:dword_18001F000
0x18000a8c5  cmp     eax, 4
0x18000a8c8  jbe     loc_18000A965
0x18000a8ce  lea     rax, [rbp+57h+PolicyHandle]
0x18000a8d2  mov     dword ptr [rbp+57h+PolicyHandle], ebx
0x18000a8d5  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rax
0x18000a8d9  lea     rcx, _TraceLoggingMetadata
0x18000a8e0  movzx   eax, cs:word_18001B532
0x18000a8e7  lea     rdx, [rbp+57h+propvarIn]; EventDescriptor
0x18000a8eb  mov     dword ptr [rbp+57h+propvarIn+4], eax
0x18000a8ee  xor     r9d, r9d; RelatedActivityId
0x18000a8f1  mov     rax, cs:off_18001F008
0x18000a8f8  xor     r8d, r8d; ActivityId
0x18000a8fb  mov     qword ptr [rbp+57h+ObjectAttributes.Length], rax
0x18000a8ff  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], 4
0x18000a907  mov     dword ptr [rbp+57h+propvarIn], 0B000000h
0x18000a90e  mov     [rbp+57h+propvarIn+8], rdi
0x18000a912  movzx   eax, word ptr [rax]
0x18000a915  mov     dword ptr [rbp+57h+ObjectAttributes.RootDirectory], eax
0x18000a918  lea     rax, dword_18001B53C
0x18000a91f  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18000a923  lea     rax, _TraceLoggingMetadataEnd
0x18000a92a  sub     eax, ecx
0x18000a92c  mov     dword ptr [rbp+57h+ObjectAttributes.RootDirectory+4], 2
0x18000a933  mov     [rbp+57h+ObjectAttributes.Attributes], 27h ; '''
0x18000a93a  mov     dword ptr [rbp+57h+ObjectAttributes+1Ch], 1
0x18000a941  mov     [rbp+57h+pfRet], eax
0x18000a944  mov     eax, [rbp+57h+pfRet]
0x18000a947  mov     rcx, cs:RegHandle; RegHandle
0x18000a94e  lea     rax, [rbp+57h+ObjectAttributes]
0x18000a952  mov     [rsp+0E0h+pvData], rax; UserData
0x18000a957  mov     dword ptr [rsp+0E0h+pdwType], 3; UserDataCount
0x18000a95f  call    cs:__imp_EventWriteTransfer
0x18000a965  mov     rdi, [rsp+0C0h]
0x18000a96d  mov     eax, ebx
0x18000a96f  mov     rbx, [rsp+0E0h+arg_18]
0x18000a977  mov     rcx, [rbp+57h+var_40]
0x18000a97b  xor     rcx, rsp; StackCookie
0x18000a97e  call    __security_check_cookie
0x18000a983  add     rsp, 0C8h
0x18000a98a  pop     r15
0x18000a98c  pop     r12
0x18000a98e  pop     rsi
0x18000a98f  pop     rbp
0x18000a990  retn
0x18000a991  mov     word ptr [r15], 0Bh
0x18000a997  mov     word ptr [r15+8], 0FFFFh
0x18000a99e  jmp     loc_18000A871
0x18000a9a3  xor     edi, edi
0x18000a9a5  mov     ebx, edi
0x18000a9a7  nop     word ptr [rax+rax+00000000h]
0x18000a9b0  mov     rax, [r12+18h]
0x18000a9b5  test    rax, rax
0x18000a9b8  jz      short loc_18000A9BE
0x18000a9ba  mov     ecx, [rax]
0x18000a9bc  jmp     short loc_18000A9C0
0x18000a9be  mov     ecx, edi
0x18000a9c0  xor     dl, dl
0x18000a9c2  cmp     ebx, ecx
0x18000a9c4  jge     loc_18000A873
0x18000a9ca  mov     rax, [rax+8]
0x18000a9ce  mov     r8, r15
0x18000a9d1  movsxd  rcx, ebx
0x18000a9d4  mov     rdx, rsi
0x18000a9d7  mov     rcx, [rax+rcx*8]
0x18000a9db  mov     rax, [rcx]
0x18000a9de  mov     rax, [rax+28h]
0x18000a9e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9e7  test    eax, eax
0x18000a9e9  js      short loc_18000AA59
0x18000a9eb  mov     eax, cs:dword_18001AA50
0x18000a9f1  cmp     [rsi+10h], eax
0x18000a9f4  jnz     loc_18000A871
0x18000a9fa  mov     rax, [rsi]
0x18000a9fd  cmp     rax, qword ptr cs:PKEY_SAM_DontEnumerateForLogon
  ... truncated ...
```
