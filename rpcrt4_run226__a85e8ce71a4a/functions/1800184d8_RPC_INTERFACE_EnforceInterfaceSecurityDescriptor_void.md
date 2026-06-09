# RPC_INTERFACE::EnforceInterfaceSecurityDescriptor(void *)

- ea: `0x1800184d8`
- end: `0x18001884e`
- name: `?EnforceInterfaceSecurityDescriptor@RPC_INTERFACE@@QEAAJPEAX@Z`
- size: `886`
- prototype: `__int64 __fastcall(RPC_INTERFACE *__hidden this, void *)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001a110`
- `0x18001a4f0`
- `0x18008435c`

## callees

- `0x1800184d8`
- `0x1800283bc`
- `0x18002c13c`
- `0x1800a4610`
- `0x1800ca140`
- `0x1800d2010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18001861f`
- `ntdll!RtlInitUnicodeString` at `0x18001862d`
- `ntdll!RtlInitUnicodeString` at `0x18001861f`
- `ntdll!RtlInitUnicodeString` at `0x18001862d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800186ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800186d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018799`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800187c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800187f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800186ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800186d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018799`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800187c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800187f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018723`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018723`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180018788`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180018788`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180018772`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180018772`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800186a1`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800186a1`

## pseudocode

```c
__int64 __fastcall RPC_INTERFACE::EnforceInterfaceSecurityDescriptor(RPC_INTERFACE *this, void *a2)
{
  PSECURITY_DESCRIPTOR v4; // r13
  int v5; // esi
  int v6; // r15d
  unsigned int v7; // ebx
  int v8; // r12d
  PVOID ArbitraryUserPointer; // r14
  HANDLE AnonymousToken; // rax
  DWORD v11; // eax
  unsigned __int16 v12; // r8
  HANDLE CurrentThread; // rax
  DWORD v15; // eax
  DWORD LastError; // eax
  HANDLE ClientToken; // [rsp+40h] [rbp-C0h] BYREF
  WINBOOL AccessStatus; // [rsp+48h] [rbp-B8h] BYREF
  DWORD GrantedAccess; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD PrivilegeSetLength; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v21; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING *v22; // [rsp+68h] [rbp-98h]
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING v24; // [rsp+80h] [rbp-80h] BYREF
  __int128 v25; // [rsp+90h] [rbp-70h] BYREF
  _GENERIC_MAPPING GenericMapping; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR SourceString[40]; // [rsp+B0h] [rbp-50h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+100h] [rbp+0h] BYREF

  GenericMapping.GenericAll = 2031616;
  GenericMapping.GenericRead = 0x20000;
  GenericMapping.GenericWrite = 0x20000;
  GenericMapping.GenericExecute = 0x20000;
  ClientToken = 0;
  GrantedAccess = 0;
  AccessStatus = 0;
  PrivilegeSetLength = 256;
  v21 = 0;
  v22 = 0;
  DestinationString = 0;
  v24 = 0;
  if ( this == GlobalManagementInterface )
    return 0;
  v4 = (PSECURITY_DESCRIPTOR)*((_QWORD *)this + 70);
  if ( (*(__int64 (__fastcall **)(void *))(*(_QWORD *)a2 + 488LL))(a2) || (v7 = 0, *((_QWORD *)this + 70)) )
  {
    v5 = 1;
    v6 = 1;
    if ( !v4 )
      v4 = gDefaultSecurityDescriptor;
    v7 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)a2 + 328LL))(a2, 2);
    if ( v7 == 1764 )
    {
      v6 = 0;
      v7 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)a2 + 328LL))(a2, 1);
    }
    if ( v7 )
    {
      v8 = 0;
      v7 = 0;
    }
    else
    {
      v5 = 0;
      v8 = 1;
      if ( v6 )
      {
        ClientToken = (HANDLE)-5LL;
        goto LABEL_10;
      }
      CurrentThread = GetCurrentThread();
      if ( OpenThreadToken(CurrentThread, 8u, 1, &ClientToken) )
      {
LABEL_10:
        v25 = *(_OWORD *)((char *)this + 84);
        RPC_UUID::ConvertToString((RPC_UUID *)&v25, SourceString);
        LODWORD(v21) = -1395763957;
        RtlInitUnicodeString(&DestinationString, L"RPC Interface");
        RtlInitUnicodeString(&v24, SourceString);
        *((_QWORD *)&v21 + 1) = &DestinationString;
        v22 = &v24;
        ArbitraryUserPointer = NtCurrentTeb()->NtTib.ArbitraryUserPointer;
        NtCurrentTeb()->NtTib.ArbitraryUserPointer = &v21;
        AnonymousToken = ClientToken;
        while ( !AccessCheck(
                   v4,
                   AnonymousToken,
                   0x2000000u,
                   &GenericMapping,
                   &PrivilegeSet,
                   &PrivilegeSetLength,
                   &GrantedAccess,
                   &AccessStatus) )
        {
          LastError = GetLastError();
          if ( LastError != 1347 || v5 || ClientToken != (HANDLE)-5LL )
          {
            RpcpErrorAddRecord(1u, LastError, 0x52Du, 0, 0);
LABEL_40:
            NtCurrentTeb()->NtTib.ArbitraryUserPointer = ArbitraryUserPointer;
            goto LABEL_17;
          }
          AnonymousToken = GetAnonymousToken();
          ClientToken = AnonymousToken;
          if ( !AnonymousToken )
            goto LABEL_40;
          v5 = 1;
        }
        NtCurrentTeb()->NtTib.ArbitraryUserPointer = ArbitraryUserPointer;
        if ( AccessStatus )
        {
          if ( GrantedAccess )
            goto LABEL_18;
          v11 = GetLastError();
          v12 = 1327;
        }
        else
        {
          v11 = GetLastError();
          v12 = 1326;
        }
        RpcpErrorAddRecord(1u, v11, v12, 0, 0);
LABEL_17:
        v7 = 5;
LABEL_18:
        if ( !v8 )
          goto LABEL_20;
        goto LABEL_19;
      }
      if ( GetLastError() != 1347 )
      {
        v15 = GetLastError();
        RpcpErrorAddRecord(1u, v15, 0x52Cu, 0, 0);
        v7 = 5;
LABEL_19:
        (*(void (__fastcall **)(void *))(*(_QWORD *)a2 + 336LL))(a2);
        goto LABEL_20;
      }
      v5 = 1;
    }
    ClientToken = GetAnonymousToken();
    if ( !ClientToken )
      goto LABEL_17;
    goto LABEL_10;
  }
