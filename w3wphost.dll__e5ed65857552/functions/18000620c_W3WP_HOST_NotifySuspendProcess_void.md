# W3WP_HOST::NotifySuspendProcess(void)

- ea: `0x18000620c`
- end: `0x1800062b5`
- name: `?NotifySuspendProcess@W3WP_HOST@@QEAAJXZ`
- size: `169`
- prototype: `__int64 __fastcall(W3WP_HOST *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009a78`

## callees

- `0x1800019f0`
- `0x18000620c`
- `0x18000e010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180006275`
- `iisutil!PuDbgPrint` at `0x180006275`

## string_xrefs

- `0x18000625c`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`

## pseudocode

```c
__int64 __fastcall W3WP_HOST::NotifySuspendProcess(W3WP_HOST *this)
{
  W3WP_HOST *v1; // rsi
  unsigned int v2; // ebx
  PROTOCOL_MANAGER_ENTRY **i; // rdx
  int v4; // eax
  PROTOCOL_MANAGER_ENTRY **NextProtocolManagerEntry; // rax
  PROTOCOL_MANAGER_ENTRY **v6; // rdi

  v1 = g_pW3WPHost;
  v2 = 0;
  for ( i = 0; ; i = v6 )
  {
    NextProtocolManagerEntry = PROTOCOL_MANAGER_LIST::GetNextProtocolManagerEntry((W3WP_HOST *)((char *)v1 + 320), i);
    v6 = NextProtocolManagerEntry;
    if ( !NextProtocolManagerEntry )
      break;
    v4 = (*(__int64 (__fastcall **)(PROTOCOL_MANAGER_ENTRY *))(*(_QWORD *)NextProtocolManagerEntry[37] + 16LL))(NextProtocolManagerEntry[37]);
    v2 = v4;
    if ( v4 < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
          5773,
          "W3WP_HOST::NotifySuspendProcess",
          "Notification of idle paged out call failed with error 0x%x \n",
          v4);
      if ( v2 != -2147467263 )
        return v2;
      v2 = 0;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18000620c  mov     [rsp+arg_0], rbx
0x180006211  mov     [rsp+arg_8], rsi
0x180006216  push    rdi
0x180006217  sub     rsp, 30h
0x18000621b  mov     rsi, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x180006222  xor     ebx, ebx
0x180006224  xor     edx, edx
0x180006226  jmp     short loc_18000628E
0x180006228  mov     rcx, [rdi+128h]
0x18000622f  mov     rax, [rcx]
0x180006232  mov     rax, [rax+10h]
0x180006236  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000623b  mov     ebx, eax
0x18000623d  test    eax, eax
0x18000623f  jns     short loc_18000628B
0x180006241  test    byte ptr cs:g_dwDebugFlags, 3
0x180006248  jz      short loc_180006281
0x18000624a  mov     rcx, cs:g_pDebug
0x180006251  lea     r9, aW3wpHostNotify; "W3WP_HOST::NotifySuspendProcess"
0x180006258  mov     [rsp+38h+var_10], eax
0x18000625c  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180006263  lea     rax, aNotificationOf; "Notification of idle paged out call fai"...
0x18000626a  mov     r8d, 168Dh
0x180006270  mov     [rsp+38h+var_18], rax
0x180006275  call    cs:__imp_PuDbgPrint
0x18000627c  nop     dword ptr [rax+rax+00h]
0x180006281  cmp     ebx, 80004001h
0x180006287  jnz     short loc_1800062A2
0x180006289  xor     ebx, ebx
0x18000628b  mov     rdx, rdi; struct PROTOCOL_MANAGER_ENTRY *
0x18000628e  lea     rcx, [rsi+140h]; this
0x180006295  call    ?GetNextProtocolManagerEntry@PROTOCOL_MANAGER_LIST@@QEAAPEAVPROTOCOL_MANAGER_ENTRY@@PEAV2@@Z; PROTOCOL_MANAGER_LIST::GetNextProtocolManagerEntry(PROTOCOL_MANAGER_ENTRY *)
0x18000629a  mov     rdi, rax
0x18000629d  test    rax, rax
0x1800062a0  jnz     short loc_180006228
0x1800062a2  mov     rsi, [rsp+38h+arg_8]
0x1800062a7  mov     eax, ebx
0x1800062a9  mov     rbx, [rsp+38h+arg_0]
0x1800062ae  add     rsp, 30h
0x1800062b2  pop     rdi
0x1800062b3  retn
```
