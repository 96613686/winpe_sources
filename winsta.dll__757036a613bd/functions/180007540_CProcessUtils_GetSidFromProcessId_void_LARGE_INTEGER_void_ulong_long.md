# CProcessUtils::GetSidFromProcessId(void *,_LARGE_INTEGER,void * *,ulong *,long *)

- ea: `0x180007540`
- end: `0x18000787e`
- name: `?GetSidFromProcessId@CProcessUtils@@QEAAJPEAXT_LARGE_INTEGER@@PEAPEAXPEAKPEAJ@Z`
- size: `830`
- prototype: `__int64 __fastcall(CProcessUtils *__hidden this, void *, union _LARGE_INTEGER, void **, unsigned int *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180007140`

## callees

- `0x180007540`
- `0x180007890`
- `0x18002fe40`
- `0x180031010`

## import_xrefs

- `ntdll!RtlCopySid` at `0x1800076d1`
- `ntdll!RtlCopySid` at `0x1800076d1`
- `ntdll!RtlLengthSid` at `0x1800076a5`
- `ntdll!RtlLengthSid` at `0x1800076a5`
- `ntdll!NtQueryInformationToken` at `0x18000768b`
- `ntdll!NtQueryInformationToken` at `0x18000768b`
- `ntdll!NtOpenProcess` at `0x1800075eb`
- `ntdll!NtOpenProcess` at `0x1800075eb`
- `ntdll!NtQueryInformationProcess` at `0x18000761f`
- `ntdll!NtQueryInformationProcess` at `0x18000761f`
- `ntdll!NtOpenProcessToken` at `0x180007657`
- `ntdll!NtOpenProcessToken` at `0x180007657`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800076fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000770c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800076fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000770c`

## string_xrefs

- `0x180007734`: `CProcessUtils::GetSidFromProcessId`
- `0x180007763`: `CProcessUtils::GetSidFromProcessId`
- `0x180007795`: `CProcessUtils::GetSidFromProcessId`
- `0x1800077c7`: `CProcessUtils::GetSidFromProcessId`
- `0x1800077fe`: `CProcessUtils::GetSidFromProcessId`
- `0x180007826`: `CProcessUtils::GetSidFromProcessId`
- `0x18000773e`: `NtOpenProcess failed: 0x%x in %s`
- `0x18000779f`: `NtQueryInformationToken failed: 0x%x in %s`
- `0x1800077d1`: `NtOpenProcessToken failed: 0x%x in %s`
- `0x18000785b`: `GetSidFromProcessId: mismatching create time`
- `0x180007830`: `RtlCopySid failed: 0x%x in %s`

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
0x180007540  push    rbp
0x180007542  push    rbx
0x180007543  push    rsi
0x180007544  push    rdi
0x180007545  push    r12
0x180007547  push    r13
0x180007549  push    r14
0x18000754b  push    r15
0x18000754d  lea     rbp, [rsp-28h]
0x180007552  sub     rsp, 128h
0x180007559  mov     rax, cs:__security_cookie
0x180007560  xor     rax, rsp
0x180007563  mov     [rbp+60h+var_50], rax
0x180007567  mov     r15, [rbp+60h+arg_20]
0x18000756e  xor     eax, eax
0x180007570  mov     r12, [rbp+60h+arg_28]
0x180007577  xorps   xmm0, xmm0
0x18000757a  mov     [r9], rax
0x18000757d  mov     rsi, r8
0x180007580  mov     r14, r9
0x180007583  mov     [rsp+160h+var_118], rcx
0x180007588  mov     rbx, r8
0x18000758b  mov     [rsp+160h+ClientId.UniqueProcess], rdx
0x180007590  mov     [r15], eax
0x180007593  lea     r9, [rsp+160h+ClientId]; ClientId
0x180007598  lea     r8, [rsp+160h+ObjectAttributes]; ObjectAttributes
0x18000759d  mov     dword ptr [r12], 0C0000002h
0x1800075a5  mov     edx, 1000h; DesiredAccess
0x1800075aa  shr     rsi, 20h
0x1800075ae  lea     rcx, [rsp+160h+ProcessHandle]; ProcessHandle
0x1800075b3  mov     [rsp+160h+var_128], eax
0x1800075b7  mov     [rsp+160h+ProcessHandle], rax
0x1800075bc  mov     [rsp+160h+TokenHandle], rax
0x1800075c1  mov     qword ptr [rsp+160h+ObjectAttributes.Length], 30h ; '0'
0x1800075ca  mov     qword ptr [rsp+160h+ObjectAttributes.Attributes], rax
0x1800075cf  movups  [rbp+60h+ProcessInformation], xmm0
0x1800075d3  mov     [rsp+160h+ObjectAttributes.RootDirectory], rax
0x1800075d8  movups  [rbp+60h+var_C0], xmm0
0x1800075dc  mov     [rsp+160h+ObjectAttributes.ObjectName], rax
0x1800075e1  movdqu  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800075e6  mov     [rsp+160h+ClientId.UniqueThread], rax
0x1800075eb  call    cs:__imp_NtOpenProcess
0x1800075f1  mov     edi, eax
0x1800075f3  mov     r13d, eax
0x1800075f6  or      edi, 10000000h
0x1800075fc  jl      loc_180007734
0x180007602  mov     rcx, [rsp+160h+ProcessHandle]; ProcessHandle
0x180007607  lea     r8, [rbp+60h+ProcessInformation]; ProcessInformation
0x18000760b  mov     r9d, 20h ; ' '; ProcessInformationLength
0x180007611  mov     [rsp+160h+ReturnLength], 0; ReturnLength
0x18000761a  mov     edx, 4; ProcessInformationClass
0x18000761f  call    cs:__imp_NtQueryInformationProcess
0x180007625  mov     edi, eax
0x180007627  mov     r13d, eax
0x18000762a  or      edi, 10000000h
0x180007630  jl      loc_180007763
0x180007636  cmp     dword ptr [rbp+60h+ProcessInformation], ebx
0x180007639  jnz     loc_18000785B
0x18000763f  cmp     dword ptr [rbp+60h+ProcessInformation+4], esi
0x180007642  jnz     loc_18000785B
0x180007648  mov     rcx, [rsp+160h+ProcessHandle]; ProcessHandle
0x18000764d  lea     r8, [rsp+160h+TokenHandle]; TokenHandle
0x180007652  mov     edx, 8; DesiredAccess
0x180007657  call    cs:__imp_NtOpenProcessToken
0x18000765d  mov     edi, eax
0x18000765f  mov     ebx, eax
0x180007661  or      edi, 10000000h
0x180007667  jl      loc_1800077C7
0x18000766d  mov     rcx, [rsp+160h+TokenHandle]; TokenHandle
0x180007672  lea     rax, [rsp+160h+var_128]
0x180007677  mov     r9d, 54h ; 'T'; TokenInformationLength
0x18000767d  mov     [rsp+160h+ReturnLength], rax; ReturnLength
0x180007682  lea     r8, [rbp+60h+TokenInformation]; TokenInformation
0x180007686  mov     edx, 1; TokenInformationClass
0x18000768b  call    cs:__imp_NtQueryInformationToken
0x180007691  mov     edi, eax
0x180007693  mov     ebx, eax
0x180007695  or      edi, 10000000h
0x18000769b  jl      loc_180007795
0x1800076a1  mov     rcx, [rbp+60h+TokenInformation]; Sid
0x1800076a5  call    cs:__imp_RtlLengthSid
0x1800076ab  mov     esi, eax
0x1800076ad  mov     ecx, eax
0x1800076af  mov     rax, [rsp+160h+var_118]
0x1800076b4  mov     rax, [rax]
0x1800076b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076bc  mov     rbx, rax
0x1800076bf  test    rax, rax
0x1800076c2  jz      loc_1800077F9
0x1800076c8  mov     r8, [rbp+60h+TokenInformation]; SourceSid
0x1800076cc  mov     rdx, rax; DestinationSid
0x1800076cf  mov     ecx, esi; DestinationSidLength
0x1800076d1  call    cs:__imp_RtlCopySid
0x1800076d7  mov     edi, eax
0x1800076d9  mov     r13d, eax
0x1800076dc  or      edi, 10000000h
0x1800076e2  jl      loc_180007826
0x1800076e8  mov     [r14], rbx
0x1800076eb  mov     [r15], esi
0x1800076ee  mov     [r12], eax
0x1800076f2  mov     rcx, [rsp+160h+ProcessHandle]; hObject
0x1800076f7  test    rcx, rcx
0x1800076fa  jz      short loc_180007702
0x1800076fc  call    cs:__imp_CloseHandle
0x180007702  mov     rcx, [rsp+160h+TokenHandle]; hObject
0x180007707  test    rcx, rcx
0x18000770a  jz      short loc_180007712
0x18000770c  call    cs:__imp_CloseHandle
0x180007712  mov     eax, edi
0x180007714  mov     rcx, [rbp+60h+var_50]
0x180007718  xor     rcx, rsp; StackCookie
0x18000771b  call    __security_check_cookie
0x180007720  add     rsp, 128h
0x180007727  pop     r15
0x180007729  pop     r14
0x18000772b  pop     r13
0x18000772d  pop     r12
0x18000772f  pop     rdi
0x180007730  pop     rsi
0x180007731  pop     rbx
0x180007732  pop     rbp
0x180007733  retn
0x180007734  lea     r9, aCprocessutilsG; "CProcessUtils::GetSidFromProcessId"
0x18000773b  mov     r8d, edi
0x18000773e  lea     rdx, aNtopenprocessF; "NtOpenProcess failed: 0x%x in %s"
0x180007745  mov     ecx, 8; int
0x18000774a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000774f  mov     [r12], r13d
0x180007753  mov     qword ptr [r14], 0
0x18000775a  mov     dword ptr [r15], 0
0x180007761  jmp     short loc_1800076F2
0x180007763  lea     r9, aCprocessutilsG; "CProcessUtils::GetSidFromProcessId"
0x18000776a  mov     r8d, edi
0x18000776d  lea     rdx, aNtqueryinforma_0; "NtQueryInformationProcess failed: 0x%x "...
0x180007774  mov     ecx, 8; int
0x180007779  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000777e  mov     [r12], r13d
0x180007782  mov     qword ptr [r14], 0
0x180007789  mov     dword ptr [r15], 0
0x180007790  jmp     loc_1800076F2
0x180007795  lea     r9, aCprocessutilsG; "CProcessUtils::GetSidFromProcessId"
0x18000779c  mov     r8d, edi
0x18000779f  lea     rdx, aNtqueryinforma; "NtQueryInformationToken failed: 0x%x in"...
0x1800077a6  mov     ecx, 8; int
0x1800077ab  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800077b0  mov     [r12], ebx
0x1800077b4  mov     qword ptr [r14], 0
0x1800077bb  mov     dword ptr [r15], 0
0x1800077c2  jmp     loc_1800076F2
0x1800077c7  lea     r9, aCprocessutilsG; "CProcessUtils::GetSidFromProcessId"
0x1800077ce  mov     r8d, edi
0x1800077d1  lea     rdx, aNtopenprocesst; "NtOpenProcessToken failed: 0x%x in %s"
0x1800077d8  mov     ecx, 8; int
0x1800077dd  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800077e2  mov     [r12], ebx
0x1800077e6  mov     qword ptr [r14], 0
0x1800077ed  mov     dword ptr [r15], 0
0x1800077f4  jmp     loc_1800076F2
0x1800077f9  mov     edi, 0D0000017h
0x1800077fe  lea     r9, aCprocessutilsG; "CProcessUtils::GetSidFromProcessId"
0x180007805  mov     r8d, edi
0x180007808  lea     rdx, aMemoryAllocati_0; "memory allocation failed: 0x%x in %s"
0x18000780f  mov     ecx, 8; int
0x180007814  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180007819  mov     dword ptr [r12], 0C0000017h
0x180007821  jmp     loc_180007753
0x180007826  lea     r9, aCprocessutilsG; "CProcessUtils::GetSidFromProcessId"
0x18000782d  mov     r8d, edi
0x180007830  lea     rdx, aRtlcopysidFail; "RtlCopySid failed: 0x%x in %s"
0x180007837  mov     ecx, 8; int
0x18000783c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180007841  mov     rax, [rsp+160h+var_118]
0x180007846  mov     rcx, rbx
0x180007849  mov     [r12], r13d
0x18000784d  mov     rax, [rax+8]
0x180007851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007856  jmp     loc_180007753
0x18000785b  lea     rdx, aGetsidfromproc_0; "GetSidFromProcessId: mismatching create"...
0x180007862  mov     ecx, 8; int
0x180007867  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000786c  mov     edi, 0D0000008h
0x180007871  mov     dword ptr [r12], 0C0000008h
0x180007879  jmp     loc_180007753
```
