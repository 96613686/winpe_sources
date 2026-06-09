# GetSystemMemoryAsString(ushort *,uint)

- ea: `0x1800248e0`
- end: `0x180024a4d`
- name: `?GetSystemMemoryAsString@@YAJPEAGI@Z`
- size: `365`
- prototype: `__int64 __fastcall(PWSTR pszBuf, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18001055c`
- `0x180010db8`

## callees

- `0x180010768`
- `0x1800151bb`
- `0x1800248e0`
- `0x18002dec0`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002495a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002495a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180024a0e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180024a21`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180024a0e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180024a21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024968`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024968`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800249c2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800249c2`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x1800249a8`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x1800249a8`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180024941`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180024941`
- `SHLWAPI!StrFormatByteSizeW` at `0x1800249f2`
- `SHLWAPI!StrFormatByteSizeW` at `0x1800249f2`

## string_xrefs

- `0x18002493a`: `Shlwapi.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetSystemMemoryAsString(PWSTR pszBuf)
{
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rbx
  DWORDLONG ullTotalPhys; // rcx
  int v5; // ebx
  LONGLONG qdw; // [rsp+38h] [rbp-39h] BYREF
  HMODULE hLibModule[5]; // [rsp+40h] [rbp-31h] BYREF
  unsigned int (__fastcall *v9)(LONGLONG *); // [rsp+68h] [rbp-9h]
  __int64 v10; // [rsp+70h] [rbp-1h]
  struct _MEMORYSTATUSEX Buffer; // [rsp+78h] [rbp+7h] BYREF

  v10 = -2;
  *pszBuf = 0;
  qdw = 0;
  memset(hLibModule, 0, sizeof(hLibModule));
  v9 = 0;
  mlib::KernelAPIs::LoadLibraryW((mlib::KernelAPIs *)hLibModule);
  LibraryW = LoadLibraryW(L"Shlwapi.dll");
  if ( !LibraryW )
  {
    ProcAddress = 0;
LABEL_4:
    GetLastError();
    goto LABEL_5;
  }
  ProcAddress = GetProcAddress(LibraryW, "StrFormatByteSizeEx");
  if ( !ProcAddress )
    goto LABEL_4;
LABEL_5:
  if ( v9 && v9(&qdw) )
  {
    ullTotalPhys = qdw << 10;
    goto LABEL_10;
  }
  memset_0(&Buffer, 0, sizeof(Buffer));
  Buffer.dwLength = 64;
  if ( GlobalMemoryStatusEx(&Buffer) )
  {
    ullTotalPhys = Buffer.ullTotalPhys;
LABEL_10:
    qdw = ullTotalPhys;
    if ( ProcAddress )
    {
      v5 = ((__int64 (__fastcall *)(DWORDLONG, __int64, PWSTR))ProcAddress)(ullTotalPhys, 1, pszBuf);
      if ( v5 >= 0 )
      {
LABEL_15:
        if ( hLibModule[0] )
          FreeLibrary(hLibModule[0]);
        return (unsigned int)v5;
      }
    }
    else
    {
      SetLastError(0x32u);
    }
    v5 = 0;
    if ( !StrFormatByteSizeW(qdw, pszBuf, 0x10u) )
      v5 = -2147467259;
    goto LABEL_15;
  }
  if ( hLibModule[0] )
    FreeLibrary(hLibModule[0]);
  return 2147500037LL;
}

```

## disassembly

