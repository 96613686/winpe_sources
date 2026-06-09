# CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::UpdateFileSize(unsigned __int64)

- ea: `0x180027c80`
- end: `0x1800280c7`
- name: `?UpdateFileSize@?$CBufferedFileWriter@VCBufferedFileWriterConnector@@$1?OnWriteDone@1@QEAAX_KK@Z$1?ReleaseBuffer@1@QEAAXPEAX0K@Z$1?OnError@1@QEAAX0KK@Z@@QEAAK_K@Z`
- size: `1095`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, LONGLONG ValidDataLength)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180028370`

## callees

- `0x180027c80`
- `0x1800283e4`
- `0x1800284e0`
- `0x180030390`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180027f11`
- `KERNEL32!CreateFileW` at `0x180027f11`
- `KERNEL32!SetFilePointerEx` at `0x180027fdb`
- `KERNEL32!SetFilePointerEx` at `0x180027fdb`
- `KERNEL32!EnterCriticalSection` at `0x180027cb6`
- `KERNEL32!EnterCriticalSection` at `0x180027cb6`
- `KERNEL32!SetEndOfFile` at `0x180028006`
- `KERNEL32!SetEndOfFile` at `0x180028006`
- `KERNEL32!LeaveCriticalSection` at `0x180027f98`
- `KERNEL32!LeaveCriticalSection` at `0x180027f98`
- `KERNEL32!GetLastError` at `0x180027d45`
- `KERNEL32!GetLastError` at `0x180027d7d`
- `KERNEL32!GetLastError` at `0x180027dd5`
- `KERNEL32!GetLastError` at `0x180027e06`
- `KERNEL32!GetLastError` at `0x180027e53`
- `KERNEL32!GetLastError` at `0x180027eb5`
- `KERNEL32!GetLastError` at `0x180027f2b`
- `KERNEL32!GetLastError` at `0x180027feb`
- `KERNEL32!GetLastError` at `0x180028016`
- `KERNEL32!GetLastError` at `0x18002804a`
- `KERNEL32!GetLastError` at `0x180028095`
- `KERNEL32!GetLastError` at `0x180027d45`
- `KERNEL32!GetLastError` at `0x180027d7d`
- `KERNEL32!GetLastError` at `0x180027dd5`
- `KERNEL32!GetLastError` at `0x180027e06`
- `KERNEL32!GetLastError` at `0x180027e53`
- `KERNEL32!GetLastError` at `0x180027eb5`
- `KERNEL32!GetLastError` at `0x180027f2b`
- `KERNEL32!GetLastError` at `0x180027feb`
- `KERNEL32!GetLastError` at `0x180028016`
- `KERNEL32!GetLastError` at `0x18002804a`
- `KERNEL32!GetLastError` at `0x180028095`
- `KERNEL32!SetFileValidData` at `0x18002803a`
- `KERNEL32!SetFileValidData` at `0x18002803a`
- `KERNEL32!CloseHandle` at `0x180027edf`
- `KERNEL32!CloseHandle` at `0x180027f85`
- `KERNEL32!CloseHandle` at `0x180027edf`
- `KERNEL32!CloseHandle` at `0x180027f85`
- `KERNEL32!GetCurrentThread` at `0x180027d15`
- `KERNEL32!GetCurrentThread` at `0x180027d15`
- `KERNEL32!GetCurrentProcess` at `0x180027d58`
- `KERNEL32!GetCurrentProcess` at `0x180027d58`
- `ADVAPI32!OpenProcessToken` at `0x180027d6d`
- `ADVAPI32!OpenProcessToken` at `0x180027d6d`
- `ADVAPI32!OpenThreadToken` at `0x180027d31`
- `ADVAPI32!OpenThreadToken` at `0x180027d31`
- `ADVAPI32!AdjustTokenPrivileges` at `0x180027ea5`
- `ADVAPI32!AdjustTokenPrivileges` at `0x180027f70`
- `ADVAPI32!AdjustTokenPrivileges` at `0x180028081`
- `ADVAPI32!AdjustTokenPrivileges` at `0x180027ea5`
- `ADVAPI32!AdjustTokenPrivileges` at `0x180027f70`
- `ADVAPI32!AdjustTokenPrivileges` at `0x180028081`
- `ADVAPI32!PrivilegeCheck` at `0x180027e43`
- `ADVAPI32!PrivilegeCheck` at `0x180027e43`
- `ADVAPI32!LookupPrivilegeValueW` at `0x180027df6`
- `ADVAPI32!LookupPrivilegeValueW` at `0x180027df6`

