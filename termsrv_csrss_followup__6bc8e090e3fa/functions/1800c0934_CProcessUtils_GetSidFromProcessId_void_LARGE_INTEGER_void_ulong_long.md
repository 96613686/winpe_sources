# CProcessUtils::GetSidFromProcessId(void *,_LARGE_INTEGER,void * *,ulong *,long *)

- ea: `0x1800c0934`
- end: `0x1800c0c12`
- name: `?GetSidFromProcessId@CProcessUtils@@QEAAJPEAXT_LARGE_INTEGER@@PEAPEAXPEAKPEAJ@Z`
- size: `734`
- prototype: `__int64 __fastcall(CProcessUtils *__hidden this, void *, union _LARGE_INTEGER, void **, unsigned int *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800c0308`

## callees

- `0x180009940`
- `0x180033f60`
- `0x1800c0934`
- `0x1800ce010`

## import_xrefs

- `ntdll!RtlCopySid` at `0x1800c0b3c`
- `ntdll!RtlCopySid` at `0x1800c0b3c`
- `ntdll!NtQueryInformationToken` at `0x1800c0ab1`
- `ntdll!NtQueryInformationToken` at `0x1800c0ab1`
- `ntdll!NtOpenProcess` at `0x1800c09e3`
- `ntdll!NtOpenProcess` at `0x1800c09e3`
- `ntdll!NtOpenProcessToken` at `0x1800c0a6f`
- `ntdll!NtOpenProcessToken` at `0x1800c0a6f`
- `ntdll!RtlLengthSid` at `0x1800c0aeb`
- `ntdll!RtlLengthSid` at `0x1800c0aeb`
- `ntdll!NtQueryInformationProcess` at `0x1800c0a21`
- `ntdll!NtQueryInformationProcess` at `0x1800c0a21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c0bcd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c0be3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c0bcd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c0be3`

## string_xrefs

