# CWerService::AdjustTokenPrivilege(wchar_t const *,int,int *)

- ea: `0x180014200`
- end: `0x180014371`
- name: `?AdjustTokenPrivilege@CWerService@@AEAAJPEB_WHPEAH@Z`
- size: `369`
- prototype: `__int64 __fastcall(CWerService *__hidden this, const wchar_t *, int, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180016318`

## callees

- `0x1800029d0`
- `0x180007cf8`
- `0x180011ef8`
- `0x180014200`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001425c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001425c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001426d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001426d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014277`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014342`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014277`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014342`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18001433a`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18001433a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800142cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800142cf`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180014300`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180014300`

## string_xrefs

- `0x1800142f7`: `SeSecurityPrivilege`

## pseudocode

```c
__int64 __fastcall CWerService::AdjustTokenPrivilege(CWerService *this, const wchar_t *a2, int a3, int *a4)
{
  unsigned int v6; // edi
  void **v7; // rbx
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  bool v10; // cc
  BOOL v12; // ebx
  DWORD ReturnLength; // [rsp+30h] [rbp-48h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-40h] BYREF
  _LUID Luid[2]; // [rsp+40h] [rbp-38h] BYREF
  struct _TOKEN_PRIVILEGES PreviousState; // [rsp+50h] [rbp-28h] BYREF

  hObject = 0;
  ReturnLength = 0;
  *(_OWORD *)&Luid[0].LowPart = 0;
  PreviousState = 0;
  if ( !a4 )
  {
    v6 = -2147024809;
LABEL_9:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 123, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids, v6);
    goto LABEL_12;
  }
  *a4 = 0;
  v7 = (void **)tlx::replace<tlx::file_handle_traits>(&hObject);
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x28u, v7)
    || (Luid[0].LowPart = 1, !LookupPrivilegeValueW(0, L"SeSecurityPrivilege", (PLUID)&Luid[0].HighPart)) )
  {
    LastError = GetLastError();
    v6 = LastError;
LABEL_5:
    v10 = LastError <= 0;
    goto LABEL_6;
  }
  Luid[1].HighPart = a3 != 0 ? 2 : 0;
  v12 = AdjustTokenPrivileges(hObject, 0, (PTOKEN_PRIVILEGES)Luid, 0x10u, &PreviousState, &ReturnLength);
  LastError = GetLastError();
  v6 = LastError;
  if ( !v12 )
    goto LABEL_5;
  v10 = LastError <= 0;
  if ( !LastError )
  {
    if ( PreviousState.Privileges[0].Attributes != Luid[1].HighPart )
      *a4 = 1;
    goto LABEL_12;
  }
LABEL_6:
  if ( !v10 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( (v6 & 0x80000000) != 0 )
    goto LABEL_9;
LABEL_12:
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  return v6;
}

```

## disassembly

