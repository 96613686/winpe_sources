# CMulticastPacket::CreateData(unsigned __int64,void *,ulong,CMemoryBuffer * *)

- ea: `0x18001c77c`
- end: `0x18001c832`
- name: `?CreateData@CMulticastPacket@@SAK_KPEAXKPEAPEAVCMemoryBuffer@@@Z`
- size: `182`
- prototype: `unsigned int __fastcall(unsigned __int64, void *Src, size_t Size, struct CMemoryBuffer **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000d454`

## callees

- `0x18001c71c`
- `0x18001c77c`
- `0x180023b28`
- `0x180026d3a`
- `0x180026d70`

## import_xrefs

- `WS2_32!__imp_htons` at `0x18001c7d1`
- `WS2_32!__imp_htons` at `0x18001c7d1`

## pseudocode

```c
__int64 __fastcall CMulticastPacket::CreateData(unsigned __int64 a1, void *Src, size_t Size, struct CMemoryBuffer **a4)
{
  size_t v4; // rbp
  unsigned int v8; // edi
  struct CMemoryBuffer *Packet; // rax
  struct CMemoryBuffer *v10; // rsi
  __int64 v11; // rbx

  v4 = (unsigned int)Size;
  v8 = 0;
  Packet = CMulticastPacket::AllocatePacket((int)Size + 13, 3u);
  v10 = Packet;
  if ( Packet )
  {
    v11 = *((_QWORD *)Packet + 5);
    *(_QWORD *)(v11 + 3) = CNetworkAddress::HostToNetworkByteOrder(a1);
    *(_WORD *)(v11 + 11) = htons(v4);
    memmove_0((void *)(v11 + 13), Src, v4);
    if ( g_ErrLibTraceFunctionEx )
      g_ErrLibTraceFunctionEx(0x400000u, L"MCAPConstruct[DATA]: Blk#=%I64u, DataLen=%u", a1, (unsigned int)v4);
    *a4 = v10;
  }
  else
  {
    return 8;
  }
  return v8;
}

```

## disassembly

```asm
0x18001c77c  mov     rax, rsp
0x18001c77f  mov     [rax+8], rbx
0x18001c783  mov     [rax+10h], rbp
0x18001c787  mov     [rax+18h], rsi
0x18001c78b  mov     [rax+20h], rdi
0x18001c78f  push    r12
0x18001c791  push    r14
0x18001c793  push    r15
0x18001c795  sub     rsp, 30h
0x18001c799  mov     ebp, r8d
0x18001c79c  mov     r12, rdx
0x18001c79f  mov     r15, rcx
0x18001c7a2  mov     dl, 3; unsigned __int8
0x18001c7a4  mov     r14, r9
0x18001c7a7  xor     edi, edi
0x18001c7a9  lea     ecx, [rbp+0Dh]; unsigned int
0x18001c7ac  call    ?AllocatePacket@CMulticastPacket@@CAPEAVCMemoryBuffer@@KE@Z; CMulticastPacket::AllocatePacket(ulong,uchar)
0x18001c7b1  mov     rsi, rax
0x18001c7b4  test    rax, rax
0x18001c7b7  jnz     short loc_18001C7BE
0x18001c7b9  lea     edi, [rax+8]
0x18001c7bc  jmp     short loc_18001C811
0x18001c7be  mov     rbx, [rax+28h]
0x18001c7c2  mov     rcx, r15; unsigned __int64
0x18001c7c5  call    ?HostToNetworkByteOrder@CNetworkAddress@@SA_K_K@Z; CNetworkAddress::HostToNetworkByteOrder(unsigned __int64)
0x18001c7ca  movzx   ecx, bp; hostshort
0x18001c7cd  mov     [rbx+3], rax
0x18001c7d1  call    cs:__imp_htons
0x18001c7d7  mov     r8, rbp; Size
0x18001c7da  lea     rcx, [rbx+0Dh]; void *
0x18001c7de  mov     rdx, r12; Src
0x18001c7e1  mov     [rbx+0Bh], ax
0x18001c7e5  call    memmove_0
0x18001c7ea  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001c7f1  test    rax, rax
0x18001c7f4  jz      short loc_18001C80E
0x18001c7f6  mov     r9d, ebp
0x18001c7f9  lea     rdx, aMcapconstructD; "MCAPConstruct[DATA]: Blk#=%I64u, DataLe"...
0x18001c800  mov     r8, r15
0x18001c803  mov     ecx, 400000h
0x18001c808  call    cs:__guard_dispatch_icall_fptr
0x18001c80e  mov     [r14], rsi
0x18001c811  mov     rbx, [rsp+48h+arg_0]
0x18001c816  mov     eax, edi
0x18001c818  mov     rdi, [rsp+48h+arg_18]
0x18001c81d  mov     rbp, [rsp+48h+arg_8]
0x18001c822  mov     rsi, [rsp+48h+arg_10]
0x18001c827  add     rsp, 30h
0x18001c82b  pop     r15
0x18001c82d  pop     r14
0x18001c82f  pop     r12
0x18001c831  retn
```
