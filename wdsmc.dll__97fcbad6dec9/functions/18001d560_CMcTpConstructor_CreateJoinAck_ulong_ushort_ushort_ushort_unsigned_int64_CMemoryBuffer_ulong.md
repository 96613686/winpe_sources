# CMcTpConstructor::CreateJoinAck(ulong,ushort,ushort,ushort,unsigned __int64,CMemoryBuffer * *,ulong,...)

- ea: `0x18001d560`
- end: `0x18001d727`
- name: `?CreateJoinAck@CMcTpConstructor@@QEAAKKGGG_KPEAPEAVCMemoryBuffer@@KZZ`
- size: `455`
- prototype: `unsigned int(CMcTpConstructor *__hidden this, u_long hostlong, unsigned __int16, unsigned __int16, unsigned __int16, unsigned __int64, struct CMemoryBuffer **, unsigned int, ...)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000ff2c`

## callees

- `0x180008f4c`
- `0x18001d4f4`
- `0x18001d560`
- `0x180020258`
- `0x180023b28`
- `0x1800247d4`
- `0x180025850`
- `0x180026d70`

## import_xrefs

- `WS2_32!__imp_htonl` at `0x18001d5f6`
- `WS2_32!__imp_htonl` at `0x18001d640`
- `WS2_32!__imp_htonl` at `0x18001d5f6`
- `WS2_32!__imp_htonl` at `0x18001d640`
- `WS2_32!__imp_htons` at `0x18001d64e`
- `WS2_32!__imp_htons` at `0x18001d65d`
- `WS2_32!__imp_htons` at `0x18001d670`
- `WS2_32!__imp_htons` at `0x18001d64e`
- `WS2_32!__imp_htons` at `0x18001d65d`
- `WS2_32!__imp_htons` at `0x18001d670`

## pseudocode

