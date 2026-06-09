# CNetworkAddress::HostToNetworkByteOrder(unsigned __int64)

- ea: `0x180023b28`
- end: `0x180023b58`
- name: `?HostToNetworkByteOrder@CNetworkAddress@@SA_K_K@Z`
- size: `48`
- prototype: `unsigned __int64 __fastcall(unsigned __int64)`
- caller_count: `14`
- callee_count: `0`
- tags: ``

## callers

- `0x1800122a4`
- `0x1800132cc`
- `0x18001bd40`
- `0x18001c2ac`
- `0x18001c77c`
- `0x18001d560`
- `0x18001d730`
- `0x18001d8a8`
- `0x18001dab0`
- `0x18001dd2c`
- `0x18001df44`
- `0x18001e16c`
- `0x18001e398`
- `0x18001e73c`

## import_xrefs

- `WS2_32!__imp_htonl` at `0x180023b33`
- `WS2_32!__imp_htonl` at `0x180023b3f`
- `WS2_32!__imp_htonl` at `0x180023b33`
- `WS2_32!__imp_htonl` at `0x180023b3f`

## pseudocode

```c
unsigned __int64 __fastcall CNetworkAddress::HostToNetworkByteOrder(__int64 a1)
{
  u_long v1; // ebx
  u_long hostlong_4; // [rsp+34h] [rbp+Ch]

  hostlong_4 = HIDWORD(a1);
  v1 = htonl(a1);
  return __PAIR64__(v1, htonl(hostlong_4));
}

```

## disassembly

```asm
0x180023b28  push    rbx
0x180023b2a  sub     rsp, 20h
0x180023b2e  mov     [rsp+28h+hostlong], rcx
0x180023b33  call    cs:__imp_htonl
0x180023b39  mov     ecx, dword ptr [rsp+28h+hostlong+4]; hostlong
0x180023b3d  mov     ebx, eax
0x180023b3f  call    cs:__imp_htonl
0x180023b45  mov     dword ptr [rsp+28h+hostlong], eax
0x180023b49  mov     dword ptr [rsp+28h+hostlong+4], ebx
0x180023b4d  mov     rax, [rsp+28h+hostlong]
0x180023b52  add     rsp, 20h
0x180023b56  pop     rbx
0x180023b57  retn
```
