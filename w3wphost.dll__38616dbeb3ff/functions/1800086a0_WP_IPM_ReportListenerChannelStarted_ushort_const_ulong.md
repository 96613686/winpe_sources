# WP_IPM::ReportListenerChannelStarted(ushort const *,ulong)

- ea: `0x1800086a0`
- end: `0x18000880f`
- name: `?ReportListenerChannelStarted@WP_IPM@@QEAAXPEBGK@Z`
- size: `367`
- prototype: `void __fastcall(WP_IPM *this, const unsigned __int16 *Src, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000b0f0`

## callees

- `0x180001890`
- `0x1800086a0`
- `0x180008b50`
- `0x18000d2a6`
- `0x18000d2f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800087a8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800087a8`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800086fc`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800086fc`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x1800086d0`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x1800086d0`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000871e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180008732`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800087b9`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000871e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180008732`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800087b9`
- `iisutil!PuDbgPrint` at `0x180008794`
- `iisutil!PuDbgPrint` at `0x180008794`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800087de`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800087de`

## string_xrefs

- `0x180008782`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`

## pseudocode

```c
void __fastcall WP_IPM::ReportListenerChannelStarted(WP_IPM *this, const unsigned __int16 *Src, int a3)
{
  __int64 v6; // rax
  size_t v7; // rbx
  char *Ptr; // rax
  void *v9; // rcx
  void *v10; // rax
  _BYTE v11[48]; // [rsp+40h] [rbp-68h] BYREF

  BUFFER::BUFFER((BUFFER *)v11);
  v6 = -1;
  do
    ++v6;
  while ( Src[v6] );
  v7 = (unsigned int)(2 * v6 + 2);
  if ( BUFFER::Resize((BUFFER *)v11, 2 * v6 + 6) )
  {
    *(_DWORD *)BUFFER::QueryPtr((BUFFER *)v11) = a3;
    Ptr = (char *)BUFFER::QueryPtr((BUFFER *)v11);
    memcpy_0(Ptr + 4, Src, v7);
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x80000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wpipm.cxx",
        1669,
        "WP_IPM::ReportListenerChannelStarted",
        "Report ListenerChannel Started for: %S, ListenerChannelId:%d\n",
        Src,
        a3);
    v9 = (void *)*((_QWORD *)this + 3);
    *((_DWORD *)this + 8) = 0;
    SetEvent(v9);
    v10 = BUFFER::QueryPtr((BUFFER *)v11);
    WP_IPM::WriteMessage(this, 14, (unsigned int)(v7 + 4), v10);
  }
  else
  {
    WP_IPM::SendUnhealthyMessage(this);
  }
  BUFFER::~BUFFER((BUFFER *)v11);
}

```

## disassembly

```asm
0x1800086a0  mov     [rsp+arg_18], rbx
0x1800086a5  push    rbp
0x1800086a6  push    rsi
0x1800086a7  push    rdi
0x1800086a8  push    r14
0x1800086aa  push    r15
0x1800086ac  sub     rsp, 80h
0x1800086b3  mov     rax, cs:__security_cookie
0x1800086ba  xor     rax, rsp
0x1800086bd  mov     [rsp+0A8h+var_38], rax
0x1800086c2  mov     rdi, rcx
0x1800086c5  mov     r14d, r8d
0x1800086c8  lea     rcx, [rsp+0A8h+var_68]
0x1800086cd  mov     rsi, rdx
0x1800086d0  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x1800086d7  nop     dword ptr [rax+rax+00h]
0x1800086dc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800086e0  xor     r15d, r15d
0x1800086e3  inc     rax
0x1800086e6  cmp     [rsi+rax*2], r15w
0x1800086eb  jnz     short loc_1800086E3
0x1800086ed  lea     ebx, ds:2[rax*2]
0x1800086f4  lea     edx, [rbx+4]
0x1800086f7  lea     rcx, [rsp+0A8h+var_68]
0x1800086fc  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180008703  nop     dword ptr [rax+rax+00h]
0x180008708  test    al, al
0x18000870a  jnz     short loc_180008719
0x18000870c  mov     rcx, rdi; this
0x18000870f  call    ?SendUnhealthyMessage@WP_IPM@@AEAAXXZ; WP_IPM::SendUnhealthyMessage(void)
0x180008714  jmp     loc_1800087D9
0x180008719  lea     rcx, [rsp+0A8h+var_68]
0x18000871e  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180008725  nop     dword ptr [rax+rax+00h]
0x18000872a  lea     rcx, [rsp+0A8h+var_68]
0x18000872f  mov     [rax], r14d
0x180008732  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180008739  nop     dword ptr [rax+rax+00h]
0x18000873e  mov     r8, rbx; Size
0x180008741  mov     rdx, rsi; Src
0x180008744  lea     rcx, [rax+4]; void *
0x180008748  call    memcpy_0
0x18000874d  mov     eax, cs:g_dwDebugFlags
0x180008753  test    al, 3
0x180008755  setnz   cl
0x180008758  bt      eax, 13h
0x18000875c  setb    al
0x18000875f  test    al, cl
0x180008761  jz      short loc_1800087A0
0x180008763  mov     rcx, cs:g_pDebug
0x18000876a  lea     rax, aReportListener_0; "Report ListenerChannel Started for: %S,"...
0x180008771  mov     [rsp+0A8h+var_78], r14d
0x180008776  lea     r9, aWpIpmReportlis; "WP_IPM::ReportListenerChannelStarted"
0x18000877d  mov     [rsp+0A8h+var_80], rsi
0x180008782  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008789  mov     r8d, 685h
0x18000878f  mov     [rsp+0A8h+var_88], rax
0x180008794  call    cs:__imp_PuDbgPrint
0x18000879b  nop     dword ptr [rax+rax+00h]
0x1800087a0  mov     rcx, [rdi+18h]; hEvent
0x1800087a4  mov     [rdi+20h], r15d
0x1800087a8  call    cs:__imp_SetEvent
0x1800087af  nop     dword ptr [rax+rax+00h]
0x1800087b4  lea     rcx, [rsp+0A8h+var_68]
0x1800087b9  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800087c0  nop     dword ptr [rax+rax+00h]
0x1800087c5  lea     r8d, [rbx+4]
0x1800087c9  mov     edx, 0Eh
0x1800087ce  mov     r9, rax
0x1800087d1  mov     rcx, rdi
0x1800087d4  call    ?WriteMessage@WP_IPM@@AEAAJW4IPM_OPCODE@@KPEAX@Z; WP_IPM::WriteMessage(IPM_OPCODE,ulong,void *)
0x1800087d9  lea     rcx, [rsp+0A8h+var_68]
0x1800087de  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800087e5  nop     dword ptr [rax+rax+00h]
0x1800087ea  mov     rcx, [rsp+0A8h+var_38]
0x1800087ef  xor     rcx, rsp; StackCookie
0x1800087f2  call    __security_check_cookie
0x1800087f7  mov     rbx, [rsp+0A8h+arg_18]
0x1800087ff  add     rsp, 80h
0x180008806  pop     r15
0x180008808  pop     r14
0x18000880a  pop     rdi
0x18000880b  pop     rsi
0x18000880c  pop     rbp
0x18000880d  retn
```
