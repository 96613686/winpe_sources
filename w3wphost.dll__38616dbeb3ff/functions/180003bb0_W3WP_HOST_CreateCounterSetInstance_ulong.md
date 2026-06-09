# W3WP_HOST::CreateCounterSetInstance(ulong)

- ea: `0x180003bb0`
- end: `0x180003e10`
- name: `?CreateCounterSetInstance@W3WP_HOST@@UEAAJK@Z`
- size: `608`
- prototype: `__int64 __fastcall(W3WP_HOST *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003bb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d78`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x180003c40`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x180003d43`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x180003c40`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x180003d43`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003c23`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003d25`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003c23`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003d25`
- `iisutil!PuDbgPrintError` at `0x180003ccf`
- `iisutil!PuDbgPrintError` at `0x180003df6`
- `iisutil!PuDbgPrintError` at `0x180003ccf`
- `iisutil!PuDbgPrintError` at `0x180003df6`

## string_xrefs

- `0x180003cc8`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x180003de1`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x180003cc1`: `W3WP_HOST::CreateCounterSetInstance`
- `0x180003dd5`: `W3WP_HOST::CreateCounterSetInstance`
- `0x180003ca4`: `Failed to create counter set instance for WAS_W3WP.\n`
- `0x180003da3`: `Failed to create counter set instance for W3SVC_W3WP.\n`

## pseudocode

```c
__int64 __fastcall W3WP_HOST::CreateCounterSetInstance(W3WP_HOST *this, int a2)
{
  unsigned int v4; // ebx
  const WCHAR *v5; // rax
  signed int v6; // eax
  const char *v7; // rax
  __int64 v8; // r8
  const WCHAR *Str; // rax
  signed int LastError; // eax

  if ( *(_DWORD *)(*((_QWORD *)this + 33) + 88LL) )
    return 0;
  v4 = 0;
  if ( *((_DWORD *)this + 18) )
  {
    if ( a2 )
    {
      if ( a2 != 1 )
      {
        v4 = -2147418113;
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
            1249,
            "W3WP_HOST::CreateCounterSetInstance",
            -2147418113,
            "Invalid CounterSet ID (%d).\n",
            a2);
        return v4;
      }
      if ( *(_QWORD *)(*((_QWORD *)this + 8) + 56LL) )
      {
        v4 = -2147418113;
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
            1206,
            "W3WP_HOST::CreateCounterSetInstance",
            -2147418113,
            "Double initialization of W3SVC_W3WP counter set.\n");
        return v4;
      }
      Str = STRU::QueryStr((W3WP_HOST *)((char *)this + 80));
      *(_QWORD *)(*((_QWORD *)this + 8) + 56LL) = PerfCreateInstance(
                                                    *(HANDLE *)(*((_QWORD *)this + 8) + 8LL),
                                                    *(LPCGUID *)(*((_QWORD *)this + 8) + 48LL),
                                                    Str,
                                                    0);
      if ( *(_QWORD *)(*((_QWORD *)this + 8) + 56LL) )
        return v4;
      if ( GetLastError() )
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v4 = -2147467259;
      }
      if ( (g_dwDebugFlags & 0xF) == 0 )
        return v4;
      v7 = "Failed to create counter set instance for W3SVC_W3WP.\n";
      v8 = 1234;
    }
    else
    {
      if ( *(_QWORD *)(*((_QWORD *)this + 8) + 32LL) )
      {
        v4 = -2147418113;
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
            1159,
            "W3WP_HOST::CreateCounterSetInstance",
            -2147418113,
            "Double initialization of WAS_W3WP counter set.\n");
        return v4;
      }
      v5 = STRU::QueryStr((W3WP_HOST *)((char *)this + 80));
      *(_QWORD *)(*((_QWORD *)this + 8) + 32LL) = PerfCreateInstance(
                                                    **((HANDLE **)this + 8),
                                                    *(LPCGUID *)(*((_QWORD *)this + 8) + 24LL),
                                                    v5,
                                                    0);
      if ( *(_QWORD *)(*((_QWORD *)this + 8) + 32LL) )
        return v4;
      if ( GetLastError() )
      {
        v6 = GetLastError();
        v4 = v6;
        if ( v6 > 0 )
          v4 = (unsigned __int16)v6 | 0x80070000;
      }
      else
      {
        v4 = -2147467259;
      }
      if ( (g_dwDebugFlags & 0xF) == 0 )
        return v4;
      v7 = "Failed to create counter set instance for WAS_W3WP.\n";
      v8 = 1187;
    }
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
      v8,
      "W3WP_HOST::CreateCounterSetInstance",
      v4,
      v7);
  }
  return v4;
}

```

