# CMcTpConstructor::CreateSPM(ulong,unsigned __int64,ushort,ushort,unsigned __int64,unsigned __int64,ushort,CMemoryBuffer * *,ulong,...)

- ea: `0x18001d8a8`
- end: `0x18001daaa`
- name: `?CreateSPM@CMcTpConstructor@@QEAAKK_KGG00GPEAPEAVCMemoryBuffer@@KZZ`
- size: `514`
- prototype: `unsigned int(CMcTpConstructor *__hidden this, u_long hostlong, unsigned __int64, unsigned __int16, unsigned __int16, unsigned __int64, unsigned __int64, unsigned __int16, struct CMemoryBuffer **, unsigned int, ...)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800112f4`

## callees

- `0x180008f4c`
- `0x18001d4f4`
- `0x18001d8a8`
- `0x180020258`
- `0x180023b28`
- `0x1800247d4`
- `0x180025850`
- `0x180026d70`

## import_xrefs

- `WS2_32!__imp_htonl` at `0x18001d93c`
- `WS2_32!__imp_htonl` at `0x18001d992`
- `WS2_32!__imp_htonl` at `0x18001d93c`
- `WS2_32!__imp_htonl` at `0x18001d992`
- `WS2_32!__imp_htons` at `0x18001d9a0`
- `WS2_32!__imp_htons` at `0x18001d9b3`
- `WS2_32!__imp_htons` at `0x18001d9eb`
- `WS2_32!__imp_htons` at `0x18001d9a0`
- `WS2_32!__imp_htons` at `0x18001d9b3`
- `WS2_32!__imp_htons` at `0x18001d9eb`

## pseudocode

```c
__int64 CMcTpConstructor::CreateSPM(
        CMcTpConstructor *this,
        u_long hostlong,
        unsigned __int64 a3,
        u_short a4,
        u_short a5,
        unsigned __int64 a6,
        unsigned __int64 a7,
        u_short a8,
        struct CMemoryBuffer **a9,
        unsigned int a10,
        ...)
{
  va_list v12; // rcx
  int v15; // r10d
  __int64 v16; // rdx
  unsigned int v17; // edi
  unsigned int Options; // edi
  struct CMemoryBuffer *v19; // rax
  struct CMemoryBuffer *v20; // rbx
  _WORD *v21; // rax
  __int64 v22; // r14
  u_long v23; // eax
  LONGLONG v24; // rax
  const char *v25; // rdx
  va_list va; // [rsp+110h] [rbp+58h] BYREF

  va_start(va, a10);
  va_copy(v12, va);
  v15 = 2;
  if ( a10 )
  {
    v16 = a10;
    do
    {
      v15 += *((_DWORD *)v12 + 2) + 4;
      v12 += 24;
      --v16;
    }
    while ( v16 );
  }
  v17 = v15 + *((_DWORD *)this + 25) + 47;
  if ( v17 <= 0xFFFF )
  {
    v19 = TptMemoryBufferAllocate(v17);
    v20 = v19;
    if ( v19 )
    {
      v21 = (_WORD *)*((_QWORD *)v19 + 5);
      *v21 = 17495;
      *(_WORD *)((char *)v21 + 3) = 0;
      v22 = *((_QWORD *)v20 + 5) + *((unsigned int *)this + 25);
      v23 = htonl(*((_DWORD *)this + 1));
      *(_BYTE *)(v22 + 4) = 1;
      *(_DWORD *)v22 = v23;
      v24 = CStopwatch::CurrentMs((CMcTpConstructor *)((char *)this + 104));
      *(_QWORD *)(v22 + 5) = CNetworkAddress::HostToNetworkByteOrder(v24);
      Options = CMcTpOptions::CreateOptions(
                  a10,
                  va,
                  (struct _WDSMCTP_OPTIONS *)(v22 + 47),
                  v17 - *((_DWORD *)this + 25) - 47);
      if ( Options )
        goto LABEL_14;
      *(_QWORD *)(v22 + 13) = CNetworkAddress::HostToNetworkByteOrder(a3);
      *(_DWORD *)(v22 + 21) = htonl(hostlong);
      *(_WORD *)(v22 + 25) = htons(a4);
      *(_WORD *)(v22 + 27) = htons(a5);
      *(_QWORD *)(v22 + 29) = CNetworkAddress::HostToNetworkByteOrder(a6);
      *(_QWORD *)(v22 + 37) = CNetworkAddress::HostToNetworkByteOrder(a7);
      *(_WORD *)(v22 + 45) = htons(a8);
      Options = CMcTpConstructor::ServerSecurePacket(this, v20);
      if ( !ElValidateWin32(Options, v25, "base\\eco\\wds\\transport\\lib\\mctpconstructor.cpp", 0x8FFu) )
      {
        if ( g_ErrLibTraceFunctionEx )
          g_ErrLibTraceFunctionEx(
            0x400000u,
            L"MCTPConstruct[SPM]: Session=0x%x, Client=0x%x, Seq#=%I64u, MinNACKBO=%u, MaxNACKBO=%u, Trail#=%I64u, Lead#=%I64u, RTT=%ums",
            *((unsigned int *)this + 1),
            hostlong,
            a3,
            a4,
            a5,
            a6,
            a7,
            a8);
        *a9 = v20;
      }
      if ( Options )
LABEL_14:
        (*(void (__fastcall **)(struct CMemoryBuffer *))(*(_QWORD *)v20 + 8LL))(v20);
    }
    else
    {
      return 8;
    }
  }
  else
  {
    return 111;
  }
  return Options;
}

```

