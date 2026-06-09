# WP_RECYCLER::SendRecyclingMsg(IPM_WP_SHUTDOWN_MSG)

- ea: `0x18000850c`
- end: `0x18000857f`
- name: `?SendRecyclingMsg@WP_RECYCLER@@QEAAXW4IPM_WP_SHUTDOWN_MSG@@@Z`
- size: `115`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x1800010c0`
- `0x180008ce0`
- `0x180008f00`
- `0x180008f70`

## callees

- `0x1800081fc`
- `0x18000850c`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180008574`
- `iisutil!PuDbgPrint` at `0x180008574`

## string_xrefs

- `0x18000855b`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wprecycler.cxx`

## pseudocode

```c
__int64 __fastcall WP_RECYCLER::SendRecyclingMsg(__int64 a1, __int64 a2)
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
                   "failed to send recycling request message to WAS: hr=0x%x\n");
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000850c  sub     rsp, 38h
0x180008510  mov     eax, 1
0x180008515  cmp     [rcx+0B0h], eax
0x18000851b  jz      short loc_18000857A
0x18000851d  xchg    eax, [rcx+0B0h]
0x180008523  test    eax, eax
0x180008525  jnz     short loc_18000857A
0x180008527  mov     rax, [rcx+0C0h]
0x18000852e  mov     rcx, [rax+58h]
0x180008532  test    rcx, rcx
0x180008535  jz      short loc_18000857A
0x180008537  call    ?SendShutdownRequestMessage@WP_IPM@@QEAAJW4IPM_WP_SHUTDOWN_MSG@@@Z; WP_IPM::SendShutdownRequestMessage(IPM_WP_SHUTDOWN_MSG)
0x18000853c  test    eax, eax
0x18000853e  jns     short loc_18000857A
0x180008540  test    byte ptr cs:g_dwDebugFlags, 3
0x180008547  jz      short loc_18000857A
0x180008549  mov     rcx, cs:g_pDebug
0x180008550  lea     r9, aWpRecyclerSend; "WP_RECYCLER::SendRecyclingMsg"
0x180008557  mov     [rsp+38h+var_10], eax
0x18000855b  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008562  lea     rax, aFailedToSendRe; "failed to send recycling request messag"...
0x180008569  mov     r8d, 576h
0x18000856f  mov     [rsp+38h+var_18], rax
0x180008574  call    cs:__imp_PuDbgPrint
0x18000857a  add     rsp, 38h
0x18000857e  retn
```