```c
__int64 CMcTpConstructor::CreateJoinAck(
        CMcTpConstructor *this,
        u_long hostlong,
        u_short a3,
        u_short a4,
        u_short a5,
        unsigned __int64 a6,
        struct CMemoryBuffer **a7,
        unsigned int a8,
        ...)
{
  va_list v10; // rcx
  int v13; // r10d
  __int64 v14; // r8
  unsigned int v15; // edi
  unsigned int Options; // edi
  struct CMemoryBuffer *v17; // rax
  struct CMemoryBuffer *v18; // rbx
  _WORD *v19; // rax
  __int64 v20; // r14
  u_long v21; // eax
  LONGLONG v22; // rax
  unsigned __int64 v23; // rax
  void (*v24)(unsigned int, const unsigned __int16 *, ...); // r10
  const char *v25; // rdx
  va_list va; // [rsp+E0h] [rbp+48h] BYREF

  va_start(va, a8);
  va_copy(v10, va);
  v13 = 2;
  if ( a8 )
  {
    v14 = a8;
    do
    {
      v13 += *((_DWORD *)v10 + 2) + 4;
      v10 += 24;
      --v14;
    }
    while ( v14 );
  }
  v15 = v13 + *((_DWORD *)this + 25) + 31;
  if ( v15 <= 0xFFFF )
  {
    v17 = TptMemoryBufferAllocate(v15);
    v18 = v17;
    if ( v17 )
    {
      v19 = (_WORD *)*((_QWORD *)v17 + 5);
      *v19 = 17495;
      *(_WORD *)((char *)v19 + 3) = 0;
      v20 = *((_QWORD *)v18 + 5) + *((unsigned int *)this + 25);
      v21 = htonl(*((_DWORD *)this + 1));
      *(_BYTE *)(v20 + 4) = 3;
      *(_DWORD *)v20 = v21;
      v22 = CStopwatch::CurrentMs((CMcTpConstructor *)((char *)this + 104));
      *(_QWORD *)(v20 + 5) = CNetworkAddress::HostToNetworkByteOrder(v22);
      Options = CMcTpOptions::CreateOptions(
                  a8,
                  va,
                  (struct _WDSMCTP_OPTIONS *)(v20 + 31),
                  v15 - *((_DWORD *)this + 25) - 31);
      if ( Options )
        goto LABEL_14;
      *(_DWORD *)(v20 + 13) = htonl(hostlong);
      *(_WORD *)(v20 + 17) = htons(a3);
      *(_WORD *)(v20 + 19) = htons(a4);
      *(_WORD *)(v20 + 21) = htons(a5);
      v23 = CNetworkAddress::HostToNetworkByteOrder(a6);
      v24 = g_ErrLibTraceFunctionEx;
      *(_QWORD *)(v20 + 23) = v23;
      if ( v24 )
        v24(
          0x400000u,
          L"MCTPConstruct[JOIN-ACK]: Session=0x%x, Client=0x%x, MinNACKBO=%ums, MaxNACKBO=%ums, RTT=%ums",
          *((unsigned int *)this + 1),
          hostlong,
          a3,
          a4,
          a5);
      Options = CMcTpConstructor::ServerSecurePacket(this, v18);
      if ( !ElValidateWin32(Options, v25, "base\\eco\\wds\\transport\\lib\\mctpconstructor.cpp", 0x85Au) )
        *a7 = v18;
      if ( Options )
LABEL_14:
        (*(void (__fastcall **)(struct CMemoryBuffer *))(*(_QWORD *)v18 + 8LL))(v18);
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
0x18001d560  mov     rax, rsp
0x18001d563  push    rbx
0x18001d564  push    rbp
0x18001d565  push    rsi
0x18001d566  push    rdi
0x18001d567  push    r12
0x18001d569  push    r13
0x18001d56b  push    r14
0x18001d56d  push    r15
0x18001d56f  sub     rsp, 58h
0x18001d573  mov     ebp, [rax+40h]
0x18001d576  xor     r14d, r14d
0x18001d579  mov     rsi, rcx
0x18001d57c  movzx   r15d, r9w
0x18001d580  lea     rcx, [rax+48h]
0x18001d584  movzx   r12d, r8w
0x18001d588  mov     r13d, edx
0x18001d58b  lea     r10d, [r14+2]
0x18001d58f  test    ebp, ebp
0x18001d591  jz      short loc_18001D5A8
0x18001d593  mov     r8d, ebp
0x18001d596  add     r10d, 4
0x18001d59a  add     r10d, [rcx+8]
0x18001d59e  lea     rcx, [rcx+18h]
0x18001d5a2  sub     r8, 1
0x18001d5a6  jnz     short loc_18001D596
0x18001d5a8  mov     edi, [rsi+64h]
0x18001d5ab  add     edi, 1Fh
0x18001d5ae  add     edi, r10d
0x18001d5b1  cmp     edi, 0FFFFh
0x18001d5b7  jbe     short loc_18001D5C3
0x18001d5b9  mov     edi, 6Fh ; 'o'
0x18001d5be  jmp     loc_18001D714
0x18001d5c3  mov     ecx, edi; unsigned int
0x18001d5c5  call    ?TptMemoryBufferAllocate@@YAPEAVCMemoryBuffer@@K@Z; TptMemoryBufferAllocate(ulong)
0x18001d5ca  mov     rbx, rax
0x18001d5cd  test    rax, rax
0x18001d5d0  jnz     short loc_18001D5DA
0x18001d5d2  lea     edi, [rax+8]
0x18001d5d5  jmp     loc_18001D714
0x18001d5da  mov     rax, [rax+28h]
0x18001d5de  mov     ecx, 4457h
0x18001d5e3  mov     [rax], cx
0x18001d5e6  mov     [rax+3], r14w
0x18001d5eb  mov     r14d, [rsi+64h]
0x18001d5ef  mov     ecx, [rsi+4]; hostlong
0x18001d5f2  add     r14, [rbx+28h]
0x18001d5f6  call    cs:__imp_htonl
0x18001d5fc  lea     rcx, [rsi+68h]; this
0x18001d600  mov     byte ptr [r14+4], 3
0x18001d605  mov     [r14], eax
0x18001d608  call    ?CurrentMs@CStopwatch@@QEAA_KXZ; CStopwatch::CurrentMs(void)
0x18001d60d  mov     rcx, rax; unsigned __int64
0x18001d610  call    ?HostToNetworkByteOrder@CNetworkAddress@@SA_K_K@Z; CNetworkAddress::HostToNetworkByteOrder(unsigned __int64)
0x18001d615  mov     [r14+5], rax
0x18001d619  lea     r8, [r14+1Fh]; struct _WDSMCTP_OPTIONS *
0x18001d61d  sub     edi, [rsi+64h]
0x18001d620  lea     rdx, [rsp+98h+arg_40]; char *
0x18001d628  mov     ecx, ebp; unsigned int
0x18001d62a  lea     r9d, [rdi-1Fh]; unsigned int
0x18001d62e  call    ?CreateOptions@CMcTpOptions@@SAKKPEADPEAU_WDSMCTP_OPTIONS@@K@Z; CMcTpOptions::CreateOptions(ulong,char *,_WDSMCTP_OPTIONS *,ulong)
0x18001d633  mov     edi, eax
0x18001d635  test    eax, eax
0x18001d637  jnz     loc_18001D704
0x18001d63d  mov     ecx, r13d; hostlong
0x18001d640  call    cs:__imp_htonl
0x18001d646  movzx   ecx, r12w; hostshort
0x18001d64a  mov     [r14+0Dh], eax
0x18001d64e  call    cs:__imp_htons
0x18001d654  movzx   ecx, r15w; hostshort
0x18001d658  mov     [r14+11h], ax
0x18001d65d  call    cs:__imp_htons
0x18001d663  movzx   ecx, [rsp+98h+arg_20]; hostshort
0x18001d66b  mov     [r14+13h], ax
0x18001d670  call    cs:__imp_htons
0x18001d676  mov     rcx, [rsp+98h+arg_28]; unsigned __int64
0x18001d67e  mov     [r14+15h], ax
0x18001d683  call    ?HostToNetworkByteOrder@CNetworkAddress@@SA_K_K@Z; CNetworkAddress::HostToNetworkByteOrder(unsigned __int64)
0x18001d688  mov     r10, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001d68f  mov     [r14+17h], rax
0x18001d693  test    r10, r10
0x18001d696  jz      short loc_18001D6D0
0x18001d698  movzx   eax, [rsp+98h+arg_20]
0x18001d6a0  mov     r9d, r13d
0x18001d6a3  mov     r8d, [rsi+4]
0x18001d6a7  mov     [rsp+98h+var_68], eax
0x18001d6ab  mov     rax, r10
0x18001d6ae  movzx   ecx, r15w
0x18001d6b2  mov     [rsp+98h+var_70], ecx
0x18001d6b6  mov     ecx, 400000h
0x18001d6bb  movzx   edx, r12w
0x18001d6bf  mov     [rsp+98h+var_78], edx
0x18001d6c3  lea     rdx, aMctpconstructJ; "MCTPConstruct[JOIN-ACK]: Session=0x%x, "...
0x18001d6ca  call    cs:__guard_dispatch_icall_fptr
0x18001d6d0  mov     rdx, rbx; struct CMemoryBuffer *
0x18001d6d3  mov     rcx, rsi; this
0x18001d6d6  call    ?ServerSecurePacket@CMcTpConstructor@@AEAAKPEAVCMemoryBuffer@@@Z; CMcTpConstructor::ServerSecurePacket(CMemoryBuffer *)
0x18001d6db  mov     r9d, 85Ah; unsigned int
0x18001d6e1  lea     r8, aBaseEcoWdsTran_17; "base\\eco\\wds\\transport\\lib\\mctpcon"...
0x18001d6e8  mov     ecx, eax; unsigned int
0x18001d6ea  mov     edi, eax
0x18001d6ec  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001d6f1  test    eax, eax
0x18001d6f3  jnz     short loc_18001D700
0x18001d6f5  mov     rcx, [rsp+98h+arg_30]
0x18001d6fd  mov     [rcx], rbx
0x18001d700  test    edi, edi
0x18001d702  jz      short loc_18001D714
0x18001d704  mov     rax, [rbx]
0x18001d707  mov     rcx, rbx
0x18001d70a  mov     rax, [rax+8]
0x18001d70e  call    cs:__guard_dispatch_icall_fptr
0x18001d714  mov     eax, edi
0x18001d716  add     rsp, 58h
0x18001d71a  pop     r15
0x18001d71c  pop     r14
0x18001d71e  pop     r13
0x18001d720  pop     r12
0x18001d722  pop     rdi
0x18001d723  pop     rsi
0x18001d724  pop     rbp
0x18001d725  pop     rbx
0x18001d726  retn
```
