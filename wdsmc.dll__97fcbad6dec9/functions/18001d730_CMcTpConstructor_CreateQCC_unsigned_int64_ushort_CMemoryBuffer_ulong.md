# CMcTpConstructor::CreateQCC(unsigned __int64,ushort,CMemoryBuffer * *,ulong,...)

- ea: `0x18001d730`
- end: `0x18001d89f`
- name: `?CreateQCC@CMcTpConstructor@@QEAAK_KGPEAPEAVCMemoryBuffer@@KZZ`
- size: `367`
- prototype: `unsigned int(CMcTpConstructor *__hidden this, unsigned __int64, unsigned __int16, struct CMemoryBuffer **, unsigned int, ...)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180010dd0`

## callees

- `0x180008f4c`
- `0x18001d4f4`
- `0x18001d730`
- `0x180020258`
- `0x180023b28`
- `0x1800247d4`
- `0x180025850`
- `0x180026d70`

## import_xrefs

- `WS2_32!__imp_htonl` at `0x18001d7c4`
- `WS2_32!__imp_htonl` at `0x18001d7c4`
- `WS2_32!__imp_htons` at `0x18001d817`
- `WS2_32!__imp_htons` at `0x18001d817`

## pseudocode

```c
__int64 CMcTpConstructor::CreateQCC(
        CMcTpConstructor *this,
        unsigned __int64 a2,
        u_short a3,
        struct CMemoryBuffer **a4,
        unsigned int a5,
        ...)
{
  va_list v5; // r10
  int v10; // r11d
  __int64 v11; // rcx
  unsigned int v12; // edi
  unsigned int Options; // edi
  struct CMemoryBuffer *v14; // rax
  struct CMemoryBuffer *v15; // rbx
  _WORD *v16; // rax
  __int64 v17; // r14
  u_long v18; // eax
  LONGLONG v19; // rax
  const char *v20; // rdx
  va_list va; // [rsp+B8h] [rbp+30h] BYREF

  va_start(va, a5);
  va_copy(v5, va);
  v10 = 2;
  if ( a5 )
  {
    v11 = a5;
    do
    {
      v10 += *((_DWORD *)v5 + 2) + 4;
      v5 += 24;
      --v11;
    }
    while ( v11 );
  }
  v12 = v10 + *((_DWORD *)this + 25) + 23;
  if ( v12 <= 0xFFFF )
  {
    v14 = TptMemoryBufferAllocate(v12);
    v15 = v14;
    if ( v14 )
    {
      v16 = (_WORD *)*((_QWORD *)v14 + 5);
      *v16 = 17495;
      *(_WORD *)((char *)v16 + 3) = 0;
      v17 = *((_QWORD *)v15 + 5) + *((unsigned int *)this + 25);
      v18 = htonl(*((_DWORD *)this + 1));
      *(_BYTE *)(v17 + 4) = 4;
      *(_DWORD *)v17 = v18;
      v19 = CStopwatch::CurrentMs((CMcTpConstructor *)((char *)this + 104));
      *(_QWORD *)(v17 + 5) = CNetworkAddress::HostToNetworkByteOrder(v19);
      Options = CMcTpOptions::CreateOptions(
                  a5,
                  (u_short *)va,
                  (struct _WDSMCTP_OPTIONS *)(v17 + 23),
                  v12 - *((_DWORD *)this + 25) - 23);
      if ( Options )
        goto LABEL_14;
      *(_QWORD *)(v17 + 13) = CNetworkAddress::HostToNetworkByteOrder(a2);
      *(_WORD *)(v17 + 21) = htons(a3);
      Options = CMcTpConstructor::ServerSecurePacket(this, v15);
      if ( !ElValidateWin32(Options, v20, "base\\eco\\wds\\transport\\lib\\mctpconstructor.cpp", 0x8A2u) )
      {
        if ( g_ErrLibTraceFunctionEx )
          g_ErrLibTraceFunctionEx(
            0x400000u,
            L"MCTPConstruct[QCC]: Session=0x%x, Seq#=%I64u, BO=%u",
            *((unsigned int *)this + 1),
            a2,
            a3);
        *a4 = v15;
      }
      if ( Options )
LABEL_14:
        (*(void (__fastcall **)(struct CMemoryBuffer *))(*(_QWORD *)v15 + 8LL))(v15);
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
0x18001d730  mov     rax, rsp
0x18001d733  push    rbx
0x18001d734  push    rbp
0x18001d735  push    rsi
0x18001d736  push    rdi
0x18001d737  push    r12
0x18001d739  push    r13
0x18001d73b  push    r14
0x18001d73d  push    r15
0x18001d73f  sub     rsp, 48h
0x18001d743  mov     ebp, [rax+28h]
0x18001d746  lea     r10, [rax+30h]
0x18001d74a  xor     r14d, r14d
0x18001d74d  mov     r13, r9
0x18001d750  movzx   r15d, r8w
0x18001d754  mov     r12, rdx
0x18001d757  mov     rsi, rcx
0x18001d75a  lea     r11d, [r14+2]
0x18001d75e  test    ebp, ebp
0x18001d760  jz      short loc_18001D776
0x18001d762  mov     ecx, ebp
0x18001d764  add     r11d, 4
0x18001d768  add     r11d, [r10+8]
0x18001d76c  lea     r10, [r10+18h]
0x18001d770  sub     rcx, 1
0x18001d774  jnz     short loc_18001D764
0x18001d776  mov     edi, [rsi+64h]
0x18001d779  add     edi, 17h
0x18001d77c  add     edi, r11d
0x18001d77f  cmp     edi, 0FFFFh
0x18001d785  jbe     short loc_18001D791
0x18001d787  mov     edi, 6Fh ; 'o'
0x18001d78c  jmp     loc_18001D88C
0x18001d791  mov     ecx, edi; unsigned int
0x18001d793  call    ?TptMemoryBufferAllocate@@YAPEAVCMemoryBuffer@@K@Z; TptMemoryBufferAllocate(ulong)
0x18001d798  mov     rbx, rax
0x18001d79b  test    rax, rax
0x18001d79e  jnz     short loc_18001D7A8
0x18001d7a0  lea     edi, [rax+8]
0x18001d7a3  jmp     loc_18001D88C
0x18001d7a8  mov     rax, [rax+28h]
0x18001d7ac  mov     ecx, 4457h
0x18001d7b1  mov     [rax], cx
0x18001d7b4  mov     [rax+3], r14w
0x18001d7b9  mov     r14d, [rsi+64h]
0x18001d7bd  mov     ecx, [rsi+4]; hostlong
0x18001d7c0  add     r14, [rbx+28h]
0x18001d7c4  call    cs:__imp_htonl
0x18001d7ca  lea     rcx, [rsi+68h]; this
0x18001d7ce  mov     byte ptr [r14+4], 4
0x18001d7d3  mov     [r14], eax
0x18001d7d6  call    ?CurrentMs@CStopwatch@@QEAA_KXZ; CStopwatch::CurrentMs(void)
0x18001d7db  mov     rcx, rax; unsigned __int64
0x18001d7de  call    ?HostToNetworkByteOrder@CNetworkAddress@@SA_K_K@Z; CNetworkAddress::HostToNetworkByteOrder(unsigned __int64)
0x18001d7e3  mov     [r14+5], rax
0x18001d7e7  lea     r8, [r14+17h]; struct _WDSMCTP_OPTIONS *
0x18001d7eb  sub     edi, [rsi+64h]
0x18001d7ee  lea     rdx, [rsp+88h+arg_28]; char *
0x18001d7f6  mov     ecx, ebp; unsigned int
0x18001d7f8  lea     r9d, [rdi-17h]; unsigned int
0x18001d7fc  call    ?CreateOptions@CMcTpOptions@@SAKKPEADPEAU_WDSMCTP_OPTIONS@@K@Z; CMcTpOptions::CreateOptions(ulong,char *,_WDSMCTP_OPTIONS *,ulong)
0x18001d801  mov     edi, eax
0x18001d803  test    eax, eax
0x18001d805  jnz     short loc_18001D87C
0x18001d807  mov     rcx, r12; unsigned __int64
0x18001d80a  call    ?HostToNetworkByteOrder@CNetworkAddress@@SA_K_K@Z; CNetworkAddress::HostToNetworkByteOrder(unsigned __int64)
0x18001d80f  movzx   ecx, r15w; hostshort
0x18001d813  mov     [r14+0Dh], rax
0x18001d817  call    cs:__imp_htons
0x18001d81d  mov     rdx, rbx; struct CMemoryBuffer *
0x18001d820  mov     rcx, rsi; this
0x18001d823  mov     [r14+15h], ax
0x18001d828  call    ?ServerSecurePacket@CMcTpConstructor@@AEAAKPEAVCMemoryBuffer@@@Z; CMcTpConstructor::ServerSecurePacket(CMemoryBuffer *)
0x18001d82d  mov     r9d, 8A2h; unsigned int
0x18001d833  lea     r8, aBaseEcoWdsTran_17; "base\\eco\\wds\\transport\\lib\\mctpcon"...
0x18001d83a  mov     ecx, eax; unsigned int
0x18001d83c  mov     edi, eax
0x18001d83e  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001d843  test    eax, eax
0x18001d845  jnz     short loc_18001D878
0x18001d847  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001d84e  test    rax, rax
0x18001d851  jz      short loc_18001D874
0x18001d853  mov     r8d, [rsi+4]
0x18001d857  lea     rdx, aMctpconstructQ; "MCTPConstruct[QCC]: Session=0x%x, Seq#="...
0x18001d85e  movzx   ecx, r15w
0x18001d862  mov     r9, r12
0x18001d865  mov     [rsp+88h+var_68], ecx
0x18001d869  mov     ecx, 400000h
0x18001d86e  call    cs:__guard_dispatch_icall_fptr
0x18001d874  mov     [r13+0], rbx
0x18001d878  test    edi, edi
0x18001d87a  jz      short loc_18001D88C
0x18001d87c  mov     rax, [rbx]
0x18001d87f  mov     rcx, rbx
0x18001d882  mov     rax, [rax+8]
0x18001d886  call    cs:__guard_dispatch_icall_fptr
0x18001d88c  mov     eax, edi
0x18001d88e  add     rsp, 48h
0x18001d892  pop     r15
0x18001d894  pop     r14
0x18001d896  pop     r13
0x18001d898  pop     r12
0x18001d89a  pop     rdi
0x18001d89b  pop     rsi
0x18001d89c  pop     rbp
0x18001d89d  pop     rbx
0x18001d89e  retn
```
