# CProcessUtils::GetSidFromProcessId(void *,_LARGE_INTEGER,void * *,ulong *,long *)

- ea: `0x1800b9f94`
- end: `0x1800ba23e`
- name: `?GetSidFromProcessId@CProcessUtils@@QEAAJPEAXT_LARGE_INTEGER@@PEAPEAXPEAKPEAJ@Z`
- size: `682`
- prototype: `__int64 __fastcall(CProcessUtils *__hidden this, void *, union _LARGE_INTEGER, void **, unsigned int *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800b9978`

## callees

- `0x18000a210`
- `0x1800321f0`
- `0x1800b9f94`
- `0x1800c8010`

## import_xrefs

- `ntdll!RtlCopySid` at `0x1800ba17b`
- `ntdll!RtlCopySid` at `0x1800ba17b`
- `ntdll!NtQueryInformationToken` at `0x1800ba0fc`
- `ntdll!NtQueryInformationToken` at `0x1800ba0fc`
- `ntdll!NtOpenProcess` at `0x1800ba043`
- `ntdll!NtOpenProcess` at `0x1800ba043`
- `ntdll!NtOpenProcessToken` at `0x1800ba0c0`
- `ntdll!NtOpenProcessToken` at `0x1800ba0c0`
- `ntdll!RtlLengthSid` at `0x1800ba130`
- `ntdll!RtlLengthSid` at `0x1800ba130`
- `ntdll!NtQueryInformationProcess` at `0x1800ba07b`
- `ntdll!NtQueryInformationProcess` at `0x1800ba07b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ba206`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ba216`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ba206`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ba216`

## string_xrefs

- `0x1800ba056`: `NtOpenProcess failed: 0x%x in %s`
- `0x1800ba115`: `CProcessUtils::GetSidFromProcessId`
- `0x1800ba151`: `CProcessUtils::GetSidFromProcessId`
- `0x1800ba18e`: `CProcessUtils::GetSidFromProcessId`
- `0x1800ba1cd`: `GetSidFromProcessId: mismatching create time`
- `0x1800ba10c`: `NtQueryInformationToken failed: 0x%x in %s`
- `0x1800ba0d6`: `NtOpenProcessToken failed: 0x%x in %s`
- `0x1800ba198`: `RtlCopySid failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CProcessUtils::GetSidFromProcessId(
        CProcessUtils *this,
        void *a2,
        union _LARGE_INTEGER a3,
        void **a4,
        unsigned int *a5,
        int *a6)
{
  DWORD LowPart; // ebx
  LONG HighPart; // r15d
  NTSTATUS InformationProcess; // r14d
  unsigned int v11; // edi
  const char *v12; // rdx
  NTSTATUS v13; // eax
  __int64 v14; // r15
  void *v15; // rax
  void *v16; // r14
  NTSTATUS v17; // r12d
  CProcessUtils *v18; // rax
  unsigned int *v19; // rax
  unsigned int *v20; // rax
  void *ProcessHandle; // [rsp+30h] [rbp-D0h] BYREF
  ULONG ReturnLength; // [rsp+38h] [rbp-C8h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int *v25; // [rsp+48h] [rbp-B8h]
  CProcessUtils *v26; // [rsp+50h] [rbp-B0h]
  _CLIENT_ID ClientId; // [rsp+58h] [rbp-A8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-98h] BYREF
  _OWORD ProcessInformation[2]; // [rsp+98h] [rbp-68h] BYREF
  PSID TokenInformation[12]; // [rsp+C0h] [rbp-40h] BYREF

  v26 = this;
  ClientId.UniqueProcess = a2;
  *a4 = 0;
  *a5 = 0;
  LowPart = a3.LowPart;
  ReturnLength = 0;
  ProcessHandle = 0;
  TokenHandle = 0;
  memset(&ObjectAttributes.RootDirectory, 0, 24);
  ClientId.UniqueThread = 0;
  HighPart = a3.HighPart;
  v25 = a5;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ProcessInformation[0] = 0;
  *a6 = -1073741822;
  ProcessInformation[1] = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  InformationProcess = NtOpenProcess(&ProcessHandle, 0x1000u, &ObjectAttributes, &ClientId);
  v11 = InformationProcess | 0x10000000;
  if ( InformationProcess < 0 )
  {
    v12 = "NtOpenProcess failed: 0x%x in %s";
LABEL_10:
    _DbgPrintMessage(8, v12, v11, "CProcessUtils::GetSidFromProcessId");
    *a6 = InformationProcess;
    goto LABEL_17;
  }
  InformationProcess = NtQueryInformationProcess(ProcessHandle, ProcessTimes, ProcessInformation, 0x20u, 0);
  v11 = InformationProcess | 0x10000000;
  if ( InformationProcess < 0 )
  {
    v12 = "NtQueryInformationProcess failed: 0x%x in %s";
    goto LABEL_10;
  }
  if ( *(_QWORD *)&ProcessInformation[0] != __PAIR64__(HighPart, LowPart) )
  {
    _DbgPrintMessage(8, "GetSidFromProcessId: mismatching create time");
    v11 = -805306360;
    *a6 = -1073741816;
    goto LABEL_17;
  }
  v13 = NtOpenProcessToken(ProcessHandle, 8u, &TokenHandle);
  v11 = v13 | 0x10000000;
  InformationProcess = v13;
  if ( v13 < 0 )
  {
    v12 = "NtOpenProcessToken failed: 0x%x in %s";
    goto LABEL_10;
  }
  InformationProcess = NtQueryInformationToken(TokenHandle, TokenUser, TokenInformation, 0x54u, &ReturnLength);
  v11 = InformationProcess | 0x10000000;
  if ( InformationProcess < 0 )
  {
    v12 = "NtQueryInformationToken failed: 0x%x in %s";
    goto LABEL_10;
  }
  v14 = RtlLengthSid(TokenInformation[0]);
  v15 = (void *)(*(__int64 (__fastcall **)(__int64))this)(v14);
  v16 = v15;
  if ( v15 )
  {
    v17 = RtlCopySid(v14, v15, TokenInformation[0]);
    v11 = v17 | 0x10000000;
    if ( v17 >= 0 )
    {
      v19 = v25;
      *a4 = v16;
      *v19 = v14;
      *a6 = v17;
      goto LABEL_18;
    }
    _DbgPrintMessage(8, "RtlCopySid failed: 0x%x in %s", v11, "CProcessUtils::GetSidFromProcessId");
    v18 = v26;
    *a6 = v17;
    (*((void (__fastcall **)(void *))v18 + 1))(v16);
  }
  else
  {
    v11 = -805306345;
    _DbgPrintMessage(8, "memory allocation failed: 0x%x in %s", -805306345, "CProcessUtils::GetSidFromProcessId");
    *a6 = -1073741801;
  }
LABEL_17:
  v20 = v25;
  *a4 = 0;
  *v20 = 0;
LABEL_18:
  if ( ProcessHandle )
    CloseHandle(ProcessHandle);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v11;
}

