# LoadWinSpool(void)

- ea: `0x1800036ec`
- end: `0x1800037f4`
- name: `?LoadWinSpool@@YAPEAUHINSTANCE__@@XZ`
- size: `264`
- prototype: `HINSTANCE(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800037fc`

## callees

- `0x18000277c`
- `0x1800036ec`
- `0x180004734`
- `0x180005320`
- `0x180014170`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180003762`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180003762`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800037c8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800037c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003781`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800037ac`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003781`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800037ac`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180003730`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180003730`

## pseudocode

```c
HINSTANCE LoadWinSpool(void)
{
  HMODULE v0; // rbx
  const WCHAR *v1; // rdi
  unsigned __int64 v2; // rdx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  FARPROC v5; // rax
  WCHAR Buffer[264]; // [rsp+20h] [rbp-228h] BYREF

  v0 = 0;
  v1 = L"spoolsvworker.exe";
  if ( !(unsigned int)IsWindowsProtectedPrintSpoolerWorkerEnabled() )
    v1 = L"spoolsv.exe";
  if ( GetSystemDirectoryW(Buffer, 0x104u) - 1 <= 0x102 && StringCchCatW(Buffer, v2, L"\\winspool.drv") >= 0 )
  {
    Library = LoadLibraryExW(Buffer, 0, 0);
    v0 = Library;
    if ( Library )
    {
      if ( g_bSandbox )
      {
        ProcAddress = GetProcAddress(Library, (LPCSTR)0x100);
        if ( ProcAddress )
          ((void (__fastcall *)(DWORD *))ProcAddress)(&g_sandboxJobTlsIndex);
      }
      if ( IsDesiredProcess(v1) )
      {
        v5 = GetProcAddress(v0, (LPCSTR)0xFD);
        if ( v5 )
        {
          ((void (__fastcall *)(_QWORD, __int64))v5)(0, 1);
        }
        else
        {
          FreeLibrary(v0);
          return 0;
        }
      }
    }
  }
  return v0;
}

```

## disassembly

```asm
0x1800036ec  mov     [rsp+arg_0], rbx
0x1800036f1  push    rdi
0x1800036f2  sub     rsp, 240h
0x1800036f9  mov     rax, cs:__security_cookie
0x180003700  xor     rax, rsp
0x180003703  mov     [rsp+248h+var_18], rax
0x18000370b  xor     ebx, ebx
0x18000370d  call    ?IsWindowsProtectedPrintSpoolerWorkerEnabled@@YAHXZ; IsWindowsProtectedPrintSpoolerWorkerEnabled(void)
0x180003712  test    eax, eax
0x180003714  lea     rcx, String2; "spoolsv.exe"
0x18000371b  lea     rdi, aSpoolsvworkerE; "spoolsvworker.exe"
0x180003722  mov     edx, 104h; uSize
0x180003727  cmovz   rdi, rcx
0x18000372b  lea     rcx, [rsp+248h+Buffer]; lpBuffer
0x180003730  call    cs:__imp_GetSystemDirectoryW
0x180003736  dec     eax
0x180003738  cmp     eax, 102h
0x18000373d  ja      loc_1800037D0
0x180003743  lea     r8, aWinspoolDrv; "\\winspool.drv"
0x18000374a  lea     rcx, [rsp+248h+Buffer]; unsigned __int16 *
0x18000374f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003754  test    eax, eax
0x180003756  js      short loc_1800037D0
0x180003758  xor     r8d, r8d; dwFlags
0x18000375b  lea     rcx, [rsp+248h+Buffer]; lpLibFileName
0x180003760  xor     edx, edx; hFile
0x180003762  call    cs:__imp_LoadLibraryExW
0x180003768  mov     rbx, rax
0x18000376b  test    rax, rax
0x18000376e  jz      short loc_1800037D0
0x180003770  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x180003777  jz      short loc_180003798
0x180003779  mov     edx, 100h; lpProcName
0x18000377e  mov     rcx, rax; hModule
0x180003781  call    cs:__imp_GetProcAddress
0x180003787  test    rax, rax
0x18000378a  jz      short loc_180003798
0x18000378c  lea     rcx, ?g_sandboxJobTlsIndex@@3KA; ulong g_sandboxJobTlsIndex
0x180003793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003798  mov     rcx, rdi; lpString2
0x18000379b  call    ?IsDesiredProcess@@YA_NPEBG@Z; IsDesiredProcess(ushort const *)
0x1800037a0  test    al, al
0x1800037a2  jz      short loc_1800037D0
0x1800037a4  mov     edx, 0FDh; lpProcName
0x1800037a9  mov     rcx, rbx; hModule
0x1800037ac  call    cs:__imp_GetProcAddress
0x1800037b2  test    rax, rax
0x1800037b5  jz      short loc_1800037C5
0x1800037b7  mov     edx, 1
0x1800037bc  xor     ecx, ecx
0x1800037be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037c3  jmp     short loc_1800037D0
0x1800037c5  mov     rcx, rbx; hLibModule
0x1800037c8  call    cs:__imp_FreeLibrary
0x1800037ce  xor     ebx, ebx
0x1800037d0  mov     rax, rbx
0x1800037d3  mov     rcx, [rsp+248h+var_18]
0x1800037db  xor     rcx, rsp; StackCookie
0x1800037de  call    __security_check_cookie
0x1800037e3  mov     rbx, [rsp+248h+arg_0]
0x1800037eb  add     rsp, 240h
0x1800037f2  pop     rdi
0x1800037f3  retn
```
