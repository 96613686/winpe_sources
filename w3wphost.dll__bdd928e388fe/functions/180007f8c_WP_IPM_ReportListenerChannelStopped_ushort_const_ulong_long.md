# WP_IPM::ReportListenerChannelStopped(ushort const *,ulong,long)

- ea: `0x180007f8c`
- end: `0x180008125`
- name: `?ReportListenerChannelStopped@WP_IPM@@QEAAXPEBGKJ@Z`
- size: `409`
- prototype: `void __fastcall(WP_IPM *__hidden this, const unsigned __int16 *Src, unsigned int, int)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000a4b0`
- `0x18000abd0`
- `0x18000affc`

## callees

- `0x180001830`
- `0x180007f8c`
- `0x180008270`
- `0x18000c386`
- `0x18000c3d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180007fc1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180007fc1`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180007ff3`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180007ff3`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180007fcc`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180007fcc`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000800f`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000801c`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000802b`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800080e1`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000800f`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000801c`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000802b`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800080e1`
- `iisutil!PuDbgPrint` at `0x18000808c`
- `iisutil!PuDbgPrint` at `0x18000808c`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180008100`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180008100`
- `iisutil!PuDbgPrintError` at `0x1800080d6`
- `iisutil!PuDbgPrintError` at `0x1800080d6`

## string_xrefs

- `0x180008075`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`
- `0x1800080c0`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`
- `0x1800080a8`: `Report ListenerChannel stopped due to failure; ProtocolId:%S, ListenerChannelId:%d\n`

## pseudocode

```c
void __fastcall WP_IPM::ReportListenerChannelStopped(WP_IPM *this, const unsigned __int16 *Src, int a3, int a4)
{
  __int64 v8; // rax
  size_t v9; // rbx
  char *Ptr; // rax
  char v11; // dl
  void *v12; // rax
  _BYTE v13[48]; // [rsp+40h] [rbp-78h] BYREF

  *((_DWORD *)this + 8) = a4;
  SetEvent(*((HANDLE *)this + 3));
  BUFFER::BUFFER((BUFFER *)v13);
  v8 = -1;
  do
    ++v8;
  while ( Src[v8] );
  v9 = (unsigned int)(2 * v8 + 2);
  if ( BUFFER::Resize((BUFFER *)v13, 2 * v8 + 10) )
  {
    *(_DWORD *)BUFFER::QueryPtr((BUFFER *)v13) = a4;
    *((_DWORD *)BUFFER::QueryPtr((BUFFER *)v13) + 1) = a3;
    Ptr = (char *)BUFFER::QueryPtr((BUFFER *)v13);
    memcpy_0(Ptr + 8, Src, v9);
    v11 = g_dwDebugFlags;
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x80000) != 0 )
    {
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wpipm.cxx",
        1734,
        "WP_IPM::ReportListenerChannelStopped",
        "Report ListenerChannel Stopped for: %S, ListenerChannelId:%d hr =0x%x\n");
      v11 = g_dwDebugFlags;
    }
    if ( a4 < 0 && (v11 & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wpipm.cxx",
        1743,
        "WP_IPM::ReportListenerChannelStopped",
        a4,
        "Report ListenerChannel stopped due to failure; ProtocolId:%S, ListenerChannelId:%d\n",
        Src,
        a3);
    v12 = BUFFER::QueryPtr((BUFFER *)v13);
    WP_IPM::WriteMessage((__int64)this, 15, v9 + 8, (__int64)v12);
  }
  else
  {
    WP_IPM::SendUnhealthyMessage(this);
  }
  BUFFER::~BUFFER((BUFFER *)v13);
}

```

## disassembly

