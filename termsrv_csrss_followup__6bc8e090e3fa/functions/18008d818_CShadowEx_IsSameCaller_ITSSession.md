# CShadowEx::IsSameCaller(ITSSession *)

- ea: `0x18008d818`
- end: `0x18008d97b`
- name: `?IsSameCaller@CShadowEx@@AEAAJPEAUITSSession@@@Z`
- size: `355`
- prototype: `__int64 __fastcall(CShadowEx *__hidden this, struct ITSSession *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18008dac0`

## callees

- `0x180008110`
- `0x180009940`
- `0x1800139c0`
- `0x180015020`
- `0x18008d818`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d873`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d873`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008d847`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008d847`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18008d863`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18008d863`

## string_xrefs

- `0x18008d895`: `OpenThreadToken failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CShadowEx::IsSameCaller(CShadowEx *this, struct ITSSession *a2)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  unsigned int v5; // edi
  int InstanceOfUserName; // eax
  struct IUserName *v7; // rbx
  int v8; // eax
  int v9; // eax
  __int64 v11; // [rsp+40h] [rbp+20h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+30h] BYREF
  struct IUserName *v13; // [rsp+58h] [rbp+38h] BYREF

  v13 = 0;
  TokenHandle = 0;
  v11 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
    goto LABEL_7;
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  if ( (v5 & 0x80000000) == 0 )
  {
LABEL_7:
    InstanceOfUserName = CUtils::GetInstanceOfUserName(&v13);
    v5 = InstanceOfUserName;
    if ( InstanceOfUserName >= 0 )
    {
      v7 = v13;
      v8 = (*(__int64 (__fastcall **)(struct IUserName *, void *, _QWORD))(*(_QWORD *)v13 + 24LL))(v13, TokenHandle, 0);
      v5 = v8;
      if ( v8 >= 0 )
      {
        v9 = (*(__int64 (__fastcall **)(struct ITSSession *, __int64 *))(*(_QWORD *)a2 + 96LL))(a2, &v11);
        v5 = v9;
        if ( v9 >= 0 )
        {
          if ( (*(unsigned int (__fastcall **)(__int64, struct IUserName *))(*(_QWORD *)v11 + 32LL))(v11, v7) )
          {
            _DbgPrintMessage(8, "UserName's don't match");
            v5 = -2147024891;
          }
        }
        else
        {
          _DbgPrintMessage(8, "Session->getUserName failed: 0x%x in %s", (unsigned int)v9, "CShadowEx::IsSameCaller");
        }
      }
      else
      {
        _DbgPrintMessage(8, "IUserName->Initialize failed: 0x%x in %s", (unsigned int)v8, "CShadowEx::IsSameCaller");
      }
    }
    else
    {
      _DbgPrintMessage(
        8,
        "GetInstanceOfUserName failed: 0x%x in %s",
        (unsigned int)InstanceOfUserName,
        "CShadowEx::IsSameCaller");
    }
  }
  else
  {
    _DbgPrintMessage(8, "OpenThreadToken failed: 0x%x in %s", v5, "CShadowEx::IsSameCaller");
  }
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v11);
  SmartHANDLE::~SmartHANDLE((SmartHANDLE *)&TokenHandle);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v13);
  return v5;
}

```

## disassembly

