# WP_IPM::ReportListenerChannelStopped(ushort const *,ulong,long)

- ea: `0x180008818`
- end: `0x1800089ee`
- name: `?ReportListenerChannelStopped@WP_IPM@@QEAAXPEBGKJ@Z`
- size: `470`
- prototype: `void __fastcall(WP_IPM *this, const unsigned __int16 *Src, int, int)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000b1a0`
- `0x18000b8e8`
- `0x18000bdc4`

## callees

- `0x180001890`
- `0x180008818`
- `0x180008b50`
- `0x18000d2a6`
- `0x18000d2f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000884d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000884d`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000888b`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000888b`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18000885e`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18000885e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800088ad`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800088c0`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800088d5`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000899d`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800088ad`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800088c0`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800088d5`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000899d`
- `iisutil!PuDbgPrint` at `0x18000893c`
- `iisutil!PuDbgPrint` at `0x18000893c`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800089c2`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800089c2`
- `iisutil!PuDbgPrintError` at `0x18000898c`
- `iisutil!PuDbgPrintError` at `0x18000898c`

## string_xrefs

- `0x180008925`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`
- `0x180008976`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`
- `0x18000895e`: `Report ListenerChannel stopped due to failure; ProtocolId:%S, ListenerChannelId:%d\n`

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
        "Report ListenerChannel Stopped for: %S, ListenerChannelId:%d hr =0x%x\n",
        Src,
        a3,
        a4);
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
    WP_IPM::WriteMessage(this, 15, (unsigned int)(v9 + 8), v12);
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
0x180008818  push    rbx
0x18000881a  push    rbp
0x18000881b  push    rsi
0x18000881c  push    rdi
0x18000881d  push    r12
0x18000881f  push    r14
0x180008821  push    r15
0x180008823  sub     rsp, 80h
0x18000882a  mov     rax, cs:__security_cookie
0x180008831  xor     rax, rsp
0x180008834  mov     [rsp+0B8h+var_48], rax
0x180008839  mov     rsi, rcx
0x18000883c  mov     [rcx+20h], r9d
0x180008840  mov     rcx, [rcx+18h]; hEvent
0x180008844  mov     edi, r9d
0x180008847  mov     r15d, r8d
0x18000884a  mov     rbp, rdx
0x18000884d  call    cs:__imp_SetEvent
0x180008854  nop     dword ptr [rax+rax+00h]
0x180008859  lea     rcx, [rsp+0B8h+var_78]
0x18000885e  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x180008865  nop     dword ptr [rax+rax+00h]
0x18000886a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000886e  xor     r12d, r12d
0x180008871  inc     rax
0x180008874  cmp     [rbp+rax*2+0], r12w
0x18000887a  jnz     short loc_180008871
0x18000887c  lea     ebx, ds:2[rax*2]
0x180008883  lea     edx, [rbx+8]
0x180008886  lea     rcx, [rsp+0B8h+var_78]
0x18000888b  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180008892  nop     dword ptr [rax+rax+00h]
0x180008897  test    al, al
0x180008899  jnz     short loc_1800088A8
0x18000889b  mov     rcx, rsi; this
0x18000889e  call    ?SendUnhealthyMessage@WP_IPM@@AEAAXXZ; WP_IPM::SendUnhealthyMessage(void)
0x1800088a3  jmp     loc_1800089BD
0x1800088a8  lea     rcx, [rsp+0B8h+var_78]
0x1800088ad  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800088b4  nop     dword ptr [rax+rax+00h]
0x1800088b9  lea     rcx, [rsp+0B8h+var_78]
0x1800088be  mov     [rax], edi
0x1800088c0  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800088c7  nop     dword ptr [rax+rax+00h]
0x1800088cc  lea     rcx, [rsp+0B8h+var_78]
0x1800088d1  mov     [rax+4], r15d
0x1800088d5  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800088dc  nop     dword ptr [rax+rax+00h]
0x1800088e1  mov     r8, rbx; Size
0x1800088e4  mov     rdx, rbp; Src
0x1800088e7  lea     rcx, [rax+8]; void *
0x1800088eb  call    memcpy_0
0x1800088f0  mov     edx, cs:g_dwDebugFlags
0x1800088f6  test    dl, 3
0x1800088f9  setnz   cl
0x1800088fc  bt      edx, 13h
0x180008900  setb    al
0x180008903  test    al, cl
0x180008905  jz      short loc_18000894E
0x180008907  mov     rcx, cs:g_pDebug
0x18000890e  lea     rax, aReportListener_1; "Report ListenerChannel Stopped for: %S,"...
0x180008915  mov     [rsp+0B8h+var_80], edi
0x180008919  lea     r9, aWpIpmReportlis_0; "WP_IPM::ReportListenerChannelStopped"
0x180008920  mov     dword ptr [rsp+0B8h+var_88], r15d
0x180008925  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000892c  mov     [rsp+0B8h+var_90], rbp
0x180008931  mov     r8d, 6C6h
0x180008937  mov     [rsp+0B8h+var_98], rax
0x18000893c  call    cs:__imp_PuDbgPrint
0x180008943  nop     dword ptr [rax+rax+00h]
0x180008948  mov     edx, cs:g_dwDebugFlags
0x18000894e  test    edi, edi
0x180008950  jns     short loc_180008998
0x180008952  test    dl, 0Fh
0x180008955  jz      short loc_180008998
0x180008957  mov     rcx, cs:g_pDebug
0x18000895e  lea     rax, aReportListener; "Report ListenerChannel stopped due to f"...
0x180008965  mov     [rsp+0B8h+var_80], r15d
0x18000896a  lea     r9, aWpIpmReportlis_0; "WP_IPM::ReportListenerChannelStopped"
0x180008971  mov     [rsp+0B8h+var_88], rbp
0x180008976  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000897d  mov     [rsp+0B8h+var_90], rax
0x180008982  mov     r8d, 6CFh
0x180008988  mov     dword ptr [rsp+0B8h+var_98], edi
0x18000898c  call    cs:__imp_PuDbgPrintError
0x180008993  nop     dword ptr [rax+rax+00h]
0x180008998  lea     rcx, [rsp+0B8h+var_78]
0x18000899d  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800089a4  nop     dword ptr [rax+rax+00h]
0x1800089a9  lea     r8d, [rbx+8]
0x1800089ad  mov     edx, 0Fh
0x1800089b2  mov     r9, rax
0x1800089b5  mov     rcx, rsi
0x1800089b8  call    ?WriteMessage@WP_IPM@@AEAAJW4IPM_OPCODE@@KPEAX@Z; WP_IPM::WriteMessage(IPM_OPCODE,ulong,void *)
0x1800089bd  lea     rcx, [rsp+0B8h+var_78]
0x1800089c2  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800089c9  nop     dword ptr [rax+rax+00h]
0x1800089ce  mov     rcx, [rsp+0B8h+var_48]
0x1800089d3  xor     rcx, rsp; StackCookie
0x1800089d6  call    __security_check_cookie
0x1800089db  add     rsp, 80h
0x1800089e2  pop     r15
0x1800089e4  pop     r14
0x1800089e6  pop     r12
0x1800089e8  pop     rdi
0x1800089e9  pop     rsi
0x1800089ea  pop     rbp
0x1800089eb  pop     rbx
0x1800089ec  retn
```
