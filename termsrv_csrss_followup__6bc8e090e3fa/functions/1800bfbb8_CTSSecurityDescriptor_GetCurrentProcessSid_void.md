# CTSSecurityDescriptor::GetCurrentProcessSid(void * *)

- ea: `0x1800bfbb8`
- end: `0x1800bfcd1`
- name: `?GetCurrentProcessSid@CTSSecurityDescriptor@@IEAAJPEAPEAX@Z`
- size: `281`
- prototype: `__int64 __fastcall(CTSSecurityDescriptor *__hidden this, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180016e30`

## callees

- `0x180008110`
- `0x180009940`
- `0x1800139c0`
- `0x180015020`
- `0x1800bfbb8`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bfc08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bfc08`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800bfbdf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800bfbdf`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800bfbf8`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800bfbf8`

## string_xrefs

- `0x1800bfc2a`: `OpenProcessToken failed: 0x%x in %s`
- `0x1800bfc99`: `CTSSecurityDescriptor::GetCurrentProcessSid`
- `0x1800bfc8f`: `IUserName->GetUserSid failed: 0x%x in %s`

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
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v10);
  SmartHANDLE::~SmartHANDLE((SmartHANDLE *)&TokenHandle);
  return v5;
}

```

## disassembly

```asm
0x1800bfbb8  mov     rax, rsp
0x1800bfbbb  mov     [rax+10h], rbx
0x1800bfbbf  mov     [rax+20h], rsi
0x1800bfbc3  mov     [rax+8], rcx
0x1800bfbc7  push    rdi
0x1800bfbc8  sub     rsp, 20h
0x1800bfbcc  mov     rsi, rdx
0x1800bfbcf  mov     qword ptr [rax+18h], 0
0x1800bfbd7  mov     qword ptr [rax+8], 0
0x1800bfbdf  call    cs:__imp_GetCurrentProcess
0x1800bfbe6  nop     dword ptr [rax+rax+00h]
0x1800bfbeb  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x1800bfbf0  mov     edx, 0Eh; DesiredAccess
0x1800bfbf5  mov     rcx, rax; ProcessHandle
0x1800bfbf8  call    cs:__imp_OpenProcessToken
0x1800bfbff  nop     dword ptr [rax+rax+00h]
0x1800bfc04  test    eax, eax
0x1800bfc06  jnz     short loc_1800BFC33
0x1800bfc08  call    cs:__imp_GetLastError
0x1800bfc0f  nop     dword ptr [rax+rax+00h]
0x1800bfc14  mov     ebx, eax
0x1800bfc16  test    eax, eax
0x1800bfc18  jle     short loc_1800BFC23
0x1800bfc1a  movzx   ebx, ax
0x1800bfc1d  or      ebx, 80070000h
0x1800bfc23  test    ebx, ebx
0x1800bfc25  jns     short loc_1800BFC33
0x1800bfc27  mov     r8d, ebx
0x1800bfc2a  lea     rdx, aOpenprocesstok; "OpenProcessToken failed: 0x%x in %s"
0x1800bfc31  jmp     short loc_1800BFC99
0x1800bfc33  lea     rcx, [rsp+28h+arg_0]; struct IUserName **
0x1800bfc38  call    ?GetInstanceOfUserName@CUtils@@SAJPEAPEAUIUserName@@@Z; CUtils::GetInstanceOfUserName(IUserName * *)
0x1800bfc3d  mov     ebx, eax
0x1800bfc3f  test    eax, eax
0x1800bfc41  jns     short loc_1800BFC4C
0x1800bfc43  lea     rdx, aGetinstanceofu; "GetInstanceOfUserName failed: 0x%x in %"...
0x1800bfc4a  jmp     short loc_1800BFC96
0x1800bfc4c  mov     rdi, [rsp+28h+arg_0]
0x1800bfc51  xor     r8d, r8d
0x1800bfc54  mov     rdx, [rsp+28h+TokenHandle]
0x1800bfc59  mov     rcx, rdi
0x1800bfc5c  mov     rax, [rdi]
0x1800bfc5f  mov     rax, [rax+18h]
0x1800bfc63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfc68  mov     ebx, eax
0x1800bfc6a  test    eax, eax
0x1800bfc6c  jns     short loc_1800BFC77
0x1800bfc6e  lea     rdx, aIusernameIniti; "IUserName->Initialize failed: 0x%x in %"...
0x1800bfc75  jmp     short loc_1800BFC96
0x1800bfc77  mov     rax, [rdi]
0x1800bfc7a  mov     rdx, rsi
0x1800bfc7d  mov     rcx, rdi
0x1800bfc80  mov     rax, [rax+48h]
0x1800bfc84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfc89  mov     ebx, eax
0x1800bfc8b  test    eax, eax
0x1800bfc8d  jns     short loc_1800BFCAA
0x1800bfc8f  lea     rdx, aIusernameGetus_0; "IUserName->GetUserSid failed: 0x%x in %"...
0x1800bfc96  mov     r8d, eax
0x1800bfc99  lea     r9, aCtssecuritydes_1; "CTSSecurityDescriptor::GetCurrentProces"...
0x1800bfca0  mov     ecx, 8; int
0x1800bfca5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800bfcaa  lea     rcx, [rsp+28h+arg_0]; void *
0x1800bfcaf  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800bfcb4  lea     rcx, [rsp+28h+TokenHandle]; this
0x1800bfcb9  call    ??1SmartHANDLE@@QEAA@XZ; SmartHANDLE::~SmartHANDLE(void)
0x1800bfcbe  mov     rsi, [rsp+28h+arg_18]
0x1800bfcc3  mov     eax, ebx
0x1800bfcc5  mov     rbx, [rsp+28h+arg_8]
0x1800bfcca  add     rsp, 20h
0x1800bfcce  pop     rdi
0x1800bfccf  retn
```
