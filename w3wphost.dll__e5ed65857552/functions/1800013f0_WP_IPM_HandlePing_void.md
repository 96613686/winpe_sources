# WP_IPM::HandlePing(void)

- ea: `0x1800013f0`
- end: `0x180001496`
- name: `?HandlePing@WP_IPM@@AEAAJXZ`
- size: `166`
- prototype: `__int64 __fastcall(WP_IPM *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001180`

## callees

- `0x1800013f0`
- `0x1800014a0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180001425`
- `msvcrt!memcpy_s` at `0x180001425`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001407`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001407`
- `iisutil!PuDbgPrint` at `0x180001488`
- `iisutil!PuDbgPrint` at `0x180001488`

## string_xrefs

- `0x180001481`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`

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
0x1800013f0  push    rbx
0x1800013f2  sub     rsp, 30h
0x1800013f6  mov     rbx, rcx
0x1800013f9  mov     qword ptr [rsp+38h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180001402  lea     rcx, [rsp+38h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001407  call    cs:__imp_GetSystemTimeAsFileTime
0x18000140e  nop     dword ptr [rax+rax+00h]
0x180001413  mov     r9d, 8; SourceSize
0x180001419  lea     rcx, [rbx+50h]; Destination
0x18000141d  mov     edx, r9d; DestinationSize
0x180001420  lea     r8, [rsp+38h+SystemTimeAsFileTime]; Source
0x180001425  call    cs:__imp_memcpy_s
0x18000142c  nop     dword ptr [rax+rax+00h]
0x180001431  mov     eax, cs:g_dwDebugFlags
0x180001437  test    al, 3
0x180001439  setnz   cl; this
0x18000143c  bt      eax, 13h
0x180001440  setb    al
0x180001443  test    al, cl
0x180001445  jnz     short loc_180001461
0x180001447  lock inc dword ptr [rbx+3Ch]
0x18000144b  mov     eax, 1
0x180001450  xchg    eax, [rbx+30h]
0x180001453  call    ?CheckHealth@W3WP_HOST@@QEAAXXZ; W3WP_HOST::CheckHealth(void)
0x180001458  xor     eax, eax
0x18000145a  add     rsp, 30h
0x18000145e  pop     rbx
0x18000145f  retn
0x180001461  mov     rcx, cs:g_pDebug
0x180001468  lea     rax, aHandlePing; "Handle Ping\n\n"
0x18000146f  lea     r9, aWpIpmHandlepin; "WP_IPM::HandlePing"
0x180001476  mov     [rsp+38h+var_18], rax
0x18000147b  mov     r8d, 284h
0x180001481  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180001488  call    cs:__imp_PuDbgPrint
0x18000148f  nop     dword ptr [rax+rax+00h]
0x180001494  jmp     short loc_180001447
```
