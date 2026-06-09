# HwCfgGetCurrentKey

- ea: `0x14001c2e0`
- end: `0x14001c539`
- name: `HwCfgGetCurrentKey`
- size: `601`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x14001c228`

## callees

- `0x14001c2e0`
- `0x140094020`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001c33a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001c33a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14001c31e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14001c31e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14001c447`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14001c447`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001c42c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001c42c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001c38f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001c41e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001c38f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001c41e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001c39d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001c39d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001c401`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001c46d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001c50e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001c401`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001c46d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001c50e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001c491`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001c523`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001c52e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001c491`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001c523`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001c52e`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x14001c4b7`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x14001c4e1`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x14001c4b7`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x14001c4e1`

## string_xrefs

- `0x14001c358`: `System\HardwareConfig`
- `0x14001c3bb`: `System\HardwareConfig`
- `0x14001c4fc`: `System\HardwareConfig`
- `0x14001c363`: `HardwareConfigState`
- `0x14001c3c5`: `HardwareConfigState`
- `0x14001c30b`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall HwCfgGetCurrentKey(int a1, HKEY *a2)
{
  HKEY v3; // rsi
  HMODULE Library; // rax
  HMODULE v5; // r14
  FARPROC ProcAddress; // rax
  __int64 (__fastcall *v7)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // r15
  NTSTATUS v8; // eax
  unsigned int v9; // ebx
  HANDLE ProcessHeap; // rax
  WCHAR *v11; // rdi
  NTSTATUS v12; // eax
  ULONG v13; // ebx
  HANDLE v14; // rax
  SIZE_T dwBytes; // [rsp+80h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+48h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp+50h] BYREF

  LODWORD(dwBytes) = a1;
  phkResult = 0;
  if ( !a2 )
    return 87;
  v3 = 0;
  LODWORD(dwBytes) = 0;
  hKey = 0;
  Library = LoadLibraryExW(L"ntdll.dll", 0, 0);
  v5 = Library;
  if ( Library
    && (ProcAddress = GetProcAddress(Library, "RtlGetPersistedStateLocation"),
        (v7 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))ProcAddress) != 0) )
  {
    v8 = ((__int64 (__fastcall *)(const wchar_t *, _QWORD, const WCHAR *, _QWORD, _QWORD, _DWORD, SIZE_T *))ProcAddress)(
           L"HardwareConfigState",
           0,
           L"System\\HardwareConfig",
           0,
           0,
           0,
           &dwBytes);
    if ( v8 >= 0 )
    {
      v13 = 1359;
      goto LABEL_11;
    }
    if ( v8 != -2147483643 )
    {
      v13 = RtlNtStatusToDosErrorNoTeb(v8);
      goto LABEL_11;
    }
    v9 = dwBytes;
    ProcessHeap = GetProcessHeap();
    v11 = (WCHAR *)HeapAlloc(ProcessHeap, 0, v9);
    if ( !v11 )
    {
      v13 = 8;
      goto LABEL_11;
    }
    v12 = v7(L"HardwareConfigState", 0, L"System\\HardwareConfig", 0, v11, dwBytes, &dwBytes);
    if ( v12 < 0 )
    {
      v13 = RtlNtStatusToDosErrorNoTeb(v12);
      goto LABEL_10;
    }
    v13 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v11, 0, 8u, &hKey);
    if ( v13 )
    {
LABEL_10:
      v14 = GetProcessHeap();
      HeapFree(v14, 0, v11);
      goto LABEL_11;
    }
  }
  else
  {
    v11 = 0;
    v13 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\HardwareConfig", 0, 8u, &hKey);
    if ( v13 )
      goto LABEL_11;
  }
  v3 = hKey;
  hKey = 0;
  if ( v11 )
    goto LABEL_10;
LABEL_11:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v5 )
    FreeLibrary(v5);
  if ( !v13 )
  {
    v13 = RegOpenKeyExW(v3, L"Current", 0, 0x20019u, &phkResult);
    if ( !v13 )
    {
      *a2 = phkResult;
      phkResult = 0;
    }
  }
  if ( v3 )
    RegCloseKey(v3);
  if ( phkResult )
    RegCloseKey(phkResult);
  return v13;
}

