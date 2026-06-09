# GetSidFromProcessId(void *,_LARGE_INTEGER,void *,ulong *)

- ea: `0x180010424`
- end: `0x180010606`
- name: `?GetSidFromProcessId@@YAJPEAXT_LARGE_INTEGER@@0PEAK@Z`
- size: `482`
- prototype: `int(void *, union _LARGE_INTEGER, void *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800103a0`

## callees

- `0x180007890`
- `0x180010424`
- `0x18002fe40`

## import_xrefs

- `ntdll!RtlCopySid` at `0x1800105a9`
- `ntdll!RtlCopySid` at `0x1800105a9`
- `ntdll!RtlLengthSid` at `0x18001058f`
- `ntdll!RtlLengthSid` at `0x18001058f`
- `ntdll!NtQueryInformationToken` at `0x180010574`
- `ntdll!NtQueryInformationToken` at `0x180010574`
- `ntdll!NtOpenProcess` at `0x1800104c8`
- `ntdll!NtOpenProcess` at `0x1800104c8`
- `ntdll!NtQueryInformationProcess` at `0x1800104f0`
- `ntdll!NtQueryInformationProcess` at `0x1800104f0`
- `ntdll!NtOpenProcessToken` at `0x180010522`
- `ntdll!NtOpenProcessToken` at `0x180010522`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010533`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010581`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800105e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010533`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010581`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800105e5`

## string_xrefs

- `0x1800105eb`: `GetSidFromProcessId: mimatching create time`

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
0x180010424  push    rbp
0x180010426  push    rbx
0x180010427  push    rsi
0x180010428  push    rdi
0x180010429  push    r14
0x18001042b  push    r15
0x18001042d  lea     rbp, [rsp-28h]
0x180010432  sub     rsp, 128h
0x180010439  mov     rax, cs:__security_cookie
0x180010440  xor     rax, rsp
0x180010443  mov     [rbp+50h+var_40], rax
0x180010447  xorps   xmm0, xmm0
0x18001044a  mov     [rsp+150h+ClientId.UniqueProcess], rcx
0x18001044f  mov     r15, rdx
0x180010452  mov     [rsp+150h+var_118], 0
0x18001045a  mov     rsi, r9
0x18001045d  shr     r15, 20h
0x180010461  mov     r14, r8
0x180010464  mov     [rsp+150h+ProcessHandle], 0
0x18001046d  mov     rbx, rdx
0x180010470  mov     [rsp+150h+TokenHandle], 0
0x180010479  lea     r9, [rsp+150h+ClientId]; ClientId
0x18001047e  mov     qword ptr [rsp+150h+ObjectAttributes.Length], 30h ; '0'
0x180010487  lea     r8, [rsp+150h+ObjectAttributes]; ObjectAttributes
0x18001048c  mov     qword ptr [rsp+150h+ObjectAttributes.Attributes], 0
0x180010495  mov     edx, 1000h; DesiredAccess
0x18001049a  mov     [rsp+150h+ObjectAttributes.RootDirectory], 0
0x1800104a3  lea     rcx, [rsp+150h+ProcessHandle]; ProcessHandle
0x1800104a8  mov     [rsp+150h+ObjectAttributes.ObjectName], 0
0x1800104b1  movups  [rbp+50h+ProcessInformation], xmm0
0x1800104b5  mov     [rsp+150h+ClientId.UniqueThread], 0
0x1800104be  movups  [rbp+50h+var_B8], xmm0
0x1800104c2  movdqu  xmmword ptr [rsp+150h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800104c8  call    cs:__imp_NtOpenProcess
0x1800104ce  mov     edi, eax
0x1800104d0  test    eax, eax
0x1800104d2  js      short loc_180010539
0x1800104d4  mov     rcx, [rsp+150h+ProcessHandle]; ProcessHandle
0x1800104d9  lea     r8, [rbp+50h+ProcessInformation]; ProcessInformation
0x1800104dd  mov     r9d, 20h ; ' '; ProcessInformationLength
0x1800104e3  mov     [rsp+150h+ReturnLength], 0; ReturnLength
0x1800104ec  lea     edx, [r9-1Ch]; ProcessInformationClass
0x1800104f0  call    cs:__imp_NtQueryInformationProcess
0x1800104f6  mov     edi, eax
0x1800104f8  test    eax, eax
0x1800104fa  js      loc_1800105C0
0x180010500  cmp     dword ptr [rbp+50h+ProcessInformation], ebx
0x180010503  jnz     loc_1800105E0
0x180010509  cmp     dword ptr [rbp+50h+ProcessInformation+4], r15d
0x18001050d  jnz     loc_1800105E0
0x180010513  mov     rcx, [rsp+150h+ProcessHandle]; ProcessHandle
0x180010518  lea     r8, [rsp+150h+TokenHandle]; TokenHandle
0x18001051d  mov     edx, 8; DesiredAccess
0x180010522  call    cs:__imp_NtOpenProcessToken
0x180010528  mov     edi, eax
0x18001052a  test    eax, eax
0x18001052c  jns     short loc_180010557
0x18001052e  mov     rcx, [rsp+150h+ProcessHandle]; hObject
0x180010533  call    cs:__imp_CloseHandle
0x180010539  mov     eax, edi
0x18001053b  mov     rcx, [rbp+50h+var_40]
0x18001053f  xor     rcx, rsp; StackCookie
0x180010542  call    __security_check_cookie
0x180010547  add     rsp, 128h
0x18001054e  pop     r15
0x180010550  pop     r14
0x180010552  pop     rdi
0x180010553  pop     rsi
0x180010554  pop     rbx
0x180010555  pop     rbp
0x180010556  retn
0x180010557  mov     rcx, [rsp+150h+TokenHandle]; TokenHandle
0x18001055c  lea     rax, [rsp+150h+var_118]
0x180010561  mov     r9d, 54h ; 'T'; TokenInformationLength
0x180010567  mov     [rsp+150h+ReturnLength], rax; ReturnLength
0x18001056c  lea     r8, [rbp+50h+TokenInformation]; TokenInformation
0x180010570  lea     edx, [r9-53h]; TokenInformationClass
0x180010574  call    cs:__imp_NtQueryInformationToken
0x18001057a  mov     rcx, [rsp+150h+TokenHandle]; hObject
0x18001057f  mov     edi, eax
0x180010581  call    cs:__imp_CloseHandle
0x180010587  test    edi, edi
0x180010589  js      short loc_18001052E
0x18001058b  mov     rcx, [rbp+50h+TokenInformation]; Sid
0x18001058f  call    cs:__imp_RtlLengthSid
0x180010595  mov     ebx, eax
0x180010597  cmp     eax, [rsi]
0x180010599  ja      short loc_1800105D9
0x18001059b  test    r14, r14
0x18001059e  jz      short loc_1800105D9
0x1800105a0  mov     r8, [rbp+50h+TokenInformation]; SourceSid
0x1800105a4  mov     rdx, r14; DestinationSid
0x1800105a7  mov     ecx, eax; DestinationSidLength
0x1800105a9  call    cs:__imp_RtlCopySid
0x1800105af  mov     edi, eax
0x1800105b1  test    eax, eax
0x1800105b3  js      loc_18001052E
0x1800105b9  mov     [rsi], ebx
0x1800105bb  jmp     loc_18001052E
0x1800105c0  mov     r8d, eax
0x1800105c3  lea     rdx, aNtqueryinforma_1; "NtQueryInformationProcess failed: 0x%x"
0x1800105ca  mov     ecx, 8; int
0x1800105cf  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800105d4  jmp     loc_18001052E
0x1800105d9  mov     edi, 0C0000023h
0x1800105de  jmp     short loc_1800105B9
0x1800105e0  mov     rcx, [rsp+150h+ProcessHandle]; hObject
0x1800105e5  call    cs:__imp_CloseHandle
0x1800105eb  lea     rdx, aGetsidfromproc; "GetSidFromProcessId: mimatching create "...
0x1800105f2  mov     ecx, 8; int
0x1800105f7  mov     edi, 0C0000008h
0x1800105fc  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180010601  jmp     loc_180010539
```
