# WP_IPM::ReportHealthy(void)

- ea: `0x180001720`
- end: `0x18000187c`
- name: `?ReportHealthy@WP_IPM@@QEAAXXZ`
- size: `348`
- prototype: `void __fastcall(WP_IPM *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800014a0`
- `0x1800016e0`

## callees

- `0x180001720`
- `0x180001890`
- `0x180008b50`
- `0x18000e010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180001797`
- `msvcrt!memcpy_s` at `0x180001797`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001778`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001778`
- `iisutil!PuDbgPrint` at `0x18000180c`
- `iisutil!PuDbgPrint` at `0x18000185e`
- `iisutil!PuDbgPrint` at `0x18000180c`
- `iisutil!PuDbgPrint` at `0x18000185e`

## string_xrefs

- `0x180001805`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`
- `0x180001857`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`

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
  if ( (int)WP_IPM::WriteMessage(this, 2, 0, 0) < 0 && (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x80000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wpipm.cxx",
      1241,
      "WP_IPM::ReportHealthy",
      "Failed to respond to ping\n\n");
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
0x180001720  mov     [rsp+arg_10], rbx
0x180001725  push    rdi
0x180001726  sub     rsp, 30h
0x18000172a  mov     eax, cs:g_dwDebugFlags
0x180001730  xor     edi, edi
0x180001732  test    al, 3
0x180001734  mov     [rsp+38h+Destination], rdi
0x180001739  mov     rbx, rcx
0x18000173c  mov     qword ptr [rsp+38h+SystemTimeAsFileTime.dwLowDateTime], rdi
0x180001741  setnz   cl
0x180001744  bt      eax, 13h
0x180001748  setb    al
0x18000174b  test    al, cl
0x18000174d  jnz     loc_1800017E5
0x180001753  mov     eax, edi
0x180001755  xor     r9d, r9d
0x180001758  xchg    eax, [rbx+30h]
0x18000175b  xor     r8d, r8d
0x18000175e  mov     edx, 2
0x180001763  mov     rcx, rbx
0x180001766  call    ?WriteMessage@WP_IPM@@AEAAJW4IPM_OPCODE@@KPEAX@Z; WP_IPM::WriteMessage(IPM_OPCODE,ulong,void *)
0x18000176b  test    eax, eax
0x18000176d  js      loc_18000181D
0x180001773  lea     rcx, [rsp+38h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001778  call    cs:__imp_GetSystemTimeAsFileTime
0x18000177f  nop     dword ptr [rax+rax+00h]
0x180001784  mov     r9d, 8; SourceSize
0x18000178a  lea     r8, [rsp+38h+SystemTimeAsFileTime]; Source
0x18000178f  mov     edx, r9d; DestinationSize
0x180001792  lea     rcx, [rsp+38h+Destination]; Destination
0x180001797  call    cs:__imp_memcpy_s
0x18000179e  nop     dword ptr [rax+rax+00h]
0x1800017a3  mov     r9, [rsp+38h+Destination]
0x1800017a8  xor     edx, edx
0x1800017aa  mov     rcx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x1800017b1  mov     r8d, 7
0x1800017b7  sub     r9, [rbx+50h]
0x1800017bb  add     rcx, 30h ; '0'
0x1800017bf  mov     [rsp+38h+Destination], r9
0x1800017c4  mov     rax, [rcx]
0x1800017c7  mov     rax, [rax+28h]
0x1800017cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800017d0  cmp     [rbx+38h], edi
0x1800017d3  jnz     loc_18000186F
0x1800017d9  mov     rbx, [rsp+38h+arg_10]
0x1800017de  add     rsp, 30h
0x1800017e2  pop     rdi
0x1800017e3  retn
0x1800017e5  mov     rcx, cs:g_pDebug
0x1800017ec  lea     rax, aSendingPingRes; "Sending ping response\n\n"
0x1800017f3  lea     r9, aWpIpmReporthea; "WP_IPM::ReportHealthy"
0x1800017fa  mov     [rsp+38h+var_18], rax
0x1800017ff  mov     r8d, 4BFh
0x180001805  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000180c  call    cs:__imp_PuDbgPrint
0x180001813  nop     dword ptr [rax+rax+00h]
0x180001818  jmp     loc_180001753
0x18000181d  mov     eax, cs:g_dwDebugFlags
0x180001823  test    al, 3
0x180001825  setnz   cl
0x180001828  bt      eax, 13h
0x18000182c  setb    al
0x18000182f  test    al, cl
0x180001831  jz      loc_180001773
0x180001837  mov     rcx, cs:g_pDebug
0x18000183e  lea     rax, aFailedToRespon; "Failed to respond to ping\n\n"
0x180001845  lea     r9, aWpIpmReporthea; "WP_IPM::ReportHealthy"
0x18000184c  mov     [rsp+38h+var_18], rax
0x180001851  mov     r8d, 4D9h
0x180001857  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000185e  call    cs:__imp_PuDbgPrint
0x180001865  nop     dword ptr [rax+rax+00h]
0x18000186a  jmp     loc_180001773
0x18000186f  mov     rcx, rbx; this
0x180001872  call    ?SendUnhealthyMessage@WP_IPM@@AEAAXXZ; WP_IPM::SendUnhealthyMessage(void)
0x180001877  jmp     loc_1800017D9
```
