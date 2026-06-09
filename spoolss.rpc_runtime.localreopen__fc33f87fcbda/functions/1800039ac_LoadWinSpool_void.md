# LoadWinSpool(void)

- ea: `0x1800039ac`
- end: `0x180003ad7`
- name: `?LoadWinSpool@@YAPEAUHINSTANCE__@@XZ`
- size: `299`
- prototype: `HINSTANCE(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180003ae0`

## callees

- `0x180002908`
- `0x1800039ac`
- `0x180004a64`
- `0x180005680`
- `0x180015a70`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180003a2c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180003a2c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003aa4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003aa4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003a51`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003a82`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003a51`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003a82`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800039f0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800039f0`

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
0x1800039ac  mov     [rsp+arg_0], rbx
0x1800039b1  push    rdi
0x1800039b2  sub     rsp, 240h
0x1800039b9  mov     rax, cs:__security_cookie
0x1800039c0  xor     rax, rsp
0x1800039c3  mov     [rsp+248h+var_18], rax
0x1800039cb  xor     ebx, ebx
0x1800039cd  call    ?IsWindowsProtectedPrintSpoolerWorkerEnabled@@YAHXZ; IsWindowsProtectedPrintSpoolerWorkerEnabled(void)
0x1800039d2  test    eax, eax
0x1800039d4  lea     rcx, String2; "spoolsv.exe"
0x1800039db  lea     rdi, aSpoolsvworkerE; "spoolsvworker.exe"
0x1800039e2  mov     edx, 104h; uSize
0x1800039e7  cmovz   rdi, rcx
0x1800039eb  lea     rcx, [rsp+248h+Buffer]; lpBuffer
0x1800039f0  call    cs:__imp_GetSystemDirectoryW
0x1800039f7  nop     dword ptr [rax+rax+00h]
0x1800039fc  dec     eax
0x1800039fe  cmp     eax, 102h
0x180003a03  ja      loc_180003AB2
0x180003a09  lea     r8, aWinspoolDrv; "\\winspool.drv"
0x180003a10  lea     rcx, [rsp+248h+Buffer]; unsigned __int16 *
0x180003a15  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003a1a  test    eax, eax
0x180003a1c  js      loc_180003AB2
0x180003a22  xor     r8d, r8d; dwFlags
0x180003a25  lea     rcx, [rsp+248h+Buffer]; lpLibFileName
0x180003a2a  xor     edx, edx; hFile
0x180003a2c  call    cs:__imp_LoadLibraryExW
0x180003a33  nop     dword ptr [rax+rax+00h]
0x180003a38  mov     rbx, rax
0x180003a3b  test    rax, rax
0x180003a3e  jz      short loc_180003AB2
0x180003a40  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x180003a47  jz      short loc_180003A6E
0x180003a49  mov     edx, 100h; lpProcName
0x180003a4e  mov     rcx, rax; hModule
0x180003a51  call    cs:__imp_GetProcAddress
0x180003a58  nop     dword ptr [rax+rax+00h]
0x180003a5d  test    rax, rax
0x180003a60  jz      short loc_180003A6E
0x180003a62  lea     rcx, ?g_sandboxJobTlsIndex@@3KA; ulong g_sandboxJobTlsIndex
0x180003a69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a6e  mov     rcx, rdi; lpString2
0x180003a71  call    ?IsDesiredProcess@@YA_NPEBG@Z; IsDesiredProcess(ushort const *)
0x180003a76  test    al, al
0x180003a78  jz      short loc_180003AB2
0x180003a7a  mov     edx, 0FDh; lpProcName
0x180003a7f  mov     rcx, rbx; hModule
0x180003a82  call    cs:__imp_GetProcAddress
0x180003a89  nop     dword ptr [rax+rax+00h]
0x180003a8e  test    rax, rax
0x180003a91  jz      short loc_180003AA1
0x180003a93  mov     edx, 1
0x180003a98  xor     ecx, ecx
0x180003a9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a9f  jmp     short loc_180003AB2
0x180003aa1  mov     rcx, rbx; hLibModule
0x180003aa4  call    cs:__imp_FreeLibrary
0x180003aab  nop     dword ptr [rax+rax+00h]
0x180003ab0  xor     ebx, ebx
0x180003ab2  mov     rax, rbx
0x180003ab5  mov     rcx, [rsp+248h+var_18]
0x180003abd  xor     rcx, rsp; StackCookie
0x180003ac0  call    __security_check_cookie
0x180003ac5  mov     rbx, [rsp+248h+arg_0]
0x180003acd  add     rsp, 240h
0x180003ad4  pop     rdi
0x180003ad5  retn
```
