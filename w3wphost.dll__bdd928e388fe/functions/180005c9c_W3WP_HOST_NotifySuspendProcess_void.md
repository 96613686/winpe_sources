# W3WP_HOST::NotifySuspendProcess(void)

- ea: `0x180005c9c`
- end: `0x180005d3e`
- name: `?NotifySuspendProcess@W3WP_HOST@@QEAAJXZ`
- size: `162`
- prototype: `__int64 __fastcall(W3WP_HOST *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009044`

## callees

- `0x180001970`
- `0x180005c9c`
- `0x18000d010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180005d05`
- `iisutil!PuDbgPrint` at `0x180005d05`

## string_xrefs

- `0x180005cec`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`

## pseudocode

```c
__int64 __fastcall W3WP_HOST::NotifySuspendProcess(W3WP_HOST *this)
{
  W3WP_HOST *v1; // rsi
  int v2; // ebx
  PROTOCOL_MANAGER_ENTRY **i; // rdx
  PROTOCOL_MANAGER_ENTRY **NextProtocolManagerEntry; // rax
  PROTOCOL_MANAGER_ENTRY **v5; // rdi

  v1 = g_pW3WPHost;
  v2 = 0;
  for ( i = 0; ; i = v5 )
  {
    NextProtocolManagerEntry = PROTOCOL_MANAGER_LIST::GetNextProtocolManagerEntry((W3WP_HOST *)((char *)v1 + 320), i);
    v5 = NextProtocolManagerEntry;
    if ( !NextProtocolManagerEntry )
      break;
    v2 = (*(__int64 (__fastcall **)(PROTOCOL_MANAGER_ENTRY *))(*(_QWORD *)NextProtocolManagerEntry[37] + 16LL))(NextProtocolManagerEntry[37]);
    if ( v2 < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
          5773,
          "W3WP_HOST::NotifySuspendProcess",
          "Notification of idle paged out call failed with error 0x%x \n");
      if ( v2 != -2147467263 )
        return (unsigned int)v2;
      v2 = 0;
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180005c9c  mov     [rsp+arg_0], rbx
0x180005ca1  mov     [rsp+arg_8], rsi
0x180005ca6  push    rdi
0x180005ca7  sub     rsp, 30h
0x180005cab  mov     rsi, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x180005cb2  xor     ebx, ebx
0x180005cb4  xor     edx, edx
0x180005cb6  jmp     short loc_180005D18
0x180005cb8  mov     rcx, [rdi+128h]
0x180005cbf  mov     rax, [rcx]
0x180005cc2  mov     rax, [rax+10h]
0x180005cc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ccb  mov     ebx, eax
0x180005ccd  test    eax, eax
0x180005ccf  jns     short loc_180005D15
0x180005cd1  test    byte ptr cs:g_dwDebugFlags, 3
0x180005cd8  jz      short loc_180005D0B
0x180005cda  mov     rcx, cs:g_pDebug
0x180005ce1  lea     r9, aW3wpHostNotify; "W3WP_HOST::NotifySuspendProcess"
0x180005ce8  mov     [rsp+38h+var_10], eax
0x180005cec  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180005cf3  lea     rax, aNotificationOf; "Notification of idle paged out call fai"...
0x180005cfa  mov     r8d, 168Dh
0x180005d00  mov     [rsp+38h+var_18], rax
0x180005d05  call    cs:__imp_PuDbgPrint
0x180005d0b  cmp     ebx, 80004001h
0x180005d11  jnz     short loc_180005D2C
0x180005d13  xor     ebx, ebx
0x180005d15  mov     rdx, rdi; struct PROTOCOL_MANAGER_ENTRY *
0x180005d18  lea     rcx, [rsi+140h]; this
0x180005d1f  call    ?GetNextProtocolManagerEntry@PROTOCOL_MANAGER_LIST@@QEAAPEAVPROTOCOL_MANAGER_ENTRY@@PEAV2@@Z; PROTOCOL_MANAGER_LIST::GetNextProtocolManagerEntry(PROTOCOL_MANAGER_ENTRY *)
0x180005d24  mov     rdi, rax
0x180005d27  test    rax, rax
0x180005d2a  jnz     short loc_180005CB8
0x180005d2c  mov     rsi, [rsp+38h+arg_8]
0x180005d31  mov     eax, ebx
0x180005d33  mov     rbx, [rsp+38h+arg_0]
0x180005d38  add     rsp, 30h
0x180005d3c  pop     rdi
0x180005d3d  retn
```
