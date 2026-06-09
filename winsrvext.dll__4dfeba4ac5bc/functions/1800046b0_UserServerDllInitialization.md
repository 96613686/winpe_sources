# UserServerDllInitialization

- ea: `0x1800046b0`
- end: `0x180004bfe`
- name: `UserServerDllInitialization`
- size: `1358`
- prototype: `NTSTATUS __fastcall(__int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003548`
- `0x180003f28`
- `0x1800044c8`
- `0x1800046b0`
- `0x18000daf0`
- `0x180010c30`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180004bd8`
- `ntdll!RtlLeaveCriticalSection` at `0x180004bd8`
- `ntdll!NtResumeThread` at `0x180004bc5`
- `ntdll!NtResumeThread` at `0x180004bc5`
- `ntdll!RtlCreateUserThread` at `0x180004abd`
- `ntdll!RtlCreateUserThread` at `0x180004b31`
- `ntdll!RtlCreateUserThread` at `0x180004b96`
- `ntdll!RtlCreateUserThread` at `0x180004abd`
- `ntdll!RtlCreateUserThread` at `0x180004b31`
- `ntdll!RtlCreateUserThread` at `0x180004b96`
- `ntdll!NtCreateKey` at `0x1800049d7`
- `ntdll!NtCreateKey` at `0x1800049d7`
- `ntdll!NtOpenKey` at `0x180004929`
- `ntdll!NtOpenKey` at `0x180004929`
- `ntdll!RtlInitUnicodeString` at `0x1800048ef`
- `ntdll!RtlInitUnicodeString` at `0x18000498a`
- `ntdll!RtlInitUnicodeString` at `0x1800048ef`
- `ntdll!RtlInitUnicodeString` at `0x18000498a`
- `ntdll!NtCreateEvent` at `0x180004798`
- `ntdll!NtCreateEvent` at `0x1800047c3`
- `ntdll!NtCreateEvent` at `0x180004821`
- `ntdll!NtCreateEvent` at `0x18000484c`
- `ntdll!NtCreateEvent` at `0x180004877`
- `ntdll!NtCreateEvent` at `0x1800048bb`
- `ntdll!NtCreateEvent` at `0x180004968`
- `ntdll!NtCreateEvent` at `0x180004798`
- `ntdll!NtCreateEvent` at `0x1800047c3`
- `ntdll!NtCreateEvent` at `0x180004821`
- `ntdll!NtCreateEvent` at `0x18000484c`
- `ntdll!NtCreateEvent` at `0x180004877`
- `ntdll!NtCreateEvent` at `0x1800048bb`
- `ntdll!NtCreateEvent` at `0x180004968`
- `ntdll!RtlEnterCriticalSection` at `0x1800046fd`
- `ntdll!RtlEnterCriticalSection` at `0x1800046fd`
- `ntdll!RtlInitializeCriticalSection` at `0x1800046e2`
- `ntdll!RtlInitializeCriticalSection` at `0x1800046e2`
- `ntdll!NtClose` at `0x180004940`
- `ntdll!NtClose` at `0x180004940`
- `ntdll!EtwEventRegister` at `0x180004771`
- `ntdll!EtwEventRegister` at `0x180004771`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800047ea`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800047ea`
- `BASESRV!BaseSetProcessCreateNotify` at `0x1800049ea`
- `BASESRV!BaseSetProcessCreateNotify` at `0x1800049ea`
- `CSRSRV!CsrAddStaticServerThread` at `0x180004ade`
- `CSRSRV!CsrAddStaticServerThread` at `0x180004b52`
- `CSRSRV!CsrAddStaticServerThread` at `0x180004bb3`
- `CSRSRV!CsrAddStaticServerThread` at `0x180004ade`
- `CSRSRV!CsrAddStaticServerThread` at `0x180004b52`
- `CSRSRV!CsrAddStaticServerThread` at `0x180004bb3`
- `win32u!NtUserNotifyProcessCreate` at `0x1800049e3`
- `win32u!NtUserInitialize` at `0x180004a5c`
- `win32u!NtUserInitialize` at `0x180004a5c`
- `GDI32!GdiSupportsFontChangeEvent` at `0x18000488d`
- `GDI32!GdiSupportsFontChangeEvent` at `0x18000488d`

## string_xrefs

- `0x1800048d2`: `\Registry\Machine\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Fonts`
- `0x18000497b`: `\Registry\Machine\SOFTWARE\Microsoft\Windows NT\CurrentVersion\FontLink`

## pseudocode

```c
NTSTATUS __fastcall UserServerDllInitialization(__int64 a1)
{
  NTSTATUS result; // eax
  NTSTATUS Event; // ebx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  void *v8; // r8
  __int128 Reserved8; // [rsp+50h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp+7h] BYREF
  HANDLE ThreadHandle; // [rsp+D8h] [rbp+6Fh] BYREF
  __int64 Reserved7; // [rsp+E0h] [rbp+77h] BYREF
  __int64 v14; // [rsp+E8h] [rbp+7Fh] BYREF

  Reserved7 = 0;
  ThreadHandle = 0;
  Reserved8 = 0;
  v14 = 0;
  result = RtlInitializeCriticalSection(&gcsUserSrv);
  if ( result >= 0 )
  {
    RtlEnterCriticalSection(&gcsUserSrv);
    ghModuleWin = *(HINSTANCE *)(a1 + 16);
    *(_QWORD *)(a1 + 40) = UserServerApiDispatchTable;
    *(_QWORD *)(a1 + 48) = &UserServerApiServerValidTable;
    *(_QWORD *)(a1 + 72) = UserClientConnect;
    *(_QWORD *)(a1 + 88) = UserHardError;
    *(_QWORD *)(a1 + 112) = UserClientShutdownProcesses;
    *(_DWORD *)(a1 + 32) = 1024;
    *(_DWORD *)(a1 + 36) = 1031;
    McGenEventRegister_EventRegister();
    EtwEventRegister(WinsrvControlGuid, 0, 0, &g_EtwRegHandle);
    Event = NtCreateEvent(&gheventCancel, 0x1F0003u, 0, NotificationEvent, 0);
    if ( Event >= 0 )
    {
      Event = NtCreateEvent(&gheventCancelled, 0x1F0003u, 0, NotificationEvent, 0);
      if ( Event >= 0 )
      {
        gheventRitExited = CreateEventW(0, 1, 0, L"EventRitExited");
        if ( gheventRitExited )
        {
          Event = NtCreateEvent(&ghPowerRequestEvent, 0x1F0003u, 0, SynchronizationEvent, 0);
          if ( Event >= 0 )
          {
            Event = NtCreateEvent(&ghMediaRequestEvent, 0x1F0003u, 0, SynchronizationEvent, 0);
            if ( Event >= 0 )
            {
              Event = NtCreateEvent(&ghNlsEvent, 0x1F0003u, 0, SynchronizationEvent, 0);
              if ( Event >= 0 )
              {
                if ( (unsigned int)GdiSupportsFontChangeEvent() )
                {
                  if ( NtCreateEvent(&ghFontChangeEventHKLM, 0x1F0003u, 0, SynchronizationEvent, 0) >= 0 )
                  {
                    DestinationString = 0;
                    memset(&ObjectAttributes, 0, 44);
                    RtlInitUnicodeString(
                      &DestinationString,
                      L"\\Registry\\Machine\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Fonts");
                    ObjectAttributes.Length = 48;
                    ObjectAttributes.ObjectName = &DestinationString;
                    ObjectAttributes.RootDirectory = 0;
                    ObjectAttributes.Attributes = 64;
                    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
                    if ( NtOpenKey(&ghFontRegistryHKLM, 0x20019u, &ObjectAttributes) < 0 )
                    {
                      NtClose(ghFontChangeEventHKLM);
                      ghFontChangeEventHKLM = 0;
                    }
                  }
                }
                if ( NtCreateEvent(&ghFontLinkChangeEvent, 0x1F0003u, 0, SynchronizationEvent, 0) >= 0 )
                {
                  DestinationString = 0;
                  RtlInitUnicodeString(
                    &DestinationString,
                    L"\\Registry\\Machine\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\FontLink");
                  ObjectAttributes.ObjectName = &DestinationString;
                  *(_QWORD *)&ObjectAttributes.Length = 48;
                  *(_QWORD *)&ObjectAttributes.Attributes = 64;
                  ObjectAttributes.RootDirectory = 0;
                  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
                  NtCreateKey(&ghFontLinkKey, 0x20019u, &ObjectAttributes, 0, 0, 0, 0);
                }
                BaseSetProcessCreateNotify(NtUserNotifyProcessCreate);
                gpwszaSUCCESS = (HLOCAL)RtlLoadStringOrError(v4, 5, 0);
                gpwszaSYSTEM_INFORMATION = (HLOCAL)RtlLoadStringOrError(v5, 6, 0);
                gpwszaSYSTEM_WARNING = (HLOCAL)RtlLoadStringOrError(v6, 7, 0);
                gpwszaSYSTEM_ERROR = (HLOCAL)RtlLoadStringOrError(v7, 8, 0);
                Event = NtUserInitialize(ghPowerRequestEvent, ghMediaRequestEvent);
                if ( Event >= 0 )
                {
                  Event = WinStationAPIInit();
                  if ( Event >= 0 )
                  {
                    Event = RtlCreateUserThread(
                              (PVOID)0xFFFFFFFFFFFFFFFFLL,
                              0,
                              0,
                              0,
                              0,
                              0,
                              GdiAddInitialFontsThread,
                              0,
                              &Reserved7,
                              &Reserved8);
                    if ( Event >= 0 )
                    {
                      CsrAddStaticServerThread(Reserved7, &Reserved8, 0);
                      Event = RegisterForDeviceBroadcastNotifications();
                      if ( Event >= 0 )
                      {
                        LOBYTE(v8) = 1;
                        Event = RtlCreateUserThread(
                                  (PVOID)0xFFFFFFFFFFFFFFFFLL,
                                  0,
                                  v8,
                                  0,
                                  0,
                                  0,
                                  NotificationThread,
                                  0,
                                  &ThreadHandle,
                                  &Reserved8);
                        if ( Event >= 0 )
                        {
                          CsrAddStaticServerThread(ThreadHandle, &Reserved8, 0);
                          Event = RtlCreateUserThread(
                                    (PVOID)0xFFFFFFFFFFFFFFFFLL,
                                    0,
                                    0,
                                    0,
                                    0,
                                    0,
                                    PowerNotificationThread,
                                    0,
                                    &v14,
                                    &Reserved8);
                          if ( Event >= 0 )
                          {
                            CsrAddStaticServerThread(v14, &Reserved8, 0);
                            NtResumeThread(ThreadHandle, 0);
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
        else
        {
          Event = -1073741823;
        }
      }
    }
    RtlLeaveCriticalSection(&gcsUserSrv);
    if ( Event < 0 )
      UserServerCleanup();
    return Event;
  }
  return result;
}

```

## disassembly

```asm
0x1800046b0  push    rbp
0x1800046b2  push    rbx
0x1800046b3  push    rsi
0x1800046b4  push    rdi
0x1800046b5  push    r14
0x1800046b7  lea     rbp, [rsp-37h]
0x1800046bc  sub     rsp, 0A0h
0x1800046c3  xor     edi, edi
0x1800046c5  mov     rbx, rcx
0x1800046c8  xorps   xmm0, xmm0
0x1800046cb  mov     [rbp+57h+arg_10], rdi
0x1800046cf  lea     rcx, gcsUserSrv; CriticalSection
0x1800046d6  mov     [rbp+57h+ThreadHandle], rdi
0x1800046da  movups  [rbp+57h+var_70], xmm0
0x1800046de  mov     [rbp+57h+arg_18], rdi
0x1800046e2  call    cs:__imp_RtlInitializeCriticalSection
0x1800046e9  nop     dword ptr [rax+rax+00h]
0x1800046ee  test    eax, eax
0x1800046f0  js      loc_180004BEF
0x1800046f6  lea     rcx, gcsUserSrv; CriticalSection
0x1800046fd  call    cs:__imp_RtlEnterCriticalSection
0x180004704  nop     dword ptr [rax+rax+00h]
0x180004709  mov     rax, [rbx+10h]
0x18000470d  mov     cs:ghModuleWin, rax
0x180004714  lea     rax, UserServerApiDispatchTable
0x18000471b  mov     [rbx+28h], rax
0x18000471f  lea     rax, UserServerApiServerValidTable
0x180004726  mov     [rbx+30h], rax
0x18000472a  lea     rax, UserClientConnect
0x180004731  mov     [rbx+48h], rax
0x180004735  lea     rax, UserHardError
0x18000473c  mov     [rbx+58h], rax
0x180004740  lea     rax, UserClientShutdownProcesses
0x180004747  mov     [rbx+70h], rax
0x18000474b  mov     dword ptr [rbx+20h], 400h
0x180004752  mov     dword ptr [rbx+24h], 407h
0x180004759  call    McGenEventRegister_EventRegister
0x18000475e  lea     r9, g_EtwRegHandle
0x180004765  xor     r8d, r8d
0x180004768  xor     edx, edx
0x18000476a  lea     rcx, WinsrvControlGuid
0x180004771  call    cs:__imp_EtwEventRegister
0x180004778  nop     dword ptr [rax+rax+00h]
0x18000477d  mov     r14d, 1F0003h
0x180004783  mov     [rsp+0C0h+InitialState], dil; InitialState
0x180004788  mov     edx, r14d; DesiredAccess
0x18000478b  lea     rcx, gheventCancel; EventHandle
0x180004792  xor     r9d, r9d; EventType
0x180004795  xor     r8d, r8d; ObjectAttributes
0x180004798  call    cs:__imp_NtCreateEvent
0x18000479f  nop     dword ptr [rax+rax+00h]
0x1800047a4  mov     ebx, eax
0x1800047a6  test    eax, eax
0x1800047a8  js      loc_180004BD1
0x1800047ae  xor     r9d, r9d; EventType
0x1800047b1  mov     [rsp+0C0h+InitialState], dil; InitialState
0x1800047b6  xor     r8d, r8d; ObjectAttributes
0x1800047b9  lea     rcx, gheventCancelled; EventHandle
0x1800047c0  mov     edx, r14d; DesiredAccess
0x1800047c3  call    cs:__imp_NtCreateEvent
0x1800047ca  nop     dword ptr [rax+rax+00h]
0x1800047cf  mov     ebx, eax
0x1800047d1  test    eax, eax
0x1800047d3  js      loc_180004BD1
0x1800047d9  lea     esi, [rdi+1]
0x1800047dc  xor     r8d, r8d; bInitialState
0x1800047df  mov     edx, esi; bManualReset
0x1800047e1  lea     r9, Name; "EventRitExited"
0x1800047e8  xor     ecx, ecx; lpEventAttributes
0x1800047ea  call    cs:__imp_CreateEventW
0x1800047f1  nop     dword ptr [rax+rax+00h]
0x1800047f6  mov     cs:gheventRitExited, rax
0x1800047fd  test    rax, rax
0x180004800  jnz     short loc_18000480C
0x180004802  mov     ebx, 0C0000001h
0x180004807  jmp     loc_180004BD1
0x18000480c  mov     r9d, esi; EventType
0x18000480f  mov     [rsp+0C0h+InitialState], dil; InitialState
0x180004814  xor     r8d, r8d; ObjectAttributes
0x180004817  lea     rcx, ghPowerRequestEvent; EventHandle
0x18000481e  mov     edx, r14d; DesiredAccess
0x180004821  call    cs:__imp_NtCreateEvent
0x180004828  nop     dword ptr [rax+rax+00h]
0x18000482d  mov     ebx, eax
0x18000482f  test    eax, eax
0x180004831  js      loc_180004BD1
0x180004837  mov     r9d, esi; EventType
0x18000483a  mov     [rsp+0C0h+InitialState], dil; InitialState
0x18000483f  xor     r8d, r8d; ObjectAttributes
0x180004842  lea     rcx, ghMediaRequestEvent; EventHandle
0x180004849  mov     edx, r14d; DesiredAccess
0x18000484c  call    cs:__imp_NtCreateEvent
0x180004853  nop     dword ptr [rax+rax+00h]
0x180004858  mov     ebx, eax
0x18000485a  test    eax, eax
0x18000485c  js      loc_180004BD1
0x180004862  mov     r9d, esi; EventType
0x180004865  mov     [rsp+0C0h+InitialState], dil; InitialState
0x18000486a  xor     r8d, r8d; ObjectAttributes
0x18000486d  lea     rcx, ghNlsEvent; EventHandle
0x180004874  mov     edx, r14d; DesiredAccess
0x180004877  call    cs:__imp_NtCreateEvent
0x18000487e  nop     dword ptr [rax+rax+00h]
0x180004883  mov     ebx, eax
0x180004885  test    eax, eax
0x180004887  js      loc_180004BD1
0x18000488d  call    cs:__imp_GdiSupportsFontChangeEvent
0x180004894  nop     dword ptr [rax+rax+00h]
0x180004899  mov     ebx, 30h ; '0'
0x18000489e  test    eax, eax
0x1800048a0  jz      loc_180004953
0x1800048a6  mov     r9d, esi; EventType
0x1800048a9  mov     [rsp+0C0h+InitialState], dil; InitialState
0x1800048ae  xor     r8d, r8d; ObjectAttributes
0x1800048b1  lea     rcx, ghFontChangeEventHKLM; EventHandle
0x1800048b8  mov     edx, r14d; DesiredAccess
0x1800048bb  call    cs:__imp_NtCreateEvent
0x1800048c2  nop     dword ptr [rax+rax+00h]
0x1800048c7  test    eax, eax
0x1800048c9  js      loc_180004953
0x1800048cf  xorps   xmm0, xmm0
0x1800048d2  lea     rdx, aRegistryMachin_3; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x1800048d9  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800048dd  xor     eax, eax
0x1800048df  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800048e3  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800048e7  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800048eb  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800048ef  call    cs:__imp_RtlInitUnicodeString
0x1800048f6  nop     dword ptr [rax+rax+00h]
0x1800048fb  lea     rax, [rbp+57h+DestinationString]
0x1800048ff  mov     [rbp+57h+ObjectAttributes.Length], ebx
0x180004902  xorps   xmm0, xmm0
0x180004905  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180004909  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000490d  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x180004911  mov     edx, 20019h; DesiredAccess
0x180004916  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18000491d  lea     rcx, ghFontRegistryHKLM; KeyHandle
0x180004924  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180004929  call    cs:__imp_NtOpenKey
0x180004930  nop     dword ptr [rax+rax+00h]
0x180004935  test    eax, eax
0x180004937  jns     short loc_180004953
0x180004939  mov     rcx, cs:ghFontChangeEventHKLM; Handle
0x180004940  call    cs:__imp_NtClose
0x180004947  nop     dword ptr [rax+rax+00h]
0x18000494c  mov     cs:ghFontChangeEventHKLM, rdi
0x180004953  mov     r9d, esi; EventType
0x180004956  mov     [rsp+0C0h+InitialState], dil; InitialState
0x18000495b  xor     r8d, r8d; ObjectAttributes
0x18000495e  lea     rcx, ghFontLinkChangeEvent; EventHandle
0x180004965  mov     edx, r14d; DesiredAccess
0x180004968  call    cs:__imp_NtCreateEvent
0x18000496f  nop     dword ptr [rax+rax+00h]
0x180004974  test    eax, eax
0x180004976  js      short loc_1800049E3
0x180004978  xorps   xmm0, xmm0
0x18000497b  lea     rdx, aRegistryMachin_2; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x180004982  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180004986  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18000498a  call    cs:__imp_RtlInitUnicodeString
0x180004991  nop     dword ptr [rax+rax+00h]
0x180004996  lea     rax, [rbp+57h+DestinationString]
0x18000499a  mov     [rsp+0C0h+Disposition], rdi; Disposition
0x18000499f  xorps   xmm0, xmm0
0x1800049a2  mov     [rsp+0C0h+CreateOptions], edi; CreateOptions
0x1800049a6  xor     r9d, r9d; TitleIndex
0x1800049a9  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800049ad  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800049b1  mov     qword ptr [rbp+57h+ObjectAttributes.Length], rbx
0x1800049b5  mov     edx, 20019h; DesiredAccess
0x1800049ba  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800049c2  lea     rcx, ghFontLinkKey; KeyHandle
0x1800049c9  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x1800049cd  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800049d2  mov     qword ptr [rsp+0C0h+InitialState], rdi; Class
0x1800049d7  call    cs:__imp_NtCreateKey
0x1800049de  nop     dword ptr [rax+rax+00h]
0x1800049e3  mov     rcx, cs:__imp_NtUserNotifyProcessCreate
0x1800049ea  call    cs:__imp_BaseSetProcessCreateNotify
0x1800049f1  nop     dword ptr [rax+rax+00h]
0x1800049f6  xor     r9d, r9d
0x1800049f9  xor     r8d, r8d
0x1800049fc  lea     edx, [r9+5]
0x180004a00  call    RtlLoadStringOrError
0x180004a05  xor     r9d, r9d
0x180004a08  mov     cs:gpwszaSUCCESS, rax
0x180004a0f  xor     r8d, r8d
0x180004a12  lea     edx, [r9+6]
0x180004a16  call    RtlLoadStringOrError
0x180004a1b  xor     r9d, r9d
0x180004a1e  mov     cs:gpwszaSYSTEM_INFORMATION, rax
0x180004a25  xor     r8d, r8d
0x180004a28  lea     edx, [r9+7]
0x180004a2c  call    RtlLoadStringOrError
0x180004a31  xor     r9d, r9d
0x180004a34  mov     cs:gpwszaSYSTEM_WARNING, rax
0x180004a3b  xor     r8d, r8d
0x180004a3e  lea     edx, [r9+8]
0x180004a42  call    RtlLoadStringOrError
0x180004a47  mov     rdx, cs:ghMediaRequestEvent
0x180004a4e  mov     rcx, cs:ghPowerRequestEvent
0x180004a55  mov     cs:gpwszaSYSTEM_ERROR, rax
0x180004a5c  call    cs:__imp_NtUserInitialize
0x180004a63  nop     dword ptr [rax+rax+00h]
0x180004a68  mov     ebx, eax
0x180004a6a  test    eax, eax
0x180004a6c  js      loc_180004BD1
0x180004a72  call    WinStationAPIInit
0x180004a77  mov     ebx, eax
0x180004a79  test    eax, eax
0x180004a7b  js      loc_180004BD1
0x180004a81  lea     rax, [rbp+57h+var_70]
0x180004a85  or      r14, 0FFFFFFFFFFFFFFFFh
0x180004a89  mov     [rsp+0C0h+Reserved8], rax; Reserved8
0x180004a8e  xor     r9d, r9d; Reserved2
0x180004a91  lea     rax, [rbp+57h+arg_10]
0x180004a95  xor     r8d, r8d; Reserved1
0x180004a98  mov     [rsp+0C0h+Reserved7], rax; Reserved7
0x180004a9d  xor     edx, edx; OutThreadHandle
0x180004a9f  mov     [rsp+0C0h+Reserved6], rdi; Reserved6
0x180004aa4  lea     rax, GdiAddInitialFontsThread
0x180004aab  mov     [rsp+0C0h+Disposition], rax; Reserved5
0x180004ab0  mov     rcx, r14; ThreadContext
0x180004ab3  mov     qword ptr [rsp+0C0h+CreateOptions], rdi; Reserved4
0x180004ab8  mov     qword ptr [rsp+0C0h+InitialState], rdi; Reserved3
0x180004abd  call    cs:__imp_RtlCreateUserThread
0x180004ac4  nop     dword ptr [rax+rax+00h]
0x180004ac9  mov     ebx, eax
0x180004acb  test    eax, eax
0x180004acd  js      loc_180004BD1
0x180004ad3  mov     rcx, [rbp+57h+arg_10]
0x180004ad7  lea     rdx, [rbp+57h+var_70]
0x180004adb  xor     r8d, r8d
0x180004ade  call    cs:__imp_CsrAddStaticServerThread
0x180004ae5  nop     dword ptr [rax+rax+00h]
0x180004aea  call    RegisterForDeviceBroadcastNotifications
0x180004aef  mov     ebx, eax
0x180004af1  test    eax, eax
0x180004af3  js      loc_180004BD1
0x180004af9  lea     rax, [rbp+57h+var_70]
0x180004afd  xor     r9d, r9d; Reserved2
0x180004b00  mov     [rsp+0C0h+Reserved8], rax; Reserved8
0x180004b05  mov     r8b, sil; Reserved1
0x180004b08  lea     rax, [rbp+57h+ThreadHandle]
0x180004b0c  xor     edx, edx; OutThreadHandle
0x180004b0e  mov     [rsp+0C0h+Reserved7], rax; Reserved7
0x180004b13  mov     rcx, r14; ThreadContext
0x180004b16  mov     [rsp+0C0h+Reserved6], rdi; Reserved6
0x180004b1b  lea     rax, NotificationThread
0x180004b22  mov     [rsp+0C0h+Disposition], rax; Reserved5
0x180004b27  mov     qword ptr [rsp+0C0h+CreateOptions], rdi; Reserved4
0x180004b2c  mov     qword ptr [rsp+0C0h+InitialState], rdi; Reserved3
0x180004b31  call    cs:__imp_RtlCreateUserThread
0x180004b38  nop     dword ptr [rax+rax+00h]
0x180004b3d  mov     ebx, eax
0x180004b3f  test    eax, eax
0x180004b41  js      loc_180004BD1
0x180004b47  mov     rcx, [rbp+57h+ThreadHandle]
0x180004b4b  lea     rdx, [rbp+57h+var_70]
0x180004b4f  xor     r8d, r8d
0x180004b52  call    cs:__imp_CsrAddStaticServerThread
0x180004b59  nop     dword ptr [rax+rax+00h]
0x180004b5e  lea     rax, [rbp+57h+var_70]
0x180004b62  xor     r9d, r9d; Reserved2
0x180004b65  mov     [rsp+0C0h+Reserved8], rax; Reserved8
0x180004b6a  xor     r8d, r8d; Reserved1
0x180004b6d  lea     rax, [rbp+57h+arg_18]
0x180004b71  xor     edx, edx; OutThreadHandle
0x180004b73  mov     [rsp+0C0h+Reserved7], rax; Reserved7
0x180004b78  mov     rcx, r14; ThreadContext
0x180004b7b  mov     [rsp+0C0h+Reserved6], rdi; Reserved6
0x180004b80  lea     rax, PowerNotificationThread
0x180004b87  mov     [rsp+0C0h+Disposition], rax; Reserved5
0x180004b8c  mov     qword ptr [rsp+0C0h+CreateOptions], rdi; Reserved4
0x180004b91  mov     qword ptr [rsp+0C0h+InitialState], rdi; Reserved3
0x180004b96  call    cs:__imp_RtlCreateUserThread
0x180004b9d  nop     dword ptr [rax+rax+00h]
0x180004ba2  mov     ebx, eax
0x180004ba4  test    eax, eax
0x180004ba6  js      short loc_180004BD1
0x180004ba8  mov     rcx, [rbp+57h+arg_18]
0x180004bac  lea     rdx, [rbp+57h+var_70]
0x180004bb0  xor     r8d, r8d
0x180004bb3  call    cs:__imp_CsrAddStaticServerThread
0x180004bba  nop     dword ptr [rax+rax+00h]
0x180004bbf  mov     rcx, [rbp+57h+ThreadHandle]; ThreadHandle
0x180004bc3  xor     edx, edx; SuspendCount
0x180004bc5  call    cs:__imp_NtResumeThread
0x180004bcc  nop     dword ptr [rax+rax+00h]
0x180004bd1  lea     rcx, gcsUserSrv; CriticalSection
0x180004bd8  call    cs:__imp_RtlLeaveCriticalSection
0x180004bdf  nop     dword ptr [rax+rax+00h]
0x180004be4  test    ebx, ebx
0x180004be6  jns     short loc_180004BED
0x180004be8  call    UserServerCleanup
0x180004bed  mov     eax, ebx
0x180004bef  add     rsp, 0A0h
0x180004bf6  pop     r14
  ... truncated ...
```
