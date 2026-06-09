# ReadAndInitMapper

- ea: `0x18002c188`
- end: `0x18002c442`
- name: `ReadAndInitMapper`
- size: `698`
- prototype: `void()`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002d6d0`

## callees

- `0x18002c188`
- `0x18002c8d4`
- `0x18003dc84`
- `0x180040010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c26b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c2e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c26b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c2e7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c218`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c218`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002c249`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002c2dd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002c249`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002c2dd`
- `KERNEL32!HeapAlloc` at `0x18002c1cd`
- `KERNEL32!HeapAlloc` at `0x18002c28a`
- `KERNEL32!HeapAlloc` at `0x18002c1cd`
- `KERNEL32!HeapAlloc` at `0x18002c28a`
- `KERNEL32!FreeLibrary` at `0x18002c389`
- `KERNEL32!FreeLibrary` at `0x18002c389`
- `KERNEL32!GetProcAddress` at `0x18002c34c`
- `KERNEL32!GetProcAddress` at `0x18002c34c`
- `KERNEL32!LoadLibraryW` at `0x18002c2f0`
- `KERNEL32!LoadLibraryW` at `0x18002c2f0`
- `KERNEL32!GetLastError` at `0x18002c2fe`
- `KERNEL32!GetLastError` at `0x18002c2fe`

## string_xrefs

- `0x18002c23b`: `MapperDll`
- `0x18002c2d6`: `MapperDll`
- `0x18002c1db`: `ServerAlloc failed in ReadAndInitMap`
- `0x18002c256`: `Cannot init client/server stuff (registry damaged?)`
- `0x18002c298`: `Alloc failed in ReadAndInitMap(o)`
- `0x18002c304`: `Serious internal failure loading client/server DLL .  Error %lu`
- `0x18002c364`: `MapperDLL does not export %s.  Server functionality disabled`
- `0x18002c409`: `Internal version mismatch!  Check that all components are in sync x%lx`

## pseudocode

```c
void ReadAndInitMapper()
{
  HMODULE *v0; // rbx
  BYTE *v1; // rdi
  HMODULE LibraryW; // rax
  DWORD LastError; // eax
  __int64 v4; // rdi
  FARPROC ProcAddress; // rax
  _DWORD *v6; // rdi
  int v7; // eax
  DWORD cbData; // [rsp+60h] [rbp+30h] BYREF
  DWORD Type; // [rsp+68h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+40h] BYREF

  hKey = 0;
  cbData = 0;
  Type = 0;
  if ( (dword_180051900 & 2) != 0 )
  {
    v0 = (HMODULE *)HeapAlloc(ghTapisrvHeap, 8u, 0x100u);
    if ( !v0 )
    {
      TRACELogPrint(65538, "ServerAlloc failed in ReadAndInitMap");
LABEL_4:
      dword_180051900 &= ~2u;
      return;
    }
    RegOpenKeyExW(
      HKEY_LOCAL_MACHINE,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\Telephony\\Server",
      0,
      0xF003Fu,
      &hKey);
    cbData = 0;
    RegQueryValueExW(hKey, L"MapperDll", 0, &Type, 0, &cbData);
    if ( !cbData )
    {
      TRACELogPrint(65538, "Cannot init client/server stuff (registry damaged?)");
      RegCloseKey(hKey);
LABEL_7:
      ServerFree(v0);
      goto LABEL_4;
    }
    v1 = (BYTE *)HeapAlloc(ghTapisrvHeap, 8u, cbData);
    if ( v1 )
    {
      RegQueryValueExW(hKey, L"MapperDll", 0, &Type, v1, &cbData);
      RegCloseKey(hKey);
      LibraryW = LoadLibraryW((LPCWSTR)v1);
      *v0 = LibraryW;
      if ( !LibraryW )
      {
        LastError = GetLastError();
        TRACELogPrint(65538, "Serious internal failure loading client/server DLL .  Error %lu", LastError);
        ServerFree(v1);
        goto LABEL_7;
      }
      v0[29] = (HMODULE)v1;
      v4 = 0;
      v0[31] = 0;
      while ( (unsigned int)v4 < 5 )
      {
        ProcAddress = GetProcAddress(*v0, (&gaszTCFuncNames)[v4]);
        v0[v4 + 2] = (HMODULE)ProcAddress;
        if ( !ProcAddress )
        {
          TRACELogPrint(262146, "MapperDLL does not export %s.  Server functionality disabled", (&gaszTCFuncNames)[v4]);
          TRACELogPrint(262146, "Disabling the Telephony server! (8)");
LABEL_17:
          FreeLibrary(*v0);
          ServerFree(v0[29]);
          ServerFree(v0);
          qword_180051988 = 0;
          goto LABEL_4;
        }
        v4 = (unsigned int)(v4 + 1);
      }
      v6 = v0 + 30;
      *((_DWORD *)v0 + 60) = 196609;
      v7 = ((__int64 (__fastcall *)(HMODULE *, __int64 (__fastcall *)(), __int64 (__fastcall *)(), _QWORD))v0[2])(
             v0 + 30,
             ManagementAddPhoneProc,
             ManagementAddPhoneProc,
             0);
      if ( v7 )
      {
        TRACELogPrint(262146, "Client/server loadup - x%lx.", v7);
        goto LABEL_17;
      }
      if ( (unsigned int)(*v6 - 131073) > 0x10000 )
      {
        TRACELogPrint(65538, "Internal version mismatch!  Check that all components are in sync x%lx", *v6);
        TRACELogPrint(262146, "   Will use version x%lx", 196609);
        *v6 = 196609;
      }
      qword_180051988 = v0;
    }
    else
    {
      TRACELogPrint(65538, "Alloc failed in ReadAndInitMap(o)");
      dword_180051900 &= ~2u;
      ServerFree(v0);
    }
  }
}

