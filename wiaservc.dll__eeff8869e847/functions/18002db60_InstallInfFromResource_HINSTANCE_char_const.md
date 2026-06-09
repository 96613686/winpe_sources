# InstallInfFromResource(HINSTANCE__ *,char const *)

- ea: `0x18002db60`
- end: `0x18002dcd3`
- name: `?InstallInfFromResource@@YAJPEAUHINSTANCE__@@PEBD@Z`
- size: `371`
- prototype: `__int64 __fastcall(HINSTANCE, const char *)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x18003ae00`
- `0x18003ae20`

## callees

- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18002db60`
- `0x18002de18`
- `0x18002def8`
- `0x180078010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18002db88`
- `KERNEL32!LoadLibraryExW` at `0x18002db88`
- `KERNEL32!FreeLibrary` at `0x18002dc57`
- `KERNEL32!FreeLibrary` at `0x18002dc57`
- `KERNEL32!GetLastError` at `0x18002dbf6`
- `KERNEL32!GetLastError` at `0x18002dc5f`
- `KERNEL32!GetLastError` at `0x18002dbf6`
- `KERNEL32!GetLastError` at `0x18002dc5f`
- `KERNEL32!GetProcAddress` at `0x18002dba4`
- `KERNEL32!GetProcAddress` at `0x18002dba4`

## string_xrefs

- `0x18002dbd6`: `InstallInfFromResource`
- `0x18002dc1a`: `InstallInfFromResource`
- `0x18002dc48`: `InstallInfFromResource`
- `0x18002dc85`: `InstallInfFromResource`
- `0x18002dcb5`: `InstallInfFromResource`
- `0x18002dc0b`: `We failed to get the proc addess of RegInstall from ADVPACK.DLL`
- `0x18002dc31`: `We failed to get the proc addess of RegInstall from ADVPACK.DLL`
- `0x18002dc76`: `LoadLibraryEx on ADVPACK.DLL failed with 0x%08X`
- `0x18002dc9e`: `LoadLibraryEx on ADVPACK.DLL failed with 0x%08X`
- `0x18002db76`: `ADVPACK.DLL`
- `0x18002db9a`: `RegInstall`
- `0x18002dbc7`: `We failed to process our INF resource to write our registration entries`
- `0x18002dbed`: `We failed to process our INF resource to write our registration entries`

## pseudocode

```c
__int64 __fastcall InstallInfFromResource(HINSTANCE a1, const char *a2)
{
  HINSTANCE v2; // rdi
  HMODULE Library; // rax
  HMODULE v5; // rsi
  FARPROC ProcAddress; // rax
  unsigned int v7; // edi
  char *v8; // rbx
  void *v9; // rdx
  void *lpMem; // rax
  int v11; // edx
  int v12; // ecx
  signed int LastError; // eax
  char *v14; // rbx
  void *v15; // rdx
  signed int v16; // eax
  char *v17; // rbx
  void *v18; // rdx
  void *v19; // rax
  int v20; // edx
  int v21; // ecx

  v2 = g_hInst;
  Library = LoadLibraryExW(L"ADVPACK.DLL", 0, 0x800u);
  v5 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "RegInstall");
    if ( ProcAddress )
    {
      v7 = ((__int64 (__fastcall *)(HINSTANCE, const char *, _QWORD))ProcAddress)(v2, a2, 0);
      if ( (v7 & 0x80000000) == 0 )
      {
LABEL_9:
        FreeLibrary(v5);
        return v7;
      }
      v8 = (char *)WiaTrace_TraceLog("We failed to process our INF resource to write our registration entries");
      WriteDbgTraceErrorWI("InstallInfFromResource", v8);
      WiaTrcLib::Free((WiaTrcLib *)v8, v9);
      lpMem = (void *)WiaTrace_Trace("We failed to process our INF resource to write our registration entries");
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      v14 = (char *)WiaTrace_TraceLog("We failed to get the proc addess of RegInstall from ADVPACK.DLL");
      WriteDbgTraceErrorWI("InstallInfFromResource", v14);
      WiaTrcLib::Free((WiaTrcLib *)v14, v15);
      lpMem = (void *)WiaTrace_Trace("We failed to get the proc addess of RegInstall from ADVPACK.DLL");
    }
    WiaTrace_ProcessTrace_Ex(v12, v11, (int)"InstallInfFromResource", 1, lpMem);
    goto LABEL_9;
  }
  v16 = GetLastError();
  v7 = v16;
  if ( v16 > 0 )
    v7 = (unsigned __int16)v16 | 0x80070000;
  v17 = (char *)WiaTrace_TraceLog("LoadLibraryEx on ADVPACK.DLL failed with 0x%08X");
  WriteDbgTraceErrorWI("InstallInfFromResource", v17);
  WiaTrcLib::Free((WiaTrcLib *)v17, v18);
  v19 = (void *)WiaTrace_Trace("LoadLibraryEx on ADVPACK.DLL failed with 0x%08X", v7);
  WiaTrace_ProcessTrace_Ex(v21, v20, (int)"InstallInfFromResource", 1, v19);
  return v7;
}

