# OpenThreadAccessToken(void * *)

- ea: `0x18008d4e8`
- end: `0x18008d659`
- name: `?OpenThreadAccessToken@@YAJPEAPEAX@Z`
- size: `369`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18002d16c`
- `0x1800be478`

## callees

- `0x180072e08`
- `0x180072f14`
- `0x18008d4e8`
- `0x1800935fc`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x18008d53f`
- `KERNEL32!GetCurrentThread` at `0x18008d5de`
- `KERNEL32!GetCurrentThread` at `0x18008d53f`
- `KERNEL32!GetCurrentThread` at `0x18008d5de`
- `KERNEL32!GetLastError` at `0x18008d580`
- `KERNEL32!GetLastError` at `0x18008d580`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18008d55c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18008d5fb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18008d55c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18008d5fb`
- `ole32!CoRevertToSelf` at `0x18008d62e`
- `ole32!CoRevertToSelf` at `0x18008d62e`
- `ole32!CoImpersonateClient` at `0x18008d5bc`
- `ole32!CoImpersonateClient` at `0x18008d5bc`

## string_xrefs

- `0x18008d4fd`: `OpenThreadAccessToken`

## pseudocode

```c
__int64 __fastcall OpenThreadAccessToken(PHANDLE TokenHandle)
{
  __int16 v2; // ax
  int v3; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  HANDLE v6; // rax
  __int64 v7; // rcx
  int LastFailureAsHRESULT; // [rsp+20h] [rbp-40h] BYREF
  __int16 v10; // [rsp+24h] [rbp-3Ch]
  __int16 v11; // [rsp+26h] [rbp-3Ah]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "OpenThreadAccessToken", 0xEBu, 1u);
  v2 = 240;
  if ( !TokenHandle )
  {
    v3 = -2147024809;
LABEL_3:
    LastFailureAsHRESULT = v3;
LABEL_4:
    v11 = v2;
    goto LABEL_16;
  }
  LastFailureAsHRESULT = 0;
  v10 = 240;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x20008u, 1, TokenHandle) )
  {
    v3 = 0;
    LastFailureAsHRESULT = 0;
    v10 = 245;
    goto LABEL_16;
  }
  LastError = GetLastError();
  v3 = LastError;
  if ( LastError != 1008 )
  {
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    v2 = 249;
    goto LABEL_3;
  }
  LastFailureAsHRESULT = 0;
  v10 = 249;
  v3 = CoImpersonateClient();
  LastFailureAsHRESULT = v3;
  v2 = 253;
  if ( v3 < 0 )
    goto LABEL_4;
  v10 = 253;
  v6 = GetCurrentThread();
  if ( OpenThreadToken(v6, 0x20008u, 1, TokenHandle) )
  {
    LastFailureAsHRESULT = 0;
    v10 = 256;
  }
  else
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v7);
    v11 = 256;
  }
  CoRevertToSelf();
  v3 = LastFailureAsHRESULT;
