# CUserName::Initialize(unsigned __int64,int)

- ea: `0x180009f50`
- end: `0x18000a208`
- name: `?Initialize@CUserName@@UEAAJ_KH@Z`
- size: `696`
- prototype: `__int64 __fastcall(CUserName *__hidden this, void *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004da60`

## callees

- `0x180009f50`
- `0x18000a210`
- `0x18002943c`
- `0x1800321f0`
- `0x1800326dc`

## import_xrefs

- `ntdll!NtDuplicateToken` at `0x180009fe3`
- `ntdll!NtDuplicateToken` at `0x180009fe3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a0a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a0d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a106`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a16e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a0a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a0d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a106`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a16e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a124`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a12d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a124`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a12d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a003`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a003`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000a14f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000a14f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a05d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a1bd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a05d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a1bd`

## string_xrefs

- `0x18000a06b`: `Can get the TOKEN_USER length`
- `0x18000a0b8`: `Can get the TOKEN_USER length: 0x%x`
- `0x18000a11b`: `GetTokenInformatino failed: 0x%x`
- `0x18000a162`: `NtDuplicateToken failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CUserName::Initialize(CUserName *this, void *a2, int a3)
{
  HANDLE *v5; // r14
  NTSTATUS v6; // eax
  unsigned int v7; // edi
  DWORD CurrentProcessId; // eax
  signed int v10; // eax
  signed int v11; // eax
  unsigned int v12; // ebx
  signed int LastError; // eax
  HANDLE CurrentProcess; // rdi
  HANDLE v15; // rax
  void *v16; // rax
  int v17; // eax
  DWORD ReturnLength; // [rsp+40h] [rbp-68h] BYREF
  DWORD v19; // [rsp+44h] [rbp-64h] BYREF
  struct _OBJECT_ATTRIBUTES v20; // [rsp+48h] [rbp-60h] BYREF
  _DWORD v21[4]; // [rsp+78h] [rbp-30h] BYREF

  if ( !a3 )
  {
    ReturnLength = 0;
    v19 = 0;
    if ( GetTokenInformation(a2, TokenUser, 0, 0, &ReturnLength) )
    {
      v7 = -2147024809;
      _DbgPrintMessage(8, "Can get the TOKEN_USER length");
LABEL_8:
      _DbgPrintMessage(8, "InitializeUserName failed: 0x%x in %s", v7, "CUserName::Initialize");
      return v7;
    }
    if ( GetLastError() == 122 )
    {
      v16 = operator new(ReturnLength, (const struct std::nothrow_t *)std::nothrow);
      *((_QWORD *)this + 201) = v16;
      if ( !v16 )
      {
        v7 = -2147024882;
        goto LABEL_8;
      }
      if ( GetTokenInformation(a2, TokenUser, v16, ReturnLength, &v19) )
      {
        v17 = CUserName::ResolveUserName(this, a2);
        v7 = v17;
        if ( v17 >= 0 )
        {
          *((_DWORD *)this + 400) |= 2u;
          return 0;
        }
        _DbgPrintMessage(8, "ResolveUserName failed: 0x%x in %s", v17, "CUserName::InitializeUserName");
        goto LABEL_8;
      }
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      _DbgPrintMessage(8, "GetTokenInformatino failed: 0x%x", v7);
    }
    else
    {
      v10 = GetLastError();
      v7 = v10;
      if ( v10 > 0 )
        v7 = (unsigned __int16)v10 | 0x80070000;
      _DbgPrintMessage(8, "Can get the TOKEN_USER length: 0x%x", v7);
    }
    if ( (v7 & 0x80000000) == 0 )
      return 0;
    goto LABEL_8;
  }
  v5 = (HANDLE *)((char *)this + 1592);
  v21[2] = 1;
  *(_QWORD *)&v20.Length = 48;
  memset(&v20.RootDirectory, 0, 32);
  v21[0] = 12;
  v21[1] = 2;
  v20.SecurityQualityOfService = v21;
  v6 = NtDuplicateToken(a2, 0x2000000u, &v20, 0, TokenPrimary, (PHANDLE)this + 199);
  v7 = v6 | 0x10000000;
  if ( (v6 | 0x10000000) != 0xD0000022 )
  {
    if ( v6 >= 0 )
    {
LABEL_4:
      CurrentProcessId = GetCurrentProcessId();
      *((_DWORD *)this + 400) |= 1u;
      *((_DWORD *)this + 672) = CurrentProcessId;
      return 0;
    }
    _DbgPrintMessage(8, "NtDuplicateToken failed: 0x%x in %s", v7, "CUserName::Initialize");
    return v7;
  }
  CurrentProcess = GetCurrentProcess();
  v15 = GetCurrentProcess();
  if ( DuplicateHandle(v15, a2, CurrentProcess, v5, 0, 0, 2u) )
    goto LABEL_4;
  v11 = GetLastError();
  v12 = v11;
  if ( v11 > 0 )
    v12 = (unsigned __int16)v11 | 0x80070000;
  _DbgPrintMessage(8, "DuplicateHandle failed: 0x%x", v12);
  return v12;
}

```