```asm
0x180007f8c  push    rbx
0x180007f8e  push    rbp
0x180007f8f  push    rsi
0x180007f90  push    rdi
0x180007f91  push    r12
0x180007f93  push    r14
0x180007f95  push    r15
0x180007f97  sub     rsp, 80h
0x180007f9e  mov     rax, cs:__security_cookie
0x180007fa5  xor     rax, rsp
0x180007fa8  mov     [rsp+0B8h+var_48], rax
0x180007fad  mov     rsi, rcx
0x180007fb0  mov     [rcx+20h], r9d
0x180007fb4  mov     rcx, [rcx+18h]; hEvent
0x180007fb8  mov     edi, r9d
0x180007fbb  mov     r15d, r8d
0x180007fbe  mov     rbp, rdx
0x180007fc1  call    cs:__imp_SetEvent
0x180007fc7  lea     rcx, [rsp+0B8h+var_78]
0x180007fcc  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x180007fd2  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007fd6  xor     r12d, r12d
0x180007fd9  inc     rax
0x180007fdc  cmp     [rbp+rax*2+0], r12w
0x180007fe2  jnz     short loc_180007FD9
0x180007fe4  lea     ebx, ds:2[rax*2]
0x180007feb  lea     edx, [rbx+8]
0x180007fee  lea     rcx, [rsp+0B8h+var_78]
0x180007ff3  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180007ff9  test    al, al
0x180007ffb  jnz     short loc_18000800A
0x180007ffd  mov     rcx, rsi; this
0x180008000  call    ?SendUnhealthyMessage@WP_IPM@@AEAAXXZ; WP_IPM::SendUnhealthyMessage(void)
0x180008005  jmp     loc_1800080FB
0x18000800a  lea     rcx, [rsp+0B8h+var_78]
0x18000800f  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180008015  lea     rcx, [rsp+0B8h+var_78]
0x18000801a  mov     [rax], edi
0x18000801c  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180008022  lea     rcx, [rsp+0B8h+var_78]
0x180008027  mov     [rax+4], r15d
0x18000802b  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180008031  mov     r8, rbx; Size
0x180008034  mov     rdx, rbp; Src
0x180008037  lea     rcx, [rax+8]; void *
0x18000803b  call    memcpy_0
0x180008040  mov     edx, cs:g_dwDebugFlags
0x180008046  test    dl, 3
0x180008049  setnz   cl
0x18000804c  bt      edx, 13h
0x180008050  setb    al
0x180008053  test    al, cl
0x180008055  jz      short loc_180008098
0x180008057  mov     rcx, cs:g_pDebug
0x18000805e  lea     rax, aReportListener_1; "Report ListenerChannel Stopped for: %S,"...
0x180008065  mov     [rsp+0B8h+var_80], edi
0x180008069  lea     r9, aWpIpmReportlis_0; "WP_IPM::ReportListenerChannelStopped"
0x180008070  mov     dword ptr [rsp+0B8h+var_88], r15d
0x180008075  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000807c  mov     [rsp+0B8h+var_90], rbp
0x180008081  mov     r8d, 6C6h
0x180008087  mov     [rsp+0B8h+var_98], rax
0x18000808c  call    cs:__imp_PuDbgPrint
0x180008092  mov     edx, cs:g_dwDebugFlags
0x180008098  test    edi, edi
0x18000809a  jns     short loc_1800080DC
0x18000809c  test    dl, 0Fh
0x18000809f  jz      short loc_1800080DC
0x1800080a1  mov     rcx, cs:g_pDebug
0x1800080a8  lea     rax, aReportListener; "Report ListenerChannel stopped due to f"...
0x1800080af  mov     [rsp+0B8h+var_80], r15d
0x1800080b4  lea     r9, aWpIpmReportlis_0; "WP_IPM::ReportListenerChannelStopped"
0x1800080bb  mov     [rsp+0B8h+var_88], rbp
0x1800080c0  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800080c7  mov     [rsp+0B8h+var_90], rax
0x1800080cc  mov     r8d, 6CFh
0x1800080d2  mov     dword ptr [rsp+0B8h+var_98], edi
0x1800080d6  call    cs:__imp_PuDbgPrintError
0x1800080dc  lea     rcx, [rsp+0B8h+var_78]
0x1800080e1  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800080e7  lea     r8d, [rbx+8]
0x1800080eb  mov     edx, 0Fh
0x1800080f0  mov     r9, rax
0x1800080f3  mov     rcx, rsi
0x1800080f6  call    ?WriteMessage@WP_IPM@@AEAAJW4IPM_OPCODE@@KPEAX@Z; WP_IPM::WriteMessage(IPM_OPCODE,ulong,void *)
0x1800080fb  lea     rcx, [rsp+0B8h+var_78]
0x180008100  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180008106  mov     rcx, [rsp+0B8h+var_48]
0x18000810b  xor     rcx, rsp; StackCookie
0x18000810e  call    __security_check_cookie
0x180008113  add     rsp, 80h
0x18000811a  pop     r15
0x18000811c  pop     r14
0x18000811e  pop     r12
0x180008120  pop     rdi
0x180008121  pop     rsi
0x180008122  pop     rbp
0x180008123  pop     rbx
0x180008124  retn
```
