# CMcTpConstructor::CreateODATA(ulong,unsigned __int64,unsigned __int64,void *,ulong,int,CMemoryBuffer * *,ulong,...)

- ea: `0x18001dab0`
- end: `0x18001dd25`
- name: `?CreateODATA@CMcTpConstructor@@QEAAKK_K0PEAXKHPEAPEAVCMemoryBuffer@@KZZ`
- size: `629`
- prototype: `__int64(CMcTpConstructor *this, u_long, unsigned __int64, unsigned __int64, void *Src, size_t Size, int, struct CMemoryBuffer **, unsigned int, ...)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800122a4`

## callees

- `0x180008f4c`
- `0x18001d4f4`
- `0x18001dab0`
- `0x180020258`
- `0x180023b28`
- `0x1800247d4`
- `0x180025850`
- `0x180026d3a`
- `0x180026d70`

## import_xrefs

- `WS2_32!__imp_htonl` at `0x18001db88`
- `WS2_32!__imp_htonl` at `0x18001dc01`
- `WS2_32!__imp_htonl` at `0x18001db88`
- `WS2_32!__imp_htonl` at `0x18001dc01`
- `WS2_32!__imp_htons` at `0x18001dc36`
- `WS2_32!__imp_htons` at `0x18001dc96`
- `WS2_32!__imp_htons` at `0x18001dc36`
- `WS2_32!__imp_htons` at `0x18001dc96`

## pseudocode

```c
__int64 CMcTpConstructor::CreateODATA(
        CMcTpConstructor *this,
        u_long a2,
        unsigned __int64 a3,
        unsigned __int64 a4,
        void *Src,
        size_t Size,
        int a7,
        struct CMemoryBuffer **a8,
        unsigned int a9,
        ...)
{
  va_list v9; // r10
  struct CMemoryBuffer *v11; // rdi
  __int64 v12; // rbp
  unsigned int v13; // ebx
  __int64 v14; // rcx
  unsigned int v15; // edx
  bool v16; // cf
  unsigned int Options; // ebx
  unsigned int v18; // r8d
  unsigned int v19; // edx
  unsigned int v20; // r8d
  struct CMemoryBuffer *v21; // rax
  struct CMemoryBuffer *v22; // rsi
  _WORD *v23; // rax
  __int64 v24; // r13
  u_long v25; // eax
  unsigned __int64 v26; // rax
  const char *v27; // rdx
  __int64 v28; // rbx
  const char *v29; // rdx
  va_list va; // [rsp+E8h] [rbp+50h] BYREF

  va_start(va, a9);
  va_copy(v9, va);
  v11 = 0;
  v12 = 0;
  v13 = 2;
  if ( a9 )
  {
    v14 = a9;
    do
    {
      v13 += *((_DWORD *)v9 + 2) + 4;
      v9 += 24;
      --v14;
    }
    while ( v14 );
  }
  v15 = Size + 35;
  v16 = (unsigned int)Size >= 0xFFFFFFDD;
  if ( (unsigned int)Size >= 0xFFFFFFDD
    || (v18 = v13 + v15, v16 = v13 + v15 < v15)
    || (v19 = v13 + v15, v20 = v18 + *((_DWORD *)this + 25), v16 = v20 < v19) )
  {
    Options = v16 ? 0x216 : 0;
  }
  else
  {
    if ( v20 > 0xFFFF )
      return 111;
    v21 = TptMemoryBufferAllocate(v20);
    v22 = v21;
    if ( !v21 )
      return 8;
    v23 = (_WORD *)*((_QWORD *)v21 + 5);
    *v23 = 17495;
    *(_WORD *)((char *)v23 + 3) = 0;
    v24 = *((_QWORD *)v22 + 5) + *((unsigned int *)this + 25);
    v25 = htonl(*((_DWORD *)this + 1));
    *(_BYTE *)(v24 + 4) = 6;
    *(_DWORD *)v24 = v25;
    v26 = CStopwatch::CurrentMs((CMcTpConstructor *)((char *)this + 104));
    *(_QWORD *)(v24 + 5) = CNetworkAddress::HostToNetworkByteOrder(v26);
    Options = CMcTpOptions::CreateOptions(a9, va, (struct _WDSMCTP_OPTIONS *)(v24 + (unsigned int)Size + 35LL), v13);
    if ( Options )
      goto LABEL_15;
    v11 = v22;
    v12 = v24;
  }
  v22 = v11;
  if ( !Options )
  {
    *(_DWORD *)(v12 + 13) = htonl(a2);
    *(_QWORD *)(v12 + 17) = CNetworkAddress::HostToNetworkByteOrder(a3);
    *(_QWORD *)(v12 + 25) = CNetworkAddress::HostToNetworkByteOrder(a4);
    *(_WORD *)(v12 + 33) = htons(Size);
    memmove_0((void *)(v12 + 35), Src, (unsigned int)Size);
    if ( a7 )
    {
      Options = CMcTpConstructor::ServerSecurePacket(this, v11);
      if ( ElValidateWin32(Options, v27, "base\\eco\\wds\\transport\\lib\\mctpconstructor.cpp", 0x964u) )
        goto LABEL_25;
    }
    else
    {
      v28 = *((_QWORD *)v11 + 5);
      *(_BYTE *)(v28 + 2) = -1;
      *(_WORD *)(v28 + 3) = htons(*((_WORD *)this + 50) - 5);
      Options = 0;
      if ( ElValidateWin32(0, v29, "base\\eco\\wds\\transport\\lib\\mctpconstructor.cpp", 0x96Au) )
        return Options;
    }
    if ( g_ErrLibTraceFunctionEx )
      g_ErrLibTraceFunctionEx(
        0x400000u,
        L"MCTPConstruct[ODATA]: Session=0x%x, Client=0x%x, Seq#=%I64u, Trail#=%I64u, DataLen=%u",
        *((unsigned int *)this + 1),
        a2,
        a3,
        a4,
        Size);
    *a8 = v11;
LABEL_25:
    if ( !Options )
      return Options;
    goto LABEL_26;
  }
LABEL_15:
  if ( v22 )
    (*(void (__fastcall **)(struct CMemoryBuffer *))(*(_QWORD *)v22 + 8LL))(v22);
LABEL_26:
  if ( v11 )
    (*(void (__fastcall **)(struct CMemoryBuffer *))(*(_QWORD *)v11 + 8LL))(v11);
  return Options;
}

```

