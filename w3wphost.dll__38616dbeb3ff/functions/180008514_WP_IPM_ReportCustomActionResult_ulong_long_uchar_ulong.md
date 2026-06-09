# WP_IPM::ReportCustomActionResult(ulong,long,uchar *,ulong)

- ea: `0x180008514`
- end: `0x180008698`
- name: `?ReportCustomActionResult@WP_IPM@@QEAAXKJPEAEK@Z`
- size: `388`
- prototype: `void __fastcall(WP_IPM *this, int, int, unsigned __int8 *, unsigned int Size)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180006ce0`

## callees

- `0x180001890`
- `0x180008514`
- `0x180008b50`
- `0x18000d2a6`
- `0x18000d2f0`

## import_xrefs

- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800085a8`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800085a8`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180008544`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180008544`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800085ca`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800085f8`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800085ca`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800085f8`
- `iisutil!PuDbgPrint` at `0x18000858d`
- `iisutil!PuDbgPrint` at `0x180008659`
- `iisutil!PuDbgPrint` at `0x18000858d`
- `iisutil!PuDbgPrint` at `0x180008659`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000866a`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000866a`

## string_xrefs

- `0x180008586`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`
- `0x180008652`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`

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
    if ( (int)WP_IPM::WriteMessage(this, 18, Size + 12, v10) < 0
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
0x180008514  mov     [rsp+arg_8], rbx
0x180008519  push    rbp
0x18000851a  push    rsi
0x18000851b  push    rdi
0x18000851c  push    r14
0x18000851e  push    r15
0x180008520  sub     rsp, 70h
0x180008524  mov     rax, cs:__security_cookie
0x18000852b  xor     rax, rsp
0x18000852e  mov     [rsp+98h+var_38], rax
0x180008533  mov     rdi, rcx
0x180008536  mov     rbp, r9
0x180008539  lea     rcx, [rsp+98h+var_68]
0x18000853e  mov     r14d, r8d
0x180008541  mov     r15d, edx
0x180008544  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x18000854b  nop     dword ptr [rax+rax+00h]
0x180008550  mov     eax, cs:g_dwDebugFlags
0x180008556  test    al, 3
0x180008558  setnz   cl
0x18000855b  bt      eax, 13h
0x18000855f  setb    al
0x180008562  test    al, cl
0x180008564  jz      short loc_180008599
0x180008566  mov     rcx, cs:g_pDebug
0x18000856d  lea     rax, aSendingWpFunct; "Sending WP Function response to WAS\n\n"
0x180008574  lea     r9, aWpIpmReportcus; "WP_IPM::ReportCustomActionResult"
0x18000857b  mov     [rsp+98h+var_78], rax
0x180008580  mov     r8d, 5E4h
0x180008586  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000858d  call    cs:__imp_PuDbgPrint
0x180008594  nop     dword ptr [rax+rax+00h]
0x180008599  mov     ebx, dword ptr [rsp+98h+Size]
0x1800085a0  lea     rcx, [rsp+98h+var_68]
0x1800085a5  lea     edx, [rbx+0Ch]
0x1800085a8  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800085af  nop     dword ptr [rax+rax+00h]
0x1800085b4  test    al, al
0x1800085b6  jnz     short loc_1800085C5
0x1800085b8  mov     rcx, rdi; this
0x1800085bb  call    ?SendUnhealthyMessage@WP_IPM@@AEAAXXZ; WP_IPM::SendUnhealthyMessage(void)
0x1800085c0  jmp     loc_180008665
0x1800085c5  lea     rcx, [rsp+98h+var_68]
0x1800085ca  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800085d1  nop     dword ptr [rax+rax+00h]
0x1800085d6  mov     [rax], r15d
0x1800085d9  mov     [rax+4], r14d
0x1800085dd  mov     [rax+8], ebx
0x1800085e0  test    ebx, ebx
0x1800085e2  jz      short loc_1800085F3
0x1800085e4  mov     r8, rbx; Size
0x1800085e7  lea     rcx, [rax+0Ch]; void *
0x1800085eb  mov     rdx, rbp; Src
0x1800085ee  call    memcpy_0
0x1800085f3  lea     rcx, [rsp+98h+var_68]
0x1800085f8  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800085ff  nop     dword ptr [rax+rax+00h]
0x180008604  lea     r8d, [rbx+0Ch]
0x180008608  mov     edx, 12h
0x18000860d  mov     r9, rax
0x180008610  mov     rcx, rdi
0x180008613  call    ?WriteMessage@WP_IPM@@AEAAJW4IPM_OPCODE@@KPEAX@Z; WP_IPM::WriteMessage(IPM_OPCODE,ulong,void *)
0x180008618  test    eax, eax
0x18000861a  jns     short loc_180008665
0x18000861c  mov     eax, cs:g_dwDebugFlags
0x180008622  test    al, 3
0x180008624  setnz   cl
0x180008627  bt      eax, 13h
0x18000862b  setb    al
0x18000862e  test    al, cl
0x180008630  jz      short loc_180008665
0x180008632  mov     rcx, cs:g_pDebug
0x180008639  lea     rax, aFailedSendingR; "Failed sending request data back to W3S"...
0x180008640  lea     r9, aWpIpmReportcus; "WP_IPM::ReportCustomActionResult"
0x180008647  mov     [rsp+98h+var_78], rax
0x18000864c  mov     r8d, 61Bh
0x180008652  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008659  call    cs:__imp_PuDbgPrint
0x180008660  nop     dword ptr [rax+rax+00h]
0x180008665  lea     rcx, [rsp+98h+var_68]
0x18000866a  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180008671  nop     dword ptr [rax+rax+00h]
0x180008676  mov     rcx, [rsp+98h+var_38]
0x18000867b  xor     rcx, rsp; StackCookie
0x18000867e  call    __security_check_cookie
0x180008683  mov     rbx, [rsp+98h+arg_8]
0x18000868b  add     rsp, 70h
0x18000868f  pop     r15
0x180008691  pop     r14
0x180008693  pop     rdi
0x180008694  pop     rsi
0x180008695  pop     rbp
0x180008696  retn
```
