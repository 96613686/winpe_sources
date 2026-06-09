# W3WP_HOST::CreateCounterSetInstance(ulong)

- ea: `0x180003900`
- end: `0x180003b23`
- name: `?CreateCounterSetInstance@W3WP_HOST@@UEAAJK@Z`
- size: `547`
- prototype: `__int64 __fastcall(W3WP_HOST *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003900`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a98`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x18000398a`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x180003a6f`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x18000398a`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x180003a6f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003973`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003a57`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003973`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003a57`
- `iisutil!PuDbgPrintError` at `0x180003a07`
- `iisutil!PuDbgPrintError` at `0x180003b10`
- `iisutil!PuDbgPrintError` at `0x180003a07`
- `iisutil!PuDbgPrintError` at `0x180003b10`

## string_xrefs

- `0x180003a00`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x180003afb`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x1800039f9`: `W3WP_HOST::CreateCounterSetInstance`
- `0x180003aef`: `W3WP_HOST::CreateCounterSetInstance`
- `0x1800039dc`: `Failed to create counter set instance for WAS_W3WP.\n`
- `0x180003abd`: `Failed to create counter set instance for W3SVC_W3WP.\n`

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
0x180003900  mov     [rsp+arg_0], rbx
0x180003905  push    rdi
0x180003906  sub     rsp, 40h
0x18000390a  mov     rax, [rcx+108h]
0x180003911  mov     rdi, rcx
0x180003914  cmp     dword ptr [rax+58h], 0
0x180003918  jz      short loc_180003921
0x18000391a  xor     eax, eax
0x18000391c  jmp     loc_180003B18
0x180003921  xor     ebx, ebx
0x180003923  cmp     [rcx+48h], ebx
0x180003926  jz      loc_180003B16
0x18000392c  test    edx, edx
0x18000392e  jnz     loc_180003A12
0x180003934  mov     rax, [rcx+40h]
0x180003938  cmp     [rax+20h], rbx
0x18000393c  jz      short loc_18000396F
0x18000393e  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180003945  mov     ebx, 8000FFFFh
0x18000394a  jz      loc_180003B16
0x180003950  lea     rax, aDoubleInitiali; "Double initialization of WAS_W3WP count"...
0x180003957  mov     r8d, 487h
0x18000395d  mov     [rsp+48h+var_20], rax
0x180003962  mov     [rsp+48h+var_28], 8000FFFFh
0x18000396a  jmp     loc_1800039F2
0x18000396f  add     rcx, 50h ; 'P'
0x180003973  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180003979  mov     rcx, [rdi+40h]
0x18000397d  xor     r9d, r9d; Id
0x180003980  mov     r8, rax; Name
0x180003983  mov     rdx, [rcx+18h]; CounterSetGuid
0x180003987  mov     rcx, [rcx]; ProviderHandle
0x18000398a  call    cs:__imp_PerfCreateInstance
0x180003990  mov     rcx, rax
0x180003993  mov     rax, [rdi+40h]
0x180003997  mov     [rax+20h], rcx
0x18000399b  mov     rax, [rdi+40h]
0x18000399f  cmp     [rax+20h], rbx
0x1800039a3  jnz     loc_180003B16
0x1800039a9  call    cs:__imp_GetLastError
0x1800039af  test    eax, eax
0x1800039b1  jz      short loc_1800039CA
0x1800039b3  call    cs:__imp_GetLastError
0x1800039b9  mov     ebx, eax
0x1800039bb  test    eax, eax
0x1800039bd  jle     short loc_1800039CF
0x1800039bf  movzx   ebx, ax
0x1800039c2  or      ebx, 80070000h
0x1800039c8  jmp     short loc_1800039CF
0x1800039ca  mov     ebx, 80004005h
0x1800039cf  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800039d6  jz      loc_180003B16
0x1800039dc  lea     rax, aFailedToCreate_4; "Failed to create counter set instance f"...
0x1800039e3  mov     r8d, 4A3h
0x1800039e9  mov     [rsp+48h+var_20], rax
0x1800039ee  mov     [rsp+48h+var_28], ebx
0x1800039f2  mov     rcx, cs:g_pDebug
0x1800039f9  lea     r9, aW3wpHostCreate; "W3WP_HOST::CreateCounterSetInstance"
0x180003a00  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180003a07  call    cs:__imp_PuDbgPrintError
0x180003a0d  jmp     loc_180003B16
0x180003a12  cmp     edx, 1
0x180003a15  jnz     loc_180003ACF
0x180003a1b  mov     rax, [rcx+40h]
0x180003a1f  cmp     [rax+38h], rbx
0x180003a23  jz      short loc_180003A53
0x180003a25  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180003a2c  mov     ebx, 8000FFFFh
0x180003a31  jz      loc_180003B16
0x180003a37  lea     rax, aDoubleInitiali_0; "Double initialization of W3SVC_W3WP cou"...
0x180003a3e  mov     r8d, 4B6h
0x180003a44  mov     [rsp+48h+var_20], rax
0x180003a49  mov     [rsp+48h+var_28], 8000FFFFh
0x180003a51  jmp     short loc_1800039F2
0x180003a53  add     rcx, 50h ; 'P'
0x180003a57  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180003a5d  mov     rcx, [rdi+40h]
0x180003a61  xor     r9d, r9d; Id
0x180003a64  mov     r8, rax; Name
0x180003a67  mov     rdx, [rcx+30h]; CounterSetGuid
0x180003a6b  mov     rcx, [rcx+8]; ProviderHandle
0x180003a6f  call    cs:__imp_PerfCreateInstance
0x180003a75  mov     rcx, rax
0x180003a78  mov     rax, [rdi+40h]
0x180003a7c  mov     [rax+38h], rcx
0x180003a80  mov     rax, [rdi+40h]
0x180003a84  cmp     [rax+38h], rbx
0x180003a88  jnz     loc_180003B16
0x180003a8e  call    cs:__imp_GetLastError
0x180003a94  test    eax, eax
0x180003a96  jz      short loc_180003AAF
0x180003a98  call    cs:__imp_GetLastError
0x180003a9e  mov     ebx, eax
0x180003aa0  test    eax, eax
0x180003aa2  jle     short loc_180003AB4
0x180003aa4  movzx   ebx, ax
0x180003aa7  or      ebx, 80070000h
0x180003aad  jmp     short loc_180003AB4
0x180003aaf  mov     ebx, 80004005h
0x180003ab4  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180003abb  jz      short loc_180003B16
0x180003abd  lea     rax, aFailedToCreate_5; "Failed to create counter set instance f"...
0x180003ac4  mov     r8d, 4D2h
0x180003aca  jmp     loc_1800039E9
0x180003acf  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180003ad6  mov     ebx, 8000FFFFh
0x180003adb  jz      short loc_180003B16
0x180003add  mov     rcx, cs:g_pDebug
0x180003ae4  lea     rax, aInvalidCounter; "Invalid CounterSet ID (%d).\n"
0x180003aeb  mov     [rsp+48h+var_18], edx
0x180003aef  lea     r9, aW3wpHostCreate; "W3WP_HOST::CreateCounterSetInstance"
0x180003af6  mov     [rsp+48h+var_20], rax
0x180003afb  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180003b02  mov     r8d, 4E1h
0x180003b08  mov     [rsp+48h+var_28], 8000FFFFh
0x180003b10  call    cs:__imp_PuDbgPrintError
0x180003b16  mov     eax, ebx
0x180003b18  mov     rbx, [rsp+48h+arg_0]
0x180003b1d  add     rsp, 40h
0x180003b21  pop     rdi
0x180003b22  retn
```
