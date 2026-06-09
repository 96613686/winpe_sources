# TLoad64BitDllsMgr::MonitorSrvrLifeExpiration(void *)

- ea: `0x140007790`
- end: `0x1400077f5`
- name: `?MonitorSrvrLifeExpiration@TLoad64BitDllsMgr@@KAKPEAX@Z`
- size: `101`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x140007790`
- `0x1400082e0`
- `0x1400086e0`

## import_xrefs

- `KERNEL32!GetModuleHandleExW` at `0x1400077c6`
- `KERNEL32!GetModuleHandleExW` at `0x1400077c6`
- `KERNEL32!Sleep` at `0x1400077d1`
- `KERNEL32!Sleep` at `0x1400077d1`
- `KERNEL32!FreeLibraryAndExitThread` at `0x1400077ee`
- `KERNEL32!FreeLibraryAndExitThread` at `0x1400077ee`

## string_xrefs

- `0x1400077a0`: `TLoad64BitDllsMgr::MonitorSrvrLifeExpiration`

## pseudocode

```c
void __fastcall __noreturn TLoad64BitDllsMgr::MonitorSrvrLifeExpiration(unsigned __int64 *Parameter)
{
  HMODULE phModule; // [rsp+30h] [rbp+8h] BYREF

  SplWow64Telemetry::WriteDbgTraceInfo("TLoad64BitDllsMgr::MonitorSrvrLifeExpiration", L"Entered..");
  phModule = 0;
  GetModuleHandleExW(4u, (LPCWSTR)TLoad64BitDllsMgr::MonitorSrvrLifeExpiration, &phModule);
  while ( (unsigned int)TLoad64BitDllsMgr::StillAlive((TLoad64BitDllsMgr *)Parameter, Parameter[8]) )
    Sleep(*((_DWORD *)Parameter + 16));
  FreeLibraryAndExitThread(phModule, 0);
}

```

## disassembly

```asm
0x140007790  push    rbx
0x140007792  sub     rsp, 20h
0x140007796  mov     rbx, rcx
0x140007799  lea     rdx, aEntered; "Entered.."
0x1400077a0  lea     rcx, aTload64bitdlls_7; "TLoad64BitDllsMgr::MonitorSrvrLifeExpir"...
0x1400077a7  call    ?WriteDbgTraceInfo@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1400077ac  lea     r8, [rsp+28h+phModule]; phModule
0x1400077b1  mov     [rsp+28h+phModule], 0
0x1400077ba  lea     rdx, ?MonitorSrvrLifeExpiration@TLoad64BitDllsMgr@@KAKPEAX@Z; lpModuleName
0x1400077c1  mov     ecx, 4; dwFlags
0x1400077c6  call    cs:__imp_GetModuleHandleExW
0x1400077cc  jmp     short loc_1400077D7
0x1400077ce  mov     ecx, [rbx+40h]; dwMilliseconds
0x1400077d1  call    cs:__imp_Sleep
0x1400077d7  mov     rdx, [rbx+40h]; unsigned __int64
0x1400077db  mov     rcx, rbx; this
0x1400077de  call    ?StillAlive@TLoad64BitDllsMgr@@QEAAH_K@Z; TLoad64BitDllsMgr::StillAlive(unsigned __int64)
0x1400077e3  test    eax, eax
0x1400077e5  jnz     short loc_1400077CE
0x1400077e7  mov     rcx, [rsp+28h+phModule]; hLibModule
0x1400077ec  xor     edx, edx; dwExitCode
0x1400077ee  call    cs:__imp_FreeLibraryAndExitThread
```
