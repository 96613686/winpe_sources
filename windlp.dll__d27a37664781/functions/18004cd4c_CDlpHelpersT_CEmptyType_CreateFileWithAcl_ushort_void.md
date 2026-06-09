# CDlpHelpersT<CEmptyType>::CreateFileWithAcl(ushort *,void * *)

- ea: `0x18004cd4c`
- end: `0x18004d017`
- name: `?CreateFileWithAcl@?$CDlpHelpersT@VCEmptyType@@@@SAJPEAGPEAPEAX@Z`
- size: `715`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180064744`

## callees

- `0x18000aba4`
- `0x18001fd60`
- `0x18004cd4c`
- `0x18007e938`
- `0x18007ed40`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004cf26`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004cf26`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ce7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004cfad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004cfda`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ce7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004cfad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004cfda`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004ce8d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004ce8d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004cfbb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004cfe8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004cfbb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004cfe8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ce01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ce30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ce01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ce30`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004cfa1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004cfa1`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18004ced5`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18004cef1`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18004ced5`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18004cef1`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004ce69`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004ce74`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004ce69`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004ce74`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18004ceb3`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18004ceb3`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18004cdf7`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18004cdf7`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18004cfcb`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18004cfcb`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18004cf65`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18004cf65`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CDlpHelpersT<CEmptyType>::CreateFileWithAcl(LPCWSTR lpFileName, _QWORD *a2)
{
  struct _ACL *v4; // rbx
  PSID v5; // r14
  __int64 v6; // rdi
  __int64 v7; // rcx
  unsigned int v8; // esi
  signed int LastError; // eax
  int v10; // esi
  signed int v11; // eax
  PSID v12; // rsi
  DWORD LengthSid; // ebx
  DWORD v14; // esi
  HANDLE ProcessHeap; // rax
  struct _ACL *v16; // rax
  HANDLE FileW; // rax
  HANDLE v18; // r15
  signed int v19; // eax
  HANDLE v20; // rax
  HANDLE v21; // rax
  PSID pSid; // [rsp+60h] [rbp-9h] BYREF
  PSID v24[3]; // [rsp+68h] [rbp-1h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+80h] [rbp+17h] BYREF

  v4 = 0;
  v24[1] = 0;
  pSid = 0;
  v5 = 0;
  v24[0] = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  v6 = -1;
  v24[2] = (PSID)-1LL;
  if ( !lpFileName || !a2 )
  {
    v7 = 2147942487LL;
    v8 = -2147024809;
LABEL_3:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
    goto LABEL_29;
  }
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pSid) )
    goto LABEL_6;
  if ( (unsigned int)GetCurrentUserSID(v24) )
  {
    v12 = pSid;
    v5 = v24[0];
    LengthSid = GetLengthSid(v24[0]);
    v14 = LengthSid + GetLengthSid(v12) + 24;
    ProcessHeap = GetProcessHeap();
    v16 = (struct _ACL *)HeapAlloc(ProcessHeap, 0, v14);
    v4 = v16;
    if ( !v16 )
    {
      v4 = 0;
      v8 = -2147024882;
      goto LABEL_11;
    }
    if ( !InitializeAcl(v16, v14, 2u)
      || !AddAccessAllowedAce(v4, 2u, 0x10000000u, pSid)
      || !AddAccessAllowedAce(v4, 2u, 0x10000000u, v5) )
    {
      goto LABEL_6;
    }
    FileW = CreateFileW(lpFileName, 0xC0040000, 1u, 0, 4u, 0x8200000u, 0);
    v18 = FileW;
    if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v6 = -1;
LABEL_6:
      LastError = GetLastError();
      v8 = LastError;
      if ( !LastError )
      {
        v8 = -2147467259;
LABEL_11:
        v7 = v8;
        goto LABEL_3;
      }
      if ( LastError <= 0 )
        goto LABEL_11;
      v10 = (unsigned __int16)LastError;
LABEL_10:
      v8 = v10 | 0x80070000;
      goto LABEL_11;
    }
    v6 = (__int64)FileW;
    v19 = SetSecurityInfo(FileW, SE_FILE_OBJECT, 0x80000004, 0, 0, v4, 0);
    v8 = v19;
    if ( v19 )
    {
      if ( v19 <= 0 )
        goto LABEL_11;
      v10 = (unsigned __int16)v19;
      goto LABEL_10;
    }
    v6 = -1;
    *a2 = v18;
    v8 = 0;
  }
  else
  {
    v11 = GetLastError();
    v8 = v11;
    if ( v11 )
    {
      if ( v11 > 0 )
        v8 = (unsigned __int16)v11 | 0x80070000;
    }
    else
    {
      v8 = -2147467259;
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8);
    v5 = v24[0];
  }
LABEL_29:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v6);
  if ( v5 )
  {
    v20 = GetProcessHeap();
    HeapFree(v20, 0, v5);
  }
  if ( pSid )
  {
    FreeSid(pSid);
    pSid = 0;
  }
  if ( v4 )
  {
    v21 = GetProcessHeap();
    HeapFree(v21, 0, v4);
  }
  return v8;
}

```

