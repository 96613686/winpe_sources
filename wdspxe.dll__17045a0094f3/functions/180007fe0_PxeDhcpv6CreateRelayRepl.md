# PxeDhcpv6CreateRelayRepl

- ea: `0x180007fe0`
- end: `0x180008148`
- name: `PxeDhcpv6CreateRelayRepl`
- size: `360`
- prototype: `DWORD __stdcall(PPXE_DHCPV6_NESTED_RELAY_MESSAGE pRelayMessages, ULONG nRelayMessages, PBYTE pInnerPacket, ULONG cbInnerPacket, PVOID pReplyBuffer, ULONG cbReplyBuffer, PULONG pcbReplyBuffer)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180007198`
- `0x1800074e0`
- `0x1800075dc`
- `0x180007fe0`

## import_xrefs

- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18000810c`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18000810c`
- `WdsCommonLib!?BufferInitializeReply@CDhcpv6Packet@@QEAAKPEAX_K01@Z` at `0x180008083`
- `WdsCommonLib!?BufferInitializeReply@CDhcpv6Packet@@QEAAKPEAX_K01@Z` at `0x180008083`
- `WdsCommonLib!??1CDhcpv6Packet@@QEAA@XZ` at `0x18000811f`
- `WdsCommonLib!??1CDhcpv6Packet@@QEAA@XZ` at `0x18000811f`
- `WdsCommonLib!?GetPacketUsedBytes@CDhcpv6Packet@@QEAA_KXZ` at `0x1800080d1`
- `WdsCommonLib!?GetPacketUsedBytes@CDhcpv6Packet@@QEAA_KXZ` at `0x1800080d1`
- `WdsCommonLib!??0CDhcpv6Packet@@QEAA@XZ` at `0x180008008`
- `WdsCommonLib!??0CDhcpv6Packet@@QEAA@XZ` at `0x180008008`

## pseudocode

```c
DWORD __stdcall PxeDhcpv6CreateRelayRepl(
        PPXE_DHCPV6_NESTED_RELAY_MESSAGE pRelayMessages,
        ULONG nRelayMessages,
        PBYTE pInnerPacket,
        ULONG cbInnerPacket,
        PVOID pReplyBuffer,
        ULONG cbReplyBuffer,
        PULONG pcbReplyBuffer)
{
  __int64 v11; // rdx
  __int64 v12; // r8
  DWORD v13; // ebx
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // r8
  unsigned __int64 PacketUsedBytes; // rax
  __int64 v19; // r8
  ULONG v20; // ecx
  unsigned int v21; // edi
  _BYTE v23[32]; // [rsp+30h] [rbp-38h] BYREF

  CDhcpv6Packet::CDhcpv6Packet((CDhcpv6Packet *)v23);
  if ( pRelayMessages
    && nRelayMessages
    && pInnerPacket
    && cbInnerPacket
    && pReplyBuffer
    && cbReplyBuffer
    && pcbReplyBuffer
    || (v13 = 87, !(unsigned int)ElValidateWin32_3(87, v11, v12, 2171)) )
  {
    v13 = CDhcpv6Packet::BufferInitializeReply(
            (CDhcpv6Packet *)v23,
            pReplyBuffer,
            cbReplyBuffer,
            pRelayMessages->pRelayMessage,
            pRelayMessages->cbRelayMessage);
    if ( !(unsigned int)ElValidateWin32_3(v13, v14, v15, 2178) )
    {
      v13 = PxeDhcpv6NestRelayRepl(
              (unsigned int)v23,
              (_DWORD)pRelayMessages,
              nRelayMessages,
              (_DWORD)pInnerPacket,
              cbInnerPacket);
      if ( !(unsigned int)ElValidateWin32_3(v13, v16, v17, 2185) )
      {
        PacketUsedBytes = CDhcpv6Packet::GetPacketUsedBytes((CDhcpv6Packet *)v23);
        v20 = -1;
        if ( PacketUsedBytes <= 0xFFFFFFFF )
          v20 = PacketUsedBytes;
        *pcbReplyBuffer = v20;
        v21 = PacketUsedBytes > 0xFFFFFFFF ? 0x80070216 : 0;
        if ( (int)ElValidateHr(v21, 0xFFFFFFFFLL, v19, 2189) < 0 )
          v13 = WIN32_FROM_HRESULT(v21);
      }
    }
  }
  CDhcpv6Packet::~CDhcpv6Packet((CDhcpv6Packet *)v23);
  return v13;
}

```

## disassembly

