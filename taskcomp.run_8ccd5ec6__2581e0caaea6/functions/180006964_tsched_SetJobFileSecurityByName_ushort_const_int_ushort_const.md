# tsched::SetJobFileSecurityByName(ushort const *,int,ushort const *)

- ea: `0x180006964`
- end: `0x180006dd2`
- name: `?SetJobFileSecurityByName@tsched@@YAJPEBGH0@Z`
- size: `1134`
- prototype: `__int64 __fastcall(wchar_t *String2, const unsigned __int16 *, int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180013820`

## callees

- `0x180005094`
- `0x180006964`
- `0x180006dd8`
- `0x18000cf80`
- `0x180011e6c`
- `0x18001afc0`
- `0x18002f4c0`
- `0x18002f578`
- `0x18002f94c`
- `0x18002f9d4`
- `0x18002fa20`
- `0x180030700`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180006aff`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180006aff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180006ae4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180006ae4`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180006ac6`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180006ac6`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180006b3c`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180006d34`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180006b3c`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180006d34`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180006a7c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180006a7c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180006a18`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180006a18`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x180006a53`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x180006a53`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x180006a30`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x180006a30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800069c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800069c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d44`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180006c9f`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180006c9f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800069b0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800069b0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall tsched::SetJobFileSecurityByName(
        wchar_t *String2,
        const unsigned __int16 *a2,
        const WCHAR *a3,
        const unsigned __int16 *a4)
{
  signed int LastError; // eax
  unsigned int v6; // ebx
  SECURITY_INFORMATION v7; // ebx
  unsigned int v8; // edi
  unsigned int v9; // r8d
  unsigned int v10; // r9d
  HANDLE CurrentThread; // rax
  signed int v12; // eax
  void *FileSafe; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  void *v16; // r12
  int v17; // edx
  int v18; // r8d
  tsched *v19; // rcx
  unsigned int LastHrError; // eax
  int v21; // edx
  unsigned int v22; // ecx
  signed int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // r8
  unsigned int v26; // r14d
  signed int v27; // eax
  struct _SECURITY_ATTRIBUTES *PreviousState; // [rsp+20h] [rbp-79h]
  unsigned int ReturnLength; // [rsp+28h] [rbp-71h]
  unsigned int v31; // [rsp+30h] [rbp-69h]
  void *v32; // [rsp+38h] [rbp-61h]
  WORD pControl[2]; // [rsp+50h] [rbp-49h] BYREF
  WINBOOL bOwnerDefaulted; // [rsp+54h] [rbp-45h] BYREF
  WINBOOL bDaclPresent; // [rsp+58h] [rbp-41h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+60h] [rbp-39h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp-31h] BYREF
  PSID pGroup; // [rsp+70h] [rbp-29h] BYREF
  PSID pOwner; // [rsp+78h] [rbp-21h] BYREF
  ULONG SecurityDescriptorSize; // [rsp+80h] [rbp-19h] BYREF
  DWORD dwRevision; // [rsp+84h] [rbp-15h] BYREF
  PACL pSacl; // [rsp+88h] [rbp-11h] BYREF
  PACL pDacl; // [rsp+90h] [rbp-9h] BYREF
  __int128 v44; // [rsp+98h] [rbp-1h] BYREF
  _TOKEN_PRIVILEGES NewState; // [rsp+A8h] [rbp+Fh] BYREF

  SecurityDescriptor = 0;
  SecurityDescriptorSize = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(a3, 1u, &SecurityDescriptor, &SecurityDescriptorSize) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_56;
  }
  v7 = 0;
  bDaclPresent = 0;
  bOwnerDefaulted = 1;
  pOwner = 0;
  pGroup = 0;
  pDacl = 0;
  pSacl = 0;
  v8 = 917504;
  pControl[0] = 0;
  dwRevision = 0;
  GetSecurityDescriptorControl(SecurityDescriptor, pControl, &dwRevision);
  if ( GetSecurityDescriptorOwner(SecurityDescriptor, &pOwner, &bOwnerDefaulted) )
    v7 = pOwner != 0;
  if ( GetSecurityDescriptorGroup(SecurityDescriptor, &pGroup, &bOwnerDefaulted) && pGroup )
    v7 |= 2u;
  if ( GetSecurityDescriptorDacl(SecurityDescriptor, &bDaclPresent, &pDacl, &bOwnerDefaulted) && bDaclPresent )
  {
    if ( (pControl[0] & 0x1000) != 0 )
      v7 |= 0x80000004;
    else
      v7 |= 0x20000004u;
  }
  TokenHandle = 0;
  NewState = 0;
  if ( GetSecurityDescriptorSacl(SecurityDescriptor, &bDaclPresent, &pSacl, &bOwnerDefaulted) && bDaclPresent )
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0x28u, 1, &TokenHandle) )
    {
      NewState.PrivilegeCount = 1;
      NewState.Privileges[0].Attributes = 2;
      NewState.Privileges[0].Luid = (LUID)8LL;
      if ( !AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0, 0, 0) )
      {
        v12 = GetLastError();
        v6 = v12;
        if ( v12 > 0 )
          v6 = (unsigned __int16)v12 | 0x80070000;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_0318f2e21e573bf245f738540b7f5294_Traceguids, v6);
        }
LABEL_24:
        wmi::AutoHandle::Close((wmi::AutoHandle *)&TokenHandle);
        goto LABEL_56;
      }
    }
    v8 = 17694720;
    if ( (pControl[0] & 0x2000) != 0 )
      v7 |= 0x40000008u;
    else
      v7 |= 0x10000008u;
  }
  v44 = 0;
  FileSafe = tsched::CreateFileSafe(
               String2,
               (const unsigned __int16 *)v8,
               v9,
               v10,
               PreviousState,
               ReturnLength,
               v31,
               v32);
  v16 = FileSafe;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, v15, FileSafe);
  }
  tsched::JobsAutoHandle::Close((tsched::JobsAutoHandle *)&v44);
  *(_QWORD *)&v44 = v16;
  v19 = (tsched *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_Sq(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, v18, (_DWORD)String2, (char)v16);
  }
  if ( v16 == (void *)-1LL )
  {
    LastHrError = tsched::GetLastHrError(v19, v17);
    v6 = 0;
    if ( !tsched::IsErrorNotFound((tsched *)LastHrError, v21) )
      v6 = v22;
    tsched::JobsAutoHandle::Close((tsched::JobsAutoHandle *)&v44);
    goto LABEL_24;
  }
  *((_QWORD *)&v44 + 1) = String2;
  v23 = SetSecurityInfo(v16, SE_FILE_OBJECT, v7, pOwner, pGroup, pDacl, pSacl);
  v26 = v23;
  if ( v23 > 0 )
    v26 = (unsigned __int16)v23 | 0x80070000;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_qDqqqqD(*((_QWORD *)WPP_GLOBAL_Control + 2), v24, v25, v16, v7, pOwner, pGroup, pDacl, pSacl, v26);
  }
  if ( TokenHandle )
  {
    if ( NewState.PrivilegeCount )
    {
      NewState.Privileges[0].Attributes = 0;
      if ( !AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0, 0, 0) )
      {
        v27 = GetLastError();
        if ( v27 > 0 )
          v27 = (unsigned __int16)v27 | 0x80070000;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            WPP_0318f2e21e573bf245f738540b7f5294_Traceguids,
            (unsigned int)v27);
        }
      }
    }
  }
  tsched::JobsAutoHandle::Close((tsched::JobsAutoHandle *)&v44);
  wmi::AutoHandle::Close((wmi::AutoHandle *)&TokenHandle);
  v6 = v26;
LABEL_56:
  tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&SecurityDescriptor);
  return v6;
}

```

