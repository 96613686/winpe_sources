# _pSpUtilsHwCfgGetRootKey

- ea: `0x180017dd0`
- end: `0x180017f9c`
- name: `_pSpUtilsHwCfgGetRootKey`
- size: `460`
- prototype: `__int64 __fastcall(__int64, HKEY *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180016ee8`

## callees

- `0x180017dd0`
- `0x18001a010`

## import_xrefs

- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180017e7b`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180017ee4`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180017e7b`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180017ee4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180017e00`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180017e00`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017e1c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017e1c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180017f86`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180017f86`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017f78`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017f78`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017f0b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017f3a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017f0b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017f3a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017f68`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017f68`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180017e96`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180017e96`

## string_xrefs

- `0x180017df9`: `ntdll.dll`
- `0x180017e3b`: `System\HardwareConfig`
- `0x180017eb9`: `System\HardwareConfig`
- `0x180017f28`: `System\HardwareConfig`
- `0x180017e4a`: `HardwareConfigState`
- `0x180017ec4`: `HardwareConfigState`

## pseudocode

```c
__int64 __fastcall pSpUtilsHwCfgGetRootKey(__int64 a1, HKEY *a2)
{
  HMODULE Library; // rax
  HMODULE v4; // rsi
  FARPROC ProcAddress; // rax
  __int64 (__fastcall *v6)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // rbx
  NTSTATUS v7; // eax
  ULONG v8; // ebx
  WCHAR *v9; // rdi
  NTSTATUS v10; // eax
  SIZE_T dwBytes; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  LODWORD(dwBytes) = 0;
  hKey = 0;
  Library = LoadLibraryExW(L"ntdll.dll", 0, 0);
  v4 = Library;
  if ( !Library
    || (ProcAddress = GetProcAddress(Library, "RtlGetPersistedStateLocation"),
        (v6 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))ProcAddress) == 0) )
  {
    v9 = 0;
    v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\HardwareConfig", 0, 1u, &hKey);
    if ( v8 )
      goto LABEL_16;
    goto LABEL_14;
  }
  v7 = ((__int64 (__fastcall *)(const wchar_t *, _QWORD, const WCHAR *, _QWORD, _QWORD, _DWORD, SIZE_T *))ProcAddress)(
         L"HardwareConfigState",
         0,
         L"System\\HardwareConfig",
         0,
         0,
         0,
         &dwBytes);
  if ( v7 >= 0 )
  {
    v8 = 1359;
    goto LABEL_16;
  }
  if ( v7 != -2147483643 )
  {
    v8 = RtlNtStatusToDosErrorNoTeb(v7);
    goto LABEL_16;
  }
  v9 = (WCHAR *)HeapAlloc(hHeap, 0, (unsigned int)dwBytes);
  if ( !v9 )
  {
    v8 = 8;
    goto LABEL_16;
  }
  v10 = v6(L"HardwareConfigState", 0, L"System\\HardwareConfig", 0, v9, dwBytes, &dwBytes);
  if ( v10 >= 0 )
  {
    v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v9, 0, 1u, &hKey);
    if ( v8 )
      goto LABEL_15;
LABEL_14:
    *a2 = hKey;
    hKey = 0;
    if ( !v9 )
      goto LABEL_16;
    goto LABEL_15;
  }
  v8 = RtlNtStatusToDosErrorNoTeb(v10);
LABEL_15:
  HeapFree(hHeap, 0, v9);
LABEL_16:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v4 )
    FreeLibrary(v4);
  return v8;
}

