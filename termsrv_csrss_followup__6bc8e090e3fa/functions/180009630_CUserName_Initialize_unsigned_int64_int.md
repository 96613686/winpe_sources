# CUserName::Initialize(unsigned __int64,int)

- ea: `0x180009630`
- end: `0x18000992b`
- name: `?Initialize@CUserName@@UEAAJ_KH@Z`
- size: `763`
- prototype: `__int64 __fastcall(CUserName *__hidden this, void *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800500a0`

## callees

- `0x180009630`
- `0x180009940`
- `0x18002aa3c`
- `0x180033f60`
- `0x18003444c`

## import_xrefs

- `ntdll!NtDuplicateToken` at `0x1800096c3`
- `ntdll!NtDuplicateToken` at `0x1800096c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009796`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800097cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009805`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009885`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009796`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800097cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009805`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009885`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180009829`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180009838`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180009829`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180009838`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800096e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800096e9`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180009860`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180009860`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000974a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800098da`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000974a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800098da`

## string_xrefs

- `0x18000975e`: `Can get the TOKEN_USER length`
- `0x1800097b1`: `Can get the TOKEN_USER length: 0x%x`
- `0x180009820`: `GetTokenInformatino failed: 0x%x`
- `0x180009879`: `NtDuplicateToken failed: 0x%x in %s`

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
0x180009630  mov     r11, rsp
0x180009633  mov     [r11+18h], rbx
0x180009637  mov     [r11+20h], rbp
0x18000963b  push    rsi
0x18000963c  push    rdi
0x18000963d  push    r14
0x18000963f  sub     rsp, 90h
0x180009646  mov     rax, cs:__security_cookie
0x18000964d  xor     rax, rsp
0x180009650  mov     [rsp+0A8h+var_20], rax
0x180009658  xor     ebx, ebx
0x18000965a  xor     r9d, r9d; TokenInformationLength
0x18000965d  mov     rbp, rdx
0x180009660  mov     rsi, rcx
0x180009663  test    r8d, r8d
0x180009666  jz      loc_18000972D
0x18000966c  lea     r14, [rcx+638h]
0x180009673  mov     dword ptr [r11-28h], 1
0x18000967b  lea     rax, [r11-30h]
0x18000967f  mov     [r11-80h], r14
0x180009683  lea     r8, [r11-60h]; ObjectAttributes
0x180009687  mov     [rsp+0A8h+TokenType], 1; TokenType
0x18000968f  mov     edx, 2000000h; DesiredAccess
0x180009694  mov     qword ptr [r11-60h], 30h ; '0'
0x18000969c  mov     rcx, rbp; ExistingTokenHandle
0x18000969f  mov     [r11-48h], rbx
0x1800096a3  mov     [r11-58h], rbx
0x1800096a7  mov     [r11-50h], rbx
0x1800096ab  mov     [r11-40h], rbx
0x1800096af  mov     [rsp+0A8h+var_30], 0Ch
0x1800096b7  mov     [rsp+0A8h+var_2C], 2
0x1800096bf  mov     [r11-38h], rax
0x1800096c3  call    cs:__imp_NtDuplicateToken
0x1800096ca  nop     dword ptr [rax+rax+00h]
0x1800096cf  mov     edi, eax
0x1800096d1  bts     edi, 1Ch
0x1800096d5  cmp     edi, 0D0000022h
0x1800096db  jz      loc_180009829
0x1800096e1  test    edi, edi
0x1800096e3  js      loc_180009879
0x1800096e9  call    cs:__imp_GetCurrentProcessId
0x1800096f0  nop     dword ptr [rax+rax+00h]
0x1800096f5  or      dword ptr [rsi+640h], 1
0x1800096fc  mov     [rsi+0A80h], eax
0x180009702  mov     eax, ebx
0x180009704  mov     rcx, [rsp+0A8h+var_20]
0x18000970c  xor     rcx, rsp; StackCookie
0x18000970f  call    __security_check_cookie
0x180009714  lea     r11, [rsp+0A8h+var_18]
0x18000971c  mov     rbx, [r11+30h]
0x180009720  mov     rbp, [r11+38h]
0x180009724  mov     rsp, r11
0x180009727  pop     r14
0x180009729  pop     rdi
0x18000972a  pop     rsi
0x18000972b  retn
0x18000972d  lea     rax, [rsp+0A8h+ReturnLength]
0x180009732  mov     [rsp+0A8h+ReturnLength], ebx
0x180009736  xor     r8d, r8d; TokenInformation
0x180009739  mov     qword ptr [rsp+0A8h+TokenType], rax; ReturnLength
0x18000973e  mov     edx, 1; TokenInformationClass
0x180009743  mov     [rsp+0A8h+var_64], ebx
0x180009747  mov     rcx, rbp; TokenHandle
0x18000974a  call    cs:__imp_GetTokenInformation
0x180009751  nop     dword ptr [rax+rax+00h]
0x180009756  test    eax, eax
0x180009758  jz      loc_180009885
0x18000975e  lea     rdx, aCanGetTheToken; "Can get the TOKEN_USER length"
0x180009765  mov     ecx, 8; int
0x18000976a  mov     edi, 80070057h
0x18000976f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180009774  lea     rdx, aInitializeuser; "InitializeUserName failed: 0x%x in %s"
0x18000977b  lea     r9, aCusernameIniti_1; "CUserName::Initialize"
0x180009782  mov     r8d, edi
0x180009785  mov     ecx, 8; int
0x18000978a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000978f  mov     eax, edi
0x180009791  jmp     loc_180009704
0x180009796  call    cs:__imp_GetLastError
0x18000979d  nop     dword ptr [rax+rax+00h]
0x1800097a2  mov     edi, eax
0x1800097a4  test    eax, eax
0x1800097a6  jle     short loc_1800097B1
0x1800097a8  movzx   edi, ax
0x1800097ab  or      edi, 80070000h
0x1800097b1  lea     rdx, aCanGetTheToken_0; "Can get the TOKEN_USER length: 0x%x"
0x1800097b8  mov     r8d, edi
0x1800097bb  mov     ecx, 8; int
0x1800097c0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800097c5  test    edi, edi
0x1800097c7  jns     loc_180009702
0x1800097cd  jmp     short loc_180009774
0x1800097cf  call    cs:__imp_GetLastError
0x1800097d6  nop     dword ptr [rax+rax+00h]
0x1800097db  mov     ebx, eax
0x1800097dd  test    eax, eax
0x1800097df  jle     short loc_1800097EA
0x1800097e1  movzx   ebx, ax
0x1800097e4  or      ebx, 80070000h
0x1800097ea  mov     r8d, ebx
0x1800097ed  lea     rdx, aDuplicatehandl_1; "DuplicateHandle failed: 0x%x"
0x1800097f4  mov     ecx, 8; int
0x1800097f9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800097fe  mov     eax, ebx
0x180009800  jmp     loc_180009704
0x180009805  call    cs:__imp_GetLastError
0x18000980c  nop     dword ptr [rax+rax+00h]
0x180009811  mov     edi, eax
0x180009813  test    eax, eax
0x180009815  jle     short loc_180009820
0x180009817  movzx   edi, ax
0x18000981a  or      edi, 80070000h
0x180009820  lea     rdx, aGettokeninform_0; "GetTokenInformatino failed: 0x%x"
0x180009827  jmp     short loc_1800097B8
0x180009829  call    cs:__imp_GetCurrentProcess
0x180009830  nop     dword ptr [rax+rax+00h]
0x180009835  mov     rdi, rax
0x180009838  call    cs:__imp_GetCurrentProcess
0x18000983f  nop     dword ptr [rax+rax+00h]
0x180009844  mov     [rsp+0A8h+dwOptions], 2; dwOptions
0x18000984c  mov     r9, r14; lpTargetHandle
0x18000984f  mov     rcx, rax; hSourceProcessHandle
0x180009852  mov     [rsp+0A8h+bInheritHandle], ebx; bInheritHandle
0x180009856  mov     r8, rdi; hTargetProcessHandle
0x180009859  mov     [rsp+0A8h+TokenType], ebx; dwDesiredAccess
0x18000985d  mov     rdx, rbp; hSourceHandle
0x180009860  call    cs:__imp_DuplicateHandle
0x180009867  nop     dword ptr [rax+rax+00h]
0x18000986c  test    eax, eax
0x18000986e  jnz     loc_1800096E9
0x180009874  jmp     loc_1800097CF
0x180009879  lea     rdx, aNtduplicatetok; "NtDuplicateToken failed: 0x%x in %s"
0x180009880  jmp     loc_18000977B
0x180009885  call    cs:__imp_GetLastError
0x18000988c  nop     dword ptr [rax+rax+00h]
0x180009891  cmp     eax, 7Ah ; 'z'
0x180009894  jnz     loc_180009796
0x18000989a  mov     ecx, [rsp+0A8h+ReturnLength]; unsigned __int64
0x18000989e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800098a5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800098aa  mov     [rsi+648h], rax
0x1800098b1  test    rax, rax
0x1800098b4  jnz     short loc_1800098C0
0x1800098b6  mov     edi, 8007000Eh
0x1800098bb  jmp     loc_180009774
0x1800098c0  mov     r9d, [rsp+0A8h+ReturnLength]; TokenInformationLength
0x1800098c5  lea     rcx, [rsp+0A8h+var_64]
0x1800098ca  mov     qword ptr [rsp+0A8h+TokenType], rcx; ReturnLength
0x1800098cf  mov     r8, rax; TokenInformation
0x1800098d2  mov     rcx, rbp; TokenHandle
0x1800098d5  mov     edx, 1; TokenInformationClass
0x1800098da  call    cs:__imp_GetTokenInformation
0x1800098e1  nop     dword ptr [rax+rax+00h]
0x1800098e6  test    eax, eax
0x1800098e8  jz      loc_180009805
0x1800098ee  mov     rdx, rbp; void *
0x1800098f1  mov     rcx, rsi; this
0x1800098f4  call    ?ResolveUserName@CUserName@@AEAAJPEAX@Z; CUserName::ResolveUserName(void *)
0x1800098f9  mov     edi, eax
0x1800098fb  test    eax, eax
0x1800098fd  jns     short loc_18000991F
0x1800098ff  lea     r9, aCusernameIniti; "CUserName::InitializeUserName"
0x180009906  mov     r8d, eax
0x180009909  lea     rdx, aResolveusernam; "ResolveUserName failed: 0x%x in %s"
0x180009910  mov     ecx, 8; int
0x180009915  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000991a  jmp     loc_180009774
0x18000991f  or      dword ptr [rsi+640h], 2
0x180009926  jmp     loc_180009702
```
