# PxeDhcpIsValid

- ea: `0x180007c60`
- end: `0x180007ce9`
- name: `PxeDhcpIsValid`
- size: `137`
- prototype: `DWORD __stdcall(PVOID pPacket, ULONG uPacketLen, BOOL bRequestPacket, PBOOL pbPxeOptionPresent)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003b78`
- `0x180005aa4`
- `0x18000e08c`

## callees

- `0x180007c60`
- `0x180011a62`

## import_xrefs

- `WdsCommonLib!?IsValidDhcpPacket@CDhcpPacket@@SAHPEAXKHPEAU_DHCP_SERVER_OPTIONS@@@Z` at `0x180007caa`
- `WdsCommonLib!?IsValidDhcpPacket@CDhcpPacket@@SAHPEAXKHPEAU_DHCP_SERVER_OPTIONS@@@Z` at `0x180007caa`

## pseudocode

```c
DWORD __stdcall PxeDhcpIsValid(PVOID pPacket, ULONG uPacketLen, BOOL bRequestPacket, PBOOL pbPxeOptionPresent)
{
  DWORD result; // eax
  struct _DHCP_SERVER_OPTIONS v9; // [rsp+20h] [rbp-118h] BYREF

  memset_0(&v9, 0, 0x110u);
  if ( !pPacket || !uPacketLen )
    return 87;
  result = CDhcpPacket::IsValidDhcpPacket(pPacket, uPacketLen, bRequestPacket, &v9);
  if ( !result )
  {
    if ( pbPxeOptionPresent )
      *pbPxeOptionPresent = HIDWORD(v9.ScopeId);
  }
  return result;
}

```

## disassembly

```asm
0x180007c60  mov     [rsp+arg_0], rbx
0x180007c65  mov     [rsp+arg_8], rbp
0x180007c6a  mov     [rsp+arg_10], rsi
0x180007c6f  push    rdi
0x180007c70  sub     rsp, 130h
0x180007c77  mov     ebp, r8d
0x180007c7a  mov     edi, edx
0x180007c7c  mov     rsi, rcx
0x180007c7f  xor     edx, edx; Val
0x180007c81  mov     r8d, 110h; Size
0x180007c87  lea     rcx, [rsp+138h+var_118]; void *
0x180007c8c  mov     rbx, r9
0x180007c8f  call    memset_0
0x180007c94  test    rsi, rsi
0x180007c97  jz      short loc_180007CCA
0x180007c99  test    edi, edi
0x180007c9b  jz      short loc_180007CCA
0x180007c9d  lea     r9, [rsp+138h+var_118]
0x180007ca2  mov     r8d, ebp
0x180007ca5  mov     edx, edi
0x180007ca7  mov     rcx, rsi
0x180007caa  call    cs:__imp_?IsValidDhcpPacket@CDhcpPacket@@SAHPEAXKHPEAU_DHCP_SERVER_OPTIONS@@@Z; CDhcpPacket::IsValidDhcpPacket(void *,ulong,int,_DHCP_SERVER_OPTIONS *)
0x180007cb1  nop     dword ptr [rax+rax+00h]
0x180007cb6  test    eax, eax
0x180007cb8  jnz     short loc_180007CCF
0x180007cba  test    rbx, rbx
0x180007cbd  jz      short loc_180007CCF
0x180007cbf  mov     ecx, [rsp+138h+var_6C]
0x180007cc6  mov     [rbx], ecx
0x180007cc8  jmp     short loc_180007CCF
0x180007cca  mov     eax, 57h ; 'W'
0x180007ccf  lea     r11, [rsp+138h+var_8]
0x180007cd7  mov     rbx, [r11+10h]
0x180007cdb  mov     rbp, [r11+18h]
0x180007cdf  mov     rsi, [r11+20h]
0x180007ce3  mov     rsp, r11
0x180007ce6  pop     rdi
0x180007ce7  retn
```
