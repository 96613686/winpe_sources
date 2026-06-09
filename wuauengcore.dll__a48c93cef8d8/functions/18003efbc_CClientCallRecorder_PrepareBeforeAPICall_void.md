# CClientCallRecorder::PrepareBeforeAPICall(void)

- ea: `0x18003efbc`
- end: `0x18003f15e`
- name: `?PrepareBeforeAPICall@CClientCallRecorder@@AEAAJXZ`
- size: `418`
- prototype: `__int64 __fastcall(CClientCallRecorder *__hidden this)`
- caller_count: `75`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003f170`
- `0x18003f450`
- `0x18003f6c0`
- `0x18003fc90`
- `0x180040550`
- `0x180040bb0`
- `0x180041250`
- `0x180041d00`
- `0x180042750`
- `0x180042920`
- `0x180042b70`
- `0x180042f20`
- `0x180043080`
- `0x180043190`
- `0x1800433a0`
- `0x180043700`
- `0x180043960`
- `0x180043d10`
- `0x180043fc0`
- `0x1800441c0`
- `0x180044720`
- `0x180044a70`
- `0x180044dd0`
- `0x180045080`
- `0x180045660`
- `0x1800458c0`
- `0x180045ae0`
- `0x180045d30`
- `0x1800466d0`
- `0x180046a60`
- `0x180046c60`
- `0x180046ee0`
- `0x1800470d0`
- `0x1800472b0`
- `0x1800475b0`
- `0x180047790`
- `0x180047ab0`
- `0x180047c10`
- `0x180047da0`
- `0x180048020`
- `0x180048460`
- `0x180048900`
- `0x180048ae0`
- `0x18004c370`
- `0x18004c460`
- `0x18004c6b0`
- `0x18004cc30`
- `0x18004d790`
- `0x18004db40`
- `0x18004eae0`

## callees

- `0x18000def4`
- `0x18001468c`
- `0x18003efbc`
- `0x1800549f4`
- `0x18012b618`
- `0x180238960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f0b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f0b3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003f06a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003f06a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003f053`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003f053`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f044`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f13e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f044`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f13e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18003f0a9`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18003f0a9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003f076`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003f076`

## string_xrefs

- `0x18003f0cc`: `C:\__w\1\s\src\Client\Engine\Agent\ClientCallRecorder.cpp`
- `0x18003f114`: `C:\__w\1\s\src\Client\Engine\Agent\ClientCallRecorder.cpp`
- `0x18003f0e1`: `Service is shutting down, do not accept new calls`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CClientCallRecorder::PrepareBeforeAPICall(CClientCallRecorder *this)
{
  char v2; // bl
  _DWORD *v3; // rax
  HANDLE CurrentThread; // rax
  __int64 v5; // rcx
  unsigned int v6; // ebx
  DWORD LastError; // eax
  unsigned int v9; // [rsp+20h] [rbp-38h]
  int v10; // [rsp+20h] [rbp-38h]
  HANDLE hObject; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v2 = 0;
  hObject = 0;
  _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)this + 56) + 10416LL));
  v3 = (_DWORD *)*((_QWORD *)this + 56);
  if ( v3[2602] || v3[2544] && (v3[2520] == 3 || v3[2546]) )
  {
    WUTrace(0, 0, 1, 5, 0, L"Service is shutting down, do not accept new calls", this, 1);
    v6 = -2145124322;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x809,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ClientCallRecorder.cpp",
      (const char *)0x8024001ELL,
      v10);
  }
  else
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xCu, 1, &hObject) )
    {
      v2 = 1;
      RevertToSelf();
LABEL_7:
      v5 = *((_QWORD *)this + 56);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 9732), 0) != 1 )
        CSusClientGlobal::DelayedInit(*(_QWORD *)(v5 + 9720), 0);
      if ( v2 )
        ImpersonateLoggedOnUser(hObject);
      goto LABEL_11;
    }
    LastError = GetLastError();
    if ( LastError == 1008 )
      goto LABEL_7;
    if ( !LastError )
    {
LABEL_11:
      v6 = 0;
      goto LABEL_16;
    }
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x81D,
           (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ClientCallRecorder.cpp",
           (const char *)LastError,
           v9);
  }
LABEL_16:
  _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)this + 56) + 10416LL));
  if ( hObject )
    CloseHandle(hObject);
  return v6;
}

```

## disassembly

