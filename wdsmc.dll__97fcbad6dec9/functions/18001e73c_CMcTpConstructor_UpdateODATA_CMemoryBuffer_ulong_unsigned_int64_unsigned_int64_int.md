# CMcTpConstructor::UpdateODATA(CMemoryBuffer *,ulong,unsigned __int64,unsigned __int64,int *)

- ea: `0x18001e73c`
- end: `0x18001e919`
- name: `?UpdateODATA@CMcTpConstructor@@QEAAKPEAVCMemoryBuffer@@K_K1PEAH@Z`
- size: `477`
- prototype: `unsigned int __fastcall(CMcTpConstructor *__hidden this, struct CMemoryBuffer *, u_long hostlong, unsigned __int64, unsigned __int64, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180012c98`

## callees

- `0x18001d4f4`
- `0x18001e73c`
- `0x18001e920`
- `0x180023af0`
- `0x180023b28`
- `0x1800247d4`
- `0x180025850`

## import_xrefs

- `WS2_32!__imp_htonl` at `0x18001e89f`
- `WS2_32!__imp_htonl` at `0x18001e89f`
- `WS2_32!__imp_ntohl` at `0x18001e822`
- `WS2_32!__imp_ntohl` at `0x18001e822`
- `WS2_32!__imp_ntohs` at `0x18001e7bb`
- `WS2_32!__imp_ntohs` at `0x18001e7c9`
- `WS2_32!__imp_ntohs` at `0x18001e7e9`
- `WS2_32!__imp_ntohs` at `0x18001e802`
- `WS2_32!__imp_ntohs` at `0x18001e7bb`
- `WS2_32!__imp_ntohs` at `0x18001e7c9`
- `WS2_32!__imp_ntohs` at `0x18001e7e9`
- `WS2_32!__imp_ntohs` at `0x18001e802`

## pseudocode

```c
__int64 __fastcall CMcTpConstructor::UpdateODATA(
        CMcTpConstructor *this,
        struct CMemoryBuffer *a2,
        u_long hostlong,
        unsigned __int64 a4,
        unsigned __int64 a5,
        int *a6)
{
  unsigned int PacketPtr; // ebx
  __int64 v11; // r14
  const char *v12; // rdx
  struct _WDSMCTP_PK_ODATA *v13; // rdi
  __int64 v14; // rsi
  const char *v15; // rdx
  unsigned int v16; // r9d
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // rdx
  int *v20; // rax
  unsigned __int64 v21; // rax
  unsigned __int64 v22; // rcx
  const char *v23; // rdx
  LONGLONG v25; // [rsp+60h] [rbp+8h]
  struct _WDSMCTP_PK_ODATA *v26; // [rsp+68h] [rbp+10h] BYREF

  v26 = 0;
  v25 = CStopwatch::CurrentMs((CMcTpConstructor *)((char *)this + 104));
  if ( *((_DWORD *)a2 + 12) >= 0x2Bu )
  {
    v11 = *((_QWORD *)a2 + 5);
    PacketPtr = CMcTpConstructor::GetPacketPtr(a2, &v26, 0);
    if ( !ElValidateWin32(PacketPtr, v12, "base\\eco\\wds\\transport\\lib\\mctpconstructor.cpp", 0xB99u) )
    {
      v13 = v26;
      v14 = ntohs(*(_WORD *)((char *)v26 + 33));
      if ( ntohs(*(_WORD *)((char *)v13 + v14 + 35)) == 1 )
      {
        if ( ntohs(*(_WORD *)((char *)v13 + v14 + 37)) == 1030 && ntohs(*(_WORD *)((char *)v13 + v14 + 39)) == 8 )
        {
          if ( *(_BYTE *)(v11 + 2) != 0xFF
            && *((_BYTE *)v13 + 4) == 6
            && ntohl(*(_DWORD *)((char *)v13 + 13)) == hostlong
            && (v17 = CNetworkAddress::NetworkToHostByteOrder(*(_QWORD *)((char *)v13 + v14 + 41)), v17 == a5)
            && CNetworkAddress::NetworkToHostByteOrder(*(_QWORD *)((char *)v13 + 25)) == a4 )
          {
            v18 = CNetworkAddress::NetworkToHostByteOrder(*(_QWORD *)((char *)v13 + 5));
            v19 = v25;
            if ( v25 - v18 <= 1 )
            {
              *a6 = 1;
              return PacketPtr;
            }
          }
          else
          {
            v19 = v25;
          }
          v20 = a6;
          *((_BYTE *)v13 + 4) = 6;
          *v20 = 0;
          *(_QWORD *)((char *)v13 + 5) = CNetworkAddress::HostToNetworkByteOrder(v19);
          *(_DWORD *)((char *)v13 + 13) = htonl(hostlong);
          v21 = CNetworkAddress::HostToNetworkByteOrder(a4);
          v22 = a5;
          *(_QWORD *)((char *)v13 + 25) = v21;
          *(_QWORD *)((char *)v13 + v14 + 41) = CNetworkAddress::HostToNetworkByteOrder(v22);
          PacketPtr = CMcTpConstructor::ServerSecurePacket(this, a2);
          ElValidateWin32(PacketPtr, v23, "base\\eco\\wds\\transport\\lib\\mctpconstructor.cpp", 0xBC5u);
          return PacketPtr;
        }
        v16 = 2982;
      }
      else
      {
        v16 = 2974;
      }
      return ElValidateWin32(0xDu, v15, "base\\eco\\wds\\transport\\lib\\mctpconstructor.cpp", v16);
    }
  }
  else
  {
    return 13;
  }
  return PacketPtr;
}

```

