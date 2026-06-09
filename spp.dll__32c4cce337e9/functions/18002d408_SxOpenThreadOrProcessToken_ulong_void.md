# SxOpenThreadOrProcessToken(ulong,void * *)

- ea: `0x18002d408`
- end: `0x18002d5e9`
- name: `?SxOpenThreadOrProcessToken@@YAJKPEAPEAX@Z`
- size: `481`
- prototype: `__int64 __fastcall(unsigned int, void **)`
- caller_count: `6`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000a280`
- `0x18000b0d0`
- `0x18001176c`
- `0x18001c2e8`
- `0x18001faf8`
- `0x18002c08c`

## callees

- `0x180020710`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002d408`
- `0x18002d6e8`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x18002d498`
- `KERNEL32!GetCurrentThread` at `0x18002d55d`
- `KERNEL32!GetCurrentThread` at `0x18002d498`
- `KERNEL32!GetCurrentThread` at `0x18002d55d`
- `KERNEL32!GetLastError` at `0x18002d4ba`
- `KERNEL32!GetLastError` at `0x18002d4ba`
- `KERNEL32!CloseHandle` at `0x18002d4fb`
- `KERNEL32!CloseHandle` at `0x18002d54f`
- `KERNEL32!CloseHandle` at `0x18002d5be`
- `KERNEL32!CloseHandle` at `0x18002d4fb`
- `KERNEL32!CloseHandle` at `0x18002d54f`
- `KERNEL32!CloseHandle` at `0x18002d5be`
- `KERNEL32!GetCurrentProcess` at `0x18002d509`
- `KERNEL32!GetCurrentProcess` at `0x18002d509`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002d4ac`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002d573`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002d4ac`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002d573`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002d51b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002d51b`

## string_xrefs

- `0x18002d454`: `SxOpenThreadOrProcessToken`

## pseudocode

