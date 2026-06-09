# tsched::SetJobFileSecurityByName(ushort const *,int,ushort const *)

- ea: `0x18007e438`
- end: `0x18007e899`
- name: `?SetJobFileSecurityByName@tsched@@YAJPEBGH0@Z`
- size: `1121`
- prototype: `__int64 __fastcall(wchar_t *String2, const unsigned __int16 *, int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180023c4c`
- `0x180054550`

## callees

- `0x18001fe10`
- `0x1800229a0`
- `0x180024730`
- `0x180040bf0`
- `0x180040dd0`
- `0x180054c80`
- `0x180056954`
- `0x18006d1c4`
- `0x18007e438`
- `0x18007e8a0`
- `0x180082a40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e495`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e624`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e80d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e495`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e624`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e80d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007e5bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007e5bb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18007e5d6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18007e5d6`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18007e52a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18007e52a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18007e4ee`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18007e4ee`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18007e506`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18007e506`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18007e553`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18007e553`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18007e59d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18007e59d`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18007e614`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18007e7fd`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18007e614`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18007e7fd`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18007e485`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18007e485`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18007e76b`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18007e76b`

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
  void *FileSafe; // rax
  int v12; // edx
  tsched *v13; // rcx
  HANDLE v14; // r12
  signed int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // r8
  unsigned int v18; // esi
  signed int v19; // eax
  struct _SECURITY_ATTRIBUTES *PreviousState; // [rsp+20h] [rbp-79h]
  unsigned int v22; // [rsp+30h] [rbp-69h]
  void *v23; // [rsp+38h] [rbp-61h]
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
  FileSafe = tsched::CreateFileSafe(String2, (const unsigned __int16 *)v8, 1u, 0, PreviousState, 0x2000000u, v22, v23);
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
0x18007e438  mov     [rsp-8+arg_8], rbx
0x18007e43d  push    rbp
0x18007e43e  push    rsi
0x18007e43f  push    rdi
0x18007e440  push    r12
0x18007e442  push    r13
0x18007e444  push    r14
0x18007e446  push    r15
0x18007e448  lea     rbp, [rsp-27h]
0x18007e44d  sub     rsp, 0C0h
0x18007e454  mov     rax, cs:__security_cookie
0x18007e45b  xor     rax, rsp
0x18007e45e  mov     [rbp+57h+var_38], rax
0x18007e462  xor     r13d, r13d
0x18007e465  lea     r9, [rbp+57h+SecurityDescriptorSize]; SecurityDescriptorSize
0x18007e469  mov     rax, r8
0x18007e46c  mov     [rbp+57h+SecurityDescriptor], r13
0x18007e470  mov     rsi, rcx
0x18007e473  mov     [rbp+57h+SecurityDescriptorSize], r13d
0x18007e477  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18007e47b  mov     rcx, rax; StringSecurityDescriptor
0x18007e47e  lea     r14d, [r13+1]
0x18007e482  mov     edx, r14d; StringSDRevision
0x18007e485  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18007e48c  nop     dword ptr [rax+rax+00h]
0x18007e491  test    eax, eax
0x18007e493  jnz     short loc_18007E4B9
0x18007e495  call    cs:__imp_GetLastError
0x18007e49c  nop     dword ptr [rax+rax+00h]
0x18007e4a1  mov     ebx, eax
0x18007e4a3  test    eax, eax
0x18007e4a5  jle     loc_18007E866
0x18007e4ab  movzx   ebx, ax
0x18007e4ae  or      ebx, 80070000h
0x18007e4b4  jmp     loc_18007E866
0x18007e4b9  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x18007e4bd  lea     r8, [rbp+57h+dwRevision]; lpdwRevision
0x18007e4c1  lea     rdx, [rbp+57h+pControl]; pControl
0x18007e4c5  mov     [rbp+57h+bDaclPresent], r13d
0x18007e4c9  mov     ebx, r13d
0x18007e4cc  mov     [rbp+57h+bOwnerDefaulted], r14d
0x18007e4d0  mov     [rbp+57h+pOwner], r13
0x18007e4d4  mov     edi, 0E0000h
0x18007e4d9  mov     [rbp+57h+pGroup], r13
0x18007e4dd  mov     [rbp+57h+pDacl], r13
0x18007e4e1  mov     [rbp+57h+pSacl], r13
0x18007e4e5  mov     [rbp+57h+pControl], r13w
0x18007e4ea  mov     [rbp+57h+dwRevision], r13d
0x18007e4ee  call    cs:__imp_GetSecurityDescriptorControl
0x18007e4f5  nop     dword ptr [rax+rax+00h]
0x18007e4fa  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x18007e4fe  lea     r8, [rbp+57h+bOwnerDefaulted]; lpbOwnerDefaulted
0x18007e502  lea     rdx, [rbp+57h+pOwner]; pOwner
0x18007e506  call    cs:__imp_GetSecurityDescriptorOwner
0x18007e50d  nop     dword ptr [rax+rax+00h]
0x18007e512  test    eax, eax
0x18007e514  jz      short loc_18007E51E
0x18007e516  cmp     [rbp+57h+pOwner], r13
0x18007e51a  cmovnz  ebx, r14d
0x18007e51e  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x18007e522  lea     r8, [rbp+57h+bOwnerDefaulted]; lpbGroupDefaulted
0x18007e526  lea     rdx, [rbp+57h+pGroup]; pGroup
0x18007e52a  call    cs:__imp_GetSecurityDescriptorGroup
0x18007e531  nop     dword ptr [rax+rax+00h]
0x18007e536  test    eax, eax
0x18007e538  jz      short loc_18007E543
0x18007e53a  cmp     [rbp+57h+pGroup], r13
0x18007e53e  jz      short loc_18007E543
0x18007e540  or      ebx, 2
0x18007e543  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x18007e547  lea     r9, [rbp+57h+bOwnerDefaulted]; lpbDaclDefaulted
0x18007e54b  lea     r8, [rbp+57h+pDacl]; pDacl
0x18007e54f  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x18007e553  call    cs:__imp_GetSecurityDescriptorDacl
0x18007e55a  nop     dword ptr [rax+rax+00h]
0x18007e55f  test    eax, eax
0x18007e561  jz      short loc_18007E582
0x18007e563  cmp     [rbp+57h+bDaclPresent], r13d
0x18007e567  jz      short loc_18007E582
0x18007e569  mov     eax, 1000h
0x18007e56e  test    [rbp+57h+pControl], ax
0x18007e572  jz      short loc_18007E57C
0x18007e574  or      ebx, 80000004h
0x18007e57a  jmp     short loc_18007E582
0x18007e57c  or      ebx, 20000004h
0x18007e582  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x18007e586  lea     r9, [rbp+57h+bOwnerDefaulted]; lpbSaclDefaulted
0x18007e58a  xorps   xmm0, xmm0
0x18007e58d  mov     [rbp+57h+TokenHandle], r13
0x18007e591  lea     r8, [rbp+57h+pSacl]; pSacl
0x18007e595  lea     rdx, [rbp+57h+bDaclPresent]; lpbSaclPresent
0x18007e599  movups  xmmword ptr [rbp+57h+NewState.PrivilegeCount], xmm0
0x18007e59d  call    cs:__imp_GetSecurityDescriptorSacl
0x18007e5a4  nop     dword ptr [rax+rax+00h]
0x18007e5a9  test    eax, eax
0x18007e5ab  jz      loc_18007E6A8
0x18007e5b1  cmp     [rbp+57h+bDaclPresent], r13d
0x18007e5b5  jz      loc_18007E6A8
0x18007e5bb  call    cs:__imp_GetCurrentThread
0x18007e5c2  nop     dword ptr [rax+rax+00h]
0x18007e5c7  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18007e5cb  mov     r8d, r14d; OpenAsSelf
0x18007e5ce  mov     rcx, rax; ThreadHandle
0x18007e5d1  mov     edx, 28h ; '('; DesiredAccess
0x18007e5d6  call    cs:__imp_OpenThreadToken
0x18007e5dd  nop     dword ptr [rax+rax+00h]
0x18007e5e2  test    eax, eax
0x18007e5e4  jz      loc_18007E68A
0x18007e5ea  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18007e5ee  lea     r8, [rbp+57h+NewState]; NewState
0x18007e5f2  mov     [rsp+0F0h+ReturnLength], r13; ReturnLength
0x18007e5f7  xor     r9d, r9d; BufferLength
0x18007e5fa  xor     edx, edx; DisableAllPrivileges
0x18007e5fc  mov     [rsp+0F0h+PreviousState], r13; PreviousState
0x18007e601  mov     [rbp+57h+NewState.PrivilegeCount], r14d
0x18007e605  mov     [rbp+57h+NewState.Privileges.Attributes], 2
0x18007e60c  mov     qword ptr [rbp+57h+NewState.Privileges.Luid.LowPart], 8
0x18007e614  call    cs:__imp_AdjustTokenPrivileges
0x18007e61b  nop     dword ptr [rax+rax+00h]
0x18007e620  test    eax, eax
0x18007e622  jnz     short loc_18007E68A
0x18007e624  call    cs:__imp_GetLastError
0x18007e62b  nop     dword ptr [rax+rax+00h]
0x18007e630  mov     ebx, eax
0x18007e632  test    eax, eax
0x18007e634  jle     short loc_18007E63F
0x18007e636  movzx   ebx, ax
0x18007e639  or      ebx, 80070000h
0x18007e63f  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e646  lea     r15, WPP_GLOBAL_Control
0x18007e64d  cmp     rcx, r15
0x18007e650  jz      short loc_18007E67C
0x18007e652  mov     r14d, 10000h
0x18007e658  test    [rcx+1Ch], r14d
0x18007e65c  jz      short loc_18007E67C
0x18007e65e  cmp     byte ptr [rcx+19h], 2
0x18007e662  jb      short loc_18007E67C
0x18007e664  mov     rcx, [rcx+10h]
0x18007e668  lea     r8, WPP_0318f2e21e573bf245f738540b7f5294_Traceguids
0x18007e66f  mov     edx, 0Ah
0x18007e674  mov     r9d, ebx
0x18007e677  call    WPP_SF_d
0x18007e67c  lea     rcx, [rbp+57h+TokenHandle]; this
0x18007e680  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x18007e685  jmp     loc_18007E866
0x18007e68a  mov     eax, 2000h
0x18007e68f  mov     edi, 10E0000h
0x18007e694  test    [rbp+57h+pControl], ax
0x18007e698  jz      short loc_18007E6A2
0x18007e69a  or      ebx, 40000008h
0x18007e6a0  jmp     short loc_18007E6A8
0x18007e6a2  or      ebx, 10000008h
0x18007e6a8  xorps   xmm0, xmm0
0x18007e6ab  mov     dword ptr [rsp+0F0h+ReturnLength], 2000000h; unsigned int
0x18007e6b3  xor     r9d, r9d; unsigned int
0x18007e6b6  mov     dword ptr [rsp+0F0h+PreviousState], 3; struct _SECURITY_ATTRIBUTES *
0x18007e6be  mov     r8d, r14d; unsigned int
0x18007e6c1  mov     edx, edi; unsigned __int16 *
0x18007e6c3  mov     rcx, rsi; String2
0x18007e6c6  movdqu  xmmword ptr [rbp+57h+handle], xmm0
0x18007e6cb  call    ?CreateFileSafe@tsched@@YAPEAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z; tsched::CreateFileSafe(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)
0x18007e6d0  mov     rdx, rax
0x18007e6d3  lea     rcx, [rbp+57h+handle]
0x18007e6d7  call    ??4JobsAutoHandle@tsched@@QEAAAEAV01@PEAX@Z; tsched::JobsAutoHandle::operator=(void *)
0x18007e6dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e6e3  lea     r15, WPP_GLOBAL_Control
0x18007e6ea  mov     r12, [rbp+57h+handle]
0x18007e6ee  mov     r14d, 10000h
0x18007e6f4  cmp     rcx, r15
0x18007e6f7  jz      short loc_18007E722
0x18007e6f9  test    [rcx+1Ch], r14d
0x18007e6fd  jz      short loc_18007E722
0x18007e6ff  cmp     byte ptr [rcx+19h], 4
0x18007e703  jb      short loc_18007E722
0x18007e705  mov     rcx, [rcx+10h]
0x18007e709  lea     r8, WPP_0318f2e21e573bf245f738540b7f5294_Traceguids
0x18007e710  mov     edx, 0Bh
0x18007e715  mov     [rsp+0F0h+PreviousState], r12
0x18007e71a  mov     r9, rsi
0x18007e71d  call    WPP_SF_Sq
0x18007e722  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x18007e726  jnz     short loc_18007E73D
0x18007e728  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x18007e72d  lea     rcx, [rbp+57h+handle]; this
0x18007e731  mov     ebx, eax
0x18007e733  call    ?Close@JobsAutoHandle@tsched@@QEAAXXZ; tsched::JobsAutoHandle::Close(void)
0x18007e738  jmp     loc_18007E67C
0x18007e73d  mov     rcx, [rbp+57h+pDacl]
0x18007e741  mov     edx, 1; ObjectType
0x18007e746  mov     r8, [rbp+57h+pGroup]
0x18007e74a  mov     rax, [rbp+57h+pSacl]
0x18007e74e  mov     r9, [rbp+57h+pOwner]; psidOwner
0x18007e752  mov     [rsp+0F0h+var_C0], rax; pSacl
0x18007e757  mov     [rsp+0F0h+ReturnLength], rcx; pDacl
0x18007e75c  mov     rcx, r12; handle
0x18007e75f  mov     [rsp+0F0h+PreviousState], r8; psidGroup
0x18007e764  mov     r8d, ebx; SecurityInfo
0x18007e767  mov     [rbp+57h+handle+8], rsi
0x18007e76b  call    cs:__imp_SetSecurityInfo
0x18007e772  nop     dword ptr [rax+rax+00h]
0x18007e777  mov     esi, eax
0x18007e779  mov     edi, 80070000h
0x18007e77e  test    eax, eax
0x18007e780  jle     short loc_18007E787
0x18007e782  movzx   esi, ax
0x18007e785  or      esi, edi
0x18007e787  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e78e  cmp     rcx, r15
0x18007e791  jz      short loc_18007E7D7
0x18007e793  test    [rcx+1Ch], r14d
0x18007e797  jz      short loc_18007E7D7
0x18007e799  cmp     byte ptr [rcx+19h], 4
0x18007e79d  jb      short loc_18007E7D7
0x18007e79f  mov     rax, [rbp+57h+pSacl]
0x18007e7a3  mov     r9, r12
0x18007e7a6  mov     rcx, [rcx+10h]
0x18007e7aa  mov     [rsp+0F0h+var_A8], esi
0x18007e7ae  mov     [rsp+0F0h+var_B0], rax
0x18007e7b3  mov     rax, [rbp+57h+pDacl]
0x18007e7b7  mov     [rsp+0F0h+var_B8], rax
0x18007e7bc  mov     rax, [rbp+57h+pGroup]
0x18007e7c0  mov     [rsp+0F0h+var_C0], rax
0x18007e7c5  mov     rax, [rbp+57h+pOwner]
0x18007e7c9  mov     [rsp+0F0h+ReturnLength], rax
0x18007e7ce  mov     dword ptr [rsp+0F0h+PreviousState], ebx
0x18007e7d2  call    WPP_SF_qDqqqqD
0x18007e7d7  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18007e7db  test    rcx, rcx
0x18007e7de  jz      short loc_18007E852
0x18007e7e0  cmp     [rbp+57h+NewState.PrivilegeCount], r13d
0x18007e7e4  jz      short loc_18007E852
0x18007e7e6  mov     [rsp+0F0h+ReturnLength], r13; ReturnLength
0x18007e7eb  lea     r8, [rbp+57h+NewState]; NewState
0x18007e7ef  xor     r9d, r9d; BufferLength
0x18007e7f2  mov     [rsp+0F0h+PreviousState], r13; PreviousState
0x18007e7f7  xor     edx, edx; DisableAllPrivileges
0x18007e7f9  mov     [rbp+57h+NewState.Privileges.Attributes], r13d
0x18007e7fd  call    cs:__imp_AdjustTokenPrivileges
0x18007e804  nop     dword ptr [rax+rax+00h]
0x18007e809  test    eax, eax
0x18007e80b  jnz     short loc_18007E852
0x18007e80d  call    cs:__imp_GetLastError
0x18007e814  nop     dword ptr [rax+rax+00h]
0x18007e819  test    eax, eax
0x18007e81b  jle     short loc_18007E822
0x18007e81d  movzx   eax, ax
0x18007e820  or      eax, edi
0x18007e822  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e829  cmp     rcx, r15
0x18007e82c  jz      short loc_18007E852
0x18007e82e  test    [rcx+1Ch], r14d
0x18007e832  jz      short loc_18007E852
0x18007e834  cmp     byte ptr [rcx+19h], 2
0x18007e838  jb      short loc_18007E852
0x18007e83a  mov     rcx, [rcx+10h]
0x18007e83e  lea     r8, WPP_0318f2e21e573bf245f738540b7f5294_Traceguids
0x18007e845  mov     edx, 0Dh
0x18007e84a  mov     r9d, eax
0x18007e84d  call    WPP_SF_d
0x18007e852  lea     rcx, [rbp+57h+handle]; this
0x18007e856  call    ?Close@JobsAutoHandle@tsched@@QEAAXXZ; tsched::JobsAutoHandle::Close(void)
0x18007e85b  lea     rcx, [rbp+57h+TokenHandle]; this
0x18007e85f  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x18007e864  mov     ebx, esi
0x18007e866  lea     rcx, [rbp+57h+SecurityDescriptor]
0x18007e86a  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x18007e86f  mov     eax, ebx
0x18007e871  mov     rcx, [rbp+57h+var_38]
0x18007e875  xor     rcx, rsp; StackCookie
0x18007e878  call    __security_check_cookie
0x18007e87d  mov     rbx, [rsp+0F0h+arg_8]
0x18007e885  add     rsp, 0C0h
0x18007e88c  pop     r15
0x18007e88e  pop     r14
0x18007e890  pop     r13
0x18007e892  pop     r12
0x18007e894  pop     rdi
0x18007e895  pop     rsi
0x18007e896  pop     rbp
0x18007e897  retn
```