## disassembly

```asm
0x18001e73c  mov     [rsp+arg_10], rbx
0x18001e741  push    rbp
0x18001e742  push    rsi
0x18001e743  push    rdi
0x18001e744  push    r12
0x18001e746  push    r13
0x18001e748  push    r14
0x18001e74a  push    r15
0x18001e74c  sub     rsp, 20h
0x18001e750  and     [rsp+58h+arg_8], 0
0x18001e756  mov     r15, rcx
0x18001e759  add     rcx, 68h ; 'h'; this
0x18001e75d  mov     r12, r9
0x18001e760  mov     r13d, r8d
0x18001e763  mov     rbp, rdx
0x18001e766  call    ?CurrentMs@CStopwatch@@QEAA_KXZ; CStopwatch::CurrentMs(void)
0x18001e76b  cmp     dword ptr [rbp+30h], 2Bh ; '+'
0x18001e76f  mov     [rsp+58h+arg_0], rax
0x18001e774  jnb     short loc_18001E780
0x18001e776  mov     ebx, 0Dh
0x18001e77b  jmp     loc_18001E902
0x18001e780  mov     r14, [rbp+28h]
0x18001e784  lea     rdx, [rsp+58h+arg_8]; struct _WDSMCTP_PK_ODATA **
0x18001e789  xor     r8d, r8d; unsigned int *
0x18001e78c  mov     rcx, rbp; struct CMemoryBuffer *
0x18001e78f  call    ?GetPacketPtr@CMcTpConstructor@@SAKPEAVCMemoryBuffer@@PEAPEAU_WDSMCTP_PK_ODATA@@PEAK@Z; CMcTpConstructor::GetPacketPtr(CMemoryBuffer *,_WDSMCTP_PK_ODATA * *,ulong *)
0x18001e794  mov     r9d, 0B99h; unsigned int
0x18001e79a  lea     r8, aBaseEcoWdsTran_17; "base\\eco\\wds\\transport\\lib\\mctpcon"...
0x18001e7a1  mov     ecx, eax; unsigned int
0x18001e7a3  mov     ebx, eax
0x18001e7a5  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001e7aa  test    eax, eax
0x18001e7ac  jnz     loc_18001E902
0x18001e7b2  mov     rdi, [rsp+58h+arg_8]
0x18001e7b7  movzx   ecx, word ptr [rdi+21h]; netshort
0x18001e7bb  call    cs:__imp_ntohs
0x18001e7c1  movzx   esi, ax
0x18001e7c4  movzx   ecx, word ptr [rsi+rdi+23h]; netshort
0x18001e7c9  call    cs:__imp_ntohs
0x18001e7cf  mov     ecx, 1
0x18001e7d4  cmp     ax, cx
0x18001e7d7  jz      short loc_18001E7E4
0x18001e7d9  mov     r9d, 0B9Eh
0x18001e7df  jmp     loc_18001E8EF
0x18001e7e4  movzx   ecx, word ptr [rsi+rdi+25h]; netshort
0x18001e7e9  call    cs:__imp_ntohs
0x18001e7ef  mov     ecx, 406h
0x18001e7f4  cmp     ax, cx
0x18001e7f7  jnz     loc_18001E8E9
0x18001e7fd  movzx   ecx, word ptr [rsi+rdi+27h]; netshort
0x18001e802  call    cs:__imp_ntohs
0x18001e808  cmp     ax, 8
0x18001e80c  jnz     loc_18001E8E9
0x18001e812  cmp     byte ptr [r14+2], 0FFh
0x18001e817  jz      short loc_18001E87C
0x18001e819  cmp     byte ptr [rdi+4], 6
0x18001e81d  jnz     short loc_18001E87C
0x18001e81f  mov     ecx, [rdi+0Dh]; netlong
0x18001e822  call    cs:__imp_ntohl
0x18001e828  cmp     eax, r13d
0x18001e82b  jnz     short loc_18001E87C
0x18001e82d  mov     rcx, [rsi+rdi+29h]; unsigned __int64
0x18001e832  call    ?NetworkToHostByteOrder@CNetworkAddress@@SA_K_K@Z; CNetworkAddress::NetworkToHostByteOrder(unsigned __int64)
0x18001e837  cmp     rax, [rsp+58h+arg_20]
0x18001e83f  jnz     short loc_18001E87C
0x18001e841  mov     rcx, [rdi+19h]; unsigned __int64
0x18001e845  call    ?NetworkToHostByteOrder@CNetworkAddress@@SA_K_K@Z; CNetworkAddress::NetworkToHostByteOrder(unsigned __int64)
0x18001e84a  cmp     rax, r12
0x18001e84d  jnz     short loc_18001E87C
0x18001e84f  mov     rcx, [rdi+5]; unsigned __int64
0x18001e853  call    ?NetworkToHostByteOrder@CNetworkAddress@@SA_K_K@Z; CNetworkAddress::NetworkToHostByteOrder(unsigned __int64)
0x18001e858  mov     rdx, [rsp+58h+arg_0]
0x18001e85d  mov     rcx, rdx
0x18001e860  sub     rcx, rax
0x18001e863  cmp     rcx, 1
0x18001e867  ja      short loc_18001E881
0x18001e869  mov     rax, [rsp+58h+arg_28]
0x18001e871  mov     dword ptr [rax], 1
0x18001e877  jmp     loc_18001E902
0x18001e87c  mov     rdx, [rsp+58h+arg_0]
0x18001e881  mov     rax, [rsp+58h+arg_28]
0x18001e889  mov     rcx, rdx; unsigned __int64
0x18001e88c  mov     byte ptr [rdi+4], 6
0x18001e890  and     dword ptr [rax], 0
0x18001e893  call    ?HostToNetworkByteOrder@CNetworkAddress@@SA_K_K@Z; CNetworkAddress::HostToNetworkByteOrder(unsigned __int64)
0x18001e898  mov     ecx, r13d; hostlong
0x18001e89b  mov     [rdi+5], rax
0x18001e89f  call    cs:__imp_htonl
0x18001e8a5  mov     rcx, r12; unsigned __int64
0x18001e8a8  mov     [rdi+0Dh], eax
0x18001e8ab  call    ?HostToNetworkByteOrder@CNetworkAddress@@SA_K_K@Z; CNetworkAddress::HostToNetworkByteOrder(unsigned __int64)
0x18001e8b0  mov     rcx, [rsp+58h+arg_20]; unsigned __int64
0x18001e8b8  mov     [rdi+19h], rax
0x18001e8bc  call    ?HostToNetworkByteOrder@CNetworkAddress@@SA_K_K@Z; CNetworkAddress::HostToNetworkByteOrder(unsigned __int64)
0x18001e8c1  mov     rdx, rbp; struct CMemoryBuffer *
0x18001e8c4  mov     [rsi+rdi+29h], rax
0x18001e8c9  mov     rcx, r15; this
0x18001e8cc  call    ?ServerSecurePacket@CMcTpConstructor@@AEAAKPEAVCMemoryBuffer@@@Z; CMcTpConstructor::ServerSecurePacket(CMemoryBuffer *)
0x18001e8d1  mov     r9d, 0BC5h; unsigned int
0x18001e8d7  lea     r8, aBaseEcoWdsTran_17; "base\\eco\\wds\\transport\\lib\\mctpcon"...
0x18001e8de  mov     ecx, eax; unsigned int
0x18001e8e0  mov     ebx, eax
0x18001e8e2  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001e8e7  jmp     short loc_18001E902
0x18001e8e9  mov     r9d, 0BA6h; unsigned int
0x18001e8ef  lea     r8, aBaseEcoWdsTran_17; "base\\eco\\wds\\transport\\lib\\mctpcon"...
0x18001e8f6  mov     ecx, 0Dh; unsigned int
0x18001e8fb  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001e900  mov     ebx, eax
0x18001e902  mov     eax, ebx
0x18001e904  mov     rbx, [rsp+58h+arg_10]
0x18001e909  add     rsp, 20h
0x18001e90d  pop     r15
0x18001e90f  pop     r14
0x18001e911  pop     r13
0x18001e913  pop     r12
0x18001e915  pop     rdi
0x18001e916  pop     rsi
0x18001e917  pop     rbp
0x18001e918  retn
```
