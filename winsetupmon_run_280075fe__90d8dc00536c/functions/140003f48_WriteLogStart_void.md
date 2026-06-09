# WriteLogStart(void)

- ea: `0x140003f48`
- end: `0x1400040ad`
- name: `?WriteLogStart@@YAXXZ`
- size: `357`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1400034f4`
- `0x14000362c`

## callees

- `0x140003944`
- `0x140003f48`
- `0x14000f900`
- `0x14000fd40`

## import_xrefs

- `ntoskrnl!RtlGetVersion` at `0x140004004`
- `ntoskrnl!RtlGetVersion` at `0x140004004`
- `ntoskrnl!ExReleaseFastMutex` at `0x140003fd9`
- `ntoskrnl!ExReleaseFastMutex` at `0x140003fd9`
- `ntoskrnl!ExAcquireFastMutex` at `0x140003f88`
- `ntoskrnl!ExAcquireFastMutex` at `0x140003f88`

## string_xrefs

- `0x140004056`: `OS Service pack major version: %hu`
- `0x14000406c`: `OS Service pack minor version: %hu`

## pseudocode

```c
void WriteLogStart(void)
{
  NTSTATUS Version; // eax
  _DWORD VersionInformation[72]; // [rsp+20h] [rbp-138h] BYREF

  WriteLogMessage(1, L"Logging started successfully to : %wZ", &String2);
  ExAcquireFastMutex(&FastMutex);
  if ( DestinationString.Length )
    WriteLogMessage(1, L"**** SESSION START: %wZ ****", &DestinationString);
  if ( stru_1400195F8.Length )
    WriteLogMessage(1, L"Session ID: %wZ", &stru_1400195F8);
  ExReleaseFastMutex(&FastMutex);
  memset(&VersionInformation[1], 0, 0x118u);
  VersionInformation[0] = 284;
  Version = RtlGetVersion((PRTL_OSVERSIONINFOW)VersionInformation);
  if ( Version < 0 )
  {
    WriteLogMessage(2, L"Failed to get OS version information (0x%08X)", (unsigned int)Version);
  }
  else
  {
    WriteLogMessage(1, L"OS Major version: %u", VersionInformation[1]);
    WriteLogMessage(1, L"OS Minor version: %u", VersionInformation[2]);
    WriteLogMessage(1, L"OS Build version: %u", VersionInformation[3]);
    WriteLogMessage(1, L"OS Service pack major version: %hu", LOWORD(VersionInformation[69]));
    WriteLogMessage(1, L"OS Service pack minor version: %hu", HIWORD(VersionInformation[69]));
  }
}

```

## disassembly

```asm
0x140003f48  mov     [rsp+arg_0], rbx
0x140003f4d  push    rdi
0x140003f4e  sub     rsp, 150h
0x140003f55  mov     rax, cs:__security_cookie
0x140003f5c  xor     rax, rsp
0x140003f5f  mov     [rsp+158h+var_18], rax
0x140003f67  mov     ebx, 1
0x140003f6c  lea     r8, String2
0x140003f73  mov     ecx, ebx
0x140003f75  lea     rdx, aLoggingStarted; "Logging started successfully to : %wZ"
0x140003f7c  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x140003f81  lea     rcx, FastMutex; FastMutex
0x140003f88  call    cs:__imp_ExAcquireFastMutex
0x140003f8f  nop     dword ptr [rax+rax+00h]
0x140003f94  xor     edi, edi
0x140003f96  cmp     cs:DestinationString.Length, di
0x140003f9d  jbe     short loc_140003FB4
0x140003f9f  lea     r8, DestinationString
0x140003fa6  mov     ecx, ebx
0x140003fa8  lea     rdx, aSessionStartWz; "**** SESSION START: %wZ ****"
0x140003faf  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x140003fb4  cmp     cs:stru_1400195F8.Length, di
0x140003fbb  jbe     short loc_140003FD2
0x140003fbd  lea     r8, stru_1400195F8
0x140003fc4  mov     ecx, ebx
0x140003fc6  lea     rdx, aSessionIdWz; "Session ID: %wZ"
0x140003fcd  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x140003fd2  lea     rcx, FastMutex; FastMutex
0x140003fd9  call    cs:__imp_ExReleaseFastMutex
0x140003fe0  nop     dword ptr [rax+rax+00h]
0x140003fe5  xor     edx, edx; Val
0x140003fe7  lea     rcx, [rsp+158h+VersionInformation.dwMajorVersion]; void *
0x140003fec  mov     r8d, 118h; Size
0x140003ff2  call    memset
0x140003ff7  lea     rcx, [rsp+158h+VersionInformation]; lpVersionInformation
0x140003ffc  mov     [rsp+158h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x140004004  call    cs:__imp_RtlGetVersion
0x14000400b  nop     dword ptr [rax+rax+00h]
0x140004010  test    eax, eax
0x140004012  js      short loc_140004075
0x140004014  mov     r8d, [rsp+158h+VersionInformation.dwMajorVersion]
0x140004019  lea     rdx, aOsMajorVersion; "OS Major version: %u"
0x140004020  mov     ecx, ebx
0x140004022  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x140004027  mov     r8d, [rsp+158h+VersionInformation.dwMinorVersion]
0x14000402c  lea     rdx, aOsMinorVersion; "OS Minor version: %u"
0x140004033  mov     ecx, ebx
0x140004035  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x14000403a  mov     r8d, [rsp+158h+VersionInformation.dwBuildNumber]
0x14000403f  lea     rdx, aOsBuildVersion; "OS Build version: %u"
0x140004046  mov     ecx, ebx
0x140004048  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x14000404d  movzx   r8d, [rsp+158h+var_24]
0x140004056  lea     rdx, aOsServicePackM_0; "OS Service pack major version: %hu"
0x14000405d  mov     ecx, ebx
0x14000405f  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x140004064  movzx   eax, [rsp+158h+var_22]
0x14000406c  lea     rdx, aOsServicePackM; "OS Service pack minor version: %hu"
0x140004073  jmp     short loc_140004081
0x140004075  mov     ebx, 2
0x14000407a  lea     rdx, aFailedToGetOsV; "Failed to get OS version information (0"...
0x140004081  mov     r8d, eax
0x140004084  mov     ecx, ebx
0x140004086  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x14000408b  mov     rcx, [rsp+158h+var_18]
0x140004093  xor     rcx, rsp; StackCookie
0x140004096  call    __security_check_cookie
0x14000409b  mov     rbx, [rsp+158h+arg_0]
0x1400040a3  add     rsp, 150h
0x1400040aa  pop     rdi
0x1400040ab  retn
```
