# ModifyPrivilegeState(ushort *,int)

- ea: `0x1800145cc`
- end: `0x1800146fb`
- name: `?ModifyPrivilegeState@@YAJPEAGH@Z`
- size: `303`
- prototype: `__int64 __fastcall(unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180014704`

## callees

- `0x1800010bc`
- `0x18000166c`
- `0x1800145cc`
- `0x18001b150`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014677`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800146ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014677`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800146ca`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180014603`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180014603`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800145f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800145f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800146c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800146c2`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180014671`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180014671`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180014637`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180014637`

## string_xrefs

- `0x180014628`: `SeTimeZonePrivilege`

## pseudocode

```c
__int64 __fastcall ModifyPrivilegeState(unsigned __int16 *a1, int a2)
{
  HANDLE CurrentProcess; // rax
  __int64 v4; // rcx
  __int64 v5; // r8
  signed int LastError; // ebx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  DWORD ReturnLength[2]; // [rsp+30h] [rbp-40h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-38h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-30h] BYREF
  struct _TOKEN_PRIVILEGES PreviousState; // [rsp+50h] [rbp-20h] BYREF

  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
  {
    NewState.Privileges[0].Luid = 0;
    NewState.PrivilegeCount = 1;
    NewState.Privileges[0].Attributes = a2 != 0 ? 2 : 0;
    if ( LookupPrivilegeValueW(0, L"SeTimeZonePrivilege", &NewState.Privileges[0].Luid) )
    {
      ReturnLength[0] = 0;
      PreviousState = 0;
      AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, &PreviousState, ReturnLength);
      LastError = GetLastError();
    }
    else
    {
      LastError = 0;
      if ( (unsigned int)dword_180030000 > 5 && (unsigned __int8)tlgKeywordOn(v4, 0x200000000000LL, v5) )
      {
        *(_QWORD *)ReturnLength = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
          v7,
          (__int64)byte_180029CCB,
          v8,
          v9,
          (__int64)ReturnLength);
      }
    }
    CloseHandle(TokenHandle);
  }
  else
  {
    LastError = GetLastError();
  }
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800145cc  mov     [rsp-8+arg_0], rbx
0x1800145d1  push    rbp
0x1800145d2  mov     rbp, rsp
0x1800145d5  sub     rsp, 70h
0x1800145d9  mov     rax, cs:__security_cookie
0x1800145e0  xor     rax, rsp
0x1800145e3  mov     [rbp+var_10], rax
0x1800145e7  mov     ebx, edx
0x1800145e9  mov     [rbp+TokenHandle], 0
0x1800145f1  call    cs:__imp_GetCurrentProcess
0x1800145f7  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800145fb  mov     edx, 28h ; '('; DesiredAccess
0x180014600  mov     rcx, rax; ProcessHandle
0x180014603  call    cs:__imp_OpenProcessToken
0x180014609  test    eax, eax
0x18001460b  jz      loc_1800146CA
0x180014611  neg     ebx
0x180014613  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], 0
0x18001461b  lea     r8, [rbp+NewState.Privileges]; lpLuid
0x18001461f  mov     [rbp+NewState.PrivilegeCount], 1
0x180014626  sbb     eax, eax
0x180014628  lea     rdx, Name; "SeTimeZonePrivilege"
0x18001462f  and     eax, 2
0x180014632  xor     ecx, ecx; lpSystemName
0x180014634  mov     [rbp+NewState.Privileges.Attributes], eax
0x180014637  call    cs:__imp_LookupPrivilegeValueW
0x18001463d  test    eax, eax
0x18001463f  jz      short loc_180014681
0x180014641  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180014645  lea     rax, [rbp+var_40]
0x180014649  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18001464e  lea     r8, [rbp+NewState]; NewState
0x180014652  lea     rax, [rbp+var_20]
0x180014656  mov     [rbp+var_40], 0
0x18001465d  xorps   xmm0, xmm0
0x180014660  mov     [rsp+70h+PreviousState], rax; PreviousState
0x180014665  mov     r9d, 10h; BufferLength
0x18001466b  xor     edx, edx; DisableAllPrivileges
0x18001466d  movups  xmmword ptr [rbp+var_20.PrivilegeCount], xmm0
0x180014671  call    cs:__imp_AdjustTokenPrivileges
0x180014677  call    cs:__imp_GetLastError
0x18001467d  mov     ebx, eax
0x18001467f  jmp     short loc_1800146BE
0x180014681  mov     eax, cs:dword_180030000
0x180014687  xor     ebx, ebx
0x180014689  cmp     eax, 5
0x18001468c  jbe     short loc_1800146BE
0x18001468e  mov     rdx, 200000000000h
0x180014698  call    _tlgKeywordOn
0x18001469d  test    al, al
0x18001469f  jz      short loc_1800146BE
0x1800146a1  lea     rax, [rbp+var_40]
0x1800146a5  mov     qword ptr [rbp+var_40], 1000000h
0x1800146ad  lea     rdx, byte_180029CCB
0x1800146b4  mov     [rsp+70h+PreviousState], rax
0x1800146b9  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x1800146be  mov     rcx, [rbp+TokenHandle]; hObject
0x1800146c2  call    cs:__imp_CloseHandle
0x1800146c8  jmp     short loc_1800146D2
0x1800146ca  call    cs:__imp_GetLastError
0x1800146d0  mov     ebx, eax
0x1800146d2  test    ebx, ebx
0x1800146d4  jle     short loc_1800146DF
0x1800146d6  movzx   ebx, bx
0x1800146d9  or      ebx, 80070000h
0x1800146df  mov     eax, ebx
0x1800146e1  mov     rcx, [rbp+var_10]
0x1800146e5  xor     rcx, rsp; StackCookie
0x1800146e8  call    __security_check_cookie
0x1800146ed  mov     rbx, [rsp+70h+arg_0]
0x1800146f5  add     rsp, 70h
0x1800146f9  pop     rbp
0x1800146fa  retn
```