```asm
0x1800248e0  mov     rax, rsp
0x1800248e3  push    rbp
0x1800248e4  lea     rbp, [rax-5Fh]
0x1800248e8  sub     rsp, 0C0h
0x1800248ef  mov     [rbp+57h+var_58], 0FFFFFFFFFFFFFFFEh
0x1800248f7  mov     [rax+10h], rbx
0x1800248fb  mov     [rax+18h], rdi
0x1800248ff  mov     rax, cs:__security_cookie
0x180024906  xor     rax, rsp
0x180024909  mov     [rbp+57h+var_10], rax
0x18002490d  mov     rdi, rcx
0x180024910  xor     eax, eax
0x180024912  mov     [rcx], ax
0x180024915  mov     [rbp+57h+qdw], rax
0x180024919  mov     [rbp+57h+hLibModule], rax
0x18002491d  mov     [rbp+57h+var_80], rax
0x180024921  mov     [rbp+57h+var_78], rax
0x180024925  mov     [rbp+57h+var_70], rax
0x180024929  mov     [rbp+57h+var_68], rax
0x18002492d  mov     [rbp+57h+var_60], rax
0x180024931  lea     rcx, [rbp+57h+hLibModule]; this
0x180024935  call    ?LoadLibraryW@KernelAPIs@mlib@@QEAAKXZ; mlib::KernelAPIs::LoadLibraryW(void)
0x18002493a  lea     rcx, aShlwapiDll_0; "Shlwapi.dll"
0x180024941  call    cs:__imp_LoadLibraryW
0x180024947  test    rax, rax
0x18002494a  jnz     short loc_180024950
0x18002494c  xor     ebx, ebx
0x18002494e  jmp     short loc_180024968
0x180024950  lea     rdx, aStrformatbytes; "StrFormatByteSizeEx"
0x180024957  mov     rcx, rax; hModule
0x18002495a  call    cs:__imp_GetProcAddress
0x180024960  mov     rbx, rax
0x180024963  test    rax, rax
0x180024966  jnz     short loc_18002496E
0x180024968  call    cs:__imp_GetLastError
0x18002496e  mov     rax, [rbp+57h+var_60]
0x180024972  test    rax, rax
0x180024975  jz      short loc_18002498E
0x180024977  lea     rcx, [rbp+57h+qdw]
0x18002497b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024980  test    eax, eax
0x180024982  jz      short loc_18002498E
0x180024984  mov     rcx, [rbp+57h+qdw]
0x180024988  shl     rcx, 0Ah
0x18002498c  jmp     short loc_1800249B6
0x18002498e  xor     edx, edx; Val
0x180024990  lea     r8d, [rdx+40h]; Size
0x180024994  lea     rcx, [rbp+57h+Buffer]; void *
0x180024998  call    memset_0
0x18002499d  mov     [rbp+57h+Buffer.dwLength], 40h ; '@'
0x1800249a4  lea     rcx, [rbp+57h+Buffer]; lpBuffer
0x1800249a8  call    cs:__imp_GlobalMemoryStatusEx
0x1800249ae  test    eax, eax
0x1800249b0  jz      short loc_180024A18
0x1800249b2  mov     rcx, [rbp+57h+Buffer.ullTotalPhys]
0x1800249b6  mov     [rbp+57h+qdw], rcx
0x1800249ba  test    rbx, rbx
0x1800249bd  jnz     short loc_1800249CA
0x1800249bf  lea     ecx, [rbx+32h]; dwErrCode
0x1800249c2  call    cs:__imp_SetLastError
0x1800249c8  jmp     short loc_1800249E5
0x1800249ca  mov     r9d, 10h
0x1800249d0  mov     r8, rdi
0x1800249d3  lea     edx, [r9-0Fh]
0x1800249d7  mov     rax, rbx
0x1800249da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800249df  mov     ebx, eax
0x1800249e1  test    eax, eax
0x1800249e3  jns     short loc_180024A05
0x1800249e5  mov     r8d, 10h; cchBuf
0x1800249eb  mov     rdx, rdi; pszBuf
0x1800249ee  mov     rcx, [rbp+57h+qdw]; qdw
0x1800249f2  call    cs:__imp_StrFormatByteSizeW
0x1800249f8  xor     ebx, ebx
0x1800249fa  mov     ecx, 80004005h
0x1800249ff  test    rax, rax
0x180024a02  cmovz   ebx, ecx
0x180024a05  mov     rcx, [rbp+57h+hLibModule]; hLibModule
0x180024a09  test    rcx, rcx
0x180024a0c  jz      short loc_180024A14
0x180024a0e  call    cs:__imp_FreeLibrary
0x180024a14  mov     eax, ebx
0x180024a16  jmp     short loc_180024A2C
0x180024a18  mov     rcx, [rbp+57h+hLibModule]; hLibModule
0x180024a1c  test    rcx, rcx
0x180024a1f  jz      short loc_180024A27
0x180024a21  call    cs:__imp_FreeLibrary
0x180024a27  mov     eax, 80004005h
0x180024a2c  mov     rcx, [rbp+57h+var_10]
0x180024a30  xor     rcx, rsp; StackCookie
0x180024a33  call    __security_check_cookie
0x180024a38  lea     r11, [rsp+0C0h+var_s0]
0x180024a40  mov     rbx, [r11+18h]
0x180024a44  mov     rdi, [r11+20h]
0x180024a48  mov     rsp, r11
0x180024a4b  pop     rbp
0x180024a4c  retn
```
