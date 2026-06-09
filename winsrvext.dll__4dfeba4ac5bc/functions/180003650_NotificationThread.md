# NotificationThread

- ea: `0x180003650`
- end: `0x180003a6c`
- name: `NotificationThread`
- size: `1052`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180001e68`
- `0x1800023c0`
- `0x1800025f8`
- `0x180002684`
- `0x180002aec`
- `0x180002e1c`
- `0x180003128`
- `0x180003650`
- `0x1800042f0`
- `0x180004384`

## import_xrefs

- `ntdll!NtResetEvent` at `0x1800039cf`
- `ntdll!NtResetEvent` at `0x1800039cf`
- `ntdll!NtWaitForMultipleObjects` at `0x18000395b`
- `ntdll!NtWaitForMultipleObjects` at `0x18000395b`
- `ntdll!NtSetInformationThread` at `0x1800036e4`
- `ntdll!NtSetInformationThread` at `0x1800036e4`
- `ntdll!NtNotifyChangeKey` at `0x18000388b`
- `ntdll!NtNotifyChangeKey` at `0x1800038e5`
- `ntdll!NtNotifyChangeKey` at `0x180003935`
- `ntdll!NtNotifyChangeKey` at `0x18000388b`
- `ntdll!NtNotifyChangeKey` at `0x1800038e5`
- `ntdll!NtNotifyChangeKey` at `0x180003935`
- `ntdll!RtlInitUnicodeString` at `0x1800037a5`
- `ntdll!RtlInitUnicodeString` at `0x1800037a5`
- `ntdll!NtCreateEvent` at `0x180003806`
- `ntdll!NtCreateEvent` at `0x180003806`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800036c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800036c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003823`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003823`
- `BASESRV!BaseSrvNlsUpdateRegistryCache` at `0x18000398a`
- `BASESRV!BaseSrvNlsUpdateRegistryCache` at `0x18000398a`
- `GDI32!EnableEUDC` at `0x180003a3b`
- `GDI32!EnableEUDC` at `0x180003a50`
- `GDI32!EnableEUDC` at `0x180003a3b`
- `GDI32!EnableEUDC` at `0x180003a50`
- `ext-ms-win32-subsystem-query-l1-1-0!QueryWin32SubsystemHost` at `0x18000373e`
- `ext-ms-win32-subsystem-query-l1-1-0!QueryWin32SubsystemHost` at `0x18000373e`

## pseudocode

```c
void __noreturn NotificationThread()
{
  int v0; // r13d
  __int64 v1; // r14
  __int64 v2; // r12
  int v3; // edi
  ULONG v4; // esi
  int v5; // ebx
  int v6; // r15d
  HANDLE CurrentThread; // rax
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v10; // eax
  BOOL v11; // eax
  HLOCAL v12; // rdi
  NTSTATUS v13; // ebx
  int v14; // eax
  bool v15; // sf
  __int64 v16; // rbx
  __int64 v17; // rdx
  __int64 v18; // r8
  int v19; // [rsp+50h] [rbp-B0h]
  int v20; // [rsp+54h] [rbp-ACh]
  int v21; // [rsp+58h] [rbp-A8h]
  int ThreadInformation; // [rsp+5Ch] [rbp-A4h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-A0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-68h] BYREF
  HANDLE Object[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v27; // [rsp+B8h] [rbp-48h]
  __int128 v28; // [rsp+C8h] [rbp-38h]
  wchar_t pszDest[256]; // [rsp+E0h] [rbp-20h] BYREF

  v0 = -1;
  hMem = 0;
  LODWORD(v1) = -1;
  LODWORD(v2) = -1;
  v3 = -1;
  v4 = 3;
  v19 = 1;
  v5 = 1;
  v21 = 1;
  v6 = 1;
  ThreadInformation = 3;
  *(_OWORD *)Object = 0;
  v27 = 0;
  v28 = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  CurrentThread = GetCurrentThread();
  NtSetInformationThread(CurrentThread, ThreadPriority, &ThreadInformation, 4u);
  Object[0] = ghNlsEvent;
  Object[1] = ghMediaRequestEvent;
  if ( ghFontChangeEventHKLM )
  {
    v0 = 2;
    *(_QWORD *)&v27 = ghFontChangeEventHKLM;
  }
  else
  {
    v4 = 2;
  }
  if ( ghFontLinkChangeEvent )
  {
    v10 = gSessionId;
    if ( !gSessionId )
    {
LABEL_10:
      if ( v10 != gServiceSessionId )
      {
        StringCchPrintfW(pszDest, 0x100u, L"%ws\\%ld\\BaseNamedObjects\\%ws", L"\\Sessions", v10, L"ScNetDrvMsg");
        RtlInitUnicodeString(&DestinationString, pszDest);
        v11 = CreateBSMEventSD(&hMem);
        v8 = 0;
        if ( v11 )
        {
          v12 = hMem;
          ObjectAttributes.ObjectName = &DestinationString;
          ObjectAttributes.RootDirectory = 0;
          ObjectAttributes.SecurityQualityOfService = 0;
          ObjectAttributes.Length = 48;
          ObjectAttributes.Attributes = 192;
          ObjectAttributes.SecurityDescriptor = hMem;
          v13 = NtCreateEvent(&Object[v4], 0x1F0003u, &ObjectAttributes, SynchronizationEvent, 0);
          v14 = -1;
          if ( v13 >= 0 )
            v14 = v4;
          v20 = v14;
          LocalFree(v12);
          v3 = v20;
          v9 = v4 + 1;
          v15 = v13 < 0;
          v5 = 1;
          if ( v15 )
            v9 = v4;
          v4 = v9;
        }
      }
      StartRegReadRead(v9, v8);
      while ( 1 )
      {
        if ( ghFontChangeEventHKLM && v5 )
        {
          NtNotifyChangeKey(ghFontRegistryHKLM, ghFontChangeEventHKLM, 0, 0, &IoStatusRegChange, 0xFu, 1u, 0, 0, 1u);
          v19 = 0;
        }
        if ( ghFontChangeEventHKCU && v21 )
        {
          NtNotifyChangeKey(ghFontRegistryHKCU, ghFontChangeEventHKCU, 0, 0, &IoStatusRegChange, 0xFu, 1u, 0, 0, 1u);
          v21 = 0;
        }
        if ( v6
          && NtNotifyChangeKey(ghFontLinkKey, ghFontLinkChangeEvent, 0, 0, &IoStatusRegChange, 4u, 1u, 0, 0, 1u) >= 0 )
        {
          v6 = 0;
        }
        v16 = (unsigned int)NtWaitForMultipleObjects(v4, Object, WaitAny, 1u, 0);
        EtwLogNotificationStart(v16, v17, v18);
        if ( (_DWORD)v16 )
        {
          if ( (_DWORD)v16 == 1 )
          {
            HandleMediaChangeEvent();
            NtResetEvent(Object[1], 0);
          }
          else if ( v3 == -1 || (_DWORD)v16 != v3 )
          {
            if ( v0 == -1 || (_DWORD)v16 != v0 )
            {
              if ( (_DWORD)v1 == -1 || (_DWORD)v16 != (_DWORD)v1 )
              {
                if ( (_DWORD)v2 != -1 && (_DWORD)v16 == (_DWORD)v2 )
                {
                  EnableEUDC(0);
                  v6 = 1;
                  EnableEUDC(1);
                }
              }
              else
              {
                HandleFontChangeEvent(ghFontRegistryHKCU);
                v21 = 1;
              }
            }
            else
            {
              HandleFontChangeEvent(ghFontRegistryHKLM);
              v19 = 1;
            }
          }
          else
          {
            HandleRemoteNetDeviceChangeEvent();
          }
        }
        else if ( gfLogon )
        {
          gfLogon = 0;
          BaseSrvNlsUpdateRegistryCache(0, 0);
          if ( ghFontChangeEventHKCU )
          {
            if ( (_DWORD)v1 == -1 )
            {
              v1 = v4++;
              Object[v1] = ghFontChangeEventHKCU;
            }
          }
        }
        EtwLogNotificationStop((unsigned int)v16);
        v5 = v19;
      }
    }
    if ( (unsigned __int8)IsQueryWin32SubsystemHostPresent() && (unsigned int)QueryWin32SubsystemHost() == 1 )
    {
      v2 = v4++;
      Object[v2] = ghFontLinkChangeEvent;
    }
  }
  v10 = gSessionId;
  goto LABEL_10;
}

```

## disassembly

```asm
0x180003650  push    rbp
0x180003652  push    rbx
0x180003653  push    rsi
0x180003654  push    rdi
0x180003655  push    r12
0x180003657  push    r13
0x180003659  push    r14
0x18000365b  push    r15
0x18000365d  lea     rbp, [rsp-1F8h]
0x180003665  sub     rsp, 2F8h
0x18000366c  mov     rax, cs:__security_cookie
0x180003673  xor     rax, rsp
0x180003676  mov     [rbp+230h+var_50], rax
0x18000367d  xorps   xmm0, xmm0
0x180003680  xor     eax, eax
0x180003682  or      r13d, 0FFFFFFFFh
0x180003686  mov     [rsp+330h+hMem], rax
0x18000368b  movups  xmmword ptr [rsp+330h+ObjectAttributes.ObjectName], xmm0
0x180003690  mov     r14d, r13d
0x180003693  mov     r12d, r13d
0x180003696  lea     ecx, [rax+1]
0x180003699  mov     edi, r13d
0x18000369c  lea     esi, [rax+3]
0x18000369f  mov     [rsp+330h+var_2E0], ecx
0x1800036a3  mov     ebx, ecx
0x1800036a5  mov     [rsp+330h+var_2D8], ecx
0x1800036a9  mov     r15d, ecx
0x1800036ac  mov     [rsp+330h+ThreadInformation], esi
0x1800036b0  movups  xmmword ptr [rbp+230h+Object], xmm0
0x1800036b4  movups  [rbp+230h+var_278], xmm0
0x1800036b8  movups  [rbp+230h+var_268], xmm0
0x1800036bc  movups  xmmword ptr [rsp+330h+ObjectAttributes.Length], xmm0
0x1800036c1  movups  xmmword ptr [rbp+230h+ObjectAttributes+1Ch], xmm0
0x1800036c5  movups  xmmword ptr [rbp+230h+DestinationString.Length], xmm0
0x1800036c9  call    cs:__imp_GetCurrentThread
0x1800036d0  nop     dword ptr [rax+rax+00h]
0x1800036d5  mov     rcx, rax; ThreadHandle
0x1800036d8  lea     r9d, [r15+3]; ThreadInformationLength
0x1800036dc  lea     r8, [rsp+330h+ThreadInformation]; ThreadInformation
0x1800036e1  lea     edx, [rsi-1]; ThreadInformationClass
0x1800036e4  call    cs:__imp_NtSetInformationThread
0x1800036eb  nop     dword ptr [rax+rax+00h]
0x1800036f0  mov     rax, cs:ghNlsEvent
0x1800036f7  mov     [rbp+230h+Object], rax
0x1800036fb  mov     rax, cs:ghMediaRequestEvent
0x180003702  mov     [rbp+230h+Object+8], rax
0x180003706  mov     rax, cs:ghFontChangeEventHKLM
0x18000370d  test    rax, rax
0x180003710  jz      short loc_18000371C
0x180003712  lea     r13d, [r15+1]
0x180003716  mov     qword ptr [rbp+230h+var_278], rax
0x18000371a  jmp     short loc_180003721
0x18000371c  mov     esi, 2
0x180003721  cmp     cs:ghFontLinkChangeEvent, 0
0x180003729  jz      short loc_18000375F
0x18000372b  mov     eax, cs:gSessionId
0x180003731  test    eax, eax
0x180003733  jz      short loc_180003765
0x180003735  call    IsQueryWin32SubsystemHostPresent
0x18000373a  test    al, al
0x18000373c  jz      short loc_18000375F
0x18000373e  call    cs:__imp_QueryWin32SubsystemHost
0x180003745  nop     dword ptr [rax+rax+00h]
0x18000374a  cmp     eax, ebx
0x18000374c  jnz     short loc_18000375F
0x18000374e  mov     rax, cs:ghFontLinkChangeEvent
0x180003755  mov     r12d, esi
0x180003758  inc     esi
0x18000375a  mov     [rbp+r12*8+230h+Object], rax
0x18000375f  mov     eax, cs:gSessionId
0x180003765  cmp     eax, cs:gServiceSessionId
0x18000376b  jz      loc_180003840
0x180003771  lea     rcx, aScnetdrvmsg; "ScNetDrvMsg"
0x180003778  mov     edx, 100h; cchDest
0x18000377d  mov     qword ptr [rsp+330h+CompletionFilter], rcx
0x180003782  lea     r9, aSessions; "\\Sessions"
0x180003789  lea     rcx, [rbp+230h+pszDest]; pszDest
0x18000378d  mov     dword ptr [rsp+330h+InitialState], eax
0x180003791  lea     r8, aWsLdBasenamedo; "%ws\\%ld\\BaseNamedObjects\\%ws"
0x180003798  call    StringCchPrintfW
0x18000379d  lea     rdx, [rbp+230h+pszDest]; SourceString
0x1800037a1  lea     rcx, [rbp+230h+DestinationString]; DestinationString
0x1800037a5  call    cs:__imp_RtlInitUnicodeString
0x1800037ac  nop     dword ptr [rax+rax+00h]
0x1800037b1  lea     rcx, [rsp+330h+hMem]
0x1800037b6  call    CreateBSMEventSD
0x1800037bb  xor     edx, edx
0x1800037bd  test    eax, eax
0x1800037bf  jz      short loc_180003840
0x1800037c1  mov     rdi, [rsp+330h+hMem]
0x1800037c6  lea     rax, [rbp+230h+DestinationString]
0x1800037ca  mov     [rsp+330h+ObjectAttributes.ObjectName], rax
0x1800037cf  lea     rcx, [rbp+230h+Object]
0x1800037d3  mov     eax, esi
0x1800037d5  lea     r8, [rsp+330h+ObjectAttributes]; ObjectAttributes
0x1800037da  mov     [rsp+330h+ObjectAttributes.RootDirectory], rdx
0x1800037df  mov     r9d, ebx; EventType
0x1800037e2  mov     [rbp+230h+ObjectAttributes.SecurityQualityOfService], rdx
0x1800037e6  mov     [rsp+330h+InitialState], dl; InitialState
0x1800037ea  mov     edx, 1F0003h; DesiredAccess
0x1800037ef  lea     rcx, [rcx+rax*8]; EventHandle
0x1800037f3  mov     [rsp+330h+ObjectAttributes.Length], 30h ; '0'
0x1800037fb  mov     [rbp+230h+ObjectAttributes.Attributes], 0C0h
0x180003802  mov     [rbp+230h+ObjectAttributes.SecurityDescriptor], rdi
0x180003806  call    cs:__imp_NtCreateEvent
0x18000380d  nop     dword ptr [rax+rax+00h]
0x180003812  mov     ebx, eax
0x180003814  mov     rcx, rdi; hMem
0x180003817  mov     eax, r14d
0x18000381a  test    ebx, ebx
0x18000381c  cmovns  eax, esi
0x18000381f  mov     [rsp+330h+var_2DC], eax
0x180003823  call    cs:__imp_LocalFree
0x18000382a  nop     dword ptr [rax+rax+00h]
0x18000382f  mov     edi, [rsp+330h+var_2DC]
0x180003833  lea     ecx, [rsi+1]
0x180003836  test    ebx, ebx
0x180003838  mov     ebx, r15d
0x18000383b  cmovs   ecx, esi
0x18000383e  mov     esi, ecx
0x180003840  call    StartRegReadRead
0x180003845  mov     rdx, cs:ghFontChangeEventHKLM; Event
0x18000384c  lea     rax, IoStatusRegChange
0x180003853  test    rdx, rdx
0x180003856  jz      short loc_1800038A4
0x180003858  test    ebx, ebx
0x18000385a  jz      short loc_1800038A4
0x18000385c  mov     rcx, cs:ghFontRegistryHKLM; KeyHandle
0x180003863  xor     ebx, ebx
0x180003865  mov     [rsp+330h+WatchSubtree], 1; WatchSubtree
0x18000386a  xor     r9d, r9d; ApcContext
0x18000386d  mov     [rsp+330h+Length], ebx; Length
0x180003871  xor     r8d, r8d; ApcRoutine
0x180003874  mov     [rsp+330h+ChangeBuffer], rbx; ChangeBuffer
0x180003879  mov     [rsp+330h+Asynchroneous], 1; Asynchroneous
0x18000387e  mov     [rsp+330h+CompletionFilter], 0Fh; CompletionFilter
0x180003886  mov     qword ptr [rsp+330h+InitialState], rax; IoStatusBlock
0x18000388b  call    cs:__imp_NtNotifyChangeKey
0x180003892  nop     dword ptr [rax+rax+00h]
0x180003897  lea     rax, IoStatusRegChange
0x18000389e  mov     [rsp+330h+var_2E0], ebx
0x1800038a2  jmp     short loc_1800038A6
0x1800038a4  xor     ebx, ebx
0x1800038a6  mov     rdx, cs:ghFontChangeEventHKCU; Event
0x1800038ad  test    rdx, rdx
0x1800038b0  jz      short loc_1800038F5
0x1800038b2  cmp     [rsp+330h+var_2D8], ebx
0x1800038b6  jz      short loc_1800038F5
0x1800038b8  mov     rcx, cs:ghFontRegistryHKCU; KeyHandle
0x1800038bf  xor     r9d, r9d; ApcContext
0x1800038c2  mov     [rsp+330h+WatchSubtree], 1; WatchSubtree
0x1800038c7  xor     r8d, r8d; ApcRoutine
0x1800038ca  mov     [rsp+330h+Length], ebx; Length
0x1800038ce  mov     [rsp+330h+ChangeBuffer], rbx; ChangeBuffer
0x1800038d3  mov     [rsp+330h+Asynchroneous], 1; Asynchroneous
0x1800038d8  mov     [rsp+330h+CompletionFilter], 0Fh; CompletionFilter
0x1800038e0  mov     qword ptr [rsp+330h+InitialState], rax; IoStatusBlock
0x1800038e5  call    cs:__imp_NtNotifyChangeKey
0x1800038ec  nop     dword ptr [rax+rax+00h]
0x1800038f1  mov     [rsp+330h+var_2D8], ebx
0x1800038f5  test    r15d, r15d
0x1800038f8  jz      short loc_180003947
0x1800038fa  mov     rdx, cs:ghFontLinkChangeEvent; Event
0x180003901  lea     rax, IoStatusRegChange
0x180003908  mov     rcx, cs:ghFontLinkKey; KeyHandle
0x18000390f  xor     r9d, r9d; ApcContext
0x180003912  mov     [rsp+330h+WatchSubtree], 1; WatchSubtree
0x180003917  xor     r8d, r8d; ApcRoutine
0x18000391a  mov     [rsp+330h+Length], ebx; Length
0x18000391e  mov     [rsp+330h+ChangeBuffer], rbx; ChangeBuffer
0x180003923  mov     [rsp+330h+Asynchroneous], 1; Asynchroneous
0x180003928  mov     [rsp+330h+CompletionFilter], 4; CompletionFilter
0x180003930  mov     qword ptr [rsp+330h+InitialState], rax; IoStatusBlock
0x180003935  call    cs:__imp_NtNotifyChangeKey
0x18000393c  nop     dword ptr [rax+rax+00h]
0x180003941  test    eax, eax
0x180003943  cmovns  r15d, ebx
0x180003947  mov     r9b, 1; Alertable
0x18000394a  mov     qword ptr [rsp+330h+InitialState], rbx; Time
0x18000394f  mov     r8d, 1; WaitType
0x180003955  lea     rdx, [rbp+230h+Object]; Object
0x180003959  mov     ecx, esi; Count
0x18000395b  call    cs:__imp_NtWaitForMultipleObjects
0x180003962  nop     dword ptr [rax+rax+00h]
0x180003967  mov     ecx, eax
0x180003969  mov     ebx, eax
0x18000396b  call    EtwLogNotificationStart
0x180003970  test    ebx, ebx
0x180003972  jnz     short loc_1800039BF
0x180003974  cmp     cs:gfLogon, ebx
0x18000397a  jz      loc_180003A5C
0x180003980  xor     edx, edx
0x180003982  mov     cs:gfLogon, ebx
0x180003988  xor     ecx, ecx
0x18000398a  call    cs:__imp_BaseSrvNlsUpdateRegistryCache
0x180003991  nop     dword ptr [rax+rax+00h]
0x180003996  mov     rcx, cs:ghFontChangeEventHKCU
0x18000399d  test    rcx, rcx
0x1800039a0  jz      loc_180003A5C
0x1800039a6  cmp     r14d, 0FFFFFFFFh
0x1800039aa  jnz     loc_180003A5C
0x1800039b0  mov     r14d, esi
0x1800039b3  inc     esi
0x1800039b5  mov     [rbp+r14*8+230h+Object], rcx
0x1800039ba  jmp     loc_180003A5C
0x1800039bf  cmp     ebx, 1
0x1800039c2  jnz     short loc_1800039DD
0x1800039c4  call    HandleMediaChangeEvent
0x1800039c9  mov     rcx, [rbp+230h+Object+8]; EventHandle
0x1800039cd  xor     edx, edx; NumberOfWaitingThreads
0x1800039cf  call    cs:__imp_NtResetEvent
0x1800039d6  nop     dword ptr [rax+rax+00h]
0x1800039db  jmp     short loc_180003A5C
0x1800039dd  or      eax, 0FFFFFFFFh
0x1800039e0  cmp     edi, eax
0x1800039e2  jz      short loc_1800039EF
0x1800039e4  cmp     ebx, edi
0x1800039e6  jnz     short loc_1800039EF
0x1800039e8  call    HandleRemoteNetDeviceChangeEvent
0x1800039ed  jmp     short loc_180003A5C
0x1800039ef  cmp     r13d, eax
0x1800039f2  jz      short loc_180003A0F
0x1800039f4  cmp     ebx, r13d
0x1800039f7  jnz     short loc_180003A0F
0x1800039f9  mov     rcx, cs:ghFontRegistryHKLM; KeyHandle
0x180003a00  call    HandleFontChangeEvent
0x180003a05  mov     [rsp+330h+var_2E0], 1
0x180003a0d  jmp     short loc_180003A5C
0x180003a0f  cmp     r14d, eax
0x180003a12  jz      short loc_180003A2F
0x180003a14  cmp     ebx, r14d
0x180003a17  jnz     short loc_180003A2F
0x180003a19  mov     rcx, cs:ghFontRegistryHKCU; KeyHandle
0x180003a20  call    HandleFontChangeEvent
0x180003a25  mov     [rsp+330h+var_2D8], 1
0x180003a2d  jmp     short loc_180003A5C
0x180003a2f  cmp     r12d, eax
0x180003a32  jz      short loc_180003A5C
0x180003a34  cmp     ebx, r12d
0x180003a37  jnz     short loc_180003A5C
0x180003a39  xor     ecx, ecx
0x180003a3b  call    cs:__imp_EnableEUDC
0x180003a42  nop     dword ptr [rax+rax+00h]
0x180003a47  mov     r15d, 1
0x180003a4d  mov     ecx, r15d
0x180003a50  call    cs:__imp_EnableEUDC
0x180003a57  nop     dword ptr [rax+rax+00h]
0x180003a5c  mov     ecx, ebx
0x180003a5e  call    EtwLogNotificationStop
0x180003a63  mov     ebx, [rsp+330h+var_2E0]
0x180003a67  jmp     loc_180003845
```
