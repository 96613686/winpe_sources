# CReport::SetDeleteFilesToken(void *)

- ea: `0x1800762c4`
- end: `0x180076454`
- name: `?SetDeleteFilesToken@CReport@@IEAAJPEAX@Z`
- size: `400`
- prototype: `int(CReport *__hidden this, void *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180028974`
- `0x180075690`

## callees

- `0x180008004`
- `0x18001c368`
- `0x180020680`
- `0x18002d930`
- `0x1800762c4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800763dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800763dc`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800763fe`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800763fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007641c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007641c`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x180076380`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x180076380`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800762ff`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800762ff`

## pseudocode

```c
__int64 __fastcall CReport::SetDeleteFilesToken(CReport *this, void *a2)
{
  char *v2; // rdi
  void **v4; // rax
  HANDLE CurrentProcess; // rbx
  __int64 v7; // rcx
  int v8; // eax
  unsigned int v9; // ebx
  wchar_t *v10; // rcx
  __int64 v11; // rdx
  void **v12; // rax
  DWORD LastError; // eax
  void *v14; // [rsp+30h] [rbp+8h] BYREF

  v2 = (char *)this + 46616;
  v14 = 0;
  if ( *((_QWORD *)this + 5827) )
    return 0;
  if ( a2 )
  {
    v4 = (void **)tlx::replace<tlx::file_handle_traits>((char *)this + 46616);
    if ( !DuplicateToken(a2, SecurityImpersonation, v4) )
    {
      tlx::unique_any<tlx::file_handle_traits>::reset(v2, 0);
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 304, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids, 0);
    }
    return 0;
  }
  CurrentProcess = (HANDLE)*((_QWORD *)this + 830);
  if ( !CurrentProcess )
  {
    v7 = *((_QWORD *)this + 1139);
    if ( v7 )
    {
      v8 = PssQuerySnapshot(v7, 1, &v14);
      v9 = v8;
      if ( v8 )
      {
        if ( v8 > 0 )
          v9 = (unsigned __int16)v8 | 0x80070000;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          return v9;
        v11 = 305;
        goto LABEL_16;
      }
      CurrentProcess = v14;
    }
    else
    {
      CurrentProcess = GetCurrentProcess();
    }
  }
  v12 = (void **)tlx::replace<tlx::file_handle_traits>(v2);
  if ( OpenProcessToken(CurrentProcess, 0xAu, v12) )
    return 0;
  tlx::unique_any<tlx::file_handle_traits>::reset(v2, 0);
  LastError = GetLastError();
  v9 = ERROR_HR_FROM_WIN32(LastError);
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
    return v9;
  v11 = 306;
LABEL_16:
  WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x1800762c4  mov     [rsp+arg_8], rbx
0x1800762c9  push    rdi
0x1800762ca  sub     rsp, 20h
0x1800762ce  lea     rdi, [rcx+0B618h]
0x1800762d5  mov     [rsp+28h+arg_0], 0
0x1800762de  cmp     qword ptr [rdi], 0
0x1800762e2  mov     rbx, rdx
0x1800762e5  jnz     short loc_18007634A
0x1800762e7  test    rdx, rdx
0x1800762ea  jz      short loc_180076358
0x1800762ec  mov     rcx, rdi
0x1800762ef  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x1800762f4  mov     r8, rax; DuplicateTokenHandle
0x1800762f7  mov     edx, 2; ImpersonationLevel
0x1800762fc  mov     rcx, rbx; ExistingTokenHandle
0x1800762ff  call    cs:__imp_DuplicateToken
0x180076306  nop     dword ptr [rax+rax+00h]
0x18007630b  test    eax, eax
0x18007630d  jnz     short loc_18007634A
0x18007630f  xor     edx, edx
0x180076311  mov     rcx, rdi
0x180076314  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180076319  mov     rcx, cs:WPP_GLOBAL_Control
0x180076320  lea     rax, WPP_GLOBAL_Control
0x180076327  cmp     rcx, rax
0x18007632a  jz      short loc_18007634A
0x18007632c  test    byte ptr [rcx+1Ch], 1
0x180076330  jz      short loc_18007634A
0x180076332  mov     rcx, [rcx+10h]
0x180076336  lea     r8, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids
0x18007633d  mov     edx, 130h
0x180076342  xor     r9d, r9d
0x180076345  call    WPP_SF_d
0x18007634a  xor     eax, eax
0x18007634c  mov     rbx, [rsp+28h+arg_8]
0x180076351  add     rsp, 20h
0x180076355  pop     rdi
0x180076356  retn
0x180076358  mov     rbx, [rcx+19F0h]
0x18007635f  test    rbx, rbx
0x180076362  jnz     loc_1800763EB
0x180076368  mov     rcx, [rcx+2398h]
0x18007636f  test    rcx, rcx
0x180076372  jz      short loc_1800763DC
0x180076374  lea     r9d, [rbx+8]
0x180076378  lea     r8, [rsp+28h+arg_0]
0x18007637d  lea     edx, [rbx+1]
0x180076380  call    cs:__imp_PssQuerySnapshot
0x180076387  nop     dword ptr [rax+rax+00h]
0x18007638c  mov     ebx, eax
0x18007638e  test    eax, eax
0x180076390  jz      short loc_1800763D5
0x180076392  jle     short loc_18007639D
0x180076394  movzx   ebx, ax
0x180076397  or      ebx, 80070000h
0x18007639d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800763a4  lea     rax, WPP_GLOBAL_Control
0x1800763ab  cmp     rcx, rax
0x1800763ae  jz      short loc_1800763CE
0x1800763b0  test    byte ptr [rcx+1Ch], 1
0x1800763b4  jz      short loc_1800763CE
0x1800763b6  mov     edx, 131h
0x1800763bb  mov     rcx, [rcx+10h]
0x1800763bf  lea     r8, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids
0x1800763c6  mov     r9d, ebx
0x1800763c9  call    WPP_SF_d
0x1800763ce  mov     eax, ebx
0x1800763d0  jmp     loc_18007634C
0x1800763d5  mov     rbx, [rsp+28h+arg_0]
0x1800763da  jmp     short loc_1800763EB
0x1800763dc  call    cs:__imp_GetCurrentProcess
0x1800763e3  nop     dword ptr [rax+rax+00h]
0x1800763e8  mov     rbx, rax
0x1800763eb  mov     rcx, rdi
0x1800763ee  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x1800763f3  mov     r8, rax; TokenHandle
0x1800763f6  mov     edx, 0Ah; DesiredAccess
0x1800763fb  mov     rcx, rbx; ProcessHandle
0x1800763fe  call    cs:__imp_OpenProcessToken
0x180076405  nop     dword ptr [rax+rax+00h]
0x18007640a  test    eax, eax
0x18007640c  jnz     loc_18007634A
0x180076412  xor     edx, edx
0x180076414  mov     rcx, rdi
0x180076417  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18007641c  call    cs:__imp_GetLastError
0x180076423  nop     dword ptr [rax+rax+00h]
0x180076428  mov     ecx, eax; unsigned int
0x18007642a  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18007642f  mov     ebx, eax
0x180076431  mov     rcx, cs:WPP_GLOBAL_Control
0x180076438  lea     rax, WPP_GLOBAL_Control
0x18007643f  cmp     rcx, rax
0x180076442  jz      short loc_1800763CE
0x180076444  test    byte ptr [rcx+1Ch], 1
0x180076448  jz      short loc_1800763CE
0x18007644a  mov     edx, 132h
0x18007644f  jmp     loc_1800763BB
```