```asm
0x18008d818  mov     [rsp-18h+arg_8], rbx
0x18008d81d  mov     [rsp-18h+arg_0], rcx
0x18008d822  push    rbp
0x18008d823  push    rsi
0x18008d824  push    rdi
0x18008d825  mov     rbp, rsp
0x18008d828  sub     rsp, 20h
0x18008d82c  mov     rsi, rdx
0x18008d82f  mov     [rbp+arg_18], 0
0x18008d837  mov     [rbp+TokenHandle], 0
0x18008d83f  mov     [rbp+arg_0], 0
0x18008d847  call    cs:__imp_GetCurrentThread
0x18008d84e  nop     dword ptr [rax+rax+00h]
0x18008d853  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18008d857  mov     edx, 0Eh; DesiredAccess
0x18008d85c  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x18008d860  mov     rcx, rax; ThreadHandle
0x18008d863  call    cs:__imp_OpenThreadToken
0x18008d86a  nop     dword ptr [rax+rax+00h]
0x18008d86f  test    eax, eax
0x18008d871  jnz     short loc_18008D8B2
0x18008d873  call    cs:__imp_GetLastError
0x18008d87a  nop     dword ptr [rax+rax+00h]
0x18008d87f  mov     edi, eax
0x18008d881  test    eax, eax
0x18008d883  jle     short loc_18008D88E
0x18008d885  movzx   edi, ax
0x18008d888  or      edi, 80070000h
0x18008d88e  test    edi, edi
0x18008d890  jns     short loc_18008D8B2
0x18008d892  mov     r8d, edi
0x18008d895  lea     rdx, aOpenthreadtoke; "OpenThreadToken failed: 0x%x in %s"
0x18008d89c  lea     r9, aCshadowexIssam; "CShadowEx::IsSameCaller"
0x18008d8a3  mov     ecx, 8; int
0x18008d8a8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18008d8ad  jmp     loc_18008D94E
0x18008d8b2  lea     rcx, [rbp+arg_18]; struct IUserName **
0x18008d8b6  call    ?GetInstanceOfUserName@CUtils@@SAJPEAPEAUIUserName@@@Z; CUtils::GetInstanceOfUserName(IUserName * *)
0x18008d8bb  mov     edi, eax
0x18008d8bd  test    eax, eax
0x18008d8bf  jns     short loc_18008D8CD
0x18008d8c1  mov     r8d, eax
0x18008d8c4  lea     rdx, aGetinstanceofu; "GetInstanceOfUserName failed: 0x%x in %"...
0x18008d8cb  jmp     short loc_18008D89C
0x18008d8cd  mov     rbx, [rbp+arg_18]
0x18008d8d1  mov     rax, [rbx]
0x18008d8d4  xor     r8d, r8d
0x18008d8d7  mov     rdx, [rbp+TokenHandle]
0x18008d8db  mov     rcx, rbx
0x18008d8de  mov     rax, [rax+18h]
0x18008d8e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d8e7  mov     edi, eax
0x18008d8e9  test    eax, eax
0x18008d8eb  jns     short loc_18008D8F9
0x18008d8ed  mov     r8d, eax
0x18008d8f0  lea     rdx, aIusernameIniti; "IUserName->Initialize failed: 0x%x in %"...
0x18008d8f7  jmp     short loc_18008D89C
0x18008d8f9  mov     rax, [rsi]
0x18008d8fc  lea     rdx, [rbp+arg_0]
0x18008d900  mov     rcx, rsi
0x18008d903  mov     rax, [rax+60h]
0x18008d907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d90c  mov     edi, eax
0x18008d90e  test    eax, eax
0x18008d910  jns     short loc_18008D921
0x18008d912  mov     r8d, eax
0x18008d915  lea     rdx, aSessionGetuser; "Session->getUserName failed: 0x%x in %s"
0x18008d91c  jmp     loc_18008D89C
0x18008d921  mov     rcx, [rbp+arg_0]
0x18008d925  mov     rax, [rcx]
0x18008d928  mov     rdx, rbx
0x18008d92b  mov     rax, [rax+20h]
0x18008d92f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d934  test    eax, eax
0x18008d936  jz      short loc_18008D94E
0x18008d938  lea     rdx, aUsernameSDonTM; "UserName's don't match"
0x18008d93f  mov     ecx, 8; int
0x18008d944  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18008d949  mov     edi, 80070005h
0x18008d94e  lea     rcx, [rbp+arg_0]; void *
0x18008d952  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18008d957  nop
0x18008d958  lea     rcx, [rbp+TokenHandle]; this
0x18008d95c  call    ??1SmartHANDLE@@QEAA@XZ; SmartHANDLE::~SmartHANDLE(void)
0x18008d961  nop
0x18008d962  lea     rcx, [rbp+arg_18]; void *
0x18008d966  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18008d96b  mov     eax, edi
0x18008d96d  mov     rbx, [rsp+20h+arg_8]
0x18008d972  add     rsp, 20h
0x18008d976  pop     rdi
0x18008d977  pop     rsi
0x18008d978  pop     rbp
0x18008d979  retn
```