```asm
0x180014200  push    rbp
0x180014202  push    rbx
0x180014203  push    rsi
0x180014204  push    rdi
0x180014205  mov     rbp, rsp
0x180014208  sub     rsp, 78h
0x18001420c  mov     rax, cs:__security_cookie
0x180014213  xor     rax, rsp
0x180014216  mov     [rbp+var_18], rax
0x18001421a  mov     [rbp+hObject], 0
0x180014222  xorps   xmm0, xmm0
0x180014225  mov     [rbp+var_48], 0
0x18001422c  xorps   xmm1, xmm1
0x18001422f  mov     rsi, r9
0x180014232  mov     edi, r8d
0x180014235  movups  xmmword ptr [rbp+Luid.LowPart], xmm0
0x180014239  movups  xmmword ptr [rbp+var_28.PrivilegeCount], xmm1
0x18001423d  test    r9, r9
0x180014240  jnz     short loc_180014249
0x180014242  mov     edi, 80070057h
0x180014247  jmp     short loc_180014290
0x180014249  lea     rcx, [rbp+hObject]
0x18001424d  mov     dword ptr [r9], 0
0x180014254  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180014259  mov     rbx, rax
0x18001425c  call    cs:__imp_GetCurrentProcess
0x180014262  mov     r8, rbx; TokenHandle
0x180014265  mov     edx, 28h ; '('; DesiredAccess
0x18001426a  mov     rcx, rax; ProcessHandle
0x18001426d  call    cs:__imp_OpenProcessToken
0x180014273  test    eax, eax
0x180014275  jnz     short loc_1800142EC
0x180014277  call    cs:__imp_GetLastError
0x18001427d  mov     edi, eax
0x18001427f  test    eax, eax
0x180014281  jle     short loc_18001428C
0x180014283  movzx   edi, ax
0x180014286  or      edi, 80070000h
0x18001428c  test    edi, edi
0x18001428e  jns     short loc_1800142C1
0x180014290  mov     rcx, cs:WPP_GLOBAL_Control
0x180014297  lea     rax, WPP_GLOBAL_Control
0x18001429e  cmp     rcx, rax
0x1800142a1  jz      short loc_1800142C1
0x1800142a3  test    byte ptr [rcx+1Ch], 1
0x1800142a7  jz      short loc_1800142C1
0x1800142a9  mov     rcx, [rcx+10h]
0x1800142ad  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x1800142b4  mov     edx, 7Bh ; '{'
0x1800142b9  mov     r9d, edi
0x1800142bc  call    WPP_SF_d
0x1800142c1  mov     rcx, [rbp+hObject]; hObject
0x1800142c5  lea     rdx, [rcx+1]
0x1800142c9  cmp     rdx, 1
0x1800142cd  jbe     short loc_1800142D5
0x1800142cf  call    cs:__imp_CloseHandle
0x1800142d5  mov     eax, edi
0x1800142d7  mov     rcx, [rbp+var_18]
0x1800142db  xor     rcx, rsp; StackCookie
0x1800142de  call    __security_check_cookie
0x1800142e3  add     rsp, 78h
0x1800142e7  pop     rdi
0x1800142e8  pop     rsi
0x1800142e9  pop     rbx
0x1800142ea  pop     rbp
0x1800142eb  retn
0x1800142ec  lea     r8, [rbp+Luid.HighPart]; lpLuid
0x1800142f0  mov     [rbp+Luid.LowPart], 1
0x1800142f7  lea     rdx, Name; "SeSecurityPrivilege"
0x1800142fe  xor     ecx, ecx; lpSystemName
0x180014300  call    cs:__imp_LookupPrivilegeValueW
0x180014306  test    eax, eax
0x180014308  jz      loc_180014277
0x18001430e  mov     rcx, [rbp+hObject]; TokenHandle
0x180014312  lea     r8, [rbp+Luid]; NewState
0x180014316  neg     edi
0x180014318  mov     r9d, 10h; BufferLength
0x18001431e  sbb     eax, eax
0x180014320  xor     edx, edx; DisableAllPrivileges
0x180014322  and     eax, 2
0x180014325  mov     [rbp+Luid.HighPart+8], eax
0x180014328  lea     rax, [rbp+var_48]
0x18001432c  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x180014331  lea     rax, [rbp+var_28]
0x180014335  mov     [rsp+78h+PreviousState], rax; PreviousState
0x18001433a  call    cs:__imp_AdjustTokenPrivileges
0x180014340  mov     ebx, eax
0x180014342  call    cs:__imp_GetLastError
0x180014348  mov     edi, eax
0x18001434a  test    ebx, ebx
0x18001434c  jz      loc_18001427F
0x180014352  test    eax, eax
0x180014354  jnz     loc_180014281
0x18001435a  mov     eax, [rbp+Luid.HighPart+8]
0x18001435d  cmp     [rbp+var_28.Privileges.Attributes], eax
0x180014360  jz      loc_1800142C1
0x180014366  mov     dword ptr [rsi], 1
0x18001436c  jmp     loc_1800142C1
```
