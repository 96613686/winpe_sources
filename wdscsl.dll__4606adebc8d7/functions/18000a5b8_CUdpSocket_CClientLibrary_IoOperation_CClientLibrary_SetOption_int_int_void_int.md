# CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::SetOption(int,int,void *,int)

- ea: `0x18000a5b8`
- end: `0x18000a607`
- name: `?SetOption@?$CUdpSocket@VCClientLibrary@@U?$IoOperation@VCClientLibrary@@@@@@QEAAKHHPEAXH@Z`
- size: `79`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180004340`
- `0x180004460`
- `0x18000a610`

## callees

- `0x18000a5b8`
- `0x18000bd5c`

## import_xrefs

- `WS2_32!__imp_setsockopt` at `0x18000a5cc`
- `WS2_32!__imp_setsockopt` at `0x18000a5cc`
- `WS2_32!__imp_WSAGetLastError` at `0x18000a5dc`
- `WS2_32!__imp_WSAGetLastError` at `0x18000a5dc`

## pseudocode

```c
__int64 __fastcall CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::SetOption(
        __int64 a1,
        int a2,
        int a3,
        const char *a4,
        int optlen)
{
  unsigned int v5; // ebx
  unsigned int Error; // eax
  __int64 v7; // rdx

  v5 = 0;
  if ( setsockopt(*(_QWORD *)(a1 + 56), a2, a3, a4, optlen) )
  {
    Error = WSAGetLastError();
    return (unsigned int)ElValidateWin32(Error, v7, (__int64)"base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", 0x25Du);
  }
  return v5;
}

```

## disassembly

```asm
0x18000a5b8  push    rbx
0x18000a5ba  sub     rsp, 30h
0x18000a5be  mov     eax, [rsp+38h+arg_20]
0x18000a5c2  xor     ebx, ebx
0x18000a5c4  mov     rcx, [rcx+38h]; s
0x18000a5c8  mov     [rsp+38h+optlen], eax; optlen
0x18000a5cc  call    cs:__imp_setsockopt
0x18000a5d3  nop     dword ptr [rax+rax+00h]
0x18000a5d8  test    eax, eax
0x18000a5da  jz      short loc_18000A5FE
0x18000a5dc  call    cs:__imp_WSAGetLastError
0x18000a5e3  nop     dword ptr [rax+rax+00h]
0x18000a5e8  mov     r9d, 25Dh
0x18000a5ee  lea     r8, aBaseEcoWdsWdsl; "base\\Eco\\WDS\\wdslib\\net\\UdpSocket."...
0x18000a5f5  mov     ecx, eax
0x18000a5f7  call    ElValidateWin32
0x18000a5fc  mov     ebx, eax
0x18000a5fe  mov     eax, ebx
0x18000a600  add     rsp, 30h
0x18000a604  pop     rbx
0x18000a605  retn
```
