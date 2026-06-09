# CMcTpConstructor::CreatePoll(unsigned __int64,ushort,void *,ulong,CMemoryBuffer * *,ulong,...)

- ea: `0x18001df44`
- end: `0x18001e166`
- name: `?CreatePoll@CMcTpConstructor@@QEAAK_KGPEAXKPEAPEAVCMemoryBuffer@@KZZ`
- size: `546`
- prototype: `unsigned int(CMcTpConstructor *__hidden this, unsigned __int64, unsigned __int16, void *, size_t Size, struct CMemoryBuffer **, unsigned int, ...)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180015aa0`

## callees

- `0x180008f4c`
- `0x18001d4f4`
- `0x18001df44`
- `0x180020258`
- `0x180023b28`
- `0x1800247d4`
- `0x180025850`
- `0x180026d3a`
- `0x180026d70`

## import_xrefs

- `WS2_32!__imp_htonl` at `0x18001e01f`
- `WS2_32!__imp_htonl` at `0x18001e01f`
- `WS2_32!__imp_htons` at `0x18001e098`
- `WS2_32!__imp_htons` at `0x18001e0ba`
- `WS2_32!__imp_htons` at `0x18001e098`
- `WS2_32!__imp_htons` at `0x18001e0ba`

## pseudocode

```c
__int64 CMcTpConstructor::CreatePoll(
        CMcTpConstructor *this,
        unsigned __int64 a2,
        u_short a3,
        void *a4,
        size_t Size,
        struct CMemoryBuffer **a6,
        unsigned int a7,
        ...)
{
  va_list v7; // r10
  struct CMemoryBuffer *v9; // rdi
  __int64 v10; // r13
  unsigned int v11; // ebx
  __int64 v12; // rcx
  unsigned int v13; // edx
  bool v14; // cf
  unsigned int Options; // ebx
  unsigned int v16; // r8d
  unsigned int v17; // edx
  unsigned int v18; // r8d
  struct CMemoryBuffer *v19; // rax
  struct CMemoryBuffer *v20; // rsi
  _WORD *v21; // rax
  __int64 v22; // r15
  u_long v23; // eax
  LONGLONG v24; // rax
  const char *v25; // rdx
  va_list va; // [rsp+D8h] [rbp+40h] BYREF

  va_start(va, a7);
  va_copy(v7, va);
  v9 = 0;
  v10 = 0;
  v11 = 2;
  if ( a7 )
  {
    v12 = a7;
    do
    {
      v11 += *((_DWORD *)v7 + 2) + 4;
      v7 += 24;
      --v12;
    }
    while ( v12 );
  }
  v13 = Size + 25;
  v14 = (unsigned int)Size >= 0xFFFFFFE7;
  if ( (unsigned int)Size >= 0xFFFFFFE7
    || (v16 = v11 + v13, v14 = v11 + v13 < v13)
    || (v17 = v11 + v13, v18 = v16 + *((_DWORD *)this + 25), v14 = v18 < v17) )
  {
    Options = v14 ? 0x216 : 0;
  }
  else
  {
    if ( v18 > 0xFFFF )
      return 111;
    v19 = TptMemoryBufferAllocate(v18);
    v20 = v19;
    if ( !v19 )
      return 8;
    v21 = (_WORD *)*((_QWORD *)v19 + 5);
    *v21 = 17495;
    *(_WORD *)((char *)v21 + 3) = 0;
    v22 = *((_QWORD *)v20 + 5) + *((unsigned int *)this + 25);
    v23 = htonl(*((_DWORD *)this + 1));
    *(_BYTE *)(v22 + 4) = 12;
    *(_DWORD *)v22 = v23;
    v24 = CStopwatch::CurrentMs((CMcTpConstructor *)((char *)this + 104));
    *(_QWORD *)(v22 + 5) = CNetworkAddress::HostToNetworkByteOrder(v24);
    Options = CMcTpOptions::CreateOptions(a7, va, (struct _WDSMCTP_OPTIONS *)(v22 + (unsigned int)Size + 25LL), v11);
    if ( Options )
      goto LABEL_15;
    v9 = v20;
    v10 = v22;
  }
  v20 = v9;
  if ( Options )
  {
LABEL_15:
    if ( v20 )
      (*(void (__fastcall **)(struct CMemoryBuffer *))(*(_QWORD *)v20 + 8LL))(v20);
LABEL_23:
    if ( v9 )
      (*(void (__fastcall **)(struct CMemoryBuffer *))(*(_QWORD *)v9 + 8LL))(v9);
    return Options;
  }
  *(_WORD *)(v10 + 21) = htons(a3);
  *(_QWORD *)(v10 + 13) = CNetworkAddress::HostToNetworkByteOrder(a2);
  *(_WORD *)(v10 + 23) = htons(Size);
  memmove_0((void *)(v10 + 25), a4, (unsigned int)Size);
  Options = CMcTpConstructor::ServerSecurePacket(this, v9);
  if ( !ElValidateWin32(Options, v25, "base\\eco\\wds\\transport\\lib\\mctpconstructor.cpp", 0xA83u) )
  {
    if ( g_ErrLibTraceFunctionEx )
      g_ErrLibTraceFunctionEx(
        0x400000u,
        L"MCTPConstruct[POLL]: Session=0x%x, Seq#=%I64u, BO=%ums, AppDataLen=%u",
        *((unsigned int *)this + 1),
        a2,
        a3,
        Size);
    *a6 = v9;
  }
  if ( Options )
    goto LABEL_23;
  return Options;
}

```

