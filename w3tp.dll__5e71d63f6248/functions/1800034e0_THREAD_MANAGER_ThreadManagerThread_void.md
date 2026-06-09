# THREAD_MANAGER::ThreadManagerThread(void *)

- ea: `0x1800034e0`
- end: `0x1800035b7`
- name: `?ThreadManagerThread@THREAD_MANAGER@@CAKPEAX@Z`
- size: `215`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001770`
- `0x1800034e0`
- `0x180005010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000352d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000352d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000351c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000351c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x1800035b0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x1800035b0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800034f8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800034f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003506`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003506`
- `iisutil!PuDbgPrint` at `0x180003599`
- `iisutil!PuDbgPrint` at `0x180003599`

## string_xrefs

- `0x18000357c`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3tp\thread_manager.cxx`
- `0x18000358d`: `W3TP: RemoveThread, decrement count on node %d\n`
- `0x18000356e`: `THREAD_MANAGER::RemoveThread`

## pseudocode

```c
void __fastcall __noreturn THREAD_MANAGER::ThreadManagerThread(_QWORD *Parameter)
{
  HMODULE Library; // rbp
  DWORD LastError; // eax
  unsigned int v4; // edx
  __int64 v5; // rbx
  DWORD v6; // edi
  __int64 v7; // rbx

  Library = LoadLibraryExW(&g_szModuleName, 0, 0);
  if ( Library )
  {
    if ( *((_DWORD *)Parameter + 9) )
    {
      v5 = Parameter[3];
      EnterCriticalSection((LPCRITICAL_SECTION)(v5 + 8));
      *(_DWORD *)(v5 + 52) = 0;
      LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 8));
    }
    LastError = ((__int64 (__fastcall *)(_QWORD))Parameter[1])(Parameter[2]);
  }
  else
  {
    LastError = GetLastError();
  }
  v6 = LastError;
  v7 = Parameter[3];
  if ( *(_DWORD *)(v7 + 144) )
  {
    _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(v7 + 152)
                                                    + 24LL * *((unsigned int *)Parameter + 10)
                                                    + 20));
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3tp\\thread_manager.cxx",
        1648,
        "THREAD_MANAGER::RemoveThread",
        "W3TP: RemoveThread, decrement count on node %d\n",
        *((_DWORD *)Parameter + 10));
  }
  _InterlockedDecrement((volatile signed __int32 *)(v7 + 76));
  THREAD_MANAGER::THREAD_PARAM::`scalar deleting destructor'((THREAD_MANAGER::THREAD_PARAM *)Parameter, v4);
  FreeLibraryAndExitThread(Library, v6);
}

```

## disassembly

```asm
0x1800034e0  push    rbx
0x1800034e2  push    rbp
0x1800034e3  push    rsi
0x1800034e4  push    rdi
0x1800034e5  sub     rsp, 38h
0x1800034e9  mov     rsi, rcx
0x1800034ec  xor     r8d, r8d; dwFlags
0x1800034ef  lea     rcx, ?g_szModuleName@@3PAGA; lpLibFileName
0x1800034f6  xor     edx, edx; hFile
0x1800034f8  call    cs:__imp_LoadLibraryExW
0x1800034fe  mov     rbp, rax
0x180003501  test    rax, rax
0x180003504  jnz     short loc_18000350E
0x180003506  call    cs:__imp_GetLastError
0x18000350c  jmp     short loc_180003540
0x18000350e  cmp     dword ptr [rsi+24h], 0
0x180003512  jz      short loc_180003533
0x180003514  mov     rbx, [rsi+18h]
0x180003518  lea     rcx, [rbx+8]; lpCriticalSection
0x18000351c  call    cs:__imp_EnterCriticalSection
0x180003522  lea     rcx, [rbx+8]; lpCriticalSection
0x180003526  mov     dword ptr [rbx+34h], 0
0x18000352d  call    cs:__imp_LeaveCriticalSection
0x180003533  mov     rcx, [rsi+10h]
0x180003537  mov     rax, [rsi+8]
0x18000353b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003540  mov     edi, eax
0x180003542  mov     rbx, [rsi+18h]
0x180003546  cmp     dword ptr [rbx+90h], 0
0x18000354d  jz      short loc_18000359F
0x18000354f  mov     eax, [rsi+28h]
0x180003552  lea     rcx, [rax+rax*2]
0x180003556  mov     rax, [rbx+98h]
0x18000355d  lock dec dword ptr [rax+rcx*8+14h]
0x180003562  test    cs:g_dwDebugFlags, 3
0x180003569  jz      short loc_18000359F
0x18000356b  mov     eax, [rsi+28h]
0x18000356e  lea     r9, aThreadManagerR; "THREAD_MANAGER::RemoveThread"
0x180003575  mov     rcx, cs:g_pDebug
0x18000357c  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180003583  mov     [rsp+58h+var_30], eax
0x180003587  mov     r8d, 670h
0x18000358d  lea     rax, aW3tpRemovethre; "W3TP: RemoveThread, decrement count on "...
0x180003594  mov     [rsp+58h+var_38], rax
0x180003599  call    cs:__imp_PuDbgPrint
0x18000359f  lock dec dword ptr [rbx+4Ch]
0x1800035a3  mov     rcx, rsi; this
0x1800035a6  call    ??_GTHREAD_PARAM@THREAD_MANAGER@@QEAAPEAXI@Z; THREAD_MANAGER::THREAD_PARAM::`scalar deleting destructor'(uint)
0x1800035ab  mov     edx, edi; dwExitCode
0x1800035ad  mov     rcx, rbp; hLibModule
0x1800035b0  call    cs:__imp_FreeLibraryAndExitThread
```
