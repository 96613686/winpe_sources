# WP_IPM::ReportListenerChannelStarted(ushort const *,ulong)

- ea: `0x180007e48`
- end: `0x180007f86`
- name: `?ReportListenerChannelStarted@WP_IPM@@QEAAXPEBGK@Z`
- size: `318`
- prototype: `void __fastcall(WP_IPM *__hidden this, const unsigned __int16 *Src, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000a410`

## callees

- `0x180001830`
- `0x180007e48`
- `0x180008270`
- `0x18000c386`
- `0x18000c3d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180007f32`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180007f32`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180007e9e`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180007e9e`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180007e78`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180007e78`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180007eba`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180007ec8`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180007f3d`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180007eba`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180007ec8`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180007f3d`
- `iisutil!PuDbgPrint` at `0x180007f24`
- `iisutil!PuDbgPrint` at `0x180007f24`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180007f5c`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180007f5c`

## string_xrefs

- `0x180007f12`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`

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
        "Report ListenerChannel Started for: %S, ListenerChannelId:%d\n");
    v9 = (void *)*((_QWORD *)this + 3);
    *((_DWORD *)this + 8) = 0;
    SetEvent(v9);
    v10 = BUFFER::QueryPtr((BUFFER *)v11);
    WP_IPM::WriteMessage((__int64)this, 14, v7 + 4, (__int64)v10);
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
0x180007e48  mov     [rsp+arg_18], rbx
0x180007e4d  push    rbp
0x180007e4e  push    rsi
0x180007e4f  push    rdi
0x180007e50  push    r14
0x180007e52  push    r15
0x180007e54  sub     rsp, 80h
0x180007e5b  mov     rax, cs:__security_cookie
0x180007e62  xor     rax, rsp
0x180007e65  mov     [rsp+0A8h+var_38], rax
0x180007e6a  mov     rdi, rcx
0x180007e6d  mov     r14d, r8d
0x180007e70  lea     rcx, [rsp+0A8h+var_68]
0x180007e75  mov     rsi, rdx
0x180007e78  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x180007e7e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007e82  xor     r15d, r15d
0x180007e85  inc     rax
0x180007e88  cmp     [rsi+rax*2], r15w
0x180007e8d  jnz     short loc_180007E85
0x180007e8f  lea     ebx, ds:2[rax*2]
0x180007e96  lea     edx, [rbx+4]
0x180007e99  lea     rcx, [rsp+0A8h+var_68]
0x180007e9e  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180007ea4  test    al, al
0x180007ea6  jnz     short loc_180007EB5
0x180007ea8  mov     rcx, rdi; this
0x180007eab  call    ?SendUnhealthyMessage@WP_IPM@@AEAAXXZ; WP_IPM::SendUnhealthyMessage(void)
0x180007eb0  jmp     loc_180007F57
0x180007eb5  lea     rcx, [rsp+0A8h+var_68]
0x180007eba  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180007ec0  lea     rcx, [rsp+0A8h+var_68]
0x180007ec5  mov     [rax], r14d
0x180007ec8  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180007ece  mov     r8, rbx; Size
0x180007ed1  mov     rdx, rsi; Src
0x180007ed4  lea     rcx, [rax+4]; void *
0x180007ed8  call    memcpy_0
0x180007edd  mov     eax, cs:g_dwDebugFlags
0x180007ee3  test    al, 3
0x180007ee5  setnz   cl
0x180007ee8  bt      eax, 13h
0x180007eec  setb    al
0x180007eef  test    al, cl
0x180007ef1  jz      short loc_180007F2A
0x180007ef3  mov     rcx, cs:g_pDebug
0x180007efa  lea     rax, aReportListener_0; "Report ListenerChannel Started for: %S,"...
0x180007f01  mov     [rsp+0A8h+var_78], r14d
0x180007f06  lea     r9, aWpIpmReportlis; "WP_IPM::ReportListenerChannelStarted"
0x180007f0d  mov     [rsp+0A8h+var_80], rsi
0x180007f12  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180007f19  mov     r8d, 685h
0x180007f1f  mov     [rsp+0A8h+var_88], rax
0x180007f24  call    cs:__imp_PuDbgPrint
0x180007f2a  mov     rcx, [rdi+18h]; hEvent
0x180007f2e  mov     [rdi+20h], r15d
0x180007f32  call    cs:__imp_SetEvent
0x180007f38  lea     rcx, [rsp+0A8h+var_68]
0x180007f3d  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180007f43  lea     r8d, [rbx+4]
0x180007f47  mov     edx, 0Eh
0x180007f4c  mov     r9, rax
0x180007f4f  mov     rcx, rdi
0x180007f52  call    ?WriteMessage@WP_IPM@@AEAAJW4IPM_OPCODE@@KPEAX@Z; WP_IPM::WriteMessage(IPM_OPCODE,ulong,void *)
0x180007f57  lea     rcx, [rsp+0A8h+var_68]
0x180007f5c  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180007f62  mov     rcx, [rsp+0A8h+var_38]
0x180007f67  xor     rcx, rsp; StackCookie
0x180007f6a  call    __security_check_cookie
0x180007f6f  mov     rbx, [rsp+0A8h+arg_18]
0x180007f77  add     rsp, 80h
0x180007f7e  pop     r15
0x180007f80  pop     r14
0x180007f82  pop     rdi
0x180007f83  pop     rsi
0x180007f84  pop     rbp
0x180007f85  retn
```
