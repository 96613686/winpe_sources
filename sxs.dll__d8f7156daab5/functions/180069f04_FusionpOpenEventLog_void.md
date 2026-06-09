# FusionpOpenEventLog(void)

- ea: `0x180069f04`
- end: `0x180069f95`
- name: `?FusionpOpenEventLog@@YAHXZ`
- size: `145`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180058ab4`

## callees

- `0x18000c000`
- `0x180069f04`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069f2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069f2e`
- `ADVAPI32!DeregisterEventSource` at `0x180069f64`
- `ADVAPI32!DeregisterEventSource` at `0x180069f64`
- `ADVAPI32!RegisterEventSourceW` at `0x180069f1a`
- `ADVAPI32!RegisterEventSourceW` at `0x180069f1a`

## string_xrefs

- `0x180069f44`: `SXS.DLL: FusionpOpenEventLog/RegisterEventSourceW failed %lx\n`
- `0x180069f11`: `SideBySide`

## pseudocode

```c
_BOOL8 FusionpOpenEventLog(void)
{
  HANDLE v0; // rax
  DWORD LastError; // eax

  if ( !g_fEventLogOpenAttempted )
  {
    v0 = RegisterEventSourceW(0, L"SideBySide");
    if ( v0 )
    {
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_hEventLog, (signed __int64)v0, 0) )
        DeregisterEventSource(v0);
      else
        g_hEventLog = v0;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError != 1722 )
        FusionpDbgPrintEx(0xC0000000, "SXS.DLL: FusionpOpenEventLog/RegisterEventSourceW failed %lx\n", LastError);
    }
  }
  g_fEventLogOpenAttempted = 1;
  return g_hEventLog != 0;
}

```

## disassembly

```asm
0x180069f04  sub     rsp, 28h
0x180069f08  cmp     cs:?g_fEventLogOpenAttempted@@3HA, 0; int g_fEventLogOpenAttempted
0x180069f0f  jnz     short loc_180069F79
0x180069f11  lea     rdx, SourceName; "SideBySide"
0x180069f18  xor     ecx, ecx; lpUNCServerName
0x180069f1a  call    cs:__imp_RegisterEventSourceW
0x180069f21  nop     dword ptr [rax+rax+00h]
0x180069f26  mov     rcx, rax; hEventLog
0x180069f29  test    rax, rax
0x180069f2c  jnz     short loc_180069F57
0x180069f2e  call    cs:__imp_GetLastError
0x180069f35  nop     dword ptr [rax+rax+00h]
0x180069f3a  cmp     eax, 6BAh
0x180069f3f  jz      short loc_180069F79
0x180069f41  mov     r8d, eax
0x180069f44  lea     rdx, aSxsDllFusionpo; "SXS.DLL: FusionpOpenEventLog/RegisterEv"...
0x180069f4b  mov     ecx, 0C0000000h; unsigned int
0x180069f50  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x180069f55  jmp     short loc_180069F79
0x180069f57  xor     eax, eax
0x180069f59  lock cmpxchg cs:?g_hEventLog@@3PEAXEA, rcx; void * g_hEventLog
0x180069f62  jz      short loc_180069F72
0x180069f64  call    cs:__imp_DeregisterEventSource
0x180069f6b  nop     dword ptr [rax+rax+00h]
0x180069f70  jmp     short loc_180069F79
0x180069f72  mov     cs:?g_hEventLog@@3PEAXEA, rcx; void * g_hEventLog
0x180069f79  xor     eax, eax
0x180069f7b  mov     cs:?g_fEventLogOpenAttempted@@3HA, 1; int g_fEventLogOpenAttempted
0x180069f85  cmp     cs:?g_hEventLog@@3PEAXEA, rax; void * g_hEventLog
0x180069f8c  setnz   al
0x180069f8f  add     rsp, 28h
0x180069f93  retn
```