```

## disassembly

```asm
0x18002c188  push    rbp
0x18002c18a  push    rbx
0x18002c18b  push    rsi
0x18002c18c  push    rdi
0x18002c18d  push    r15
0x18002c18f  mov     rbp, rsp
0x18002c192  sub     rsp, 30h
0x18002c196  test    byte ptr cs:dword_180051900, 2
0x18002c19d  mov     [rbp+hKey], 0
0x18002c1a5  mov     [rbp+cbData], 0
0x18002c1ac  mov     [rbp+Type], 0
0x18002c1b3  jz      loc_18002C437
0x18002c1b9  mov     rcx, cs:ghTapisrvHeap; hHeap
0x18002c1c0  mov     edi, 8
0x18002c1c5  mov     edx, edi; dwFlags
0x18002c1c7  mov     r8d, 100h; dwBytes
0x18002c1cd  call    cs:__imp_HeapAlloc
0x18002c1d3  mov     rbx, rax
0x18002c1d6  test    rax, rax
0x18002c1d9  jnz     short loc_18002C1F8
0x18002c1db  lea     rdx, aServerallocFai; "ServerAlloc failed in ReadAndInitMap"
0x18002c1e2  mov     ecx, 10002h
0x18002c1e7  call    TRACELogPrint
0x18002c1ec  and     cs:dword_180051900, 0FFFFFFFDh
0x18002c1f3  jmp     loc_18002C437
0x18002c1f8  lea     rax, [rbp+hKey]
0x18002c1fc  mov     r9d, 0F003Fh; samDesired
0x18002c202  xor     r8d, r8d; ulOptions
0x18002c205  mov     [rsp+30h+phkResult], rax; phkResult
0x18002c20a  lea     rdx, gszRegKeyServer; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002c211  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002c218  call    cs:__imp_RegOpenKeyExW
0x18002c21e  mov     rcx, [rbp+hKey]; hKey
0x18002c222  lea     rax, [rbp+cbData]
0x18002c226  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18002c22b  lea     r9, [rbp+Type]; lpType
0x18002c22f  xor     r8d, r8d; lpReserved
0x18002c232  mov     [rsp+30h+phkResult], 0; lpData
0x18002c23b  lea     rdx, gszMapperDll; "MapperDll"
0x18002c242  mov     [rbp+cbData], 0
0x18002c249  call    cs:__imp_RegQueryValueExW
0x18002c24f  mov     eax, [rbp+cbData]
0x18002c252  test    eax, eax
0x18002c254  jnz     short loc_18002C27E
0x18002c256  lea     rdx, aCannotInitClie; "Cannot init client/server stuff (regist"...
0x18002c25d  mov     ecx, 10002h
0x18002c262  call    TRACELogPrint
0x18002c267  mov     rcx, [rbp+hKey]; hKey
0x18002c26b  call    cs:__imp_RegCloseKey
0x18002c271  mov     rcx, rbx; lpMem
0x18002c274  call    ServerFree
0x18002c279  jmp     loc_18002C1EC
0x18002c27e  mov     rcx, cs:ghTapisrvHeap; hHeap
0x18002c285  mov     r8, rax; dwBytes
0x18002c288  mov     edx, edi; dwFlags
0x18002c28a  call    cs:__imp_HeapAlloc
0x18002c290  mov     rdi, rax
0x18002c293  test    rax, rax
0x18002c296  jnz     short loc_18002C2BD
0x18002c298  lea     rdx, aAllocFailedInR; "Alloc failed in ReadAndInitMap(o)"
0x18002c29f  mov     ecx, 10002h
0x18002c2a4  call    TRACELogPrint
0x18002c2a9  and     cs:dword_180051900, 0FFFFFFFDh
0x18002c2b0  mov     rcx, rbx; lpMem
0x18002c2b3  call    ServerFree
0x18002c2b8  jmp     loc_18002C437
0x18002c2bd  mov     rcx, [rbp+hKey]; hKey
0x18002c2c1  lea     rax, [rbp+cbData]
0x18002c2c5  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18002c2ca  lea     r9, [rbp+Type]; lpType
0x18002c2ce  xor     r8d, r8d; lpReserved
0x18002c2d1  mov     [rsp+30h+phkResult], rdi; lpData
0x18002c2d6  lea     rdx, gszMapperDll; "MapperDll"
0x18002c2dd  call    cs:__imp_RegQueryValueExW
0x18002c2e3  mov     rcx, [rbp+hKey]; hKey
0x18002c2e7  call    cs:__imp_RegCloseKey
0x18002c2ed  mov     rcx, rdi; lpLibFileName
0x18002c2f0  call    cs:__imp_LoadLibraryW
0x18002c2f6  mov     [rbx], rax
0x18002c2f9  test    rax, rax
0x18002c2fc  jnz     short loc_18002C325
0x18002c2fe  call    cs:__imp_GetLastError
0x18002c304  lea     rdx, aSeriousInterna; "Serious internal failure loading client"...
0x18002c30b  mov     ecx, 10002h
0x18002c310  mov     r8d, eax
0x18002c313  call    TRACELogPrint
0x18002c318  mov     rcx, rdi; lpMem
0x18002c31b  call    ServerFree
0x18002c320  jmp     loc_18002C271
0x18002c325  mov     [rbx+0E8h], rdi
0x18002c32c  xor     edi, edi
0x18002c32e  mov     qword ptr [rbx+0F8h], 0
0x18002c339  cmp     edi, 5
0x18002c33c  jnb     short loc_18002C3B3
0x18002c33e  mov     rcx, [rbx]; hModule
0x18002c341  lea     r15, gaszTCFuncNames
0x18002c348  mov     rdx, [r15+rdi*8]; lpProcName
0x18002c34c  call    cs:__imp_GetProcAddress
0x18002c352  mov     [rbx+rdi*8+10h], rax
0x18002c357  test    rax, rax
0x18002c35a  jz      short loc_18002C360
0x18002c35c  inc     edi
0x18002c35e  jmp     short loc_18002C339
0x18002c360  mov     r8, [r15+rdi*8]
0x18002c364  lea     rdx, aMapperdllDoesN; "MapperDLL does not export %s.  Server f"...
0x18002c36b  mov     ecx, 40002h
0x18002c370  call    TRACELogPrint
0x18002c375  lea     rdx, aDisablingTheTe; "Disabling the Telephony server! (8)"
0x18002c37c  mov     ecx, 40002h
0x18002c381  call    TRACELogPrint
0x18002c386  mov     rcx, [rbx]; hLibModule
0x18002c389  call    cs:__imp_FreeLibrary
0x18002c38f  mov     rcx, [rbx+0E8h]; lpMem
0x18002c396  call    ServerFree
0x18002c39b  mov     rcx, rbx; lpMem
0x18002c39e  call    ServerFree
0x18002c3a3  mov     cs:qword_180051988, 0
0x18002c3ae  jmp     loc_18002C1EC
0x18002c3b3  lea     rdi, [rbx+0F0h]
0x18002c3ba  mov     esi, 30001h
0x18002c3bf  mov     [rdi], esi
0x18002c3c1  lea     r8, ManagementAddPhoneProc
0x18002c3c8  mov     rax, [rbx+10h]
0x18002c3cc  lea     rdx, ManagementAddPhoneProc
0x18002c3d3  xor     r9d, r9d
0x18002c3d6  mov     rcx, rdi
0x18002c3d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c3de  test    eax, eax
0x18002c3e0  jz      short loc_18002C3F8
0x18002c3e2  mov     r8d, eax
0x18002c3e5  lea     rdx, aClientServerLo; "Client/server loadup - x%lx."
0x18002c3ec  mov     ecx, 40002h
0x18002c3f1  call    TRACELogPrint
0x18002c3f6  jmp     short loc_18002C386
0x18002c3f8  mov     r8d, [rdi]
0x18002c3fb  lea     eax, [r8-20001h]
0x18002c402  cmp     eax, 10000h
0x18002c407  jbe     short loc_18002C430
0x18002c409  lea     rdx, aInternalVersio; "Internal version mismatch!  Check that "...
0x18002c410  mov     ecx, 10002h
0x18002c415  call    TRACELogPrint
0x18002c41a  mov     r8d, esi
0x18002c41d  lea     rdx, aWillUseVersion; "   Will use version x%lx"
0x18002c424  mov     ecx, 40002h
0x18002c429  call    TRACELogPrint
0x18002c42e  mov     [rdi], esi
0x18002c430  mov     cs:qword_180051988, rbx
0x18002c437  add     rsp, 30h
0x18002c43b  pop     r15
0x18002c43d  pop     rdi
0x18002c43e  pop     rsi
0x18002c43f  pop     rbx
0x18002c440  pop     rbp
0x18002c441  retn
```
