# User::CreateLocalAdmin(void)

- ea: `0x180019c3c`
- end: `0x180019f07`
- name: `?CreateLocalAdmin@User@@CA?AV1@XZ`
- size: `715`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001aff4`

## callees

- `0x18000525c`
- `0x180008c4c`
- `0x18000cf80`
- `0x180019c3c`
- `0x18001acc4`
- `0x180030700`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180019e32`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180019e32`
- `ntdll!RtlNtStatusToDosError` at `0x180019cad`
- `ntdll!RtlNtStatusToDosError` at `0x180019d73`
- `ntdll!RtlNtStatusToDosError` at `0x180019cad`
- `ntdll!RtlNtStatusToDosError` at `0x180019d73`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180019c97`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180019c97`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180019d5d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180019d5d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180019e03`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180019d3b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct User *__fastcall User::CreateLocalAdmin(struct User *a1)
{
  int v2; // eax
  ULONG v3; // ebx
  int v4; // eax
  ULONG v5; // ebx
  int v6; // edi
  void **pExceptionObject; // [rsp+20h] [rbp-E0h] BYREF
  char v9; // [rsp+28h] [rbp-D8h]
  char *v10; // [rsp+30h] [rbp-D0h]
  __int64 v11; // [rsp+38h] [rbp-C8h]
  __int64 v12; // [rsp+40h] [rbp-C0h]
  ULONG v13; // [rsp+48h] [rbp-B8h]
  __int64 v14; // [rsp+4Ch] [rbp-B4h]
  DWORD cbSid; // [rsp+58h] [rbp-A8h] BYREF
  int v16; // [rsp+5Ch] [rbp-A4h]
  PVOID PolicyHandle; // [rsp+60h] [rbp-A0h] BYREF
  PVOID Buffer; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v19[8]; // [rsp+70h] [rbp-90h] BYREF
  NTSTATUS (__stdcall *v20)(PVOID); // [rsp+78h] [rbp-88h]
  PVOID v21; // [rsp+80h] [rbp-80h]
  _BYTE v22[8]; // [rsp+88h] [rbp-78h] BYREF
  NTSTATUS (__stdcall *v23)(LSA_HANDLE); // [rsp+90h] [rbp-70h]
  PVOID v24; // [rsp+98h] [rbp-68h]
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-60h] BYREF
  struct User *v26; // [rsp+D0h] [rbp-30h]
  _BYTE pSid[80]; // [rsp+E0h] [rbp-20h] BYREF

  v26 = a1;
  v16 = 0;
  PolicyHandle = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 40);
  v2 = LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle);
  if ( v2 < 0 )
  {
    v3 = RtlNtStatusToDosError(v2);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids, v3);
    }
    v9 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v10 = byte_180052608;
    v11 = 0;
    v12 = 0;
    v13 = v3;
    v14 = -1;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  v22[0] = 0;
  v23 = LsaClose;
  v24 = PolicyHandle;
  Buffer = 0;
  v4 = LsaQueryInformationPolicy(PolicyHandle, PolicyAccountDomainInformation, &Buffer);
  if ( v4 < 0 )
  {
    v5 = RtlNtStatusToDosError(v4);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids, v5);
    }
    v9 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v10 = byte_180052608;
    v11 = 0;
    v12 = 0;
    v13 = v5;
    v14 = -1;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  v19[0] = 0;
  v20 = LsaFreeMemory;
  v21 = Buffer;
  cbSid = 68;
  CreateWellKnownSid(WinAccountAdministratorSid, *((PSID *)Buffer + 2), pSid, &cbSid);
  *(_QWORD *)a1 = 0;
  v16 = 1;
  v6 = User::FromSid(a1, pSid, SidTypeUser);
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids,
        (unsigned int)v6);
    }
    v9 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v10 = byte_180052608;
    v11 = 0;
    v12 = 0;
    v13 = v6;
    v14 = -1;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  wmi::ScopeGuardImpl1<void * (*)(void *),unsigned short *>::~ScopeGuardImpl1<void * (*)(void *),unsigned short *>(v19);
  wmi::ScopeGuardImpl1<void * (*)(void *),unsigned short *>::~ScopeGuardImpl1<void * (*)(void *),unsigned short *>(v22);
  return a1;
}

