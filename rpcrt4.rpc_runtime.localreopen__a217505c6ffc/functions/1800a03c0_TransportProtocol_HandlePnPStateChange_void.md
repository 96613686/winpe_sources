# TransportProtocol::HandlePnPStateChange(void)

- ea: `0x1800a03c0`
- end: `0x1800a0496`
- name: `?HandlePnPStateChange@TransportProtocol@@SAHXZ`
- size: `214`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800bdccc`

## callees

- `0x180023a40`
- `0x180044870`
- `0x1800a03c0`
- `0x1800a049c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0420`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0420`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a043c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a043c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a03de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a03de`
- `WS2_32!WSAEnumProtocolsW` at `0x1800a0405`
- `WS2_32!WSAEnumProtocolsW` at `0x1800a0405`

## pseudocode

```c
__int64 TransportProtocol::HandlePnPStateChange(void)
{
  struct _WSAPROTOCOL_INFOW *v0; // rax
  struct _WSAPROTOCOL_INFOW *v1; // rbx
  int v2; // esi
  unsigned int v3; // ebx
  int i; // edi
  unsigned int Size; // [rsp+30h] [rbp+8h] BYREF

  Size = 512;
  EnterCriticalSection(&AddressListLock);
  while ( 1 )
  {
    v0 = (struct _WSAPROTOCOL_INFOW *)I_RpcAllocate(Size);
    v1 = v0;
    if ( !v0 )
    {
LABEL_5:
      v3 = 0;
      goto LABEL_6;
    }
    v2 = WSAEnumProtocolsW(0, v0, &Size);
    if ( v2 != -1 )
      break;
    FreeWrapper(v1);
    if ( GetLastError() != 10055 )
      goto LABEL_5;
  }
  for ( i = 1; i < 16; ++i )
    TransportProtocol::HandleProtocolChange(
      (struct TransportProtocol *)((char *)TransportProtocolArray + 72 * (unsigned int)i),
      v1,
      v2,
      i);
  FreeWrapper(v1);
  v3 = g_NotifyRt;
LABEL_6:
  LeaveCriticalSection(&AddressListLock);
  return v3;
}

```

## disassembly

```asm
0x1800a03c0  mov     [rsp+arg_8], rbx
0x1800a03c5  mov     [rsp+arg_10], rsi
0x1800a03ca  push    rdi
0x1800a03cb  sub     rsp, 20h
0x1800a03cf  lea     rcx, ?AddressListLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800a03d6  mov     [rsp+28h+Size], 200h
0x1800a03de  call    cs:__imp_EnterCriticalSection
0x1800a03e5  nop     dword ptr [rax+rax+00h]
0x1800a03ea  mov     ecx, [rsp+28h+Size]; Size
0x1800a03ee  call    I_RpcAllocate
0x1800a03f3  mov     rbx, rax
0x1800a03f6  test    rax, rax
0x1800a03f9  jz      short loc_1800A0433
0x1800a03fb  lea     r8, [rsp+28h+Size]; lpdwBufferLength
0x1800a0400  mov     rdx, rax; lpProtocolBuffer
0x1800a0403  xor     ecx, ecx; lpiProtocols
0x1800a0405  call    cs:__imp_WSAEnumProtocolsW
0x1800a040c  nop     dword ptr [rax+rax+00h]
0x1800a0411  mov     esi, eax
0x1800a0413  cmp     eax, 0FFFFFFFFh
0x1800a0416  jnz     short loc_1800A045B
0x1800a0418  mov     rcx, rbx; lpMem
0x1800a041b  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800a0420  call    cs:__imp_GetLastError
0x1800a0427  nop     dword ptr [rax+rax+00h]
0x1800a042c  cmp     eax, 2747h
0x1800a0431  jz      short loc_1800A03EA
0x1800a0433  xor     ebx, ebx
0x1800a0435  lea     rcx, ?AddressListLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800a043c  call    cs:__imp_LeaveCriticalSection
0x1800a0443  nop     dword ptr [rax+rax+00h]
0x1800a0448  mov     rsi, [rsp+28h+arg_10]
0x1800a044d  mov     eax, ebx
0x1800a044f  mov     rbx, [rsp+28h+arg_8]
0x1800a0454  add     rsp, 20h
0x1800a0458  pop     rdi
0x1800a0459  retn
0x1800a045b  mov     edi, 1
0x1800a0460  mov     eax, edi
0x1800a0462  mov     r9d, edi; int
0x1800a0465  mov     r8d, esi; int
0x1800a0468  mov     rdx, rbx; struct _WSAPROTOCOL_INFOW *
0x1800a046b  lea     rcx, [rax+rax*8]
0x1800a046f  mov     rax, cs:?TransportProtocolArray@@3PEAVTransportProtocol@@EA; TransportProtocol * TransportProtocolArray
0x1800a0476  lea     rcx, [rax+rcx*8]; this
0x1800a047a  call    ?HandleProtocolChange@TransportProtocol@@QEAAXPEAU_WSAPROTOCOL_INFOW@@HH@Z; TransportProtocol::HandleProtocolChange(_WSAPROTOCOL_INFOW *,int,int)
0x1800a047f  inc     edi
0x1800a0481  cmp     edi, 10h
0x1800a0484  jl      short loc_1800A0460
0x1800a0486  mov     rcx, rbx; lpMem
0x1800a0489  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800a048e  mov     ebx, cs:?g_NotifyRt@@3JA; long g_NotifyRt
0x1800a0494  jmp     short loc_1800A0435
```