LABEL_20:
  if ( ClientToken && ClientToken != (HANDLE)-5LL )
    CloseHandle(ClientToken);
  return v7;
}

```

## disassembly

```asm
0x1800184d8  mov     [rsp-8+arg_10], rbx
0x1800184dd  push    rbp
0x1800184de  push    rsi
0x1800184df  push    rdi
0x1800184e0  push    r12
0x1800184e2  push    r13
0x1800184e4  push    r14
0x1800184e6  push    r15
0x1800184e8  lea     rbp, [rsp-110h]
0x1800184f0  sub     rsp, 210h
0x1800184f7  mov     rax, cs:__security_cookie
0x1800184fe  xor     rax, rsp
0x180018501  mov     [rbp+140h+var_40], rax
0x180018508  mov     eax, 20000h
0x18001850d  mov     [rbp+140h+GenericMapping.GenericAll], 1F0000h
0x180018514  xor     r15d, r15d
0x180018517  mov     [rbp+140h+GenericMapping.GenericRead], eax
0x18001851a  xorps   xmm0, xmm0
0x18001851d  mov     [rbp+140h+GenericMapping.GenericWrite], eax
0x180018520  mov     [rbp+140h+GenericMapping.GenericExecute], eax
0x180018523  xorps   xmm1, xmm1
0x180018526  xor     eax, eax
0x180018528  mov     [rsp+240h+ClientToken], r15
0x18001852d  cmp     rcx, cs:?GlobalManagementInterface@@3PEAVRPC_INTERFACE@@EA; RPC_INTERFACE * GlobalManagementInterface
0x180018534  mov     rdi, rdx
0x180018537  mov     r14, rcx
0x18001853a  mov     [rsp+240h+var_1F4], r15d
0x18001853f  mov     [rsp+240h+var_1F8], r15d
0x180018544  mov     [rsp+240h+var_1F0], 100h
0x18001854c  movups  [rsp+240h+var_1E8], xmm0
0x180018551  mov     [rsp+240h+var_1D8], rax
0x180018556  movups  xmmword ptr [rsp+240h+DestinationString.Length], xmm0
0x18001855b  movups  xmmword ptr [rbp+140h+var_1C0.Length], xmm1
0x18001855f  jz      loc_1800187AC
0x180018565  mov     rax, [rdx]
0x180018568  mov     r13, [rcx+230h]
0x18001856f  mov     rcx, rdx
0x180018572  mov     rax, [rax+1E8h]
0x180018579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001857e  test    rax, rax
0x180018581  jz      loc_1800187B4
0x180018587  mov     rax, [rdi]
0x18001858a  mov     esi, 1
0x18001858f  test    r13, r13
0x180018592  mov     rcx, rdi
0x180018595  mov     r15d, esi
0x180018598  cmovz   r13, cs:?gDefaultSecurityDescriptor@@3PEAXEA; void * gDefaultSecurityDescriptor
0x1800185a0  mov     rax, [rax+148h]
0x1800185a7  lea     edx, [rsi+1]
0x1800185aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185af  mov     ebx, eax
0x1800185b1  cmp     eax, 6E4h
0x1800185b6  jnz     short loc_1800185D1
0x1800185b8  mov     rax, [rdi]
0x1800185bb  xor     r15d, r15d
0x1800185be  mov     edx, esi
0x1800185c0  mov     rcx, rdi
0x1800185c3  mov     rax, [rax+148h]
0x1800185ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185cf  mov     ebx, eax
0x1800185d1  test    ebx, ebx
0x1800185d3  jnz     loc_180018755
0x1800185d9  xor     esi, esi
0x1800185db  lea     r12d, [rbx+1]
0x1800185df  test    r15d, r15d
0x1800185e2  jz      loc_180018772
0x1800185e8  mov     [rsp+240h+ClientToken], 0FFFFFFFFFFFFFFFBh
0x1800185f1  xor     r15d, r15d
0x1800185f4  movups  xmm0, xmmword ptr [r14+54h]
0x1800185f9  lea     rdx, [rbp+140h+SourceString]; unsigned __int16 *
0x1800185fd  lea     rcx, [rbp+140h+var_1B0]; this
0x180018601  movdqu  [rbp+140h+var_1B0], xmm0
0x180018606  call    ?ConvertToString@RPC_UUID@@QEAAPEAGPEAG@Z; RPC_UUID::ConvertToString(ushort *)
0x18001860b  lea     rcx, [rsp+240h+DestinationString]; DestinationString
0x180018610  mov     dword ptr [rsp+240h+var_1E8], 0ACCE550Bh
0x180018618  lea     rdx, SourceString; "RPC Interface"
0x18001861f  call    cs:__imp_RtlInitUnicodeString
0x180018625  lea     rdx, [rbp+140h+SourceString]; SourceString
0x180018629  lea     rcx, [rbp+140h+var_1C0]; DestinationString
0x18001862d  call    cs:__imp_RtlInitUnicodeString
0x180018633  lea     rax, [rsp+240h+DestinationString]
0x180018638  mov     qword ptr [rsp+240h+var_1E8+8], rax
0x18001863d  lea     rcx, [rsp+240h+var_1E8]
0x180018642  lea     rax, [rbp+140h+var_1C0]
0x180018646  mov     [rsp+240h+var_1D8], rax
0x18001864b  mov     rax, gs:30h
0x180018654  mov     r14, [rax+28h]
0x180018658  mov     rax, gs:30h
0x180018661  mov     [rax+28h], rcx
0x180018665  mov     rax, [rsp+240h+ClientToken]
0x18001866a  lea     rcx, [rsp+240h+var_1F8]
0x18001866f  mov     r8d, 2000000h; DesiredAccess
0x180018675  mov     [rsp+240h+AccessStatus], rcx; AccessStatus
0x18001867a  lea     r9, [rbp+140h+GenericMapping]; GenericMapping
0x18001867e  lea     rcx, [rsp+240h+var_1F4]
0x180018683  mov     rdx, rax; ClientToken
0x180018686  mov     [rsp+240h+GrantedAccess], rcx; GrantedAccess
0x18001868b  lea     rcx, [rsp+240h+var_1F0]
0x180018690  mov     [rsp+240h+PrivilegeSetLength], rcx; PrivilegeSetLength
0x180018695  lea     rcx, [rbp+140h+var_140]
0x180018699  mov     [rsp+240h+PrivilegeSet], rcx; PrivilegeSet
0x18001869e  mov     rcx, r13; pSecurityDescriptor
0x1800186a1  call    cs:__imp_AccessCheck
0x1800186a7  test    eax, eax
0x1800186a9  jz      loc_1800187F1
0x1800186af  mov     rax, gs:30h
0x1800186b8  mov     [rax+28h], r14
0x1800186bc  cmp     [rsp+240h+var_1F8], r15d
0x1800186c1  jz      short loc_1800186D8
0x1800186c3  cmp     [rsp+240h+var_1F4], r15d
0x1800186c8  jnz     short loc_1800186FC
0x1800186ca  call    cs:__imp_GetLastError
0x1800186d0  mov     r8d, 52Fh
0x1800186d6  jmp     short loc_1800186E4
0x1800186d8  call    cs:__imp_GetLastError
0x1800186de  mov     r8d, 52Eh; unsigned __int16
0x1800186e4  xor     r9d, r9d; int
0x1800186e7  mov     [rsp+240h+PrivilegeSet], r15; struct tagParam *
0x1800186ec  mov     edx, eax; int
0x1800186ee  lea     ecx, [r9+1]; unsigned int
0x1800186f2  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x1800186f7  mov     ebx, 5
0x1800186fc  test    r12d, r12d
0x1800186ff  jz      short loc_180018713
0x180018701  mov     rax, [rdi]
0x180018704  mov     rcx, rdi
0x180018707  mov     rax, [rax+150h]
0x18001870e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018713  mov     rcx, [rsp+240h+ClientToken]; hObject
0x180018718  test    rcx, rcx
0x18001871b  jz      short loc_180018729
0x18001871d  cmp     rcx, 0FFFFFFFFFFFFFFFBh
0x180018721  jz      short loc_180018729
0x180018723  call    cs:__imp_CloseHandle
0x180018729  mov     eax, ebx
0x18001872b  mov     rcx, [rbp+140h+var_40]
0x180018732  xor     rcx, rsp; StackCookie
0x180018735  call    __security_check_cookie
0x18001873a  mov     rbx, [rsp+240h+arg_10]
0x180018742  add     rsp, 210h
0x180018749  pop     r15
0x18001874b  pop     r14
0x18001874d  pop     r13
0x18001874f  pop     r12
0x180018751  pop     rdi
0x180018752  pop     rsi
0x180018753  pop     rbp
0x180018754  retn
0x180018755  xor     r15d, r15d
0x180018758  mov     r12d, r15d
0x18001875b  mov     ebx, r15d
0x18001875e  call    ?GetAnonymousToken@@YAPEAXXZ; GetAnonymousToken(void)
0x180018763  mov     [rsp+240h+ClientToken], rax
0x180018768  test    rax, rax
0x18001876b  jz      short loc_1800186F7
0x18001876d  jmp     loc_1800185F4
0x180018772  call    cs:__imp_GetCurrentThread
0x180018778  lea     r9, [rsp+240h+ClientToken]; TokenHandle
0x18001877d  mov     edx, 8; DesiredAccess
0x180018782  mov     rcx, rax; ThreadHandle
0x180018785  mov     r8d, r12d; OpenAsSelf
0x180018788  call    cs:__imp_OpenThreadToken
0x18001878e  xor     r15d, r15d
0x180018791  test    eax, eax
0x180018793  jnz     loc_1800185F4
0x180018799  call    cs:__imp_GetLastError
0x18001879f  cmp     eax, 543h
0x1800187a4  jnz     short loc_1800187C9
0x1800187a6  lea     esi, [r15+1]
0x1800187aa  jmp     short loc_18001875E
0x1800187ac  mov     ebx, r15d
0x1800187af  jmp     loc_180018729
0x1800187b4  mov     ebx, r15d
0x1800187b7  cmp     [r14+230h], r15
0x1800187be  jz      loc_180018713
0x1800187c4  jmp     loc_180018587
0x1800187c9  call    cs:__imp_GetLastError
0x1800187cf  mov     r8d, 52Ch; unsigned __int16
0x1800187d5  mov     [rsp+240h+PrivilegeSet], r15; struct tagParam *
0x1800187da  mov     edx, eax; int
0x1800187dc  xor     r9d, r9d; int
0x1800187df  mov     ecx, r12d; unsigned int
0x1800187e2  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x1800187e7  mov     ebx, 5
0x1800187ec  jmp     loc_180018701
0x1800187f1  call    cs:__imp_GetLastError
0x1800187f7  cmp     eax, 543h
0x1800187fc  jnz     short loc_180018823
0x1800187fe  test    esi, esi
0x180018800  jnz     short loc_180018823
0x180018802  cmp     [rsp+240h+ClientToken], 0FFFFFFFFFFFFFFFBh
0x180018808  jnz     short loc_180018823
0x18001880a  call    ?GetAnonymousToken@@YAPEAXXZ; GetAnonymousToken(void)
0x18001880f  mov     [rsp+240h+ClientToken], rax
0x180018814  test    rax, rax
0x180018817  jz      short loc_18001883C
0x180018819  mov     esi, 1
0x18001881e  jmp     loc_18001866A
0x180018823  xor     r9d, r9d; int
0x180018826  mov     [rsp+240h+PrivilegeSet], r15; struct tagParam *
0x18001882b  mov     r8d, 52Dh; unsigned __int16
0x180018831  mov     edx, eax; int
0x180018833  lea     ecx, [r9+1]; unsigned int
0x180018837  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x18001883c  mov     rax, gs:30h
0x180018845  mov     [rax+28h], r14
0x180018849  jmp     loc_1800186F7
```