```

## disassembly

```asm
0x180019c3c  push    rbp
0x180019c3e  push    rbx
0x180019c3f  push    rsi
0x180019c40  push    rdi
0x180019c41  lea     rbp, [rsp-48h]
0x180019c46  sub     rsp, 148h
0x180019c4d  mov     rax, cs:__security_cookie
0x180019c54  xor     rax, rsp
0x180019c57  mov     [rbp+60h+var_30], rax
0x180019c5b  mov     rbx, rcx
0x180019c5e  mov     [rbp+60h+var_90], rcx
0x180019c62  xor     esi, esi
0x180019c64  mov     [rsp+160h+var_104], esi
0x180019c68  mov     [rsp+160h+PolicyHandle], rsi
0x180019c6d  mov     qword ptr [rbp+60h+ObjectAttributes.Length], 30h ; '0'
0x180019c75  xorps   xmm0, xmm0
0x180019c78  movdqu  xmmword ptr [rbp+60h+ObjectAttributes.RootDirectory], xmm0
0x180019c7d  mov     qword ptr [rbp+60h+ObjectAttributes.Attributes], rsi
0x180019c81  movdqu  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm0
0x180019c86  lea     r9, [rsp+160h+PolicyHandle]; PolicyHandle
0x180019c8b  lea     edi, [rsi+1]
0x180019c8e  mov     r8d, edi; DesiredAccess
0x180019c91  lea     rdx, [rbp+60h+ObjectAttributes]; ObjectAttributes
0x180019c95  xor     ecx, ecx; SystemName
0x180019c97  call    cs:__imp_LsaOpenPolicy
0x180019c9e  nop     dword ptr [rax+rax+00h]
0x180019ca3  test    eax, eax
0x180019ca5  jns     loc_180019D36
0x180019cab  mov     ecx, eax; Status
0x180019cad  call    cs:__imp_RtlNtStatusToDosError
0x180019cb4  nop     dword ptr [rax+rax+00h]
0x180019cb9  mov     ebx, eax
0x180019cbb  lea     rax, WPP_GLOBAL_Control
0x180019cc2  mov     rcx, cs:WPP_GLOBAL_Control
0x180019cc9  cmp     rcx, rax
0x180019ccc  jz      short loc_180019CF0
0x180019cce  test    byte ptr [rcx+1Ch], 80h
0x180019cd2  jz      short loc_180019CF0
0x180019cd4  cmp     byte ptr [rcx+19h], 2
0x180019cd8  jb      short loc_180019CF0
0x180019cda  lea     edx, [rsi+0Ch]
0x180019cdd  mov     r9d, ebx
0x180019ce0  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x180019ce7  mov     rcx, [rcx+10h]
0x180019ceb  call    WPP_SF_d
0x180019cf0  mov     [rsp+160h+var_138], sil
0x180019cf5  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180019cfc  mov     [rsp+160h+pExceptionObject], rax
0x180019d01  lea     rax, byte_180052608
0x180019d08  mov     [rsp+160h+var_130], rax
0x180019d0d  mov     [rsp+160h+var_128], rsi
0x180019d12  mov     [rsp+160h+var_120], rsi
0x180019d17  mov     [rsp+160h+var_118], ebx
0x180019d1b  mov     [rsp+160h+var_114], 0FFFFFFFFFFFFFFFFh
0x180019d24  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180019d2b  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x180019d30  call    _CxxThrowException_0
0x180019d36  mov     rcx, [rsp+160h+PolicyHandle]; PolicyHandle
0x180019d3b  mov     rax, cs:__imp_LsaClose
0x180019d42  mov     [rbp+60h+var_D8], sil
0x180019d46  mov     [rbp+60h+var_D0], rax
0x180019d4a  mov     [rbp+60h+var_C8], rcx
0x180019d4e  mov     [rsp+160h+Buffer], rsi
0x180019d53  lea     r8, [rsp+160h+Buffer]; Buffer
0x180019d58  mov     edx, 5; InformationClass
0x180019d5d  call    cs:__imp_LsaQueryInformationPolicy
0x180019d64  nop     dword ptr [rax+rax+00h]
0x180019d69  test    eax, eax
0x180019d6b  jns     loc_180019DFE
0x180019d71  mov     ecx, eax; Status
0x180019d73  call    cs:__imp_RtlNtStatusToDosError
0x180019d7a  nop     dword ptr [rax+rax+00h]
0x180019d7f  mov     ebx, eax
0x180019d81  lea     rax, WPP_GLOBAL_Control
0x180019d88  mov     rcx, cs:WPP_GLOBAL_Control
0x180019d8f  cmp     rcx, rax
0x180019d92  jz      short loc_180019DB8
0x180019d94  test    byte ptr [rcx+1Ch], 80h
0x180019d98  jz      short loc_180019DB8
0x180019d9a  cmp     byte ptr [rcx+19h], 2
0x180019d9e  jb      short loc_180019DB8
0x180019da0  mov     edx, 0Dh
0x180019da5  mov     r9d, ebx
0x180019da8  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x180019daf  mov     rcx, [rcx+10h]
0x180019db3  call    WPP_SF_d
0x180019db8  mov     [rsp+160h+var_138], sil
0x180019dbd  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180019dc4  mov     [rsp+160h+pExceptionObject], rax
0x180019dc9  lea     rax, byte_180052608
0x180019dd0  mov     [rsp+160h+var_130], rax
0x180019dd5  mov     [rsp+160h+var_128], rsi
0x180019dda  mov     [rsp+160h+var_120], rsi
0x180019ddf  mov     [rsp+160h+var_118], ebx
0x180019de3  mov     [rsp+160h+var_114], 0FFFFFFFFFFFFFFFFh
0x180019dec  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180019df3  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x180019df8  call    _CxxThrowException_0
0x180019dfe  mov     rdx, [rsp+160h+Buffer]
0x180019e03  mov     rax, cs:__imp_LsaFreeMemory
0x180019e0a  mov     [rsp+160h+var_F0], sil
0x180019e0f  mov     [rsp+160h+var_E8], rax
0x180019e14  mov     [rbp+60h+var_E0], rdx
0x180019e18  mov     [rsp+160h+cbSid], 44h ; 'D'
0x180019e20  lea     r9, [rsp+160h+cbSid]; cbSid
0x180019e25  lea     r8, [rbp+60h+pSid]; pSid
0x180019e29  mov     rdx, [rdx+10h]; DomainSid
0x180019e2d  mov     ecx, 26h ; '&'; WellKnownSidType
0x180019e32  call    cs:__imp_CreateWellKnownSid
0x180019e39  nop     dword ptr [rax+rax+00h]
0x180019e3e  mov     [rbx], rsi
0x180019e41  mov     [rsp+160h+var_104], edi
0x180019e45  mov     r8d, edi; enum _SID_NAME_USE
0x180019e48  lea     rdx, [rbp+60h+pSid]; void *
0x180019e4c  mov     rcx, rbx; this
0x180019e4f  call    ?FromSid@User@@SAJAEAV1@PEAXW4_SID_NAME_USE@@@Z; User::FromSid(User &,void *,_SID_NAME_USE)
0x180019e54  mov     edi, eax
0x180019e56  test    eax, eax
0x180019e58  jns     short loc_180019ED7
0x180019e5a  lea     rax, WPP_GLOBAL_Control
0x180019e61  mov     rcx, cs:WPP_GLOBAL_Control
0x180019e68  cmp     rcx, rax
0x180019e6b  jz      short loc_180019E91
0x180019e6d  test    byte ptr [rcx+1Ch], 80h
0x180019e71  jz      short loc_180019E91
0x180019e73  cmp     byte ptr [rcx+19h], 2
0x180019e77  jb      short loc_180019E91
0x180019e79  mov     edx, 0Eh
0x180019e7e  mov     r9d, edi
0x180019e81  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x180019e88  mov     rcx, [rcx+10h]
0x180019e8c  call    WPP_SF_d
0x180019e91  mov     [rsp+160h+var_138], sil
0x180019e96  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180019e9d  mov     [rsp+160h+pExceptionObject], rax
0x180019ea2  lea     rax, byte_180052608
0x180019ea9  mov     [rsp+160h+var_130], rax
0x180019eae  mov     [rsp+160h+var_128], rsi
0x180019eb3  mov     [rsp+160h+var_120], rsi
0x180019eb8  mov     [rsp+160h+var_118], edi
0x180019ebc  mov     [rsp+160h+var_114], 0FFFFFFFFFFFFFFFFh
0x180019ec5  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180019ecc  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x180019ed1  call    _CxxThrowException_0
0x180019ed7  lea     rcx, [rsp+160h+var_F0]
0x180019edc  call    ??1?$ScopeGuardImpl1@P6APEAXPEAX@ZPEAG@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void * (*)(void *),ushort *>::~ScopeGuardImpl1<void * (*)(void *),ushort *>(void)
0x180019ee1  nop
0x180019ee2  lea     rcx, [rbp+60h+var_D8]
0x180019ee6  call    ??1?$ScopeGuardImpl1@P6APEAXPEAX@ZPEAG@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void * (*)(void *),ushort *>::~ScopeGuardImpl1<void * (*)(void *),ushort *>(void)
0x180019eeb  mov     rax, rbx
0x180019eee  mov     rcx, [rbp+60h+var_30]
0x180019ef2  xor     rcx, rsp; StackCookie
0x180019ef5  call    __security_check_cookie
0x180019efa  add     rsp, 148h
0x180019f01  pop     rdi
0x180019f02  pop     rsi
0x180019f03  pop     rbx
0x180019f04  pop     rbp
0x180019f05  retn
```