```asm
0x180007fe0  mov     rax, rsp
0x180007fe3  mov     [rax+8], rbx
0x180007fe7  mov     [rax+10h], rbp
0x180007feb  mov     [rax+18h], rsi
0x180007fef  push    rdi
0x180007ff0  push    r13
0x180007ff2  push    r14
0x180007ff4  sub     rsp, 50h
0x180007ff8  mov     rdi, rcx
0x180007ffb  mov     esi, r9d
0x180007ffe  lea     rcx, [rax-38h]
0x180008002  mov     rbp, r8
0x180008005  mov     r14d, edx
0x180008008  call    cs:__imp_??0CDhcpv6Packet@@QEAA@XZ; CDhcpv6Packet::CDhcpv6Packet(void)
0x18000800f  nop     dword ptr [rax+rax+00h]
0x180008014  mov     r13, [rsp+68h+pcbReplyBuffer]
0x18000801c  test    rdi, rdi
0x18000801f  jz      short loc_180008049
0x180008021  test    r14d, r14d
0x180008024  jz      short loc_180008049
0x180008026  test    rbp, rbp
0x180008029  jz      short loc_180008049
0x18000802b  test    esi, esi
0x18000802d  jz      short loc_180008049
0x18000802f  cmp     [rsp+68h+pReplyBuffer], 0
0x180008038  jz      short loc_180008049
0x18000803a  cmp     [rsp+68h+cbReplyBuffer], 0
0x180008042  jz      short loc_180008049
0x180008044  test    r13, r13
0x180008047  jnz     short loc_180008063
0x180008049  mov     ebx, 57h ; 'W'
0x18000804e  mov     r9d, 87Bh
0x180008054  mov     ecx, ebx
0x180008056  call    ElValidateWin32_3
0x18000805b  test    eax, eax
0x18000805d  jnz     loc_18000811A
0x180008063  mov     eax, [rdi+8]
0x180008066  lea     rcx, [rsp+68h+var_38]
0x18000806b  mov     r8d, [rsp+68h+cbReplyBuffer]
0x180008073  mov     r9, [rdi]
0x180008076  mov     rdx, [rsp+68h+pReplyBuffer]
0x18000807e  mov     [rsp+68h+var_48], rax
0x180008083  call    cs:__imp_?BufferInitializeReply@CDhcpv6Packet@@QEAAKPEAX_K01@Z; CDhcpv6Packet::BufferInitializeReply(void *,unsigned __int64,void *,unsigned __int64)
0x18000808a  nop     dword ptr [rax+rax+00h]
0x18000808f  mov     ecx, eax
0x180008091  mov     r9d, 882h
0x180008097  mov     ebx, eax
0x180008099  call    ElValidateWin32_3
0x18000809e  test    eax, eax
0x1800080a0  jnz     short loc_18000811A
0x1800080a2  mov     r9, rbp
0x1800080a5  mov     dword ptr [rsp+68h+var_48], esi
0x1800080a9  mov     r8d, r14d
0x1800080ac  lea     rcx, [rsp+68h+var_38]
0x1800080b1  mov     rdx, rdi
0x1800080b4  call    PxeDhcpv6NestRelayRepl
0x1800080b9  mov     r9d, 889h
0x1800080bf  mov     ecx, eax
0x1800080c1  mov     ebx, eax
0x1800080c3  call    ElValidateWin32_3
0x1800080c8  test    eax, eax
0x1800080ca  jnz     short loc_18000811A
0x1800080cc  lea     rcx, [rsp+68h+var_38]
0x1800080d1  call    cs:__imp_?GetPacketUsedBytes@CDhcpv6Packet@@QEAA_KXZ; CDhcpv6Packet::GetPacketUsedBytes(void)
0x1800080d8  nop     dword ptr [rax+rax+00h]
0x1800080dd  mov     edx, 0FFFFFFFFh
0x1800080e2  mov     r9d, 88Dh
0x1800080e8  cmp     rax, rdx
0x1800080eb  mov     ecx, edx
0x1800080ed  cmovbe  ecx, eax
0x1800080f0  cmp     rdx, rax
0x1800080f3  mov     [r13+0], ecx
0x1800080f7  sbb     edi, edi
0x1800080f9  and     edi, 80070216h
0x1800080ff  mov     ecx, edi
0x180008101  call    ElValidateHr
0x180008106  test    eax, eax
0x180008108  jns     short loc_18000811A
0x18000810a  mov     ecx, edi
0x18000810c  call    cs:__imp_?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x180008113  nop     dword ptr [rax+rax+00h]
0x180008118  mov     ebx, eax
0x18000811a  lea     rcx, [rsp+68h+var_38]
0x18000811f  call    cs:__imp_??1CDhcpv6Packet@@QEAA@XZ; CDhcpv6Packet::~CDhcpv6Packet(void)
0x180008126  nop     dword ptr [rax+rax+00h]
0x18000812b  lea     r11, [rsp+68h+var_18]
0x180008130  mov     eax, ebx
0x180008132  mov     rbx, [r11+20h]
0x180008136  mov     rbp, [r11+28h]
0x18000813a  mov     rsi, [r11+30h]
0x18000813e  mov     rsp, r11
0x180008141  pop     r14
0x180008143  pop     r13
0x180008145  pop     rdi
0x180008146  retn
```
