# WP_IPM::SendFatalFailure(IPM_WP_SHUTDOWN_MSG)

- ea: `0x18000812c`
- end: `0x1800081f3`
- name: `?SendFatalFailure@WP_IPM@@QEAAXW4IPM_WP_SHUTDOWN_MSG@@@Z`
- size: `199`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800061dc`
- `0x1800065f0`

## callees

- `0x18000812c`
- `0x1800081fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000814e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000814e`
- `iisutil!PuDbgPrint` at `0x180008191`
- `iisutil!PuDbgPrint` at `0x1800081e2`
- `iisutil!PuDbgPrint` at `0x180008191`
- `iisutil!PuDbgPrint` at `0x1800081e2`

## string_xrefs

- `0x18000818a`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`
- `0x1800081db`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`

## pseudocode

```c
char __fastcall WP_IPM::SendFatalFailure(__int64 a1, unsigned int a2)
{
  int v4; // eax

  if ( *(_DWORD *)(a1 + 52) )
    RaiseException(0xC0000005, 0, 0, 0);
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x80000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wpipm.cxx",
      1414,
      "WP_IPM::SendFatalFailure",
      "Sendind fatal failure preload failure\n\n");
  v4 = WP_IPM::SendShutdownRequestMessage(a1, a2);
  if ( v4 < 0 )
  {
    LOBYTE(v4) = (g_dwDebugFlags & 0x80000) != 0;
    if ( (((g_dwDebugFlags & 3) != 0) & (unsigned __int8)v4) != 0 )
      LOBYTE(v4) = PuDbgPrint(
                     g_pDebug,
                     "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wpipm.cxx",
                     1424,
                     "WP_IPM::SendFatalFailure",
                     "Failed telling WAS to shut us down\n\n");
  }
  return v4;
}

```

## disassembly

```asm
0x18000812c  mov     [rsp+arg_0], rbx
0x180008131  push    rdi
0x180008132  sub     rsp, 30h
0x180008136  cmp     dword ptr [rcx+34h], 0
0x18000813a  mov     edi, edx
0x18000813c  mov     rbx, rcx
0x18000813f  jz      short loc_180008154
0x180008141  xor     r9d, r9d; lpArguments
0x180008144  xor     r8d, r8d; nNumberOfArguments
0x180008147  xor     edx, edx; dwExceptionFlags
0x180008149  mov     ecx, 0C0000005h; dwExceptionCode
0x18000814e  call    cs:__imp_RaiseException
0x180008154  mov     eax, cs:g_dwDebugFlags
0x18000815a  test    al, 3
0x18000815c  setnz   cl
0x18000815f  bt      eax, 13h
0x180008163  setb    al
0x180008166  test    al, cl
0x180008168  jz      short loc_180008197
0x18000816a  mov     rcx, cs:g_pDebug
0x180008171  lea     rax, aSendindFatalFa; "Sendind fatal failure preload failure\n"...
0x180008178  lea     r9, aWpIpmSendfatal; "WP_IPM::SendFatalFailure"
0x18000817f  mov     [rsp+38h+var_18], rax
0x180008184  mov     r8d, 586h
0x18000818a  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008191  call    cs:__imp_PuDbgPrint
0x180008197  mov     edx, edi
0x180008199  mov     rcx, rbx
0x18000819c  call    ?SendShutdownRequestMessage@WP_IPM@@QEAAJW4IPM_WP_SHUTDOWN_MSG@@@Z; WP_IPM::SendShutdownRequestMessage(IPM_WP_SHUTDOWN_MSG)
0x1800081a1  test    eax, eax
0x1800081a3  jns     short loc_1800081E8
0x1800081a5  mov     eax, cs:g_dwDebugFlags
0x1800081ab  test    al, 3
0x1800081ad  setnz   cl
0x1800081b0  bt      eax, 13h
0x1800081b4  setb    al
0x1800081b7  test    al, cl
0x1800081b9  jz      short loc_1800081E8
0x1800081bb  mov     rcx, cs:g_pDebug
0x1800081c2  lea     rax, aFailedTellingW; "Failed telling WAS to shut us down\n\n"
0x1800081c9  lea     r9, aWpIpmSendfatal; "WP_IPM::SendFatalFailure"
0x1800081d0  mov     [rsp+38h+var_18], rax
0x1800081d5  mov     r8d, 590h
0x1800081db  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800081e2  call    cs:__imp_PuDbgPrint
0x1800081e8  mov     rbx, [rsp+38h+arg_0]
0x1800081ed  add     rsp, 30h
0x1800081f1  pop     rdi
0x1800081f2  retn
```