```

## disassembly

```asm
0x180017dd0  mov     rax, rsp
0x180017dd3  mov     [rax+10h], rbx
0x180017dd7  mov     [rax+8], ecx
0x180017dda  push    rsi
0x180017ddb  push    rdi
0x180017ddc  push    r14
0x180017dde  sub     rsp, 40h
0x180017de2  mov     r14, rdx
0x180017de5  mov     dword ptr [rax+8], 0
0x180017dec  xor     edx, edx; hFile
0x180017dee  mov     qword ptr [rax+18h], 0
0x180017df6  xor     r8d, r8d; dwFlags
0x180017df9  lea     rcx, ModuleName; "ntdll.dll"
0x180017e00  call    cs:__imp_LoadLibraryExW
0x180017e06  mov     rsi, rax
0x180017e09  test    rax, rax
0x180017e0c  jz      loc_180017F19
0x180017e12  lea     rdx, aRtlgetpersiste; "RtlGetPersistedStateLocation"
0x180017e19  mov     rcx, rax; hModule
0x180017e1c  call    cs:__imp_GetProcAddress
0x180017e22  mov     rbx, rax
0x180017e25  test    rax, rax
0x180017e28  jz      loc_180017F19
0x180017e2e  lea     rax, [rsp+58h+dwBytes]
0x180017e33  xor     r9d, r9d
0x180017e36  mov     [rsp+58h+var_28], rax
0x180017e3b  lea     r8, aSystemHardware; "System\\HardwareConfig"
0x180017e42  mov     [rsp+58h+var_30], 0
0x180017e4a  lea     rcx, aHardwareconfig; "HardwareConfigState"
0x180017e51  mov     rax, rbx
0x180017e54  mov     [rsp+58h+phkResult], 0
0x180017e5d  xor     edx, edx
0x180017e5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e64  test    eax, eax
0x180017e66  js      short loc_180017E72
0x180017e68  mov     ebx, 54Fh
0x180017e6d  jmp     loc_180017F6E
0x180017e72  cmp     eax, 80000005h
0x180017e77  jz      short loc_180017E88
0x180017e79  mov     ecx, eax; Status
0x180017e7b  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180017e81  mov     ebx, eax
0x180017e83  jmp     loc_180017F6E
0x180017e88  mov     r8d, dword ptr [rsp+58h+dwBytes]; dwBytes
0x180017e8d  xor     edx, edx; dwFlags
0x180017e8f  mov     rcx, cs:hHeap; hHeap
0x180017e96  call    cs:__imp_HeapAlloc
0x180017e9c  mov     rdi, rax
0x180017e9f  test    rax, rax
0x180017ea2  jnz     short loc_180017EAC
0x180017ea4  lea     ebx, [rax+8]
0x180017ea7  jmp     loc_180017F6E
0x180017eac  lea     rax, [rsp+58h+dwBytes]
0x180017eb1  xor     r9d, r9d
0x180017eb4  mov     [rsp+58h+var_28], rax
0x180017eb9  lea     r8, aSystemHardware; "System\\HardwareConfig"
0x180017ec0  mov     eax, dword ptr [rsp+58h+dwBytes]
0x180017ec4  lea     rcx, aHardwareconfig; "HardwareConfigState"
0x180017ecb  mov     [rsp+58h+var_30], eax
0x180017ecf  xor     edx, edx
0x180017ed1  mov     rax, rbx
0x180017ed4  mov     [rsp+58h+phkResult], rdi
0x180017ed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ede  test    eax, eax
0x180017ee0  jns     short loc_180017EEE
0x180017ee2  mov     ecx, eax; Status
0x180017ee4  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180017eea  mov     ebx, eax
0x180017eec  jmp     short loc_180017F5C
0x180017eee  lea     rax, [rsp+58h+hKey]
0x180017ef3  mov     r9d, 1; samDesired
0x180017ef9  xor     r8d, r8d; ulOptions
0x180017efc  mov     [rsp+58h+phkResult], rax; phkResult
0x180017f01  mov     rdx, rdi; lpSubKey
0x180017f04  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180017f0b  call    cs:__imp_RegOpenKeyExW
0x180017f11  mov     ebx, eax
0x180017f13  test    eax, eax
0x180017f15  jnz     short loc_180017F5C
0x180017f17  jmp     short loc_180017F46
0x180017f19  lea     rax, [rsp+58h+hKey]
0x180017f1e  xor     edi, edi
0x180017f20  xor     r8d, r8d; ulOptions
0x180017f23  mov     [rsp+58h+phkResult], rax; phkResult
0x180017f28  lea     rdx, aSystemHardware; "System\\HardwareConfig"
0x180017f2f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180017f36  lea     r9d, [rdi+1]; samDesired
0x180017f3a  call    cs:__imp_RegOpenKeyExW
0x180017f40  mov     ebx, eax
0x180017f42  test    eax, eax
0x180017f44  jnz     short loc_180017F6E
0x180017f46  mov     rax, [rsp+58h+hKey]
0x180017f4b  mov     [r14], rax
0x180017f4e  mov     [rsp+58h+hKey], 0
0x180017f57  test    rdi, rdi
0x180017f5a  jz      short loc_180017F6E
0x180017f5c  mov     rcx, cs:hHeap; hHeap
0x180017f63  mov     r8, rdi; lpMem
0x180017f66  xor     edx, edx; dwFlags
0x180017f68  call    cs:__imp_HeapFree
0x180017f6e  mov     rcx, [rsp+58h+hKey]; hKey
0x180017f73  test    rcx, rcx
0x180017f76  jz      short loc_180017F7E
0x180017f78  call    cs:__imp_RegCloseKey
0x180017f7e  test    rsi, rsi
0x180017f81  jz      short loc_180017F8C
0x180017f83  mov     rcx, rsi; hLibModule
0x180017f86  call    cs:__imp_FreeLibrary
0x180017f8c  mov     eax, ebx
0x180017f8e  mov     rbx, [rsp+58h+arg_8]
0x180017f93  add     rsp, 40h
0x180017f97  pop     r14
0x180017f99  pop     rdi
0x180017f9a  pop     rsi
0x180017f9b  retn
```
