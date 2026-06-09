# UserTokenUtility::GetProcessToken(void *,int,tlx::unique_any<tlx::file_handle_traits> *)

- ea: `0x1800300c0`
- end: `0x1800304a5`
- name: `?GetProcessToken@UserTokenUtility@@SAJPEAXHPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z`
- size: `997`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002060c`
- `0x180022108`
- `0x180027460`

## callees

- `0x1800029d0`
- `0x180006a80`
- `0x180007cf8`
- `0x180011ef8`
- `0x1800300c0`
- `0x180030bc0`
- `0x180034258`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800302ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800302ea`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003014e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800302fb`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003014e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800302fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030158`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030294`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030305`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003038b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030158`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030294`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030305`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003038b`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x180030381`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x180030381`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030134`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030267`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800303f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030451`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030465`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030479`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030134`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030267`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800303f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030451`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030465`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030479`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18003028a`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18003028a`

## string_xrefs

- `0x180030281`: `SeTcbPrivilege`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UserTokenUtility::GetProcessToken(HANDLE ProcessHandle, int a2, void **a3)
{
  void *v6; // rcx
  void **v7; // rax
  signed int LastError; // eax
  int v9; // ebx
  void **v10; // rax
  int v11; // eax
  const wchar_t *v12; // rdx
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  HANDLE v15; // rcx
  signed int v16; // eax
  void **v17; // rbx
  HANDLE CurrentProcess; // rax
  signed int v19; // eax
  void **NewTokenHandle; // rax
  signed int v21; // eax
  void *v22; // rdx
  unsigned __int64 v23; // r8
  HANDLE v24; // rcx
  HANDLE v25; // rax
  HANDLE hObject; // [rsp+50h] [rbp-30h] BYREF
  HANDLE TokenHandle; // [rsp+58h] [rbp-28h] BYREF
  HANDLE ExistingTokenHandle; // [rsp+60h] [rbp-20h] BYREF
  struct _LUID_AND_ATTRIBUTES Luid; // [rsp+68h] [rbp-18h] BYREF

  TokenHandle = 0;
  hObject = 0;
  ExistingTokenHandle = 0;
  Luid.Luid = 0;
  Luid.Attributes = 0;
  if ( !ProcessHandle || !a3 )
  {
    v9 = -2147024809;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_a23aa53e43603591c4e5d6b4fc0b4a04_Traceguids);
    goto LABEL_58;
  }
  v6 = *a3;
  *a3 = 0;
  if ( (unsigned __int64)v6 + 1 > 1 )
    CloseHandle(v6);
  v7 = (void **)tlx::replace<tlx::file_handle_traits>(&TokenHandle);
  if ( !OpenProcessToken(ProcessHandle, 0x4Fu, v7) )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        &WPP_a23aa53e43603591c4e5d6b4fc0b4a04_Traceguids,
        (unsigned int)v9);
    goto LABEL_58;
  }
  if ( !a2 )
    goto LABEL_49;
  v10 = (void **)tlx::replace<tlx::file_handle_traits>(&hObject);
  v11 = LUAGetElevatedToken(TokenHandle, v10);
  v9 = v11 | 0x10000000;
  if ( v11 < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_58;
    v14 = 18;
LABEL_16:
    WPP_SF_d(v13[2], v14, &WPP_a23aa53e43603591c4e5d6b4fc0b4a04_Traceguids, (unsigned int)v9);
    goto LABEL_58;
  }
  if ( (unsigned __int64)hObject + 1 > 1 && !(unsigned int)UtilTokenHasPrivilege(hObject, v12) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_a23aa53e43603591c4e5d6b4fc0b4a04_Traceguids);
    v15 = hObject;
    hObject = 0;
    if ( (unsigned __int64)v15 + 1 > 1 )
      CloseHandle(v15);
  }
  if ( (unsigned __int64)hObject + 1 > 1 )
    goto LABEL_49;
  if ( LookupPrivilegeValueW(0, L"SeTcbPrivilege", &Luid.Luid) )
  {
    Luid.Attributes = 0;
    v17 = (void **)tlx::replace<tlx::file_handle_traits>(&ExistingTokenHandle);
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0xF01FFu, v17) )
    {
      v19 = GetLastError();
      v9 = v19;
      if ( v19 > 0 )
        v9 = (unsigned __int16)v19 | 0x80070000;
      if ( v9 >= 0 )
        v9 = -2147467259;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v14 = 21;
        goto LABEL_16;
      }
      goto LABEL_58;
    }
    NewTokenHandle = (void **)tlx::replace<tlx::file_handle_traits>(&hObject);
    if ( !CreateRestrictedToken(ExistingTokenHandle, 0, 0, 0, 1u, &Luid, 0, 0, NewTokenHandle) )
    {
      v21 = GetLastError();
      v9 = v21;
      if ( v21 > 0 )
        v9 = (unsigned __int16)v21 | 0x80070000;
      if ( v9 >= 0 )
        v9 = -2147467259;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v14 = 22;
        goto LABEL_16;
      }
      goto LABEL_58;
    }
