# CSdCommonImpl::_AssertPrivileges(void)

- ea: `0x18004b8ec`
- end: `0x18004ba57`
- name: `?_AssertPrivileges@CSdCommonImpl@@AEAAJXZ`
- size: `363`
- prototype: `__int64 __fastcall(CSdCommonImpl *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004aa10`

## callees

- `0x18004b8ec`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008ea3c`
- `0x18008f5d0`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x18004b924`
- `KERNEL32!GetCurrentThread` at `0x18004b924`
- `KERNEL32!GetLastError` at `0x18004b945`
- `KERNEL32!GetLastError` at `0x18004b945`
- `KERNEL32!CloseHandle` at `0x18004ba33`
- `KERNEL32!CloseHandle` at `0x18004ba33`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004b939`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004b939`

## string_xrefs

- `0x18004b90c`: `CSdCommonImpl::_AssertPrivileges`
- `0x18004b98d`: `SeBackupPrivilege`
- `0x18004b9b3`: `SeRestorePrivilege`
- `0x18004b9cf`: `SeSecurityPrivilege`
- `0x18004b9eb`: `SeTakeOwnershipPrivilege`
- `0x18004ba07`: `SeCreateSymbolicLinkPrivilege`

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
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v7, "CSdCommonImpl::_AssertPrivileges", 1749, 1);
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
0x18004b8ec  mov     [rsp-8+arg_8], rbx
0x18004b8f1  mov     [rsp-8+TokenHandle], rcx
0x18004b8f6  push    rbp
0x18004b8f7  mov     rbp, rsp
0x18004b8fa  sub     rsp, 60h
0x18004b8fe  mov     ebx, 1
0x18004b903  mov     r9d, ebx; unsigned __int16
0x18004b906  mov     r8d, 6D5h; unsigned __int16
0x18004b90c  lea     rdx, aCsdcommonimplA_0; "CSdCommonImpl::_AssertPrivileges"
0x18004b913  lea     rcx, [rbp+var_40]; this
0x18004b917  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18004b91c  mov     [rbp+TokenHandle], 0
0x18004b924  call    cs:__imp_GetCurrentThread
0x18004b92a  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18004b92e  mov     r8d, ebx; OpenAsSelf
0x18004b931  mov     edx, 2000Ch; DesiredAccess
0x18004b936  mov     rcx, rax; ThreadHandle
0x18004b939  call    cs:__imp_OpenThreadToken
0x18004b93f  mov     ebx, eax
0x18004b941  test    eax, eax
0x18004b943  jnz     short loc_18004B96A
0x18004b945  call    cs:__imp_GetLastError
0x18004b94b  cmp     eax, 3F0h
0x18004b950  jz      short loc_18004B96A
0x18004b952  call    GetLastFailureAsHRESULT
0x18004b957  mov     ebx, eax
0x18004b959  mov     [rbp+var_40], eax
0x18004b95c  mov     eax, 6DAh
0x18004b961  mov     [rbp+var_3A], ax
0x18004b965  jmp     loc_18004BA25
0x18004b96a  mov     [rbp+var_40], 0
0x18004b971  mov     eax, 6DAh
0x18004b976  mov     [rbp+var_3C], ax
0x18004b97a  test    ebx, ebx
0x18004b97c  jz      short loc_18004B98D
0x18004b97e  xor     ebx, ebx
0x18004b980  mov     [rbp+var_40], ebx
0x18004b983  mov     eax, 6DEh
0x18004b988  jmp     loc_18004BA21
0x18004b98d  lea     rcx, aSebackupprivil; "SeBackupPrivilege"
0x18004b994  call    ?AssertPrivilege@@YAJPEBG@Z; AssertPrivilege(ushort const *)
0x18004b999  mov     [rbp+var_40], eax
0x18004b99c  test    eax, eax
0x18004b99e  mov     eax, 6E1h
0x18004b9a3  jns     short loc_18004B9AF
0x18004b9a5  mov     ebx, 81000010h
0x18004b9aa  mov     [rbp+var_40], ebx
0x18004b9ad  jmp     short loc_18004B961
0x18004b9af  mov     [rbp+var_3C], ax
0x18004b9b3  lea     rcx, aSerestoreprivi; "SeRestorePrivilege"
0x18004b9ba  call    ?AssertPrivilege@@YAJPEBG@Z; AssertPrivilege(ushort const *)
0x18004b9bf  mov     [rbp+var_40], eax
0x18004b9c2  test    eax, eax
0x18004b9c4  mov     eax, 6E2h
0x18004b9c9  js      short loc_18004B9A5
0x18004b9cb  mov     [rbp+var_3C], ax
0x18004b9cf  lea     rcx, aSesecuritypriv; "SeSecurityPrivilege"
0x18004b9d6  call    ?AssertPrivilege@@YAJPEBG@Z; AssertPrivilege(ushort const *)
0x18004b9db  mov     [rbp+var_40], eax
0x18004b9de  test    eax, eax
0x18004b9e0  mov     eax, 6E3h
0x18004b9e5  js      short loc_18004B9A5
0x18004b9e7  mov     [rbp+var_3C], ax
0x18004b9eb  lea     rcx, aSetakeownershi; "SeTakeOwnershipPrivilege"
0x18004b9f2  call    ?AssertPrivilege@@YAJPEBG@Z; AssertPrivilege(ushort const *)
0x18004b9f7  mov     [rbp+var_40], eax
0x18004b9fa  test    eax, eax
0x18004b9fc  mov     eax, 6E4h
0x18004ba01  js      short loc_18004B9A5
0x18004ba03  mov     [rbp+var_3C], ax
0x18004ba07  lea     rcx, aSecreatesymbol; "SeCreateSymbolicLinkPrivilege"
0x18004ba0e  call    ?AssertPrivilege@@YAJPEBG@Z; AssertPrivilege(ushort const *)
0x18004ba13  mov     ebx, eax
0x18004ba15  mov     [rbp+var_40], eax
0x18004ba18  test    eax, eax
0x18004ba1a  mov     eax, 6E5h
0x18004ba1f  js      short loc_18004B9A5
0x18004ba21  mov     [rbp+var_3C], ax
0x18004ba25  mov     rcx, [rbp+TokenHandle]; hObject
0x18004ba29  lea     rdx, [rcx-1]
0x18004ba2d  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18004ba31  ja      short loc_18004BA41
0x18004ba33  call    cs:__imp_CloseHandle
0x18004ba39  mov     [rbp+TokenHandle], 0
0x18004ba41  lea     rcx, [rbp+var_40]; this
0x18004ba45  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18004ba4a  mov     eax, ebx
0x18004ba4c  mov     rbx, [rsp+60h+arg_8]
0x18004ba51  add     rsp, 60h
0x18004ba55  pop     rbp
0x18004ba56  retn
```
