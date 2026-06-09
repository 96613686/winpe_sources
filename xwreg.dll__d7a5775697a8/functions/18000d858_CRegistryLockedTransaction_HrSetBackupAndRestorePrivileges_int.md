# CRegistryLockedTransaction::HrSetBackupAndRestorePrivileges(int)

- ea: `0x18000d858`
- end: `0x18000da5c`
- name: `?HrSetBackupAndRestorePrivileges@CRegistryLockedTransaction@@AEAAJH@Z`
- size: `516`
- prototype: `__int64 __fastcall(CRegistryLockedTransaction *__hidden this, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000d294`
- `0x18000d548`

## callees

- `0x180003b90`
- `0x180007820`
- `0x18000d858`
- `0x180012800`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000d8a0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000d8a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000d88e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000d88e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000da14`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000da14`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18000d9d5`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18000d9d5`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18000d8eb`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18000d942`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18000d8eb`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18000d942`

## string_xrefs

- `0x18000d8e2`: `SeBackupPrivilege`
- `0x18000d93b`: `SeRestorePrivilege`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRegistryLockedTransaction::HrSetBackupAndRestorePrivileges(
        CRegistryLockedTransaction *this,
        int a2)
{
  HANDLE CurrentProcess; // rax
  int v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  unsigned int LastErrorHRESULT; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  HANDLE TokenHandle; // [rsp+30h] [rbp-48h] BYREF
  _LUID Luid; // [rsp+38h] [rbp-40h] BYREF
  struct _LUID v13; // [rsp+40h] [rbp-38h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+48h] [rbp-30h] BYREF
  struct _LUID v15; // [rsp+58h] [rbp-20h]
  int v16; // [rsp+60h] [rbp-18h]

  TokenHandle = 0;
  Luid = 0;
  v13 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x20u, &TokenHandle) )
  {
    v4 = 0;
    if ( LookupPrivilegeValueW(0, L"SeBackupPrivilege", &Luid) )
      goto LABEL_12;
    LastErrorHRESULT = GetLastErrorHRESULT();
    v4 = LastErrorHRESULT;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        WPP_b6864e106af034a19631ace060353c02_Traceguids,
        LastErrorHRESULT);
    if ( v4 >= 0 )
    {
LABEL_12:
      if ( !LookupPrivilegeValueW(0, L"SeRestorePrivilege", &v13) )
      {
        v8 = GetLastErrorHRESULT();
        v4 = v8;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_b6864e106af034a19631ace060353c02_Traceguids, v8);
      }
      if ( v4 >= 0 )
      {
        NewState.Privileges[0].Luid = Luid;
        v15 = v13;
        NewState.Privileges[0].Attributes = 0;
        v16 = 0;
        NewState.PrivilegeCount = 2;
        if ( a2 )
        {
          NewState.Privileges[0].Attributes = 2;
          v16 = 2;
        }
        if ( !AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0, 0, 0) )
        {
          v9 = GetLastErrorHRESULT();
          v4 = v9;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_b6864e106af034a19631ace060353c02_Traceguids, v9);
        }
      }
    }
    CloseHandle(TokenHandle);
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v6 = 26;
      goto LABEL_24;
    }
  }
  else
  {
    v4 = GetLastErrorHRESULT();
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v6 = 22;
LABEL_24:
      WPP_SF_D(v5[2], v6, WPP_b6864e106af034a19631ace060353c02_Traceguids, (unsigned int)v4);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000d858  push    rbp
0x18000d85a  push    rbx
0x18000d85b  push    rdi
0x18000d85c  push    r14
0x18000d85e  mov     rbp, rsp
0x18000d861  sub     rsp, 78h
0x18000d865  mov     rax, cs:__security_cookie
0x18000d86c  xor     rax, rsp
0x18000d86f  mov     [rbp+var_10], rax
0x18000d873  mov     r14d, edx
0x18000d876  mov     [rbp+TokenHandle], 0
0x18000d87e  mov     qword ptr [rbp+Luid.LowPart], 0
0x18000d886  mov     qword ptr [rbp+var_38.LowPart], 0
0x18000d88e  call    cs:__imp_GetCurrentProcess
0x18000d894  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18000d898  mov     edx, 20h ; ' '; DesiredAccess
0x18000d89d  mov     rcx, rax; ProcessHandle
0x18000d8a0  call    cs:__imp_OpenProcessToken
0x18000d8a6  test    eax, eax
0x18000d8a8  jnz     short loc_18000D8DC
0x18000d8aa  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18000d8af  mov     ebx, eax
0x18000d8b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d8b8  lea     rdi, WPP_GLOBAL_Control
0x18000d8bf  cmp     rcx, rdi
0x18000d8c2  jz      loc_18000DA44
0x18000d8c8  test    byte ptr [rcx+1Ch], 4
0x18000d8cc  jz      loc_18000DA44
0x18000d8d2  mov     edx, 16h
0x18000d8d7  jmp     loc_18000DA31
0x18000d8dc  lea     r8, [rbp+Luid]; lpLuid
0x18000d8e0  xor     ecx, ecx; lpSystemName
0x18000d8e2  lea     rdx, Name; "SeBackupPrivilege"
0x18000d8e9  xor     ebx, ebx
0x18000d8eb  call    cs:__imp_LookupPrivilegeValueW
0x18000d8f1  lea     rdi, WPP_GLOBAL_Control
0x18000d8f8  test    eax, eax
0x18000d8fa  jnz     short loc_18000D935
0x18000d8fc  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18000d901  mov     ebx, eax
0x18000d903  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d90a  cmp     rcx, rdi
0x18000d90d  jz      short loc_18000D92D
0x18000d90f  test    byte ptr [rcx+1Ch], 4
0x18000d913  jz      short loc_18000D92D
0x18000d915  mov     rcx, [rcx+10h]
0x18000d919  lea     r8, WPP_b6864e106af034a19631ace060353c02_Traceguids
0x18000d920  mov     edx, 17h
0x18000d925  mov     r9d, eax
0x18000d928  call    WPP_SF_D
0x18000d92d  test    ebx, ebx
0x18000d92f  js      loc_18000DA10
0x18000d935  lea     r8, [rbp+var_38]; lpLuid
0x18000d939  xor     ecx, ecx; lpSystemName
0x18000d93b  lea     rdx, aSerestoreprivi; "SeRestorePrivilege"
0x18000d942  call    cs:__imp_LookupPrivilegeValueW
0x18000d948  test    eax, eax
0x18000d94a  jnz     short loc_18000D97D
0x18000d94c  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18000d951  mov     ebx, eax
0x18000d953  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d95a  cmp     rcx, rdi
0x18000d95d  jz      short loc_18000D97D
0x18000d95f  test    byte ptr [rcx+1Ch], 4
0x18000d963  jz      short loc_18000D97D
0x18000d965  mov     rcx, [rcx+10h]
0x18000d969  lea     r8, WPP_b6864e106af034a19631ace060353c02_Traceguids
0x18000d970  mov     edx, 18h
0x18000d975  mov     r9d, eax
0x18000d978  call    WPP_SF_D
0x18000d97d  test    ebx, ebx
0x18000d97f  js      loc_18000DA10
0x18000d985  mov     rax, qword ptr [rbp+Luid.LowPart]
0x18000d989  mov     ecx, 2
0x18000d98e  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rax
0x18000d992  mov     rax, qword ptr [rbp+var_38.LowPart]
0x18000d996  mov     [rbp+var_20], rax
0x18000d99a  mov     [rbp+NewState.Privileges.Attributes], 0
0x18000d9a1  mov     [rbp+var_18], 0
0x18000d9a8  mov     [rbp+NewState.PrivilegeCount], ecx
0x18000d9ab  test    r14d, r14d
0x18000d9ae  jz      short loc_18000D9B6
0x18000d9b0  mov     [rbp+NewState.Privileges.Attributes], ecx
0x18000d9b3  mov     [rbp+var_18], ecx
0x18000d9b6  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18000d9ba  lea     r8, [rbp+NewState]; NewState
0x18000d9be  mov     [rsp+78h+ReturnLength], 0; ReturnLength
0x18000d9c7  xor     r9d, r9d; BufferLength
0x18000d9ca  xor     edx, edx; DisableAllPrivileges
0x18000d9cc  mov     [rsp+78h+PreviousState], 0; PreviousState
0x18000d9d5  call    cs:__imp_AdjustTokenPrivileges
0x18000d9db  test    eax, eax
0x18000d9dd  jnz     short loc_18000DA10
0x18000d9df  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18000d9e4  mov     ebx, eax
0x18000d9e6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d9ed  cmp     rcx, rdi
0x18000d9f0  jz      short loc_18000DA10
0x18000d9f2  test    byte ptr [rcx+1Ch], 4
0x18000d9f6  jz      short loc_18000DA10
0x18000d9f8  mov     rcx, [rcx+10h]
0x18000d9fc  lea     r8, WPP_b6864e106af034a19631ace060353c02_Traceguids
0x18000da03  mov     edx, 19h
0x18000da08  mov     r9d, eax
0x18000da0b  call    WPP_SF_D
0x18000da10  mov     rcx, [rbp+TokenHandle]; hObject
0x18000da14  call    cs:__imp_CloseHandle
0x18000da1a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da21  cmp     rcx, rdi
0x18000da24  jz      short loc_18000DA44
0x18000da26  test    byte ptr [rcx+1Ch], 10h
0x18000da2a  jz      short loc_18000DA44
0x18000da2c  mov     edx, 1Ah
0x18000da31  mov     rcx, [rcx+10h]
0x18000da35  lea     r8, WPP_b6864e106af034a19631ace060353c02_Traceguids
0x18000da3c  mov     r9d, ebx
0x18000da3f  call    WPP_SF_D
0x18000da44  mov     eax, ebx
0x18000da46  mov     rcx, [rbp+var_10]
0x18000da4a  xor     rcx, rsp; StackCookie
0x18000da4d  call    __security_check_cookie
0x18000da52  add     rsp, 78h
0x18000da56  pop     r14
0x18000da58  pop     rdi
0x18000da59  pop     rbx
0x18000da5a  pop     rbp
0x18000da5b  retn
```
