# CProcessUtils::GetSidFromProcessId(void *,_LARGE_INTEGER,void * *,ulong *,long *)

- ea: `0x1800057c0`
- end: `0x180005b2f`
- name: `?GetSidFromProcessId@CProcessUtils@@QEAAJPEAXT_LARGE_INTEGER@@PEAPEAXPEAKPEAJ@Z`
- size: `879`
- prototype: `__int64 __fastcall(CProcessUtils *__hidden this, void *, union _LARGE_INTEGER, void **, unsigned int *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800053c0`

## callees

- `0x1800057c0`
- `0x180005b40`
- `0x180032c20`
- `0x180034010`

## import_xrefs

- `ntdll!RtlCopySid` at `0x18000596f`
- `ntdll!RtlCopySid` at `0x18000596f`
- `ntdll!RtlLengthSid` at `0x18000593d`
- `ntdll!RtlLengthSid` at `0x18000593d`
- `ntdll!NtQueryInformationToken` at `0x18000591d`
- `ntdll!NtQueryInformationToken` at `0x18000591d`
- `ntdll!NtOpenProcess` at `0x18000586b`
- `ntdll!NtOpenProcess` at `0x18000586b`
- `ntdll!NtQueryInformationProcess` at `0x1800058a5`
- `ntdll!NtQueryInformationProcess` at `0x1800058a5`
- `ntdll!NtOpenProcessToken` at `0x1800058e3`
- `ntdll!NtOpenProcessToken` at `0x1800058e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800059a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800059b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800059a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800059b6`

## string_xrefs

- `0x1800059e5`: `CProcessUtils::GetSidFromProcessId`
- `0x180005a14`: `CProcessUtils::GetSidFromProcessId`
- `0x180005a46`: `CProcessUtils::GetSidFromProcessId`
- `0x180005a78`: `CProcessUtils::GetSidFromProcessId`
- `0x180005aaf`: `CProcessUtils::GetSidFromProcessId`
- `0x180005ad7`: `CProcessUtils::GetSidFromProcessId`
- `0x1800059ef`: `NtOpenProcess failed: 0x%x in %s`
- `0x180005a50`: `NtQueryInformationToken failed: 0x%x in %s`
- `0x180005a82`: `NtOpenProcessToken failed: 0x%x in %s`
- `0x180005b0c`: `GetSidFromProcessId: mismatching create time`
- `0x180005ae1`: `RtlCopySid failed: 0x%x in %s`

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
  LONG HighPart; // esi
  NTSTATUS v9; // r13d
  unsigned int v10; // edi
  NTSTATUS InformationProcess; // r13d
  NTSTATUS v12; // ebx
  NTSTATUS v13; // ebx
  __int64 v14; // rsi
  void *v15; // rax
  void *v16; // rbx
  NTSTATUS v17; // eax
  int v18; // r13d
  CProcessUtils *v20; // rax
  void *ProcessHandle; // [rsp+30h] [rbp-D0h] BYREF
  ULONG ReturnLength; // [rsp+38h] [rbp-C8h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-C0h] BYREF
  CProcessUtils *v24; // [rsp+48h] [rbp-B8h]
  _CLIENT_ID ClientId; // [rsp+50h] [rbp-B0h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-A0h] BYREF
  _OWORD ProcessInformation[2]; // [rsp+90h] [rbp-70h] BYREF
  PSID TokenInformation[12]; // [rsp+B0h] [rbp-50h] BYREF

  *a4 = 0;
  v24 = this;
  LowPart = a3.LowPart;
  ClientId.UniqueProcess = a2;
  *a5 = 0;
  *a6 = -1073741822;
  HighPart = a3.HighPart;
  ReturnLength = 0;
  ProcessHandle = 0;
  TokenHandle = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  memset(ProcessInformation, 0, sizeof(ProcessInformation));
  memset(&ObjectAttributes.RootDirectory, 0, 40);
  ClientId.UniqueThread = 0;
  v9 = NtOpenProcess(&ProcessHandle, 0x1000u, &ObjectAttributes, &ClientId);
  v10 = v9 | 0x10000000;
  if ( v9 < 0 )
  {
    _DbgPrintMessage(8, "NtOpenProcess failed: 0x%x in %s", v10, "CProcessUtils::GetSidFromProcessId");
    *a6 = v9;
LABEL_15:
    *a4 = 0;
    *a5 = 0;
    goto LABEL_9;
  }
  InformationProcess = NtQueryInformationProcess(ProcessHandle, ProcessTimes, ProcessInformation, 0x20u, 0);
  v10 = InformationProcess | 0x10000000;
  if ( InformationProcess < 0 )
  {
    _DbgPrintMessage(8, "NtQueryInformationProcess failed: 0x%x in %s", v10, "CProcessUtils::GetSidFromProcessId");
    *a6 = InformationProcess;
    *a4 = 0;
    *a5 = 0;
    goto LABEL_9;
  }
  if ( *(_QWORD *)&ProcessInformation[0] != __PAIR64__(HighPart, LowPart) )
  {
    _DbgPrintMessage(8, "GetSidFromProcessId: mismatching create time");
    v10 = -805306360;
    *a6 = -1073741816;
    goto LABEL_15;
  }
  v12 = NtOpenProcessToken(ProcessHandle, 8u, &TokenHandle);
  v10 = v12 | 0x10000000;
  if ( v12 < 0 )
  {
    _DbgPrintMessage(8, "NtOpenProcessToken failed: 0x%x in %s", v10, "CProcessUtils::GetSidFromProcessId");
    *a6 = v12;
    *a4 = 0;
    *a5 = 0;
  }
  else
  {
    v13 = NtQueryInformationToken(TokenHandle, TokenUser, TokenInformation, 0x54u, &ReturnLength);
    v10 = v13 | 0x10000000;
    if ( v13 >= 0 )
    {
      v14 = RtlLengthSid(TokenInformation[0]);
      v15 = (void *)(*(__int64 (__fastcall **)(__int64))v24)(v14);
      v16 = v15;
      if ( v15 )
      {
        v17 = RtlCopySid(v14, v15, TokenInformation[0]);
        v18 = v17;
        v10 = v17 | 0x10000000;
        if ( v17 >= 0 )
        {
          *a4 = v16;
          *a5 = v14;
          *a6 = v17;
          goto LABEL_9;
        }
        _DbgPrintMessage(8, "RtlCopySid failed: 0x%x in %s", v10, "CProcessUtils::GetSidFromProcessId");
        v20 = v24;
        *a6 = v18;
        (*((void (__fastcall **)(void *))v20 + 1))(v16);
      }
      else
      {
        v10 = -805306345;
        _DbgPrintMessage(8, "memory allocation failed: 0x%x in %s", -805306345, "CProcessUtils::GetSidFromProcessId");
        *a6 = -1073741801;
      }
      goto LABEL_15;
    }
    _DbgPrintMessage(8, "NtQueryInformationToken failed: 0x%x in %s", v10, "CProcessUtils::GetSidFromProcessId");
    *a6 = v13;
    *a4 = 0;
    *a5 = 0;
  }
