# OpenThreadAccessToken(void * *)

- ea: `0x180089968`
- end: `0x180089aab`
- name: `?OpenThreadAccessToken@@YAJPEAPEAX@Z`
- size: `323`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18002c07c`
- `0x1800b8988`

## callees

- `0x18006fe84`
- `0x18006ff8c`
- `0x180089968`
- `0x18008f5d0`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x1800899bf`
- `KERNEL32!GetCurrentThread` at `0x180089a43`
- `KERNEL32!GetCurrentThread` at `0x1800899bf`
- `KERNEL32!GetCurrentThread` at `0x180089a43`
- `KERNEL32!GetLastError` at `0x1800899f4`
- `KERNEL32!GetLastError` at `0x1800899f4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800899d6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180089a5a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800899d6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180089a5a`
- `ole32!CoRevertToSelf` at `0x180089a87`
- `ole32!CoRevertToSelf` at `0x180089a87`
- `ole32!CoImpersonateClient` at `0x180089a27`
- `ole32!CoImpersonateClient` at `0x180089a27`

## string_xrefs

- `0x18008997d`: `OpenThreadAccessToken`

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

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "OpenThreadAccessToken", 235, 1);
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
0x180089968  mov     [rsp-8+arg_0], rbx
0x18008996d  mov     [rsp-8+arg_8], rdi
0x180089972  push    rbp
0x180089973  mov     rbp, rsp
0x180089976  sub     rsp, 60h
0x18008997a  mov     rdi, rcx
0x18008997d  lea     rdx, aOpenthreadacce; "OpenThreadAccessToken"
0x180089984  lea     rcx, [rbp+var_40]; this
0x180089988  mov     r9d, 1; unsigned __int16
0x18008998e  mov     r8d, 0EBh; unsigned __int16
0x180089994  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180089999  mov     eax, 0F0h
0x18008999e  test    rdi, rdi
0x1800899a1  jnz     short loc_1800899B4
0x1800899a3  mov     ebx, 80070057h
0x1800899a8  mov     [rbp+var_40], ebx
0x1800899ab  mov     [rbp+var_3A], ax
0x1800899af  jmp     loc_180089A90
0x1800899b4  mov     [rbp+var_40], 0
0x1800899bb  mov     [rbp+var_3C], ax
0x1800899bf  call    cs:__imp_GetCurrentThread
0x1800899c5  mov     r9, rdi; TokenHandle
0x1800899c8  mov     edx, 20008h; DesiredAccess
0x1800899cd  mov     rcx, rax; ThreadHandle
0x1800899d0  mov     r8d, 1; OpenAsSelf
0x1800899d6  call    cs:__imp_OpenThreadToken
0x1800899dc  cmp     eax, 1
0x1800899df  jnz     short loc_1800899F4
0x1800899e1  xor     ebx, ebx
0x1800899e3  mov     eax, 0F5h
0x1800899e8  mov     [rbp+var_40], ebx
0x1800899eb  mov     [rbp+var_3C], ax
0x1800899ef  jmp     loc_180089A90
0x1800899f4  call    cs:__imp_GetLastError
0x1800899fa  mov     ebx, eax
0x1800899fc  cmp     eax, 3F0h
0x180089a01  jz      short loc_180089A17
0x180089a03  test    eax, eax
0x180089a05  jle     short loc_180089A10
0x180089a07  movzx   ebx, ax
0x180089a0a  or      ebx, 80070000h
0x180089a10  mov     eax, 0F9h
0x180089a15  jmp     short loc_1800899A8
0x180089a17  mov     eax, 0F9h
0x180089a1c  mov     [rbp+var_40], 0
0x180089a23  mov     [rbp+var_3C], ax
0x180089a27  call    cs:__imp_CoImpersonateClient
0x180089a2d  mov     ebx, eax
0x180089a2f  mov     [rbp+var_40], eax
0x180089a32  test    eax, eax
0x180089a34  mov     eax, 0FDh
0x180089a39  js      loc_1800899AB
0x180089a3f  mov     [rbp+var_3C], ax
0x180089a43  call    cs:__imp_GetCurrentThread
0x180089a49  mov     r9, rdi; TokenHandle
0x180089a4c  mov     edx, 20008h; DesiredAccess
0x180089a51  mov     rcx, rax; ThreadHandle
0x180089a54  mov     r8d, 1; OpenAsSelf
0x180089a5a  call    cs:__imp_OpenThreadToken
0x180089a60  test    eax, eax
0x180089a62  jnz     short loc_180089A77
0x180089a64  call    GetLastFailureAsHRESULT
0x180089a69  mov     [rbp+var_40], eax
0x180089a6c  mov     eax, 100h
0x180089a71  mov     [rbp+var_3A], ax
0x180089a75  jmp     short loc_180089A87
0x180089a77  mov     eax, 100h
0x180089a7c  mov     [rbp+var_40], 0
0x180089a83  mov     [rbp+var_3C], ax
0x180089a87  call    cs:__imp_CoRevertToSelf
0x180089a8d  mov     ebx, [rbp+var_40]
0x180089a90  lea     rcx, [rbp+var_40]; this
0x180089a94  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180089a99  mov     rdi, [rsp+60h+arg_8]
0x180089a9e  mov     eax, ebx
0x180089aa0  mov     rbx, [rsp+60h+arg_0]
0x180089aa5  add     rsp, 60h
0x180089aa9  pop     rbp
0x180089aaa  retn
```