```

## disassembly

```asm
0x1800b9f94  push    rbp
0x1800b9f96  push    rbx
0x1800b9f97  push    rsi
0x1800b9f98  push    rdi
0x1800b9f99  push    r12
0x1800b9f9b  push    r13
0x1800b9f9d  push    r14
0x1800b9f9f  push    r15
0x1800b9fa1  lea     rbp, [rsp-38h]
0x1800b9fa6  sub     rsp, 138h
0x1800b9fad  mov     rax, cs:__security_cookie
0x1800b9fb4  xor     rax, rsp
0x1800b9fb7  mov     [rbp+70h+var_50], rax
0x1800b9fbb  mov     rax, [rbp+70h+arg_20]
0x1800b9fc2  xorps   xmm0, xmm0
0x1800b9fc5  mov     rsi, [rbp+70h+arg_28]
0x1800b9fcc  mov     r12, rcx
0x1800b9fcf  mov     [rsp+170h+var_120], rcx
0x1800b9fd4  mov     r15, r8
0x1800b9fd7  xor     ecx, ecx
0x1800b9fd9  mov     [rsp+170h+ClientId.UniqueProcess], rdx
0x1800b9fde  mov     [r9], rcx
0x1800b9fe1  mov     r13, r9
0x1800b9fe4  mov     [rax], ecx
0x1800b9fe6  lea     r9, [rsp+170h+ClientId]; ClientId
0x1800b9feb  mov     rbx, r8
0x1800b9fee  mov     [rsp+170h+var_138], ecx
0x1800b9ff2  mov     [rsp+170h+ProcessHandle], rcx
0x1800b9ff7  lea     r8, [rsp+170h+ObjectAttributes]; ObjectAttributes
0x1800b9ffc  mov     [rsp+170h+TokenHandle], rcx
0x1800ba001  mov     edx, 1000h; DesiredAccess
0x1800ba006  mov     qword ptr [rbp+70h+ObjectAttributes.Attributes], rcx
0x1800ba00a  mov     [rsp+170h+ObjectAttributes.RootDirectory], rcx
0x1800ba00f  mov     [rsp+170h+ObjectAttributes.ObjectName], rcx
0x1800ba014  mov     [rsp+170h+ClientId.UniqueThread], rcx
0x1800ba019  lea     rcx, [rsp+170h+ProcessHandle]; ProcessHandle
0x1800ba01e  shr     r15, 20h
0x1800ba022  mov     [rsp+170h+var_128], rax
0x1800ba027  mov     qword ptr [rsp+170h+ObjectAttributes.Length], 30h ; '0'
0x1800ba030  movups  [rbp+70h+ProcessInformation], xmm0
0x1800ba034  mov     dword ptr [rsi], 0C0000002h
0x1800ba03a  movups  [rbp+70h+var_C8], xmm0
0x1800ba03e  movdqu  xmmword ptr [rbp+70h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800ba043  call    cs:__imp_NtOpenProcess
0x1800ba049  mov     edi, eax
0x1800ba04b  mov     r14d, eax
0x1800ba04e  or      edi, 10000000h
0x1800ba054  jge     short loc_1800BA05F
0x1800ba056  lea     rdx, aNtopenprocessF; "NtOpenProcess failed: 0x%x in %s"
0x1800ba05d  jmp     short loc_1800BA095
0x1800ba05f  mov     rcx, [rsp+170h+ProcessHandle]; ProcessHandle
0x1800ba064  lea     r8, [rbp+70h+ProcessInformation]; ProcessInformation
0x1800ba068  mov     r9d, 20h ; ' '; ProcessInformationLength
0x1800ba06e  mov     [rsp+170h+ReturnLength], 0; ReturnLength
0x1800ba077  lea     edx, [r9-1Ch]; ProcessInformationClass
0x1800ba07b  call    cs:__imp_NtQueryInformationProcess
0x1800ba081  mov     edi, eax
0x1800ba083  mov     r14d, eax
0x1800ba086  or      edi, 10000000h
0x1800ba08c  jge     short loc_1800BA09C
0x1800ba08e  lea     rdx, aNtqueryinforma_0; "NtQueryInformationProcess failed: 0x%x "...
0x1800ba095  mov     ecx, 8
0x1800ba09a  jmp     short loc_1800BA115
0x1800ba09c  cmp     dword ptr [rbp+70h+ProcessInformation], ebx
0x1800ba09f  jnz     loc_1800BA1CD
0x1800ba0a5  cmp     dword ptr [rbp+70h+ProcessInformation+4], r15d
0x1800ba0a9  jnz     loc_1800BA1CD
0x1800ba0af  mov     rcx, [rsp+170h+ProcessHandle]; ProcessHandle
0x1800ba0b4  lea     r8, [rsp+170h+TokenHandle]; TokenHandle
0x1800ba0b9  mov     ebx, 8
0x1800ba0be  mov     edx, ebx; DesiredAccess
0x1800ba0c0  call    cs:__imp_NtOpenProcessToken
0x1800ba0c6  mov     edi, eax
0x1800ba0c8  mov     r15d, 10000000h
0x1800ba0ce  or      edi, r15d
0x1800ba0d1  mov     r14d, eax
0x1800ba0d4  jge     short loc_1800BA0DF
0x1800ba0d6  lea     rdx, aNtopenprocesst; "NtOpenProcessToken failed: 0x%x in %s"
0x1800ba0dd  jmp     short loc_1800BA113
0x1800ba0df  mov     rcx, [rsp+170h+TokenHandle]; TokenHandle
0x1800ba0e4  lea     rax, [rsp+170h+var_138]
0x1800ba0e9  mov     r9d, 54h ; 'T'; TokenInformationLength
0x1800ba0ef  mov     [rsp+170h+ReturnLength], rax; ReturnLength
0x1800ba0f4  lea     r8, [rbp+70h+TokenInformation]; TokenInformation
0x1800ba0f8  lea     edx, [r9-53h]; TokenInformationClass
0x1800ba0fc  call    cs:__imp_NtQueryInformationToken
0x1800ba102  mov     edi, eax
0x1800ba104  mov     r14d, eax
0x1800ba107  or      edi, r15d
0x1800ba10a  jge     short loc_1800BA12C
0x1800ba10c  lea     rdx, aNtqueryinforma; "NtQueryInformationToken failed: 0x%x in"...
0x1800ba113  mov     ecx, ebx; int
0x1800ba115  lea     r9, aCprocessutilsG; "CProcessUtils::GetSidFromProcessId"
0x1800ba11c  mov     r8d, edi
0x1800ba11f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800ba124  mov     [rsi], r14d
0x1800ba127  jmp     loc_1800BA1E9
0x1800ba12c  mov     rcx, [rbp+70h+TokenInformation]; Sid
0x1800ba130  call    cs:__imp_RtlLengthSid
0x1800ba136  mov     r15d, eax
0x1800ba139  mov     ecx, eax
0x1800ba13b  mov     rax, [r12]
0x1800ba13f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba144  mov     r14, rax
0x1800ba147  test    rax, rax
0x1800ba14a  jnz     short loc_1800BA171
0x1800ba14c  mov     edi, 0D0000017h
0x1800ba151  lea     r9, aCprocessutilsG; "CProcessUtils::GetSidFromProcessId"
0x1800ba158  mov     r8d, edi
0x1800ba15b  lea     rdx, aMemoryAllocati_0; "memory allocation failed: 0x%x in %s"
0x1800ba162  mov     ecx, ebx; int
0x1800ba164  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800ba169  mov     dword ptr [rsi], 0C0000017h
0x1800ba16f  jmp     short loc_1800BA1E9
0x1800ba171  mov     r8, [rbp+70h+TokenInformation]; SourceSid
0x1800ba175  mov     rdx, r14; DestinationSid
0x1800ba178  mov     ecx, r15d; DestinationSidLength
0x1800ba17b  call    cs:__imp_RtlCopySid
0x1800ba181  mov     edi, eax
0x1800ba183  mov     r12d, eax
0x1800ba186  or      edi, 10000000h
0x1800ba18c  jge     short loc_1800BA1BC
0x1800ba18e  lea     r9, aCprocessutilsG; "CProcessUtils::GetSidFromProcessId"
0x1800ba195  mov     r8d, edi
0x1800ba198  lea     rdx, aRtlcopysidFail; "RtlCopySid failed: 0x%x in %s"
0x1800ba19f  mov     ecx, ebx; int
0x1800ba1a1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800ba1a6  mov     rax, [rsp+170h+var_120]
0x1800ba1ab  mov     rcx, r14
0x1800ba1ae  mov     [rsi], r12d
0x1800ba1b1  mov     rax, [rax+8]
0x1800ba1b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba1ba  jmp     short loc_1800BA1E9
0x1800ba1bc  mov     rax, [rsp+170h+var_128]
0x1800ba1c1  mov     [r13+0], r14
0x1800ba1c5  mov     [rax], r15d
0x1800ba1c8  mov     [rsi], r12d
0x1800ba1cb  jmp     short loc_1800BA1FC
0x1800ba1cd  lea     rdx, aGetsidfromproc; "GetSidFromProcessId: mismatching create"...
0x1800ba1d4  mov     ecx, 8; int
0x1800ba1d9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800ba1de  mov     edi, 0D0000008h
0x1800ba1e3  mov     dword ptr [rsi], 0C0000008h
0x1800ba1e9  mov     rax, [rsp+170h+var_128]
0x1800ba1ee  mov     qword ptr [r13+0], 0
0x1800ba1f6  mov     dword ptr [rax], 0
0x1800ba1fc  mov     rcx, [rsp+170h+ProcessHandle]; hObject
0x1800ba201  test    rcx, rcx
0x1800ba204  jz      short loc_1800BA20C
0x1800ba206  call    cs:__imp_CloseHandle
0x1800ba20c  mov     rcx, [rsp+170h+TokenHandle]; hObject
0x1800ba211  test    rcx, rcx
0x1800ba214  jz      short loc_1800BA21C
0x1800ba216  call    cs:__imp_CloseHandle
0x1800ba21c  mov     eax, edi
0x1800ba21e  mov     rcx, [rbp+70h+var_50]
0x1800ba222  xor     rcx, rsp; StackCookie
0x1800ba225  call    __security_check_cookie
0x1800ba22a  add     rsp, 138h
0x1800ba231  pop     r15
0x1800ba233  pop     r14
0x1800ba235  pop     r13
0x1800ba237  pop     r12
0x1800ba239  pop     rdi
0x1800ba23a  pop     rsi
0x1800ba23b  pop     rbx
0x1800ba23c  pop     rbp
0x1800ba23d  retn
```
