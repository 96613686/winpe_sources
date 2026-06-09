# TransportProtocol::HandlePnPStateChange(void)

- ea: `0x18009cb80`
- end: `0x18009cc3d`
- name: `?HandlePnPStateChange@TransportProtocol@@SAHXZ`
- size: `189`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800b97d4`

## callees

- `0x1800122f0`
- `0x180022870`
- `0x18009cb80`
- `0x18009cc44`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009cbd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009cbd4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009cbea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009cbea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009cb9e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009cb9e`
- `WS2_32!WSAEnumProtocolsW` at `0x18009cbbf`
- `WS2_32!WSAEnumProtocolsW` at `0x18009cbbf`

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
0x18009cb80  mov     [rsp+arg_8], rbx
0x18009cb85  mov     [rsp+arg_10], rsi
0x18009cb8a  push    rdi
0x18009cb8b  sub     rsp, 20h
0x18009cb8f  lea     rcx, ?AddressListLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18009cb96  mov     [rsp+28h+Size], 200h
0x18009cb9e  call    cs:__imp_EnterCriticalSection
0x18009cba4  mov     ecx, [rsp+28h+Size]; Size
0x18009cba8  call    I_RpcAllocate
0x18009cbad  mov     rbx, rax
0x18009cbb0  test    rax, rax
0x18009cbb3  jz      short loc_18009CBE1
0x18009cbb5  lea     r8, [rsp+28h+Size]; lpdwBufferLength
0x18009cbba  mov     rdx, rax; lpProtocolBuffer
0x18009cbbd  xor     ecx, ecx; lpiProtocols
0x18009cbbf  call    cs:__imp_WSAEnumProtocolsW
0x18009cbc5  mov     esi, eax
0x18009cbc7  cmp     eax, 0FFFFFFFFh
0x18009cbca  jnz     short loc_18009CC02
0x18009cbcc  mov     rcx, rbx; lpMem
0x18009cbcf  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18009cbd4  call    cs:__imp_GetLastError
0x18009cbda  cmp     eax, 2747h
0x18009cbdf  jz      short loc_18009CBA4
0x18009cbe1  xor     ebx, ebx
0x18009cbe3  lea     rcx, ?AddressListLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18009cbea  call    cs:__imp_LeaveCriticalSection
0x18009cbf0  mov     rsi, [rsp+28h+arg_10]
0x18009cbf5  mov     eax, ebx
0x18009cbf7  mov     rbx, [rsp+28h+arg_8]
0x18009cbfc  add     rsp, 20h
0x18009cc00  pop     rdi
0x18009cc01  retn
0x18009cc02  mov     edi, 1
0x18009cc07  mov     eax, edi
0x18009cc09  mov     r9d, edi; int
0x18009cc0c  mov     r8d, esi; int
0x18009cc0f  mov     rdx, rbx; struct _WSAPROTOCOL_INFOW *
0x18009cc12  lea     rcx, [rax+rax*8]
0x18009cc16  mov     rax, cs:?TransportProtocolArray@@3PEAVTransportProtocol@@EA; TransportProtocol * TransportProtocolArray
0x18009cc1d  lea     rcx, [rax+rcx*8]; this
0x18009cc21  call    ?HandleProtocolChange@TransportProtocol@@QEAAXPEAU_WSAPROTOCOL_INFOW@@HH@Z; TransportProtocol::HandleProtocolChange(_WSAPROTOCOL_INFOW *,int,int)
0x18009cc26  inc     edi
0x18009cc28  cmp     edi, 10h
0x18009cc2b  jl      short loc_18009CC07
0x18009cc2d  mov     rcx, rbx; lpMem
0x18009cc30  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18009cc35  mov     ebx, cs:?g_NotifyRt@@3JA; long g_NotifyRt
0x18009cc3b  jmp     short loc_18009CBE3
```