## disassembly

```asm
0x18001dab0  mov     rax, rsp
0x18001dab3  mov     [rax+20h], r9
0x18001dab7  mov     [rax+18h], r8
0x18001dabb  mov     [rax+10h], edx
0x18001dabe  push    rbx
0x18001dabf  push    rbp
0x18001dac0  push    rsi
0x18001dac1  push    rdi
0x18001dac2  push    r12
0x18001dac4  push    r13
0x18001dac6  push    r14
0x18001dac8  push    r15
0x18001daca  sub     rsp, 58h
0x18001dace  mov     r12d, [rax+48h]
0x18001dad2  lea     r10, [rax+50h]
0x18001dad6  xor     r13d, r13d
0x18001dad9  mov     r14, rcx
0x18001dadc  mov     edi, r13d
0x18001dadf  mov     ebp, r13d
0x18001dae2  lea     ebx, [r13+2]
0x18001dae6  test    r12d, r12d
0x18001dae9  jz      short loc_18001DAFF
0x18001daeb  mov     ecx, r12d
0x18001daee  add     ebx, 4
0x18001daf1  add     ebx, [r10+8]
0x18001daf5  lea     r10, [r10+18h]
0x18001daf9  sub     rcx, 1
0x18001dafd  jnz     short loc_18001DAEE
0x18001daff  mov     r15d, dword ptr [rsp+98h+Size]
0x18001db07  or      ecx, 0FFFFFFFFh
0x18001db0a  mov     eax, ecx
0x18001db0c  lea     edx, [r15+23h]
0x18001db10  cmp     edx, 23h ; '#'
0x18001db13  cmovnb  eax, edx
0x18001db16  jnb     short loc_18001DB25
0x18001db18  sbb     ebx, ebx
0x18001db1a  and     ebx, 216h
0x18001db20  jmp     loc_18001DBD2
0x18001db25  lea     r8d, [rbx+rax]
0x18001db29  mov     edx, ecx
0x18001db2b  cmp     r8d, eax
0x18001db2e  cmovnb  edx, r8d
0x18001db32  jb      short loc_18001DB18
0x18001db34  mov     r8d, [r14+64h]
0x18001db38  add     r8d, edx
0x18001db3b  cmp     r8d, edx
0x18001db3e  cmovnb  ecx, r8d; unsigned int
0x18001db42  jb      short loc_18001DB18
0x18001db44  cmp     ecx, 0FFFFh
0x18001db4a  jbe     short loc_18001DB56
0x18001db4c  mov     ebx, 6Fh ; 'o'
0x18001db51  jmp     loc_18001DD12
0x18001db56  call    ?TptMemoryBufferAllocate@@YAPEAVCMemoryBuffer@@K@Z; TptMemoryBufferAllocate(ulong)
0x18001db5b  mov     rsi, rax
0x18001db5e  test    rax, rax
0x18001db61  jnz     short loc_18001DB6B
0x18001db63  lea     ebx, [rax+8]
0x18001db66  jmp     loc_18001DD12
0x18001db6b  mov     rax, [rax+28h]
0x18001db6f  mov     ecx, 4457h
0x18001db74  mov     [rax], cx
0x18001db77  mov     [rax+3], r13w
0x18001db7c  mov     r13d, [r14+64h]
0x18001db80  mov     ecx, [r14+4]; hostlong
0x18001db84  add     r13, [rsi+28h]
0x18001db88  call    cs:__imp_htonl
0x18001db8e  lea     rcx, [r14+68h]; this
0x18001db92  mov     byte ptr [r13+4], 6
0x18001db97  mov     [r13+0], eax
0x18001db9b  call    ?CurrentMs@CStopwatch@@QEAA_KXZ; CStopwatch::CurrentMs(void)
0x18001dba0  mov     rcx, rax; unsigned __int64
0x18001dba3  call    ?HostToNetworkByteOrder@CNetworkAddress@@SA_K_K@Z; CNetworkAddress::HostToNetworkByteOrder(unsigned __int64)
0x18001dba8  lea     r8, [r15+23h]
0x18001dbac  mov     [r13+5], rax
0x18001dbb0  add     r8, r13; struct _WDSMCTP_OPTIONS *
0x18001dbb3  lea     rdx, [rsp+98h+arg_48]; char *
0x18001dbbb  mov     r9d, ebx; unsigned int
0x18001dbbe  mov     ecx, r12d; unsigned int
0x18001dbc1  call    ?CreateOptions@CMcTpOptions@@SAKKPEADPEAU_WDSMCTP_OPTIONS@@K@Z; CMcTpOptions::CreateOptions(ulong,char *,_WDSMCTP_OPTIONS *,ulong)
0x18001dbc6  mov     ebx, eax
0x18001dbc8  test    eax, eax
0x18001dbca  jnz     short loc_18001DBD9
0x18001dbcc  mov     rdi, rsi
0x18001dbcf  mov     rbp, r13
0x18001dbd2  mov     rsi, rdi
0x18001dbd5  test    ebx, ebx
0x18001dbd7  jz      short loc_18001DBF6
0x18001dbd9  test    rsi, rsi
0x18001dbdc  jz      short loc_18001DBEE
0x18001dbde  mov     rax, [rsi]
0x18001dbe1  mov     rcx, rsi
0x18001dbe4  mov     rax, [rax+8]
0x18001dbe8  call    cs:__guard_dispatch_icall_fptr
0x18001dbee  test    ebx, ebx
0x18001dbf0  jnz     loc_18001DCFD
0x18001dbf6  mov     r13d, [rsp+98h+hostlong]
0x18001dbfe  mov     ecx, r13d; hostlong
0x18001dc01  call    cs:__imp_htonl
0x18001dc07  mov     r12, [rsp+98h+arg_10]
0x18001dc0f  mov     rcx, r12; unsigned __int64
0x18001dc12  mov     [rbp+0Dh], eax
0x18001dc15  call    ?HostToNetworkByteOrder@CNetworkAddress@@SA_K_K@Z; CNetworkAddress::HostToNetworkByteOrder(unsigned __int64)
0x18001dc1a  mov     rsi, [rsp+98h+arg_18]
0x18001dc22  mov     rcx, rsi; unsigned __int64
0x18001dc25  mov     [rbp+11h], rax
0x18001dc29  call    ?HostToNetworkByteOrder@CNetworkAddress@@SA_K_K@Z; CNetworkAddress::HostToNetworkByteOrder(unsigned __int64)
0x18001dc2e  movzx   ecx, r15w; hostshort
0x18001dc32  mov     [rbp+19h], rax
0x18001dc36  call    cs:__imp_htons
0x18001dc3c  mov     rdx, [rsp+98h+Src]; Src
0x18001dc44  lea     rcx, [rbp+23h]; void *
0x18001dc48  mov     r8, r15; Size
0x18001dc4b  mov     [rbp+21h], ax
0x18001dc4f  call    memmove_0
0x18001dc54  cmp     [rsp+98h+arg_30], 0
0x18001dc5c  jz      short loc_18001DC85
0x18001dc5e  mov     rdx, rdi; struct CMemoryBuffer *
0x18001dc61  mov     rcx, r14; this
0x18001dc64  call    ?ServerSecurePacket@CMcTpConstructor@@AEAAKPEAVCMemoryBuffer@@@Z; CMcTpConstructor::ServerSecurePacket(CMemoryBuffer *)
0x18001dc69  mov     r9d, 964h; unsigned int
0x18001dc6f  lea     r8, aBaseEcoWdsTran_17; "base\\eco\\wds\\transport\\lib\\mctpcon"...
0x18001dc76  mov     ecx, eax; unsigned int
0x18001dc78  mov     ebx, eax
0x18001dc7a  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001dc7f  test    eax, eax
0x18001dc81  jnz     short loc_18001DCF9
0x18001dc83  jmp     short loc_18001DCBA
0x18001dc85  mov     rbx, [rdi+28h]
0x18001dc89  mov     byte ptr [rbx+2], 0FFh
0x18001dc8d  movzx   ecx, word ptr [r14+64h]
0x18001dc92  sub     cx, 5; hostshort
0x18001dc96  call    cs:__imp_htons
0x18001dc9c  mov     [rbx+3], ax
0x18001dca0  mov     r9d, 96Ah; unsigned int
0x18001dca6  lea     r8, aBaseEcoWdsTran_17; "base\\eco\\wds\\transport\\lib\\mctpcon"...
0x18001dcad  xor     ecx, ecx; unsigned int
0x18001dcaf  xor     ebx, ebx
0x18001dcb1  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001dcb6  test    eax, eax
0x18001dcb8  jnz     short loc_18001DD12
0x18001dcba  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001dcc1  test    rax, rax
0x18001dcc4  jz      short loc_18001DCEE
0x18001dcc6  mov     r8d, [r14+4]
0x18001dcca  lea     rdx, aMctpconstructO; "MCTPConstruct[ODATA]: Session=0x%x, Cli"...
0x18001dcd1  mov     [rsp+98h+var_68], r15d
0x18001dcd6  mov     r9d, r13d
0x18001dcd9  mov     [rsp+98h+var_70], rsi
0x18001dcde  mov     ecx, 400000h
0x18001dce3  mov     [rsp+98h+var_78], r12
0x18001dce8  call    cs:__guard_dispatch_icall_fptr
0x18001dcee  mov     rax, [rsp+98h+arg_38]
0x18001dcf6  mov     [rax], rdi
0x18001dcf9  test    ebx, ebx
0x18001dcfb  jz      short loc_18001DD12
0x18001dcfd  test    rdi, rdi
0x18001dd00  jz      short loc_18001DD12
0x18001dd02  mov     rax, [rdi]
0x18001dd05  mov     rcx, rdi
0x18001dd08  mov     rax, [rax+8]
0x18001dd0c  call    cs:__guard_dispatch_icall_fptr
0x18001dd12  mov     eax, ebx
0x18001dd14  add     rsp, 58h
0x18001dd18  pop     r15
0x18001dd1a  pop     r14
0x18001dd1c  pop     r13
0x18001dd1e  pop     r12
0x18001dd20  pop     rdi
0x18001dd21  pop     rsi
0x18001dd22  pop     rbp
0x18001dd23  pop     rbx
0x18001dd24  retn
```
