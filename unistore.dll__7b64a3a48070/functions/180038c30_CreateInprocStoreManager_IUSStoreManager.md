# _CreateInprocStoreManager(IUSStoreManager * *)

- ea: `0x180038c30`
- end: `0x180038d5c`
- name: `?_CreateInprocStoreManager@@YAJPEAPEAUIUSStoreManager@@@Z`
- size: `300`
- prototype: `__int64 __fastcall(struct IUSStoreManager **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800390c0`

## callees

- `0x1800068f0`
- `0x180038c30`
- `0x1800396c8`
- `0x180039898`
- `0x18006f180`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038d28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038d45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038d28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038d45`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180038c72`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180038c72`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180038c8b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180038c8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180038c9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180038c9d`

## string_xrefs

- `0x180038c4c`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\createstore.cpp`
- `0x180038d0c`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\createstore.cpp`
- `0x180038c6b`: `unistore.dll`

## pseudocode

```c
__int64 __fastcall _CreateInprocStoreManager(struct IUSStoreManager **a1)
{
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rbx
  unsigned int v4; // ebx
  void *v6; // rax
  __int64 v7; // r9
  __int64 v8; // rdx
  signed int LastError; // eax
  signed int v10; // eax
  DWORD CurrentProcessId; // [rsp+48h] [rbp+10h] BYREF

  if ( !g_fInProc )
    Log_AssertionEvent(
      a1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\createstore.cpp",
      110);
  if ( !g_fForceInproc )
    g_RundownProtectionId = -2;
  ModuleHandleW = GetModuleHandleW(L"unistore.dll");
  if ( !ModuleHandleW )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    v7 = 123;
    goto LABEL_14;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "GetRealStoreManager");
  if ( !ProcAddress )
  {
    v10 = GetLastError();
    v4 = v10;
    if ( v10 > 0 )
      v4 = (unsigned __int16)v10 | 0x80070000;
    v7 = 126;
LABEL_14:
    v8 = 0;
    goto LABEL_12;
  }
  CurrentProcessId = GetCurrentProcessId();
  if ( (Microsoft_Windows_UserDataAccess_UnifiedStoreEnableBits & 0x20) != 0 )
  {
    v6 = _t_address();
    EtwTraceMessage(&ETWMESSAGE, v6, &CurrentProcessId, 4, 0, -1);
  }
  v4 = ((__int64 (__fastcall *)(struct IUSStoreManager **))ProcAddress)(a1);
  if ( (v4 & 0x80000000) == 0 )
    return 0;
  v7 = 131;
  v8 = 1;
LABEL_12:
  Log_UnistoreHREvent_0(
    v4,
    v8,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\createstore.cpp",
    v7);
  return v4;
}

```

## disassembly

```asm
0x180038c30  mov     [rsp+arg_0], rbx
0x180038c35  push    rdi
0x180038c36  sub     rsp, 30h
0x180038c3a  cmp     cs:?g_fInProc@@3HA, 0; int g_fInProc
0x180038c41  mov     rdi, rcx
0x180038c44  jnz     short loc_180038C58
0x180038c46  mov     r8d, 6Eh ; 'n'
0x180038c4c  lea     rdx, aOnecoreuapBase_47; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180038c53  call    Log_AssertionEvent
0x180038c58  cmp     cs:?g_fForceInproc@@3HA, 0; int g_fForceInproc
0x180038c5f  jnz     short loc_180038C6B
0x180038c61  mov     cs:?g_RundownProtectionId@@3KA, 0FFFFFFFEh; ulong g_RundownProtectionId
0x180038c6b  lea     rcx, ModuleName; "unistore.dll"
0x180038c72  call    cs:__imp_GetModuleHandleW
0x180038c78  test    rax, rax
0x180038c7b  jz      loc_180038D28
0x180038c81  lea     rdx, ProcName; "GetRealStoreManager"
0x180038c88  mov     rcx, rax; hModule
0x180038c8b  call    cs:__imp_GetProcAddress
0x180038c91  mov     rbx, rax
0x180038c94  test    rax, rax
0x180038c97  jz      loc_180038D45
0x180038c9d  call    cs:__imp_GetCurrentProcessId
0x180038ca3  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UnifiedStoreEnableBits, 20h
0x180038caa  mov     [rsp+38h+arg_8], eax
0x180038cae  jnz     short loc_180038CCE
0x180038cb0  mov     rcx, rdi
0x180038cb3  mov     rax, rbx
0x180038cb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038cbb  mov     ebx, eax
0x180038cbd  test    eax, eax
0x180038cbf  js      short loc_180038D01
0x180038cc1  xor     eax, eax
0x180038cc3  mov     rbx, [rsp+38h+arg_0]
0x180038cc8  add     rsp, 30h
0x180038ccc  pop     rdi
0x180038ccd  retn
0x180038cce  call    ?_t_address@@YAPEAXXZ; _t_address(void)
0x180038cd3  mov     rdx, rax; void *
0x180038cd6  mov     [rsp+38h+var_10], 0FFFFFFFFFFFFFFFFh
0x180038cdf  mov     r9d, 4
0x180038ce5  mov     [rsp+38h+var_18], 0
0x180038cee  lea     r8, [rsp+38h+arg_8]
0x180038cf3  lea     rcx, _ETWMESSAGE; EventDescriptor
0x180038cfa  call    ?EtwTraceMessage@@YAXPEBU_EVENT_DESCRIPTOR@@PEAXZZ; EtwTraceMessage(_EVENT_DESCRIPTOR const *,void *,...)
0x180038cff  jmp     short loc_180038CB0
0x180038d01  mov     r9d, 83h
0x180038d07  mov     edx, 1
0x180038d0c  lea     r8, aOnecoreuapBase_47; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180038d13  mov     ecx, ebx
0x180038d15  call    Log_UnistoreHREvent_0
0x180038d1a  mov     eax, ebx
0x180038d1c  jmp     short loc_180038CC3
0x180038d1e  mov     r9d, 7Eh ; '~'
0x180038d24  xor     edx, edx
0x180038d26  jmp     short loc_180038D0C
0x180038d28  call    cs:__imp_GetLastError
0x180038d2e  mov     ebx, eax
0x180038d30  test    eax, eax
0x180038d32  jle     short loc_180038D3D
0x180038d34  movzx   ebx, ax
0x180038d37  or      ebx, 80070000h
0x180038d3d  mov     r9d, 7Bh ; '{'
0x180038d43  jmp     short loc_180038D24
0x180038d45  call    cs:__imp_GetLastError
0x180038d4b  mov     ebx, eax
0x180038d4d  test    eax, eax
0x180038d4f  jle     short loc_180038D1E
0x180038d51  movzx   ebx, ax
0x180038d54  or      ebx, 80070000h
0x180038d5a  jmp     short loc_180038D1E
```
