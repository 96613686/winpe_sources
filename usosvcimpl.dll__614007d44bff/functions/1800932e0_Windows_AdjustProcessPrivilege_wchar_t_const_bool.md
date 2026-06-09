# Windows::AdjustProcessPrivilege(wchar_t const *,bool)

- ea: `0x1800932e0`
- end: `0x180093403`
- name: `?AdjustProcessPrivilege@Windows@@YAXPEB_W_N@Z`
- size: `291`
- prototype: `void __fastcall(LPCWSTR lpName, bool)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180093410`
- `0x18009383c`

## callees

- `0x180010f24`
- `0x1800932e0`
- `0x1800dd930`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18009330d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18009330d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180093320`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180093320`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800933a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800933a7`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180093389`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180093389`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180093352`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180093352`

## string_xrefs

- `0x1800933ca`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Reboot.cpp`
- `0x1800933dc`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Reboot.cpp`
- `0x1800933ee`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Reboot.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::AdjustProcessPrivilege(LPCWSTR lpName, unsigned __int8 a2)
{
  int v2; // esi
  HANDLE CurrentProcess; // rax
  const char *v5; // r9
  const char *v6; // r9
  const char *v7; // r9
  void *TokenHandle; // [rsp+30h] [rbp-28h] BYREF
  _LUID Luid[2]; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v2 = a2;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x61,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Reboot.cpp",
      v5);
  *(_OWORD *)&Luid[0].LowPart = 0;
  Luid[0].LowPart = 1;
  if ( !LookupPrivilegeValueW(0, lpName, (PLUID)&Luid[0].HighPart) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x65,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Reboot.cpp",
      v6);
  Luid[1].HighPart = 2 * v2;
  if ( !AdjustTokenPrivileges(TokenHandle, 0, (PTOKEN_PRIVILEGES)Luid, 0, 0, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x6E,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Reboot.cpp",
      v7);
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
}

```

## disassembly

```asm
0x1800932e0  mov     [rsp+arg_8], rbx
0x1800932e5  mov     [rsp+arg_10], rsi
0x1800932ea  push    rdi
0x1800932eb  sub     rsp, 50h
0x1800932ef  mov     rax, cs:__security_cookie
0x1800932f6  xor     rax, rsp
0x1800932f9  mov     [rsp+58h+var_10], rax
0x1800932fe  movzx   esi, dl
0x180093301  mov     rdi, rcx
0x180093304  mov     [rsp+58h+TokenHandle], 0
0x18009330d  call    cs:__imp_GetCurrentProcess
0x180093313  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x180093318  mov     edx, 28h ; '('; DesiredAccess
0x18009331d  mov     rcx, rax; ProcessHandle
0x180093320  call    cs:__imp_OpenProcessToken
0x180093326  mov     rcx, [rsp+58h]; this
0x18009332b  test    eax, eax
0x18009332d  jz      loc_1800933DC
0x180093333  xorps   xmm0, xmm0
0x180093336  movups  xmmword ptr [rsp+58h+Luid.LowPart], xmm0
0x18009333b  mov     [rsp+58h+Luid.LowPart], 1
0x180093343  mov     rbx, [rsp+58h]
0x180093348  lea     r8, [rsp+58h+Luid.HighPart]; lpLuid
0x18009334d  mov     rdx, rdi; lpName
0x180093350  xor     ecx, ecx; lpSystemName
0x180093352  call    cs:__imp_LookupPrivilegeValueW
0x180093358  test    eax, eax
0x18009335a  jz      loc_1800933EE
0x180093360  mov     eax, esi
0x180093362  add     eax, eax
0x180093364  mov     [rsp+58h+Luid.HighPart+8], eax
0x180093368  mov     [rsp+58h+ReturnLength], 0; ReturnLength
0x180093371  mov     [rsp+58h+PreviousState], 0; PreviousState
0x18009337a  xor     r9d, r9d; BufferLength
0x18009337d  lea     r8, [rsp+58h+Luid]; NewState
0x180093382  xor     edx, edx; DisableAllPrivileges
0x180093384  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x180093389  call    cs:__imp_AdjustTokenPrivileges
0x18009338f  mov     rcx, [rsp+58h]; this
0x180093394  test    eax, eax
0x180093396  jz      short loc_1800933CA
0x180093398  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x18009339d  lea     rax, [rcx-1]
0x1800933a1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800933a5  ja      short loc_1800933AD
0x1800933a7  call    cs:__imp_CloseHandle
0x1800933ad  mov     rcx, [rsp+58h+var_10]
0x1800933b2  xor     rcx, rsp; StackCookie
0x1800933b5  call    __security_check_cookie
0x1800933ba  mov     rbx, [rsp+58h+arg_8]
0x1800933bf  mov     rsi, [rsp+58h+arg_10]
0x1800933c4  add     rsp, 50h
0x1800933c8  pop     rdi
0x1800933c9  retn
0x1800933ca  lea     r8, aCW1SSrcOrchest_27; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800933d1  mov     edx, 6Eh ; 'n'; void *
0x1800933d6  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800933dc  lea     r8, aCW1SSrcOrchest_27; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800933e3  mov     edx, 61h ; 'a'; void *
0x1800933e8  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800933ee  lea     r8, aCW1SSrcOrchest_27; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800933f5  mov     edx, 65h ; 'e'; void *
0x1800933fa  mov     rcx, rbx; this
0x1800933fd  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