## disassembly

```asm
0x180006964  mov     [rsp-8+arg_8], rbx
0x180006969  push    rbp
0x18000696a  push    rsi
0x18000696b  push    rdi
0x18000696c  push    r12
0x18000696e  push    r13
0x180006970  push    r14
0x180006972  push    r15
0x180006974  lea     rbp, [rsp-27h]
0x180006979  sub     rsp, 0C0h
0x180006980  mov     rax, cs:__security_cookie
0x180006987  xor     rax, rsp
0x18000698a  mov     [rbp+57h+var_38], rax
0x18000698e  mov     rax, r8
0x180006991  mov     r14, rcx
0x180006994  xor     r13d, r13d
0x180006997  mov     [rbp+57h+SecurityDescriptor], r13
0x18000699b  mov     [rbp+57h+SecurityDescriptorSize], r13d
0x18000699f  lea     r9, [rbp+57h+SecurityDescriptorSize]; SecurityDescriptorSize
0x1800069a3  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1800069a7  lea     esi, [r13+1]
0x1800069ab  mov     edx, esi; StringSDRevision
0x1800069ad  mov     rcx, rax; StringSecurityDescriptor
0x1800069b0  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800069b7  nop     dword ptr [rax+rax+00h]
0x1800069bc  test    eax, eax
0x1800069be  jnz     short loc_1800069E4
0x1800069c0  call    cs:__imp_GetLastError
0x1800069c7  nop     dword ptr [rax+rax+00h]
0x1800069cc  mov     ebx, eax
0x1800069ce  test    eax, eax
0x1800069d0  jle     loc_180006D9F
0x1800069d6  movzx   ebx, ax
0x1800069d9  or      ebx, 80070000h
0x1800069df  jmp     loc_180006D9F
0x1800069e4  mov     ebx, r13d
0x1800069e7  mov     [rbp+57h+bDaclPresent], r13d
0x1800069eb  mov     [rbp+57h+bOwnerDefaulted], esi
0x1800069ee  mov     [rbp+57h+pOwner], r13
0x1800069f2  mov     [rbp+57h+pGroup], r13
0x1800069f6  mov     [rbp+57h+pDacl], r13
0x1800069fa  mov     [rbp+57h+pSacl], r13
0x1800069fe  mov     edi, 0E0000h
0x180006a03  mov     [rbp+57h+pControl], r13w
0x180006a08  mov     [rbp+57h+dwRevision], r13d
0x180006a0c  lea     r8, [rbp+57h+dwRevision]; lpdwRevision
0x180006a10  lea     rdx, [rbp+57h+pControl]; pControl
0x180006a14  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x180006a18  call    cs:__imp_GetSecurityDescriptorControl
0x180006a1f  nop     dword ptr [rax+rax+00h]
0x180006a24  lea     r8, [rbp+57h+bOwnerDefaulted]; lpbOwnerDefaulted
0x180006a28  lea     rdx, [rbp+57h+pOwner]; pOwner
0x180006a2c  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x180006a30  call    cs:__imp_GetSecurityDescriptorOwner
0x180006a37  nop     dword ptr [rax+rax+00h]
0x180006a3c  test    eax, eax
0x180006a3e  jz      short loc_180006A47
0x180006a40  cmp     [rbp+57h+pOwner], r13
0x180006a44  cmovnz  ebx, esi
0x180006a47  lea     r8, [rbp+57h+bOwnerDefaulted]; lpbGroupDefaulted
0x180006a4b  lea     rdx, [rbp+57h+pGroup]; pGroup
0x180006a4f  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x180006a53  call    cs:__imp_GetSecurityDescriptorGroup
0x180006a5a  nop     dword ptr [rax+rax+00h]
0x180006a5f  test    eax, eax
0x180006a61  jz      short loc_180006A6C
0x180006a63  cmp     [rbp+57h+pGroup], r13
0x180006a67  jz      short loc_180006A6C
0x180006a69  or      ebx, 2
0x180006a6c  lea     r9, [rbp+57h+bOwnerDefaulted]; lpbDaclDefaulted
0x180006a70  lea     r8, [rbp+57h+pDacl]; pDacl
0x180006a74  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x180006a78  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x180006a7c  call    cs:__imp_GetSecurityDescriptorDacl
0x180006a83  nop     dword ptr [rax+rax+00h]
0x180006a88  test    eax, eax
0x180006a8a  jz      short loc_180006AAB
0x180006a8c  cmp     [rbp+57h+bDaclPresent], r13d
0x180006a90  jz      short loc_180006AAB
0x180006a92  mov     eax, 1000h
0x180006a97  test    [rbp+57h+pControl], ax
0x180006a9b  jz      short loc_180006AA5
0x180006a9d  or      ebx, 80000004h
0x180006aa3  jmp     short loc_180006AAB
0x180006aa5  or      ebx, 20000004h
0x180006aab  mov     [rbp+57h+TokenHandle], r13
0x180006aaf  xorps   xmm0, xmm0
0x180006ab2  movups  xmmword ptr [rbp+57h+NewState.PrivilegeCount], xmm0
0x180006ab6  lea     r9, [rbp+57h+bOwnerDefaulted]; lpbSaclDefaulted
0x180006aba  lea     r8, [rbp+57h+pSacl]; pSacl
0x180006abe  lea     rdx, [rbp+57h+bDaclPresent]; lpbSaclPresent
0x180006ac2  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x180006ac6  call    cs:__imp_GetSecurityDescriptorSacl
0x180006acd  nop     dword ptr [rax+rax+00h]
0x180006ad2  test    eax, eax
0x180006ad4  jz      loc_180006BCF
0x180006ada  cmp     [rbp+57h+bDaclPresent], r13d
0x180006ade  jz      loc_180006BCF
0x180006ae4  call    cs:__imp_GetCurrentThread
0x180006aeb  nop     dword ptr [rax+rax+00h]
0x180006af0  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180006af4  mov     r8d, esi; OpenAsSelf
0x180006af7  mov     edx, 28h ; '('; DesiredAccess
0x180006afc  mov     rcx, rax; ThreadHandle
0x180006aff  call    cs:__imp_OpenThreadToken
0x180006b06  nop     dword ptr [rax+rax+00h]
0x180006b0b  test    eax, eax
0x180006b0d  jz      loc_180006BB1
0x180006b13  mov     [rbp+57h+NewState.PrivilegeCount], esi
0x180006b16  mov     [rbp+57h+NewState.Privileges.Attributes], 2
0x180006b1d  mov     qword ptr [rbp+57h+NewState.Privileges.Luid.LowPart], 8
0x180006b25  mov     [rsp+0F0h+ReturnLength], r13; ReturnLength
0x180006b2a  mov     [rsp+0F0h+PreviousState], r13; PreviousState
0x180006b2f  xor     r9d, r9d; BufferLength
0x180006b32  lea     r8, [rbp+57h+NewState]; NewState
0x180006b36  xor     edx, edx; DisableAllPrivileges
0x180006b38  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180006b3c  call    cs:__imp_AdjustTokenPrivileges
0x180006b43  nop     dword ptr [rax+rax+00h]
0x180006b48  test    eax, eax
0x180006b4a  jnz     short loc_180006BB1
0x180006b4c  call    cs:__imp_GetLastError
0x180006b53  nop     dword ptr [rax+rax+00h]
0x180006b58  mov     ebx, eax
0x180006b5a  test    eax, eax
0x180006b5c  jle     short loc_180006B67
0x180006b5e  movzx   ebx, ax
0x180006b61  or      ebx, 80070000h
0x180006b67  lea     r15, WPP_GLOBAL_Control
0x180006b6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b75  cmp     rcx, r15
0x180006b78  jz      short loc_180006BA3
0x180006b7a  mov     esi, 10000h
0x180006b7f  test    [rcx+1Ch], esi
0x180006b82  jz      short loc_180006BA3
0x180006b84  cmp     byte ptr [rcx+19h], 2
0x180006b88  jb      short loc_180006BA3
0x180006b8a  mov     edx, 0Ah
0x180006b8f  mov     r9d, ebx
0x180006b92  lea     r8, WPP_0318f2e21e573bf245f738540b7f5294_Traceguids
0x180006b99  mov     rcx, [rcx+10h]
0x180006b9d  call    WPP_SF_d
0x180006ba2  nop
0x180006ba3  lea     rcx, [rbp+57h+TokenHandle]; this
0x180006ba7  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x180006bac  jmp     loc_180006D9F
0x180006bb1  mov     edi, 10E0000h
0x180006bb6  mov     eax, 2000h
0x180006bbb  test    [rbp+57h+pControl], ax
0x180006bbf  jz      short loc_180006BC9
0x180006bc1  or      ebx, 40000008h
0x180006bc7  jmp     short loc_180006BCF
0x180006bc9  or      ebx, 10000008h
0x180006bcf  xorps   xmm0, xmm0
0x180006bd2  movdqu  [rbp+57h+var_58], xmm0
0x180006bd7  mov     edx, edi; unsigned __int16 *
0x180006bd9  mov     rcx, r14; String2
0x180006bdc  call    ?CreateFileSafe@tsched@@YAPEAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z; tsched::CreateFileSafe(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)
0x180006be1  mov     r12, rax
0x180006be4  lea     r15, WPP_GLOBAL_Control
0x180006beb  mov     esi, 10000h
0x180006bf0  mov     rcx, cs:WPP_GLOBAL_Control
0x180006bf7  cmp     rcx, r15
0x180006bfa  jz      short loc_180006C13
0x180006bfc  test    [rcx+1Ch], esi
0x180006bff  jz      short loc_180006C13
0x180006c01  cmp     byte ptr [rcx+19h], 4
0x180006c05  jb      short loc_180006C13
0x180006c07  mov     r9, rax
0x180006c0a  mov     rcx, [rcx+10h]
0x180006c0e  call    WPP_SF_q
0x180006c13  lea     rcx, [rbp+57h+var_58]; this
0x180006c17  call    ?Close@JobsAutoHandle@tsched@@QEAAXXZ; tsched::JobsAutoHandle::Close(void)
0x180006c1c  mov     qword ptr [rbp+57h+var_58], r12
0x180006c20  mov     rcx, cs:WPP_GLOBAL_Control
0x180006c27  cmp     rcx, r15
0x180006c2a  jz      short loc_180006C48
0x180006c2c  test    [rcx+1Ch], esi
0x180006c2f  jz      short loc_180006C48
0x180006c31  cmp     byte ptr [rcx+19h], 4
0x180006c35  jb      short loc_180006C48
0x180006c37  mov     [rsp+0F0h+PreviousState], r12
0x180006c3c  mov     r9, r14
0x180006c3f  mov     rcx, [rcx+10h]
0x180006c43  call    WPP_SF_Sq
0x180006c48  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x180006c4c  jnz     short loc_180006C71
0x180006c4e  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x180006c53  mov     ecx, eax; this
0x180006c55  call    ?IsErrorNotFound@tsched@@YA_NJ@Z; tsched::IsErrorNotFound(long)
0x180006c5a  nop
0x180006c5b  mov     ebx, r13d
0x180006c5e  test    al, al
0x180006c60  cmovz   ebx, ecx
0x180006c63  lea     rcx, [rbp+57h+var_58]; this
0x180006c67  call    ?Close@JobsAutoHandle@tsched@@QEAAXXZ; tsched::JobsAutoHandle::Close(void)
0x180006c6c  jmp     loc_180006BA3
0x180006c71  mov     qword ptr [rbp+57h+var_58+8], r14
0x180006c75  mov     rax, [rbp+57h+pSacl]
0x180006c79  mov     rcx, [rbp+57h+pDacl]
0x180006c7d  mov     r8, [rbp+57h+pGroup]
0x180006c81  mov     [rsp+0F0h+var_C0], rax; pSacl
0x180006c86  mov     [rsp+0F0h+ReturnLength], rcx; pDacl
0x180006c8b  mov     [rsp+0F0h+PreviousState], r8; psidGroup
0x180006c90  mov     r9, [rbp+57h+pOwner]; psidOwner
0x180006c94  mov     r8d, ebx; SecurityInfo
0x180006c97  mov     edx, 1; ObjectType
0x180006c9c  mov     rcx, r12; handle
0x180006c9f  call    cs:__imp_SetSecurityInfo
0x180006ca6  nop     dword ptr [rax+rax+00h]
0x180006cab  mov     r14d, eax
0x180006cae  mov     edi, 80070000h
0x180006cb3  test    eax, eax
0x180006cb5  jle     short loc_180006CBE
0x180006cb7  movzx   r14d, ax
0x180006cbb  or      r14d, edi
0x180006cbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180006cc5  cmp     rcx, r15
0x180006cc8  jz      short loc_180006D0E
0x180006cca  test    [rcx+1Ch], esi
0x180006ccd  jz      short loc_180006D0E
0x180006ccf  cmp     byte ptr [rcx+19h], 4
0x180006cd3  jb      short loc_180006D0E
0x180006cd5  mov     [rsp+0F0h+var_A8], r14d
0x180006cda  mov     rax, [rbp+57h+pSacl]
0x180006cde  mov     [rsp+0F0h+var_B0], rax
0x180006ce3  mov     rax, [rbp+57h+pDacl]
0x180006ce7  mov     [rsp+0F0h+var_B8], rax
0x180006cec  mov     rax, [rbp+57h+pGroup]
0x180006cf0  mov     [rsp+0F0h+var_C0], rax
0x180006cf5  mov     rax, [rbp+57h+pOwner]
0x180006cf9  mov     [rsp+0F0h+ReturnLength], rax
0x180006cfe  mov     dword ptr [rsp+0F0h+PreviousState], ebx
0x180006d02  mov     r9, r12
0x180006d05  mov     rcx, [rcx+10h]
0x180006d09  call    WPP_SF_qDqqqqD
0x180006d0e  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180006d12  test    rcx, rcx
0x180006d15  jz      short loc_180006D89
0x180006d17  cmp     [rbp+57h+NewState.PrivilegeCount], r13d
0x180006d1b  jz      short loc_180006D89
0x180006d1d  mov     [rbp+57h+NewState.Privileges.Attributes], r13d
0x180006d21  mov     [rsp+0F0h+ReturnLength], r13; ReturnLength
0x180006d26  mov     [rsp+0F0h+PreviousState], r13; PreviousState
0x180006d2b  xor     r9d, r9d; BufferLength
0x180006d2e  lea     r8, [rbp+57h+NewState]; NewState
0x180006d32  xor     edx, edx; DisableAllPrivileges
0x180006d34  call    cs:__imp_AdjustTokenPrivileges
0x180006d3b  nop     dword ptr [rax+rax+00h]
0x180006d40  test    eax, eax
0x180006d42  jnz     short loc_180006D89
0x180006d44  call    cs:__imp_GetLastError
0x180006d4b  nop     dword ptr [rax+rax+00h]
0x180006d50  test    eax, eax
0x180006d52  jle     short loc_180006D59
0x180006d54  movzx   eax, ax
0x180006d57  or      eax, edi
0x180006d59  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d60  cmp     rcx, r15
0x180006d63  jz      short loc_180006D89
0x180006d65  test    [rcx+1Ch], esi
0x180006d68  jz      short loc_180006D89
0x180006d6a  cmp     byte ptr [rcx+19h], 2
0x180006d6e  jb      short loc_180006D89
0x180006d70  mov     edx, 0Dh
0x180006d75  mov     r9d, eax
0x180006d78  lea     r8, WPP_0318f2e21e573bf245f738540b7f5294_Traceguids
0x180006d7f  mov     rcx, [rcx+10h]
0x180006d83  call    WPP_SF_d
0x180006d88  nop
0x180006d89  lea     rcx, [rbp+57h+var_58]; this
0x180006d8d  call    ?Close@JobsAutoHandle@tsched@@QEAAXXZ; tsched::JobsAutoHandle::Close(void)
0x180006d92  nop
0x180006d93  lea     rcx, [rbp+57h+TokenHandle]; this
0x180006d97  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x180006d9c  mov     ebx, r14d
0x180006d9f  lea     rcx, [rbp+57h+SecurityDescriptor]
0x180006da3  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180006da8  mov     eax, ebx
0x180006daa  mov     rcx, [rbp+57h+var_38]
0x180006dae  xor     rcx, rsp; StackCookie
0x180006db1  call    __security_check_cookie
0x180006db6  mov     rbx, [rsp+0F0h+arg_8]
0x180006dbe  add     rsp, 0C0h
0x180006dc5  pop     r15
0x180006dc7  pop     r14
0x180006dc9  pop     r13
0x180006dcb  pop     r12
0x180006dcd  pop     rdi
0x180006dce  pop     rsi
0x180006dcf  pop     rbp
0x180006dd0  retn
```