## disassembly

```asm
0x180009f50  mov     r11, rsp
0x180009f53  mov     [r11+18h], rbx
0x180009f57  mov     [r11+20h], rbp
0x180009f5b  push    rsi
0x180009f5c  push    rdi
0x180009f5d  push    r14
0x180009f5f  sub     rsp, 90h
0x180009f66  mov     rax, cs:__security_cookie
0x180009f6d  xor     rax, rsp
0x180009f70  mov     [rsp+0A8h+var_20], rax
0x180009f78  xor     ebx, ebx
0x180009f7a  xor     r9d, r9d; TokenInformationLength
0x180009f7d  mov     rbp, rdx
0x180009f80  mov     rsi, rcx
0x180009f83  test    r8d, r8d
0x180009f86  jz      loc_18000A040
0x180009f8c  lea     r14, [rcx+638h]
0x180009f93  mov     dword ptr [r11-28h], 1
0x180009f9b  lea     rax, [r11-30h]
0x180009f9f  mov     [r11-80h], r14
0x180009fa3  lea     r8, [r11-60h]; ObjectAttributes
0x180009fa7  mov     [rsp+0A8h+TokenType], 1; TokenType
0x180009faf  mov     edx, 2000000h; DesiredAccess
0x180009fb4  mov     qword ptr [r11-60h], 30h ; '0'
0x180009fbc  mov     rcx, rbp; ExistingTokenHandle
0x180009fbf  mov     [r11-48h], rbx
0x180009fc3  mov     [r11-58h], rbx
0x180009fc7  mov     [r11-50h], rbx
0x180009fcb  mov     [r11-40h], rbx
0x180009fcf  mov     [rsp+0A8h+var_30], 0Ch
0x180009fd7  mov     [rsp+0A8h+var_2C], 2
0x180009fdf  mov     [r11-38h], rax
0x180009fe3  call    cs:__imp_NtDuplicateToken
0x180009fe9  mov     edi, eax
0x180009feb  bts     edi, 1Ch
0x180009fef  cmp     edi, 0D0000022h
0x180009ff5  jz      loc_18000A124
0x180009ffb  test    edi, edi
0x180009ffd  js      loc_18000A162
0x18000a003  call    cs:__imp_GetCurrentProcessId
0x18000a009  or      dword ptr [rsi+640h], 1
0x18000a010  mov     [rsi+0A80h], eax
0x18000a016  mov     eax, ebx
0x18000a018  mov     rcx, [rsp+0A8h+var_20]
0x18000a020  xor     rcx, rsp; StackCookie
0x18000a023  call    __security_check_cookie
0x18000a028  lea     r11, [rsp+0A8h+var_18]
0x18000a030  mov     rbx, [r11+30h]
0x18000a034  mov     rbp, [r11+38h]
0x18000a038  mov     rsp, r11
0x18000a03b  pop     r14
0x18000a03d  pop     rdi
0x18000a03e  pop     rsi
0x18000a03f  retn
0x18000a040  lea     rax, [rsp+0A8h+ReturnLength]
0x18000a045  mov     [rsp+0A8h+ReturnLength], ebx
0x18000a049  xor     r8d, r8d; TokenInformation
0x18000a04c  mov     qword ptr [rsp+0A8h+TokenType], rax; ReturnLength
0x18000a051  mov     edx, 1; TokenInformationClass
0x18000a056  mov     [rsp+0A8h+var_64], ebx
0x18000a05a  mov     rcx, rbp; TokenHandle
0x18000a05d  call    cs:__imp_GetTokenInformation
0x18000a063  test    eax, eax
0x18000a065  jz      loc_18000A16E
0x18000a06b  lea     rdx, aCanGetTheToken; "Can get the TOKEN_USER length"
0x18000a072  mov     ecx, 8; int
0x18000a077  mov     edi, 80070057h
0x18000a07c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000a081  lea     rdx, aInitializeuser; "InitializeUserName failed: 0x%x in %s"
0x18000a088  lea     r9, aCusernameIniti_1; "CUserName::Initialize"
0x18000a08f  mov     r8d, edi
0x18000a092  mov     ecx, 8; int
0x18000a097  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000a09c  mov     eax, edi
0x18000a09e  jmp     loc_18000A018
0x18000a0a3  call    cs:__imp_GetLastError
0x18000a0a9  mov     edi, eax
0x18000a0ab  test    eax, eax
0x18000a0ad  jle     short loc_18000A0B8
0x18000a0af  movzx   edi, ax
0x18000a0b2  or      edi, 80070000h
0x18000a0b8  lea     rdx, aCanGetTheToken_0; "Can get the TOKEN_USER length: 0x%x"
0x18000a0bf  mov     r8d, edi
0x18000a0c2  mov     ecx, 8; int
0x18000a0c7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000a0cc  test    edi, edi
0x18000a0ce  jns     loc_18000A016
0x18000a0d4  jmp     short loc_18000A081
0x18000a0d6  call    cs:__imp_GetLastError
0x18000a0dc  mov     ebx, eax
0x18000a0de  test    eax, eax
0x18000a0e0  jle     short loc_18000A0EB
0x18000a0e2  movzx   ebx, ax
0x18000a0e5  or      ebx, 80070000h
0x18000a0eb  mov     r8d, ebx
0x18000a0ee  lea     rdx, aDuplicatehandl_1; "DuplicateHandle failed: 0x%x"
0x18000a0f5  mov     ecx, 8; int
0x18000a0fa  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000a0ff  mov     eax, ebx
0x18000a101  jmp     loc_18000A018
0x18000a106  call    cs:__imp_GetLastError
0x18000a10c  mov     edi, eax
0x18000a10e  test    eax, eax
0x18000a110  jle     short loc_18000A11B
0x18000a112  movzx   edi, ax
0x18000a115  or      edi, 80070000h
0x18000a11b  lea     rdx, aGettokeninform_0; "GetTokenInformatino failed: 0x%x"
0x18000a122  jmp     short loc_18000A0BF
0x18000a124  call    cs:__imp_GetCurrentProcess
0x18000a12a  mov     rdi, rax
0x18000a12d  call    cs:__imp_GetCurrentProcess
0x18000a133  mov     [rsp+0A8h+dwOptions], 2; dwOptions
0x18000a13b  mov     r9, r14; lpTargetHandle
0x18000a13e  mov     rcx, rax; hSourceProcessHandle
0x18000a141  mov     [rsp+0A8h+bInheritHandle], ebx; bInheritHandle
0x18000a145  mov     r8, rdi; hTargetProcessHandle
0x18000a148  mov     [rsp+0A8h+TokenType], ebx; dwDesiredAccess
0x18000a14c  mov     rdx, rbp; hSourceHandle
0x18000a14f  call    cs:__imp_DuplicateHandle
0x18000a155  test    eax, eax
0x18000a157  jnz     loc_18000A003
0x18000a15d  jmp     loc_18000A0D6
0x18000a162  lea     rdx, aNtduplicatetok; "NtDuplicateToken failed: 0x%x in %s"
0x18000a169  jmp     loc_18000A088
0x18000a16e  call    cs:__imp_GetLastError
0x18000a174  cmp     eax, 7Ah ; 'z'
0x18000a177  jnz     loc_18000A0A3
0x18000a17d  mov     ecx, [rsp+0A8h+ReturnLength]; unsigned __int64
0x18000a181  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a188  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a18d  mov     [rsi+648h], rax
0x18000a194  test    rax, rax
0x18000a197  jnz     short loc_18000A1A3
0x18000a199  mov     edi, 8007000Eh
0x18000a19e  jmp     loc_18000A081
0x18000a1a3  mov     r9d, [rsp+0A8h+ReturnLength]; TokenInformationLength
0x18000a1a8  lea     rcx, [rsp+0A8h+var_64]
0x18000a1ad  mov     qword ptr [rsp+0A8h+TokenType], rcx; ReturnLength
0x18000a1b2  mov     r8, rax; TokenInformation
0x18000a1b5  mov     rcx, rbp; TokenHandle
0x18000a1b8  mov     edx, 1; TokenInformationClass
0x18000a1bd  call    cs:__imp_GetTokenInformation
0x18000a1c3  test    eax, eax
0x18000a1c5  jz      loc_18000A106
0x18000a1cb  mov     rdx, rbp; void *
0x18000a1ce  mov     rcx, rsi; this
0x18000a1d1  call    ?ResolveUserName@CUserName@@AEAAJPEAX@Z; CUserName::ResolveUserName(void *)
0x18000a1d6  mov     edi, eax
0x18000a1d8  test    eax, eax
0x18000a1da  jns     short loc_18000A1FC
0x18000a1dc  lea     r9, aCusernameIniti; "CUserName::InitializeUserName"
0x18000a1e3  mov     r8d, eax
0x18000a1e6  lea     rdx, aResolveusernam; "ResolveUserName failed: 0x%x in %s"
0x18000a1ed  mov     ecx, 8; int
0x18000a1f2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000a1f7  jmp     loc_18000A081
0x18000a1fc  or      dword ptr [rsi+640h], 2
0x18000a203  jmp     loc_18000A016
```
