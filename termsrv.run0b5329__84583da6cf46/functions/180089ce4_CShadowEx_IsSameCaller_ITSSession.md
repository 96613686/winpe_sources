# CShadowEx::IsSameCaller(ITSSession *)

- ea: `0x180089ce4`
- end: `0x180089e34`
- name: `?IsSameCaller@CShadowEx@@AEAAJPEAUITSSession@@@Z`
- size: `336`
- prototype: `__int64 __fastcall(CShadowEx *__hidden this, struct ITSSession *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180089f70`

## callees

- `0x180008b40`
- `0x18000a210`
- `0x180013150`
- `0x1800148d0`
- `0x180089ce4`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089d33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089d33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180089d13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180089d13`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180089d29`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180089d29`

## string_xrefs

- `0x180089d4f`: `OpenThreadToken failed: 0x%x in %s`

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
0x180089ce4  mov     [rsp-18h+arg_8], rbx
0x180089ce9  mov     [rsp-18h+arg_0], rcx
0x180089cee  push    rbp
0x180089cef  push    rsi
0x180089cf0  push    rdi
0x180089cf1  mov     rbp, rsp
0x180089cf4  sub     rsp, 20h
0x180089cf8  mov     rsi, rdx
0x180089cfb  mov     [rbp+arg_18], 0
0x180089d03  mov     [rbp+TokenHandle], 0
0x180089d0b  mov     [rbp+arg_0], 0
0x180089d13  call    cs:__imp_GetCurrentThread
0x180089d19  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180089d1d  mov     edx, 0Eh; DesiredAccess
0x180089d22  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x180089d26  mov     rcx, rax; ThreadHandle
0x180089d29  call    cs:__imp_OpenThreadToken
0x180089d2f  test    eax, eax
0x180089d31  jnz     short loc_180089D6C
0x180089d33  call    cs:__imp_GetLastError
0x180089d39  mov     edi, eax
0x180089d3b  test    eax, eax
0x180089d3d  jle     short loc_180089D48
0x180089d3f  movzx   edi, ax
0x180089d42  or      edi, 80070000h
0x180089d48  test    edi, edi
0x180089d4a  jns     short loc_180089D6C
0x180089d4c  mov     r8d, edi
0x180089d4f  lea     rdx, aOpenthreadtoke; "OpenThreadToken failed: 0x%x in %s"
0x180089d56  lea     r9, aCshadowexIssam; "CShadowEx::IsSameCaller"
0x180089d5d  mov     ecx, 8; int
0x180089d62  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180089d67  jmp     loc_180089E08
0x180089d6c  lea     rcx, [rbp+arg_18]; struct IUserName **
0x180089d70  call    ?GetInstanceOfUserName@CUtils@@SAJPEAPEAUIUserName@@@Z; CUtils::GetInstanceOfUserName(IUserName * *)
0x180089d75  mov     edi, eax
0x180089d77  test    eax, eax
0x180089d79  jns     short loc_180089D87
0x180089d7b  mov     r8d, eax
0x180089d7e  lea     rdx, aGetinstanceofu; "GetInstanceOfUserName failed: 0x%x in %"...
0x180089d85  jmp     short loc_180089D56
0x180089d87  mov     rbx, [rbp+arg_18]
0x180089d8b  mov     rax, [rbx]
0x180089d8e  xor     r8d, r8d
0x180089d91  mov     rdx, [rbp+TokenHandle]
0x180089d95  mov     rcx, rbx
0x180089d98  mov     rax, [rax+18h]
0x180089d9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089da1  mov     edi, eax
0x180089da3  test    eax, eax
0x180089da5  jns     short loc_180089DB3
0x180089da7  mov     r8d, eax
0x180089daa  lea     rdx, aIusernameIniti; "IUserName->Initialize failed: 0x%x in %"...
0x180089db1  jmp     short loc_180089D56
0x180089db3  mov     rax, [rsi]
0x180089db6  lea     rdx, [rbp+arg_0]
0x180089dba  mov     rcx, rsi
0x180089dbd  mov     rax, [rax+60h]
0x180089dc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089dc6  mov     edi, eax
0x180089dc8  test    eax, eax
0x180089dca  jns     short loc_180089DDB
0x180089dcc  mov     r8d, eax
0x180089dcf  lea     rdx, aSessionGetuser; "Session->getUserName failed: 0x%x in %s"
0x180089dd6  jmp     loc_180089D56
0x180089ddb  mov     rcx, [rbp+arg_0]
0x180089ddf  mov     rax, [rcx]
0x180089de2  mov     rdx, rbx
0x180089de5  mov     rax, [rax+20h]
0x180089de9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089dee  test    eax, eax
0x180089df0  jz      short loc_180089E08
0x180089df2  lea     rdx, aUsernameSDonTM; "UserName's don't match"
0x180089df9  mov     ecx, 8; int
0x180089dfe  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180089e03  mov     edi, 80070005h
0x180089e08  lea     rcx, [rbp+arg_0]; void *
0x180089e0c  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180089e11  nop
0x180089e12  lea     rcx, [rbp+TokenHandle]; this
0x180089e16  call    ??1SmartHANDLE@@QEAA@XZ; SmartHANDLE::~SmartHANDLE(void)
0x180089e1b  nop
0x180089e1c  lea     rcx, [rbp+arg_18]; void *
0x180089e20  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180089e25  mov     eax, edi
0x180089e27  mov     rbx, [rsp+20h+arg_8]
0x180089e2c  add     rsp, 20h
0x180089e30  pop     rdi
0x180089e31  pop     rsi
0x180089e32  pop     rbp
0x180089e33  retn
```
