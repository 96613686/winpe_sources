# CSdCommonImpl::_AssertPrivileges(void)

- ea: `0x18004d5b8`
- end: `0x18004d73c`
- name: `?_AssertPrivileges@CSdCommonImpl@@AEAAJXZ`
- size: `388`
- prototype: `__int64 __fastcall(CSdCommonImpl *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004c6c0`

## callees

- `0x18004d5b8`
- `0x180072e08`
- `0x180072f14`
- `0x1800929c4`
- `0x1800935fc`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x18004d5f0`
- `KERNEL32!GetCurrentThread` at `0x18004d5f0`
- `KERNEL32!GetLastError` at `0x18004d61d`
- `KERNEL32!GetLastError` at `0x18004d61d`
- `KERNEL32!CloseHandle` at `0x18004d711`
- `KERNEL32!CloseHandle` at `0x18004d711`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004d60b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004d60b`

## string_xrefs

- `0x18004d5d8`: `CSdCommonImpl::_AssertPrivileges`
- `0x18004d66b`: `SeBackupPrivilege`
- `0x18004d691`: `SeRestorePrivilege`
- `0x18004d6ad`: `SeSecurityPrivilege`
- `0x18004d6c9`: `SeTakeOwnershipPrivilege`
- `0x18004d6e5`: `SeCreateSymbolicLinkPrivilege`

## pseudocode