```c
__int64 __fastcall SxOpenThreadOrProcessToken(__int64 a1, void **a2)
{
  char *v3; // rdx
  __int64 v4; // r8
  signed int LastFailureAsHRESULT; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  __int16 v8; // ax
  HANDLE CurrentProcess; // rax
  __int64 v10; // rcx
  HANDLE v11; // rax
  __int64 v12; // rcx
  int v14; // [rsp+20h] [rbp-40h] BYREF
  __int16 v15; // [rsp+24h] [rbp-3Ch]
  __int16 v16; // [rsp+26h] [rbp-3Ah]
  void *TokenHandle; // [rsp+78h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v14, "SxOpenThreadOrProcessToken", 600, 1);
  TokenHandle = 0;
  if ( !a2 )
  {
    LastFailureAsHRESULT = -2147024809;
    v16 = 605;
    v14 = -2147024809;
    goto LABEL_30;
  }
  v14 = 0;
  v15 = 605;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x28u, 0, &TokenHandle) )
  {
    LastFailureAsHRESULT = v14;
    goto LABEL_27;
  }
  LastError = GetLastError();
  LastFailureAsHRESULT = LastError;
  if ( LastError == 5 )
  {
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandle(TokenHandle);
      TokenHandle = 0;
    }
    v11 = GetCurrentThread();
    if ( !OpenThreadToken(v11, 0x28u, 1, &TokenHandle) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v12);
      v14 = LastFailureAsHRESULT;
      v8 = 630;
      goto LABEL_17;
    }
    v8 = 630;
  }
  else
  {
    if ( LastError != 1008 )
    {
      if ( LastError > 0 )
        LastFailureAsHRESULT = (unsigned __int16)LastError | 0x80070000;
      v14 = LastFailureAsHRESULT;
      v8 = 637;
      if ( LastFailureAsHRESULT < 0 )
        goto LABEL_17;
      goto LABEL_25;
    }
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandle(TokenHandle);
      TokenHandle = 0;
    }
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v10);
      v14 = LastFailureAsHRESULT;
      v8 = 623;
LABEL_17:
      v16 = v8;
      goto LABEL_28;
    }
    v8 = 623;
  }
  LastFailureAsHRESULT = 0;
  v14 = 0;
LABEL_25:
  v15 = v8;
LABEL_27:
  *a2 = TokenHandle;
  TokenHandle = 0;
LABEL_28:
  v3 = (char *)TokenHandle - 1;
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
LABEL_30:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v14, (__int64)v3, v4);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18002d408  mov     [rsp-8+arg_0], rbx
0x18002d40d  mov     [rsp-8+arg_10], rdi
0x18002d412  push    rbp
0x18002d413  mov     rbp, rsp
0x18002d416  sub     rsp, 60h
0x18002d41a  mov     rdi, rdx
0x18002d41d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d424  lea     rax, WPP_GLOBAL_Control
0x18002d42b  cmp     rcx, rax
0x18002d42e  jz      short loc_18002D44E
0x18002d430  test    dword ptr [rcx+1Ch], 20000000h
0x18002d437  jz      short loc_18002D44E
0x18002d439  mov     rcx, [rcx+10h]
0x18002d43d  lea     r8, WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids
0x18002d444  mov     edx, 15h
0x18002d449  call    WPP_SF_
0x18002d44e  mov     r9d, 1; unsigned __int16
0x18002d454  lea     rdx, aSxopenthreador; "SxOpenThreadOrProcessToken"
0x18002d45b  mov     r8d, 258h; unsigned __int16
0x18002d461  lea     rcx, [rbp+var_40]; this
0x18002d465  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002d46a  mov     [rbp+TokenHandle], 0
0x18002d472  mov     eax, 25Dh
0x18002d477  test    rdi, rdi
0x18002d47a  jnz     short loc_18002D48D
0x18002d47c  mov     ebx, 80070057h
0x18002d481  mov     [rbp+var_3A], ax
0x18002d485  mov     [rbp+var_40], ebx
0x18002d488  jmp     loc_18002D5CC
0x18002d48d  mov     [rbp+var_40], 0
0x18002d494  mov     [rbp+var_3C], ax
0x18002d498  call    cs:__imp_GetCurrentThread
0x18002d49e  xor     r8d, r8d; OpenAsSelf
0x18002d4a1  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18002d4a5  mov     rcx, rax; ThreadHandle
0x18002d4a8  lea     edx, [r8+28h]; DesiredAccess
0x18002d4ac  call    cs:__imp_OpenThreadToken
0x18002d4b2  test    eax, eax
0x18002d4b4  jnz     loc_18002D59E
0x18002d4ba  call    cs:__imp_GetLastError
0x18002d4c0  mov     ebx, eax
0x18002d4c2  cmp     eax, 5
0x18002d4c5  jz      short loc_18002D541
0x18002d4c7  cmp     eax, 3F0h
0x18002d4cc  jz      short loc_18002D4ED
0x18002d4ce  test    eax, eax
0x18002d4d0  jle     short loc_18002D4DB
0x18002d4d2  movzx   ebx, ax
0x18002d4d5  or      ebx, 80070000h
0x18002d4db  mov     [rbp+var_40], ebx
0x18002d4de  mov     eax, 27Dh
0x18002d4e3  test    ebx, ebx
0x18002d4e5  jns     loc_18002D598
0x18002d4eb  jmp     short loc_18002D534
0x18002d4ed  mov     rcx, [rbp+TokenHandle]; hObject
0x18002d4f1  lea     rax, [rcx-1]
0x18002d4f5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002d4f9  ja      short loc_18002D509
0x18002d4fb  call    cs:__imp_CloseHandle
0x18002d501  mov     [rbp+TokenHandle], 0
0x18002d509  call    cs:__imp_GetCurrentProcess
0x18002d50f  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18002d513  mov     edx, 28h ; '('; DesiredAccess
0x18002d518  mov     rcx, rax; ProcessHandle
0x18002d51b  call    cs:__imp_OpenProcessToken
0x18002d521  test    eax, eax
0x18002d523  jnz     short loc_18002D53A
0x18002d525  call    GetLastFailureAsHRESULT
0x18002d52a  mov     ebx, eax
0x18002d52c  mov     [rbp+var_40], eax
0x18002d52f  mov     eax, 26Fh
0x18002d534  mov     [rbp+var_3A], ax
0x18002d538  jmp     short loc_18002D5B0
0x18002d53a  mov     eax, 26Fh
0x18002d53f  jmp     short loc_18002D593
0x18002d541  mov     rcx, [rbp+TokenHandle]; hObject
0x18002d545  lea     rax, [rcx-1]
0x18002d549  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002d54d  ja      short loc_18002D55D
0x18002d54f  call    cs:__imp_CloseHandle
0x18002d555  mov     [rbp+TokenHandle], 0
0x18002d55d  call    cs:__imp_GetCurrentThread
0x18002d563  mov     edx, 28h ; '('; DesiredAccess
0x18002d568  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18002d56c  mov     rcx, rax; ThreadHandle
0x18002d56f  lea     r8d, [rdx-27h]; OpenAsSelf
0x18002d573  call    cs:__imp_OpenThreadToken
0x18002d579  test    eax, eax
0x18002d57b  jnz     short loc_18002D58E
0x18002d57d  call    GetLastFailureAsHRESULT
0x18002d582  mov     ebx, eax
0x18002d584  mov     [rbp+var_40], eax
0x18002d587  mov     eax, 276h
0x18002d58c  jmp     short loc_18002D534
0x18002d58e  mov     eax, 276h
0x18002d593  xor     ebx, ebx
0x18002d595  mov     [rbp+var_40], ebx
0x18002d598  mov     [rbp+var_3C], ax
0x18002d59c  jmp     short loc_18002D5A1
0x18002d59e  mov     ebx, [rbp+var_40]
0x18002d5a1  mov     rax, [rbp+TokenHandle]
0x18002d5a5  mov     [rdi], rax
0x18002d5a8  mov     [rbp+TokenHandle], 0
0x18002d5b0  mov     rcx, [rbp+TokenHandle]; hObject
0x18002d5b4  lea     rdx, [rcx-1]
0x18002d5b8  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002d5bc  ja      short loc_18002D5CC
0x18002d5be  call    cs:__imp_CloseHandle
0x18002d5c4  mov     [rbp+TokenHandle], 0
0x18002d5cc  lea     rcx, [rbp+var_40]; this
0x18002d5d0  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18002d5d5  lea     r11, [rsp+60h+var_s0]
0x18002d5da  mov     eax, ebx
0x18002d5dc  mov     rbx, [r11+10h]
0x18002d5e0  mov     rdi, [r11+20h]
0x18002d5e4  mov     rsp, r11
0x18002d5e7  pop     rbp
0x18002d5e8  retn
```
