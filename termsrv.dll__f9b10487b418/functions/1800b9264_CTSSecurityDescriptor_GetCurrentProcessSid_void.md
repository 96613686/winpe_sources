# CTSSecurityDescriptor::GetCurrentProcessSid(void * *)

- ea: `0x1800b9264`
- end: `0x1800b936a`
- name: `?GetCurrentProcessSid@CTSSecurityDescriptor@@IEAAJPEAPEAX@Z`
- size: `262`
- prototype: `__int64 __fastcall(CTSSecurityDescriptor *__hidden this, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800163e0`

## callees

- `0x180008b40`
- `0x18000a210`
- `0x180013150`
- `0x1800148d0`
- `0x1800b9264`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b92a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b92a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b928b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b928b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800b929e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800b929e`

## string_xrefs

- `0x1800b92c4`: `OpenProcessToken failed: 0x%x in %s`
- `0x1800b9333`: `CTSSecurityDescriptor::GetCurrentProcessSid`
- `0x1800b9329`: `IUserName->GetUserSid failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CTSSecurityDescriptor::GetCurrentProcessSid(CTSSecurityDescriptor *this, void **a2)
{
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  unsigned int v5; // ebx
  int InstanceOfUserName; // eax
  const char *v7; // rdx
  struct IUserName *v8; // rdi
  struct IUserName *v10; // [rsp+30h] [rbp+8h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp+18h] BYREF

  TokenHandle = 0;
  v10 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0xEu, &TokenHandle) )
    goto LABEL_6;
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  if ( (v5 & 0x80000000) == 0 )
  {
LABEL_6:
    InstanceOfUserName = CUtils::GetInstanceOfUserName(&v10);
    v5 = InstanceOfUserName;
    if ( InstanceOfUserName >= 0 )
    {
      v8 = v10;
      InstanceOfUserName = (*(__int64 (__fastcall **)(struct IUserName *, void *, _QWORD))(*(_QWORD *)v10 + 24LL))(
                             v10,
                             TokenHandle,
                             0);
      v5 = InstanceOfUserName;
      if ( InstanceOfUserName >= 0 )
      {
        InstanceOfUserName = (*(__int64 (__fastcall **)(struct IUserName *, void **))(*(_QWORD *)v8 + 72LL))(v8, a2);
        v5 = InstanceOfUserName;
        if ( InstanceOfUserName >= 0 )
          goto LABEL_13;
        v7 = "IUserName->GetUserSid failed: 0x%x in %s";
      }
      else
      {
        v7 = "IUserName->Initialize failed: 0x%x in %s";
      }
    }
    else
    {
      v7 = "GetInstanceOfUserName failed: 0x%x in %s";
    }
    _DbgPrintMessage(8, v7, (unsigned int)InstanceOfUserName, "CTSSecurityDescriptor::GetCurrentProcessSid");
    goto LABEL_13;
  }
  _DbgPrintMessage(8, "OpenProcessToken failed: 0x%x in %s", v5, "CTSSecurityDescriptor::GetCurrentProcessSid");
LABEL_13:
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((__int64 *)&v10);
  SmartHANDLE::~SmartHANDLE((SmartHANDLE *)&TokenHandle);
  return v5;
}

```

## disassembly

```asm
0x1800b9264  mov     rax, rsp
0x1800b9267  mov     [rax+10h], rbx
0x1800b926b  mov     [rax+20h], rsi
0x1800b926f  mov     [rax+8], rcx
0x1800b9273  push    rdi
0x1800b9274  sub     rsp, 20h
0x1800b9278  mov     rsi, rdx
0x1800b927b  mov     qword ptr [rax+18h], 0
0x1800b9283  mov     qword ptr [rax+8], 0
0x1800b928b  call    cs:__imp_GetCurrentProcess
0x1800b9291  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x1800b9296  mov     edx, 0Eh; DesiredAccess
0x1800b929b  mov     rcx, rax; ProcessHandle
0x1800b929e  call    cs:__imp_OpenProcessToken
0x1800b92a4  test    eax, eax
0x1800b92a6  jnz     short loc_1800B92CD
0x1800b92a8  call    cs:__imp_GetLastError
0x1800b92ae  mov     ebx, eax
0x1800b92b0  test    eax, eax
0x1800b92b2  jle     short loc_1800B92BD
0x1800b92b4  movzx   ebx, ax
0x1800b92b7  or      ebx, 80070000h
0x1800b92bd  test    ebx, ebx
0x1800b92bf  jns     short loc_1800B92CD
0x1800b92c1  mov     r8d, ebx
0x1800b92c4  lea     rdx, aOpenprocesstok; "OpenProcessToken failed: 0x%x in %s"
0x1800b92cb  jmp     short loc_1800B9333
0x1800b92cd  lea     rcx, [rsp+28h+arg_0]; struct IUserName **
0x1800b92d2  call    ?GetInstanceOfUserName@CUtils@@SAJPEAPEAUIUserName@@@Z; CUtils::GetInstanceOfUserName(IUserName * *)
0x1800b92d7  mov     ebx, eax
0x1800b92d9  test    eax, eax
0x1800b92db  jns     short loc_1800B92E6
0x1800b92dd  lea     rdx, aGetinstanceofu; "GetInstanceOfUserName failed: 0x%x in %"...
0x1800b92e4  jmp     short loc_1800B9330
0x1800b92e6  mov     rdi, [rsp+28h+arg_0]
0x1800b92eb  xor     r8d, r8d
0x1800b92ee  mov     rdx, [rsp+28h+TokenHandle]
0x1800b92f3  mov     rcx, rdi
0x1800b92f6  mov     rax, [rdi]
0x1800b92f9  mov     rax, [rax+18h]
0x1800b92fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9302  mov     ebx, eax
0x1800b9304  test    eax, eax
0x1800b9306  jns     short loc_1800B9311
0x1800b9308  lea     rdx, aIusernameIniti; "IUserName->Initialize failed: 0x%x in %"...
0x1800b930f  jmp     short loc_1800B9330
0x1800b9311  mov     rax, [rdi]
0x1800b9314  mov     rdx, rsi
0x1800b9317  mov     rcx, rdi
0x1800b931a  mov     rax, [rax+48h]
0x1800b931e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9323  mov     ebx, eax
0x1800b9325  test    eax, eax
0x1800b9327  jns     short loc_1800B9344
0x1800b9329  lea     rdx, aIusernameGetus_0; "IUserName->GetUserSid failed: 0x%x in %"...
0x1800b9330  mov     r8d, eax
0x1800b9333  lea     r9, aCtssecuritydes_1; "CTSSecurityDescriptor::GetCurrentProces"...
0x1800b933a  mov     ecx, 8; int
0x1800b933f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800b9344  lea     rcx, [rsp+28h+arg_0]; void *
0x1800b9349  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800b934e  lea     rcx, [rsp+28h+TokenHandle]; this
0x1800b9353  call    ??1SmartHANDLE@@QEAA@XZ; SmartHANDLE::~SmartHANDLE(void)
0x1800b9358  mov     rsi, [rsp+28h+arg_18]
0x1800b935d  mov     eax, ebx
0x1800b935f  mov     rbx, [rsp+28h+arg_8]
0x1800b9364  add     rsp, 20h
0x1800b9368  pop     rdi
0x1800b9369  retn
```
