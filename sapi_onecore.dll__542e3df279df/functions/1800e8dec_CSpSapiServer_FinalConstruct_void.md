# CSpSapiServer::FinalConstruct(void)

- ea: `0x1800e8dec`
- end: `0x1800e8f46`
- name: `?FinalConstruct@CSpSapiServer@@QEAAJXZ`
- size: `346`
- prototype: `__int64 __fastcall(CSpSapiServer *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task`

## callers

- `0x18008e908`
- `0x180091d6c`

## callees

- `0x180013ec0`
- `0x180045938`
- `0x1800e8dec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800e8ea3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800e8ea3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800e8ef9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800e8ef9`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800e8f0c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800e8f0c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e8f33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e8f33`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterWindowMessageW` at `0x1800e8e11`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterWindowMessageW` at `0x1800e8e47`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterWindowMessageW` at `0x1800e8e11`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterWindowMessageW` at `0x1800e8e47`

## string_xrefs

- `0x1800e8e40`: `SpeechServicesNotification`
- `0x1800e8e0a`: `SpeechServicesStartUI`
- `0x1800e8ebd`: `SpSapiServer: Created event (handle=%u) for user logoff event`
- `0x1800e8edf`: `SpSapiServer: Failed to create event for user logoff, hr=%08x`
- `0x1800e8f18`: `No UIAccess`

## pseudocode

```c
__int64 __fastcall CSpSapiServer::FinalConstruct(CSpSapiServer *this)
{
  int v2; // ebx
  UINT v3; // eax
  UINT v4; // eax
  char *EventW; // rdi
  int Win32Error; // eax
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  v2 = 0;
  DoTraceMessage(8, "Starting sapisvr.exe ...");
  v3 = RegisterWindowMessageW(L"SpeechServicesStartUI");
  *((_DWORD *)this + 42) = v3;
  if ( (v3
     || (v2 = SpHrFromLastWin32Error(),
         DoTraceMessage(2, "RegisterWindowMessage failed when starting sapisvr - %d", v2),
         v2 >= 0))
    && ((v4 = RegisterWindowMessageW(L"SpeechServicesNotification"), (*((_DWORD *)this + 43) = v4) != 0)
     || (v2 = SpHrFromLastWin32Error(),
         DoTraceMessage(2, "RegisterWindowMessage failed when starting sapisvr - %d", v2),
         v2 >= 0)) )
  {
    if ( hEvent == (HANDLE)-1LL )
    {
      EventW = (char *)CreateEventW(0, 0, 0, 0);
      if ( (unsigned __int64)(EventW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      {
        Win32Error = SpHrFromLastWin32Error();
        DoTraceMessage(2, "SpSapiServer: Failed to create event for user logoff, hr=%08x", Win32Error);
      }
      else
      {
        DoTraceMessage(8, "SpSapiServer: Created event (handle=%u) for user logoff event", (_DWORD)hEvent);
        hEvent = EventW;
      }
    }
    TokenHandle = 0;
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
      v2 = 0;
      DoTraceMessage(8, "SapiSvr is running with %s", "No UIAccess");
      CloseHandle(TokenHandle);
    }
  }
  else
  {
    DoTraceMessage(2, "Startup of sapisvr.exe failed, %d", v2);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800e8dec  mov     [rsp+arg_8], rbx
0x1800e8df1  push    rdi
0x1800e8df2  sub     rsp, 20h
0x1800e8df6  mov     rdi, rcx
0x1800e8df9  lea     rdx, aStartingSapisv; "Starting sapisvr.exe ..."
0x1800e8e00  xor     ebx, ebx
0x1800e8e02  lea     ecx, [rbx+8]; int
0x1800e8e05  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800e8e0a  lea     rcx, aSpeechservices_0; "SpeechServicesStartUI"
0x1800e8e11  call    cs:__imp_RegisterWindowMessageW
0x1800e8e17  mov     [rdi+0A8h], eax
0x1800e8e1d  test    eax, eax
0x1800e8e1f  jnz     short loc_1800E8E40
0x1800e8e21  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x1800e8e26  mov     r8d, eax
0x1800e8e29  lea     rdx, aRegisterwindow; "RegisterWindowMessage failed when start"...
0x1800e8e30  mov     ecx, 2; int
0x1800e8e35  mov     ebx, eax
0x1800e8e37  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800e8e3c  test    ebx, ebx
0x1800e8e3e  js      short loc_1800E8E76
0x1800e8e40  lea     rcx, aSpeechservices; "SpeechServicesNotification"
0x1800e8e47  call    cs:__imp_RegisterWindowMessageW
0x1800e8e4d  mov     [rdi+0ACh], eax
0x1800e8e53  test    eax, eax
0x1800e8e55  jnz     short loc_1800E8E8F
0x1800e8e57  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x1800e8e5c  mov     r8d, eax
0x1800e8e5f  lea     rdx, aRegisterwindow; "RegisterWindowMessage failed when start"...
0x1800e8e66  mov     ecx, 2; int
0x1800e8e6b  mov     ebx, eax
0x1800e8e6d  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800e8e72  test    ebx, ebx
0x1800e8e74  jns     short loc_1800E8E8F
0x1800e8e76  mov     r8d, ebx
0x1800e8e79  lea     rdx, aStartupOfSapis; "Startup of sapisvr.exe failed, %d"
0x1800e8e80  mov     ecx, 2; int
0x1800e8e85  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800e8e8a  jmp     loc_1800E8F39
0x1800e8e8f  cmp     cs:hEvent, 0FFFFFFFFFFFFFFFFh
0x1800e8e97  jnz     short loc_1800E8EF0
0x1800e8e99  xor     r9d, r9d; lpName
0x1800e8e9c  xor     r8d, r8d; bInitialState
0x1800e8e9f  xor     edx, edx; bManualReset
0x1800e8ea1  xor     ecx, ecx; lpEventAttributes
0x1800e8ea3  call    cs:__imp_CreateEventW
0x1800e8ea9  mov     rdi, rax
0x1800e8eac  lea     rcx, [rax-1]
0x1800e8eb0  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800e8eb4  ja      short loc_1800E8ED7
0x1800e8eb6  mov     r8, cs:hEvent
0x1800e8ebd  lea     rdx, aSpsapiserverCr; "SpSapiServer: Created event (handle=%u)"...
0x1800e8ec4  mov     ecx, 8; int
0x1800e8ec9  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800e8ece  mov     cs:hEvent, rdi
0x1800e8ed5  jmp     short loc_1800E8EF0
0x1800e8ed7  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x1800e8edc  mov     r8d, eax
0x1800e8edf  lea     rdx, aSpsapiserverFa_0; "SpSapiServer: Failed to create event fo"...
0x1800e8ee6  mov     ecx, 2; int
0x1800e8eeb  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800e8ef0  mov     [rsp+28h+TokenHandle], 0
0x1800e8ef9  call    cs:__imp_GetCurrentProcess
0x1800e8eff  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x1800e8f04  mov     edx, 8; DesiredAccess
0x1800e8f09  mov     rcx, rax; ProcessHandle
0x1800e8f0c  call    cs:__imp_OpenProcessToken
0x1800e8f12  test    eax, eax
0x1800e8f14  jz      short loc_1800E8F39
0x1800e8f16  xor     ebx, ebx
0x1800e8f18  lea     r8, aNoUiaccess; "No UIAccess"
0x1800e8f1f  lea     rdx, aSapisvrIsRunni; "SapiSvr is running with %s"
0x1800e8f26  lea     ecx, [rbx+8]; int
0x1800e8f29  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800e8f2e  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x1800e8f33  call    cs:__imp_CloseHandle
0x1800e8f39  mov     eax, ebx
0x1800e8f3b  mov     rbx, [rsp+28h+arg_8]
0x1800e8f40  add     rsp, 20h
0x1800e8f44  pop     rdi
0x1800e8f45  retn
```
