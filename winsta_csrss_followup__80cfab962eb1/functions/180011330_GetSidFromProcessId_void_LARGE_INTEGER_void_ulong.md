# GetSidFromProcessId(void *,_LARGE_INTEGER,void *,ulong *)

- ea: `0x180011330`
- end: `0x180011549`
- name: `?GetSidFromProcessId@@YAJPEAXT_LARGE_INTEGER@@0PEAK@Z`
- size: `537`
- prototype: `int(void *, union _LARGE_INTEGER, void *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800112a0`

## callees

- `0x180005b40`
- `0x180011330`
- `0x180032c20`

## import_xrefs

- `ntdll!RtlCopySid` at `0x1800114e0`
- `ntdll!RtlCopySid` at `0x1800114e0`
- `ntdll!RtlLengthSid` at `0x1800114c0`
- `ntdll!RtlLengthSid` at `0x1800114c0`
- `ntdll!NtQueryInformationToken` at `0x180011499`
- `ntdll!NtQueryInformationToken` at `0x180011499`
- `ntdll!NtOpenProcess` at `0x1800113d4`
- `ntdll!NtOpenProcess` at `0x1800113d4`
- `ntdll!NtQueryInformationProcess` at `0x180011402`
- `ntdll!NtQueryInformationProcess` at `0x180011402`
- `ntdll!NtOpenProcessToken` at `0x18001143a`
- `ntdll!NtOpenProcessToken` at `0x18001143a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011451`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800114ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011522`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011451`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800114ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011522`

## string_xrefs

- `0x18001152e`: `GetSidFromProcessId: mimatching create time`

## pseudocode

```c
__int64 __fastcall GetSidFromProcessId(void *a1, union _LARGE_INTEGER a2, void *a3, unsigned int *a4)
{
  LONG HighPart; // r15d
  DWORD LowPart; // ebx
  NTSTATUS v8; // edi
  NTSTATUS InformationProcess; // eax
  unsigned int v11; // eax
  unsigned int v12; // ebx
  void *ProcessHandle; // [rsp+30h] [rbp-D0h] BYREF
  ULONG ReturnLength; // [rsp+38h] [rbp-C8h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-C0h] BYREF
  struct _CLIENT_ID ClientId; // [rsp+48h] [rbp-B8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-A8h] BYREF
  _OWORD ProcessInformation[2]; // [rsp+88h] [rbp-78h] BYREF
  PSID TokenInformation[12]; // [rsp+B0h] [rbp-50h] BYREF

  ClientId.UniqueProcess = a1;
  ReturnLength = 0;
  HighPart = a2.HighPart;
  ProcessHandle = 0;
  LowPart = a2.LowPart;
  TokenHandle = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 40);
  memset(ProcessInformation, 0, sizeof(ProcessInformation));
  ClientId.UniqueThread = 0;
  v8 = NtOpenProcess(&ProcessHandle, 0x1000u, &ObjectAttributes, &ClientId);
  if ( v8 >= 0 )
  {
    InformationProcess = NtQueryInformationProcess(ProcessHandle, ProcessTimes, ProcessInformation, 0x20u, 0);
    v8 = InformationProcess;
    if ( InformationProcess < 0 )
    {
      _DbgPrintMessage(8, "NtQueryInformationProcess failed: 0x%x", InformationProcess);
      goto LABEL_5;
    }
    if ( *(_QWORD *)&ProcessInformation[0] != __PAIR64__(HighPart, LowPart) )
    {
      CloseHandle(ProcessHandle);
      v8 = -1073741816;
      _DbgPrintMessage(8, "GetSidFromProcessId: mimatching create time");
      return (unsigned int)v8;
    }
    v8 = NtOpenProcessToken(ProcessHandle, 8u, &TokenHandle);
    if ( v8 < 0 )
      goto LABEL_5;
    v8 = NtQueryInformationToken(TokenHandle, TokenUser, TokenInformation, 0x54u, &ReturnLength);
    CloseHandle(TokenHandle);
    if ( v8 < 0 )
      goto LABEL_5;
    v11 = RtlLengthSid(TokenInformation[0]);
    v12 = v11;
    if ( v11 <= *a4 && a3 )
    {
      v8 = RtlCopySid(v11, a3, TokenInformation[0]);
      if ( v8 < 0 )
      {
LABEL_5:
        CloseHandle(ProcessHandle);
        return (unsigned int)v8;
      }
    }
    else
    {
      v8 = -1073741789;
    }
    *a4 = v12;
    goto LABEL_5;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180011330  push    rbp
0x180011332  push    rbx
0x180011333  push    rsi
0x180011334  push    rdi
0x180011335  push    r14
0x180011337  push    r15
0x180011339  lea     rbp, [rsp-28h]
0x18001133e  sub     rsp, 128h
0x180011345  mov     rax, cs:__security_cookie
0x18001134c  xor     rax, rsp
0x18001134f  mov     [rbp+50h+var_40], rax
0x180011353  xorps   xmm0, xmm0
0x180011356  mov     [rsp+150h+ClientId.UniqueProcess], rcx
0x18001135b  mov     r15, rdx
0x18001135e  mov     [rsp+150h+var_118], 0
0x180011366  mov     rsi, r9
0x180011369  shr     r15, 20h
0x18001136d  mov     r14, r8
0x180011370  mov     [rsp+150h+ProcessHandle], 0
0x180011379  mov     rbx, rdx
0x18001137c  mov     [rsp+150h+TokenHandle], 0
0x180011385  lea     r9, [rsp+150h+ClientId]; ClientId
0x18001138a  mov     qword ptr [rsp+150h+ObjectAttributes.Length], 30h ; '0'
0x180011393  lea     r8, [rsp+150h+ObjectAttributes]; ObjectAttributes
0x180011398  mov     qword ptr [rsp+150h+ObjectAttributes.Attributes], 0
0x1800113a1  mov     edx, 1000h; DesiredAccess
0x1800113a6  mov     [rsp+150h+ObjectAttributes.RootDirectory], 0
0x1800113af  lea     rcx, [rsp+150h+ProcessHandle]; ProcessHandle
0x1800113b4  mov     [rsp+150h+ObjectAttributes.ObjectName], 0
0x1800113bd  movups  [rbp+50h+ProcessInformation], xmm0
0x1800113c1  mov     [rsp+150h+ClientId.UniqueThread], 0
0x1800113ca  movups  [rbp+50h+var_B8], xmm0
0x1800113ce  movdqu  xmmword ptr [rsp+150h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800113d4  call    cs:__imp_NtOpenProcess
0x1800113db  nop     dword ptr [rax+rax+00h]
0x1800113e0  mov     edi, eax
0x1800113e2  test    eax, eax
0x1800113e4  js      short loc_18001145D
0x1800113e6  mov     rcx, [rsp+150h+ProcessHandle]; ProcessHandle
0x1800113eb  lea     r8, [rbp+50h+ProcessInformation]; ProcessInformation
0x1800113ef  mov     r9d, 20h ; ' '; ProcessInformationLength
0x1800113f5  mov     [rsp+150h+ReturnLength], 0; ReturnLength
0x1800113fe  lea     edx, [r9-1Ch]; ProcessInformationClass
0x180011402  call    cs:__imp_NtQueryInformationProcess
0x180011409  nop     dword ptr [rax+rax+00h]
0x18001140e  mov     edi, eax
0x180011410  test    eax, eax
0x180011412  js      loc_1800114FD
0x180011418  cmp     dword ptr [rbp+50h+ProcessInformation], ebx
0x18001141b  jnz     loc_18001151D
0x180011421  cmp     dword ptr [rbp+50h+ProcessInformation+4], r15d
0x180011425  jnz     loc_18001151D
0x18001142b  mov     rcx, [rsp+150h+ProcessHandle]; ProcessHandle
0x180011430  lea     r8, [rsp+150h+TokenHandle]; TokenHandle
0x180011435  mov     edx, 8; DesiredAccess
0x18001143a  call    cs:__imp_NtOpenProcessToken
0x180011441  nop     dword ptr [rax+rax+00h]
0x180011446  mov     edi, eax
0x180011448  test    eax, eax
0x18001144a  jns     short loc_18001147C
0x18001144c  mov     rcx, [rsp+150h+ProcessHandle]; hObject
0x180011451  call    cs:__imp_CloseHandle
0x180011458  nop     dword ptr [rax+rax+00h]
0x18001145d  mov     eax, edi
0x18001145f  mov     rcx, [rbp+50h+var_40]
0x180011463  xor     rcx, rsp; StackCookie
0x180011466  call    __security_check_cookie
0x18001146b  add     rsp, 128h
0x180011472  pop     r15
0x180011474  pop     r14
0x180011476  pop     rdi
0x180011477  pop     rsi
0x180011478  pop     rbx
0x180011479  pop     rbp
0x18001147a  retn
0x18001147c  mov     rcx, [rsp+150h+TokenHandle]; TokenHandle
0x180011481  lea     rax, [rsp+150h+var_118]
0x180011486  mov     r9d, 54h ; 'T'; TokenInformationLength
0x18001148c  mov     [rsp+150h+ReturnLength], rax; ReturnLength
0x180011491  lea     r8, [rbp+50h+TokenInformation]; TokenInformation
0x180011495  lea     edx, [r9-53h]; TokenInformationClass
0x180011499  call    cs:__imp_NtQueryInformationToken
0x1800114a0  nop     dword ptr [rax+rax+00h]
0x1800114a5  mov     rcx, [rsp+150h+TokenHandle]; hObject
0x1800114aa  mov     edi, eax
0x1800114ac  call    cs:__imp_CloseHandle
0x1800114b3  nop     dword ptr [rax+rax+00h]
0x1800114b8  test    edi, edi
0x1800114ba  js      short loc_18001144C
0x1800114bc  mov     rcx, [rbp+50h+TokenInformation]; Sid
0x1800114c0  call    cs:__imp_RtlLengthSid
0x1800114c7  nop     dword ptr [rax+rax+00h]
0x1800114cc  mov     ebx, eax
0x1800114ce  cmp     eax, [rsi]
0x1800114d0  ja      short loc_180011516
0x1800114d2  test    r14, r14
0x1800114d5  jz      short loc_180011516
0x1800114d7  mov     r8, [rbp+50h+TokenInformation]; SourceSid
0x1800114db  mov     rdx, r14; DestinationSid
0x1800114de  mov     ecx, eax; DestinationSidLength
0x1800114e0  call    cs:__imp_RtlCopySid
0x1800114e7  nop     dword ptr [rax+rax+00h]
0x1800114ec  mov     edi, eax
0x1800114ee  test    eax, eax
0x1800114f0  js      loc_18001144C
0x1800114f6  mov     [rsi], ebx
0x1800114f8  jmp     loc_18001144C
0x1800114fd  mov     r8d, eax
0x180011500  lea     rdx, aNtqueryinforma_1; "NtQueryInformationProcess failed: 0x%x"
0x180011507  mov     ecx, 8; int
0x18001150c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180011511  jmp     loc_18001144C
0x180011516  mov     edi, 0C0000023h
0x18001151b  jmp     short loc_1800114F6
0x18001151d  mov     rcx, [rsp+150h+ProcessHandle]; hObject
0x180011522  call    cs:__imp_CloseHandle
0x180011529  nop     dword ptr [rax+rax+00h]
0x18001152e  lea     rdx, aGetsidfromproc; "GetSidFromProcessId: mimatching create "...
0x180011535  mov     ecx, 8; int
0x18001153a  mov     edi, 0C0000008h
0x18001153f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180011544  jmp     loc_18001145D
```
