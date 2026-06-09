# GetProcessInfo(void *,_UNICODE_STRING * *,void * *,ulong *,uchar *)

- ea: `0x14000e488`
- end: `0x14000e772`
- name: `?GetProcessInfo@@YAJPEAXPEAPEAU_UNICODE_STRING@@PEAPEAXPEAKPEAE@Z`
- size: `746`
- prototype: `__int64 __fastcall(void *, struct _UNICODE_STRING **, void **, unsigned int *, HANDLE ProcessHandle)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14000439c`
- `0x14001e808`

## callees

- `0x14000e488`
- `0x14000f684`
- `0x14000fd40`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14000e644`
- `ntoskrnl!ZwClose` at `0x14000e644`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000e514`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000e514`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000e62c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000e62c`
- `ntoskrnl!ObfDereferenceObject` at `0x14000e659`
- `ntoskrnl!ObfDereferenceObject` at `0x14000e659`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e761`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e761`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000e5e0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000e6e1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000e5e0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000e6e1`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x14000e4c3`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x14000e4c3`
- `ntoskrnl!ZwQueryInformationProcess` at `0x14000e560`
- `ntoskrnl!ZwQueryInformationProcess` at `0x14000e6a3`
- `ntoskrnl!ZwQueryInformationProcess` at `0x14000e732`
- `ntoskrnl!ZwQueryInformationProcess` at `0x14000e560`
- `ntoskrnl!ZwQueryInformationProcess` at `0x14000e6a3`
- `ntoskrnl!ZwQueryInformationProcess` at `0x14000e732`
- `ntoskrnl!PsInitialSystemProcess` at `0x14000e598`

## string_xrefs

- `0x14000e4d8`: `WinSetupMon::GetProcessInfo: Failed PsLookupProcessByProcessId(%p) (0x%08X)`
- `0x14000e52a`: `WinSetupMon::GetProcessInfo: Failed ObOpenObjectByPointer(%p) (0x%08X)`

## pseudocode

```c
__int64 __fastcall GetProcessInfo(
        void *a1,
        struct _UNICODE_STRING **a2,
        void **a3,
        unsigned int *a4,
        HANDLE ProcessHandle)
{
  NTSTATUS InformationProcess; // ebx
  const char *v8; // rdx
  struct _UNICODE_STRING *PoolWithTag; // rax
  struct _UNICODE_STRING *v10; // rdi
  struct _UNICODE_STRING *v11; // rsi
  unsigned int v13; // edi
  struct _UNICODE_STRING *v14; // rax
  struct _UNICODE_STRING *v15; // rbx
  NTSTATUS v16; // eax
  PEPROCESS Process; // [rsp+48h] [rbp-11h] BYREF
  UNICODE_STRING SourceString; // [rsp+50h] [rbp-9h] BYREF
  _OWORD ProcessInformation[2]; // [rsp+60h] [rbp+7h] BYREF
  __int128 v20; // [rsp+80h] [rbp+27h]
  unsigned int *ReturnLength; // [rsp+D0h] [rbp+77h] BYREF

  ReturnLength = a4;
  Process = 0;
  ProcessHandle = 0;
  InformationProcess = PsLookupProcessByProcessId(a1, &Process);
  if ( InformationProcess < 0 )
  {
    v8 = "WinSetupMon::GetProcessInfo: Failed PsLookupProcessByProcessId(%p) (0x%08X)";
LABEL_3:
    WriteLog(0, v8);
    goto LABEL_17;
  }
  InformationProcess = ObOpenObjectByPointer(Process, 0x200u, 0, 0, 0, 0, &ProcessHandle);
  if ( InformationProcess < 0 )
  {
    v8 = "WinSetupMon::GetProcessInfo: Failed ObOpenObjectByPointer(%p) (0x%08X)";
    goto LABEL_3;
  }
  if ( a3 )
  {
    memset(ProcessInformation, 0, sizeof(ProcessInformation));
    v20 = 0;
    InformationProcess = ZwQueryInformationProcess(ProcessHandle, ProcessBasicInformation, ProcessInformation, 0x30u, 0);
    if ( InformationProcess < 0 )
    {
      v8 = "WinSetupMon::GetProcessInfo: Failed QueryInformationProcess(ProcessBasicInformation) (0x%08X)";
      goto LABEL_3;
    }
    *a3 = (void *)*((_QWORD *)&v20 + 1);
  }
  if ( !a2 )
    goto LABEL_17;
  LODWORD(ReturnLength) = 0;
  if ( Process == PsInitialSystemProcess )
  {
    *(_QWORD *)&SourceString.Length = 917516;
    SourceString.Buffer = L"System";
    LODWORD(ReturnLength) = 30;
    PoolWithTag = (struct _UNICODE_STRING *)ExAllocatePoolWithTag((POOL_TYPE)1025, 0x1Eu, 0x6E6D7377u);
    v10 = PoolWithTag;
    if ( ExPoolZeroingNativelySupported )
    {
      if ( PoolWithTag )
        goto LABEL_15;
    }
    else if ( PoolWithTag )
    {
      memset(PoolWithTag, 0, 0x1Eu);
LABEL_15:
      v10->MaximumLength = SourceString.MaximumLength;
      v11 = v10;
      v10->Buffer = &v10[1].Length;
      RtlCopyUnicodeString(v10, &SourceString);
LABEL_16:
      *a2 = v11;
      goto LABEL_17;
    }
    goto LABEL_23;
  }
  InformationProcess = ZwQueryInformationProcess(ProcessHandle, ProcessImageFileName, 0, 0, (PULONG)&ReturnLength);
  if ( InformationProcess != -1073741820 )
  {
    v8 = "WinSetupMon::GetProcessInfo: Failed QueryInformationProcess(ProcessImageFileName) (0x%08X)";
    if ( InformationProcess >= 0 )
      InformationProcess = -1073741823;
    goto LABEL_3;
  }
  v13 = (unsigned int)ReturnLength;
  v14 = (struct _UNICODE_STRING *)ExAllocatePoolWithTag((POOL_TYPE)1025, (unsigned int)ReturnLength, 0x6E6D7377u);
  v15 = v14;
  if ( ExPoolZeroingNativelySupported )
  {
    if ( v14 )
      goto LABEL_32;
LABEL_23:
    InformationProcess = -1073741670;
    goto LABEL_17;
  }
  if ( !v14 )
    goto LABEL_23;
  memset(v14, 0, v13);
LABEL_32:
  v11 = v15;
  v16 = ZwQueryInformationProcess(ProcessHandle, ProcessImageFileName, v15, (ULONG)ReturnLength, 0);
  InformationProcess = v16;
  if ( v16 >= 0 )
    goto LABEL_16;
  WriteLog(0, "WinSetupMon::GetProcessInfo: Failed QueryInformationProcess(ProcessImageFileName) (0x%08X)", v16);
  ExFreePoolWithTag(v11, 0x6E6D7377u);
LABEL_17:
  if ( ProcessHandle )
    ZwClose(ProcessHandle);
  if ( Process )
    ObfDereferenceObject(Process);
  return (unsigned int)InformationProcess;
}

