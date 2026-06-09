# WP_CONTEXT::Start(void)

- ea: `0x18000ec08`
- end: `0x18000eca8`
- name: `?Start@WP_CONTEXT@@QEAAJXZ`
- size: `160`
- prototype: `__int64 __fastcall(WP_CONTEXT *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180015980`

## callees

- `0x18000ec08`
- `0x18000edc0`
- `0x180013450`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18000ec5b`
- `iisutil!PuDbgPrint` at `0x18000ec9d`
- `iisutil!PuDbgPrint` at `0x18000ec5b`
- `iisutil!PuDbgPrint` at `0x18000ec9d`

## string_xrefs

- `0x18000ec42`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\wpcontext.cxx`
- `0x18000ec84`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\wpcontext.cxx`

## pseudocode

```c
__int64 __fastcall WP_CONTEXT::Start(WP_CONTEXT *this)
{
  int v1; // eax
  signed int started; // eax
  unsigned int v3; // ebx

  v1 = UL_NATIVE_REQUEST::AddPendingRequests(0x14u);
  if ( v1 < 0 && (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\wpcontext.cxx",
      385,
      "WP_CONTEXT::Start",
      "Failed to add pending UL_NATIVE_REQUESTs.  hr = %x\n",
      v1);
  started = UL_NATIVE_REQUEST::StartPendingRequestsMonitor();
  v3 = started;
  if ( started < 0 && (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\wpcontext.cxx",
      401,
      "WP_CONTEXT::Start",
      "Failed to start Pending requests monitor.  hr = %x\n",
      started);
  return v3;
}

```

## disassembly

```asm
0x18000ec08  push    rbx
0x18000ec0a  sub     rsp, 30h
0x18000ec0e  mov     ecx, 14h; unsigned int
0x18000ec13  call    ?AddPendingRequests@UL_NATIVE_REQUEST@@SAJK@Z; UL_NATIVE_REQUEST::AddPendingRequests(ulong)
0x18000ec18  test    eax, eax
0x18000ec1a  js      short loc_18000EC69
0x18000ec1c  call    ?StartPendingRequestsMonitor@UL_NATIVE_REQUEST@@SAJXZ; UL_NATIVE_REQUEST::StartPendingRequestsMonitor(void)
0x18000ec21  mov     ebx, eax
0x18000ec23  test    eax, eax
0x18000ec25  jns     short loc_18000EC61
0x18000ec27  test    byte ptr cs:g_dwDebugFlags, 3
0x18000ec2e  jz      short loc_18000EC61
0x18000ec30  mov     rcx, cs:g_pDebug
0x18000ec37  lea     r9, aWpContextStart; "WP_CONTEXT::Start"
0x18000ec3e  mov     [rsp+38h+var_10], eax
0x18000ec42  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000ec49  lea     rax, aFailedToStartP; "Failed to start Pending requests monito"...
0x18000ec50  mov     r8d, 191h
0x18000ec56  mov     [rsp+38h+var_18], rax
0x18000ec5b  call    cs:__imp_PuDbgPrint
0x18000ec61  mov     eax, ebx
0x18000ec63  add     rsp, 30h
0x18000ec67  pop     rbx
0x18000ec68  retn
0x18000ec69  test    byte ptr cs:g_dwDebugFlags, 3
0x18000ec70  jz      short loc_18000EC1C
0x18000ec72  mov     rcx, cs:g_pDebug
0x18000ec79  lea     r9, aWpContextStart; "WP_CONTEXT::Start"
0x18000ec80  mov     [rsp+38h+var_10], eax
0x18000ec84  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000ec8b  lea     rax, aFailedToAddPen; "Failed to add pending UL_NATIVE_REQUEST"...
0x18000ec92  mov     r8d, 181h
0x18000ec98  mov     [rsp+38h+var_18], rax
0x18000ec9d  call    cs:__imp_PuDbgPrint
0x18000eca3  jmp     loc_18000EC1C
```