## disassembly

```asm
0x18001d8a8  mov     rax, rsp
0x18001d8ab  push    rbx
0x18001d8ac  push    rbp
0x18001d8ad  push    rsi
0x18001d8ae  push    rdi
0x18001d8af  push    r12
0x18001d8b1  push    r13
0x18001d8b3  push    r14
0x18001d8b5  push    r15
0x18001d8b7  sub     rsp, 78h
0x18001d8bb  mov     ebp, [rax+50h]
0x18001d8be  xor     r14d, r14d
0x18001d8c1  mov     rsi, rcx
0x18001d8c4  movzx   r15d, r9w
0x18001d8c8  lea     rcx, [rax+58h]
0x18001d8cc  mov     r12, r8
0x18001d8cf  mov     r13d, edx
0x18001d8d2  lea     r10d, [r14+2]
0x18001d8d6  test    ebp, ebp
0x18001d8d8  jz      short loc_18001D8EE
0x18001d8da  mov     edx, ebp
0x18001d8dc  add     r10d, 4
0x18001d8e0  add     r10d, [rcx+8]
0x18001d8e4  lea     rcx, [rcx+18h]
0x18001d8e8  sub     rdx, 1
0x18001d8ec  jnz     short loc_18001D8DC
0x18001d8ee  mov     edi, [rsi+64h]
0x18001d8f1  add     edi, 2Fh ; '/'
0x18001d8f4  add     edi, r10d
0x18001d8f7  cmp     edi, 0FFFFh
0x18001d8fd  jbe     short loc_18001D909
0x18001d8ff  mov     edi, 6Fh ; 'o'
0x18001d904  jmp     loc_18001DA97
0x18001d909  mov     ecx, edi; unsigned int
0x18001d90b  call    ?TptMemoryBufferAllocate@@YAPEAVCMemoryBuffer@@K@Z; TptMemoryBufferAllocate(ulong)
0x18001d910  mov     rbx, rax
0x18001d913  test    rax, rax
0x18001d916  jnz     short loc_18001D920
0x18001d918  lea     edi, [rax+8]
0x18001d91b  jmp     loc_18001DA97
0x18001d920  mov     rax, [rax+28h]
0x18001d924  mov     ecx, 4457h
0x18001d929  mov     [rax], cx
0x18001d92c  mov     [rax+3], r14w
0x18001d931  mov     r14d, [rsi+64h]
0x18001d935  mov     ecx, [rsi+4]; hostlong
0x18001d938  add     r14, [rbx+28h]
0x18001d93c  call    cs:__imp_htonl
0x18001d942  lea     rcx, [rsi+68h]; this
0x18001d946  mov     byte ptr [r14+4], 1
0x18001d94b  mov     [r14], eax
0x18001d94e  call    ?CurrentMs@CStopwatch@@QEAA_KXZ; CStopwatch::CurrentMs(void)
0x18001d953  mov     rcx, rax; unsigned __int64
0x18001d956  call    ?HostToNetworkByteOrder@CNetworkAddress@@SA_K_K@Z; CNetworkAddress::HostToNetworkByteOrder(unsigned __int64)
0x18001d95b  mov     [r14+5], rax
0x18001d95f  lea     r8, [r14+2Fh]; struct _WDSMCTP_OPTIONS *
0x18001d963  sub     edi, [rsi+64h]
0x18001d966  lea     rdx, [rsp+0B8h+arg_50]; char *
0x18001d96e  mov     ecx, ebp; unsigned int
0x18001d970  lea     r9d, [rdi-2Fh]; unsigned int
0x18001d974  call    ?CreateOptions@CMcTpOptions@@SAKKPEADPEAU_WDSMCTP_OPTIONS@@K@Z; CMcTpOptions::CreateOptions(ulong,char *,_WDSMCTP_OPTIONS *,ulong)
0x18001d979  mov     edi, eax
0x18001d97b  test    eax, eax
0x18001d97d  jnz     loc_18001DA87
0x18001d983  mov     rcx, r12; unsigned __int64
0x18001d986  call    ?HostToNetworkByteOrder@CNetworkAddress@@SA_K_K@Z; CNetworkAddress::HostToNetworkByteOrder(unsigned __int64)
0x18001d98b  mov     ecx, r13d; hostlong
0x18001d98e  mov     [r14+0Dh], rax
0x18001d992  call    cs:__imp_htonl
0x18001d998  movzx   ecx, r15w; hostshort
0x18001d99c  mov     [r14+15h], eax
0x18001d9a0  call    cs:__imp_htons
0x18001d9a6  movzx   ecx, [rsp+0B8h+arg_20]; hostshort
0x18001d9ae  mov     [r14+19h], ax
0x18001d9b3  call    cs:__imp_htons
0x18001d9b9  mov     rbp, [rsp+0B8h+arg_28]
0x18001d9c1  mov     rcx, rbp; unsigned __int64
0x18001d9c4  mov     [r14+1Bh], ax
0x18001d9c9  call    ?HostToNetworkByteOrder@CNetworkAddress@@SA_K_K@Z; CNetworkAddress::HostToNetworkByteOrder(unsigned __int64)
0x18001d9ce  mov     rcx, [rsp+0B8h+arg_30]; unsigned __int64
0x18001d9d6  mov     [r14+1Dh], rax
0x18001d9da  call    ?HostToNetworkByteOrder@CNetworkAddress@@SA_K_K@Z; CNetworkAddress::HostToNetworkByteOrder(unsigned __int64)
0x18001d9df  movzx   ecx, [rsp+0B8h+arg_38]; hostshort
0x18001d9e7  mov     [r14+25h], rax
0x18001d9eb  call    cs:__imp_htons
0x18001d9f1  mov     rdx, rbx; struct CMemoryBuffer *
0x18001d9f4  mov     rcx, rsi; this
0x18001d9f7  mov     [r14+2Dh], ax
0x18001d9fc  call    ?ServerSecurePacket@CMcTpConstructor@@AEAAKPEAVCMemoryBuffer@@@Z; CMcTpConstructor::ServerSecurePacket(CMemoryBuffer *)
0x18001da01  mov     r9d, 8FFh; unsigned int
0x18001da07  lea     r8, aBaseEcoWdsTran_17; "base\\eco\\wds\\transport\\lib\\mctpcon"...
0x18001da0e  mov     ecx, eax; unsigned int
0x18001da10  mov     edi, eax
0x18001da12  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001da17  test    eax, eax
0x18001da19  jnz     short loc_18001DA83
0x18001da1b  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001da22  test    rax, rax
0x18001da25  jz      short loc_18001DA78
0x18001da27  movzx   ecx, [rsp+0B8h+arg_38]
0x18001da2f  mov     r9d, r13d
0x18001da32  movzx   edx, [rsp+0B8h+arg_20]
0x18001da3a  mov     [rsp+0B8h+var_70], ecx
0x18001da3e  mov     rcx, [rsp+0B8h+arg_30]
0x18001da46  mov     [rsp+0B8h+var_78], rcx
0x18001da4b  mov     ecx, 400000h
0x18001da50  mov     [rsp+0B8h+var_80], rbp
0x18001da55  mov     [rsp+0B8h+var_88], edx
0x18001da59  lea     rdx, aMctpconstructS; "MCTPConstruct[SPM]: Session=0x%x, Clien"...
0x18001da60  movzx   r8d, r15w
0x18001da64  mov     [rsp+0B8h+var_90], r8d
0x18001da69  mov     r8d, [rsi+4]
0x18001da6d  mov     [rsp+0B8h+var_98], r12
0x18001da72  call    cs:__guard_dispatch_icall_fptr
0x18001da78  mov     rax, [rsp+0B8h+arg_40]
0x18001da80  mov     [rax], rbx
0x18001da83  test    edi, edi
0x18001da85  jz      short loc_18001DA97
0x18001da87  mov     rax, [rbx]
0x18001da8a  mov     rcx, rbx
0x18001da8d  mov     rax, [rax+8]
0x18001da91  call    cs:__guard_dispatch_icall_fptr
0x18001da97  mov     eax, edi
0x18001da99  add     rsp, 78h
0x18001da9d  pop     r15
0x18001da9f  pop     r14
0x18001daa1  pop     r13
0x18001daa3  pop     r12
0x18001daa5  pop     rdi
0x18001daa6  pop     rsi
0x18001daa7  pop     rbp
0x18001daa8  pop     rbx
0x18001daa9  retn
```
