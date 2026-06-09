# CMcSePacket::CreateReplyPacket(CTptControlPacket *,CMemoryBuffer * *)

- ea: `0x18001bd40`
- end: `0x18001c0b7`
- name: `?CreateReplyPacket@CMcSePacket@@SAKPEAVCTptControlPacket@@PEAPEAVCMemoryBuffer@@@Z`
- size: `887`
- prototype: `__int64 __fastcall(struct CTptControlPacket *this, struct CMemoryBuffer **)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180008040`

## callees

- `0x180008f4c`
- `0x18001bd40`
- `0x180020350`
- `0x1800209c8`
- `0x180020ab0`
- `0x180020dc8`
- `0x180023b28`
- `0x180025850`
- `0x180026d46`
- `0x180026d70`

## import_xrefs

- `WS2_32!__imp_htonl` at `0x18001bf64`
- `WS2_32!__imp_htonl` at `0x18001bf76`
- `WS2_32!__imp_htonl` at `0x18001bf64`
- `WS2_32!__imp_htonl` at `0x18001bf76`
- `WS2_32!__imp_htons` at `0x18001bf29`
- `WS2_32!__imp_htons` at `0x18001bf3a`
- `WS2_32!__imp_htons` at `0x18001bf29`
- `WS2_32!__imp_htons` at `0x18001bf3a`

## pseudocode

```c
__int64 __fastcall CMcSePacket::CreateReplyPacket(struct CTptControlPacket *this, struct CMemoryBuffer **a2)
{
  struct CMemoryBuffer *v4; // rdi
  const unsigned __int16 *v5; // r8
  unsigned int v6; // r9d
  unsigned int UdpEndpoint; // ebx
  const char *v8; // rdx
  const unsigned __int16 *v9; // r8
  unsigned int v10; // r9d
  const char *v11; // rdx
  const char *v12; // rdx
  const char *v13; // rdx
  const char *v14; // rdx
  const char *v15; // rdx
  struct CMemoryBuffer *v16; // rax
  __int64 v17; // rbx
  struct tagWDS_ENDPOINT *v19; // [rsp+20h] [rbp-140h]
  unsigned __int64 v20; // [rsp+E0h] [rbp-80h] BYREF
  unsigned __int64 v21; // [rsp+E8h] [rbp-78h] BYREF
  _BYTE v22[12]; // [rsp+F0h] [rbp-70h] BYREF
  u_short v23; // [rsp+FCh] [rbp-64h] BYREF
  _BYTE v24[16]; // [rsp+100h] [rbp-60h] BYREF
  int v25; // [rsp+110h] [rbp-50h]
  _BYTE v26[12]; // [rsp+510h] [rbp+3B0h] BYREF
  u_short v27; // [rsp+51Ch] [rbp+3BCh] BYREF
  _BYTE v28[16]; // [rsp+520h] [rbp+3C0h] BYREF
  int v29; // [rsp+530h] [rbp+3D0h]
  u_long v30; // [rsp+970h] [rbp+810h] BYREF
  u_long hostlong; // [rsp+978h] [rbp+818h] BYREF

  v4 = 0;
  memset_0(v26, 0, 0x41Cu);
  memset_0(v22, 0, 0x41Cu);
  v21 = 0;
  v20 = 0;
  hostlong = 0;
  v30 = 0;
  UdpEndpoint = CControlPacket::GetUdpEndpoint(this, L"TpMcAddress", v5, v6, (struct tagWDS_ENDPOINT *)v26);
  if ( ElValidateWin32(UdpEndpoint, v8, "base\\eco\\wds\\transport\\lib\\mcsepacket.cpp", 0x257u)
    || (UdpEndpoint = CControlPacket::GetUdpEndpoint(this, L"TpUniAddress", v9, v10, (struct tagWDS_ENDPOINT *)v22),
        ElValidateWin32(UdpEndpoint, v11, "base\\eco\\wds\\transport\\lib\\mcsepacket.cpp", 0x262u))
    || (UdpEndpoint = CControlPacket::GetULONG64(this, L"ContentSize", 0, 0xFFFFFFFF, &v21),
        ElValidateWin32(UdpEndpoint, v12, "base\\eco\\wds\\transport\\lib\\mcsepacket.cpp", 0x26Du))
    || (UdpEndpoint = CControlPacket::GetULONG64(this, L"TotalBlocks", 0, 0xFFFFFFFF, &v20),
        ElValidateWin32(UdpEndpoint, v13, "base\\eco\\wds\\transport\\lib\\mcsepacket.cpp", 0x278u))
    || (UdpEndpoint = CControlPacket::GetULONG(this, L"BlockSize", 0, 0xFFFFFFFF, &hostlong),
        ElValidateWin32(UdpEndpoint, v14, "base\\eco\\wds\\transport\\lib\\mcsepacket.cpp", 0x283u))
    || (UdpEndpoint = CControlPacket::GetULONG(this, L"SessionId", 0, 0xFFFFFFFF, &v30),
        ElValidateWin32(UdpEndpoint, v15, "base\\eco\\wds\\transport\\lib\\mcsepacket.cpp", 0x28Eu)) )
  {
LABEL_11:
    if ( !UdpEndpoint )
      return UdpEndpoint;
    goto LABEL_12;
  }
  v16 = TptMemoryBufferAllocate(v25 + 63 + v29);
  v4 = v16;
  if ( !v16 )
    return 8;
  v17 = *((_QWORD *)v16 + 5);
  *(_BYTE *)v17 = 2;
  v27 = htons(v27);
  v23 = htons(v23);
  v21 = CNetworkAddress::HostToNetworkByteOrder(v21);
  v20 = CNetworkAddress::HostToNetworkByteOrder(v20);
  hostlong = htonl(hostlong);
  v30 = htonl(v30);
  LODWORD(v19) = v29;
  UdpEndpoint = CMcTpOptions::CreateOptions(
                  (struct _WDSMCTP_OPTIONS *)(v17 + 1),
                  *((_DWORD *)v4 + 12) - 1,
                  8u,
                  1283,
                  v19,
                  v28,
                  1284,
                  v25,
                  v24,
                  517,
                  2,
                  &v27,
                  518,
                  2,
                  &v23,
                  1031,
                  8,
                  &v21,
                  1032,
                  8,
                  &v20,
                  777,
                  4,
                  &hostlong,
                  778,
                  4,
                  &v30);
  if ( !UdpEndpoint )
  {
    *a2 = v4;
    goto LABEL_11;
  }
LABEL_12:
  if ( v4 )
    (*(void (__fastcall **)(struct CMemoryBuffer *))(*(_QWORD *)v4 + 8LL))(v4);
  return UdpEndpoint;
}

```

