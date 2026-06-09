# tsched::SetJobFileSecurityByName(ushort const *,int,ushort const *)

- ea: `0x18007a26c`
- end: `0x18007a678`
- name: `?SetJobFileSecurityByName@tsched@@YAJPEBGH0@Z`
- size: `1036`
- prototype: `__int64 __fastcall(wchar_t *String2, const unsigned __int16 *, const WCHAR *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180029978`
- `0x180051ed0`

## callees

- `0x180025040`
- `0x1800276c0`
- `0x180039d00`
- `0x18003f270`
- `0x18003f3c0`
- `0x180052584`
- `0x180054084`
- `0x180069d84`
- `0x18007a26c`
- `0x18007a680`
- `0x18007e6d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a2c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a41c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a5f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a2c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a41c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a5f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007a3c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007a3c5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18007a3da`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18007a3da`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18007a346`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18007a346`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18007a316`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18007a316`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18007a328`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18007a328`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18007a369`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18007a369`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18007a3ad`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18007a3ad`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18007a412`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18007a5e9`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18007a412`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18007a5e9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18007a2b9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18007a2b9`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18007a55d`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18007a55d`

## pseudocode

```c
__int64 __fastcall tsched::SetJobFileSecurityByName(
        wchar_t *String2,
        const unsigned __int16 *a2,
        const WCHAR *a3,
        const unsigned __int16 *a4)
{
  signed int LastError; // eax
  unsigned int LastHrError; // ebx
  SECURITY_INFORMATION v7; // ebx
  unsigned int v8; // edi
  HANDLE CurrentThread; // rax
  signed int v10; // eax
  __int64 FileSafe; // rax
  int v12; // edx
  tsched *v13; // rcx
  HANDLE v14; // r12
  signed int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // r8
  unsigned int v18; // esi
  signed int v19; // eax
  struct _SECURITY_ATTRIBUTES *PreviousState; // [rsp+20h] [rbp-79h]
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
  HANDLE handle[2]; // [rsp+98h] [rbp-1h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+A8h] [rbp+Fh] BYREF

  SecurityDescriptor = 0;
  SecurityDescriptorSize = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(a3, 1u, &SecurityDescriptor, &SecurityDescriptorSize) )
  {
    LastError = GetLastError();
    LastHrError = LastError;
    if ( LastError > 0 )
      LastHrError = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_50;
  }
  bDaclPresent = 0;
  v7 = 0;
  bOwnerDefaulted = 1;
  pOwner = 0;
  v8 = 917504;
  pGroup = 0;
  pDacl = 0;
  pSacl = 0;
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
        v10 = GetLastError();
        LastHrError = v10;
        if ( v10 > 0 )
          LastHrError = (unsigned __int16)v10 | 0x80070000;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            10,
            WPP_0318f2e21e573bf245f738540b7f5294_Traceguids,
            LastHrError);
        }
        goto LABEL_24;
      }
    }
    v8 = 17694720;
    if ( (pControl[0] & 0x2000) != 0 )
      v7 |= 0x40000008u;
    else
      v7 |= 0x10000008u;
  }
  LODWORD(PreviousState) = 3;
  *(_OWORD *)handle = 0;
  FileSafe = tsched::CreateFileSafe(String2, (const unsigned __int16 *)v8, 1u, 0, PreviousState, 0x2000000u);
  tsched::JobsAutoHandle::operator=(handle, FileSafe);
  v13 = (tsched *)WPP_GLOBAL_Control;
  v14 = handle[0];
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_Sq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      (unsigned int)WPP_0318f2e21e573bf245f738540b7f5294_Traceguids,
      (_DWORD)String2,
      (char)handle[0]);
  }
  if ( v14 == (HANDLE)-1LL )
  {
    LastHrError = tsched::GetLastHrError(v13, v12);
    tsched::JobsAutoHandle::Close((tsched::JobsAutoHandle *)handle);
LABEL_24:
    wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&TokenHandle);
    goto LABEL_50;
  }
  handle[1] = String2;
  v15 = SetSecurityInfo(v14, SE_FILE_OBJECT, v7, pOwner, pGroup, pDacl, pSacl);
  v18 = v15;
  if ( v15 > 0 )
    v18 = (unsigned __int16)v15 | 0x80070000;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_qDqqqqD(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, v17, v14, v7, pOwner, pGroup, pDacl, pSacl, v18);
  }
  if ( TokenHandle )
  {
    if ( NewState.PrivilegeCount )
    {
      NewState.Privileges[0].Attributes = 0;
      if ( !AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0, 0, 0) )
      {
        v19 = GetLastError();
        if ( v19 > 0 )
          v19 = (unsigned __int16)v19 | 0x80070000;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            WPP_0318f2e21e573bf245f738540b7f5294_Traceguids,
            (unsigned int)v19);
        }
      }
    }
  }
  tsched::JobsAutoHandle::Close((tsched::JobsAutoHandle *)handle);
  wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&TokenHandle);
  LastHrError = v18;