```

## disassembly

```asm
0x14000e488  mov     rax, rsp
0x14000e48b  mov     [rax+8], rbx
0x14000e48f  mov     [rax+10h], rsi
0x14000e493  mov     [rax+20h], r9
0x14000e497  push    rbp
0x14000e498  push    rdi
0x14000e499  push    r14
0x14000e49b  lea     rbp, [rax-57h]
0x14000e49f  sub     rsp, 90h
0x14000e4a6  mov     r14, rdx
0x14000e4a9  mov     [rbp+4Fh+Process], 0
0x14000e4b1  lea     rdx, [rbp+4Fh+Process]; Process
0x14000e4b5  mov     [rbp+4Fh+ProcessHandle], 0
0x14000e4bd  mov     rdi, r8
0x14000e4c0  mov     rsi, rcx
0x14000e4c3  call    cs:__imp_PsLookupProcessByProcessId
0x14000e4ca  nop     dword ptr [rax+rax+00h]
0x14000e4cf  mov     ebx, eax
0x14000e4d1  test    eax, eax
0x14000e4d3  jns     short loc_14000E4EE
0x14000e4d5  mov     r8, rsi
0x14000e4d8  lea     rdx, aWinsetupmonGet_5; "WinSetupMon::GetProcessInfo: Failed PsL"...
0x14000e4df  mov     r9d, eax
0x14000e4e2  xor     ecx, ecx
0x14000e4e4  call    ?WriteLog@@YAXW4LogLevel@@PEBDZZ; WriteLog(LogLevel,char const *,...)
0x14000e4e9  jmp     loc_14000E63B
0x14000e4ee  mov     rcx, [rbp+4Fh+Process]; Object
0x14000e4f2  lea     rax, [rbp+4Fh+ProcessHandle]
0x14000e4f6  mov     [rsp+0A0h+Handle], rax; Handle
0x14000e4fb  xor     r9d, r9d; DesiredAccess
0x14000e4fe  mov     [rsp+0A0h+AccessMode], 0; AccessMode
0x14000e503  xor     r8d, r8d; PassedAccessState
0x14000e506  mov     edx, 200h; HandleAttributes
0x14000e50b  mov     [rsp+0A0h+ObjectType], 0; ObjectType
0x14000e514  call    cs:__imp_ObOpenObjectByPointer
0x14000e51b  nop     dword ptr [rax+rax+00h]
0x14000e520  mov     ebx, eax
0x14000e522  test    eax, eax
0x14000e524  jns     short loc_14000E533
0x14000e526  mov     r8, [rbp+4Fh+Process]
0x14000e52a  lea     rdx, aWinsetupmonGet_3; "WinSetupMon::GetProcessInfo: Failed ObO"...
0x14000e531  jmp     short loc_14000E4DF
0x14000e533  test    rdi, rdi
0x14000e536  jz      short loc_14000E58F
0x14000e538  mov     rcx, [rbp+4Fh+ProcessHandle]; ProcessHandle
0x14000e53c  lea     r8, [rbp+4Fh+ProcessInformation]; ProcessInformation
0x14000e540  xorps   xmm0, xmm0
0x14000e543  mov     [rsp+0A0h+ObjectType], 0; ReturnLength
0x14000e54c  mov     r9d, 30h ; '0'; ProcessInformationLength
0x14000e552  xor     edx, edx; ProcessInformationClass
0x14000e554  movups  [rbp+4Fh+ProcessInformation], xmm0
0x14000e558  movups  [rbp+4Fh+var_38], xmm0
0x14000e55c  movups  [rbp+4Fh+var_28], xmm0
0x14000e560  call    cs:__imp_ZwQueryInformationProcess
0x14000e567  nop     dword ptr [rax+rax+00h]
0x14000e56c  mov     ebx, eax
0x14000e56e  test    eax, eax
0x14000e570  jns     short loc_14000E588
0x14000e572  mov     r8d, eax
0x14000e575  lea     rdx, aWinsetupmonGet_13; "WinSetupMon::GetProcessInfo: Failed Que"...
0x14000e57c  xor     ecx, ecx
0x14000e57e  call    ?WriteLog@@YAXW4LogLevel@@PEBDZZ; WriteLog(LogLevel,char const *,...)
0x14000e583  jmp     loc_14000E63B
0x14000e588  mov     rax, qword ptr [rbp+4Fh+var_28+8]
0x14000e58c  mov     [rdi], rax
0x14000e58f  test    r14, r14
0x14000e592  jz      loc_14000E63B
0x14000e598  mov     rax, cs:__imp_PsInitialSystemProcess
0x14000e59f  mov     dword ptr [rbp+4Fh+ReturnLength], 0
0x14000e5a6  mov     rcx, [rax]
0x14000e5a9  cmp     [rbp+4Fh+Process], rcx
0x14000e5ad  jnz     loc_14000E68C
0x14000e5b3  mov     ecx, 0Eh
0x14000e5b8  mov     qword ptr [rbp+4Fh+SourceString.Length], 0E000Ch
0x14000e5c0  lea     rax, aSystem; "System"
0x14000e5c7  mov     r8d, 6E6D7377h; Tag
0x14000e5cd  mov     [rbp+4Fh+SourceString.Buffer], rax
0x14000e5d1  lea     eax, [rcx+10h]
0x14000e5d4  mov     ecx, 401h; PoolType
0x14000e5d9  mov     edx, eax; NumberOfBytes
0x14000e5db  mov     dword ptr [rbp+4Fh+ReturnLength], eax
0x14000e5de  mov     esi, eax
0x14000e5e0  call    cs:__imp_ExAllocatePoolWithTag
0x14000e5e7  nop     dword ptr [rax+rax+00h]
0x14000e5ec  cmp     cs:ExPoolZeroingNativelySupported, 0
0x14000e5f3  mov     rdi, rax
0x14000e5f6  jnz     loc_14000E680
0x14000e5fc  test    rax, rax
0x14000e5ff  jz      loc_14000E685
0x14000e605  mov     r8d, esi; Size
0x14000e608  xor     edx, edx; Val
0x14000e60a  mov     rcx, rax; void *
0x14000e60d  call    memset
0x14000e612  movzx   eax, [rbp+4Fh+SourceString.MaximumLength]
0x14000e616  lea     rdx, [rbp+4Fh+SourceString]; SourceString
0x14000e61a  mov     [rdi+2], ax
0x14000e61e  mov     rcx, rdi; DestinationString
0x14000e621  lea     rax, [rdi+10h]
0x14000e625  mov     rsi, rdi
0x14000e628  mov     [rdi+8], rax
0x14000e62c  call    cs:__imp_RtlCopyUnicodeString
0x14000e633  nop     dword ptr [rax+rax+00h]
0x14000e638  mov     [r14], rsi
0x14000e63b  mov     rcx, [rbp+4Fh+ProcessHandle]; Handle
0x14000e63f  test    rcx, rcx
0x14000e642  jz      short loc_14000E650
0x14000e644  call    cs:__imp_ZwClose
0x14000e64b  nop     dword ptr [rax+rax+00h]
0x14000e650  mov     rcx, [rbp+4Fh+Process]; Object
0x14000e654  test    rcx, rcx
0x14000e657  jz      short loc_14000E665
0x14000e659  call    cs:__imp_ObfDereferenceObject
0x14000e660  nop     dword ptr [rax+rax+00h]
0x14000e665  lea     r11, [rsp+0A0h+var_10]
0x14000e66d  mov     eax, ebx
0x14000e66f  mov     rbx, [r11+20h]
0x14000e673  mov     rsi, [r11+28h]
0x14000e677  mov     rsp, r11
0x14000e67a  pop     r14
0x14000e67c  pop     rdi
0x14000e67d  pop     rbp
0x14000e67e  retn
0x14000e680  test    rdi, rdi
0x14000e683  jnz     short loc_14000E612
0x14000e685  mov     ebx, 0C000009Ah
0x14000e68a  jmp     short loc_14000E63B
0x14000e68c  mov     rcx, [rbp+4Fh+ProcessHandle]; ProcessHandle
0x14000e690  lea     rax, [rbp+4Fh+ReturnLength]
0x14000e694  xor     r9d, r9d; ProcessInformationLength
0x14000e697  mov     [rsp+0A0h+ObjectType], rax; ReturnLength
0x14000e69c  xor     r8d, r8d; ProcessInformation
0x14000e69f  lea     edx, [r9+1Bh]; ProcessInformationClass
0x14000e6a3  call    cs:__imp_ZwQueryInformationProcess
0x14000e6aa  nop     dword ptr [rax+rax+00h]
0x14000e6af  mov     ebx, eax
0x14000e6b1  cmp     eax, 0C0000004h
0x14000e6b6  jz      short loc_14000E6D1
0x14000e6b8  test    ebx, ebx
0x14000e6ba  lea     rdx, aWinsetupmonGet; "WinSetupMon::GetProcessInfo: Failed Que"...
0x14000e6c1  mov     eax, 0C0000001h
0x14000e6c6  cmovns  ebx, eax
0x14000e6c9  mov     r8d, ebx
0x14000e6cc  jmp     loc_14000E57C
0x14000e6d1  mov     edi, dword ptr [rbp+4Fh+ReturnLength]
0x14000e6d4  mov     r8d, 6E6D7377h; Tag
0x14000e6da  mov     edx, edi; NumberOfBytes
0x14000e6dc  mov     ecx, 401h; PoolType
0x14000e6e1  call    cs:__imp_ExAllocatePoolWithTag
0x14000e6e8  nop     dword ptr [rax+rax+00h]
0x14000e6ed  cmp     cs:ExPoolZeroingNativelySupported, 0
0x14000e6f4  mov     rbx, rax
0x14000e6f7  jnz     short loc_14000E70D
0x14000e6f9  test    rax, rax
0x14000e6fc  jz      short loc_14000E685
0x14000e6fe  mov     r8d, edi; Size
0x14000e701  xor     edx, edx; Val
0x14000e703  mov     rcx, rax; void *
0x14000e706  call    memset
0x14000e70b  jmp     short loc_14000E716
0x14000e70d  test    rbx, rbx
0x14000e710  jz      loc_14000E685
0x14000e716  mov     r9d, dword ptr [rbp+4Fh+ReturnLength]; ProcessInformationLength
0x14000e71a  mov     r8, rbx; ProcessInformation
0x14000e71d  mov     rcx, [rbp+4Fh+ProcessHandle]; ProcessHandle
0x14000e721  mov     edx, 1Bh; ProcessInformationClass
0x14000e726  mov     rsi, rbx
0x14000e729  mov     [rsp+0A0h+ObjectType], 0; ReturnLength
0x14000e732  call    cs:__imp_ZwQueryInformationProcess
0x14000e739  nop     dword ptr [rax+rax+00h]
0x14000e73e  mov     ebx, eax
0x14000e740  test    eax, eax
0x14000e742  jns     loc_14000E638
0x14000e748  mov     r8d, eax
0x14000e74b  lea     rdx, aWinsetupmonGet; "WinSetupMon::GetProcessInfo: Failed Que"...
0x14000e752  xor     ecx, ecx
0x14000e754  call    ?WriteLog@@YAXW4LogLevel@@PEBDZZ; WriteLog(LogLevel,char const *,...)
0x14000e759  mov     edx, 6E6D7377h; Tag
0x14000e75e  mov     rcx, rsi; P
0x14000e761  call    cs:__imp_ExFreePoolWithTag
0x14000e768  nop     dword ptr [rax+rax+00h]
0x14000e76d  jmp     loc_14000E63B
```
