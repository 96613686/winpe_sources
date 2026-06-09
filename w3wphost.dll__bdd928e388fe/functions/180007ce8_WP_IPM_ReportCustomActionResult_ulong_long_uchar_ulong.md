# WP_IPM::ReportCustomActionResult(ulong,long,uchar *,ulong)

- ea: `0x180007ce8`
- end: `0x180007e41`
- name: `?ReportCustomActionResult@WP_IPM@@QEAAXKJPEAEK@Z`
- size: `345`
- prototype: `void __fastcall(WP_IPM *this, int, int, unsigned __int8 *, unsigned int Size)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180006680`

## callees

- `0x180001830`
- `0x180007ce8`
- `0x180008270`
- `0x18000c386`
- `0x18000c3d0`

## import_xrefs

- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180007d70`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180007d70`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180007d18`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180007d18`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180007d8c`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180007db4`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180007d8c`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180007db4`
- `iisutil!PuDbgPrint` at `0x180007d5b`
- `iisutil!PuDbgPrint` at `0x180007e0f`
- `iisutil!PuDbgPrint` at `0x180007d5b`
- `iisutil!PuDbgPrint` at `0x180007e0f`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180007e1a`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180007e1a`

## string_xrefs

- `0x180007d54`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`
- `0x180007e08`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`

## pseudocode

```c
void __fastcall WP_IPM::ReportCustomActionResult(WP_IPM *this, int a2, int a3, unsigned __int8 *a4, unsigned int Size)
{
  _DWORD *Ptr; // rax
  void *v10; // rax
  _BYTE v11[48]; // [rsp+30h] [rbp-68h] BYREF

  BUFFER::BUFFER((BUFFER *)v11);
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x80000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wpipm.cxx",
      1508,
      "WP_IPM::ReportCustomActionResult",
      "Sending WP Function response to WAS\n\n");
  if ( BUFFER::Resize((BUFFER *)v11, Size + 12) )
  {
    Ptr = BUFFER::QueryPtr((BUFFER *)v11);
    *Ptr = a2;
    Ptr[1] = a3;
    Ptr[2] = Size;
    if ( Size )
      memcpy_0(Ptr + 3, a4, Size);
    v10 = BUFFER::QueryPtr((BUFFER *)v11);
    if ( (int)WP_IPM::WriteMessage((__int64)this, 18, Size + 12, (__int64)v10) < 0
      && (g_dwDebugFlags & 3) != 0
      && (g_dwDebugFlags & 0x80000) != 0 )
    {
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wpipm.cxx",
        1563,
        "WP_IPM::ReportCustomActionResult",
        "Failed sending request data back to W3SVC \n\n");
    }
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
0x180007ce8  mov     [rsp+arg_8], rbx
0x180007ced  push    rbp
0x180007cee  push    rsi
0x180007cef  push    rdi
0x180007cf0  push    r14
0x180007cf2  push    r15
0x180007cf4  sub     rsp, 70h
0x180007cf8  mov     rax, cs:__security_cookie
0x180007cff  xor     rax, rsp
0x180007d02  mov     [rsp+98h+var_38], rax
0x180007d07  mov     rdi, rcx
0x180007d0a  mov     rbp, r9
0x180007d0d  lea     rcx, [rsp+98h+var_68]
0x180007d12  mov     r14d, r8d
0x180007d15  mov     r15d, edx
0x180007d18  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x180007d1e  mov     eax, cs:g_dwDebugFlags
0x180007d24  test    al, 3
0x180007d26  setnz   cl
0x180007d29  bt      eax, 13h
0x180007d2d  setb    al
0x180007d30  test    al, cl
0x180007d32  jz      short loc_180007D61
0x180007d34  mov     rcx, cs:g_pDebug
0x180007d3b  lea     rax, aSendingWpFunct; "Sending WP Function response to WAS\n\n"
0x180007d42  lea     r9, aWpIpmReportcus; "WP_IPM::ReportCustomActionResult"
0x180007d49  mov     [rsp+98h+var_78], rax
0x180007d4e  mov     r8d, 5E4h
0x180007d54  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180007d5b  call    cs:__imp_PuDbgPrint
0x180007d61  mov     ebx, dword ptr [rsp+98h+Size]
0x180007d68  lea     rcx, [rsp+98h+var_68]
0x180007d6d  lea     edx, [rbx+0Ch]
0x180007d70  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180007d76  test    al, al
0x180007d78  jnz     short loc_180007D87
0x180007d7a  mov     rcx, rdi; this
0x180007d7d  call    ?SendUnhealthyMessage@WP_IPM@@AEAAXXZ; WP_IPM::SendUnhealthyMessage(void)
0x180007d82  jmp     loc_180007E15
0x180007d87  lea     rcx, [rsp+98h+var_68]
0x180007d8c  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180007d92  mov     [rax], r15d
0x180007d95  mov     [rax+4], r14d
0x180007d99  mov     [rax+8], ebx
0x180007d9c  test    ebx, ebx
0x180007d9e  jz      short loc_180007DAF
0x180007da0  mov     r8, rbx; Size
0x180007da3  lea     rcx, [rax+0Ch]; void *
0x180007da7  mov     rdx, rbp; Src
0x180007daa  call    memcpy_0
0x180007daf  lea     rcx, [rsp+98h+var_68]
0x180007db4  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180007dba  lea     r8d, [rbx+0Ch]
0x180007dbe  mov     edx, 12h
0x180007dc3  mov     r9, rax
0x180007dc6  mov     rcx, rdi
0x180007dc9  call    ?WriteMessage@WP_IPM@@AEAAJW4IPM_OPCODE@@KPEAX@Z; WP_IPM::WriteMessage(IPM_OPCODE,ulong,void *)
0x180007dce  test    eax, eax
0x180007dd0  jns     short loc_180007E15
0x180007dd2  mov     eax, cs:g_dwDebugFlags
0x180007dd8  test    al, 3
0x180007dda  setnz   cl
0x180007ddd  bt      eax, 13h
0x180007de1  setb    al
0x180007de4  test    al, cl
0x180007de6  jz      short loc_180007E15
0x180007de8  mov     rcx, cs:g_pDebug
0x180007def  lea     rax, aFailedSendingR; "Failed sending request data back to W3S"...
0x180007df6  lea     r9, aWpIpmReportcus; "WP_IPM::ReportCustomActionResult"
0x180007dfd  mov     [rsp+98h+var_78], rax
0x180007e02  mov     r8d, 61Bh
0x180007e08  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180007e0f  call    cs:__imp_PuDbgPrint
0x180007e15  lea     rcx, [rsp+98h+var_68]
0x180007e1a  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180007e20  mov     rcx, [rsp+98h+var_38]
0x180007e25  xor     rcx, rsp; StackCookie
0x180007e28  call    __security_check_cookie
0x180007e2d  mov     rbx, [rsp+98h+arg_8]
0x180007e35  add     rsp, 70h
0x180007e39  pop     r15
0x180007e3b  pop     r14
0x180007e3d  pop     rdi
0x180007e3e  pop     rsi
0x180007e3f  pop     rbp
0x180007e40  retn
```