## disassembly

```asm
0x180003bb0  mov     [rsp+arg_0], rbx
0x180003bb5  push    rdi
0x180003bb6  sub     rsp, 40h
0x180003bba  mov     rax, [rcx+108h]
0x180003bc1  mov     rdi, rcx
0x180003bc4  cmp     dword ptr [rax+58h], 0
0x180003bc8  jz      short loc_180003BD1
0x180003bca  xor     eax, eax
0x180003bcc  jmp     loc_180003E04
0x180003bd1  xor     ebx, ebx
0x180003bd3  cmp     [rcx+48h], ebx
0x180003bd6  jz      loc_180003E02
0x180003bdc  test    edx, edx
0x180003bde  jnz     loc_180003CE0
0x180003be4  mov     rax, [rcx+40h]
0x180003be8  cmp     [rax+20h], rbx
0x180003bec  jz      short loc_180003C1F
0x180003bee  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180003bf5  mov     ebx, 8000FFFFh
0x180003bfa  jz      loc_180003E02
0x180003c00  lea     rax, aDoubleInitiali; "Double initialization of WAS_W3WP count"...
0x180003c07  mov     r8d, 487h
0x180003c0d  mov     [rsp+48h+var_20], rax
0x180003c12  mov     [rsp+48h+var_28], 8000FFFFh
0x180003c1a  jmp     loc_180003CBA
0x180003c1f  add     rcx, 50h ; 'P'
0x180003c23  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180003c2a  nop     dword ptr [rax+rax+00h]
0x180003c2f  mov     rcx, [rdi+40h]
0x180003c33  xor     r9d, r9d; Id
0x180003c36  mov     r8, rax; Name
0x180003c39  mov     rdx, [rcx+18h]; CounterSetGuid
0x180003c3d  mov     rcx, [rcx]; ProviderHandle
0x180003c40  call    cs:__imp_PerfCreateInstance
0x180003c47  nop     dword ptr [rax+rax+00h]
0x180003c4c  mov     rcx, rax
0x180003c4f  mov     rax, [rdi+40h]
0x180003c53  mov     [rax+20h], rcx
0x180003c57  mov     rax, [rdi+40h]
0x180003c5b  cmp     [rax+20h], rbx
0x180003c5f  jnz     loc_180003E02
0x180003c65  call    cs:__imp_GetLastError
0x180003c6c  nop     dword ptr [rax+rax+00h]
0x180003c71  test    eax, eax
0x180003c73  jz      short loc_180003C92
0x180003c75  call    cs:__imp_GetLastError
0x180003c7c  nop     dword ptr [rax+rax+00h]
0x180003c81  mov     ebx, eax
0x180003c83  test    eax, eax
0x180003c85  jle     short loc_180003C97
0x180003c87  movzx   ebx, ax
0x180003c8a  or      ebx, 80070000h
0x180003c90  jmp     short loc_180003C97
0x180003c92  mov     ebx, 80004005h
0x180003c97  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180003c9e  jz      loc_180003E02
0x180003ca4  lea     rax, aFailedToCreate_4; "Failed to create counter set instance f"...
0x180003cab  mov     r8d, 4A3h
0x180003cb1  mov     [rsp+48h+var_20], rax
0x180003cb6  mov     [rsp+48h+var_28], ebx
0x180003cba  mov     rcx, cs:g_pDebug
0x180003cc1  lea     r9, aW3wpHostCreate; "W3WP_HOST::CreateCounterSetInstance"
0x180003cc8  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180003ccf  call    cs:__imp_PuDbgPrintError
0x180003cd6  nop     dword ptr [rax+rax+00h]
0x180003cdb  jmp     loc_180003E02
0x180003ce0  cmp     edx, 1
0x180003ce3  jnz     loc_180003DB5
0x180003ce9  mov     rax, [rcx+40h]
0x180003ced  cmp     [rax+38h], rbx
0x180003cf1  jz      short loc_180003D21
0x180003cf3  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180003cfa  mov     ebx, 8000FFFFh
0x180003cff  jz      loc_180003E02
0x180003d05  lea     rax, aDoubleInitiali_0; "Double initialization of W3SVC_W3WP cou"...
0x180003d0c  mov     r8d, 4B6h
0x180003d12  mov     [rsp+48h+var_20], rax
0x180003d17  mov     [rsp+48h+var_28], 8000FFFFh
0x180003d1f  jmp     short loc_180003CBA
0x180003d21  add     rcx, 50h ; 'P'
0x180003d25  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180003d2c  nop     dword ptr [rax+rax+00h]
0x180003d31  mov     rcx, [rdi+40h]
0x180003d35  xor     r9d, r9d; Id
0x180003d38  mov     r8, rax; Name
0x180003d3b  mov     rdx, [rcx+30h]; CounterSetGuid
0x180003d3f  mov     rcx, [rcx+8]; ProviderHandle
0x180003d43  call    cs:__imp_PerfCreateInstance
0x180003d4a  nop     dword ptr [rax+rax+00h]
0x180003d4f  mov     rcx, rax
0x180003d52  mov     rax, [rdi+40h]
0x180003d56  mov     [rax+38h], rcx
0x180003d5a  mov     rax, [rdi+40h]
0x180003d5e  cmp     [rax+38h], rbx
0x180003d62  jnz     loc_180003E02
0x180003d68  call    cs:__imp_GetLastError
0x180003d6f  nop     dword ptr [rax+rax+00h]
0x180003d74  test    eax, eax
0x180003d76  jz      short loc_180003D95
0x180003d78  call    cs:__imp_GetLastError
0x180003d7f  nop     dword ptr [rax+rax+00h]
0x180003d84  mov     ebx, eax
0x180003d86  test    eax, eax
0x180003d88  jle     short loc_180003D9A
0x180003d8a  movzx   ebx, ax
0x180003d8d  or      ebx, 80070000h
0x180003d93  jmp     short loc_180003D9A
0x180003d95  mov     ebx, 80004005h
0x180003d9a  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180003da1  jz      short loc_180003E02
0x180003da3  lea     rax, aFailedToCreate_5; "Failed to create counter set instance f"...
0x180003daa  mov     r8d, 4D2h
0x180003db0  jmp     loc_180003CB1
0x180003db5  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180003dbc  mov     ebx, 8000FFFFh
0x180003dc1  jz      short loc_180003E02
0x180003dc3  mov     rcx, cs:g_pDebug
0x180003dca  lea     rax, aInvalidCounter; "Invalid CounterSet ID (%d).\n"
0x180003dd1  mov     [rsp+48h+var_18], edx
0x180003dd5  lea     r9, aW3wpHostCreate; "W3WP_HOST::CreateCounterSetInstance"
0x180003ddc  mov     [rsp+48h+var_20], rax
0x180003de1  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180003de8  mov     r8d, 4E1h
0x180003dee  mov     [rsp+48h+var_28], 8000FFFFh
0x180003df6  call    cs:__imp_PuDbgPrintError
0x180003dfd  nop     dword ptr [rax+rax+00h]
0x180003e02  mov     eax, ebx
0x180003e04  mov     rbx, [rsp+48h+arg_0]
0x180003e09  add     rsp, 40h
0x180003e0d  pop     rdi
0x180003e0e  retn
```
