# WP_IPM::HandlePing(void)

- ea: `0x1800013e0`
- end: `0x180001473`
- name: `?HandlePing@WP_IPM@@AEAAJXZ`
- size: `147`
- prototype: `__int64 __fastcall(WP_IPM *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001170`

## callees

- `0x1800013e0`
- `0x180001480`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000140f`
- `msvcrt!memcpy_s` at `0x18000140f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800013f7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800013f7`
- `iisutil!PuDbgPrint` at `0x18000146b`
- `iisutil!PuDbgPrint` at `0x18000146b`

## string_xrefs

- `0x180001464`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`

## pseudocode

```c
__int64 __fastcall WP_IPM::HandlePing(WP_IPM *this)
{
  W3WP_HOST *v2; // rcx
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+8h] BYREF

  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  memcpy_s((char *)this + 80, 8u, &SystemTimeAsFileTime, 8u);
  LOBYTE(v2) = (g_dwDebugFlags & 3) != 0;
  if ( ((unsigned __int8)v2 & ((g_dwDebugFlags & 0x80000) != 0)) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wpipm.cxx",
      644,
      "WP_IPM::HandlePing",
      "Handle Ping\n\n");
  _InterlockedIncrement((volatile signed __int32 *)this + 15);
  _InterlockedExchange((volatile __int32 *)this + 12, 1);
  W3WP_HOST::CheckHealth(v2);
  return 0;
}

```

## disassembly

```asm
0x1800013e0  push    rbx
0x1800013e2  sub     rsp, 30h
0x1800013e6  mov     rbx, rcx
0x1800013e9  mov     qword ptr [rsp+38h+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800013f2  lea     rcx, [rsp+38h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800013f7  call    cs:__imp_GetSystemTimeAsFileTime
0x1800013fd  mov     r9d, 8; SourceSize
0x180001403  lea     rcx, [rbx+50h]; Destination
0x180001407  mov     edx, r9d; DestinationSize
0x18000140a  lea     r8, [rsp+38h+SystemTimeAsFileTime]; Source
0x18000140f  call    cs:__imp_memcpy_s
0x180001415  mov     eax, cs:g_dwDebugFlags
0x18000141b  test    al, 3
0x18000141d  setnz   cl; this
0x180001420  bt      eax, 13h
0x180001424  setb    al
0x180001427  test    al, cl
0x180001429  jnz     short loc_180001444
0x18000142b  lock inc dword ptr [rbx+3Ch]
0x18000142f  mov     eax, 1
0x180001434  xchg    eax, [rbx+30h]
0x180001437  call    ?CheckHealth@W3WP_HOST@@QEAAXXZ; W3WP_HOST::CheckHealth(void)
0x18000143c  xor     eax, eax
0x18000143e  add     rsp, 30h
0x180001442  pop     rbx
0x180001443  retn
0x180001444  mov     rcx, cs:g_pDebug
0x18000144b  lea     rax, aHandlePing; "Handle Ping\n\n"
0x180001452  lea     r9, aWpIpmHandlepin; "WP_IPM::HandlePing"
0x180001459  mov     [rsp+38h+var_18], rax
0x18000145e  mov     r8d, 284h
0x180001464  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000146b  call    cs:__imp_PuDbgPrint
0x180001471  jmp     short loc_18000142B
```
