# RPC_INTERFACE::EnforceInterfaceSecurityDescriptor(void *)

- ea: `0x180085260`
- end: `0x180085619`
- name: `?EnforceInterfaceSecurityDescriptor@RPC_INTERFACE@@QEAAJPEAX@Z`
- size: `953`
- prototype: `__int64 __fastcall(RPC_INTERFACE *__hidden this, void *)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001b0e0`
- `0x18001b4d0`
- `0x180085138`

## callees

- `0x1800295d8`
- `0x18002d45c`
- `0x180085260`
- `0x1800a7aec`
- `0x1800ceda0`
- `0x1800d7010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800853a7`
- `ntdll!RtlInitUnicodeString` at `0x1800853bb`
- `ntdll!RtlInitUnicodeString` at `0x1800853a7`
- `ntdll!RtlInitUnicodeString` at `0x1800853bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085464`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085478`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085552`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085588`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800855b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085464`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085478`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085552`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085588`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800855b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800854c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800854c9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18008553b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18008553b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008551f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008551f`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180085435`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180085435`

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
  struct _GENERIC_MAPPING GenericMapping; // [rsp+A0h] [rbp-60h] BYREF
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
0x180085260  mov     [rsp-8+arg_10], rbx
0x180085265  push    rbp
0x180085266  push    rsi
0x180085267  push    rdi
0x180085268  push    r12
0x18008526a  push    r13
0x18008526c  push    r14
0x18008526e  push    r15
0x180085270  lea     rbp, [rsp-110h]
0x180085278  sub     rsp, 210h
0x18008527f  mov     rax, cs:__security_cookie
0x180085286  xor     rax, rsp
0x180085289  mov     [rbp+140h+var_40], rax
0x180085290  mov     eax, 20000h
0x180085295  mov     [rbp+140h+GenericMapping.GenericAll], 1F0000h
0x18008529c  xor     r15d, r15d
0x18008529f  mov     [rbp+140h+GenericMapping.GenericRead], eax
0x1800852a2  xorps   xmm0, xmm0
0x1800852a5  mov     [rbp+140h+GenericMapping.GenericWrite], eax
0x1800852a8  mov     [rbp+140h+GenericMapping.GenericExecute], eax
0x1800852ab  xorps   xmm1, xmm1
0x1800852ae  xor     eax, eax
0x1800852b0  mov     [rsp+240h+ClientToken], r15
0x1800852b5  cmp     rcx, cs:?GlobalManagementInterface@@3PEAVRPC_INTERFACE@@EA; RPC_INTERFACE * GlobalManagementInterface
0x1800852bc  mov     rdi, rdx
0x1800852bf  mov     r14, rcx
0x1800852c2  mov     [rsp+240h+var_1F4], r15d
0x1800852c7  mov     [rsp+240h+var_1F8], r15d
0x1800852cc  mov     [rsp+240h+var_1F0], 100h
0x1800852d4  movups  [rsp+240h+var_1E8], xmm0
0x1800852d9  mov     [rsp+240h+var_1D8], rax
0x1800852de  movups  xmmword ptr [rsp+240h+DestinationString.Length], xmm0
0x1800852e3  movups  xmmword ptr [rbp+140h+var_1C0.Length], xmm1
0x1800852e7  jz      loc_18008556B
0x1800852ed  mov     rax, [rdx]
0x1800852f0  mov     r13, [rcx+230h]
0x1800852f7  mov     rcx, rdx
0x1800852fa  mov     rax, [rax+1E8h]
0x180085301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085306  test    rax, rax
0x180085309  jz      loc_180085573
0x18008530f  mov     rax, [rdi]
0x180085312  mov     esi, 1
0x180085317  test    r13, r13
0x18008531a  mov     rcx, rdi
0x18008531d  mov     r15d, esi
0x180085320  cmovz   r13, cs:?gDefaultSecurityDescriptor@@3PEAXEA; void * gDefaultSecurityDescriptor
0x180085328  mov     rax, [rax+148h]
0x18008532f  lea     edx, [rsi+1]
0x180085332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085337  mov     ebx, eax
0x180085339  cmp     eax, 6E4h
0x18008533e  jnz     short loc_180085359
0x180085340  mov     rax, [rdi]
0x180085343  xor     r15d, r15d
0x180085346  mov     edx, esi
0x180085348  mov     rcx, rdi
0x18008534b  mov     rax, [rax+148h]
0x180085352  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085357  mov     ebx, eax
0x180085359  test    ebx, ebx
0x18008535b  jnz     loc_180085502
0x180085361  xor     esi, esi
0x180085363  lea     r12d, [rbx+1]
0x180085367  test    r15d, r15d
0x18008536a  jz      loc_18008551F
0x180085370  mov     [rsp+240h+ClientToken], 0FFFFFFFFFFFFFFFBh
0x180085379  xor     r15d, r15d
0x18008537c  movups  xmm0, xmmword ptr [r14+54h]
0x180085381  lea     rdx, [rbp+140h+SourceString]; unsigned __int16 *
0x180085385  lea     rcx, [rbp+140h+var_1B0]; this
0x180085389  movdqu  [rbp+140h+var_1B0], xmm0
0x18008538e  call    ?ConvertToString@RPC_UUID@@QEAAPEAGPEAG@Z; RPC_UUID::ConvertToString(ushort *)
0x180085393  lea     rcx, [rsp+240h+DestinationString]; DestinationString
0x180085398  mov     dword ptr [rsp+240h+var_1E8], 0ACCE550Bh
0x1800853a0  lea     rdx, SourceString; "RPC Interface"
0x1800853a7  call    cs:__imp_RtlInitUnicodeString
0x1800853ae  nop     dword ptr [rax+rax+00h]
0x1800853b3  lea     rdx, [rbp+140h+SourceString]; SourceString
0x1800853b7  lea     rcx, [rbp+140h+var_1C0]; DestinationString
0x1800853bb  call    cs:__imp_RtlInitUnicodeString
0x1800853c2  nop     dword ptr [rax+rax+00h]
0x1800853c7  lea     rax, [rsp+240h+DestinationString]
0x1800853cc  mov     qword ptr [rsp+240h+var_1E8+8], rax
0x1800853d1  lea     rcx, [rsp+240h+var_1E8]
0x1800853d6  lea     rax, [rbp+140h+var_1C0]
0x1800853da  mov     [rsp+240h+var_1D8], rax
0x1800853df  mov     rax, gs:30h
0x1800853e8  mov     r14, [rax+28h]
0x1800853ec  mov     rax, gs:30h
0x1800853f5  mov     [rax+28h], rcx
0x1800853f9  mov     rax, [rsp+240h+ClientToken]
0x1800853fe  lea     rcx, [rsp+240h+var_1F8]
0x180085403  mov     r8d, 2000000h; DesiredAccess
0x180085409  mov     [rsp+240h+AccessStatus], rcx; AccessStatus
0x18008540e  lea     r9, [rbp+140h+GenericMapping]; GenericMapping
0x180085412  lea     rcx, [rsp+240h+var_1F4]
0x180085417  mov     rdx, rax; ClientToken
0x18008541a  mov     [rsp+240h+GrantedAccess], rcx; GrantedAccess
0x18008541f  lea     rcx, [rsp+240h+var_1F0]
0x180085424  mov     [rsp+240h+PrivilegeSetLength], rcx; PrivilegeSetLength
0x180085429  lea     rcx, [rbp+140h+var_140]
0x18008542d  mov     [rsp+240h+PrivilegeSet], rcx; PrivilegeSet
0x180085432  mov     rcx, r13; pSecurityDescriptor
0x180085435  call    cs:__imp_AccessCheck
0x18008543c  nop     dword ptr [rax+rax+00h]
0x180085441  test    eax, eax
0x180085443  jz      loc_1800855B6
0x180085449  mov     rax, gs:30h
0x180085452  mov     [rax+28h], r14
0x180085456  cmp     [rsp+240h+var_1F8], r15d
0x18008545b  jz      short loc_180085478
0x18008545d  cmp     [rsp+240h+var_1F4], r15d
0x180085462  jnz     short loc_1800854A2
0x180085464  call    cs:__imp_GetLastError
0x18008546b  nop     dword ptr [rax+rax+00h]
0x180085470  mov     r8d, 52Fh
0x180085476  jmp     short loc_18008548A
0x180085478  call    cs:__imp_GetLastError
0x18008547f  nop     dword ptr [rax+rax+00h]
0x180085484  mov     r8d, 52Eh; unsigned __int16
0x18008548a  xor     r9d, r9d; int
0x18008548d  mov     [rsp+240h+PrivilegeSet], r15; struct tagParam *
0x180085492  mov     edx, eax; int
0x180085494  lea     ecx, [r9+1]; unsigned int
0x180085498  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x18008549d  mov     ebx, 5
0x1800854a2  test    r12d, r12d
0x1800854a5  jz      short loc_1800854B9
0x1800854a7  mov     rax, [rdi]
0x1800854aa  mov     rcx, rdi
0x1800854ad  mov     rax, [rax+150h]
0x1800854b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800854b9  mov     rcx, [rsp+240h+ClientToken]; hObject
0x1800854be  test    rcx, rcx
0x1800854c1  jz      short loc_1800854D5
0x1800854c3  cmp     rcx, 0FFFFFFFFFFFFFFFBh
0x1800854c7  jz      short loc_1800854D5
0x1800854c9  call    cs:__imp_CloseHandle
0x1800854d0  nop     dword ptr [rax+rax+00h]
0x1800854d5  mov     eax, ebx
0x1800854d7  mov     rcx, [rbp+140h+var_40]
0x1800854de  xor     rcx, rsp; StackCookie
0x1800854e1  call    __security_check_cookie
0x1800854e6  mov     rbx, [rsp+240h+arg_10]
0x1800854ee  add     rsp, 210h
0x1800854f5  pop     r15
0x1800854f7  pop     r14
0x1800854f9  pop     r13
0x1800854fb  pop     r12
0x1800854fd  pop     rdi
0x1800854fe  pop     rsi
0x1800854ff  pop     rbp
0x180085500  retn
0x180085502  xor     r15d, r15d
0x180085505  mov     r12d, r15d
0x180085508  mov     ebx, r15d
0x18008550b  call    ?GetAnonymousToken@@YAPEAXXZ; GetAnonymousToken(void)
0x180085510  mov     [rsp+240h+ClientToken], rax
0x180085515  test    rax, rax
0x180085518  jz      short loc_18008549D
0x18008551a  jmp     loc_18008537C
0x18008551f  call    cs:__imp_GetCurrentThread
0x180085526  nop     dword ptr [rax+rax+00h]
0x18008552b  lea     r9, [rsp+240h+ClientToken]; TokenHandle
0x180085530  mov     edx, 8; DesiredAccess
0x180085535  mov     rcx, rax; ThreadHandle
0x180085538  mov     r8d, r12d; OpenAsSelf
0x18008553b  call    cs:__imp_OpenThreadToken
0x180085542  nop     dword ptr [rax+rax+00h]
0x180085547  xor     r15d, r15d
0x18008554a  test    eax, eax
0x18008554c  jnz     loc_18008537C
0x180085552  call    cs:__imp_GetLastError
0x180085559  nop     dword ptr [rax+rax+00h]
0x18008555e  cmp     eax, 543h
0x180085563  jnz     short loc_180085588
0x180085565  lea     esi, [r15+1]
0x180085569  jmp     short loc_18008550B
0x18008556b  mov     ebx, r15d
0x18008556e  jmp     loc_1800854D5
0x180085573  mov     ebx, r15d
0x180085576  cmp     [r14+230h], r15
0x18008557d  jz      loc_1800854B9
0x180085583  jmp     loc_18008530F
0x180085588  call    cs:__imp_GetLastError
0x18008558f  nop     dword ptr [rax+rax+00h]
0x180085594  mov     r8d, 52Ch; unsigned __int16
0x18008559a  mov     [rsp+240h+PrivilegeSet], r15; struct tagParam *
0x18008559f  mov     edx, eax; int
0x1800855a1  xor     r9d, r9d; int
0x1800855a4  mov     ecx, r12d; unsigned int
0x1800855a7  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x1800855ac  mov     ebx, 5
0x1800855b1  jmp     loc_1800854A7
0x1800855b6  call    cs:__imp_GetLastError
0x1800855bd  nop     dword ptr [rax+rax+00h]
0x1800855c2  cmp     eax, 543h
0x1800855c7  jnz     short loc_1800855EE
0x1800855c9  test    esi, esi
0x1800855cb  jnz     short loc_1800855EE
0x1800855cd  cmp     [rsp+240h+ClientToken], 0FFFFFFFFFFFFFFFBh
0x1800855d3  jnz     short loc_1800855EE
0x1800855d5  call    ?GetAnonymousToken@@YAPEAXXZ; GetAnonymousToken(void)
0x1800855da  mov     [rsp+240h+ClientToken], rax
0x1800855df  test    rax, rax
0x1800855e2  jz      short loc_180085607
0x1800855e4  mov     esi, 1
0x1800855e9  jmp     loc_1800853FE
0x1800855ee  xor     r9d, r9d; int
0x1800855f1  mov     [rsp+240h+PrivilegeSet], r15; struct tagParam *
0x1800855f6  mov     r8d, 52Dh; unsigned __int16
0x1800855fc  mov     edx, eax; int
0x1800855fe  lea     ecx, [r9+1]; unsigned int
0x180085602  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x180085607  mov     rax, gs:30h
0x180085610  mov     [rax+28h], r14
0x180085614  jmp     loc_18008549D
```