## string_xrefs

- `0x180027d91`: `onecore\base\Eco\WDS\wdslib\common\inc\BufferedFileWriter.h`
- `0x180027f3f`: `onecore\base\Eco\WDS\wdslib\common\inc\BufferedFileWriter.h`
- `0x1800280a7`: `onecore\base\Eco\WDS\wdslib\common\inc\BufferedFileWriter.h`
- `0x180027def`: `SeManageVolumePrivilege`

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
0x180027c80  mov     [rsp-8+arg_10], rbx
0x180027c85  push    rbp
0x180027c86  push    rsi
0x180027c87  push    rdi
0x180027c88  push    r12
0x180027c8a  push    r13
0x180027c8c  push    r14
0x180027c8e  push    r15
0x180027c90  lea     rbp, [rsp-27h]
0x180027c95  sub     rsp, 0D0h
0x180027c9c  mov     rax, cs:__security_cookie
0x180027ca3  xor     rax, rsp
0x180027ca6  mov     [rbp+57h+var_40], rax
0x180027caa  xor     r12d, r12d
0x180027cad  mov     rsi, rdx
0x180027cb0  mov     ebx, r12d
0x180027cb3  mov     rdi, rcx
0x180027cb6  call    cs:__imp_EnterCriticalSection
0x180027cbd  nop     dword ptr [rax+rax+00h]
0x180027cc2  xor     eax, eax
0x180027cc4  mov     qword ptr [rbp+57h+Luid.LowPart], r12
0x180027cc8  xorps   xmm0, xmm0
0x180027ccb  mov     [rbp+57h+var_90], rax
0x180027ccf  mov     [rbp+57h+var_88], eax
0x180027cd2  xorps   xmm1, xmm1
0x180027cd5  mov     [rbp+57h+var_50], rax
0x180027cd9  mov     r14d, r12d
0x180027cdc  mov     [rbp+57h+var_48], eax
0x180027cdf  mov     rax, 7FFFFFFFFFFFFFFFh
0x180027ce9  mov     [rbp+57h+TokenHandle], r12
0x180027ced  mov     [rbp+57h+pfResult], r12d
0x180027cf1  mov     [rbp+57h+var_B0], r12d
0x180027cf5  movups  xmmword ptr [rbp+57h+RequiredPrivileges], xmm0
0x180027cf9  movups  xmmword ptr [rbp+57h+RequiredPrivileges+10h], xmm0
0x180027cfd  movups  xmmword ptr [rbp+57h+NewState.PrivilegeCount], xmm1
0x180027d01  movups  xmmword ptr [rbp+57h+var_60.PrivilegeCount], xmm0
0x180027d05  cmp     rsi, rax
0x180027d08  ja      loc_180027DAF
0x180027d0e  mov     r15, rsi
0x180027d11  mov     [rdi+38h], rsi
0x180027d15  call    cs:__imp_GetCurrentThread
0x180027d1c  nop     dword ptr [rax+rax+00h]
0x180027d21  xor     r8d, r8d; OpenAsSelf
0x180027d24  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180027d28  mov     rcx, rax; ThreadHandle
0x180027d2b  lea     esi, [r8+28h]
0x180027d2f  mov     edx, esi; DesiredAccess
0x180027d31  call    cs:__imp_OpenThreadToken
0x180027d38  nop     dword ptr [rax+rax+00h]
0x180027d3d  test    eax, eax
0x180027d3f  jnz     loc_180027DE9
0x180027d45  call    cs:__imp_GetLastError
0x180027d4c  nop     dword ptr [rax+rax+00h]
0x180027d51  cmp     eax, 3F0h
0x180027d56  jnz     short loc_180027DD5
0x180027d58  call    cs:__imp_GetCurrentProcess
0x180027d5f  nop     dword ptr [rax+rax+00h]
0x180027d64  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x180027d68  mov     edx, esi; DesiredAccess
0x180027d6a  mov     rcx, rax; ProcessHandle
0x180027d6d  call    cs:__imp_OpenProcessToken
0x180027d74  nop     dword ptr [rax+rax+00h]
0x180027d79  test    eax, eax
0x180027d7b  jnz     short loc_180027DE9
0x180027d7d  call    cs:__imp_GetLastError
0x180027d84  nop     dword ptr [rax+rax+00h]
0x180027d89  mov     r9d, 1C3h
0x180027d8f  mov     ecx, eax
0x180027d91  lea     r8, aOnecoreBaseEco_26; "onecore\\base\\Eco\\WDS\\wdslib\\common"...
0x180027d98  call    ElValidateWin32_14
0x180027d9d  mov     ebx, eax
0x180027d9f  test    eax, eax
0x180027da1  jnz     loc_180027F7C
0x180027da7  lea     ebx, [rax+1Fh]
0x180027daa  jmp     loc_180027F7C
0x180027daf  mov     ecx, 80070216h
0x180027db4  mov     r9d, 1A4h
0x180027dba  or      r15, 0FFFFFFFFFFFFFFFFh
0x180027dbe  call    ElValidateHr_8
0x180027dc3  test    eax, eax
0x180027dc5  jns     loc_180027D11
0x180027dcb  mov     ebx, 216h
0x180027dd0  jmp     loc_180027F7C
0x180027dd5  call    cs:__imp_GetLastError
0x180027ddc  nop     dword ptr [rax+rax+00h]
0x180027de1  mov     r9d, 1C8h
0x180027de7  jmp     short loc_180027D8F
0x180027de9  lea     r8, [rbp+57h+Luid]; lpLuid
0x180027ded  xor     ecx, ecx; lpSystemName
0x180027def  lea     rdx, aSemanagevolume; "SeManageVolumePrivilege"
0x180027df6  call    cs:__imp_LookupPrivilegeValueW
0x180027dfd  nop     dword ptr [rax+rax+00h]
0x180027e02  test    eax, eax
0x180027e04  jnz     short loc_180027E1D
0x180027e06  call    cs:__imp_GetLastError
0x180027e0d  nop     dword ptr [rax+rax+00h]
0x180027e12  mov     r9d, 1D2h
0x180027e18  jmp     loc_180027D8F
0x180027e1d  mov     rax, qword ptr [rbp+57h+Luid.LowPart]
0x180027e21  lea     r8, [rbp+57h+pfResult]; pfResult
0x180027e25  mov     rcx, [rbp+57h+TokenHandle]; ClientToken
0x180027e29  lea     rdx, [rbp+57h+RequiredPrivileges]; RequiredPrivileges
0x180027e2d  mov     esi, 1
0x180027e32  mov     qword ptr [rbp+57h+RequiredPrivileges+8], rax
0x180027e36  mov     dword ptr [rbp+57h+RequiredPrivileges], esi
0x180027e39  mov     dword ptr [rbp+57h+RequiredPrivileges+4], esi
0x180027e3c  mov     dword ptr [rbp+57h+RequiredPrivileges+10h], 80000000h
0x180027e43  call    cs:__imp_PrivilegeCheck
0x180027e4a  nop     dword ptr [rax+rax+00h]
0x180027e4f  test    eax, eax
0x180027e51  jnz     short loc_180027E6A
0x180027e53  call    cs:__imp_GetLastError
0x180027e5a  nop     dword ptr [rax+rax+00h]
0x180027e5f  mov     r9d, 1E0h
0x180027e65  jmp     loc_180027D8F
0x180027e6a  mov     r13d, 2
0x180027e70  cmp     [rbp+57h+pfResult], r12d
0x180027e74  jnz     short loc_180027ED5
0x180027e76  mov     rax, qword ptr [rbp+57h+Luid.LowPart]
0x180027e7a  lea     r9d, [r13+1Ah]; BufferLength
0x180027e7e  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180027e82  lea     r8, [rbp+57h+NewState]; NewState
0x180027e86  mov     qword ptr [rbp+57h+NewState.Privileges.Luid.LowPart], rax
0x180027e8a  xor     edx, edx; DisableAllPrivileges
0x180027e8c  lea     rax, [rbp+57h+var_B0]
0x180027e90  mov     [rbp+57h+NewState.PrivilegeCount], esi
0x180027e93  mov     [rsp+100h+ReturnLength], rax; ReturnLength
0x180027e98  lea     rax, [rbp+57h+var_60]
0x180027e9c  mov     [rsp+100h+PreviousState], rax; PreviousState
0x180027ea1  mov     [rbp+57h+NewState.Privileges.Attributes], r13d
0x180027ea5  call    cs:__imp_AdjustTokenPrivileges
0x180027eac  nop     dword ptr [rax+rax+00h]
0x180027eb1  test    eax, eax
0x180027eb3  jz      short loc_180027ECB
0x180027eb5  call    cs:__imp_GetLastError
0x180027ebc  nop     dword ptr [rax+rax+00h]
0x180027ec1  test    eax, eax
0x180027ec3  jnz     short loc_180027EC8
0x180027ec5  mov     [rbp+57h+pfResult], esi
0x180027ec8  mov     r14d, esi
0x180027ecb  cmp     [rbp+57h+pfResult], r12d
0x180027ecf  jz      loc_180027FCE
0x180027ed5  mov     rcx, [rdi+30h]; hObject
0x180027ed9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180027edd  jz      short loc_180027EF0
0x180027edf  call    cs:__imp_CloseHandle
0x180027ee6  nop     dword ptr [rax+rax+00h]
0x180027eeb  or      qword ptr [rdi+30h], 0FFFFFFFFFFFFFFFFh
0x180027ef0  mov     rcx, [rdi+50h]; lpFileName
0x180027ef4  xor     r9d, r9d; lpSecurityAttributes
0x180027ef7  mov     [rsp+100h+hTemplateFile], r12; hTemplateFile
0x180027efc  xor     r8d, r8d; dwShareMode
0x180027eff  mov     dword ptr [rsp+100h+ReturnLength], 80h; dwFlagsAndAttributes
0x180027f07  mov     edx, 40000000h; dwDesiredAccess
0x180027f0c  mov     dword ptr [rsp+100h+PreviousState], r13d; dwCreationDisposition
0x180027f11  call    cs:__imp_CreateFileW
0x180027f18  nop     dword ptr [rax+rax+00h]
0x180027f1d  mov     [rdi+30h], rax
0x180027f21  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180027f25  jnz     loc_180027FCE
0x180027f2b  call    cs:__imp_GetLastError
0x180027f32  nop     dword ptr [rax+rax+00h]
0x180027f37  mov     r9d, 21Ah
0x180027f3d  mov     ecx, eax
0x180027f3f  lea     r8, aOnecoreBaseEco_26; "onecore\\base\\Eco\\WDS\\wdslib\\common"...
0x180027f46  call    ElValidateWin32_14
0x180027f4b  mov     ebx, eax
0x180027f4d  test    eax, eax
0x180027f4f  jnz     short loc_180027F54
0x180027f51  lea     ebx, [rax+1Fh]
0x180027f54  test    r14d, r14d
0x180027f57  jz      short loc_180027F7C
0x180027f59  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180027f5d  lea     r8, [rbp+57h+var_60]; NewState
0x180027f61  mov     [rsp+100h+ReturnLength], r12; ReturnLength
0x180027f66  xor     r9d, r9d; BufferLength
0x180027f69  xor     edx, edx; DisableAllPrivileges
0x180027f6b  mov     [rsp+100h+PreviousState], r12; PreviousState
0x180027f70  call    cs:__imp_AdjustTokenPrivileges
0x180027f77  nop     dword ptr [rax+rax+00h]
0x180027f7c  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180027f80  test    rcx, rcx
0x180027f83  jz      short loc_180027F95
0x180027f85  call    cs:__imp_CloseHandle
0x180027f8c  nop     dword ptr [rax+rax+00h]
0x180027f91  mov     [rbp+57h+TokenHandle], r12
0x180027f95  mov     rcx, rdi; lpCriticalSection
0x180027f98  call    cs:__imp_LeaveCriticalSection
0x180027f9f  nop     dword ptr [rax+rax+00h]
0x180027fa4  mov     eax, ebx
0x180027fa6  mov     rcx, [rbp+57h+var_40]
0x180027faa  xor     rcx, rsp; StackCookie
0x180027fad  call    __security_check_cookie
0x180027fb2  mov     rbx, [rsp+100h+arg_10]
0x180027fba  add     rsp, 0D0h
0x180027fc1  pop     r15
0x180027fc3  pop     r14
0x180027fc5  pop     r13
0x180027fc7  pop     r12
0x180027fc9  pop     rdi
0x180027fca  pop     rsi
0x180027fcb  pop     rbp
0x180027fcc  retn
0x180027fce  mov     rcx, [rdi+30h]; hFile
0x180027fd2  xor     r9d, r9d; dwMoveMethod
0x180027fd5  xor     r8d, r8d; lpNewFilePointer
0x180027fd8  mov     rdx, r15; liDistanceToMove
0x180027fdb  call    cs:__imp_SetFilePointerEx
0x180027fe2  nop     dword ptr [rax+rax+00h]
0x180027fe7  test    eax, eax
0x180027fe9  jnz     short loc_180028002
0x180027feb  call    cs:__imp_GetLastError
0x180027ff2  nop     dword ptr [rax+rax+00h]
0x180027ff7  mov     r9d, 22Ah
0x180027ffd  jmp     loc_180027F3D
0x180028002  mov     rcx, [rdi+30h]; hFile
0x180028006  call    cs:__imp_SetEndOfFile
0x18002800d  nop     dword ptr [rax+rax+00h]
0x180028012  test    eax, eax
0x180028014  jnz     short loc_18002802D
0x180028016  call    cs:__imp_GetLastError
0x18002801d  nop     dword ptr [rax+rax+00h]
0x180028022  mov     r9d, 22Fh
0x180028028  jmp     loc_180027F3D
0x18002802d  cmp     [rbp+57h+pfResult], r12d
0x180028031  jz      short loc_180028061
0x180028033  mov     rcx, [rdi+30h]; hFile
0x180028037  mov     rdx, r15; ValidDataLength
0x18002803a  call    cs:__imp_SetFileValidData
0x180028041  nop     dword ptr [rax+rax+00h]
0x180028046  test    eax, eax
0x180028048  jnz     short loc_180028061
0x18002804a  call    cs:__imp_GetLastError
0x180028051  nop     dword ptr [rax+rax+00h]
0x180028056  mov     r9d, 23Ah
0x18002805c  jmp     loc_180027F3D
0x180028061  test    r14d, r14d
0x180028064  jz      loc_180027F7C
0x18002806a  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18002806e  lea     r8, [rbp+57h+var_60]; NewState
0x180028072  mov     [rsp+100h+ReturnLength], r12; ReturnLength
0x180028077  xor     r9d, r9d; BufferLength
0x18002807a  xor     edx, edx; DisableAllPrivileges
0x18002807c  mov     [rsp+100h+PreviousState], r12; PreviousState
0x180028081  call    cs:__imp_AdjustTokenPrivileges
0x180028088  nop     dword ptr [rax+rax+00h]
0x18002808d  test    eax, eax
0x18002808f  jnz     loc_180027F7C
0x180028095  call    cs:__imp_GetLastError
0x18002809c  nop     dword ptr [rax+rax+00h]
0x1800280a1  mov     r9d, 24Bh
0x1800280a7  lea     r8, aOnecoreBaseEco_26; "onecore\\base\\Eco\\WDS\\wdslib\\common"...
0x1800280ae  mov     ecx, eax
0x1800280b0  call    ElValidateWin32_14
0x1800280b5  mov     ebx, eax
0x1800280b7  test    eax, eax
0x1800280b9  jnz     loc_180027F59
0x1800280bf  lea     ebx, [rax+1Fh]
0x1800280c2  jmp     loc_180027F59
```
