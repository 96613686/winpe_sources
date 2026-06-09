# CListenerEx::AccessCheck(ulong)

- ea: `0x18000f830`
- end: `0x18000f960`
- name: `?AccessCheck@CListenerEx@@UEAAJK@Z`
- size: `304`
- prototype: `int(CListenerEx *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000a210`
- `0x18000f830`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f91b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f91b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000f84b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000f84b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000f861`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000f861`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f901`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f901`
- `api-ms-win-security-base-l1-1-0!AccessCheckAndAuditAlarmW` at `0x18000f8dc`
- `api-ms-win-security-base-l1-1-0!AccessCheckAndAuditAlarmW` at `0x18000f8dc`

## string_xrefs

- `0x18000f934`: `AccessCheckAndAuditAlarm failed: %x.`
- `0x18000f947`: `AccessCheck w/o impersonation`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CListenerEx::AccessCheck(PSECURITY_DESCRIPTOR *this, DWORD a2)
{
  HANDLE CurrentThread; // rax
  unsigned int v5; // ebx
  signed int LastError; // eax
  DWORD GrantedAccess; // [rsp+60h] [rbp-18h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp-10h] BYREF
  WINBOOL AccessStatus; // [rsp+90h] [rbp+18h] BYREF
  WINBOOL pfGenerateOnClose; // [rsp+98h] [rbp+20h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
  {
    GrantedAccess = 0;
    AccessStatus = 0;
    pfGenerateOnClose = 0;
    if ( AccessCheckAndAuditAlarmW(
           L"Termsrv",
           0,
           (LPWSTR)L"Termsrv Session",
           (LPWSTR)L"Termsrv Session",
           this[393],
           a2,
           (PGENERIC_MAPPING)&GenericMapping,
           0,
           &GrantedAccess,
           &AccessStatus,
           &pfGenerateOnClose) )
    {
      v5 = 0;
      if ( !AccessStatus )
        v5 = -2147024891;
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      _DbgPrintMessage(4, "AccessCheckAndAuditAlarm failed: %x.", v5);
    }
  }
  else
  {
    _DbgPrintMessage(8, "AccessCheck w/o impersonation");
    v5 = -2147024891;
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v5;
}

```

## disassembly

```asm
0x18000f830  mov     [rsp+arg_0], rbx
0x18000f835  mov     [rsp+arg_8], rsi
0x18000f83a  push    rdi
0x18000f83b  sub     rsp, 70h
0x18000f83f  mov     ebx, edx
0x18000f841  mov     rdi, rcx
0x18000f844  xor     esi, esi
0x18000f846  mov     [rsp+78h+TokenHandle], rsi
0x18000f84b  call    cs:__imp_GetCurrentThread
0x18000f851  lea     r9, [rsp+78h+TokenHandle]; TokenHandle
0x18000f856  xor     r8d, r8d; OpenAsSelf
0x18000f859  mov     edx, 8; DesiredAccess
0x18000f85e  mov     rcx, rax; ThreadHandle
0x18000f861  call    cs:__imp_OpenThreadToken
0x18000f867  test    eax, eax
0x18000f869  jz      loc_18000F947
0x18000f86f  mov     [rsp+78h+var_18], esi
0x18000f873  mov     [rsp+78h+arg_10], esi
0x18000f87a  mov     [rsp+78h+arg_18], esi
0x18000f881  lea     rax, [rsp+78h+arg_18]
0x18000f889  mov     [rsp+78h+pfGenerateOnClose], rax; pfGenerateOnClose
0x18000f88e  lea     rax, [rsp+78h+arg_10]
0x18000f896  mov     [rsp+78h+AccessStatus], rax; AccessStatus
0x18000f89b  lea     rax, [rsp+78h+var_18]
0x18000f8a0  mov     [rsp+78h+GrantedAccess], rax; GrantedAccess
0x18000f8a5  mov     [rsp+78h+ObjectCreation], esi; ObjectCreation
0x18000f8a9  lea     rax, GenericMapping
0x18000f8b0  mov     [rsp+78h+GenericMapping], rax; GenericMapping
0x18000f8b5  mov     [rsp+78h+DesiredAccess], ebx; DesiredAccess
0x18000f8b9  mov     rax, [rdi+0C48h]
0x18000f8c0  mov     [rsp+78h+SecurityDescriptor], rax; SecurityDescriptor
0x18000f8c5  lea     r9, ObjectName; "Termsrv Session"
0x18000f8cc  lea     r8, ObjectName; "Termsrv Session"
0x18000f8d3  xor     edx, edx; HandleId
0x18000f8d5  lea     rcx, SubsystemName; "Termsrv"
0x18000f8dc  call    cs:__imp_AccessCheckAndAuditAlarmW
0x18000f8e2  test    eax, eax
0x18000f8e4  jz      short loc_18000F91B
0x18000f8e6  mov     eax, 80070005h
0x18000f8eb  mov     ebx, esi
0x18000f8ed  cmp     [rsp+78h+arg_10], ebx
0x18000f8f4  cmovz   ebx, eax
0x18000f8f7  mov     rcx, [rsp+78h+TokenHandle]; hObject
0x18000f8fc  test    rcx, rcx
0x18000f8ff  jz      short loc_18000F907
0x18000f901  call    cs:__imp_CloseHandle
0x18000f907  mov     eax, ebx
0x18000f909  lea     r11, [rsp+78h+var_8]
0x18000f90e  mov     rbx, [r11+10h]
0x18000f912  mov     rsi, [r11+18h]
0x18000f916  mov     rsp, r11
0x18000f919  pop     rdi
0x18000f91a  retn
0x18000f91b  call    cs:__imp_GetLastError
0x18000f921  nop
0x18000f922  mov     ebx, eax
0x18000f924  test    eax, eax
0x18000f926  jle     short loc_18000F931
0x18000f928  movzx   ebx, ax
0x18000f92b  or      ebx, 80070000h
0x18000f931  mov     r8d, ebx
0x18000f934  lea     rdx, aAccesscheckand; "AccessCheckAndAuditAlarm failed: %x."
0x18000f93b  mov     ecx, 4; int
0x18000f940  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000f945  jmp     short loc_18000F8F7
0x18000f947  lea     rdx, aAccesscheckWOI; "AccessCheck w/o impersonation"
0x18000f94e  mov     ecx, 8; int
0x18000f953  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000f958  mov     ebx, 80070005h
0x18000f95d  jmp     short loc_18000F8F7
```