```

## disassembly

```asm
0x18002db60  mov     [rsp+arg_0], rbx
0x18002db65  mov     [rsp+arg_8], rsi
0x18002db6a  push    rdi
0x18002db6b  sub     rsp, 30h
0x18002db6f  mov     rdi, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInst
0x18002db76  lea     rcx, LibFileName; "ADVPACK.DLL"
0x18002db7d  mov     rbx, rdx
0x18002db80  mov     r8d, 800h; dwFlags
0x18002db86  xor     edx, edx; hFile
0x18002db88  call    cs:__imp_LoadLibraryExW
0x18002db8e  mov     rsi, rax
0x18002db91  test    rax, rax
0x18002db94  jz      loc_18002DC5F
0x18002db9a  lea     rdx, aReginstall; "RegInstall"
0x18002dba1  mov     rcx, rax; hModule
0x18002dba4  call    cs:__imp_GetProcAddress
0x18002dbaa  test    rax, rax
0x18002dbad  jz      short loc_18002DBF6
0x18002dbaf  xor     r8d, r8d
0x18002dbb2  mov     rdx, rbx
0x18002dbb5  mov     rcx, rdi
0x18002dbb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dbbd  mov     edi, eax
0x18002dbbf  test    eax, eax
0x18002dbc1  jns     loc_18002DC54
0x18002dbc7  lea     rcx, aWeFailedToProc; "We failed to process our INF resource t"...
0x18002dbce  call    WiaTrace_TraceLog
0x18002dbd3  mov     rdx, rax; char *
0x18002dbd6  lea     rcx, aInstallinffrom; "InstallInfFromResource"
0x18002dbdd  mov     rbx, rax
0x18002dbe0  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002dbe5  mov     rcx, rbx; this
0x18002dbe8  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002dbed  lea     rcx, aWeFailedToProc; "We failed to process our INF resource t"...
0x18002dbf4  jmp     short loc_18002DC38
0x18002dbf6  call    cs:__imp_GetLastError
0x18002dbfc  mov     edi, eax
0x18002dbfe  test    eax, eax
0x18002dc00  jle     short loc_18002DC0B
0x18002dc02  movzx   edi, ax
0x18002dc05  or      edi, 80070000h
0x18002dc0b  lea     rcx, aWeFailedToGetT; "We failed to get the proc addess of Reg"...
0x18002dc12  call    WiaTrace_TraceLog
0x18002dc17  mov     rdx, rax; char *
0x18002dc1a  lea     rcx, aInstallinffrom; "InstallInfFromResource"
0x18002dc21  mov     rbx, rax
0x18002dc24  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002dc29  mov     rcx, rbx; this
0x18002dc2c  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002dc31  lea     rcx, aWeFailedToGetT; "We failed to get the proc addess of Reg"...
0x18002dc38  call    WiaTrace_Trace
0x18002dc3d  mov     r9d, 1; int
0x18002dc43  mov     [rsp+38h+lpMem], rax; lpMem
0x18002dc48  lea     r8, aInstallinffrom; "InstallInfFromResource"
0x18002dc4f  call    WiaTrace_ProcessTrace_Ex
0x18002dc54  mov     rcx, rsi; hLibModule
0x18002dc57  call    cs:__imp_FreeLibrary
0x18002dc5d  jmp     short loc_18002DCC1
0x18002dc5f  call    cs:__imp_GetLastError
0x18002dc65  mov     edi, eax
0x18002dc67  test    eax, eax
0x18002dc69  jle     short loc_18002DC74
0x18002dc6b  movzx   edi, ax
0x18002dc6e  or      edi, 80070000h
0x18002dc74  mov     edx, edi
0x18002dc76  lea     rcx, aLoadlibraryexO; "LoadLibraryEx on ADVPACK.DLL failed wit"...
0x18002dc7d  call    WiaTrace_TraceLog
0x18002dc82  mov     rdx, rax; char *
0x18002dc85  lea     rcx, aInstallinffrom; "InstallInfFromResource"
0x18002dc8c  mov     rbx, rax
0x18002dc8f  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002dc94  mov     rcx, rbx; this
0x18002dc97  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002dc9c  mov     edx, edi
0x18002dc9e  lea     rcx, aLoadlibraryexO; "LoadLibraryEx on ADVPACK.DLL failed wit"...
0x18002dca5  call    WiaTrace_Trace
0x18002dcaa  mov     r9d, 1; int
0x18002dcb0  mov     [rsp+38h+lpMem], rax; lpMem
0x18002dcb5  lea     r8, aInstallinffrom; "InstallInfFromResource"
0x18002dcbc  call    WiaTrace_ProcessTrace_Ex
0x18002dcc1  mov     rbx, [rsp+38h+arg_0]
0x18002dcc6  mov     eax, edi
0x18002dcc8  mov     rsi, [rsp+38h+arg_8]
0x18002dccd  add     rsp, 30h
0x18002dcd1  pop     rdi
0x18002dcd2  retn
```