## disassembly

```asm
0x18001df44  mov     rax, rsp
0x18001df47  mov     [rax+20h], r9
0x18001df4b  mov     [rax+18h], r8w
0x18001df50  mov     [rax+10h], rdx
0x18001df54  push    rbx
0x18001df55  push    rbp
0x18001df56  push    rsi
0x18001df57  push    rdi
0x18001df58  push    r12
0x18001df5a  push    r13
0x18001df5c  push    r14
0x18001df5e  push    r15
0x18001df60  sub     rsp, 58h
0x18001df64  mov     r14d, [rax+38h]
0x18001df68  lea     r10, [rax+40h]
0x18001df6c  xor     r15d, r15d
0x18001df6f  mov     r12, rcx
0x18001df72  mov     edi, r15d
0x18001df75  mov     r13d, r15d
0x18001df78  lea     ebx, [r15+2]
0x18001df7c  test    r14d, r14d
0x18001df7f  jz      short loc_18001DF95
0x18001df81  mov     ecx, r14d
0x18001df84  add     ebx, 4
0x18001df87  add     ebx, [r10+8]
0x18001df8b  lea     r10, [r10+18h]
0x18001df8f  sub     rcx, 1
0x18001df93  jnz     short loc_18001DF84
0x18001df95  mov     ebp, dword ptr [rsp+98h+Size]
0x18001df9c  or      ecx, 0FFFFFFFFh
0x18001df9f  mov     eax, ecx
0x18001dfa1  lea     edx, [rbp+19h]
0x18001dfa4  cmp     edx, 19h
0x18001dfa7  cmovnb  eax, edx
0x18001dfaa  jnb     short loc_18001DFB9
0x18001dfac  sbb     ebx, ebx
0x18001dfae  and     ebx, 216h
0x18001dfb4  jmp     loc_18001E069
0x18001dfb9  lea     r8d, [rbx+rax]
0x18001dfbd  mov     edx, ecx
0x18001dfbf  cmp     r8d, eax
0x18001dfc2  cmovnb  edx, r8d
0x18001dfc6  jb      short loc_18001DFAC
0x18001dfc8  mov     r8d, [r12+64h]
0x18001dfcd  add     r8d, edx
0x18001dfd0  cmp     r8d, edx
0x18001dfd3  cmovnb  ecx, r8d; unsigned int
0x18001dfd7  jb      short loc_18001DFAC
0x18001dfd9  cmp     ecx, 0FFFFh
0x18001dfdf  jbe     short loc_18001DFEB
0x18001dfe1  mov     ebx, 6Fh ; 'o'
0x18001dfe6  jmp     loc_18001E153
0x18001dfeb  call    ?TptMemoryBufferAllocate@@YAPEAVCMemoryBuffer@@K@Z; TptMemoryBufferAllocate(ulong)
0x18001dff0  mov     rsi, rax
0x18001dff3  test    rax, rax
0x18001dff6  jnz     short loc_18001E000
0x18001dff8  lea     ebx, [rax+8]
0x18001dffb  jmp     loc_18001E153
0x18001e000  mov     rax, [rax+28h]
0x18001e004  mov     ecx, 4457h
0x18001e009  mov     [rax], cx
0x18001e00c  mov     [rax+3], r15w
0x18001e011  mov     r15d, [r12+64h]
0x18001e016  mov     ecx, [r12+4]; hostlong
0x18001e01b  add     r15, [rsi+28h]
0x18001e01f  call    cs:__imp_htonl
0x18001e025  lea     rcx, [r12+68h]; this
0x18001e02a  mov     byte ptr [r15+4], 0Ch
0x18001e02f  mov     [r15], eax
0x18001e032  call    ?CurrentMs@CStopwatch@@QEAA_KXZ; CStopwatch::CurrentMs(void)
0x18001e037  mov     rcx, rax; unsigned __int64
0x18001e03a  call    ?HostToNetworkByteOrder@CNetworkAddress@@SA_K_K@Z; CNetworkAddress::HostToNetworkByteOrder(unsigned __int64)
0x18001e03f  lea     r8, [rbp+19h]
0x18001e043  mov     [r15+5], rax
0x18001e047  add     r8, r15; struct _WDSMCTP_OPTIONS *
0x18001e04a  lea     rdx, [rsp+98h+arg_38]; char *
0x18001e052  mov     r9d, ebx; unsigned int
0x18001e055  mov     ecx, r14d; unsigned int
0x18001e058  call    ?CreateOptions@CMcTpOptions@@SAKKPEADPEAU_WDSMCTP_OPTIONS@@K@Z; CMcTpOptions::CreateOptions(ulong,char *,_WDSMCTP_OPTIONS *,ulong)
0x18001e05d  mov     ebx, eax
0x18001e05f  test    eax, eax
0x18001e061  jnz     short loc_18001E070
0x18001e063  mov     rdi, rsi
0x18001e066  mov     r13, r15
0x18001e069  mov     rsi, rdi
0x18001e06c  test    ebx, ebx
0x18001e06e  jz      short loc_18001E08D
0x18001e070  test    rsi, rsi
0x18001e073  jz      short loc_18001E085
0x18001e075  mov     rax, [rsi]
0x18001e078  mov     rcx, rsi
0x18001e07b  mov     rax, [rax+8]
0x18001e07f  call    cs:__guard_dispatch_icall_fptr
0x18001e085  test    ebx, ebx
0x18001e087  jnz     loc_18001E13E
0x18001e08d  movzx   esi, [rsp+98h+arg_10]
0x18001e095  movzx   ecx, si; hostshort
0x18001e098  call    cs:__imp_htons
0x18001e09e  mov     r14, [rsp+98h+arg_8]
0x18001e0a6  mov     rcx, r14; unsigned __int64
0x18001e0a9  mov     [r13+15h], ax
0x18001e0ae  call    ?HostToNetworkByteOrder@CNetworkAddress@@SA_K_K@Z; CNetworkAddress::HostToNetworkByteOrder(unsigned __int64)
0x18001e0b3  movzx   ecx, bp; hostshort
0x18001e0b6  mov     [r13+0Dh], rax
0x18001e0ba  call    cs:__imp_htons
0x18001e0c0  mov     rdx, [rsp+98h+Src]; Src
0x18001e0c8  lea     rcx, [r13+19h]; void *
0x18001e0cc  mov     r8, rbp; Size
0x18001e0cf  mov     [r13+17h], ax
0x18001e0d4  call    memmove_0
0x18001e0d9  mov     rdx, rdi; struct CMemoryBuffer *
0x18001e0dc  mov     rcx, r12; this
0x18001e0df  call    ?ServerSecurePacket@CMcTpConstructor@@AEAAKPEAVCMemoryBuffer@@@Z; CMcTpConstructor::ServerSecurePacket(CMemoryBuffer *)
0x18001e0e4  mov     r9d, 0A83h; unsigned int
0x18001e0ea  lea     r8, aBaseEcoWdsTran_17; "base\\eco\\wds\\transport\\lib\\mctpcon"...
0x18001e0f1  mov     ecx, eax; unsigned int
0x18001e0f3  mov     ebx, eax
0x18001e0f5  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001e0fa  test    eax, eax
0x18001e0fc  jnz     short loc_18001E13A
0x18001e0fe  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001e105  test    rax, rax
0x18001e108  jz      short loc_18001E12F
0x18001e10a  mov     r8d, [r12+4]
0x18001e10f  lea     rdx, aMctpconstructP; "MCTPConstruct[POLL]: Session=0x%x, Seq#"...
0x18001e116  movzx   ecx, si
0x18001e119  mov     r9, r14
0x18001e11c  mov     [rsp+98h+var_70], ebp
0x18001e120  mov     [rsp+98h+var_78], ecx
0x18001e124  mov     ecx, 400000h
0x18001e129  call    cs:__guard_dispatch_icall_fptr
0x18001e12f  mov     rax, [rsp+98h+arg_28]
0x18001e137  mov     [rax], rdi
0x18001e13a  test    ebx, ebx
0x18001e13c  jz      short loc_18001E153
0x18001e13e  test    rdi, rdi
0x18001e141  jz      short loc_18001E153
0x18001e143  mov     rax, [rdi]
0x18001e146  mov     rcx, rdi
0x18001e149  mov     rax, [rax+8]
0x18001e14d  call    cs:__guard_dispatch_icall_fptr
0x18001e153  mov     eax, ebx
0x18001e155  add     rsp, 58h
0x18001e159  pop     r15
0x18001e15b  pop     r14
0x18001e15d  pop     r13
0x18001e15f  pop     r12
0x18001e161  pop     rdi
0x18001e162  pop     rsi
0x18001e163  pop     rbp
0x18001e164  pop     rbx
0x18001e165  retn
```
