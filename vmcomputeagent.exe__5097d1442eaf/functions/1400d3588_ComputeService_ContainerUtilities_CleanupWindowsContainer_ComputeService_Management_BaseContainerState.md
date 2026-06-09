# ComputeService::ContainerUtilities::CleanupWindowsContainer(ComputeService::Management::BaseContainerState *)

- ea: `0x1400d3588`
- end: `0x1400d3695`
- name: `?CleanupWindowsContainer@ContainerUtilities@ComputeService@@YAXPEAUBaseContainerState@Management@2@@Z`
- size: `269`
- prototype: `void __fastcall(ComputeService::ContainerUtilities *__hidden this, struct ComputeService::Management::BaseContainerState *)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x140088e10`
- `0x14008c5c0`
- `0x14009b370`

## callees

- `0x140005360`
- `0x140041b14`
- `0x140041d9c`
- `0x1400d3588`
- `0x1400d68d0`
- `0x1400d6908`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d3632`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d3660`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d3632`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d3660`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d361f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d364d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d361f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d364d`
- `ntdll!NtMakeTemporaryObject` at `0x1400d35fa`
- `ntdll!NtMakeTemporaryObject` at `0x1400d35fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400d3658`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400d3658`
- `container!WcCleanupContainer` at `0x1400d35db`
- `container!WcCleanupContainer` at `0x1400d35db`
- `container!WcReleaseContainerTerminationNotification` at `0x1400d362a`
- `container!WcReleaseContainerTerminationNotification` at `0x1400d362a`

## pseudocode

```c
void __fastcall ComputeService::ContainerUtilities::CleanupWindowsContainer(
        HANDLE *this,
        struct ComputeService::Management::BaseContainerState *a2)
{
  int v3; // eax
  unsigned int v4; // r8d
  NTSTATUS TemporaryObject; // eax
  unsigned int v6; // r8d
  HANDLE v7; // rsi
  DWORD LastError; // ebx
  HANDLE v9; // rsi
  DWORD v10; // ebx
  const char *v11; // r9
  int v12[4]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v13; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( (((unsigned __int64)*this + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    *(_OWORD *)v12 = 0;
    v13 = 0;
    try
    {
      Vml::TemporaryPrivilege::TemporaryPrivilege((Vml::TemporaryPrivilege *)v12, 18);
      v3 = WcCleanupContainer(*this, 0);
      if ( v3 < 0 )
        wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x2CE, v4, (const char *)(unsigned int)v3, v12[0]);
      TemporaryObject = NtMakeTemporaryObject(*this);
      if ( TemporaryObject < 0 )
        wil::details::in1diag3::_Log_NtStatus(
          retaddr,
          (void *)0x2D2,
          v6,
          (const char *)(unsigned int)TemporaryObject,
          v12[0]);
      v7 = this[1];
      if ( v7 )
      {
        LastError = GetLastError();
        WcReleaseContainerTerminationNotification(v7);
        SetLastError(LastError);
      }
      this[1] = 0;
      v9 = *this;
      if ( (char *)*this - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        v10 = GetLastError();
        CloseHandle(v9);
        SetLastError(v10);
      }
      *this = 0;
      Vml::TemporaryPrivilege::~TemporaryPrivilege((Vml::TemporaryPrivilege *)v12);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x2D8,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerutilities.cpp",
        v11);
    }
  }
}

```

## disassembly

```asm
0x1400d3588  mov     r11, rsp
0x1400d358b  mov     [r11+10h], rbx
0x1400d358f  mov     [r11+18h], rsi
0x1400d3593  push    rdi
0x1400d3594  sub     rsp, 40h
0x1400d3598  mov     rax, cs:__security_cookie
0x1400d359f  xor     rax, rsp
0x1400d35a2  mov     [rsp+48h+var_10], rax
0x1400d35a7  mov     rdi, rcx
0x1400d35aa  mov     rax, [rcx]
0x1400d35ad  inc     rax
0x1400d35b0  test    rax, 0FFFFFFFFFFFFFFFEh
0x1400d35b6  jz      loc_1400D3678
0x1400d35bc  xorps   xmm0, xmm0
0x1400d35bf  xor     eax, eax
0x1400d35c1  movups  xmmword ptr [rsp+48h+var_28], xmm0; int
0x1400d35c6  mov     [r11-18h], rax
0x1400d35ca  lea     edx, [rax+12h]; int
0x1400d35cd  lea     rcx, [r11-28h]; this
0x1400d35d1  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x1400d35d6  xor     edx, edx
0x1400d35d8  mov     rcx, [rdi]
0x1400d35db  call    cs:__imp_WcCleanupContainer
0x1400d35e1  mov     rcx, [rsp+48h]; this
0x1400d35e6  test    eax, eax
0x1400d35e8  jns     short loc_1400D35F7
0x1400d35ea  mov     r9d, eax; char *
0x1400d35ed  mov     edx, 2CEh; void *
0x1400d35f2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400d35f7  mov     rcx, [rdi]; Handle
0x1400d35fa  call    cs:__imp_NtMakeTemporaryObject
0x1400d3600  mov     rcx, [rsp+48h]; this
0x1400d3605  test    eax, eax
0x1400d3607  jns     short loc_1400D3616
0x1400d3609  mov     r9d, eax; char *
0x1400d360c  mov     edx, 2D2h; void *
0x1400d3611  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x1400d3616  mov     rsi, [rdi+8]
0x1400d361a  test    rsi, rsi
0x1400d361d  jz      short loc_1400D3638
0x1400d361f  call    cs:__imp_GetLastError
0x1400d3625  mov     ebx, eax
0x1400d3627  mov     rcx, rsi
0x1400d362a  call    cs:__imp_WcReleaseContainerTerminationNotification
0x1400d3630  mov     ecx, ebx; dwErrCode
0x1400d3632  call    cs:__imp_SetLastError
0x1400d3638  mov     qword ptr [rdi+8], 0
0x1400d3640  mov     rsi, [rdi]
0x1400d3643  lea     rax, [rsi-1]
0x1400d3647  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400d364b  ja      short loc_1400D3666
0x1400d364d  call    cs:__imp_GetLastError
0x1400d3653  mov     ebx, eax
0x1400d3655  mov     rcx, rsi; hObject
0x1400d3658  call    cs:__imp_CloseHandle
0x1400d365e  mov     ecx, ebx; dwErrCode
0x1400d3660  call    cs:__imp_SetLastError
0x1400d3666  mov     qword ptr [rdi], 0
0x1400d366d  lea     rcx, [rsp+48h+var_28]; this
0x1400d3672  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
0x1400d3677  nop
0x1400d3678  mov     rcx, [rsp+48h+var_10]
0x1400d367d  xor     rcx, rsp; StackCookie
0x1400d3680  call    __security_check_cookie
0x1400d3685  mov     rbx, [rsp+48h+arg_8]
0x1400d368a  mov     rsi, [rsp+48h+arg_10]
0x1400d368f  add     rsp, 40h
0x1400d3693  pop     rdi
0x1400d3694  retn
```
