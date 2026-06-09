# TLoad64BitDllsMgr::StillAlive(unsigned __int64)

- ea: `0x1400082e0`
- end: `0x1400083eb`
- name: `?StillAlive@TLoad64BitDllsMgr@@QEAAH_K@Z`
- size: `267`
- prototype: `__int64 __fastcall(TLoad64BitDllsMgr *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x140007790`
- `0x140012740`

## callees

- `0x1400082e0`
- `0x1400086e0`
- `0x140016010`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x140008307`
- `KERNEL32!GetTickCount64` at `0x1400083c2`
- `KERNEL32!GetTickCount64` at `0x140008307`
- `KERNEL32!GetTickCount64` at `0x1400083c2`
- `KERNEL32!SetEvent` at `0x14000838b`
- `KERNEL32!SetEvent` at `0x14000838b`
- `KERNEL32!EnterCriticalSection` at `0x140008301`
- `KERNEL32!EnterCriticalSection` at `0x140008301`
- `KERNEL32!LeaveCriticalSection` at `0x1400083d0`
- `KERNEL32!LeaveCriticalSection` at `0x1400083d0`
- `USER32!EnumWindows` at `0x14000834c`
- `USER32!EnumWindows` at `0x14000834c`

## string_xrefs

- `0x140008378`: `TLoad64BitDllsMgr::MarkToStopService`
- `0x14000831b`: `TLoad64BitDllsMgr::StillAlive`
- `0x1400083b6`: `TLoad64BitDllsMgr::StillAlive`
- `0x1400083ac`: `StillAlive - UI refcount=%u, areWindowsOpen=%ws, sandbox can unload=%ws`

## pseudocode

```c
__int64 __fastcall TLoad64BitDllsMgr::StillAlive(TLoad64BitDllsMgr *this, ULONGLONG a2)
{
  unsigned int v4; // ebp
  ULONGLONG v5; // rbx
  unsigned int v6; // edi
  char v7; // bl
  const wchar_t *v8; // r9
  LPARAM lParam; // [rsp+50h] [rbp+8h] BYREF

  v4 = 1;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v5 = GetTickCount64() - *((_QWORD *)this + 10);
  SplWow64Telemetry::WriteDbgTraceInfo("TLoad64BitDllsMgr::StillAlive", L"TimeDiff = %llu", v5);
  if ( v5 > a2 )
  {
    v6 = *((_DWORD *)this + 15);
    v7 = 0;
    if ( v6
      || (LOBYTE(lParam) = 0,
          EnumWindows((WNDENUMPROC)TLoad64BitDllsMgr::EnumWindowsProc, (LPARAM)&lParam),
          (v7 = lParam) != 0)
      || sandbox::g_pfnDllCanUnloadNow && sandbox::g_pfnDllCanUnloadNow() )
    {
      v8 = L"true";
      if ( !v7 )
        v8 = L"false";
      SplWow64Telemetry::WriteDbgTraceInfo(
        "TLoad64BitDllsMgr::StillAlive",
        L"StillAlive - UI refcount=%u, areWindowsOpen=%ws, sandbox can unload=%ws",
        v6,
        v8,
        L"false");
      *((_QWORD *)this + 10) = GetTickCount64();
    }
    else
    {
      v4 = 0;
      SplWow64Telemetry::WriteDbgTraceInfo("TLoad64BitDllsMgr::MarkToStopService", L"Entered..");
      SetEvent(*((HANDLE *)this + 16));
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  return v4;
}

```

## disassembly

```asm
0x1400082e0  mov     [rsp+arg_8], rbx
0x1400082e5  mov     [rsp+arg_10], rbp
0x1400082ea  push    rsi
0x1400082eb  push    rdi
0x1400082ec  push    r14
0x1400082ee  sub     rsp, 30h
0x1400082f2  mov     rsi, rcx
0x1400082f5  mov     rdi, rdx
0x1400082f8  add     rcx, 58h ; 'X'; lpCriticalSection
0x1400082fc  mov     ebp, 1
0x140008301  call    cs:__imp_EnterCriticalSection
0x140008307  call    cs:__imp_GetTickCount64
0x14000830d  mov     rbx, rax
0x140008310  lea     rdx, aTimediffLlu; "TimeDiff = %llu"
0x140008317  sub     rbx, [rsi+50h]
0x14000831b  lea     rcx, aTload64bitdlls_4; "TLoad64BitDllsMgr::StillAlive"
0x140008322  mov     r8, rbx
0x140008325  call    ?WriteDbgTraceInfo@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14000832a  cmp     rbx, rdi
0x14000832d  jbe     loc_1400083CC
0x140008333  mov     edi, [rsi+3Ch]
0x140008336  xor     bl, bl
0x140008338  test    edi, edi
0x14000833a  jnz     short loc_140008393
0x14000833c  lea     rdx, [rsp+48h+lParam]; lParam
0x140008341  mov     byte ptr [rsp+48h+lParam], bl
0x140008345  lea     rcx, ?EnumWindowsProc@TLoad64BitDllsMgr@@KAHPEAX_J@Z; lpEnumFunc
0x14000834c  call    cs:__imp_EnumWindows
0x140008352  mov     bl, byte ptr [rsp+48h+lParam]
0x140008356  test    bl, bl
0x140008358  jnz     short loc_140008393
0x14000835a  mov     rax, cs:?g_pfnDllCanUnloadNow@sandbox@@3P6AJXZEA; long (*sandbox::g_pfnDllCanUnloadNow)(void)
0x140008361  test    rax, rax
0x140008364  jz      short loc_14000836F
0x140008366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000836b  test    eax, eax
0x14000836d  jnz     short loc_140008393
0x14000836f  lea     rdx, aEntered; "Entered.."
0x140008376  xor     ebp, ebp
0x140008378  lea     rcx, aTload64bitdlls_2; "TLoad64BitDllsMgr::MarkToStopService"
0x14000837f  call    ?WriteDbgTraceInfo@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140008384  mov     rcx, [rsi+80h]; hEvent
0x14000838b  call    cs:__imp_SetEvent
0x140008391  jmp     short loc_1400083CC
0x140008393  lea     rax, aFalse; "false"
0x14000839a  test    bl, bl
0x14000839c  lea     r9, aTrue; "true"
0x1400083a3  mov     [rsp+48h+var_28], rax
0x1400083a8  cmovz   r9, rax
0x1400083ac  lea     rdx, aStillaliveUiRe; "StillAlive - UI refcount=%u, areWindows"...
0x1400083b3  mov     r8d, edi
0x1400083b6  lea     rcx, aTload64bitdlls_4; "TLoad64BitDllsMgr::StillAlive"
0x1400083bd  call    ?WriteDbgTraceInfo@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1400083c2  call    cs:__imp_GetTickCount64
0x1400083c8  mov     [rsi+50h], rax
0x1400083cc  lea     rcx, [rsi+58h]; lpCriticalSection
0x1400083d0  call    cs:__imp_LeaveCriticalSection
0x1400083d6  mov     rbx, [rsp+48h+arg_8]
0x1400083db  mov     eax, ebp
0x1400083dd  mov     rbp, [rsp+48h+arg_10]
0x1400083e2  add     rsp, 30h
0x1400083e6  pop     r14
0x1400083e8  pop     rdi
0x1400083e9  pop     rsi
0x1400083ea  retn
```