## disassembly

```asm
0x18004cd4c  mov     [rsp-8+arg_10], rbx
0x18004cd51  push    rbp
0x18004cd52  push    rsi
0x18004cd53  push    rdi
0x18004cd54  push    r12
0x18004cd56  push    r13
0x18004cd58  push    r14
0x18004cd5a  push    r15
0x18004cd5c  lea     rbp, [rsp-27h]
0x18004cd61  sub     rsp, 90h
0x18004cd68  mov     rax, cs:__security_cookie
0x18004cd6f  xor     rax, rsp
0x18004cd72  mov     [rbp+57h+var_38], rax
0x18004cd76  mov     r12, rdx
0x18004cd79  mov     r15, rcx
0x18004cd7c  xor     r13d, r13d
0x18004cd7f  mov     ebx, r13d
0x18004cd82  mov     [rbp+57h+var_50], rbx
0x18004cd86  mov     [rbp+57h+var_60], r13
0x18004cd8a  mov     r14d, r13d
0x18004cd8d  mov     [rbp+57h+var_58], r13
0x18004cd91  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r13d
0x18004cd95  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18004cd9b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004cd9f  mov     [rbp+57h+var_48], rdi
0x18004cda3  test    rcx, rcx
0x18004cda6  jnz     short loc_18004CDB9
0x18004cda8  mov     ecx, 80070057h
0x18004cdad  mov     esi, ecx
0x18004cdaf  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18004cdb4  jmp     loc_18004CF8C
0x18004cdb9  test    r12, r12
0x18004cdbc  jz      short loc_18004CDA8
0x18004cdbe  lea     rax, [rbp+57h+var_60]
0x18004cdc2  mov     [rsp+0C0h+pSid], rax; pSid
0x18004cdc7  mov     [rsp+0C0h+nSubAuthority7], r13d; nSubAuthority7
0x18004cdcc  mov     [rsp+0C0h+nSubAuthority6], r13d; nSubAuthority6
0x18004cdd1  mov     [rsp+0C0h+nSubAuthority5], r13d; nSubAuthority5
0x18004cdd6  mov     [rsp+0C0h+nSubAuthority4], r13d; nSubAuthority4
0x18004cddb  mov     [rsp+0C0h+nSubAuthority3], r13d; nSubAuthority3
0x18004cde0  mov     [rsp+0C0h+nSubAuthority2], r13d; nSubAuthority2
0x18004cde5  mov     r9d, 220h; nSubAuthority1
0x18004cdeb  mov     r8d, 20h ; ' '; nSubAuthority0
0x18004cdf1  mov     dl, 2; nSubAuthorityCount
0x18004cdf3  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18004cdf7  call    cs:__imp_AllocateAndInitializeSid
0x18004cdfd  test    eax, eax
0x18004cdff  jnz     short loc_18004CE23
0x18004ce01  call    cs:__imp_GetLastError
0x18004ce07  mov     esi, eax
0x18004ce09  test    eax, eax
0x18004ce0b  jnz     short loc_18004CE14
0x18004ce0d  mov     esi, 80004005h
0x18004ce12  jmp     short loc_18004CE1F
0x18004ce14  jle     short loc_18004CE1F
0x18004ce16  movzx   esi, ax
0x18004ce19  or      esi, 80070000h
0x18004ce1f  mov     ecx, esi
0x18004ce21  jmp     short loc_18004CDAF
0x18004ce23  lea     rcx, [rbp+57h+var_58]
0x18004ce27  call    GetCurrentUserSID
0x18004ce2c  test    eax, eax
0x18004ce2e  jnz     short loc_18004CE5E
0x18004ce30  call    cs:__imp_GetLastError
0x18004ce36  mov     esi, eax
0x18004ce38  test    eax, eax
0x18004ce3a  jnz     short loc_18004CE43
0x18004ce3c  mov     esi, 80004005h
0x18004ce41  jmp     short loc_18004CE4E
0x18004ce43  jle     short loc_18004CE4E
0x18004ce45  movzx   esi, ax
0x18004ce48  or      esi, 80070000h
0x18004ce4e  mov     ecx, esi
0x18004ce50  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18004ce55  mov     r14, [rbp+57h+var_58]
0x18004ce59  jmp     loc_18004CF8C
0x18004ce5e  mov     rsi, [rbp+57h+var_60]
0x18004ce62  mov     r14, [rbp+57h+var_58]
0x18004ce66  mov     rcx, r14; pSid
0x18004ce69  call    cs:__imp_GetLengthSid
0x18004ce6f  mov     ebx, eax
0x18004ce71  mov     rcx, rsi; pSid
0x18004ce74  call    cs:__imp_GetLengthSid
0x18004ce7a  lea     esi, [rax+18h]
0x18004ce7d  add     esi, ebx
0x18004ce7f  call    cs:__imp_GetProcessHeap
0x18004ce85  mov     rcx, rax; hHeap
0x18004ce88  mov     r8d, esi; dwBytes
0x18004ce8b  xor     edx, edx; dwFlags
0x18004ce8d  call    cs:__imp_HeapAlloc
0x18004ce93  mov     rbx, rax
0x18004ce96  test    rax, rax
0x18004ce99  jnz     short loc_18004CEA8
0x18004ce9b  mov     rbx, r13
0x18004ce9e  mov     esi, 8007000Eh
0x18004cea3  jmp     loc_18004CE1F
0x18004cea8  mov     r8d, 2; dwAclRevision
0x18004ceae  mov     edx, esi; nAclLength
0x18004ceb0  mov     rcx, rbx; pAcl
0x18004ceb3  call    cs:__imp_InitializeAcl
0x18004ceb9  test    eax, eax
0x18004cebb  jz      loc_18004CE01
0x18004cec1  mov     r9, [rbp+57h+var_60]; pSid
0x18004cec5  mov     esi, 2
0x18004ceca  mov     r8d, 10000000h; AccessMask
0x18004ced0  mov     edx, esi; dwAceRevision
0x18004ced2  mov     rcx, rbx; pAcl
0x18004ced5  call    cs:__imp_AddAccessAllowedAce
0x18004cedb  test    eax, eax
0x18004cedd  jz      loc_18004CE01
0x18004cee3  mov     r9, r14; pSid
0x18004cee6  mov     r8d, 10000000h; AccessMask
0x18004ceec  mov     edx, esi; dwAceRevision
0x18004ceee  mov     rcx, rbx; pAcl
0x18004cef1  call    cs:__imp_AddAccessAllowedAce
0x18004cef7  test    eax, eax
0x18004cef9  jz      loc_18004CE01
0x18004ceff  mov     qword ptr [rsp+0C0h+nSubAuthority4], r13; hTemplateFile
0x18004cf04  mov     [rsp+0C0h+nSubAuthority3], 8200000h; dwFlagsAndAttributes
0x18004cf0c  mov     [rsp+0C0h+nSubAuthority2], 4; dwCreationDisposition
0x18004cf14  xor     r9d, r9d; lpSecurityAttributes
0x18004cf17  lea     esi, [r9+1]
0x18004cf1b  mov     r8d, esi; dwShareMode
0x18004cf1e  mov     edx, 0C0040000h; dwDesiredAccess
0x18004cf23  mov     rcx, r15; lpFileName
0x18004cf26  call    cs:__imp_CreateFileW
0x18004cf2c  mov     r15, rax
0x18004cf2f  lea     rcx, [rax+1]
0x18004cf33  test    rcx, 0FFFFFFFFFFFFFFFEh
0x18004cf3a  jnz     short loc_18004CF45
0x18004cf3c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004cf40  jmp     loc_18004CE01
0x18004cf45  mov     rdi, r15
0x18004cf48  mov     qword ptr [rsp+0C0h+nSubAuthority4], r13; pSacl
0x18004cf4d  mov     qword ptr [rsp+0C0h+nSubAuthority3], rbx; pDacl
0x18004cf52  mov     qword ptr [rsp+0C0h+nSubAuthority2], r13; psidGroup
0x18004cf57  xor     r9d, r9d; psidOwner
0x18004cf5a  mov     r8d, 80000004h; SecurityInfo
0x18004cf60  mov     edx, esi; ObjectType
0x18004cf62  mov     rcx, r15; handle
0x18004cf65  call    cs:__imp_SetSecurityInfo
0x18004cf6b  mov     esi, eax
0x18004cf6d  test    eax, eax
0x18004cf6f  jz      short loc_18004CF81
0x18004cf71  test    eax, eax
0x18004cf73  jle     loc_18004CE1F
0x18004cf79  movzx   esi, si
0x18004cf7c  jmp     loc_18004CE19
0x18004cf81  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004cf85  mov     [r12], r15
0x18004cf89  mov     esi, r13d
0x18004cf8c  mov     ecx, esi
0x18004cf8e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18004cf93  nop
0x18004cf94  lea     rax, [rdi-1]
0x18004cf98  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004cf9c  ja      short loc_18004CFA8
0x18004cf9e  mov     rcx, rdi; hObject
0x18004cfa1  call    cs:__imp_CloseHandle
0x18004cfa7  nop
0x18004cfa8  test    r14, r14
0x18004cfab  jz      short loc_18004CFC2
0x18004cfad  call    cs:__imp_GetProcessHeap
0x18004cfb3  mov     rcx, rax; hHeap
0x18004cfb6  mov     r8, r14; lpMem
0x18004cfb9  xor     edx, edx; dwFlags
0x18004cfbb  call    cs:__imp_HeapFree
0x18004cfc1  nop
0x18004cfc2  mov     rcx, [rbp+57h+var_60]; pSid
0x18004cfc6  test    rcx, rcx
0x18004cfc9  jz      short loc_18004CFD5
0x18004cfcb  call    cs:__imp_FreeSid
0x18004cfd1  mov     [rbp+57h+var_60], r13
0x18004cfd5  test    rbx, rbx
0x18004cfd8  jz      short loc_18004CFEE
0x18004cfda  call    cs:__imp_GetProcessHeap
0x18004cfe0  mov     rcx, rax; hHeap
0x18004cfe3  mov     r8, rbx; lpMem
0x18004cfe6  xor     edx, edx; dwFlags
0x18004cfe8  call    cs:__imp_HeapFree
0x18004cfee  mov     eax, esi
0x18004cff0  mov     rcx, [rbp+57h+var_38]
0x18004cff4  xor     rcx, rsp; StackCookie
0x18004cff7  call    __security_check_cookie
0x18004cffc  mov     rbx, [rsp+0C0h+arg_10]
0x18004d004  add     rsp, 90h
0x18004d00b  pop     r15
0x18004d00d  pop     r14
0x18004d00f  pop     r13
0x18004d011  pop     r12
0x18004d013  pop     rdi
0x18004d014  pop     rsi
0x18004d015  pop     rbp
0x18004d016  retn
```
