# WP_IPM::ReportHealthy(void)

- ea: `0x1800016e0`
- end: `0x180001823`
- name: `?ReportHealthy@WP_IPM@@QEAAXXZ`
- size: `323`
- prototype: `void __fastcall(WP_IPM *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180001480`
- `0x1800016a0`

## callees

- `0x1800016e0`
- `0x180001830`
- `0x180008270`
- `0x18000d010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180001751`
- `msvcrt!memcpy_s` at `0x180001751`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001738`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001738`
- `iisutil!PuDbgPrint` at `0x1800017bf`
- `iisutil!PuDbgPrint` at `0x18000180b`
- `iisutil!PuDbgPrint` at `0x1800017bf`
- `iisutil!PuDbgPrint` at `0x18000180b`

## string_xrefs

- `0x1800017b8`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`
- `0x180001804`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`

## pseudocode

```c
void __fastcall WP_IPM::ReportHealthy(WP_IPM *this)
{
  __int64 Destination; // [rsp+40h] [rbp+8h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+10h] BYREF

  Destination = 0;
  SystemTimeAsFileTime = 0;
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x80000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wpipm.cxx",
      1215,
      "WP_IPM::ReportHealthy",
      "Sending ping response\n\n");
  _InterlockedExchange((volatile __int32 *)this + 12, 0);
  if ( (int)WP_IPM::WriteMessage((__int64)this, 2, 0, 0) < 0
    && (g_dwDebugFlags & 3) != 0
    && (g_dwDebugFlags & 0x80000) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wpipm.cxx",
      1241,
      "WP_IPM::ReportHealthy",
      "Failed to respond to ping\n\n");
  }
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  memcpy_s(&Destination, 8u, &SystemTimeAsFileTime, 8u);
  Destination -= *((_QWORD *)this + 10);
  (*(void (__fastcall **)(char *, _QWORD, __int64))(*((_QWORD *)g_pW3WPHost + 6) + 40LL))(
    (char *)g_pW3WPHost + 48,
    0,
    7);
  if ( *((_DWORD *)this + 14) )
    WP_IPM::SendUnhealthyMessage(this);
}

```

## disassembly

```asm
0x1800016e0  mov     [rsp+arg_10], rbx
0x1800016e5  push    rdi
0x1800016e6  sub     rsp, 30h
0x1800016ea  mov     eax, cs:g_dwDebugFlags
0x1800016f0  xor     edi, edi
0x1800016f2  test    al, 3
0x1800016f4  mov     [rsp+38h+Destination], rdi
0x1800016f9  mov     rbx, rcx
0x1800016fc  mov     qword ptr [rsp+38h+SystemTimeAsFileTime.dwLowDateTime], rdi
0x180001701  setnz   cl
0x180001704  bt      eax, 13h
0x180001708  setb    al
0x18000170b  test    al, cl
0x18000170d  jnz     loc_180001798
0x180001713  mov     eax, edi
0x180001715  xor     r9d, r9d
0x180001718  xchg    eax, [rbx+30h]
0x18000171b  xor     r8d, r8d
0x18000171e  mov     edx, 2
0x180001723  mov     rcx, rbx
0x180001726  call    ?WriteMessage@WP_IPM@@AEAAJW4IPM_OPCODE@@KPEAX@Z; WP_IPM::WriteMessage(IPM_OPCODE,ulong,void *)
0x18000172b  test    eax, eax
0x18000172d  js      loc_1800017CA
0x180001733  lea     rcx, [rsp+38h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001738  call    cs:__imp_GetSystemTimeAsFileTime
0x18000173e  mov     r9d, 8; SourceSize
0x180001744  lea     r8, [rsp+38h+SystemTimeAsFileTime]; Source
0x180001749  mov     edx, r9d; DestinationSize
0x18000174c  lea     rcx, [rsp+38h+Destination]; Destination
0x180001751  call    cs:__imp_memcpy_s
0x180001757  mov     r9, [rsp+38h+Destination]
0x18000175c  xor     edx, edx
0x18000175e  mov     rcx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x180001765  mov     r8d, 7
0x18000176b  sub     r9, [rbx+50h]
0x18000176f  add     rcx, 30h ; '0'
0x180001773  mov     [rsp+38h+Destination], r9
0x180001778  mov     rax, [rcx]
0x18000177b  mov     rax, [rax+28h]
0x18000177f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001784  cmp     [rbx+38h], edi
0x180001787  jnz     loc_180001816
0x18000178d  mov     rbx, [rsp+38h+arg_10]
0x180001792  add     rsp, 30h
0x180001796  pop     rdi
0x180001797  retn
0x180001798  mov     rcx, cs:g_pDebug
0x18000179f  lea     rax, aSendingPingRes; "Sending ping response\n\n"
0x1800017a6  lea     r9, aWpIpmReporthea; "WP_IPM::ReportHealthy"
0x1800017ad  mov     [rsp+38h+var_18], rax
0x1800017b2  mov     r8d, 4BFh
0x1800017b8  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800017bf  call    cs:__imp_PuDbgPrint
0x1800017c5  jmp     loc_180001713
0x1800017ca  mov     eax, cs:g_dwDebugFlags
0x1800017d0  test    al, 3
0x1800017d2  setnz   cl
0x1800017d5  bt      eax, 13h
0x1800017d9  setb    al
0x1800017dc  test    al, cl
0x1800017de  jz      loc_180001733
0x1800017e4  mov     rcx, cs:g_pDebug
0x1800017eb  lea     rax, aFailedToRespon; "Failed to respond to ping\n\n"
0x1800017f2  lea     r9, aWpIpmReporthea; "WP_IPM::ReportHealthy"
0x1800017f9  mov     [rsp+38h+var_18], rax
0x1800017fe  mov     r8d, 4D9h
0x180001804  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000180b  call    cs:__imp_PuDbgPrint
0x180001811  jmp     loc_180001733
0x180001816  mov     rcx, rbx; this
0x180001819  call    ?SendUnhealthyMessage@WP_IPM@@AEAAXXZ; WP_IPM::SendUnhealthyMessage(void)
0x18000181e  jmp     loc_18000178D
```
