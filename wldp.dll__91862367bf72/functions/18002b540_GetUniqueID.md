# GetUniqueID

- ea: `0x18002b540`
- end: `0x18002b66a`
- name: `GetUniqueID`
- size: `298`
- prototype: `__int64 __fastcall(void *Src, size_t Size, void *, unsigned int, __int64, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001d220`
- `0x180024370`

## callees

- `0x1800201b4`
- `0x1800229f8`
- `0x18002b4e8`
- `0x18002b540`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b646`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b646`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002b5db`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002b5db`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002b572`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002b572`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b5aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b5aa`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002b63d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002b63d`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002b5c6`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002b5c6`

## string_xrefs

- `0x18002b56b`: `DMCfgUtils.dll`

## pseudocode

```c
__int64 __fastcall GetUniqueID(void *Src, size_t Size, void *a3, unsigned int a4, __int64 a5, __int64 a6)
{
  size_t v6; // r14
  size_t v8; // r15
  HMODULE Library; // rax
  FARPROC ProcAddress; // rbp
  HRESULT v13; // ebx
  char *v14; // rdi
  char *v15; // rax
  HMODULE hModule[11]; // [rsp+40h] [rbp-58h] BYREF

  v6 = a4;
  v8 = (unsigned int)Size;
  hModule[0] = 0;
  Library = LoadLibraryExW(L"DMCfgUtils.dll", 0, 0);
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
    hModule,
    Library);
  if ( hModule[0] )
  {
    ProcAddress = GetProcAddress(hModule[0], "SyncGetDeviceUniqueID");
    if ( ProcAddress )
    {
      v14 = 0;
      v13 = CoInitializeEx(0, 0);
      if ( v13 >= 0 )
      {
        v15 = (char *)LocalAlloc(0x40u, (unsigned int)(v8 + v6));
        v14 = v15;
        if ( v15 )
        {
          memcpy_0(v15, a3, v6);
          memcpy_0(&v14[v6], Src, v8);
          v13 = ((__int64 (__fastcall *)(char *, _QWORD, __int64, __int64, __int64, int))ProcAddress)(
                  v14,
                  (unsigned int)(v8 + v6),
                  1,
                  a6,
                  a5,
                  1);
        }
        else
        {
          v13 = -2147024882;
        }
      }
      CoUninitialize();
      LocalFree(v14);
    }
    else
    {
      v13 = 1;
    }
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(hModule);
    return (unsigned int)v13;
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(hModule);
    return 1;
  }
}

```

## disassembly

```asm
0x18002b540  push    rbx
0x18002b542  push    rbp
0x18002b543  push    rsi
0x18002b544  push    rdi
0x18002b545  push    r12
0x18002b547  push    r13
0x18002b549  push    r14
0x18002b54b  push    r15
0x18002b54d  sub     rsp, 58h
0x18002b551  mov     r14d, r9d
0x18002b554  mov     r12, r8
0x18002b557  mov     r15d, edx
0x18002b55a  mov     r13, rcx
0x18002b55d  mov     [rsp+98h+hModule], 0
0x18002b566  xor     r8d, r8d; dwFlags
0x18002b569  xor     edx, edx; hFile
0x18002b56b  lea     rcx, aDmcfgutilsDll; "DMCfgUtils.dll"
0x18002b572  call    cs:__imp_LoadLibraryExW
0x18002b578  mov     rdx, rax
0x18002b57b  lea     rcx, [rsp+98h+hModule]
0x18002b580  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x18002b585  mov     rcx, [rsp+98h+hModule]; hModule
0x18002b58a  test    rcx, rcx
0x18002b58d  jnz     short loc_18002B5A3
0x18002b58f  lea     rcx, [rsp+98h+hModule]
0x18002b594  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18002b599  mov     eax, 1
0x18002b59e  jmp     loc_18002B659
0x18002b5a3  lea     rdx, aSyncgetdeviceu; "SyncGetDeviceUniqueID"
0x18002b5aa  call    cs:__imp_GetProcAddress
0x18002b5b0  mov     rbp, rax
0x18002b5b3  test    rax, rax
0x18002b5b6  jnz     short loc_18002B5C0
0x18002b5b8  lea     ebx, [rax+1]
0x18002b5bb  jmp     loc_18002B64D
0x18002b5c0  xor     edi, edi
0x18002b5c2  xor     edx, edx; dwCoInit
0x18002b5c4  xor     ecx, ecx; pvReserved
0x18002b5c6  call    cs:__imp_CoInitializeEx
0x18002b5cc  mov     ebx, eax
0x18002b5ce  test    eax, eax
0x18002b5d0  js      short loc_18002B63D
0x18002b5d2  lea     esi, [r15+r14]
0x18002b5d6  mov     edx, esi; uBytes
0x18002b5d8  lea     ecx, [rdi+40h]; uFlags
0x18002b5db  call    cs:__imp_LocalAlloc
0x18002b5e1  mov     rdi, rax
0x18002b5e4  test    rax, rax
0x18002b5e7  jnz     short loc_18002B5F0
0x18002b5e9  mov     ebx, 8007000Eh
0x18002b5ee  jmp     short loc_18002B63D
0x18002b5f0  mov     r8, r14; Size
0x18002b5f3  mov     rdx, r12; Src
0x18002b5f6  mov     rcx, rdi; void *
0x18002b5f9  call    memcpy_0
0x18002b5fe  mov     r8, r15; Size
0x18002b601  lea     rcx, [r14+rdi]; void *
0x18002b605  mov     rdx, r13; Src
0x18002b608  call    memcpy_0
0x18002b60d  mov     ebx, 1
0x18002b612  mov     [rsp+98h+var_70], ebx
0x18002b616  mov     rax, [rsp+98h+arg_20]
0x18002b61e  mov     [rsp+98h+var_78], rax
0x18002b623  mov     r9, [rsp+98h+arg_28]
0x18002b62b  mov     r8d, ebx
0x18002b62e  mov     edx, esi
0x18002b630  mov     rcx, rdi
0x18002b633  mov     rax, rbp
0x18002b636  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b63b  mov     ebx, eax
0x18002b63d  call    cs:__imp_CoUninitialize
0x18002b643  mov     rcx, rdi; hMem
0x18002b646  call    cs:__imp_LocalFree
0x18002b64c  nop
0x18002b64d  lea     rcx, [rsp+98h+hModule]
0x18002b652  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18002b657  mov     eax, ebx
0x18002b659  add     rsp, 58h
0x18002b65d  pop     r15
0x18002b65f  pop     r14
0x18002b661  pop     r13
0x18002b663  pop     r12
0x18002b665  pop     rdi
0x18002b666  pop     rsi
0x18002b667  pop     rbp
0x18002b668  pop     rbx
0x18002b669  retn
```
