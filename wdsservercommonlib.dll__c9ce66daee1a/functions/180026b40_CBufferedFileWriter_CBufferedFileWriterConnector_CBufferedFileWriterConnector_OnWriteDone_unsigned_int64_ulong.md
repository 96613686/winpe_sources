# CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::UpdateFileSize(unsigned __int64)

- ea: `0x180026b40`
- end: `0x180026f87`
- name: `?UpdateFileSize@?$CBufferedFileWriter@VCBufferedFileWriterConnector@@$1?OnWriteDone@1@QEAAX_KK@Z$1?ReleaseBuffer@1@QEAAXPEAX0K@Z$1?OnError@1@QEAAX0KK@Z@@QEAAK_K@Z`
- size: `1095`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, LONGLONG ValidDataLength)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180027220`

## callees

- `0x180026b40`
- `0x180027294`
- `0x180027390`
- `0x18002f3e0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180026b76`
- `KERNEL32!EnterCriticalSection` at `0x180026b76`
- `KERNEL32!LeaveCriticalSection` at `0x180026e58`
- `KERNEL32!LeaveCriticalSection` at `0x180026e58`
- `KERNEL32!GetLastError` at `0x180026c05`
- `KERNEL32!GetLastError` at `0x180026c3d`
- `KERNEL32!GetLastError` at `0x180026c95`
- `KERNEL32!GetLastError` at `0x180026cc6`
- `KERNEL32!GetLastError` at `0x180026d13`
- `KERNEL32!GetLastError` at `0x180026d75`
- `KERNEL32!GetLastError` at `0x180026deb`
- `KERNEL32!GetLastError` at `0x180026eab`
- `KERNEL32!GetLastError` at `0x180026ed6`
- `KERNEL32!GetLastError` at `0x180026f0a`
- `KERNEL32!GetLastError` at `0x180026f55`
- `KERNEL32!GetLastError` at `0x180026c05`
- `KERNEL32!GetLastError` at `0x180026c3d`
- `KERNEL32!GetLastError` at `0x180026c95`
- `KERNEL32!GetLastError` at `0x180026cc6`
- `KERNEL32!GetLastError` at `0x180026d13`
- `KERNEL32!GetLastError` at `0x180026d75`
- `KERNEL32!GetLastError` at `0x180026deb`
- `KERNEL32!GetLastError` at `0x180026eab`
- `KERNEL32!GetLastError` at `0x180026ed6`
- `KERNEL32!GetLastError` at `0x180026f0a`
- `KERNEL32!GetLastError` at `0x180026f55`
- `KERNEL32!CloseHandle` at `0x180026d9f`
- `KERNEL32!CloseHandle` at `0x180026e45`
- `KERNEL32!CloseHandle` at `0x180026d9f`
- `KERNEL32!CloseHandle` at `0x180026e45`
- `KERNEL32!SetFileValidData` at `0x180026efa`
- `KERNEL32!SetFileValidData` at `0x180026efa`
- `KERNEL32!SetEndOfFile` at `0x180026ec6`
- `KERNEL32!SetEndOfFile` at `0x180026ec6`
- `KERNEL32!SetFilePointerEx` at `0x180026e9b`
- `KERNEL32!SetFilePointerEx` at `0x180026e9b`
- `KERNEL32!GetCurrentThread` at `0x180026bd5`
- `KERNEL32!GetCurrentThread` at `0x180026bd5`
- `KERNEL32!GetCurrentProcess` at `0x180026c18`
- `KERNEL32!GetCurrentProcess` at `0x180026c18`
- `KERNEL32!CreateFileW` at `0x180026dd1`
- `KERNEL32!CreateFileW` at `0x180026dd1`
- `ADVAPI32!OpenThreadToken` at `0x180026bf1`
- `ADVAPI32!OpenThreadToken` at `0x180026bf1`
- `ADVAPI32!AdjustTokenPrivileges` at `0x180026d65`
- `ADVAPI32!AdjustTokenPrivileges` at `0x180026e30`
- `ADVAPI32!AdjustTokenPrivileges` at `0x180026f41`
- `ADVAPI32!AdjustTokenPrivileges` at `0x180026d65`
- `ADVAPI32!AdjustTokenPrivileges` at `0x180026e30`
- `ADVAPI32!AdjustTokenPrivileges` at `0x180026f41`
- `ADVAPI32!PrivilegeCheck` at `0x180026d03`
- `ADVAPI32!PrivilegeCheck` at `0x180026d03`
- `ADVAPI32!LookupPrivilegeValueW` at `0x180026cb6`
- `ADVAPI32!LookupPrivilegeValueW` at `0x180026cb6`
- `ADVAPI32!OpenProcessToken` at `0x180026c2d`
- `ADVAPI32!OpenProcessToken` at `0x180026c2d`

## string_xrefs

- `0x180026c51`: `onecore\base\Eco\WDS\wdslib\common\inc\BufferedFileWriter.h`
- `0x180026dff`: `onecore\base\Eco\WDS\wdslib\common\inc\BufferedFileWriter.h`
- `0x180026f67`: `onecore\base\Eco\WDS\wdslib\common\inc\BufferedFileWriter.h`
- `0x180026caf`: `SeManageVolumePrivilege`

## pseudocode

```c
__int64 __fastcall CBufferedFileWriter<CBufferedFileWriterConnector,&public: void CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::OnError(unsigned __int64,unsigned long,unsigned long)>::UpdateFileSize(
        LPCRITICAL_SECTION lpCriticalSection,
        unsigned __int64 ValidDataLength)
{
  unsigned int v3; // ebx
  __int64 v5; // rdx
  __int64 v6; // r8
  int v7; // r14d
  LONGLONG v8; // r15
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  DWORD LastError; // eax
  __int64 v12; // rdx
  __int64 v13; // r9
  void *v14; // rcx
  HANDLE FileW; // rax
  DWORD v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r9
  DWORD v20; // eax
  __int64 v21; // rdx
  WINBOOL pfResult; // [rsp+40h] [rbp-69h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-61h] BYREF
  DWORD ReturnLength; // [rsp+50h] [rbp-59h] BYREF
  struct _LUID Luid; // [rsp+58h] [rbp-51h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+60h] [rbp-49h] BYREF
  __int64 v27; // [rsp+70h] [rbp-39h]
  int v28; // [rsp+78h] [rbp-31h]
  _BYTE RequiredPrivileges[32]; // [rsp+80h] [rbp-29h] BYREF
  struct _TOKEN_PRIVILEGES PreviousState; // [rsp+A0h] [rbp-9h] BYREF
  __int64 v31; // [rsp+B0h] [rbp+7h]
  int v32; // [rsp+B8h] [rbp+Fh]

  v3 = 0;
  EnterCriticalSection(lpCriticalSection);
  Luid = 0;
  v27 = 0;
  v28 = 0;
  v31 = 0;
  v7 = 0;
  v32 = 0;
  TokenHandle = 0;
  pfResult = 0;
  ReturnLength = 0;
  memset(RequiredPrivileges, 0, sizeof(RequiredPrivileges));
  NewState = 0;
  PreviousState = 0;
  if ( ValidDataLength > 0x7FFFFFFFFFFFFFFFLL )
  {
    v8 = -1;
    if ( (int)ElValidateHr_8(2147942934LL, v5, v6, 420) < 0 )
    {
      v3 = 534;
      goto LABEL_30;
    }
  }
  else
  {
    v8 = ValidDataLength;
  }
  lpCriticalSection[1].OwningThread = (HANDLE)ValidDataLength;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x28u, 0, &TokenHandle) )
  {
    if ( GetLastError() != 1008 )
    {
      LastError = GetLastError();
      v13 = 456;
      goto LABEL_7;
    }
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
    {
      LastError = GetLastError();
      v13 = 451;
      goto LABEL_7;
    }
  }
  if ( !LookupPrivilegeValueW(0, L"SeManageVolumePrivilege", &Luid) )
  {
    LastError = GetLastError();
    v13 = 466;
    goto LABEL_7;
  }
  *(struct _LUID *)&RequiredPrivileges[8] = Luid;
  *(_QWORD *)RequiredPrivileges = 0x100000001LL;
  *(_DWORD *)&RequiredPrivileges[16] = 0x80000000;
  if ( !PrivilegeCheck(TokenHandle, (PPRIVILEGE_SET)RequiredPrivileges, &pfResult) )
  {
    LastError = GetLastError();
    v13 = 480;
LABEL_7:
    v3 = ElValidateWin32_14(LastError, v12, "onecore\\base\\Eco\\WDS\\wdslib\\common\\inc\\BufferedFileWriter.h", v13);
    if ( !v3 )
      v3 = 31;
    goto LABEL_30;
  }
  if ( !pfResult )
  {
    NewState.Privileges[0].Luid = Luid;
    NewState.PrivilegeCount = 1;
    NewState.Privileges[0].Attributes = 2;
    if ( AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x1Cu, &PreviousState, &ReturnLength) )
    {
      if ( !GetLastError() )
        pfResult = 1;
      v7 = 1;
    }
    if ( !pfResult )
      goto LABEL_46;
  }
  v14 = *(void **)&lpCriticalSection[1].LockCount;
  if ( v14 != (void *)-1LL )
  {
    CloseHandle(v14);
    *(_QWORD *)&lpCriticalSection[1].LockCount = -1;
  }
  FileW = CreateFileW(&lpCriticalSection[2].DebugInfo->Type, 0x40000000u, 0, 0, 2u, 0x80u, 0);
  *(_QWORD *)&lpCriticalSection[1].LockCount = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v16 = GetLastError();
    v18 = 538;
  }
  else
  {
LABEL_46:
    if ( SetFilePointerEx(*(HANDLE *)&lpCriticalSection[1].LockCount, (LARGE_INTEGER)v8, 0, 0) )
    {
      if ( SetEndOfFile(*(HANDLE *)&lpCriticalSection[1].LockCount) )
      {
        if ( !pfResult || SetFileValidData(*(HANDLE *)&lpCriticalSection[1].LockCount, v8) )
        {
          if ( !v7 || AdjustTokenPrivileges(TokenHandle, 0, &PreviousState, 0, 0, 0) )
            goto LABEL_30;
          v20 = GetLastError();
          v3 = ElValidateWin32_14(v20, v21, "onecore\\base\\Eco\\WDS\\wdslib\\common\\inc\\BufferedFileWriter.h", 587);
          if ( !v3 )
            v3 = 31;
LABEL_29:
          AdjustTokenPrivileges(TokenHandle, 0, &PreviousState, 0, 0, 0);
          goto LABEL_30;
        }
        v16 = GetLastError();
        v18 = 570;
      }
      else
      {
        v16 = GetLastError();
        v18 = 559;
      }
    }
    else
    {
      v16 = GetLastError();
      v18 = 554;
    }
  }
  v3 = ElValidateWin32_14(v16, v17, "onecore\\base\\Eco\\WDS\\wdslib\\common\\inc\\BufferedFileWriter.h", v18);
  if ( !v3 )
    v3 = 31;
  if ( v7 )
    goto LABEL_29;
