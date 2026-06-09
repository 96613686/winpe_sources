# WP_IPM::SendFatalFailure(IPM_WP_SHUTDOWN_MSG)

- ea: `0x1800089f4`
- end: `0x180008ace`
- name: `?SendFatalFailure@WP_IPM@@QEAAXW4IPM_WP_SHUTDOWN_MSG@@@Z`
- size: `218`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800067f4`
- `0x180006c50`

## callees

- `0x1800089f4`
- `0x180008ad4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008a16`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008a16`
- `iisutil!PuDbgPrint` at `0x180008a5f`
- `iisutil!PuDbgPrint` at `0x180008ab6`
- `iisutil!PuDbgPrint` at `0x180008a5f`
- `iisutil!PuDbgPrint` at `0x180008ab6`

## string_xrefs

- `0x180008a58`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`
- `0x180008aaf`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`

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
0x1800089f4  mov     [rsp+arg_0], rbx
0x1800089f9  push    rdi
0x1800089fa  sub     rsp, 30h
0x1800089fe  cmp     dword ptr [rcx+34h], 0
0x180008a02  mov     edi, edx
0x180008a04  mov     rbx, rcx
0x180008a07  jz      short loc_180008A22
0x180008a09  xor     r9d, r9d; lpArguments
0x180008a0c  xor     r8d, r8d; nNumberOfArguments
0x180008a0f  xor     edx, edx; dwExceptionFlags
0x180008a11  mov     ecx, 0C0000005h; dwExceptionCode
0x180008a16  call    cs:__imp_RaiseException
0x180008a1d  nop     dword ptr [rax+rax+00h]
0x180008a22  mov     eax, cs:g_dwDebugFlags
0x180008a28  test    al, 3
0x180008a2a  setnz   cl
0x180008a2d  bt      eax, 13h
0x180008a31  setb    al
0x180008a34  test    al, cl
0x180008a36  jz      short loc_180008A6B
0x180008a38  mov     rcx, cs:g_pDebug
0x180008a3f  lea     rax, aSendindFatalFa; "Sendind fatal failure preload failure\n"...
0x180008a46  lea     r9, aWpIpmSendfatal; "WP_IPM::SendFatalFailure"
0x180008a4d  mov     [rsp+38h+var_18], rax
0x180008a52  mov     r8d, 586h
0x180008a58  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008a5f  call    cs:__imp_PuDbgPrint
0x180008a66  nop     dword ptr [rax+rax+00h]
0x180008a6b  mov     edx, edi
0x180008a6d  mov     rcx, rbx
0x180008a70  call    ?SendShutdownRequestMessage@WP_IPM@@QEAAJW4IPM_WP_SHUTDOWN_MSG@@@Z; WP_IPM::SendShutdownRequestMessage(IPM_WP_SHUTDOWN_MSG)
0x180008a75  test    eax, eax
0x180008a77  jns     short loc_180008AC2
0x180008a79  mov     eax, cs:g_dwDebugFlags
0x180008a7f  test    al, 3
0x180008a81  setnz   cl
0x180008a84  bt      eax, 13h
0x180008a88  setb    al
0x180008a8b  test    al, cl
0x180008a8d  jz      short loc_180008AC2
0x180008a8f  mov     rcx, cs:g_pDebug
0x180008a96  lea     rax, aFailedTellingW; "Failed telling WAS to shut us down\n\n"
0x180008a9d  lea     r9, aWpIpmSendfatal; "WP_IPM::SendFatalFailure"
0x180008aa4  mov     [rsp+38h+var_18], rax
0x180008aa9  mov     r8d, 590h
0x180008aaf  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008ab6  call    cs:__imp_PuDbgPrint
0x180008abd  nop     dword ptr [rax+rax+00h]
0x180008ac2  mov     rbx, [rsp+38h+arg_0]
0x180008ac7  add     rsp, 30h
0x180008acb  pop     rdi
0x180008acc  retn
```