LABEL_9:
  if ( ProcessHandle )
    CloseHandle(ProcessHandle);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v10;
}

```

## disassembly

```asm
0x1800057c0  push    rbp
0x1800057c2  push    rbx
0x1800057c3  push    rsi
0x1800057c4  push    rdi
0x1800057c5  push    r12
0x1800057c7  push    r13
0x1800057c9  push    r14
0x1800057cb  push    r15
0x1800057cd  lea     rbp, [rsp-28h]
0x1800057d2  sub     rsp, 128h
0x1800057d9  mov     rax, cs:__security_cookie
0x1800057e0  xor     rax, rsp
0x1800057e3  mov     [rbp+60h+var_50], rax
0x1800057e7  mov     r15, [rbp+60h+arg_20]
0x1800057ee  xor     eax, eax
0x1800057f0  mov     r12, [rbp+60h+arg_28]
0x1800057f7  xorps   xmm0, xmm0
0x1800057fa  mov     [r9], rax
0x1800057fd  mov     rsi, r8
0x180005800  mov     r14, r9
0x180005803  mov     [rsp+160h+var_118], rcx
0x180005808  mov     rbx, r8
0x18000580b  mov     [rsp+160h+ClientId.UniqueProcess], rdx
0x180005810  mov     [r15], eax
0x180005813  lea     r9, [rsp+160h+ClientId]; ClientId
0x180005818  lea     r8, [rsp+160h+ObjectAttributes]; ObjectAttributes
0x18000581d  mov     dword ptr [r12], 0C0000002h
0x180005825  mov     edx, 1000h; DesiredAccess
0x18000582a  shr     rsi, 20h
0x18000582e  lea     rcx, [rsp+160h+ProcessHandle]; ProcessHandle
0x180005833  mov     [rsp+160h+var_128], eax
0x180005837  mov     [rsp+160h+ProcessHandle], rax
0x18000583c  mov     [rsp+160h+TokenHandle], rax
0x180005841  mov     qword ptr [rsp+160h+ObjectAttributes.Length], 30h ; '0'
0x18000584a  mov     qword ptr [rsp+160h+ObjectAttributes.Attributes], rax
0x18000584f  movups  [rbp+60h+ProcessInformation], xmm0
0x180005853  mov     [rsp+160h+ObjectAttributes.RootDirectory], rax
0x180005858  movups  [rbp+60h+var_C0], xmm0
0x18000585c  mov     [rsp+160h+ObjectAttributes.ObjectName], rax
0x180005861  movdqu  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm0
0x180005866  mov     [rsp+160h+ClientId.UniqueThread], rax
0x18000586b  call    cs:__imp_NtOpenProcess
0x180005872  nop     dword ptr [rax+rax+00h]
0x180005877  mov     edi, eax
0x180005879  mov     r13d, eax
0x18000587c  or      edi, 10000000h
0x180005882  jl      loc_1800059E5
0x180005888  mov     rcx, [rsp+160h+ProcessHandle]; ProcessHandle
0x18000588d  lea     r8, [rbp+60h+ProcessInformation]; ProcessInformation
0x180005891  mov     r9d, 20h ; ' '; ProcessInformationLength
0x180005897  mov     [rsp+160h+ReturnLength], 0; ReturnLength
0x1800058a0  mov     edx, 4; ProcessInformationClass
0x1800058a5  call    cs:__imp_NtQueryInformationProcess
0x1800058ac  nop     dword ptr [rax+rax+00h]
0x1800058b1  mov     edi, eax
0x1800058b3  mov     r13d, eax
0x1800058b6  or      edi, 10000000h
0x1800058bc  jl      loc_180005A14
0x1800058c2  cmp     dword ptr [rbp+60h+ProcessInformation], ebx
0x1800058c5  jnz     loc_180005B0C
0x1800058cb  cmp     dword ptr [rbp+60h+ProcessInformation+4], esi
0x1800058ce  jnz     loc_180005B0C
0x1800058d4  mov     rcx, [rsp+160h+ProcessHandle]; ProcessHandle
0x1800058d9  lea     r8, [rsp+160h+TokenHandle]; TokenHandle
0x1800058de  mov     edx, 8; DesiredAccess
0x1800058e3  call    cs:__imp_NtOpenProcessToken
0x1800058ea  nop     dword ptr [rax+rax+00h]
0x1800058ef  mov     edi, eax
0x1800058f1  mov     ebx, eax
0x1800058f3  or      edi, 10000000h
0x1800058f9  jl      loc_180005A78
0x1800058ff  mov     rcx, [rsp+160h+TokenHandle]; TokenHandle
0x180005904  lea     rax, [rsp+160h+var_128]
0x180005909  mov     r9d, 54h ; 'T'; TokenInformationLength
0x18000590f  mov     [rsp+160h+ReturnLength], rax; ReturnLength
0x180005914  lea     r8, [rbp+60h+TokenInformation]; TokenInformation
0x180005918  mov     edx, 1; TokenInformationClass
0x18000591d  call    cs:__imp_NtQueryInformationToken
0x180005924  nop     dword ptr [rax+rax+00h]
0x180005929  mov     edi, eax
0x18000592b  mov     ebx, eax
0x18000592d  or      edi, 10000000h
0x180005933  jl      loc_180005A46
0x180005939  mov     rcx, [rbp+60h+TokenInformation]; Sid
0x18000593d  call    cs:__imp_RtlLengthSid
0x180005944  nop     dword ptr [rax+rax+00h]
0x180005949  mov     esi, eax
0x18000594b  mov     ecx, eax
0x18000594d  mov     rax, [rsp+160h+var_118]
0x180005952  mov     rax, [rax]
0x180005955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000595a  mov     rbx, rax
0x18000595d  test    rax, rax
0x180005960  jz      loc_180005AAA
0x180005966  mov     r8, [rbp+60h+TokenInformation]; SourceSid
0x18000596a  mov     rdx, rax; DestinationSid
0x18000596d  mov     ecx, esi; DestinationSidLength
0x18000596f  call    cs:__imp_RtlCopySid
0x180005976  nop     dword ptr [rax+rax+00h]
0x18000597b  mov     edi, eax
0x18000597d  mov     r13d, eax
0x180005980  or      edi, 10000000h
0x180005986  jl      loc_180005AD7
0x18000598c  mov     [r14], rbx
0x18000598f  mov     [r15], esi
0x180005992  mov     [r12], eax
0x180005996  mov     rcx, [rsp+160h+ProcessHandle]; hObject
0x18000599b  test    rcx, rcx
0x18000599e  jz      short loc_1800059AC
0x1800059a0  call    cs:__imp_CloseHandle
0x1800059a7  nop     dword ptr [rax+rax+00h]
0x1800059ac  mov     rcx, [rsp+160h+TokenHandle]; hObject
0x1800059b1  test    rcx, rcx
0x1800059b4  jz      short loc_1800059C2
0x1800059b6  call    cs:__imp_CloseHandle
0x1800059bd  nop     dword ptr [rax+rax+00h]
0x1800059c2  mov     eax, edi
0x1800059c4  mov     rcx, [rbp+60h+var_50]
0x1800059c8  xor     rcx, rsp; StackCookie
0x1800059cb  call    __security_check_cookie
0x1800059d0  add     rsp, 128h
0x1800059d7  pop     r15
0x1800059d9  pop     r14
0x1800059db  pop     r13
0x1800059dd  pop     r12
0x1800059df  pop     rdi
0x1800059e0  pop     rsi
0x1800059e1  pop     rbx
0x1800059e2  pop     rbp
0x1800059e3  retn
0x1800059e5  lea     r9, aCprocessutilsG; "CProcessUtils::GetSidFromProcessId"
0x1800059ec  mov     r8d, edi
0x1800059ef  lea     rdx, aNtopenprocessF; "NtOpenProcess failed: 0x%x in %s"
0x1800059f6  mov     ecx, 8; int
0x1800059fb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180005a00  mov     [r12], r13d
0x180005a04  mov     qword ptr [r14], 0
0x180005a0b  mov     dword ptr [r15], 0
0x180005a12  jmp     short loc_180005996
0x180005a14  lea     r9, aCprocessutilsG; "CProcessUtils::GetSidFromProcessId"
0x180005a1b  mov     r8d, edi
0x180005a1e  lea     rdx, aNtqueryinforma_0; "NtQueryInformationProcess failed: 0x%x "...
0x180005a25  mov     ecx, 8; int
0x180005a2a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180005a2f  mov     [r12], r13d
0x180005a33  mov     qword ptr [r14], 0
0x180005a3a  mov     dword ptr [r15], 0
0x180005a41  jmp     loc_180005996
0x180005a46  lea     r9, aCprocessutilsG; "CProcessUtils::GetSidFromProcessId"
0x180005a4d  mov     r8d, edi
0x180005a50  lea     rdx, aNtqueryinforma; "NtQueryInformationToken failed: 0x%x in"...
0x180005a57  mov     ecx, 8; int
0x180005a5c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180005a61  mov     [r12], ebx
0x180005a65  mov     qword ptr [r14], 0
0x180005a6c  mov     dword ptr [r15], 0
0x180005a73  jmp     loc_180005996
0x180005a78  lea     r9, aCprocessutilsG; "CProcessUtils::GetSidFromProcessId"
0x180005a7f  mov     r8d, edi
0x180005a82  lea     rdx, aNtopenprocesst; "NtOpenProcessToken failed: 0x%x in %s"
0x180005a89  mov     ecx, 8; int
0x180005a8e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180005a93  mov     [r12], ebx
0x180005a97  mov     qword ptr [r14], 0
0x180005a9e  mov     dword ptr [r15], 0
0x180005aa5  jmp     loc_180005996
0x180005aaa  mov     edi, 0D0000017h
0x180005aaf  lea     r9, aCprocessutilsG; "CProcessUtils::GetSidFromProcessId"
0x180005ab6  mov     r8d, edi
0x180005ab9  lea     rdx, aMemoryAllocati_0; "memory allocation failed: 0x%x in %s"
0x180005ac0  mov     ecx, 8; int
0x180005ac5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180005aca  mov     dword ptr [r12], 0C0000017h
0x180005ad2  jmp     loc_180005A04
0x180005ad7  lea     r9, aCprocessutilsG; "CProcessUtils::GetSidFromProcessId"
0x180005ade  mov     r8d, edi
0x180005ae1  lea     rdx, aRtlcopysidFail; "RtlCopySid failed: 0x%x in %s"
0x180005ae8  mov     ecx, 8; int
0x180005aed  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180005af2  mov     rax, [rsp+160h+var_118]
0x180005af7  mov     rcx, rbx
0x180005afa  mov     [r12], r13d
0x180005afe  mov     rax, [rax+8]
0x180005b02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b07  jmp     loc_180005A04
0x180005b0c  lea     rdx, aGetsidfromproc_0; "GetSidFromProcessId: mismatching create"...
0x180005b13  mov     ecx, 8; int
0x180005b18  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180005b1d  mov     edi, 0D0000008h
0x180005b22  mov     dword ptr [r12], 0C0000008h
0x180005b2a  jmp     loc_180005A04
```
