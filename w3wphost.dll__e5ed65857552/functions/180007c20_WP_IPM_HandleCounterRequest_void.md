# WP_IPM::HandleCounterRequest(void)

- ea: `0x180007c20`
- end: `0x180007c7a`
- name: `?HandleCounterRequest@WP_IPM@@AEAAJXZ`
- size: `90`
- prototype: `__int64 __fastcall(WP_IPM *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001180`

## callees

- `0x180006d24`
- `0x180007c20`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180007c61`
- `iisutil!PuDbgPrint` at `0x180007c61`

## string_xrefs

- `0x180007c5a`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`

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
0x180007c20  sub     rsp, 38h
0x180007c24  mov     eax, cs:g_dwDebugFlags
0x180007c2a  test    al, 3
0x180007c2c  setnz   cl
0x180007c2f  bt      eax, 13h
0x180007c33  setb    al
0x180007c36  test    al, cl
0x180007c38  jz      short loc_180007C6D
0x180007c3a  mov     rcx, cs:g_pDebug
0x180007c41  lea     rax, aHandleCounterR; "Handle Counter Request\n\n"
0x180007c48  lea     r9, aWpIpmHandlecou; "WP_IPM::HandleCounterRequest"
0x180007c4f  mov     [rsp+38h+var_18], rax
0x180007c54  mov     r8d, 366h
0x180007c5a  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180007c61  call    cs:__imp_PuDbgPrint
0x180007c68  nop     dword ptr [rax+rax+00h]
0x180007c6d  call    ?RequestCounters@W3WP_HOST@@QEAAXXZ; W3WP_HOST::RequestCounters(void)
0x180007c72  xor     eax, eax
0x180007c74  add     rsp, 38h
0x180007c78  retn
```
