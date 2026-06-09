# WP_IPM::HandleCounterRequest(void)

- ea: `0x180007480`
- end: `0x1800074d3`
- name: `?HandleCounterRequest@WP_IPM@@AEAAJXZ`
- size: `83`
- prototype: `__int64 __fastcall(WP_IPM *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001170`

## callees

- `0x1800066c4`
- `0x180007480`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x1800074c1`
- `iisutil!PuDbgPrint` at `0x1800074c1`

## string_xrefs

- `0x1800074ba`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`

## pseudocode

```c
__int64 __fastcall WP_IPM::HandleCounterRequest(WP_IPM *this)
{
  LOBYTE(this) = (g_dwDebugFlags & 3) != 0;
  if ( ((unsigned __int8)this & ((g_dwDebugFlags & 0x80000) != 0)) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wpipm.cxx",
      870,
      "WP_IPM::HandleCounterRequest",
      "Handle Counter Request\n\n");
  W3WP_HOST::RequestCounters(this);
  return 0;
}

```

## disassembly

```asm
0x180007480  sub     rsp, 38h
0x180007484  mov     eax, cs:g_dwDebugFlags
0x18000748a  test    al, 3
0x18000748c  setnz   cl
0x18000748f  bt      eax, 13h
0x180007493  setb    al
0x180007496  test    al, cl
0x180007498  jz      short loc_1800074C7
0x18000749a  mov     rcx, cs:g_pDebug
0x1800074a1  lea     rax, aHandleCounterR; "Handle Counter Request\n\n"
0x1800074a8  lea     r9, aWpIpmHandlecou; "WP_IPM::HandleCounterRequest"
0x1800074af  mov     [rsp+38h+var_18], rax
0x1800074b4  mov     r8d, 366h
0x1800074ba  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800074c1  call    cs:__imp_PuDbgPrint
0x1800074c7  call    ?RequestCounters@W3WP_HOST@@QEAAXXZ; W3WP_HOST::RequestCounters(void)
0x1800074cc  xor     eax, eax
0x1800074ce  add     rsp, 38h
0x1800074d2  retn
```
