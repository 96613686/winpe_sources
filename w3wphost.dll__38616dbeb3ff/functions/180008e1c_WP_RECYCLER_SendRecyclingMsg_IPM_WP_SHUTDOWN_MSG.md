# WP_RECYCLER::SendRecyclingMsg(IPM_WP_SHUTDOWN_MSG)

- ea: `0x180008e1c`
- end: `0x180008e96`
- name: `?SendRecyclingMsg@WP_RECYCLER@@QEAAXW4IPM_WP_SHUTDOWN_MSG@@@Z`
- size: `122`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x1800010c0`
- `0x1800096cc`
- `0x180009920`
- `0x180009990`

## callees

- `0x180008ad4`
- `0x180008e1c`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180008e84`
- `iisutil!PuDbgPrint` at `0x180008e84`

## string_xrefs

- `0x180008e6b`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wprecycler.cxx`

## pseudocode

```c
__int64 __fastcall WP_RECYCLER::SendRecyclingMsg(__int64 a1, int a2)
{
  __int64 result; // rax
  __int64 v3; // rcx

  result = 1;
  if ( *(_DWORD *)(a1 + 176) != 1 )
  {
    result = (unsigned int)_InterlockedExchange((volatile __int32 *)(a1 + 176), 1);
    if ( !(_DWORD)result )
    {
      result = *(_QWORD *)(a1 + 192);
      v3 = *(_QWORD *)(result + 88);
      if ( v3 )
      {
        result = WP_IPM::SendShutdownRequestMessage(v3, a2);
        if ( (int)result < 0 && (g_dwDebugFlags & 3) != 0 )
          return PuDbgPrint(
                   g_pDebug,
                   "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wprecycler.cxx",
                   1398,
                   "WP_RECYCLER::SendRecyclingMsg",
                   "failed to send recycling request message to WAS: hr=0x%x\n",
                   result);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180008e1c  sub     rsp, 38h
0x180008e20  mov     eax, 1
0x180008e25  cmp     [rcx+0B0h], eax
0x180008e2b  jz      short loc_180008E90
0x180008e2d  xchg    eax, [rcx+0B0h]
0x180008e33  test    eax, eax
0x180008e35  jnz     short loc_180008E90
0x180008e37  mov     rax, [rcx+0C0h]
0x180008e3e  mov     rcx, [rax+58h]
0x180008e42  test    rcx, rcx
0x180008e45  jz      short loc_180008E90
0x180008e47  call    ?SendShutdownRequestMessage@WP_IPM@@QEAAJW4IPM_WP_SHUTDOWN_MSG@@@Z; WP_IPM::SendShutdownRequestMessage(IPM_WP_SHUTDOWN_MSG)
0x180008e4c  test    eax, eax
0x180008e4e  jns     short loc_180008E90
0x180008e50  test    byte ptr cs:g_dwDebugFlags, 3
0x180008e57  jz      short loc_180008E90
0x180008e59  mov     rcx, cs:g_pDebug
0x180008e60  lea     r9, aWpRecyclerSend; "WP_RECYCLER::SendRecyclingMsg"
0x180008e67  mov     [rsp+38h+var_10], eax
0x180008e6b  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008e72  lea     rax, aFailedToSendRe; "failed to send recycling request messag"...
0x180008e79  mov     r8d, 576h
0x180008e7f  mov     [rsp+38h+var_18], rax
0x180008e84  call    cs:__imp_PuDbgPrint
0x180008e8b  nop     dword ptr [rax+rax+00h]
0x180008e90  add     rsp, 38h
0x180008e94  retn
```
