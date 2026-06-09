# CNetworkAddress::NetworkToHostByteOrder(unsigned __int64)

- ea: `0x180023af0`
- end: `0x180023b20`
- name: `?NetworkToHostByteOrder@CNetworkAddress@@SA_K_K@Z`
- size: `48`
- prototype: `unsigned __int64 __fastcall(unsigned __int64)`
- caller_count: `17`
- callee_count: `0`
- tags: ``

## callers

- `0x1800132cc`
- `0x18001bbb8`
- `0x18001c238`
- `0x18001c48c`
- `0x18001e73c`
- `0x18001e9d4`
- `0x18001ebc0`
- `0x18001ec1c`
- `0x18001ef8c`
- `0x18001f148`
- `0x18001f414`
- `0x18001f538`
- `0x18001f658`
- `0x18001f714`
- `0x18001f870`
- `0x18001f9b0`
- `0x18001fbec`

## import_xrefs

- `WS2_32!__imp_ntohl` at `0x180023afb`
- `WS2_32!__imp_ntohl` at `0x180023b07`
- `WS2_32!__imp_ntohl` at `0x180023afb`
- `WS2_32!__imp_ntohl` at `0x180023b07`

## pseudocode

```c
unsigned __int64 __fastcall CNetworkAddress::NetworkToHostByteOrder(__int64 a1)
{
  u_long v1; // ebx
  u_long netlong_4; // [rsp+34h] [rbp+Ch]

  netlong_4 = HIDWORD(a1);
  v1 = ntohl(a1);
  return __PAIR64__(v1, ntohl(netlong_4));
}

```

## disassembly

```asm
0x180023af0  push    rbx
0x180023af2  sub     rsp, 20h
0x180023af6  mov     [rsp+28h+netlong], rcx
0x180023afb  call    cs:__imp_ntohl
0x180023b01  mov     ecx, dword ptr [rsp+28h+netlong+4]; netlong
0x180023b05  mov     ebx, eax
0x180023b07  call    cs:__imp_ntohl
0x180023b0d  mov     dword ptr [rsp+28h+netlong], eax
0x180023b11  mov     dword ptr [rsp+28h+netlong+4], ebx
0x180023b15  mov     rax, [rsp+28h+netlong]
0x180023b1a  add     rsp, 20h
0x180023b1e  pop     rbx
0x180023b1f  retn
```