## disassembly

```asm
0x18001bd40  mov     [rsp-8+arg_0], rbx
0x18001bd45  push    rbp
0x18001bd46  push    rsi
0x18001bd47  push    rdi
0x18001bd48  push    r12
0x18001bd4a  push    r14
0x18001bd4c  lea     rbp, [rsp-7D0h]
0x18001bd54  sub     rsp, 930h
0x18001bd5b  mov     r14, rdx
0x18001bd5e  mov     rsi, rcx
0x18001bd61  mov     ebx, 41Ch
0x18001bd66  lea     rcx, [rbp+7F0h+var_440]; void *
0x18001bd6d  mov     r8d, ebx; Size
0x18001bd70  xor     edx, edx; Val
0x18001bd72  xor     edi, edi
0x18001bd74  call    memset_0
0x18001bd79  mov     r8d, ebx; Size
0x18001bd7c  lea     rcx, [rbp+7F0h+var_860]; void *
0x18001bd80  xor     edx, edx; Val
0x18001bd82  call    memset_0
0x18001bd87  and     [rbp+7F0h+var_868], rdi
0x18001bd8b  lea     rax, [rbp+7F0h+var_440]
0x18001bd92  and     [rbp+7F0h+var_870], rdi
0x18001bd96  lea     rdx, aTpmcaddress; "TpMcAddress"
0x18001bd9d  and     [rbp+7F0h+hostlong], edi
0x18001bda3  mov     rcx, rsi; this
0x18001bda6  and     [rbp+7F0h+arg_10], edi
0x18001bdac  mov     [rsp+950h+var_930], rax; struct tagWDS_ENDPOINT *
0x18001bdb1  call    ?GetUdpEndpoint@CControlPacket@@QEAAKPEBG0KPEAUtagWDS_ENDPOINT@@@Z; CControlPacket::GetUdpEndpoint(ushort const *,ushort const *,ulong,tagWDS_ENDPOINT *)
0x18001bdb6  lea     r12, aBaseEcoWdsTran_25; "base\\eco\\wds\\transport\\lib\\mcsepac"...
0x18001bdbd  mov     r9d, 257h; unsigned int
0x18001bdc3  mov     r8, r12; char *
0x18001bdc6  mov     ecx, eax; unsigned int
0x18001bdc8  mov     ebx, eax
0x18001bdca  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001bdcf  test    eax, eax
0x18001bdd1  jnz     loc_18001C085
0x18001bdd7  lea     rax, [rbp+7F0h+var_860]
0x18001bddb  mov     rcx, rsi; this
0x18001bdde  lea     rdx, aTpuniaddress; "TpUniAddress"
0x18001bde5  mov     [rsp+950h+var_930], rax; struct tagWDS_ENDPOINT *
0x18001bdea  call    ?GetUdpEndpoint@CControlPacket@@QEAAKPEBG0KPEAUtagWDS_ENDPOINT@@@Z; CControlPacket::GetUdpEndpoint(ushort const *,ushort const *,ulong,tagWDS_ENDPOINT *)
0x18001bdef  mov     r9d, 262h; unsigned int
0x18001bdf5  mov     r8, r12; char *
0x18001bdf8  mov     ecx, eax; unsigned int
0x18001bdfa  mov     ebx, eax
0x18001bdfc  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001be01  test    eax, eax
0x18001be03  jnz     loc_18001C085
0x18001be09  lea     rax, [rbp+7F0h+var_868]
0x18001be0d  or      r9d, 0FFFFFFFFh; unsigned int
0x18001be11  xor     r8d, r8d; unsigned __int16 *
0x18001be14  mov     [rsp+950h+var_930], rax; unsigned __int64 *
0x18001be19  lea     rdx, aContentsize; "ContentSize"
0x18001be20  mov     rcx, rsi; this
0x18001be23  call    ?GetULONG64@CControlPacket@@QEAAKPEBG0KPEA_K@Z; CControlPacket::GetULONG64(ushort const *,ushort const *,ulong,unsigned __int64 *)
0x18001be28  mov     r9d, 26Dh; unsigned int
0x18001be2e  mov     r8, r12; char *
0x18001be31  mov     ecx, eax; unsigned int
0x18001be33  mov     ebx, eax
0x18001be35  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001be3a  test    eax, eax
0x18001be3c  jnz     loc_18001C085
0x18001be42  lea     rax, [rbp+7F0h+var_870]
0x18001be46  or      r9d, 0FFFFFFFFh; unsigned int
0x18001be4a  xor     r8d, r8d; unsigned __int16 *
0x18001be4d  mov     [rsp+950h+var_930], rax; unsigned __int64 *
0x18001be52  lea     rdx, aTotalblocks; "TotalBlocks"
0x18001be59  mov     rcx, rsi; this
0x18001be5c  call    ?GetULONG64@CControlPacket@@QEAAKPEBG0KPEA_K@Z; CControlPacket::GetULONG64(ushort const *,ushort const *,ulong,unsigned __int64 *)
0x18001be61  mov     r9d, 278h; unsigned int
0x18001be67  mov     r8, r12; char *
0x18001be6a  mov     ecx, eax; unsigned int
0x18001be6c  mov     ebx, eax
0x18001be6e  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001be73  test    eax, eax
0x18001be75  jnz     loc_18001C085
0x18001be7b  lea     rax, [rbp+7F0h+hostlong]
0x18001be82  or      r9d, 0FFFFFFFFh; unsigned int
0x18001be86  xor     r8d, r8d; unsigned __int16 *
0x18001be89  mov     [rsp+950h+var_930], rax; unsigned int *
0x18001be8e  lea     rdx, aBlocksize; "BlockSize"
0x18001be95  mov     rcx, rsi; this
0x18001be98  call    ?GetULONG@CControlPacket@@QEAAKPEBG0KPEAK@Z; CControlPacket::GetULONG(ushort const *,ushort const *,ulong,ulong *)
0x18001be9d  mov     r9d, 283h; unsigned int
0x18001bea3  mov     r8, r12; char *
0x18001bea6  mov     ecx, eax; unsigned int
0x18001bea8  mov     ebx, eax
0x18001beaa  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001beaf  test    eax, eax
0x18001beb1  jnz     loc_18001C085
0x18001beb7  lea     rax, [rbp+7F0h+arg_10]
0x18001bebe  or      r9d, 0FFFFFFFFh; unsigned int
0x18001bec2  xor     r8d, r8d; unsigned __int16 *
0x18001bec5  mov     [rsp+950h+var_930], rax; unsigned int *
0x18001beca  lea     rdx, aSessionid; "SessionId"
0x18001bed1  mov     rcx, rsi; this
0x18001bed4  call    ?GetULONG@CControlPacket@@QEAAKPEBG0KPEAK@Z; CControlPacket::GetULONG(ushort const *,ushort const *,ulong,ulong *)
0x18001bed9  mov     r9d, 28Eh; unsigned int
0x18001bedf  mov     r8, r12; char *
0x18001bee2  mov     ecx, eax; unsigned int
0x18001bee4  mov     ebx, eax
0x18001bee6  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001beeb  test    eax, eax
0x18001beed  jnz     loc_18001C085
0x18001bef3  mov     eax, [rbp+7F0h+var_840]
0x18001bef6  mov     ecx, [rbp+7F0h+var_420]
0x18001befc  add     eax, 3Fh ; '?'
0x18001beff  add     ecx, eax; unsigned int
0x18001bf01  call    ?TptMemoryBufferAllocate@@YAPEAVCMemoryBuffer@@K@Z; TptMemoryBufferAllocate(ulong)
0x18001bf06  mov     rdi, rax
0x18001bf09  test    rax, rax
0x18001bf0c  jnz     short loc_18001BF16
0x18001bf0e  lea     ebx, [rax+8]
0x18001bf11  jmp     loc_18001C09E
0x18001bf16  mov     rbx, [rax+28h]
0x18001bf1a  mov     esi, 2
0x18001bf1f  mov     [rbx], sil
0x18001bf22  movzx   ecx, [rbp+7F0h+var_434]; hostshort
0x18001bf29  call    cs:__imp_htons
0x18001bf2f  movzx   ecx, [rbp+7F0h+var_854]; hostshort
0x18001bf33  mov     [rbp+7F0h+var_434], ax
0x18001bf3a  call    cs:__imp_htons
0x18001bf40  mov     rcx, [rbp+7F0h+var_868]; unsigned __int64
0x18001bf44  mov     [rbp+7F0h+var_854], ax
0x18001bf48  call    ?HostToNetworkByteOrder@CNetworkAddress@@SA_K_K@Z; CNetworkAddress::HostToNetworkByteOrder(unsigned __int64)
0x18001bf4d  mov     rcx, [rbp+7F0h+var_870]; unsigned __int64
0x18001bf51  mov     [rbp+7F0h+var_868], rax
0x18001bf55  call    ?HostToNetworkByteOrder@CNetworkAddress@@SA_K_K@Z; CNetworkAddress::HostToNetworkByteOrder(unsigned __int64)
0x18001bf5a  mov     ecx, [rbp+7F0h+hostlong]; hostlong
0x18001bf60  mov     [rbp+7F0h+var_870], rax
0x18001bf64  call    cs:__imp_htonl
0x18001bf6a  mov     ecx, [rbp+7F0h+arg_10]; hostlong
0x18001bf70  mov     [rbp+7F0h+hostlong], eax
0x18001bf76  call    cs:__imp_htonl
0x18001bf7c  mov     [rbp+7F0h+arg_10], eax
0x18001bf82  lea     r8d, [rsi+2]
0x18001bf86  mov     edx, [rdi+30h]
0x18001bf89  mov     r9d, 503h
0x18001bf8f  lea     rax, [rbp+7F0h+arg_10]
0x18001bf96  dec     edx; unsigned int
0x18001bf98  mov     [rsp+950h+var_880], rax
0x18001bfa0  lea     rcx, [rbx+1]; struct _WDSMCTP_OPTIONS *
0x18001bfa4  mov     [rsp+950h+var_888], r8
0x18001bfac  lea     ebx, [rsi+6]
0x18001bfaf  mov     [rsp+950h+var_890], 30Ah
0x18001bfba  lea     rax, [rbp+7F0h+hostlong]
0x18001bfc1  mov     [rsp+950h+var_898], rax
0x18001bfc9  lea     rax, [rbp+7F0h+var_870]
0x18001bfcd  mov     [rsp+950h+var_8A0], r8
0x18001bfd5  mov     r8d, ebx; unsigned int
0x18001bfd8  mov     [rsp+950h+var_8A8], 309h
0x18001bfe3  mov     [rsp+950h+var_8B0], rax
0x18001bfeb  lea     rax, [rbp+7F0h+var_868]
0x18001bfef  mov     [rsp+950h+var_8B8], rbx
0x18001bff7  mov     [rsp+950h+var_8C0], 408h
0x18001c002  mov     [rsp+950h+var_8C8], rax
0x18001c00a  lea     rax, [rbp+7F0h+var_854]
0x18001c00e  mov     [rsp+950h+var_8D0], rbx
0x18001c016  mov     [rsp+950h+var_8D8], 407h
0x18001c01e  mov     [rsp+950h+var_8E0], rax
0x18001c023  lea     rax, [rbp+7F0h+var_434]
0x18001c02a  mov     [rsp+950h+var_8E8], rsi
0x18001c02f  mov     [rsp+950h+var_8F0], 206h
0x18001c037  mov     [rsp+950h+var_8F8], rax
0x18001c03c  lea     rax, [rbp+7F0h+var_850]
0x18001c040  mov     [rsp+950h+var_900], rsi
0x18001c045  mov     [rsp+950h+var_908], 205h
0x18001c04d  mov     [rsp+950h+var_910], rax
0x18001c052  mov     eax, [rbp+7F0h+var_840]
0x18001c055  mov     [rsp+950h+var_918], eax
0x18001c059  lea     rax, [rbp+7F0h+var_430]
0x18001c060  mov     [rsp+950h+var_920], 504h
0x18001c068  mov     [rsp+950h+var_928], rax
0x18001c06d  mov     eax, [rbp+7F0h+var_420]
0x18001c073  mov     dword ptr [rsp+950h+var_930], eax
0x18001c077  call    ?CreateOptions@CMcTpOptions@@SAKPEAU_WDSMCTP_OPTIONS@@KKZZ; CMcTpOptions::CreateOptions(_WDSMCTP_OPTIONS *,ulong,ulong,...)
0x18001c07c  mov     ebx, eax
0x18001c07e  test    eax, eax
0x18001c080  jnz     short loc_18001C089
0x18001c082  mov     [r14], rdi
0x18001c085  test    ebx, ebx
0x18001c087  jz      short loc_18001C09E
0x18001c089  test    rdi, rdi
0x18001c08c  jz      short loc_18001C09E
0x18001c08e  mov     rax, [rdi]
0x18001c091  mov     rcx, rdi
0x18001c094  mov     rax, [rax+8]
0x18001c098  call    cs:__guard_dispatch_icall_fptr
0x18001c09e  mov     eax, ebx
0x18001c0a0  mov     rbx, [rsp+950h+arg_0]
0x18001c0a8  add     rsp, 930h
0x18001c0af  pop     r14
0x18001c0b1  pop     r12
0x18001c0b3  pop     rdi
0x18001c0b4  pop     rsi
0x18001c0b5  pop     rbp
0x18001c0b6  retn
```