LABEL_30:
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  LeaveCriticalSection(lpCriticalSection);
  return v3;
}

```

## disassembly

```asm
0x180026b40  mov     [rsp-8+arg_10], rbx
0x180026b45  push    rbp
0x180026b46  push    rsi
0x180026b47  push    rdi
0x180026b48  push    r12
0x180026b4a  push    r13
0x180026b4c  push    r14
0x180026b4e  push    r15
0x180026b50  lea     rbp, [rsp-27h]
0x180026b55  sub     rsp, 0D0h
0x180026b5c  mov     rax, cs:__security_cookie
0x180026b63  xor     rax, rsp
0x180026b66  mov     [rbp+57h+var_40], rax
0x180026b6a  xor     r12d, r12d
0x180026b6d  mov     rsi, rdx
0x180026b70  mov     ebx, r12d
0x180026b73  mov     rdi, rcx
0x180026b76  call    cs:__imp_EnterCriticalSection
0x180026b7d  nop     dword ptr [rax+rax+00h]
0x180026b82  xor     eax, eax
0x180026b84  mov     qword ptr [rbp+57h+Luid.LowPart], r12
0x180026b88  xorps   xmm0, xmm0
0x180026b8b  mov     [rbp+57h+var_90], rax
0x180026b8f  mov     [rbp+57h+var_88], eax
0x180026b92  xorps   xmm1, xmm1
0x180026b95  mov     [rbp+57h+var_50], rax
0x180026b99  mov     r14d, r12d
0x180026b9c  mov     [rbp+57h+var_48], eax
0x180026b9f  mov     rax, 7FFFFFFFFFFFFFFFh
0x180026ba9  mov     [rbp+57h+TokenHandle], r12
0x180026bad  mov     [rbp+57h+pfResult], r12d
0x180026bb1  mov     [rbp+57h+var_B0], r12d
0x180026bb5  movups  xmmword ptr [rbp+57h+RequiredPrivileges], xmm0
0x180026bb9  movups  xmmword ptr [rbp+57h+RequiredPrivileges+10h], xmm0
0x180026bbd  movups  xmmword ptr [rbp+57h+NewState.PrivilegeCount], xmm1
0x180026bc1  movups  xmmword ptr [rbp+57h+var_60.PrivilegeCount], xmm0
0x180026bc5  cmp     rsi, rax
0x180026bc8  ja      loc_180026C6F
0x180026bce  mov     r15, rsi
0x180026bd1  mov     [rdi+38h], rsi
0x180026bd5  call    cs:__imp_GetCurrentThread
0x180026bdc  nop     dword ptr [rax+rax+00h]
0x180026be1  xor     r8d, r8d; OpenAsSelf
0x180026be4  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180026be8  mov     rcx, rax; ThreadHandle
0x180026beb  lea     esi, [r8+28h]
0x180026bef  mov     edx, esi; DesiredAccess
0x180026bf1  call    cs:__imp_OpenThreadToken
0x180026bf8  nop     dword ptr [rax+rax+00h]
0x180026bfd  test    eax, eax
0x180026bff  jnz     loc_180026CA9
0x180026c05  call    cs:__imp_GetLastError
0x180026c0c  nop     dword ptr [rax+rax+00h]
0x180026c11  cmp     eax, 3F0h
0x180026c16  jnz     short loc_180026C95
0x180026c18  call    cs:__imp_GetCurrentProcess
0x180026c1f  nop     dword ptr [rax+rax+00h]
0x180026c24  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x180026c28  mov     edx, esi; DesiredAccess
0x180026c2a  mov     rcx, rax; ProcessHandle
0x180026c2d  call    cs:__imp_OpenProcessToken
0x180026c34  nop     dword ptr [rax+rax+00h]
0x180026c39  test    eax, eax
0x180026c3b  jnz     short loc_180026CA9
0x180026c3d  call    cs:__imp_GetLastError
0x180026c44  nop     dword ptr [rax+rax+00h]
0x180026c49  mov     r9d, 1C3h
0x180026c4f  mov     ecx, eax
0x180026c51  lea     r8, aOnecoreBaseEco_27; "onecore\\base\\Eco\\WDS\\wdslib\\common"...
0x180026c58  call    ElValidateWin32_14
0x180026c5d  mov     ebx, eax
0x180026c5f  test    eax, eax
0x180026c61  jnz     loc_180026E3C
0x180026c67  lea     ebx, [rax+1Fh]
0x180026c6a  jmp     loc_180026E3C
0x180026c6f  mov     ecx, 80070216h
0x180026c74  mov     r9d, 1A4h
0x180026c7a  or      r15, 0FFFFFFFFFFFFFFFFh
0x180026c7e  call    ElValidateHr_8
0x180026c83  test    eax, eax
0x180026c85  jns     loc_180026BD1
0x180026c8b  mov     ebx, 216h
0x180026c90  jmp     loc_180026E3C
0x180026c95  call    cs:__imp_GetLastError
0x180026c9c  nop     dword ptr [rax+rax+00h]
0x180026ca1  mov     r9d, 1C8h
0x180026ca7  jmp     short loc_180026C4F
0x180026ca9  lea     r8, [rbp+57h+Luid]; lpLuid
0x180026cad  xor     ecx, ecx; lpSystemName
0x180026caf  lea     rdx, aSemanagevolume; "SeManageVolumePrivilege"
0x180026cb6  call    cs:__imp_LookupPrivilegeValueW
0x180026cbd  nop     dword ptr [rax+rax+00h]
0x180026cc2  test    eax, eax
0x180026cc4  jnz     short loc_180026CDD
0x180026cc6  call    cs:__imp_GetLastError
0x180026ccd  nop     dword ptr [rax+rax+00h]
0x180026cd2  mov     r9d, 1D2h
0x180026cd8  jmp     loc_180026C4F
0x180026cdd  mov     rax, qword ptr [rbp+57h+Luid.LowPart]
0x180026ce1  lea     r8, [rbp+57h+pfResult]; pfResult
0x180026ce5  mov     rcx, [rbp+57h+TokenHandle]; ClientToken
0x180026ce9  lea     rdx, [rbp+57h+RequiredPrivileges]; RequiredPrivileges
0x180026ced  mov     esi, 1
0x180026cf2  mov     qword ptr [rbp+57h+RequiredPrivileges+8], rax
0x180026cf6  mov     dword ptr [rbp+57h+RequiredPrivileges], esi
0x180026cf9  mov     dword ptr [rbp+57h+RequiredPrivileges+4], esi
0x180026cfc  mov     dword ptr [rbp+57h+RequiredPrivileges+10h], 80000000h
0x180026d03  call    cs:__imp_PrivilegeCheck
0x180026d0a  nop     dword ptr [rax+rax+00h]
0x180026d0f  test    eax, eax
0x180026d11  jnz     short loc_180026D2A
0x180026d13  call    cs:__imp_GetLastError
0x180026d1a  nop     dword ptr [rax+rax+00h]
0x180026d1f  mov     r9d, 1E0h
0x180026d25  jmp     loc_180026C4F
0x180026d2a  mov     r13d, 2
0x180026d30  cmp     [rbp+57h+pfResult], r12d
0x180026d34  jnz     short loc_180026D95
0x180026d36  mov     rax, qword ptr [rbp+57h+Luid.LowPart]
0x180026d3a  lea     r9d, [r13+1Ah]; BufferLength
0x180026d3e  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180026d42  lea     r8, [rbp+57h+NewState]; NewState
0x180026d46  mov     qword ptr [rbp+57h+NewState.Privileges.Luid.LowPart], rax
0x180026d4a  xor     edx, edx; DisableAllPrivileges
0x180026d4c  lea     rax, [rbp+57h+var_B0]
0x180026d50  mov     [rbp+57h+NewState.PrivilegeCount], esi
0x180026d53  mov     [rsp+100h+ReturnLength], rax; ReturnLength
0x180026d58  lea     rax, [rbp+57h+var_60]
0x180026d5c  mov     [rsp+100h+PreviousState], rax; PreviousState
0x180026d61  mov     [rbp+57h+NewState.Privileges.Attributes], r13d
0x180026d65  call    cs:__imp_AdjustTokenPrivileges
0x180026d6c  nop     dword ptr [rax+rax+00h]
0x180026d71  test    eax, eax
0x180026d73  jz      short loc_180026D8B
0x180026d75  call    cs:__imp_GetLastError
0x180026d7c  nop     dword ptr [rax+rax+00h]
0x180026d81  test    eax, eax
0x180026d83  jnz     short loc_180026D88
0x180026d85  mov     [rbp+57h+pfResult], esi
0x180026d88  mov     r14d, esi
0x180026d8b  cmp     [rbp+57h+pfResult], r12d
0x180026d8f  jz      loc_180026E8E
0x180026d95  mov     rcx, [rdi+30h]; hObject
0x180026d99  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180026d9d  jz      short loc_180026DB0
0x180026d9f  call    cs:__imp_CloseHandle
0x180026da6  nop     dword ptr [rax+rax+00h]
0x180026dab  or      qword ptr [rdi+30h], 0FFFFFFFFFFFFFFFFh
0x180026db0  mov     rcx, [rdi+50h]; lpFileName
0x180026db4  xor     r9d, r9d; lpSecurityAttributes
0x180026db7  mov     [rsp+100h+hTemplateFile], r12; hTemplateFile
0x180026dbc  xor     r8d, r8d; dwShareMode
0x180026dbf  mov     dword ptr [rsp+100h+ReturnLength], 80h; dwFlagsAndAttributes
0x180026dc7  mov     edx, 40000000h; dwDesiredAccess
0x180026dcc  mov     dword ptr [rsp+100h+PreviousState], r13d; dwCreationDisposition
0x180026dd1  call    cs:__imp_CreateFileW
0x180026dd8  nop     dword ptr [rax+rax+00h]
0x180026ddd  mov     [rdi+30h], rax
0x180026de1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180026de5  jnz     loc_180026E8E
0x180026deb  call    cs:__imp_GetLastError
0x180026df2  nop     dword ptr [rax+rax+00h]
0x180026df7  mov     r9d, 21Ah
0x180026dfd  mov     ecx, eax
0x180026dff  lea     r8, aOnecoreBaseEco_27; "onecore\\base\\Eco\\WDS\\wdslib\\common"...
0x180026e06  call    ElValidateWin32_14
0x180026e0b  mov     ebx, eax
0x180026e0d  test    eax, eax
0x180026e0f  jnz     short loc_180026E14
0x180026e11  lea     ebx, [rax+1Fh]
0x180026e14  test    r14d, r14d
0x180026e17  jz      short loc_180026E3C
0x180026e19  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180026e1d  lea     r8, [rbp+57h+var_60]; NewState
0x180026e21  mov     [rsp+100h+ReturnLength], r12; ReturnLength
0x180026e26  xor     r9d, r9d; BufferLength
0x180026e29  xor     edx, edx; DisableAllPrivileges
0x180026e2b  mov     [rsp+100h+PreviousState], r12; PreviousState
0x180026e30  call    cs:__imp_AdjustTokenPrivileges
0x180026e37  nop     dword ptr [rax+rax+00h]
0x180026e3c  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180026e40  test    rcx, rcx
0x180026e43  jz      short loc_180026E55
0x180026e45  call    cs:__imp_CloseHandle
0x180026e4c  nop     dword ptr [rax+rax+00h]
0x180026e51  mov     [rbp+57h+TokenHandle], r12
0x180026e55  mov     rcx, rdi; lpCriticalSection
0x180026e58  call    cs:__imp_LeaveCriticalSection
0x180026e5f  nop     dword ptr [rax+rax+00h]
0x180026e64  mov     eax, ebx
0x180026e66  mov     rcx, [rbp+57h+var_40]
0x180026e6a  xor     rcx, rsp; StackCookie
0x180026e6d  call    __security_check_cookie
0x180026e72  mov     rbx, [rsp+100h+arg_10]
0x180026e7a  add     rsp, 0D0h
0x180026e81  pop     r15
0x180026e83  pop     r14
0x180026e85  pop     r13
0x180026e87  pop     r12
0x180026e89  pop     rdi
0x180026e8a  pop     rsi
0x180026e8b  pop     rbp
0x180026e8c  retn
0x180026e8e  mov     rcx, [rdi+30h]; hFile
0x180026e92  xor     r9d, r9d; dwMoveMethod
0x180026e95  xor     r8d, r8d; lpNewFilePointer
0x180026e98  mov     rdx, r15; liDistanceToMove
0x180026e9b  call    cs:__imp_SetFilePointerEx
0x180026ea2  nop     dword ptr [rax+rax+00h]
0x180026ea7  test    eax, eax
0x180026ea9  jnz     short loc_180026EC2
0x180026eab  call    cs:__imp_GetLastError
0x180026eb2  nop     dword ptr [rax+rax+00h]
0x180026eb7  mov     r9d, 22Ah
0x180026ebd  jmp     loc_180026DFD
0x180026ec2  mov     rcx, [rdi+30h]; hFile
0x180026ec6  call    cs:__imp_SetEndOfFile
0x180026ecd  nop     dword ptr [rax+rax+00h]
0x180026ed2  test    eax, eax
0x180026ed4  jnz     short loc_180026EED
0x180026ed6  call    cs:__imp_GetLastError
0x180026edd  nop     dword ptr [rax+rax+00h]
0x180026ee2  mov     r9d, 22Fh
0x180026ee8  jmp     loc_180026DFD
0x180026eed  cmp     [rbp+57h+pfResult], r12d
0x180026ef1  jz      short loc_180026F21
0x180026ef3  mov     rcx, [rdi+30h]; hFile
0x180026ef7  mov     rdx, r15; ValidDataLength
0x180026efa  call    cs:__imp_SetFileValidData
0x180026f01  nop     dword ptr [rax+rax+00h]
0x180026f06  test    eax, eax
0x180026f08  jnz     short loc_180026F21
0x180026f0a  call    cs:__imp_GetLastError
0x180026f11  nop     dword ptr [rax+rax+00h]
0x180026f16  mov     r9d, 23Ah
0x180026f1c  jmp     loc_180026DFD
0x180026f21  test    r14d, r14d
0x180026f24  jz      loc_180026E3C
0x180026f2a  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180026f2e  lea     r8, [rbp+57h+var_60]; NewState
0x180026f32  mov     [rsp+100h+ReturnLength], r12; ReturnLength
0x180026f37  xor     r9d, r9d; BufferLength
0x180026f3a  xor     edx, edx; DisableAllPrivileges
0x180026f3c  mov     [rsp+100h+PreviousState], r12; PreviousState
0x180026f41  call    cs:__imp_AdjustTokenPrivileges
0x180026f48  nop     dword ptr [rax+rax+00h]
0x180026f4d  test    eax, eax
0x180026f4f  jnz     loc_180026E3C
0x180026f55  call    cs:__imp_GetLastError
0x180026f5c  nop     dword ptr [rax+rax+00h]
0x180026f61  mov     r9d, 24Bh
0x180026f67  lea     r8, aOnecoreBaseEco_27; "onecore\\base\\Eco\\WDS\\wdslib\\common"...
0x180026f6e  mov     ecx, eax
0x180026f70  call    ElValidateWin32_14
0x180026f75  mov     ebx, eax
0x180026f77  test    eax, eax
0x180026f79  jnz     loc_180026E19
0x180026f7f  lea     ebx, [rax+1Fh]
0x180026f82  jmp     loc_180026E19
```
