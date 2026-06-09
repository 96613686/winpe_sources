# tsched::SetJobFileSecurityByName(ushort const *,int,ushort const *)

- ea: `0x180006534`
- end: `0x1800069a0`
- name: `?SetJobFileSecurityByName@tsched@@YAJPEBGH0@Z`
- size: `1132`
- prototype: `__int64 __fastcall(wchar_t *String2, const unsigned __int16 *, const WCHAR *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180012c50`

## callees

- `0x180004e1c`
- `0x180006534`
- `0x1800069a8`
- `0x18000c760`
- `0x1800113cc`
- `0x180019cf0`
- `0x18002d51c`
- `0x18002d820`
- `0x18002d8ec`
- `0x18002d970`
- `0x18002d9b8`
- `0x18002e5b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800066a2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800066a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000668d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000668d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180006675`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180006675`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800066da`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18000690e`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800066da`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18000690e`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180006631`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180006631`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x1800065de`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x1800065de`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18000660e`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18000660e`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1800065f0`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1800065f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000658b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006918`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000658b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006918`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800067b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800067b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800067b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800067b9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000678b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000678b`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18000687e`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18000687e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180006581`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180006581`

## pseudocode

```c
__int64 __fastcall tsched::SetJobFileSecurityByName(
        wchar_t *String2,
        const unsigned __int16 *a2,
        const WCHAR *a3,
        const unsigned __int16 *a4)
{
  signed int LastError; // eax
  unsigned int v6; // ebx
  SECURITY_INFORMATION v7; // ebx
  DWORD v8; // edi
  HANDLE CurrentThread; // rax
  signed int v10; // eax
  HANDLE FileW; // rax
  __int64 v12; // rdx
  void *v13; // r8
  __int64 v14; // rdi
  int v15; // edx
  int v16; // r8d
  tsched *v17; // rcx
  unsigned int LastHrError; // eax
  int v19; // edx
  unsigned int v20; // ecx
  signed int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // r8
  unsigned int v24; // r12d
  signed int v25; // eax
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
  __int128 v38; // [rsp+98h] [rbp-1h] BYREF
  _TOKEN_PRIVILEGES NewState; // [rsp+A8h] [rbp+Fh] BYREF

  SecurityDescriptor = 0;
  SecurityDescriptorSize = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(a3, 1u, &SecurityDescriptor, &SecurityDescriptorSize) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_60;
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
        v10 = GetLastError();
        v6 = v10;
        if ( v10 > 0 )
          v6 = (unsigned __int16)v10 | 0x80070000;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_0318f2e21e573bf245f738540b7f5294_Traceguids, v6);
        }
LABEL_24:
        wmi::AutoHandle::Close((wmi::AutoHandle *)&TokenHandle);
        goto LABEL_60;
      }
    }
    v8 = 17694720;
    if ( (pControl[0] & 0x2000) != 0 )
      v7 |= 0x40000008u;
    else
      v7 |= 0x10000008u;
  }
  v38 = 0;
  FileW = CreateFileW(String2, v8, 1u, 0, 3u, 0x2000000u, 0);
  v14 = (__int64)FileW;
  if ( FileW == (HANDLE)-1LL )
    goto LABEL_31;
  if ( (int)tsched::VerifyJobFilePath(String2, FileW, v13) < 0 )
  {
    SetLastError(5u);
    CloseHandle((HANDLE)v14);
LABEL_31:
    v14 = -1;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, v13, v14);
  }
  tsched::JobsAutoHandle::Close((tsched::JobsAutoHandle *)&v38);
  *(_QWORD *)&v38 = v14;
  v17 = (tsched *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_Sq(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, v16, (_DWORD)String2, v14);
  }
  if ( v14 == -1 )
  {
    LastHrError = tsched::GetLastHrError(v17, v15);
    v6 = 0;
    if ( !tsched::IsErrorNotFound((tsched *)LastHrError, v19) )
      v6 = v20;
    tsched::JobsAutoHandle::Close((tsched::JobsAutoHandle *)&v38);
    goto LABEL_24;
  }
  *((_QWORD *)&v38 + 1) = String2;
  v21 = SetSecurityInfo((HANDLE)v14, SE_FILE_OBJECT, v7, pOwner, pGroup, pDacl, pSacl);
  v24 = v21;
  if ( v21 > 0 )
    v24 = (unsigned __int16)v21 | 0x80070000;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_qDqqqqD(*((_QWORD *)WPP_GLOBAL_Control + 2), v22, v23, v14, v7, pOwner, pGroup, pDacl, pSacl, v24);
  }
  if ( TokenHandle )
  {
    if ( NewState.PrivilegeCount )
    {
      NewState.Privileges[0].Attributes = 0;
      if ( !AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0, 0, 0) )
      {
        v25 = GetLastError();
        if ( v25 > 0 )
          v25 = (unsigned __int16)v25 | 0x80070000;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            WPP_0318f2e21e573bf245f738540b7f5294_Traceguids,
            (unsigned int)v25);
        }
      }
    }
  }
  tsched::JobsAutoHandle::Close((tsched::JobsAutoHandle *)&v38);
  wmi::AutoHandle::Close((wmi::AutoHandle *)&TokenHandle);
  v6 = v24;
LABEL_60:
  tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&SecurityDescriptor);
  return v6;
}

```