```

## disassembly

```asm
0x14001c2e0  mov     dword ptr [rsp-38h+dwBytes], ecx
0x14001c2e4  push    rbp
0x14001c2e5  push    rbx
0x14001c2e6  push    rsi
0x14001c2e7  push    rdi
0x14001c2e8  push    r12
0x14001c2ea  push    r14
0x14001c2ec  push    r15
0x14001c2ee  mov     rbp, rsp
0x14001c2f1  sub     rsp, 40h
0x14001c2f5  mov     [rbp+arg_10], 0
0x14001c2fd  mov     r12, rdx
0x14001c300  test    rdx, rdx
0x14001c303  jz      loc_14001C4C4
0x14001c309  xor     esi, esi
0x14001c30b  lea     rcx, LibFileName; "ntdll.dll"
0x14001c312  xor     r8d, r8d; dwFlags
0x14001c315  mov     dword ptr [rbp+dwBytes], esi
0x14001c318  xor     edx, edx; hFile
0x14001c31a  mov     [rbp+hKey], rsi
0x14001c31e  call    cs:__imp_LoadLibraryExW
0x14001c324  mov     r14, rax
0x14001c327  test    rax, rax
0x14001c32a  jz      loc_14001C4EE
0x14001c330  lea     rdx, ProcName; "RtlGetPersistedStateLocation"
0x14001c337  mov     rcx, rax; hModule
0x14001c33a  call    cs:__imp_GetProcAddress
0x14001c340  mov     r15, rax
0x14001c343  test    rax, rax
0x14001c346  jz      loc_14001C4EE
0x14001c34c  lea     rax, [rbp+dwBytes]
0x14001c350  xor     r9d, r9d
0x14001c353  mov     [rsp+40h+var_10], rax
0x14001c358  lea     r8, aSystemHardware; "System\\HardwareConfig"
0x14001c35f  mov     [rsp+40h+var_18], esi
0x14001c363  lea     rcx, aHardwareconfig; "HardwareConfigState"
0x14001c36a  mov     rax, r15
0x14001c36d  mov     [rsp+40h+phkResult], rsi
0x14001c372  xor     edx, edx
0x14001c374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c379  test    eax, eax
0x14001c37b  jns     loc_14001C4CB
0x14001c381  cmp     eax, 80000005h
0x14001c386  jnz     loc_14001C4B5
0x14001c38c  mov     ebx, dword ptr [rbp+dwBytes]
0x14001c38f  call    cs:__imp_GetProcessHeap
0x14001c395  mov     r8d, ebx; dwBytes
0x14001c398  xor     edx, edx; dwFlags
0x14001c39a  mov     rcx, rax; hHeap
0x14001c39d  call    cs:__imp_HeapAlloc
0x14001c3a3  mov     rdi, rax
0x14001c3a6  test    rax, rax
0x14001c3a9  jz      loc_14001C4D5
0x14001c3af  lea     rax, [rbp+dwBytes]
0x14001c3b3  xor     r9d, r9d
0x14001c3b6  mov     [rsp+40h+var_10], rax
0x14001c3bb  lea     r8, aSystemHardware; "System\\HardwareConfig"
0x14001c3c2  mov     eax, dword ptr [rbp+dwBytes]
0x14001c3c5  lea     rcx, aHardwareconfig; "HardwareConfigState"
0x14001c3cc  mov     [rsp+40h+var_18], eax
0x14001c3d0  xor     edx, edx
0x14001c3d2  mov     rax, r15
0x14001c3d5  mov     [rsp+40h+phkResult], rdi
0x14001c3da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c3df  test    eax, eax
0x14001c3e1  js      loc_14001C4DF
0x14001c3e7  lea     rax, [rbp+hKey]
0x14001c3eb  xor     r8d, r8d; ulOptions
0x14001c3ee  lea     r9d, [rsi+8]; samDesired
0x14001c3f2  mov     [rsp+40h+phkResult], rax; phkResult
0x14001c3f7  mov     rdx, rdi; lpSubKey
0x14001c3fa  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14001c401  call    cs:__imp_RegOpenKeyExW
0x14001c407  mov     ebx, eax
0x14001c409  test    eax, eax
0x14001c40b  jnz     short loc_14001C41E
0x14001c40d  mov     rsi, [rbp+hKey]
0x14001c411  mov     [rbp+hKey], 0
0x14001c419  test    rdi, rdi
0x14001c41c  jz      short loc_14001C432
0x14001c41e  call    cs:__imp_GetProcessHeap
0x14001c424  mov     r8, rdi; lpMem
0x14001c427  xor     edx, edx; dwFlags
0x14001c429  mov     rcx, rax; hHeap
0x14001c42c  call    cs:__imp_HeapFree
0x14001c432  mov     rcx, [rbp+hKey]; hKey
0x14001c436  test    rcx, rcx
0x14001c439  jnz     loc_14001C523
0x14001c43f  test    r14, r14
0x14001c442  jz      short loc_14001C44D
0x14001c444  mov     rcx, r14; hLibModule
0x14001c447  call    cs:__imp_FreeLibrary
0x14001c44d  test    ebx, ebx
0x14001c44f  jnz     short loc_14001C489
0x14001c451  lea     rax, [rbp+arg_10]
0x14001c455  mov     r9d, 20019h; samDesired
0x14001c45b  xor     r8d, r8d; ulOptions
0x14001c45e  mov     [rsp+40h+phkResult], rax; phkResult
0x14001c463  lea     rdx, aCurrent; "Current"
0x14001c46a  mov     rcx, rsi; hKey
0x14001c46d  call    cs:__imp_RegOpenKeyExW
0x14001c473  mov     ebx, eax
0x14001c475  test    eax, eax
0x14001c477  jnz     short loc_14001C489
0x14001c479  mov     rcx, [rbp+arg_10]
0x14001c47d  mov     [r12], rcx
0x14001c481  mov     [rbp+arg_10], 0
0x14001c489  test    rsi, rsi
0x14001c48c  jz      short loc_14001C497
0x14001c48e  mov     rcx, rsi; hKey
0x14001c491  call    cs:__imp_RegCloseKey
0x14001c497  mov     rcx, [rbp+arg_10]; hKey
0x14001c49b  test    rcx, rcx
0x14001c49e  jnz     loc_14001C52E
0x14001c4a4  mov     eax, ebx
0x14001c4a6  add     rsp, 40h
0x14001c4aa  pop     r15
0x14001c4ac  pop     r14
0x14001c4ae  pop     r12
0x14001c4b0  pop     rdi
0x14001c4b1  pop     rsi
0x14001c4b2  pop     rbx
0x14001c4b3  pop     rbp
0x14001c4b4  retn
0x14001c4b5  mov     ecx, eax; Status
0x14001c4b7  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x14001c4bd  mov     ebx, eax
0x14001c4bf  jmp     loc_14001C432
0x14001c4c4  mov     ebx, 57h ; 'W'
0x14001c4c9  jmp     short loc_14001C4A4
0x14001c4cb  mov     ebx, 54Fh
0x14001c4d0  jmp     loc_14001C432
0x14001c4d5  mov     ebx, 8
0x14001c4da  jmp     loc_14001C432
0x14001c4df  mov     ecx, eax; Status
0x14001c4e1  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x14001c4e7  mov     ebx, eax
0x14001c4e9  jmp     loc_14001C41E
0x14001c4ee  lea     rax, [rbp+hKey]
0x14001c4f2  xor     edi, edi
0x14001c4f4  xor     r8d, r8d; ulOptions
0x14001c4f7  mov     [rsp+40h+phkResult], rax; phkResult
0x14001c4fc  lea     rdx, aSystemHardware; "System\\HardwareConfig"
0x14001c503  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14001c50a  lea     r9d, [rdi+8]; samDesired
0x14001c50e  call    cs:__imp_RegOpenKeyExW
0x14001c514  mov     ebx, eax
0x14001c516  test    eax, eax
0x14001c518  jnz     loc_14001C432
0x14001c51e  jmp     loc_14001C40D
0x14001c523  call    cs:__imp_RegCloseKey
0x14001c529  jmp     loc_14001C43F
0x14001c52e  call    cs:__imp_RegCloseKey
0x14001c534  jmp     loc_14001C4A4
```
