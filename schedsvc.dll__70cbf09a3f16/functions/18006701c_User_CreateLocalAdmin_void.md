# User::CreateLocalAdmin(void)

- ea: `0x18006701c`
- end: `0x1800672c9`
- name: `?CreateLocalAdmin@User@@CA?AV1@XZ`
- size: `685`
- prototype: `struct User *__fastcall(struct User *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180028dd4`

## callees

- `0x18002af2c`
- `0x1800538cc`
- `0x180054084`
- `0x18005790c`
- `0x18006701c`
- `0x18007e6d0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180067087`
- `ntdll!RtlNtStatusToDosError` at `0x180067141`
- `ntdll!RtlNtStatusToDosError` at `0x180067087`
- `ntdll!RtlNtStatusToDosError` at `0x180067141`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800671fa`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800671fa`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800671cb`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180067131`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180067131`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18006710f`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180067077`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180067077`

## pseudocode

```c
struct User *__fastcall User::CreateLocalAdmin(struct User *a1)
{
  int v2; // eax
  ULONG v3; // ebx
  int v4; // eax
  ULONG v5; // ebx
  int v6; // edi
  void **pExceptionObject; // [rsp+20h] [rbp-E0h] BYREF
  char v9; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *v10; // [rsp+30h] [rbp-D0h]
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
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-60h] BYREF
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
    v10 = &qword_1800A4718;
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
    v10 = &qword_1800A4718;
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
    v10 = &qword_1800A4718;
    v11 = 0;
    v12 = 0;
    v13 = v6;
    v14 = -1;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  wmi::ScopeGuardImpl1<long (*)(void *),void *>::~ScopeGuardImpl1<long (*)(void *),void *>(v19);
  wmi::ScopeGuardImpl1<long (*)(void *),void *>::~ScopeGuardImpl1<long (*)(void *),void *>(v22);
  return a1;
}

```

## disassembly