## disassembly

```asm
0x180006534  mov     [rsp-8+arg_8], rbx
0x180006539  push    rbp
0x18000653a  push    rsi
0x18000653b  push    rdi
0x18000653c  push    r12
0x18000653e  push    r13
0x180006540  push    r14
0x180006542  push    r15
0x180006544  lea     rbp, [rsp-27h]
0x180006549  sub     rsp, 0C0h
0x180006550  mov     rax, cs:__security_cookie
0x180006557  xor     rax, rsp
0x18000655a  mov     [rbp+57h+var_38], rax
0x18000655e  mov     rax, r8
0x180006561  mov     rsi, rcx
0x180006564  xor     r13d, r13d
0x180006567  mov     [rbp+57h+SecurityDescriptor], r13
0x18000656b  mov     [rbp+57h+SecurityDescriptorSize], r13d
0x18000656f  lea     r9, [rbp+57h+SecurityDescriptorSize]; SecurityDescriptorSize
0x180006573  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180006577  lea     r12d, [r13+1]
0x18000657b  mov     edx, r12d; StringSDRevision
0x18000657e  mov     rcx, rax; StringSecurityDescriptor
0x180006581  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180006587  test    eax, eax
0x180006589  jnz     short loc_1800065A9
0x18000658b  call    cs:__imp_GetLastError
0x180006591  mov     ebx, eax
0x180006593  test    eax, eax
0x180006595  jle     loc_18000696E
0x18000659b  movzx   ebx, ax
0x18000659e  or      ebx, 80070000h
0x1800065a4  jmp     loc_18000696E
0x1800065a9  mov     ebx, r13d
0x1800065ac  mov     [rbp+57h+bDaclPresent], r13d
0x1800065b0  mov     [rbp+57h+bOwnerDefaulted], r12d
0x1800065b4  mov     [rbp+57h+pOwner], r13
0x1800065b8  mov     [rbp+57h+pGroup], r13
0x1800065bc  mov     [rbp+57h+pDacl], r13
0x1800065c0  mov     [rbp+57h+pSacl], r13
0x1800065c4  mov     edi, 0E0000h
0x1800065c9  mov     [rbp+57h+pControl], r13w
0x1800065ce  mov     [rbp+57h+dwRevision], r13d
0x1800065d2  lea     r8, [rbp+57h+dwRevision]; lpdwRevision
0x1800065d6  lea     rdx, [rbp+57h+pControl]; pControl
0x1800065da  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x1800065de  call    cs:__imp_GetSecurityDescriptorControl
0x1800065e4  lea     r8, [rbp+57h+bOwnerDefaulted]; lpbOwnerDefaulted
0x1800065e8  lea     rdx, [rbp+57h+pOwner]; pOwner
0x1800065ec  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x1800065f0  call    cs:__imp_GetSecurityDescriptorOwner
0x1800065f6  test    eax, eax
0x1800065f8  jz      short loc_180006602
0x1800065fa  cmp     [rbp+57h+pOwner], r13
0x1800065fe  cmovnz  ebx, r12d
0x180006602  lea     r8, [rbp+57h+bOwnerDefaulted]; lpbGroupDefaulted
0x180006606  lea     rdx, [rbp+57h+pGroup]; pGroup
0x18000660a  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x18000660e  call    cs:__imp_GetSecurityDescriptorGroup
0x180006614  test    eax, eax
0x180006616  jz      short loc_180006621
0x180006618  cmp     [rbp+57h+pGroup], r13
0x18000661c  jz      short loc_180006621
0x18000661e  or      ebx, 2
0x180006621  lea     r9, [rbp+57h+bOwnerDefaulted]; lpbDaclDefaulted
0x180006625  lea     r8, [rbp+57h+pDacl]; pDacl
0x180006629  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x18000662d  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x180006631  call    cs:__imp_GetSecurityDescriptorDacl
0x180006637  test    eax, eax
0x180006639  jz      short loc_18000665A
0x18000663b  cmp     [rbp+57h+bDaclPresent], r13d
0x18000663f  jz      short loc_18000665A
0x180006641  mov     eax, 1000h
0x180006646  test    [rbp+57h+pControl], ax
0x18000664a  jz      short loc_180006654
0x18000664c  or      ebx, 80000004h
0x180006652  jmp     short loc_18000665A
0x180006654  or      ebx, 20000004h
0x18000665a  mov     [rbp+57h+TokenHandle], r13
0x18000665e  xorps   xmm0, xmm0
0x180006661  movups  xmmword ptr [rbp+57h+NewState.PrivilegeCount], xmm0
0x180006665  lea     r9, [rbp+57h+bOwnerDefaulted]; lpbSaclDefaulted
0x180006669  lea     r8, [rbp+57h+pSacl]; pSacl
0x18000666d  lea     rdx, [rbp+57h+bDaclPresent]; lpbSaclPresent
0x180006671  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x180006675  call    cs:__imp_GetSecurityDescriptorSacl
0x18000667b  test    eax, eax
0x18000667d  jz      loc_180006763
0x180006683  cmp     [rbp+57h+bDaclPresent], r13d
0x180006687  jz      loc_180006763
0x18000668d  call    cs:__imp_GetCurrentThread
0x180006693  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180006697  mov     r8d, r12d; OpenAsSelf
0x18000669a  mov     edx, 28h ; '('; DesiredAccess
0x18000669f  mov     rcx, rax; ThreadHandle
0x1800066a2  call    cs:__imp_OpenThreadToken
0x1800066a8  test    eax, eax
0x1800066aa  jz      loc_180006745
0x1800066b0  mov     [rbp+57h+NewState.PrivilegeCount], r12d
0x1800066b4  mov     [rbp+57h+NewState.Privileges.Attributes], 2
0x1800066bb  mov     qword ptr [rbp+57h+NewState.Privileges.Luid.LowPart], 8
0x1800066c3  mov     [rsp+0F0h+ReturnLength], r13; ReturnLength
0x1800066c8  mov     [rsp+0F0h+PreviousState], r13; PreviousState
0x1800066cd  xor     r9d, r9d; BufferLength
0x1800066d0  lea     r8, [rbp+57h+NewState]; NewState
0x1800066d4  xor     edx, edx; DisableAllPrivileges
0x1800066d6  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800066da  call    cs:__imp_AdjustTokenPrivileges
0x1800066e0  test    eax, eax
0x1800066e2  jnz     short loc_180006745
0x1800066e4  call    cs:__imp_GetLastError
0x1800066ea  mov     ebx, eax
0x1800066ec  test    eax, eax
0x1800066ee  jle     short loc_1800066F9
0x1800066f0  movzx   ebx, ax
0x1800066f3  or      ebx, 80070000h
0x1800066f9  lea     r15, WPP_GLOBAL_Control
0x180006700  mov     rcx, cs:WPP_GLOBAL_Control
0x180006707  cmp     rcx, r15
0x18000670a  jz      short loc_180006737
0x18000670c  mov     r14d, 10000h
0x180006712  test    [rcx+1Ch], r14d
0x180006716  jz      short loc_180006737
0x180006718  cmp     byte ptr [rcx+19h], 2
0x18000671c  jb      short loc_180006737
0x18000671e  mov     edx, 0Ah
0x180006723  mov     r9d, ebx
0x180006726  lea     r8, WPP_0318f2e21e573bf245f738540b7f5294_Traceguids
0x18000672d  mov     rcx, [rcx+10h]
0x180006731  call    WPP_SF_d
0x180006736  nop
0x180006737  lea     rcx, [rbp+57h+TokenHandle]; this
0x18000673b  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x180006740  jmp     loc_18000696E
0x180006745  mov     edi, 10E0000h
0x18000674a  mov     eax, 2000h
0x18000674f  test    [rbp+57h+pControl], ax
0x180006753  jz      short loc_18000675D
0x180006755  or      ebx, 40000008h
0x18000675b  jmp     short loc_180006763
0x18000675d  or      ebx, 10000008h
0x180006763  xorps   xmm0, xmm0
0x180006766  movdqu  [rbp+57h+var_58], xmm0
0x18000676b  mov     [rsp+0F0h+hTemplateFile], r13; hTemplateFile
0x180006770  mov     dword ptr [rsp+0F0h+ReturnLength], 2000000h; dwFlagsAndAttributes
0x180006778  mov     dword ptr [rsp+0F0h+PreviousState], 3; dwCreationDisposition
0x180006780  xor     r9d, r9d; lpSecurityAttributes
0x180006783  mov     r8d, r12d; dwShareMode
0x180006786  mov     edx, edi; dwDesiredAccess
0x180006788  mov     rcx, rsi; lpFileName
0x18000678b  call    cs:__imp_CreateFileW
0x180006791  mov     rdi, rax
0x180006794  or      r14, 0FFFFFFFFFFFFFFFFh
0x180006798  cmp     rax, r14
0x18000679b  jz      short loc_1800067BF
0x18000679d  mov     rdx, rax; hFile
0x1800067a0  mov     rcx, rsi; String2
0x1800067a3  call    ?VerifyJobFilePath@tsched@@YAJPEBGPEAX@Z; tsched::VerifyJobFilePath(ushort const *,void *)
0x1800067a8  test    eax, eax
0x1800067aa  jns     short loc_1800067C2
0x1800067ac  lea     ecx, [r14+6]; dwErrCode
0x1800067b0  call    cs:__imp_SetLastError
0x1800067b6  mov     rcx, rdi; hObject
0x1800067b9  call    cs:__imp_CloseHandle
0x1800067bf  mov     rdi, r14
0x1800067c2  lea     r15, WPP_GLOBAL_Control
0x1800067c9  mov     r14d, 10000h
0x1800067cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800067d6  cmp     rcx, r15
0x1800067d9  jz      short loc_1800067F3
0x1800067db  test    [rcx+1Ch], r14d
0x1800067df  jz      short loc_1800067F3
0x1800067e1  cmp     byte ptr [rcx+19h], 4
0x1800067e5  jb      short loc_1800067F3
0x1800067e7  mov     r9, rdi
0x1800067ea  mov     rcx, [rcx+10h]
0x1800067ee  call    WPP_SF_q
0x1800067f3  lea     rcx, [rbp+57h+var_58]; this
0x1800067f7  call    ?Close@JobsAutoHandle@tsched@@QEAAXXZ; tsched::JobsAutoHandle::Close(void)
0x1800067fc  mov     qword ptr [rbp+57h+var_58], rdi
0x180006800  mov     rcx, cs:WPP_GLOBAL_Control
0x180006807  cmp     rcx, r15
0x18000680a  jz      short loc_180006829
0x18000680c  test    [rcx+1Ch], r14d
0x180006810  jz      short loc_180006829
0x180006812  cmp     byte ptr [rcx+19h], 4
0x180006816  jb      short loc_180006829
0x180006818  mov     [rsp+0F0h+PreviousState], rdi
0x18000681d  mov     r9, rsi
0x180006820  mov     rcx, [rcx+10h]
0x180006824  call    WPP_SF_Sq
0x180006829  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18000682d  jnz     short loc_180006852
0x18000682f  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x180006834  mov     ecx, eax; this
0x180006836  call    ?IsErrorNotFound@tsched@@YA_NJ@Z; tsched::IsErrorNotFound(long)
0x18000683b  nop
0x18000683c  mov     ebx, r13d
0x18000683f  test    al, al
0x180006841  cmovz   ebx, ecx
0x180006844  lea     rcx, [rbp+57h+var_58]; this
0x180006848  call    ?Close@JobsAutoHandle@tsched@@QEAAXXZ; tsched::JobsAutoHandle::Close(void)
0x18000684d  jmp     loc_180006737
0x180006852  mov     qword ptr [rbp+57h+var_58+8], rsi
0x180006856  mov     rax, [rbp+57h+pSacl]
0x18000685a  mov     rcx, [rbp+57h+pDacl]
0x18000685e  mov     r8, [rbp+57h+pGroup]
0x180006862  mov     [rsp+0F0h+hTemplateFile], rax; pSacl
0x180006867  mov     [rsp+0F0h+ReturnLength], rcx; pDacl
0x18000686c  mov     [rsp+0F0h+PreviousState], r8; psidGroup
0x180006871  mov     r9, [rbp+57h+pOwner]; psidOwner
0x180006875  mov     r8d, ebx; SecurityInfo
0x180006878  mov     edx, r12d; ObjectType
0x18000687b  mov     rcx, rdi; handle
0x18000687e  call    cs:__imp_SetSecurityInfo
0x180006884  mov     r12d, eax
0x180006887  mov     esi, 80070000h
0x18000688c  test    eax, eax
0x18000688e  jle     short loc_180006897
0x180006890  movzx   r12d, ax
0x180006894  or      r12d, esi
0x180006897  mov     rcx, cs:WPP_GLOBAL_Control
0x18000689e  cmp     rcx, r15
0x1800068a1  jz      short loc_1800068E8
0x1800068a3  test    [rcx+1Ch], r14d
0x1800068a7  jz      short loc_1800068E8
0x1800068a9  cmp     byte ptr [rcx+19h], 4
0x1800068ad  jb      short loc_1800068E8
0x1800068af  mov     [rsp+0F0h+var_A8], r12d
0x1800068b4  mov     rax, [rbp+57h+pSacl]
0x1800068b8  mov     [rsp+0F0h+var_B0], rax
0x1800068bd  mov     rax, [rbp+57h+pDacl]
0x1800068c1  mov     [rsp+0F0h+var_B8], rax
0x1800068c6  mov     rax, [rbp+57h+pGroup]
0x1800068ca  mov     [rsp+0F0h+hTemplateFile], rax
0x1800068cf  mov     rax, [rbp+57h+pOwner]
0x1800068d3  mov     [rsp+0F0h+ReturnLength], rax
0x1800068d8  mov     dword ptr [rsp+0F0h+PreviousState], ebx
0x1800068dc  mov     r9, rdi
0x1800068df  mov     rcx, [rcx+10h]
0x1800068e3  call    WPP_SF_qDqqqqD
0x1800068e8  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800068ec  test    rcx, rcx
0x1800068ef  jz      short loc_180006958
0x1800068f1  cmp     [rbp+57h+NewState.PrivilegeCount], r13d
0x1800068f5  jz      short loc_180006958
0x1800068f7  mov     [rbp+57h+NewState.Privileges.Attributes], r13d
0x1800068fb  mov     [rsp+0F0h+ReturnLength], r13; ReturnLength
0x180006900  mov     [rsp+0F0h+PreviousState], r13; PreviousState
0x180006905  xor     r9d, r9d; BufferLength
0x180006908  lea     r8, [rbp+57h+NewState]; NewState
0x18000690c  xor     edx, edx; DisableAllPrivileges
0x18000690e  call    cs:__imp_AdjustTokenPrivileges
0x180006914  test    eax, eax
0x180006916  jnz     short loc_180006958
0x180006918  call    cs:__imp_GetLastError
0x18000691e  test    eax, eax
0x180006920  jle     short loc_180006927
0x180006922  movzx   eax, ax
0x180006925  or      eax, esi
0x180006927  mov     rcx, cs:WPP_GLOBAL_Control
0x18000692e  cmp     rcx, r15
0x180006931  jz      short loc_180006958
0x180006933  test    [rcx+1Ch], r14d
0x180006937  jz      short loc_180006958
0x180006939  cmp     byte ptr [rcx+19h], 2
0x18000693d  jb      short loc_180006958
0x18000693f  mov     edx, 0Dh
0x180006944  mov     r9d, eax
0x180006947  lea     r8, WPP_0318f2e21e573bf245f738540b7f5294_Traceguids
0x18000694e  mov     rcx, [rcx+10h]
0x180006952  call    WPP_SF_d
0x180006957  nop
0x180006958  lea     rcx, [rbp+57h+var_58]; this
0x18000695c  call    ?Close@JobsAutoHandle@tsched@@QEAAXXZ; tsched::JobsAutoHandle::Close(void)
0x180006961  nop
0x180006962  lea     rcx, [rbp+57h+TokenHandle]; this
0x180006966  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x18000696b  mov     ebx, r12d
0x18000696e  lea     rcx, [rbp+57h+SecurityDescriptor]
0x180006972  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180006977  mov     eax, ebx
0x180006979  mov     rcx, [rbp+57h+var_38]
0x18000697d  xor     rcx, rsp; StackCookie
0x180006980  call    __security_check_cookie
0x180006985  mov     rbx, [rsp+0F0h+arg_8]
0x18000698d  add     rsp, 0C0h
0x180006994  pop     r15
0x180006996  pop     r14
0x180006998  pop     r13
0x18000699a  pop     r12
0x18000699c  pop     rdi
0x18000699d  pop     rsi
0x18000699e  pop     rbp
0x18000699f  retn
```