```c
__int64 __fastcall CSdCommonImpl::_AssertPrivileges(CSdCommonImpl *this)
{
  HANDLE CurrentThread; // rax
  BOOL v2; // ebx
  __int64 v3; // rcx
  int LastFailureAsHRESULT; // ebx
  __int16 v5; // ax
  int v7; // [rsp+20h] [rbp-40h] BYREF
  __int16 v8; // [rsp+24h] [rbp-3Ch]
  __int16 v9; // [rsp+26h] [rbp-3Ah]
  void *TokenHandle; // [rsp+70h] [rbp+10h] BYREF

  TokenHandle = this;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v7, "CSdCommonImpl::_AssertPrivileges", 0x6D5u, 1u);
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  v2 = OpenThreadToken(CurrentThread, 0x2000Cu, 1, &TokenHandle);
  if ( !v2 && GetLastError() != 1008 )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v3);
    v7 = LastFailureAsHRESULT;
    v5 = 1754;
LABEL_4:
    v9 = v5;
    goto LABEL_14;
  }
  v7 = 0;
  v8 = 1754;
  if ( v2 )
  {
    LastFailureAsHRESULT = 0;
    v7 = 0;
    v5 = 1758;
  }
  else
  {
    v7 = AssertPrivilege(L"SeBackupPrivilege");
    v5 = 1761;
    if ( v7 < 0 )
      goto LABEL_8;
    v8 = 1761;
    v7 = AssertPrivilege(L"SeRestorePrivilege");
    v5 = 1762;
    if ( v7 < 0 )
      goto LABEL_8;
    v8 = 1762;
    v7 = AssertPrivilege(L"SeSecurityPrivilege");
    v5 = 1763;
    if ( v7 < 0
      || (v8 = 1763, v7 = AssertPrivilege(L"SeTakeOwnershipPrivilege"), v5 = 1764, v7 < 0)
      || (v8 = 1764,
          LastFailureAsHRESULT = AssertPrivilege(L"SeCreateSymbolicLinkPrivilege"),
          v7 = LastFailureAsHRESULT,
          v5 = 1765,
          LastFailureAsHRESULT < 0) )
    {
LABEL_8:
      LastFailureAsHRESULT = -2130706416;
      v7 = -2130706416;
      goto LABEL_4;
    }
  }
  v8 = v5;
LABEL_14:
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v7);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18004d5b8  mov     [rsp-8+arg_8], rbx
0x18004d5bd  mov     [rsp-8+TokenHandle], rcx
0x18004d5c2  push    rbp
0x18004d5c3  mov     rbp, rsp
0x18004d5c6  sub     rsp, 60h
0x18004d5ca  mov     ebx, 1
0x18004d5cf  mov     r9d, ebx; unsigned __int16
0x18004d5d2  mov     r8d, 6D5h; unsigned __int16
0x18004d5d8  lea     rdx, aCsdcommonimplA_0; "CSdCommonImpl::_AssertPrivileges"
0x18004d5df  lea     rcx, [rbp+var_40]; this
0x18004d5e3  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18004d5e8  mov     [rbp+TokenHandle], 0
0x18004d5f0  call    cs:__imp_GetCurrentThread
0x18004d5f7  nop     dword ptr [rax+rax+00h]
0x18004d5fc  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18004d600  mov     r8d, ebx; OpenAsSelf
0x18004d603  mov     edx, 2000Ch; DesiredAccess
0x18004d608  mov     rcx, rax; ThreadHandle
0x18004d60b  call    cs:__imp_OpenThreadToken
0x18004d612  nop     dword ptr [rax+rax+00h]
0x18004d617  mov     ebx, eax
0x18004d619  test    eax, eax
0x18004d61b  jnz     short loc_18004D648
0x18004d61d  call    cs:__imp_GetLastError
0x18004d624  nop     dword ptr [rax+rax+00h]
0x18004d629  cmp     eax, 3F0h
0x18004d62e  jz      short loc_18004D648
0x18004d630  call    GetLastFailureAsHRESULT
0x18004d635  mov     ebx, eax
0x18004d637  mov     [rbp+var_40], eax
0x18004d63a  mov     eax, 6DAh
0x18004d63f  mov     [rbp+var_3A], ax
0x18004d643  jmp     loc_18004D703
0x18004d648  mov     [rbp+var_40], 0
0x18004d64f  mov     eax, 6DAh
0x18004d654  mov     [rbp+var_3C], ax
0x18004d658  test    ebx, ebx
0x18004d65a  jz      short loc_18004D66B
0x18004d65c  xor     ebx, ebx
0x18004d65e  mov     [rbp+var_40], ebx
0x18004d661  mov     eax, 6DEh
0x18004d666  jmp     loc_18004D6FF
0x18004d66b  lea     rcx, aSebackupprivil; "SeBackupPrivilege"
0x18004d672  call    ?AssertPrivilege@@YAJPEBG@Z; AssertPrivilege(ushort const *)
0x18004d677  mov     [rbp+var_40], eax
0x18004d67a  test    eax, eax
0x18004d67c  mov     eax, 6E1h
0x18004d681  jns     short loc_18004D68D
0x18004d683  mov     ebx, 81000010h
0x18004d688  mov     [rbp+var_40], ebx
0x18004d68b  jmp     short loc_18004D63F
0x18004d68d  mov     [rbp+var_3C], ax
0x18004d691  lea     rcx, aSerestoreprivi; "SeRestorePrivilege"
0x18004d698  call    ?AssertPrivilege@@YAJPEBG@Z; AssertPrivilege(ushort const *)
0x18004d69d  mov     [rbp+var_40], eax
0x18004d6a0  test    eax, eax
0x18004d6a2  mov     eax, 6E2h
0x18004d6a7  js      short loc_18004D683
0x18004d6a9  mov     [rbp+var_3C], ax
0x18004d6ad  lea     rcx, aSesecuritypriv; "SeSecurityPrivilege"
0x18004d6b4  call    ?AssertPrivilege@@YAJPEBG@Z; AssertPrivilege(ushort const *)
0x18004d6b9  mov     [rbp+var_40], eax
0x18004d6bc  test    eax, eax
0x18004d6be  mov     eax, 6E3h
0x18004d6c3  js      short loc_18004D683
0x18004d6c5  mov     [rbp+var_3C], ax
0x18004d6c9  lea     rcx, aSetakeownershi; "SeTakeOwnershipPrivilege"
0x18004d6d0  call    ?AssertPrivilege@@YAJPEBG@Z; AssertPrivilege(ushort const *)
0x18004d6d5  mov     [rbp+var_40], eax
0x18004d6d8  test    eax, eax
0x18004d6da  mov     eax, 6E4h
0x18004d6df  js      short loc_18004D683
0x18004d6e1  mov     [rbp+var_3C], ax
0x18004d6e5  lea     rcx, aSecreatesymbol; "SeCreateSymbolicLinkPrivilege"
0x18004d6ec  call    ?AssertPrivilege@@YAJPEBG@Z; AssertPrivilege(ushort const *)
0x18004d6f1  mov     ebx, eax
0x18004d6f3  mov     [rbp+var_40], eax
0x18004d6f6  test    eax, eax
0x18004d6f8  mov     eax, 6E5h
0x18004d6fd  js      short loc_18004D683
0x18004d6ff  mov     [rbp+var_3C], ax
0x18004d703  mov     rcx, [rbp+TokenHandle]; hObject
0x18004d707  lea     rdx, [rcx-1]
0x18004d70b  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18004d70f  ja      short loc_18004D725
0x18004d711  call    cs:__imp_CloseHandle
0x18004d718  nop     dword ptr [rax+rax+00h]
0x18004d71d  mov     [rbp+TokenHandle], 0
0x18004d725  lea     rcx, [rbp+var_40]; this
0x18004d729  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18004d72e  mov     eax, ebx
0x18004d730  mov     rbx, [rsp+60h+arg_8]
0x18004d735  add     rsp, 60h
0x18004d739  pop     rbp
0x18004d73a  retn
```
