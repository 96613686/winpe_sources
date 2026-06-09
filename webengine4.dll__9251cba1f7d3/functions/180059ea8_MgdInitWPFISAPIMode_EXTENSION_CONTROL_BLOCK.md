# MgdInitWPFISAPIMode(_EXTENSION_CONTROL_BLOCK *)

- ea: `0x180059ea8`
- end: `0x18005a091`
- name: `?MgdInitWPFISAPIMode@@YAJPEAU_EXTENSION_CONTROL_BLOCK@@@Z`
- size: `489`
- prototype: `__int64 __fastcall(struct _EXTENSION_CONTROL_BLOCK *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180014a40`

## callees

- `0x180059ea8`
- `0x18005b928`
- `0x180065b60`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180059f62`
- `KERNEL32!CloseHandle` at `0x18005a07b`
- `KERNEL32!CloseHandle` at `0x180059f62`
- `KERNEL32!CloseHandle` at `0x18005a07b`
- `KERNEL32!GetLastError` at `0x180059f20`
- `KERNEL32!GetLastError` at `0x180059f4d`
- `KERNEL32!GetLastError` at `0x180059f9c`
- `KERNEL32!GetLastError` at `0x18005a066`
- `KERNEL32!GetLastError` at `0x180059f20`
- `KERNEL32!GetLastError` at `0x180059f4d`
- `KERNEL32!GetLastError` at `0x180059f9c`
- `KERNEL32!GetLastError` at `0x18005a066`
- `KERNEL32!EnterCriticalSection` at `0x180059ee6`
- `KERNEL32!EnterCriticalSection` at `0x180059ee6`
- `KERNEL32!LeaveCriticalSection` at `0x18005a04b`
- `KERNEL32!LeaveCriticalSection` at `0x18005a04b`
- `KERNEL32!GetCurrentThread` at `0x180059efe`
- `KERNEL32!GetCurrentThread` at `0x180059efe`
- `ADVAPI32!SetThreadToken` at `0x18005a05c`
- `ADVAPI32!SetThreadToken` at `0x18005a05c`
- `ADVAPI32!OpenThreadToken` at `0x180059f16`
- `ADVAPI32!OpenThreadToken` at `0x180059f16`
- `ADVAPI32!RevertToSelf` at `0x180059f43`
- `ADVAPI32!RevertToSelf` at `0x180059f43`

## pseudocode

```c
__int64 __fastcall MgdInitWPFISAPIMode(struct _EXTENSION_CONTROL_BLOCK *a1)
{
  signed int inited; // ebx
  HANDLE CurrentThread; // rax
  signed int v4; // eax
  signed int v5; // eax
  HCONN ConnID; // rcx
  BOOL (__stdcall *ServerSupportFunction)(HCONN, DWORD, LPVOID, LPDWORD, LPDWORD); // rax
  signed int LastError; // eax
  HCONN v9; // rcx
  BOOL (__stdcall *v10)(HCONN, DWORD, LPVOID, LPDWORD, LPDWORD); // rax
  signed int v11; // eax
  unsigned __int64 v13; // [rsp+30h] [rbp-10h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp+28h] BYREF
  __int64 v15; // [rsp+70h] [rbp+30h] BYREF
  int (*v16)(const unsigned __int16 *, const unsigned __int16 *, unsigned int, void **); // [rsp+78h] [rbp+38h] BYREF

  inited = 0;
  TokenHandle = 0;
  if ( !g_fIsapiWorkerProcessInited )
  {
    if ( g_fIsapiLockInited )
    {
      EnterCriticalSection(&g_csIsapiModeWPFLock);
      if ( !g_fIsapiWorkerProcessInited )
      {
        CurrentThread = GetCurrentThread();
        if ( OpenThreadToken(CurrentThread, 0x2000Cu, 1, &TokenHandle) || (v4 = GetLastError(), v4 == 1008) )
        {
          if ( !TokenHandle || RevertToSelf() )
          {
            ConnID = a1->ConnID;
            ServerSupportFunction = a1->ServerSupportFunction;
            v16 = 0;
            if ( ((unsigned int (__fastcall *)(HCONN, __int64, int (**)(const unsigned __int16 *, const unsigned __int16 *, unsigned int, void **), _QWORD, _QWORD))ServerSupportFunction)(
                   ConnID,
                   1048,
                   &v16,
                   0,
                   0) )
            {
              inited = InitClrHost(&g_pProcessHost, v16);
            }
            else
            {
              LastError = GetLastError();
              if ( LastError != 120 )
              {
                inited = (unsigned __int16)LastError | 0x80070000;
                if ( LastError <= 0 )
                  inited = LastError;
              }
            }
            if ( inited >= 0 )
            {
              v9 = a1->ConnID;
              v10 = a1->ServerSupportFunction;
              v15 = 0;
              if ( ((unsigned int (__fastcall *)(HCONN, __int64, __int64 *, _QWORD, _QWORD))v10)(v9, 1047, &v15, 0, 0) )
              {
                inited = (*(__int64 (__fastcall **)(__int64, __int64, unsigned __int64 *))(*(_QWORD *)v15 + 24LL))(
                           v15,
                           1,
                           &v13);
                if ( inited < 0 )
                  inited = 0;
                else
                  g_MemoryLimitKB = v13 >> 10;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
              }
            }
            g_fIsapiWorkerProcessInited = 1;
          }
          else
          {
            v5 = GetLastError();
            inited = (unsigned __int16)v5 | 0x80070000;
            if ( v5 <= 0 )
              inited = v5;
            CloseHandle(TokenHandle);
            TokenHandle = 0;
          }
        }
        else
        {
          inited = (unsigned __int16)v4 | 0x80070000;
          if ( v4 <= 0 )
            inited = v4;
        }
      }
      LeaveCriticalSection(&g_csIsapiModeWPFLock);
      if ( TokenHandle )
      {
        if ( !SetThreadToken(0, TokenHandle) )
        {
          v11 = GetLastError();
          inited = (unsigned __int16)v11 | 0x80070000;
          if ( v11 <= 0 )
            inited = v11;
        }
        CloseHandle(TokenHandle);
      }
    }
    else
    {
      return (unsigned int)-2147418113;
    }
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180059ea8  mov     [rsp-18h+arg_0], rbx
0x180059ead  push    rbp
0x180059eae  push    rdi
0x180059eaf  push    r14
0x180059eb1  mov     rbp, rsp
0x180059eb4  sub     rsp, 40h
0x180059eb8  xor     ebx, ebx
0x180059eba  mov     rdi, rcx
0x180059ebd  and     [rbp+TokenHandle], rbx
0x180059ec1  cmp     cs:?g_fIsapiWorkerProcessInited@@3HA, ebx; int g_fIsapiWorkerProcessInited
0x180059ec7  jnz     loc_18005A081
0x180059ecd  cmp     cs:?g_fIsapiLockInited@@3HA, ebx; int g_fIsapiLockInited
0x180059ed3  jnz     short loc_180059EDF
0x180059ed5  mov     ebx, 8000FFFFh
0x180059eda  jmp     loc_18005A081
0x180059edf  lea     rcx, ?g_csIsapiModeWPFLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180059ee6  call    cs:__imp_EnterCriticalSection
0x180059eec  cmp     cs:?g_fIsapiWorkerProcessInited@@3HA, ebx; int g_fIsapiWorkerProcessInited
0x180059ef2  mov     r14d, 80070000h
0x180059ef8  jnz     loc_18005A044
0x180059efe  call    cs:__imp_GetCurrentThread
0x180059f04  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180059f08  mov     edx, 2000Ch; DesiredAccess
0x180059f0d  mov     rcx, rax; ThreadHandle
0x180059f10  mov     r8d, 1; OpenAsSelf
0x180059f16  call    cs:__imp_OpenThreadToken
0x180059f1c  test    eax, eax
0x180059f1e  jnz     short loc_180059F3D
0x180059f20  call    cs:__imp_GetLastError
0x180059f26  cmp     eax, 3F0h
0x180059f2b  jz      short loc_180059F3D
0x180059f2d  movzx   ebx, ax
0x180059f30  or      ebx, r14d
0x180059f33  test    eax, eax
0x180059f35  cmovle  ebx, eax
0x180059f38  jmp     loc_18005A044
0x180059f3d  cmp     [rbp+TokenHandle], rbx
0x180059f41  jz      short loc_180059F72
0x180059f43  call    cs:__imp_RevertToSelf
0x180059f49  test    eax, eax
0x180059f4b  jnz     short loc_180059F72
0x180059f4d  call    cs:__imp_GetLastError
0x180059f53  mov     rcx, [rbp+TokenHandle]; hObject
0x180059f57  movzx   ebx, ax
0x180059f5a  or      ebx, r14d
0x180059f5d  test    eax, eax
0x180059f5f  cmovle  ebx, eax
0x180059f62  call    cs:__imp_CloseHandle
0x180059f68  and     [rbp+TokenHandle], 0
0x180059f6d  jmp     loc_18005A044
0x180059f72  mov     rcx, [rdi+8]
0x180059f76  lea     r8, [rbp+arg_18]
0x180059f7a  mov     rax, [rdi+0B8h]
0x180059f81  xor     r9d, r9d
0x180059f84  and     [rbp+arg_18], rbx
0x180059f88  mov     edx, 418h
0x180059f8d  and     [rsp+40h+var_20], rbx
0x180059f92  call    cs:__guard_dispatch_icall_fptr
0x180059f98  test    eax, eax
0x180059f9a  jnz     short loc_180059FB4
0x180059f9c  call    cs:__imp_GetLastError
0x180059fa2  cmp     eax, 78h ; 'x'
0x180059fa5  jz      short loc_180059FC6
0x180059fa7  movzx   ebx, ax
0x180059faa  or      ebx, r14d
0x180059fad  test    eax, eax
0x180059faf  cmovle  ebx, eax
0x180059fb2  jmp     short loc_180059FC6
0x180059fb4  mov     rdx, [rbp+arg_18]; int (*)(const unsigned __int16 *, const unsigned __int16 *, unsigned int, void **)
0x180059fb8  lea     rcx, ?g_pProcessHost@@3PEAUIProcessHost@@EA; struct IProcessHost **
0x180059fbf  call    ?InitClrHost@@YAJPEAPEAUIProcessHost@@P6AJPEBG1KPEAPEAX@Z@Z; InitClrHost(IProcessHost * *,long (*)(ushort const *,ushort const *,ulong,void * *))
0x180059fc4  mov     ebx, eax
0x180059fc6  test    ebx, ebx
0x180059fc8  js      short loc_18005A03A
0x180059fca  mov     rcx, [rdi+8]
0x180059fce  lea     r8, [rbp+arg_10]
0x180059fd2  mov     rax, [rdi+0B8h]
0x180059fd9  xor     r9d, r9d
0x180059fdc  and     [rbp+arg_10], 0
0x180059fe1  mov     edx, 417h
0x180059fe6  and     [rsp+40h+var_20], 0
0x180059fec  call    cs:__guard_dispatch_icall_fptr
0x180059ff2  test    eax, eax
0x180059ff4  jz      short loc_18005A03A
0x180059ff6  mov     rcx, [rbp+arg_10]
0x180059ffa  lea     r8, [rbp+var_10]
0x180059ffe  mov     edx, 1
0x18005a003  mov     rax, [rcx]
0x18005a006  mov     rax, [rax+18h]
0x18005a00a  call    cs:__guard_dispatch_icall_fptr
0x18005a010  mov     ebx, eax
0x18005a012  test    eax, eax
0x18005a014  js      short loc_18005A027
0x18005a016  mov     rax, [rbp+var_10]
0x18005a01a  shr     rax, 0Ah
0x18005a01e  mov     cs:?g_MemoryLimitKB@@3_KA, rax; unsigned __int64 g_MemoryLimitKB
0x18005a025  jmp     short loc_18005A029
0x18005a027  xor     ebx, ebx
0x18005a029  mov     rcx, [rbp+arg_10]
0x18005a02d  mov     rax, [rcx]
0x18005a030  mov     rax, [rax+8]
0x18005a034  call    cs:__guard_dispatch_icall_fptr
0x18005a03a  mov     cs:?g_fIsapiWorkerProcessInited@@3HA, 1; int g_fIsapiWorkerProcessInited
0x18005a044  lea     rcx, ?g_csIsapiModeWPFLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005a04b  call    cs:__imp_LeaveCriticalSection
0x18005a051  mov     rdx, [rbp+TokenHandle]; Token
0x18005a055  test    rdx, rdx
0x18005a058  jz      short loc_18005A081
0x18005a05a  xor     ecx, ecx; Thread
0x18005a05c  call    cs:__imp_SetThreadToken
0x18005a062  test    eax, eax
0x18005a064  jnz     short loc_18005A077
0x18005a066  call    cs:__imp_GetLastError
0x18005a06c  movzx   ebx, ax
0x18005a06f  or      ebx, r14d
0x18005a072  test    eax, eax
0x18005a074  cmovle  ebx, eax
0x18005a077  mov     rcx, [rbp+TokenHandle]; hObject
0x18005a07b  call    cs:__imp_CloseHandle
0x18005a081  mov     eax, ebx
0x18005a083  mov     rbx, [rsp+40h+arg_0]
0x18005a088  add     rsp, 40h
0x18005a08c  pop     r14
0x18005a08e  pop     rdi
0x18005a08f  pop     rbp
0x18005a090  retn
```