```asm
0x18003efbc  mov     [rsp+arg_8], rbx
0x18003efc1  push    rdi
0x18003efc2  sub     rsp, 50h
0x18003efc6  mov     rax, cs:__security_cookie
0x18003efcd  xor     rax, rsp
0x18003efd0  mov     [rsp+58h+var_10], rax
0x18003efd5  mov     rdi, rcx
0x18003efd8  xor     bl, bl
0x18003efda  mov     [rsp+58h+hObject], 0
0x18003efe3  mov     rax, [rcx+1C0h]
0x18003efea  lock inc dword ptr [rax+28B0h]
0x18003eff1  xorps   xmm0, xmm0
0x18003eff4  movups  [rsp+58h+var_28], xmm0
0x18003eff9  mov     qword ptr [rsp+58h+var_28], rcx
0x18003effe  mov     byte ptr [rsp+58h+var_28+8], 1
0x18003f003  mov     rax, [rcx+1C0h]
0x18003f00a  cmp     dword ptr [rax+28A8h], 0
0x18003f011  jnz     loc_18003F0E1
0x18003f017  cmp     dword ptr [rax+27C0h], 0
0x18003f01e  jz      short loc_18003F03A
0x18003f020  cmp     dword ptr [rax+2760h], 3
0x18003f027  jz      loc_18003F0E1
0x18003f02d  cmp     dword ptr [rax+27C8h], 0
0x18003f034  jnz     loc_18003F0E1
0x18003f03a  mov     rcx, [rsp+58h+hObject]; hObject
0x18003f03f  test    rcx, rcx
0x18003f042  jz      short loc_18003F053
0x18003f044  call    cs:__imp_CloseHandle
0x18003f04a  mov     [rsp+58h+hObject], 0
0x18003f053  call    cs:__imp_GetCurrentThread
0x18003f059  lea     r9, [rsp+58h+hObject]; TokenHandle
0x18003f05e  mov     edx, 0Ch; DesiredAccess
0x18003f063  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x18003f067  mov     rcx, rax; ThreadHandle
0x18003f06a  call    cs:__imp_OpenThreadToken
0x18003f070  test    eax, eax
0x18003f072  jz      short loc_18003F0B3
0x18003f074  mov     bl, 1
0x18003f076  call    cs:__imp_RevertToSelf
0x18003f07c  mov     rcx, [rdi+1C0h]
0x18003f083  xor     eax, eax
0x18003f085  lock xadd [rcx+2604h], eax
0x18003f08d  cmp     eax, 1
0x18003f090  jz      short loc_18003F0A0
0x18003f092  xor     edx, edx
0x18003f094  mov     rcx, [rcx+25F8h]
0x18003f09b  call    ?DelayedInit@CSusClientGlobal@@QEAAXW4tagSusDestination@@@Z; CSusClientGlobal::DelayedInit(tagSusDestination)
0x18003f0a0  test    bl, bl
0x18003f0a2  jz      short loc_18003F0AF
0x18003f0a4  mov     rcx, [rsp+58h+hObject]; hToken
0x18003f0a9  call    cs:__imp_ImpersonateLoggedOnUser
0x18003f0af  xor     ebx, ebx
0x18003f0b1  jmp     short loc_18003F126
0x18003f0b3  call    cs:__imp_GetLastError
0x18003f0b9  cmp     eax, 3F0h
0x18003f0be  jz      short loc_18003F07C
0x18003f0c0  test    eax, eax
0x18003f0c2  jz      short loc_18003F0AF
0x18003f0c4  mov     rcx, [rsp+58h]; this
0x18003f0c9  mov     r9d, eax; char *
0x18003f0cc  lea     r8, aCW1SSrcClientE_27; "C:\\__w\\1\\s\\src\\Client\\Engine\\Age"...
0x18003f0d3  mov     edx, 81Dh; void *
0x18003f0d8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003f0dd  mov     ebx, eax
0x18003f0df  jmp     short loc_18003F126
0x18003f0e1  lea     rax, aServiceIsShutt; "Service is shutting down, do not accept"...
0x18003f0e8  mov     [rsp+58h+var_30], rax
0x18003f0ed  mov     qword ptr [rsp+58h+var_38], 0; int
0x18003f0f6  xor     edx, edx
0x18003f0f8  xor     ecx, ecx
0x18003f0fa  lea     r9d, [rdx+5]
0x18003f0fe  lea     r8d, [rdx+1]
0x18003f102  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003f107  mov     rcx, [rsp+58h]; this
0x18003f10c  mov     ebx, 8024001Eh
0x18003f111  mov     r9d, ebx; char *
0x18003f114  lea     r8, aCW1SSrcClientE_27; "C:\\__w\\1\\s\\src\\Client\\Engine\\Age"...
0x18003f11b  mov     edx, 809h; void *
0x18003f120  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f125  nop
0x18003f126  mov     rcx, [rdi+1C0h]
0x18003f12d  lock dec dword ptr [rcx+28B0h]
0x18003f134  mov     rcx, [rsp+58h+hObject]; hObject
0x18003f139  test    rcx, rcx
0x18003f13c  jz      short loc_18003F144
0x18003f13e  call    cs:__imp_CloseHandle
0x18003f144  mov     eax, ebx
0x18003f146  mov     rcx, [rsp+58h+var_10]
0x18003f14b  xor     rcx, rsp; StackCookie
0x18003f14e  call    __security_check_cookie
0x18003f153  mov     rbx, [rsp+58h+arg_8]
0x18003f158  add     rsp, 50h
0x18003f15c  pop     rdi
0x18003f15d  retn
```