LABEL_49:
    v22 = *a3;
    v23 = (unsigned __int64)*a3 + 1;
    v24 = hObject;
    if ( (unsigned __int64)hObject + 1 <= 1 )
    {
      v25 = TokenHandle;
      TokenHandle = 0;
      *a3 = v25;
    }
    else
    {
      hObject = 0;
      *a3 = v24;
    }
    if ( v23 > 1 )
      CloseHandle(v22);
    v9 = 0;
    goto LABEL_58;
  }
  v16 = GetLastError();
  v9 = v16;
  if ( v16 > 0 )
    v9 = (unsigned __int16)v16 | 0x80070000;
  if ( v9 >= 0 )
    v9 = -2147467259;
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v14 = 20;
    goto LABEL_16;
  }
LABEL_58:
  if ( (unsigned __int64)ExistingTokenHandle + 1 > 1 )
    CloseHandle(ExistingTokenHandle);
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  if ( (unsigned __int64)TokenHandle + 1 > 1 )
    CloseHandle(TokenHandle);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800300c0  mov     [rsp-18h+arg_8], rbx
0x1800300c5  mov     [rsp-18h+arg_18], rsi
0x1800300ca  push    rbp
0x1800300cb  push    rdi
0x1800300cc  push    r15
0x1800300ce  mov     rbp, rsp
0x1800300d1  sub     rsp, 80h
0x1800300d8  mov     rax, cs:__security_cookie
0x1800300df  xor     rax, rsp
0x1800300e2  mov     [rbp+var_8], rax
0x1800300e6  mov     rsi, r8
0x1800300e9  mov     edi, edx
0x1800300eb  mov     rbx, rcx
0x1800300ee  mov     [rbp+TokenHandle], 0
0x1800300f6  mov     [rbp+hObject], 0
0x1800300fe  mov     [rbp+ExistingTokenHandle], 0
0x180030106  xor     eax, eax
0x180030108  mov     qword ptr [rbp+Luid.LowPart], rax
0x18003010c  mov     [rbp+var_10], eax
0x18003010f  lea     r15d, [rax+1]
0x180030113  test    rcx, rcx
0x180030116  jz      loc_180030410
0x18003011c  test    r8, r8
0x18003011f  jz      loc_180030410
0x180030125  mov     rcx, [r8]; hObject
0x180030128  mov     [r8], rax
0x18003012b  lea     rax, [rcx+1]
0x18003012f  cmp     rax, r15
0x180030132  jbe     short loc_18003013A
0x180030134  call    cs:__imp_CloseHandle
0x18003013a  lea     rcx, [rbp+TokenHandle]
0x18003013e  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180030143  mov     r8, rax; TokenHandle
0x180030146  mov     edx, 4Fh ; 'O'; DesiredAccess
0x18003014b  mov     rcx, rbx; ProcessHandle
0x18003014e  call    cs:__imp_OpenProcessToken
0x180030154  test    eax, eax
0x180030156  jnz     short loc_1800301AB
0x180030158  call    cs:__imp_GetLastError
0x18003015e  mov     ebx, eax
0x180030160  test    eax, eax
0x180030162  jle     short loc_18003016D
0x180030164  movzx   ebx, ax
0x180030167  or      ebx, 80070000h
0x18003016d  lea     rdi, WPP_GLOBAL_Control
0x180030174  mov     rcx, cs:WPP_GLOBAL_Control
0x18003017b  cmp     rcx, rdi
0x18003017e  jz      loc_180030444
0x180030184  test    [rcx+1Ch], r15b
0x180030188  jz      loc_180030444
0x18003018e  mov     edx, 11h
0x180030193  mov     r9d, ebx
0x180030196  lea     r8, WPP_a23aa53e43603591c4e5d6b4fc0b4a04_Traceguids
0x18003019d  mov     rcx, [rcx+10h]
0x1800301a1  call    WPP_SF_d
0x1800301a6  jmp     loc_180030444
0x1800301ab  test    edi, edi
0x1800301ad  jz      loc_1800303CE
0x1800301b3  lea     rcx, [rbp+hObject]
0x1800301b7  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x1800301bc  mov     rdx, rax; NewTokenHandle
0x1800301bf  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800301c3  call    LUAGetElevatedToken
0x1800301c8  mov     ebx, eax
0x1800301ca  or      ebx, 10000000h
0x1800301d0  jge     short loc_180030210
0x1800301d2  lea     rdi, WPP_GLOBAL_Control
0x1800301d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800301e0  cmp     rcx, rdi
0x1800301e3  jz      loc_180030444
0x1800301e9  test    [rcx+1Ch], r15b
0x1800301ed  jz      loc_180030444
0x1800301f3  mov     edx, 12h
0x1800301f8  mov     r9d, ebx
0x1800301fb  lea     r8, WPP_a23aa53e43603591c4e5d6b4fc0b4a04_Traceguids
0x180030202  mov     rcx, [rcx+10h]
0x180030206  call    WPP_SF_d
0x18003020b  jmp     loc_180030444
0x180030210  mov     rcx, [rbp+hObject]; TokenHandle
0x180030214  lea     rax, [rcx+1]
0x180030218  lea     rdi, WPP_GLOBAL_Control
0x18003021f  cmp     rax, r15
0x180030222  jbe     short loc_18003026D
0x180030224  call    ?UtilTokenHasPrivilege@@YAHPEAXPEB_W@Z; UtilTokenHasPrivilege(void *,wchar_t const *)
0x180030229  test    eax, eax
0x18003022b  jnz     short loc_18003026D
0x18003022d  mov     rcx, cs:WPP_GLOBAL_Control
0x180030234  cmp     rcx, rdi
0x180030237  jz      short loc_180030252
0x180030239  test    byte ptr [rcx+1Ch], 4
0x18003023d  jz      short loc_180030252
0x18003023f  lea     edx, [rax+13h]
0x180030242  lea     r8, WPP_a23aa53e43603591c4e5d6b4fc0b4a04_Traceguids
0x180030249  mov     rcx, [rcx+10h]
0x18003024d  call    WPP_SF_
0x180030252  mov     rcx, [rbp+hObject]; hObject
0x180030256  mov     [rbp+hObject], 0
0x18003025e  lea     rax, [rcx+1]
0x180030262  cmp     rax, r15
0x180030265  jbe     short loc_18003026D
0x180030267  call    cs:__imp_CloseHandle
0x18003026d  mov     rax, [rbp+hObject]
0x180030271  inc     rax
0x180030274  cmp     rax, r15
0x180030277  ja      loc_1800303CE
0x18003027d  lea     r8, [rbp+Luid]; lpLuid
0x180030281  lea     rdx, aSetcbprivilege; "SeTcbPrivilege"
0x180030288  xor     ecx, ecx; lpSystemName
0x18003028a  call    cs:__imp_LookupPrivilegeValueW
0x180030290  test    eax, eax
0x180030292  jnz     short loc_1800302D7
0x180030294  call    cs:__imp_GetLastError
0x18003029a  mov     ebx, eax
0x18003029c  test    eax, eax
0x18003029e  jle     short loc_1800302A9
0x1800302a0  movzx   ebx, ax
0x1800302a3  or      ebx, 80070000h
0x1800302a9  mov     eax, 80004005h
0x1800302ae  test    ebx, ebx
0x1800302b0  cmovns  ebx, eax
0x1800302b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800302ba  cmp     rcx, rdi
0x1800302bd  jz      loc_180030444
0x1800302c3  test    [rcx+1Ch], r15b
0x1800302c7  jz      loc_180030444
0x1800302cd  mov     edx, 14h
0x1800302d2  jmp     loc_1800301F8
0x1800302d7  mov     [rbp+var_10], 0
0x1800302de  lea     rcx, [rbp+ExistingTokenHandle]
0x1800302e2  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x1800302e7  mov     rbx, rax
0x1800302ea  call    cs:__imp_GetCurrentProcess
0x1800302f0  mov     r8, rbx; TokenHandle
0x1800302f3  mov     edx, 0F01FFh; DesiredAccess
0x1800302f8  mov     rcx, rax; ProcessHandle
0x1800302fb  call    cs:__imp_OpenProcessToken
0x180030301  test    eax, eax
0x180030303  jnz     short loc_180030348
0x180030305  call    cs:__imp_GetLastError
0x18003030b  mov     ebx, eax
0x18003030d  test    eax, eax
0x18003030f  jle     short loc_18003031A
0x180030311  movzx   ebx, ax
0x180030314  or      ebx, 80070000h
0x18003031a  mov     eax, 80004005h
0x18003031f  test    ebx, ebx
0x180030321  cmovns  ebx, eax
0x180030324  mov     rcx, cs:WPP_GLOBAL_Control
0x18003032b  cmp     rcx, rdi
0x18003032e  jz      loc_180030444
0x180030334  test    [rcx+1Ch], r15b
0x180030338  jz      loc_180030444
0x18003033e  mov     edx, 15h
0x180030343  jmp     loc_1800301F8
0x180030348  lea     rcx, [rbp+hObject]
0x18003034c  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180030351  mov     [rsp+80h+NewTokenHandle], rax; NewTokenHandle
0x180030356  mov     [rsp+80h+SidsToRestrict], 0; SidsToRestrict
0x18003035f  mov     [rsp+80h+RestrictedSidCount], 0; RestrictedSidCount
0x180030367  lea     rax, [rbp+Luid]
0x18003036b  mov     [rsp+80h+PrivilegesToDelete], rax; PrivilegesToDelete
0x180030370  mov     [rsp+80h+DeletePrivilegeCount], r15d; DeletePrivilegeCount
0x180030375  xor     r9d, r9d; SidsToDisable
0x180030378  xor     r8d, r8d; DisableSidCount
0x18003037b  xor     edx, edx; Flags
0x18003037d  mov     rcx, [rbp+ExistingTokenHandle]; ExistingTokenHandle
0x180030381  call    cs:__imp_CreateRestrictedToken
0x180030387  test    eax, eax
0x180030389  jnz     short loc_1800303CE
0x18003038b  call    cs:__imp_GetLastError
0x180030391  mov     ebx, eax
0x180030393  test    eax, eax
0x180030395  jle     short loc_1800303A0
0x180030397  movzx   ebx, ax
0x18003039a  or      ebx, 80070000h
0x1800303a0  mov     eax, 80004005h
0x1800303a5  test    ebx, ebx
0x1800303a7  cmovns  ebx, eax
0x1800303aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800303b1  cmp     rcx, rdi
0x1800303b4  jz      loc_180030444
0x1800303ba  test    [rcx+1Ch], r15b
0x1800303be  jz      loc_180030444
0x1800303c4  mov     edx, 16h
0x1800303c9  jmp     loc_1800301F8
0x1800303ce  mov     rdx, [rsi]
0x1800303d1  lea     r8, [rdx+1]
0x1800303d5  mov     rcx, [rbp+hObject]
0x1800303d9  lea     rax, [rcx+1]
0x1800303dd  cmp     rax, r15
0x1800303e0  jbe     short loc_1800303FF
0x1800303e2  mov     [rbp+hObject], 0
0x1800303ea  mov     [rsi], rcx
0x1800303ed  cmp     r8, r15
0x1800303f0  jbe     short loc_1800303FB
0x1800303f2  mov     rcx, rdx; hObject
0x1800303f5  call    cs:__imp_CloseHandle
0x1800303fb  xor     ebx, ebx
0x1800303fd  jmp     short loc_180030444
0x1800303ff  mov     rax, [rbp+TokenHandle]
0x180030403  mov     [rbp+TokenHandle], 0
0x18003040b  mov     [rsi], rax
0x18003040e  jmp     short loc_1800303ED
0x180030410  mov     ebx, 80070057h
0x180030415  lea     rdi, WPP_GLOBAL_Control
0x18003041c  mov     rcx, cs:WPP_GLOBAL_Control
0x180030423  cmp     rcx, rdi
0x180030426  jz      short loc_180030444
0x180030428  test    [rcx+1Ch], r15b
0x18003042c  jz      short loc_180030444
0x18003042e  mov     edx, 10h
0x180030433  lea     r8, WPP_a23aa53e43603591c4e5d6b4fc0b4a04_Traceguids
0x18003043a  mov     rcx, [rcx+10h]
0x18003043e  call    WPP_SF_
0x180030443  nop
0x180030444  mov     rcx, [rbp+ExistingTokenHandle]; hObject
0x180030448  lea     rax, [rcx+1]
0x18003044c  cmp     rax, r15
0x18003044f  jbe     short loc_180030458
0x180030451  call    cs:__imp_CloseHandle
0x180030457  nop
0x180030458  mov     rcx, [rbp+hObject]; hObject
0x18003045c  lea     rax, [rcx+1]
0x180030460  cmp     rax, r15
0x180030463  jbe     short loc_18003046C
0x180030465  call    cs:__imp_CloseHandle
0x18003046b  nop
0x18003046c  mov     rcx, [rbp+TokenHandle]; hObject
0x180030470  lea     rdx, [rcx+1]
0x180030474  cmp     rdx, r15
0x180030477  jbe     short loc_18003047F
0x180030479  call    cs:__imp_CloseHandle
0x18003047f  mov     eax, ebx
0x180030481  mov     rcx, [rbp+var_8]
0x180030485  xor     rcx, rsp; StackCookie
0x180030488  call    __security_check_cookie
0x18003048d  lea     r11, [rsp+80h+var_s0]
0x180030495  mov     rbx, [r11+28h]
0x180030499  mov     rsi, [r11+38h]
0x18003049d  mov     rsp, r11
0x1800304a0  pop     r15
0x1800304a2  pop     rdi
0x1800304a3  pop     rbp
0x1800304a4  retn
```
