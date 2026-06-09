# GetCallerSecToken(int,void * *)

- ea: `0x18000d45c`
- end: `0x18000d58e`
- name: `?GetCallerSecToken@@YAJHPEAPEAX@Z`
- size: `306`
- prototype: `int(int, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000d878`

## callees

- `0x18000d45c`
- `0x180089ee0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d514`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d532`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d558`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d514`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d532`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d558`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000d49d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000d550`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000d49d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000d550`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000d48b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000d53c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000d48b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000d53c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d505`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d505`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18000d528`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18000d528`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000d560`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000d560`
- `RPCRT4!RpcRevertToSelfEx` at `0x18000d4ad`
- `RPCRT4!RpcRevertToSelfEx` at `0x18000d4ad`
- `RPCRT4!RpcImpersonateClient` at `0x18000d478`
- `RPCRT4!RpcImpersonateClient` at `0x18000d478`

## string_xrefs

- `0x18000d576`: `onecoreuap\net\wcm\service\base\selection\lib\policyhelpers.cpp`

## pseudocode

```c
__int64 __fastcall GetCallerSecToken(__int64 a1, void **a2)
{
  int v3; // ebp
  RPC_STATUS v4; // eax
  signed int v5; // edi
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  HANDLE v9; // rax
  BOOL v10; // ebx
  int v11; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( a2 )
  {
    v3 = 0;
    *a2 = 0;
    v4 = RpcImpersonateClient(0);
    v5 = v4;
    if ( v4 )
    {
      if ( v4 != 1725 )
      {
        if ( v4 > 0 )
          v5 = (unsigned __int16)v4 | 0x80070000;
LABEL_7:
        if ( v5 >= 0 )
          return (unsigned int)v5;
        goto LABEL_18;
      }
    }
    else
    {
      v3 = 1;
    }
    v5 = 0;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 1, a2) )
      goto LABEL_5;
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError == 1008 )
    {
      if ( ImpersonateSelf(SecurityImpersonation) )
      {
        v9 = GetCurrentThread();
        v10 = OpenThreadToken(v9, 8u, 1, a2);
        v5 = GetLastError();
        RevertToSelf();
        if ( v10 )
        {
          v5 = 0;
          goto LABEL_5;
        }
        if ( v5 <= 0 )
        {
LABEL_5:
          if ( v3 && RpcRevertToSelfEx(0) )
            wil::details::in1diag3::_FailFast_Hr(
              retaddr,
              (void *)0x9B,
              (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\selection\\lib\\policyhelpers.cpp",
              (const char *)0x8000FFFFLL,
              v11);
          goto LABEL_7;
        }
        v5 = (unsigned __int16)v5;
LABEL_14:
        v5 |= 0x80070000;
        goto LABEL_5;
      }
      LastError = GetLastError();
      v5 = LastError;
    }
    if ( LastError <= 0 )
      goto LABEL_5;
    v5 = (unsigned __int16)LastError;
    goto LABEL_14;
  }
  v5 = -2147467261;
