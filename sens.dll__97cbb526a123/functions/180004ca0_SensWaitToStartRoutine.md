# SensWaitToStartRoutine

- ea: `0x180004ca0`
- end: `0x180004deb`
- name: `SensWaitToStartRoutine`
- size: `331`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x180004ca0`
- `0x180005960`
- `0x18000b010`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180004d66`
- `RPCRT4!NdrClientCall3` at `0x180004d66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004dd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004de0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004dd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004de0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004d70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004d70`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004d83`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004d96`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004da9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004dbb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004d83`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004d96`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004da9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004dbb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180004cf8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180004cf8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180004cc1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180004cc1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004cdd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004cdd`

## string_xrefs

- `0x180004cb8`: `ES.DLL`

## pseudocode

```c
__int64 __fastcall SensWaitToStartRoutine(PVOID Parameter)
{
  HMODULE Library; // rax
  HMODULE v3; // rdi
  FARPROC ProcAddress; // rax
  int v5; // ecx
  __int64 v7; // [rsp+30h] [rbp-40h] BYREF
  int v8; // [rsp+38h] [rbp-38h]
  int v9; // [rsp+3Ch] [rbp-34h]
  __int64 v10; // [rsp+40h] [rbp-30h]
  __int64 v11; // [rsp+48h] [rbp-28h]
  __int64 v12; // [rsp+50h] [rbp-20h]
  int v13; // [rsp+58h] [rbp-18h]
  int v14; // [rsp+5Ch] [rbp-14h]
  int v15; // [rsp+60h] [rbp-10h]
  int v16; // [rsp+64h] [rbp-Ch]

  Library = LoadLibraryExW(L"ES.DLL", 0, 0);
  v3 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "NotifyLogonUser");
    if ( ProcAddress )
      ((void (__fastcall *)(_QWORD))ProcAddress)(*((_QWORD *)Parameter + 4));
    else
      GetLastError();
    FreeLibrary(v3);
  }
  else
  {
    GetLastError();
  }
  v5 = *((_DWORD *)Parameter + 1);
  v10 = *((_QWORD *)Parameter + 1);
  v11 = *((_QWORD *)Parameter + 2);
  v12 = *((_QWORD *)Parameter + 3);
  v13 = *((_DWORD *)Parameter + 8);
  v14 = *((_DWORD *)Parameter + 10);
  v7 = 0x8000;
  v16 = 0;
  v8 = 56;
  v9 = v5;
  v15 = v5;
  if ( !(unsigned int)DoRpcSetup() )
    NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0, 0, ghSensNotify, &v7);
  CloseHandle(*((HANDLE *)Parameter + 4));
  HeapFree(ghSensHeap, 0, *((LPVOID *)Parameter + 1));
  HeapFree(ghSensHeap, 0, *((LPVOID *)Parameter + 2));
  HeapFree(ghSensHeap, 0, *((LPVOID *)Parameter + 3));
  HeapFree(ghSensHeap, 0, Parameter);
  return 0;
}

```

## disassembly

```asm
0x180004ca0  mov     [rsp-8+arg_0], rbx
0x180004ca5  mov     [rsp-8+arg_8], rdi
0x180004caa  push    rbp
0x180004cab  mov     rbp, rsp
0x180004cae  sub     rsp, 70h
0x180004cb2  mov     rbx, rcx
0x180004cb5  xor     r8d, r8d; dwFlags
0x180004cb8  lea     rcx, aEsDll; "ES.DLL"
0x180004cbf  xor     edx, edx; hFile
0x180004cc1  call    cs:__imp_LoadLibraryExW
0x180004cc7  mov     rdi, rax
0x180004cca  test    rax, rax
0x180004ccd  jz      loc_180004DD5
0x180004cd3  lea     rdx, aNotifylogonuse; "NotifyLogonUser"
0x180004cda  mov     rcx, rax; hModule
0x180004cdd  call    cs:__imp_GetProcAddress
0x180004ce3  test    rax, rax
0x180004ce6  jz      loc_180004DE0
0x180004cec  mov     rcx, [rbx+20h]
0x180004cf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cf5  mov     rcx, rdi; hLibModule
0x180004cf8  call    cs:__imp_FreeLibrary
0x180004cfe  mov     rax, [rbx+8]
0x180004d02  mov     ecx, [rbx+4]
0x180004d05  mov     [rbp+var_30], rax
0x180004d09  mov     rax, [rbx+10h]
0x180004d0d  mov     [rbp+var_28], rax
0x180004d11  mov     rax, [rbx+18h]
0x180004d15  mov     [rbp+var_20], rax
0x180004d19  mov     eax, [rbx+20h]
0x180004d1c  mov     [rbp+var_18], eax
0x180004d1f  mov     eax, [rbx+28h]
0x180004d22  mov     [rbp+var_14], eax
0x180004d25  mov     [rbp+var_40], 8000h
0x180004d2d  mov     [rbp+var_C], 0
0x180004d34  mov     [rbp+var_38], 38h ; '8'
0x180004d3b  mov     [rbp+var_34], ecx
0x180004d3e  mov     [rbp+var_10], ecx
0x180004d41  call    ?DoRpcSetup@@YAJXZ; DoRpcSetup(void)
0x180004d46  test    eax, eax
0x180004d48  jnz     short loc_180004D6C
0x180004d4a  mov     r9, cs:?ghSensNotify@@3PEAXEA; void * ghSensNotify
0x180004d51  lea     rax, [rbp+var_40]
0x180004d55  xor     r8d, r8d; pReturnValue
0x180004d58  mov     [rsp+70h+var_50], rax
0x180004d5d  xor     edx, edx; nProcNum
0x180004d5f  lea     rcx, pProxyInfo; pProxyInfo
0x180004d66  call    cs:__imp_NdrClientCall3
0x180004d6c  mov     rcx, [rbx+20h]; hObject
0x180004d70  call    cs:__imp_CloseHandle
0x180004d76  mov     r8, [rbx+8]; lpMem
0x180004d7a  xor     edx, edx; dwFlags
0x180004d7c  mov     rcx, cs:?ghSensHeap@@3PEAXEA; hHeap
0x180004d83  call    cs:__imp_HeapFree
0x180004d89  mov     r8, [rbx+10h]; lpMem
0x180004d8d  xor     edx, edx; dwFlags
0x180004d8f  mov     rcx, cs:?ghSensHeap@@3PEAXEA; hHeap
0x180004d96  call    cs:__imp_HeapFree
0x180004d9c  mov     r8, [rbx+18h]; lpMem
0x180004da0  xor     edx, edx; dwFlags
0x180004da2  mov     rcx, cs:?ghSensHeap@@3PEAXEA; hHeap
0x180004da9  call    cs:__imp_HeapFree
0x180004daf  mov     rcx, cs:?ghSensHeap@@3PEAXEA; hHeap
0x180004db6  mov     r8, rbx; lpMem
0x180004db9  xor     edx, edx; dwFlags
0x180004dbb  call    cs:__imp_HeapFree
0x180004dc1  lea     r11, [rsp+70h+var_s0]
0x180004dc6  xor     eax, eax
0x180004dc8  mov     rbx, [r11+10h]
0x180004dcc  mov     rdi, [r11+18h]
0x180004dd0  mov     rsp, r11
0x180004dd3  pop     rbp
0x180004dd4  retn
0x180004dd5  call    cs:__imp_GetLastError
0x180004ddb  jmp     loc_180004CFE
0x180004de0  call    cs:__imp_GetLastError
0x180004de6  jmp     loc_180004CF5
```