- `0x1800c0ad0`: `CProcessUtils::GetSidFromProcessId`
- `0x1800c0b12`: `CProcessUtils::GetSidFromProcessId`
- `0x1800c0b55`: `CProcessUtils::GetSidFromProcessId`
- `0x1800c09fc`: `NtOpenProcess failed: 0x%x in %s`
- `0x1800c0a8b`: `NtOpenProcessToken failed: 0x%x in %s`
- `0x1800c0b94`: `GetSidFromProcessId: mismatching create time`
- `0x1800c0b5f`: `RtlCopySid failed: 0x%x in %s`
- `0x1800c0ac7`: `NtQueryInformationToken failed: 0x%x in %s`

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
0x1800c0934  push    rbp
0x1800c0936  push    rbx
0x1800c0937  push    rsi
0x1800c0938  push    rdi
0x1800c0939  push    r12
0x1800c093b  push    r13
0x1800c093d  push    r14
0x1800c093f  push    r15
0x1800c0941  lea     rbp, [rsp-38h]
0x1800c0946  sub     rsp, 138h
0x1800c094d  mov     rax, cs:__security_cookie
0x1800c0954  xor     rax, rsp
0x1800c0957  mov     [rbp+70h+var_50], rax
0x1800c095b  mov     rax, [rbp+70h+arg_20]
0x1800c0962  xorps   xmm0, xmm0
0x1800c0965  mov     rsi, [rbp+70h+arg_28]
0x1800c096c  mov     r12, rcx
0x1800c096f  mov     [rsp+170h+var_120], rcx
0x1800c0974  mov     r15, r8
0x1800c0977  xor     ecx, ecx
0x1800c0979  mov     [rsp+170h+ClientId.UniqueProcess], rdx
0x1800c097e  mov     [r9], rcx
0x1800c0981  mov     r13, r9
0x1800c0984  mov     [rax], ecx
0x1800c0986  lea     r9, [rsp+170h+ClientId]; ClientId
0x1800c098b  mov     rbx, r8
0x1800c098e  mov     [rsp+170h+var_138], ecx
0x1800c0992  mov     [rsp+170h+ProcessHandle], rcx
0x1800c0997  lea     r8, [rsp+170h+ObjectAttributes]; ObjectAttributes
0x1800c099c  mov     [rsp+170h+TokenHandle], rcx
0x1800c09a1  mov     edx, 1000h; DesiredAccess
0x1800c09a6  mov     qword ptr [rbp+70h+ObjectAttributes.Attributes], rcx
0x1800c09aa  mov     [rsp+170h+ObjectAttributes.RootDirectory], rcx
0x1800c09af  mov     [rsp+170h+ObjectAttributes.ObjectName], rcx
0x1800c09b4  mov     [rsp+170h+ClientId.UniqueThread], rcx
0x1800c09b9  lea     rcx, [rsp+170h+ProcessHandle]; ProcessHandle
0x1800c09be  shr     r15, 20h
0x1800c09c2  mov     [rsp+170h+var_128], rax
0x1800c09c7  mov     qword ptr [rsp+170h+ObjectAttributes.Length], 30h ; '0'
0x1800c09d0  movups  [rbp+70h+ProcessInformation], xmm0
0x1800c09d4  mov     dword ptr [rsi], 0C0000002h
0x1800c09da  movups  [rbp+70h+var_C8], xmm0
0x1800c09de  movdqu  xmmword ptr [rbp+70h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800c09e3  call    cs:__imp_NtOpenProcess
0x1800c09ea  nop     dword ptr [rax+rax+00h]
0x1800c09ef  mov     edi, eax
0x1800c09f1  mov     r14d, eax
0x1800c09f4  or      edi, 10000000h
0x1800c09fa  jge     short loc_1800C0A05
0x1800c09fc  lea     rdx, aNtopenprocessF; "NtOpenProcess failed: 0x%x in %s"
0x1800c0a03  jmp     short loc_1800C0A41
0x1800c0a05  mov     rcx, [rsp+170h+ProcessHandle]; ProcessHandle
0x1800c0a0a  lea     r8, [rbp+70h+ProcessInformation]; ProcessInformation
0x1800c0a0e  mov     r9d, 20h ; ' '; ProcessInformationLength
0x1800c0a14  mov     [rsp+170h+ReturnLength], 0; ReturnLength
0x1800c0a1d  lea     edx, [r9-1Ch]; ProcessInformationClass
0x1800c0a21  call    cs:__imp_NtQueryInformationProcess
0x1800c0a28  nop     dword ptr [rax+rax+00h]
0x1800c0a2d  mov     edi, eax
0x1800c0a2f  mov     r14d, eax
0x1800c0a32  or      edi, 10000000h
0x1800c0a38  jge     short loc_1800C0A4B
0x1800c0a3a  lea     rdx, aNtqueryinforma_0; "NtQueryInformationProcess failed: 0x%x "...
0x1800c0a41  mov     ecx, 8
0x1800c0a46  jmp     loc_1800C0AD0
0x1800c0a4b  cmp     dword ptr [rbp+70h+ProcessInformation], ebx
0x1800c0a4e  jnz     loc_1800C0B94
0x1800c0a54  cmp     dword ptr [rbp+70h+ProcessInformation+4], r15d
0x1800c0a58  jnz     loc_1800C0B94
0x1800c0a5e  mov     rcx, [rsp+170h+ProcessHandle]; ProcessHandle
0x1800c0a63  lea     r8, [rsp+170h+TokenHandle]; TokenHandle
0x1800c0a68  mov     ebx, 8
0x1800c0a6d  mov     edx, ebx; DesiredAccess
0x1800c0a6f  call    cs:__imp_NtOpenProcessToken
0x1800c0a76  nop     dword ptr [rax+rax+00h]
0x1800c0a7b  mov     edi, eax
0x1800c0a7d  mov     r15d, 10000000h
0x1800c0a83  or      edi, r15d
0x1800c0a86  mov     r14d, eax
0x1800c0a89  jge     short loc_1800C0A94
0x1800c0a8b  lea     rdx, aNtopenprocesst; "NtOpenProcessToken failed: 0x%x in %s"
0x1800c0a92  jmp     short loc_1800C0ACE
0x1800c0a94  mov     rcx, [rsp+170h+TokenHandle]; TokenHandle
0x1800c0a99  lea     rax, [rsp+170h+var_138]
0x1800c0a9e  mov     r9d, 54h ; 'T'; TokenInformationLength
0x1800c0aa4  mov     [rsp+170h+ReturnLength], rax; ReturnLength
0x1800c0aa9  lea     r8, [rbp+70h+TokenInformation]; TokenInformation
0x1800c0aad  lea     edx, [r9-53h]; TokenInformationClass
0x1800c0ab1  call    cs:__imp_NtQueryInformationToken
0x1800c0ab8  nop     dword ptr [rax+rax+00h]
0x1800c0abd  mov     edi, eax
0x1800c0abf  mov     r14d, eax
0x1800c0ac2  or      edi, r15d
0x1800c0ac5  jge     short loc_1800C0AE7
0x1800c0ac7  lea     rdx, aNtqueryinforma; "NtQueryInformationToken failed: 0x%x in"...
0x1800c0ace  mov     ecx, ebx; int
0x1800c0ad0  lea     r9, aCprocessutilsG; "CProcessUtils::GetSidFromProcessId"
0x1800c0ad7  mov     r8d, edi
0x1800c0ada  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800c0adf  mov     [rsi], r14d
0x1800c0ae2  jmp     loc_1800C0BB0
0x1800c0ae7  mov     rcx, [rbp+70h+TokenInformation]; Sid
0x1800c0aeb  call    cs:__imp_RtlLengthSid
0x1800c0af2  nop     dword ptr [rax+rax+00h]
0x1800c0af7  mov     r15d, eax
0x1800c0afa  mov     ecx, eax
0x1800c0afc  mov     rax, [r12]
0x1800c0b00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0b05  mov     r14, rax
0x1800c0b08  test    rax, rax
0x1800c0b0b  jnz     short loc_1800C0B32
0x1800c0b0d  mov     edi, 0D0000017h
0x1800c0b12  lea     r9, aCprocessutilsG; "CProcessUtils::GetSidFromProcessId"
0x1800c0b19  mov     r8d, edi
0x1800c0b1c  lea     rdx, aMemoryAllocati_0; "memory allocation failed: 0x%x in %s"
0x1800c0b23  mov     ecx, ebx; int
0x1800c0b25  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800c0b2a  mov     dword ptr [rsi], 0C0000017h
0x1800c0b30  jmp     short loc_1800C0BB0
0x1800c0b32  mov     r8, [rbp+70h+TokenInformation]; SourceSid
0x1800c0b36  mov     rdx, r14; DestinationSid
0x1800c0b39  mov     ecx, r15d; DestinationSidLength
0x1800c0b3c  call    cs:__imp_RtlCopySid
0x1800c0b43  nop     dword ptr [rax+rax+00h]
0x1800c0b48  mov     edi, eax
0x1800c0b4a  mov     r12d, eax
0x1800c0b4d  or      edi, 10000000h
0x1800c0b53  jge     short loc_1800C0B83
0x1800c0b55  lea     r9, aCprocessutilsG; "CProcessUtils::GetSidFromProcessId"
0x1800c0b5c  mov     r8d, edi
0x1800c0b5f  lea     rdx, aRtlcopysidFail; "RtlCopySid failed: 0x%x in %s"
0x1800c0b66  mov     ecx, ebx; int
0x1800c0b68  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800c0b6d  mov     rax, [rsp+170h+var_120]
0x1800c0b72  mov     rcx, r14
0x1800c0b75  mov     [rsi], r12d
0x1800c0b78  mov     rax, [rax+8]
0x1800c0b7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0b81  jmp     short loc_1800C0BB0
0x1800c0b83  mov     rax, [rsp+170h+var_128]
0x1800c0b88  mov     [r13+0], r14
0x1800c0b8c  mov     [rax], r15d
0x1800c0b8f  mov     [rsi], r12d
0x1800c0b92  jmp     short loc_1800C0BC3
0x1800c0b94  lea     rdx, aGetsidfromproc; "GetSidFromProcessId: mismatching create"...
0x1800c0b9b  mov     ecx, 8; int
0x1800c0ba0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800c0ba5  mov     edi, 0D0000008h
0x1800c0baa  mov     dword ptr [rsi], 0C0000008h
0x1800c0bb0  mov     rax, [rsp+170h+var_128]
0x1800c0bb5  mov     qword ptr [r13+0], 0
0x1800c0bbd  mov     dword ptr [rax], 0
0x1800c0bc3  mov     rcx, [rsp+170h+ProcessHandle]; hObject
0x1800c0bc8  test    rcx, rcx
0x1800c0bcb  jz      short loc_1800C0BD9
0x1800c0bcd  call    cs:__imp_CloseHandle
0x1800c0bd4  nop     dword ptr [rax+rax+00h]
0x1800c0bd9  mov     rcx, [rsp+170h+TokenHandle]; hObject
0x1800c0bde  test    rcx, rcx
0x1800c0be1  jz      short loc_1800C0BEF
0x1800c0be3  call    cs:__imp_CloseHandle
0x1800c0bea  nop     dword ptr [rax+rax+00h]
0x1800c0bef  mov     eax, edi
0x1800c0bf1  mov     rcx, [rbp+70h+var_50]
0x1800c0bf5  xor     rcx, rsp; StackCookie
0x1800c0bf8  call    __security_check_cookie
0x1800c0bfd  add     rsp, 138h
0x1800c0c04  pop     r15
0x1800c0c06  pop     r14
0x1800c0c08  pop     r13
0x1800c0c0a  pop     r12
0x1800c0c0c  pop     rdi
0x1800c0c0d  pop     rsi
0x1800c0c0e  pop     rbx
0x1800c0c0f  pop     rbp
0x1800c0c10  retn
```