```asm
0x18006701c  push    rbp
0x18006701e  push    rbx
0x18006701f  push    rsi
0x180067020  push    rdi
0x180067021  lea     rbp, [rsp-48h]
0x180067026  sub     rsp, 148h
0x18006702d  mov     rax, cs:__security_cookie
0x180067034  xor     rax, rsp
0x180067037  mov     [rbp+60h+var_30], rax
0x18006703b  mov     rbx, rcx
0x18006703e  mov     [rbp+60h+var_90], rcx
0x180067042  xor     esi, esi
0x180067044  mov     [rsp+160h+var_104], esi
0x180067048  mov     [rsp+160h+PolicyHandle], rsi
0x18006704d  mov     qword ptr [rbp+60h+ObjectAttributes.Length], 30h ; '0'
0x180067055  xorps   xmm0, xmm0
0x180067058  movdqu  xmmword ptr [rbp+60h+ObjectAttributes.RootDirectory], xmm0
0x18006705d  mov     qword ptr [rbp+60h+ObjectAttributes.Attributes], rsi
0x180067061  movdqu  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm0
0x180067066  lea     r9, [rsp+160h+PolicyHandle]; PolicyHandle
0x18006706b  lea     edi, [rsi+1]
0x18006706e  mov     r8d, edi; DesiredAccess
0x180067071  lea     rdx, [rbp+60h+ObjectAttributes]; ObjectAttributes
0x180067075  xor     ecx, ecx; SystemName
0x180067077  call    cs:__imp_LsaOpenPolicy
0x18006707d  test    eax, eax
0x18006707f  jns     loc_18006710A
0x180067085  mov     ecx, eax; Status
0x180067087  call    cs:__imp_RtlNtStatusToDosError
0x18006708d  mov     ebx, eax
0x18006708f  lea     rax, WPP_GLOBAL_Control
0x180067096  mov     rcx, cs:WPP_GLOBAL_Control
0x18006709d  cmp     rcx, rax
0x1800670a0  jz      short loc_1800670C4
0x1800670a2  test    byte ptr [rcx+1Ch], 80h
0x1800670a6  jz      short loc_1800670C4
0x1800670a8  cmp     byte ptr [rcx+19h], 2
0x1800670ac  jb      short loc_1800670C4
0x1800670ae  lea     edx, [rsi+0Ch]
0x1800670b1  mov     r9d, ebx
0x1800670b4  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x1800670bb  mov     rcx, [rcx+10h]
0x1800670bf  call    WPP_SF_d
0x1800670c4  mov     [rsp+160h+var_138], sil
0x1800670c9  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800670d0  mov     [rsp+160h+pExceptionObject], rax
0x1800670d5  lea     rax, qword_1800A4718
0x1800670dc  mov     [rsp+160h+var_130], rax
0x1800670e1  mov     [rsp+160h+var_128], rsi
0x1800670e6  mov     [rsp+160h+var_120], rsi
0x1800670eb  mov     [rsp+160h+var_118], ebx
0x1800670ef  mov     [rsp+160h+var_114], 0FFFFFFFFFFFFFFFFh
0x1800670f8  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x1800670ff  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x180067104  call    _CxxThrowException_0
0x18006710a  mov     rcx, [rsp+160h+PolicyHandle]; PolicyHandle
0x18006710f  mov     rax, cs:__imp_LsaClose
0x180067116  mov     [rbp+60h+var_D8], sil
0x18006711a  mov     [rbp+60h+var_D0], rax
0x18006711e  mov     [rbp+60h+var_C8], rcx
0x180067122  mov     [rsp+160h+Buffer], rsi
0x180067127  lea     r8, [rsp+160h+Buffer]; Buffer
0x18006712c  mov     edx, 5; InformationClass
0x180067131  call    cs:__imp_LsaQueryInformationPolicy
0x180067137  test    eax, eax
0x180067139  jns     loc_1800671C6
0x18006713f  mov     ecx, eax; Status
0x180067141  call    cs:__imp_RtlNtStatusToDosError
0x180067147  mov     ebx, eax
0x180067149  lea     rax, WPP_GLOBAL_Control
0x180067150  mov     rcx, cs:WPP_GLOBAL_Control
0x180067157  cmp     rcx, rax
0x18006715a  jz      short loc_180067180
0x18006715c  test    byte ptr [rcx+1Ch], 80h
0x180067160  jz      short loc_180067180
0x180067162  cmp     byte ptr [rcx+19h], 2
0x180067166  jb      short loc_180067180
0x180067168  mov     edx, 0Dh
0x18006716d  mov     r9d, ebx
0x180067170  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x180067177  mov     rcx, [rcx+10h]
0x18006717b  call    WPP_SF_d
0x180067180  mov     [rsp+160h+var_138], sil
0x180067185  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18006718c  mov     [rsp+160h+pExceptionObject], rax
0x180067191  lea     rax, qword_1800A4718
0x180067198  mov     [rsp+160h+var_130], rax
0x18006719d  mov     [rsp+160h+var_128], rsi
0x1800671a2  mov     [rsp+160h+var_120], rsi
0x1800671a7  mov     [rsp+160h+var_118], ebx
0x1800671ab  mov     [rsp+160h+var_114], 0FFFFFFFFFFFFFFFFh
0x1800671b4  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x1800671bb  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x1800671c0  call    _CxxThrowException_0
0x1800671c6  mov     rdx, [rsp+160h+Buffer]
0x1800671cb  mov     rax, cs:__imp_LsaFreeMemory
0x1800671d2  mov     [rsp+160h+var_F0], sil
0x1800671d7  mov     [rsp+160h+var_E8], rax
0x1800671dc  mov     [rbp+60h+var_E0], rdx
0x1800671e0  mov     [rsp+160h+cbSid], 44h ; 'D'
0x1800671e8  lea     r9, [rsp+160h+cbSid]; cbSid
0x1800671ed  lea     r8, [rbp+60h+pSid]; pSid
0x1800671f1  mov     rdx, [rdx+10h]; DomainSid
0x1800671f5  mov     ecx, 26h ; '&'; WellKnownSidType
0x1800671fa  call    cs:__imp_CreateWellKnownSid
0x180067200  mov     [rbx], rsi
0x180067203  mov     [rsp+160h+var_104], edi
0x180067207  mov     r8d, edi; enum _SID_NAME_USE
0x18006720a  lea     rdx, [rbp+60h+pSid]; void *
0x18006720e  mov     rcx, rbx; this
0x180067211  call    ?FromSid@User@@SAJAEAV1@PEAXW4_SID_NAME_USE@@@Z; User::FromSid(User &,void *,_SID_NAME_USE)
0x180067216  mov     edi, eax
0x180067218  test    eax, eax
0x18006721a  jns     short loc_180067299
0x18006721c  lea     rax, WPP_GLOBAL_Control
0x180067223  mov     rcx, cs:WPP_GLOBAL_Control
0x18006722a  cmp     rcx, rax
0x18006722d  jz      short loc_180067253
0x18006722f  test    byte ptr [rcx+1Ch], 80h
0x180067233  jz      short loc_180067253
0x180067235  cmp     byte ptr [rcx+19h], 2
0x180067239  jb      short loc_180067253
0x18006723b  mov     edx, 0Eh
0x180067240  mov     r9d, edi
0x180067243  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x18006724a  mov     rcx, [rcx+10h]
0x18006724e  call    WPP_SF_d
0x180067253  mov     [rsp+160h+var_138], sil
0x180067258  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18006725f  mov     [rsp+160h+pExceptionObject], rax
0x180067264  lea     rax, qword_1800A4718
0x18006726b  mov     [rsp+160h+var_130], rax
0x180067270  mov     [rsp+160h+var_128], rsi
0x180067275  mov     [rsp+160h+var_120], rsi
0x18006727a  mov     [rsp+160h+var_118], edi
0x18006727e  mov     [rsp+160h+var_114], 0FFFFFFFFFFFFFFFFh
0x180067287  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18006728e  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x180067293  call    _CxxThrowException_0
0x180067299  lea     rcx, [rsp+160h+var_F0]
0x18006729e  call    ??1?$ScopeGuardImpl1@P6AJPEAX@ZPEAX@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<long (*)(void *),void *>::~ScopeGuardImpl1<long (*)(void *),void *>(void)
0x1800672a3  nop
0x1800672a4  lea     rcx, [rbp+60h+var_D8]
0x1800672a8  call    ??1?$ScopeGuardImpl1@P6AJPEAX@ZPEAX@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<long (*)(void *),void *>::~ScopeGuardImpl1<long (*)(void *),void *>(void)
0x1800672ad  mov     rax, rbx
0x1800672b0  mov     rcx, [rbp+60h+var_30]
0x1800672b4  xor     rcx, rsp; StackCookie
0x1800672b7  call    __security_check_cookie
0x1800672bc  add     rsp, 148h
0x1800672c3  pop     rdi
0x1800672c4  pop     rsi
0x1800672c5  pop     rbx
0x1800672c6  pop     rbp
0x1800672c7  retn
```
