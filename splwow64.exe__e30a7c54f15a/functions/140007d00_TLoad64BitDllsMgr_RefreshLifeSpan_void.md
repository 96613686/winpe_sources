# TLoad64BitDllsMgr::RefreshLifeSpan(void)

- ea: `0x140007d00`
- end: `0x140007d4c`
- name: `?RefreshLifeSpan@TLoad64BitDllsMgr@@QEAAXXZ`
- size: `76`
- prototype: `void __fastcall(TLoad64BitDllsMgr *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140006c10`
- `0x140006f98`
- `0x1400077fc`
- `0x14000dce0`
- `0x14000e680`
- `0x14000f42c`
- `0x14000f5c4`

## callees

- `0x1400086e0`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x140007d17`
- `KERNEL32!GetTickCount64` at `0x140007d17`
- `KERNEL32!EnterCriticalSection` at `0x140007d11`
- `KERNEL32!EnterCriticalSection` at `0x140007d11`
- `KERNEL32!LeaveCriticalSection` at `0x140007d45`

## string_xrefs

- `0x140007d2b`: `TLoad64BitDllsMgr::RefreshLifeSpan`

## pseudocode

```c
void __fastcall TLoad64BitDllsMgr::RefreshLifeSpan(TLoad64BitDllsMgr *this)
{
  ULONGLONG TickCount64; // rax

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  TickCount64 = GetTickCount64();
  *((_QWORD *)this + 10) = TickCount64;
  SplWow64Telemetry::WriteDbgTraceInfo(
    "TLoad64BitDllsMgr::RefreshLifeSpan",
    L"Last Transaction time: %llu",
    TickCount64);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
}

```

## disassembly

```asm
0x140007d00  mov     [rsp+arg_0], rbx
0x140007d05  push    rdi
0x140007d06  sub     rsp, 20h
0x140007d0a  mov     rbx, rcx
0x140007d0d  add     rcx, 58h ; 'X'; lpCriticalSection
0x140007d11  call    cs:__imp_EnterCriticalSection
0x140007d17  call    cs:__imp_GetTickCount64
0x140007d1d  mov     r8, rax
0x140007d20  mov     [rbx+50h], rax
0x140007d24  lea     rdx, aLastTransactio; "Last Transaction time: %llu"
0x140007d2b  lea     rcx, aTload64bitdlls_0; "TLoad64BitDllsMgr::RefreshLifeSpan"
0x140007d32  call    ?WriteDbgTraceInfo@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140007d37  lea     rcx, [rbx+58h]
0x140007d3b  mov     rbx, [rsp+28h+arg_0]
0x140007d40  add     rsp, 20h
0x140007d44  pop     rdi
0x140007d45  jmp     cs:__imp_LeaveCriticalSection
```