LABEL_50:
  tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&SecurityDescriptor);
  return LastHrError;
}

```

## disassembly

```asm
0x18007a26c  mov     [rsp-8+arg_8], rbx
0x18007a271  push    rbp
0x18007a272  push    rsi
0x18007a273  push    rdi
0x18007a274  push    r12
0x18007a276  push    r13
0x18007a278  push    r14
0x18007a27a  push    r15
0x18007a27c  lea     rbp, [rsp-27h]
0x18007a281  sub     rsp, 0C0h
0x18007a288  mov     rax, cs:__security_cookie
0x18007a28f  xor     rax, rsp
0x18007a292  mov     [rbp+57h+var_38], rax
0x18007a296  xor     r13d, r13d
0x18007a299  lea     r9, [rbp+57h+SecurityDescriptorSize]; SecurityDescriptorSize
0x18007a29d  mov     rax, r8
0x18007a2a0  mov     [rbp+57h+SecurityDescriptor], r13
0x18007a2a4  mov     rsi, rcx
0x18007a2a7  mov     [rbp+57h+SecurityDescriptorSize], r13d
0x18007a2ab  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18007a2af  mov     rcx, rax; StringSecurityDescriptor
0x18007a2b2  lea     r14d, [r13+1]
0x18007a2b6  mov     edx, r14d; StringSDRevision
0x18007a2b9  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18007a2bf  test    eax, eax
0x18007a2c1  jnz     short loc_18007A2E1
0x18007a2c3  call    cs:__imp_GetLastError
0x18007a2c9  mov     ebx, eax
0x18007a2cb  test    eax, eax
0x18007a2cd  jle     loc_18007A646
0x18007a2d3  movzx   ebx, ax
0x18007a2d6  or      ebx, 80070000h
0x18007a2dc  jmp     loc_18007A646
0x18007a2e1  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x18007a2e5  lea     r8, [rbp+57h+dwRevision]; lpdwRevision
0x18007a2e9  lea     rdx, [rbp+57h+pControl]; pControl
0x18007a2ed  mov     [rbp+57h+bDaclPresent], r13d
0x18007a2f1  mov     ebx, r13d
0x18007a2f4  mov     [rbp+57h+bOwnerDefaulted], r14d
0x18007a2f8  mov     [rbp+57h+pOwner], r13
0x18007a2fc  mov     edi, 0E0000h
0x18007a301  mov     [rbp+57h+pGroup], r13
0x18007a305  mov     [rbp+57h+pDacl], r13
0x18007a309  mov     [rbp+57h+pSacl], r13
0x18007a30d  mov     [rbp+57h+pControl], r13w
0x18007a312  mov     [rbp+57h+dwRevision], r13d
0x18007a316  call    cs:__imp_GetSecurityDescriptorControl
0x18007a31c  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x18007a320  lea     r8, [rbp+57h+bOwnerDefaulted]; lpbOwnerDefaulted
0x18007a324  lea     rdx, [rbp+57h+pOwner]; pOwner
0x18007a328  call    cs:__imp_GetSecurityDescriptorOwner
0x18007a32e  test    eax, eax
0x18007a330  jz      short loc_18007A33A
0x18007a332  cmp     [rbp+57h+pOwner], r13
0x18007a336  cmovnz  ebx, r14d
0x18007a33a  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x18007a33e  lea     r8, [rbp+57h+bOwnerDefaulted]; lpbGroupDefaulted
0x18007a342  lea     rdx, [rbp+57h+pGroup]; pGroup
0x18007a346  call    cs:__imp_GetSecurityDescriptorGroup
0x18007a34c  test    eax, eax
0x18007a34e  jz      short loc_18007A359
0x18007a350  cmp     [rbp+57h+pGroup], r13
0x18007a354  jz      short loc_18007A359
0x18007a356  or      ebx, 2
0x18007a359  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x18007a35d  lea     r9, [rbp+57h+bOwnerDefaulted]; lpbDaclDefaulted
0x18007a361  lea     r8, [rbp+57h+pDacl]; pDacl
0x18007a365  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x18007a369  call    cs:__imp_GetSecurityDescriptorDacl
0x18007a36f  test    eax, eax
0x18007a371  jz      short loc_18007A392
0x18007a373  cmp     [rbp+57h+bDaclPresent], r13d
0x18007a377  jz      short loc_18007A392
0x18007a379  mov     eax, 1000h
0x18007a37e  test    [rbp+57h+pControl], ax
0x18007a382  jz      short loc_18007A38C
0x18007a384  or      ebx, 80000004h
0x18007a38a  jmp     short loc_18007A392
0x18007a38c  or      ebx, 20000004h
0x18007a392  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x18007a396  lea     r9, [rbp+57h+bOwnerDefaulted]; lpbSaclDefaulted
0x18007a39a  xorps   xmm0, xmm0
0x18007a39d  mov     [rbp+57h+TokenHandle], r13
0x18007a3a1  lea     r8, [rbp+57h+pSacl]; pSacl
0x18007a3a5  lea     rdx, [rbp+57h+bDaclPresent]; lpbSaclPresent
0x18007a3a9  movups  xmmword ptr [rbp+57h+NewState.PrivilegeCount], xmm0
0x18007a3ad  call    cs:__imp_GetSecurityDescriptorSacl
0x18007a3b3  test    eax, eax
0x18007a3b5  jz      loc_18007A49A
0x18007a3bb  cmp     [rbp+57h+bDaclPresent], r13d
0x18007a3bf  jz      loc_18007A49A
0x18007a3c5  call    cs:__imp_GetCurrentThread
0x18007a3cb  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18007a3cf  mov     r8d, r14d; OpenAsSelf
0x18007a3d2  mov     rcx, rax; ThreadHandle
0x18007a3d5  mov     edx, 28h ; '('; DesiredAccess
0x18007a3da  call    cs:__imp_OpenThreadToken
0x18007a3e0  test    eax, eax
0x18007a3e2  jz      loc_18007A47C
0x18007a3e8  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18007a3ec  lea     r8, [rbp+57h+NewState]; NewState
0x18007a3f0  mov     [rsp+0F0h+ReturnLength], r13; ReturnLength
0x18007a3f5  xor     r9d, r9d; BufferLength
0x18007a3f8  xor     edx, edx; DisableAllPrivileges
0x18007a3fa  mov     [rsp+0F0h+PreviousState], r13; PreviousState
0x18007a3ff  mov     [rbp+57h+NewState.PrivilegeCount], r14d
0x18007a403  mov     [rbp+57h+NewState.Privileges.Attributes], 2
0x18007a40a  mov     qword ptr [rbp+57h+NewState.Privileges.Luid.LowPart], 8
0x18007a412  call    cs:__imp_AdjustTokenPrivileges
0x18007a418  test    eax, eax
0x18007a41a  jnz     short loc_18007A47C
0x18007a41c  call    cs:__imp_GetLastError
0x18007a422  mov     ebx, eax
0x18007a424  test    eax, eax
0x18007a426  jle     short loc_18007A431
0x18007a428  movzx   ebx, ax
0x18007a42b  or      ebx, 80070000h
0x18007a431  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a438  lea     r15, WPP_GLOBAL_Control
0x18007a43f  cmp     rcx, r15
0x18007a442  jz      short loc_18007A46E
0x18007a444  mov     r14d, 10000h
0x18007a44a  test    [rcx+1Ch], r14d
0x18007a44e  jz      short loc_18007A46E
0x18007a450  cmp     byte ptr [rcx+19h], 2
0x18007a454  jb      short loc_18007A46E
0x18007a456  mov     rcx, [rcx+10h]
0x18007a45a  lea     r8, WPP_0318f2e21e573bf245f738540b7f5294_Traceguids
0x18007a461  mov     edx, 0Ah
0x18007a466  mov     r9d, ebx
0x18007a469  call    WPP_SF_d
0x18007a46e  lea     rcx, [rbp+57h+TokenHandle]; this
0x18007a472  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x18007a477  jmp     loc_18007A646
0x18007a47c  mov     eax, 2000h
0x18007a481  mov     edi, 10E0000h
0x18007a486  test    [rbp+57h+pControl], ax
0x18007a48a  jz      short loc_18007A494
0x18007a48c  or      ebx, 40000008h
0x18007a492  jmp     short loc_18007A49A
0x18007a494  or      ebx, 10000008h
0x18007a49a  xorps   xmm0, xmm0
0x18007a49d  mov     dword ptr [rsp+0F0h+ReturnLength], 2000000h; unsigned int
0x18007a4a5  xor     r9d, r9d; unsigned int
0x18007a4a8  mov     dword ptr [rsp+0F0h+PreviousState], 3; struct _SECURITY_ATTRIBUTES *
0x18007a4b0  mov     r8d, r14d; unsigned int
0x18007a4b3  mov     edx, edi; unsigned __int16 *
0x18007a4b5  mov     rcx, rsi; String2
0x18007a4b8  movdqu  xmmword ptr [rbp+57h+handle], xmm0
0x18007a4bd  call    ?CreateFileSafe@tsched@@YAPEAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z; tsched::CreateFileSafe(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)
0x18007a4c2  mov     rdx, rax
0x18007a4c5  lea     rcx, [rbp+57h+handle]
0x18007a4c9  call    ??4JobsAutoHandle@tsched@@QEAAAEAV01@PEAX@Z; tsched::JobsAutoHandle::operator=(void *)
0x18007a4ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a4d5  lea     r15, WPP_GLOBAL_Control
0x18007a4dc  mov     r12, [rbp+57h+handle]
0x18007a4e0  mov     r14d, 10000h
0x18007a4e6  cmp     rcx, r15
0x18007a4e9  jz      short loc_18007A514
0x18007a4eb  test    [rcx+1Ch], r14d
0x18007a4ef  jz      short loc_18007A514
0x18007a4f1  cmp     byte ptr [rcx+19h], 4
0x18007a4f5  jb      short loc_18007A514
0x18007a4f7  mov     rcx, [rcx+10h]
0x18007a4fb  lea     r8, WPP_0318f2e21e573bf245f738540b7f5294_Traceguids
0x18007a502  mov     edx, 0Bh
0x18007a507  mov     [rsp+0F0h+PreviousState], r12
0x18007a50c  mov     r9, rsi
0x18007a50f  call    WPP_SF_Sq
0x18007a514  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x18007a518  jnz     short loc_18007A52F
0x18007a51a  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x18007a51f  lea     rcx, [rbp+57h+handle]; this
0x18007a523  mov     ebx, eax
0x18007a525  call    ?Close@JobsAutoHandle@tsched@@QEAAXXZ; tsched::JobsAutoHandle::Close(void)
0x18007a52a  jmp     loc_18007A46E
0x18007a52f  mov     rcx, [rbp+57h+pDacl]
0x18007a533  mov     edx, 1; ObjectType
0x18007a538  mov     r8, [rbp+57h+pGroup]
0x18007a53c  mov     rax, [rbp+57h+pSacl]
0x18007a540  mov     r9, [rbp+57h+pOwner]; psidOwner
0x18007a544  mov     [rsp+0F0h+var_C0], rax; pSacl
0x18007a549  mov     [rsp+0F0h+ReturnLength], rcx; pDacl
0x18007a54e  mov     rcx, r12; handle
0x18007a551  mov     [rsp+0F0h+PreviousState], r8; psidGroup
0x18007a556  mov     r8d, ebx; SecurityInfo
0x18007a559  mov     [rbp+57h+handle+8], rsi
0x18007a55d  call    cs:__imp_SetSecurityInfo
0x18007a563  mov     esi, eax
0x18007a565  mov     edi, 80070000h
0x18007a56a  test    eax, eax
0x18007a56c  jle     short loc_18007A573
0x18007a56e  movzx   esi, ax
0x18007a571  or      esi, edi
0x18007a573  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a57a  cmp     rcx, r15
0x18007a57d  jz      short loc_18007A5C3
0x18007a57f  test    [rcx+1Ch], r14d
0x18007a583  jz      short loc_18007A5C3
0x18007a585  cmp     byte ptr [rcx+19h], 4
0x18007a589  jb      short loc_18007A5C3
0x18007a58b  mov     rax, [rbp+57h+pSacl]
0x18007a58f  mov     r9, r12
0x18007a592  mov     rcx, [rcx+10h]
0x18007a596  mov     [rsp+0F0h+var_A8], esi
0x18007a59a  mov     [rsp+0F0h+var_B0], rax
0x18007a59f  mov     rax, [rbp+57h+pDacl]
0x18007a5a3  mov     [rsp+0F0h+var_B8], rax
0x18007a5a8  mov     rax, [rbp+57h+pGroup]
0x18007a5ac  mov     [rsp+0F0h+var_C0], rax
0x18007a5b1  mov     rax, [rbp+57h+pOwner]
0x18007a5b5  mov     [rsp+0F0h+ReturnLength], rax
0x18007a5ba  mov     dword ptr [rsp+0F0h+PreviousState], ebx
0x18007a5be  call    WPP_SF_qDqqqqD
0x18007a5c3  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18007a5c7  test    rcx, rcx
0x18007a5ca  jz      short loc_18007A632
0x18007a5cc  cmp     [rbp+57h+NewState.PrivilegeCount], r13d
0x18007a5d0  jz      short loc_18007A632
0x18007a5d2  mov     [rsp+0F0h+ReturnLength], r13; ReturnLength
0x18007a5d7  lea     r8, [rbp+57h+NewState]; NewState
0x18007a5db  xor     r9d, r9d; BufferLength
0x18007a5de  mov     [rsp+0F0h+PreviousState], r13; PreviousState
0x18007a5e3  xor     edx, edx; DisableAllPrivileges
0x18007a5e5  mov     [rbp+57h+NewState.Privileges.Attributes], r13d
0x18007a5e9  call    cs:__imp_AdjustTokenPrivileges
0x18007a5ef  test    eax, eax
0x18007a5f1  jnz     short loc_18007A632
0x18007a5f3  call    cs:__imp_GetLastError
0x18007a5f9  test    eax, eax
0x18007a5fb  jle     short loc_18007A602
0x18007a5fd  movzx   eax, ax
0x18007a600  or      eax, edi
0x18007a602  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a609  cmp     rcx, r15
0x18007a60c  jz      short loc_18007A632
0x18007a60e  test    [rcx+1Ch], r14d
0x18007a612  jz      short loc_18007A632
0x18007a614  cmp     byte ptr [rcx+19h], 2
0x18007a618  jb      short loc_18007A632
0x18007a61a  mov     rcx, [rcx+10h]
0x18007a61e  lea     r8, WPP_0318f2e21e573bf245f738540b7f5294_Traceguids
0x18007a625  mov     edx, 0Dh
0x18007a62a  mov     r9d, eax
0x18007a62d  call    WPP_SF_d
0x18007a632  lea     rcx, [rbp+57h+handle]; this
0x18007a636  call    ?Close@JobsAutoHandle@tsched@@QEAAXXZ; tsched::JobsAutoHandle::Close(void)
0x18007a63b  lea     rcx, [rbp+57h+TokenHandle]; this
0x18007a63f  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x18007a644  mov     ebx, esi
0x18007a646  lea     rcx, [rbp+57h+SecurityDescriptor]
0x18007a64a  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x18007a64f  mov     eax, ebx
0x18007a651  mov     rcx, [rbp+57h+var_38]
0x18007a655  xor     rcx, rsp; StackCookie
0x18007a658  call    __security_check_cookie
0x18007a65d  mov     rbx, [rsp+0F0h+arg_8]
0x18007a665  add     rsp, 0C0h
0x18007a66c  pop     r15
0x18007a66e  pop     r14
0x18007a670  pop     r13
0x18007a672  pop     r12
0x18007a674  pop     rdi
0x18007a675  pop     rsi
0x18007a676  pop     rbp
0x18007a677  retn
```