LABEL_16:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18008d4e8  mov     [rsp-8+arg_0], rbx
0x18008d4ed  mov     [rsp-8+arg_8], rdi
0x18008d4f2  push    rbp
0x18008d4f3  mov     rbp, rsp
0x18008d4f6  sub     rsp, 60h
0x18008d4fa  mov     rdi, rcx
0x18008d4fd  lea     rdx, aOpenthreadacce; "OpenThreadAccessToken"
0x18008d504  lea     rcx, [rbp+var_40]; this
0x18008d508  mov     r9d, 1; unsigned __int16
0x18008d50e  mov     r8d, 0EBh; unsigned __int16
0x18008d514  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18008d519  mov     eax, 0F0h
0x18008d51e  test    rdi, rdi
0x18008d521  jnz     short loc_18008D534
0x18008d523  mov     ebx, 80070057h
0x18008d528  mov     [rbp+var_40], ebx
0x18008d52b  mov     [rbp+var_3A], ax
0x18008d52f  jmp     loc_18008D63D
0x18008d534  mov     [rbp+var_40], 0
0x18008d53b  mov     [rbp+var_3C], ax
0x18008d53f  call    cs:__imp_GetCurrentThread
0x18008d546  nop     dword ptr [rax+rax+00h]
0x18008d54b  mov     r9, rdi; TokenHandle
0x18008d54e  mov     edx, 20008h; DesiredAccess
0x18008d553  mov     rcx, rax; ThreadHandle
0x18008d556  mov     r8d, 1; OpenAsSelf
0x18008d55c  call    cs:__imp_OpenThreadToken
0x18008d563  nop     dword ptr [rax+rax+00h]
0x18008d568  cmp     eax, 1
0x18008d56b  jnz     short loc_18008D580
0x18008d56d  xor     ebx, ebx
0x18008d56f  mov     eax, 0F5h
0x18008d574  mov     [rbp+var_40], ebx
0x18008d577  mov     [rbp+var_3C], ax
0x18008d57b  jmp     loc_18008D63D
0x18008d580  call    cs:__imp_GetLastError
0x18008d587  nop     dword ptr [rax+rax+00h]
0x18008d58c  mov     ebx, eax
0x18008d58e  cmp     eax, 3F0h
0x18008d593  jz      short loc_18008D5AC
0x18008d595  test    eax, eax
0x18008d597  jle     short loc_18008D5A2
0x18008d599  movzx   ebx, ax
0x18008d59c  or      ebx, 80070000h
0x18008d5a2  mov     eax, 0F9h
0x18008d5a7  jmp     loc_18008D528
0x18008d5ac  mov     eax, 0F9h
0x18008d5b1  mov     [rbp+var_40], 0
0x18008d5b8  mov     [rbp+var_3C], ax
0x18008d5bc  call    cs:__imp_CoImpersonateClient
0x18008d5c3  nop     dword ptr [rax+rax+00h]
0x18008d5c8  mov     ebx, eax
0x18008d5ca  mov     [rbp+var_40], eax
0x18008d5cd  test    eax, eax
0x18008d5cf  mov     eax, 0FDh
0x18008d5d4  js      loc_18008D52B
0x18008d5da  mov     [rbp+var_3C], ax
0x18008d5de  call    cs:__imp_GetCurrentThread
0x18008d5e5  nop     dword ptr [rax+rax+00h]
0x18008d5ea  mov     r9, rdi; TokenHandle
0x18008d5ed  mov     edx, 20008h; DesiredAccess
0x18008d5f2  mov     rcx, rax; ThreadHandle
0x18008d5f5  mov     r8d, 1; OpenAsSelf
0x18008d5fb  call    cs:__imp_OpenThreadToken
0x18008d602  nop     dword ptr [rax+rax+00h]
0x18008d607  test    eax, eax
0x18008d609  jnz     short loc_18008D61E
0x18008d60b  call    GetLastFailureAsHRESULT
0x18008d610  mov     [rbp+var_40], eax
0x18008d613  mov     eax, 100h
0x18008d618  mov     [rbp+var_3A], ax
0x18008d61c  jmp     short loc_18008D62E
0x18008d61e  mov     eax, 100h
0x18008d623  mov     [rbp+var_40], 0
0x18008d62a  mov     [rbp+var_3C], ax
0x18008d62e  call    cs:__imp_CoRevertToSelf
0x18008d635  nop     dword ptr [rax+rax+00h]
0x18008d63a  mov     ebx, [rbp+var_40]
0x18008d63d  lea     rcx, [rbp+var_40]; this
0x18008d641  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18008d646  mov     rdi, [rsp+60h+arg_8]
0x18008d64b  mov     eax, ebx
0x18008d64d  mov     rbx, [rsp+60h+arg_0]
0x18008d652  add     rsp, 60h
0x18008d656  pop     rbp
0x18008d657  retn
```
