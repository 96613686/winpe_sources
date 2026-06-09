# CListenerEx::AccessCheck(ulong)

- ea: `0x18000fef0`
- end: `0x18001003f`
- name: `?AccessCheck@CListenerEx@@UEAAJK@Z`
- size: `335`
- prototype: `int(CListenerEx *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180009940`
- `0x18000fef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fff4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fff4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000ff0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000ff0b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000ff27`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000ff27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ffd3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ffd3`
- `api-ms-win-security-base-l1-1-0!AccessCheckAndAuditAlarmW` at `0x18000ffa8`
- `api-ms-win-security-base-l1-1-0!AccessCheckAndAuditAlarmW` at `0x18000ffa8`

## string_xrefs

- `0x180010013`: `AccessCheckAndAuditAlarm failed: %x.`
- `0x180010026`: `AccessCheck w/o impersonation`

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
0x18000fef0  mov     [rsp+arg_0], rbx
0x18000fef5  mov     [rsp+arg_8], rsi
0x18000fefa  push    rdi
0x18000fefb  sub     rsp, 70h
0x18000feff  mov     ebx, edx
0x18000ff01  mov     rdi, rcx
0x18000ff04  xor     esi, esi
0x18000ff06  mov     [rsp+78h+TokenHandle], rsi
0x18000ff0b  call    cs:__imp_GetCurrentThread
0x18000ff12  nop     dword ptr [rax+rax+00h]
0x18000ff17  lea     r9, [rsp+78h+TokenHandle]; TokenHandle
0x18000ff1c  xor     r8d, r8d; OpenAsSelf
0x18000ff1f  mov     edx, 8; DesiredAccess
0x18000ff24  mov     rcx, rax; ThreadHandle
0x18000ff27  call    cs:__imp_OpenThreadToken
0x18000ff2e  nop     dword ptr [rax+rax+00h]
0x18000ff33  test    eax, eax
0x18000ff35  jz      loc_180010026
0x18000ff3b  mov     [rsp+78h+var_18], esi
0x18000ff3f  mov     [rsp+78h+arg_10], esi
0x18000ff46  mov     [rsp+78h+arg_18], esi
0x18000ff4d  lea     rax, [rsp+78h+arg_18]
0x18000ff55  mov     [rsp+78h+pfGenerateOnClose], rax; pfGenerateOnClose
0x18000ff5a  lea     rax, [rsp+78h+arg_10]
0x18000ff62  mov     [rsp+78h+AccessStatus], rax; AccessStatus
0x18000ff67  lea     rax, [rsp+78h+var_18]
0x18000ff6c  mov     [rsp+78h+GrantedAccess], rax; GrantedAccess
0x18000ff71  mov     [rsp+78h+ObjectCreation], esi; ObjectCreation
0x18000ff75  lea     rax, GenericMapping
0x18000ff7c  mov     [rsp+78h+GenericMapping], rax; GenericMapping
0x18000ff81  mov     [rsp+78h+DesiredAccess], ebx; DesiredAccess
0x18000ff85  mov     rax, [rdi+0C48h]
0x18000ff8c  mov     [rsp+78h+SecurityDescriptor], rax; SecurityDescriptor
0x18000ff91  lea     r9, ObjectName; "Termsrv Session"
0x18000ff98  lea     r8, ObjectName; "Termsrv Session"
0x18000ff9f  xor     edx, edx; HandleId
0x18000ffa1  lea     rcx, SubsystemName; "Termsrv"
0x18000ffa8  call    cs:__imp_AccessCheckAndAuditAlarmW
0x18000ffaf  nop     dword ptr [rax+rax+00h]
0x18000ffb4  test    eax, eax
0x18000ffb6  jz      short loc_18000FFF4
0x18000ffb8  mov     eax, 80070005h
0x18000ffbd  mov     ebx, esi
0x18000ffbf  cmp     [rsp+78h+arg_10], ebx
0x18000ffc6  cmovz   ebx, eax
0x18000ffc9  mov     rcx, [rsp+78h+TokenHandle]; hObject
0x18000ffce  test    rcx, rcx
0x18000ffd1  jz      short loc_18000FFDF
0x18000ffd3  call    cs:__imp_CloseHandle
0x18000ffda  nop     dword ptr [rax+rax+00h]
0x18000ffdf  mov     eax, ebx
0x18000ffe1  lea     r11, [rsp+78h+var_8]
0x18000ffe6  mov     rbx, [r11+10h]
0x18000ffea  mov     rsi, [r11+18h]
0x18000ffee  mov     rsp, r11
0x18000fff1  pop     rdi
0x18000fff2  retn
0x18000fff4  call    cs:__imp_GetLastError
0x18000fffb  nop     dword ptr [rax+rax+00h]
0x180010000  nop
0x180010001  mov     ebx, eax
0x180010003  test    eax, eax
0x180010005  jle     short loc_180010010
0x180010007  movzx   ebx, ax
0x18001000a  or      ebx, 80070000h
0x180010010  mov     r8d, ebx
0x180010013  lea     rdx, aAccesscheckand; "AccessCheckAndAuditAlarm failed: %x."
0x18001001a  mov     ecx, 4; int
0x18001001f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180010024  jmp     short loc_18000FFC9
0x180010026  lea     rdx, aAccesscheckWOI; "AccessCheck w/o impersonation"
0x18001002d  mov     ecx, 8; int
0x180010032  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180010037  mov     ebx, 80070005h
0x18001003c  jmp     short loc_18000FFC9
```