LABEL_18:
  if ( *a2 )
  {
    CloseHandle(*a2);
    *a2 = 0;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000d45c  push    rbx
0x18000d45e  push    rbp
0x18000d45f  push    rsi
0x18000d460  push    rdi
0x18000d461  sub     rsp, 28h
0x18000d465  mov     rsi, rdx
0x18000d468  test    rdx, rdx
0x18000d46b  jz      loc_18000D4F8
0x18000d471  xor     ebp, ebp
0x18000d473  xor     ecx, ecx; BindingHandle
0x18000d475  mov     [rdx], rbp
0x18000d478  call    cs:__imp_RpcImpersonateClient
0x18000d47e  lea     ebx, [rbp+1]
0x18000d481  mov     edi, eax
0x18000d483  test    eax, eax
0x18000d485  jnz     short loc_18000D4CA
0x18000d487  mov     ebp, ebx
0x18000d489  xor     edi, edi
0x18000d48b  call    cs:__imp_GetCurrentThread
0x18000d491  mov     r9, rsi; TokenHandle
0x18000d494  lea     edx, [rdi+8]; DesiredAccess
0x18000d497  mov     rcx, rax; ThreadHandle
0x18000d49a  mov     r8d, ebx; OpenAsSelf
0x18000d49d  call    cs:__imp_OpenThreadToken
0x18000d4a3  test    eax, eax
0x18000d4a5  jz      short loc_18000D514
0x18000d4a7  test    ebp, ebp
0x18000d4a9  jz      short loc_18000D4BB
0x18000d4ab  xor     ecx, ecx; BindingHandle
0x18000d4ad  call    cs:__imp_RpcRevertToSelfEx
0x18000d4b3  test    eax, eax
0x18000d4b5  jnz     loc_18000D571
0x18000d4bb  test    edi, edi
0x18000d4bd  js      short loc_18000D4FD
0x18000d4bf  mov     eax, edi
0x18000d4c1  add     rsp, 28h
0x18000d4c5  pop     rdi
0x18000d4c6  pop     rsi
0x18000d4c7  pop     rbp
0x18000d4c8  pop     rbx
0x18000d4c9  retn
0x18000d4ca  cmp     eax, 6BDh
0x18000d4cf  jz      short loc_18000D489
0x18000d4d1  test    eax, eax
0x18000d4d3  jle     short loc_18000D4BB
0x18000d4d5  movzx   edi, ax
0x18000d4d8  or      edi, 80070000h
0x18000d4de  jmp     short loc_18000D4BB
0x18000d4e0  test    eax, eax
0x18000d4e2  jle     short loc_18000D4A7
0x18000d4e4  movzx   edi, ax
0x18000d4e7  or      edi, 80070000h
0x18000d4ed  jmp     short loc_18000D4A7
0x18000d4ef  test    edi, edi
0x18000d4f1  jle     short loc_18000D4A7
0x18000d4f3  movzx   edi, di
0x18000d4f6  jmp     short loc_18000D4E7
0x18000d4f8  mov     edi, 80004003h
0x18000d4fd  mov     rcx, [rsi]; hObject
0x18000d500  test    rcx, rcx
0x18000d503  jz      short loc_18000D4BF
0x18000d505  call    cs:__imp_CloseHandle
0x18000d50b  mov     qword ptr [rsi], 0
0x18000d512  jmp     short loc_18000D4BF
0x18000d514  call    cs:__imp_GetLastError
0x18000d51a  mov     edi, eax
0x18000d51c  cmp     eax, 3F0h
0x18000d521  jnz     short loc_18000D4E0
0x18000d523  mov     ecx, 2; ImpersonationLevel
0x18000d528  call    cs:__imp_ImpersonateSelf
0x18000d52e  test    eax, eax
0x18000d530  jnz     short loc_18000D53C
0x18000d532  call    cs:__imp_GetLastError
0x18000d538  mov     edi, eax
0x18000d53a  jmp     short loc_18000D4E0
0x18000d53c  call    cs:__imp_GetCurrentThread
0x18000d542  mov     r9, rsi; TokenHandle
0x18000d545  mov     r8d, ebx; OpenAsSelf
0x18000d548  mov     rcx, rax; ThreadHandle
0x18000d54b  mov     edx, 8; DesiredAccess
0x18000d550  call    cs:__imp_OpenThreadToken
0x18000d556  mov     ebx, eax
0x18000d558  call    cs:__imp_GetLastError
0x18000d55e  mov     edi, eax
0x18000d560  call    cs:__imp_RevertToSelf
0x18000d566  test    ebx, ebx
0x18000d568  jz      short loc_18000D4EF
0x18000d56a  xor     edi, edi
0x18000d56c  jmp     loc_18000D4A7
0x18000d571  mov     rcx, [rsp+48h]; this
0x18000d576  lea     r8, aOnecoreuapNetW_7; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x18000d57d  mov     r9d, 8000FFFFh; char *
0x18000d583  mov     edx, 9Bh; void *
0x18000d588  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
