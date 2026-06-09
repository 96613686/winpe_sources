# UL_NATIVE_REQUEST::PendingRequestsMonitorHandler(void *,uchar)

- ea: `0x180012b00`
- end: `0x180012b56`
- name: `?PendingRequestsMonitorHandler@UL_NATIVE_REQUEST@@SAXPEAXE@Z`
- size: `86`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000edc0`
- `0x180012b00`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180012b42`
- `iisutil!PuDbgPrint` at `0x180012b42`

## string_xrefs

- `0x180012b3b`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\nativerequest.cxx`

## pseudocode

```c
void __fastcall UL_NATIVE_REQUEST::PendingRequestsMonitorHandler(PVOID a1)
{
  if ( !UL_NATIVE_REQUEST::sm_cRequestsPending )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\nativerequest.cxx",
        1948,
        "UL_NATIVE_REQUEST::PendingRequestsMonitorHandler",
        "Worker process has run out of pending requests. Trying to add one\n");
    UL_NATIVE_REQUEST::AddPendingRequests(1u);
  }
}

```

## disassembly

```asm
0x180012b00  sub     rsp, 38h
0x180012b04  cmp     cs:?sm_cRequestsPending@UL_NATIVE_REQUEST@@0KA, 0; ulong UL_NATIVE_REQUEST::sm_cRequestsPending
0x180012b0b  jz      short loc_180012B12
0x180012b0d  add     rsp, 38h
0x180012b11  retn
0x180012b12  test    byte ptr cs:g_dwDebugFlags, 3
0x180012b19  jz      short loc_180012B48
0x180012b1b  mov     rcx, cs:g_pDebug
0x180012b22  lea     rax, aWorkerProcessH; "Worker process has run out of pending r"...
0x180012b29  lea     r9, aUlNativeReques; "UL_NATIVE_REQUEST::PendingRequestsMonit"...
0x180012b30  mov     [rsp+38h+var_18], rax
0x180012b35  mov     r8d, 79Ch
0x180012b3b  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180012b42  call    cs:__imp_PuDbgPrint
0x180012b48  mov     ecx, 1; unsigned int
0x180012b4d  add     rsp, 38h
0x180012b51  jmp     ?AddPendingRequests@UL_NATIVE_REQUEST@@SAJK@Z; UL_NATIVE_REQUEST::AddPendingRequests(ulong)
```
