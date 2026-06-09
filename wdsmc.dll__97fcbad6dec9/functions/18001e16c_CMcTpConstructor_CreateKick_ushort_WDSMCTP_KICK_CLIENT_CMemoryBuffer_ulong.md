# CMcTpConstructor::CreateKick(ushort,_WDSMCTP_KICK_CLIENT *,CMemoryBuffer * *,ulong,...)

- ea: `0x18001e16c`
- end: `0x18001e392`
- name: `?CreateKick@CMcTpConstructor@@QEAAKGPEAU_WDSMCTP_KICK_CLIENT@@PEAPEAVCMemoryBuffer@@KZZ`
- size: `550`
- prototype: `unsigned int(CMcTpConstructor *__hidden this, unsigned __int16, struct _WDSMCTP_KICK_CLIENT *, struct CMemoryBuffer **, unsigned int, ...)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000ea7c`

## callees

- `0x180008f4c`
- `0x18001d4f4`
- `0x18001e16c`
- `0x180020258`
- `0x180023b28`
- `0x1800247d4`
- `0x180025850`
- `0x180026d70`

## import_xrefs

- `WS2_32!__imp_htonl` at `0x18001e25a`
- `WS2_32!__imp_htonl` at `0x18001e2f7`
- `WS2_32!__imp_htonl` at `0x18001e25a`
- `WS2_32!__imp_htonl` at `0x18001e2f7`
- `WS2_32!__imp_htons` at `0x18001e2d3`
- `WS2_32!__imp_htons` at `0x18001e2d3`

## pseudocode

```c
__int64 CMcTpConstructor::CreateKick(
        CMcTpConstructor *this,
        u_short a2,
        struct _WDSMCTP_KICK_CLIENT *a3,
        struct CMemoryBuffer **a4,
        unsigned int a5,
        ...)
{
  u_short v5; // r15
  va_list v7; // rcx
  unsigned int v8; // ebx
  struct CMemoryBuffer *v9; // rdi
  __int64 v10; // rbp
  unsigned int v11; // r8d
  __int64 v12; // rdx
  bool v13; // cf
  unsigned int v14; // eax
  unsigned int Options; // ebx
  unsigned int v16; // r8d
  unsigned int v17; // edx
  unsigned int v18; // r8d
  struct CMemoryBuffer *v19; // rax
  struct CMemoryBuffer *v20; // rsi
  _WORD *v21; // rax
  __int64 v22; // r12
  u_long v23; // eax
  LONGLONG v24; // rax
  __int64 v25; // rsi
  __int64 v26; // rbp
  _BYTE *v27; // rbx
  const char *v28; // rdx
  va_list va; // [rsp+B8h] [rbp+30h] BYREF

  va_start(va, a5);
  v5 = a2;
  if ( a2 > 0xC8u )
    v5 = 200;
  va_copy(v7, va);
  v8 = 2;
  v9 = 0;
  v10 = 0;
  v11 = 5 * (v5 + 3);
  if ( a5 )
  {
    v12 = a5;
    do
    {
      v8 += *((_DWORD *)v7 + 2) + 4;
      v7 += 24;
      --v12;
    }
    while ( v12 );
  }
  v13 = v11 < 0xF;
  if ( v11 < 0xF
    || (v14 = 5 * (v5 + 3),
        (v16 = v8 + v11, v13 = v16 < v14) || (v17 = v16, v18 = v16 + *((_DWORD *)this + 25), v13 = v18 < v17)) )
  {
    Options = v13 ? 0x216 : 0;
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
    *(_BYTE *)(v22 + 4) = 14;
    *(_DWORD *)v22 = v23;
    v24 = CStopwatch::CurrentMs((CMcTpConstructor *)((char *)this + 104));
    *(_QWORD *)(v22 + 5) = CNetworkAddress::HostToNetworkByteOrder(v24);
    Options = CMcTpOptions::CreateOptions(a5, va, (struct _WDSMCTP_OPTIONS *)(v22 + 5 * (unsigned int)v5 + 15LL), v8);
    if ( Options )
      goto LABEL_18;
    v9 = v20;
    v10 = v22;
  }
  v20 = v9;
  if ( Options )
  {
LABEL_18:
    if ( v20 )
      (*(void (__fastcall **)(struct CMemoryBuffer *))(*(_QWORD *)v20 + 8LL))(v20);
LABEL_29:
    if ( v9 )
      (*(void (__fastcall **)(struct CMemoryBuffer *))(*(_QWORD *)v9 + 8LL))(v9);
    return Options;
  }
  *(_WORD *)(v10 + 13) = htons(v5);
  if ( v5 )
  {
    v25 = v5;
    v26 = v10 - (_QWORD)a3;
    v27 = (char *)a3 + 4;
    do
    {
      *(_DWORD *)&v27[v26 + 11] = htonl(*((_DWORD *)v27 - 1));
      v27[v26 + 15] = *v27;
      v27 += 5;
      --v25;
    }
    while ( v25 );
  }
  Options = CMcTpConstructor::ServerSecurePacket(this, v9);
  if ( !ElValidateWin32(Options, v28, "base\\eco\\wds\\transport\\lib\\mctpconstructor.cpp", 0xADDu) )
  {
    if ( g_ErrLibTraceFunctionEx )
      g_ErrLibTraceFunctionEx(
        0x400000u,
        L"MCTPConstruct[KICK]: Session=0x%x, ClientCount=%u",
        *((unsigned int *)this + 1),
        v5);
    *a4 = v9;
  }
  if ( Options )
    goto LABEL_29;
  return Options;
}

```

## disassembly

```asm
0x18001e16c  mov     r11, rsp
0x18001e16f  mov     [r11+20h], r9
0x18001e173  mov     [r11+18h], r8
0x18001e177  push    rbx
0x18001e178  push    rbp
0x18001e179  push    rsi
0x18001e17a  push    rdi
0x18001e17b  push    r12
0x18001e17d  push    r13
0x18001e17f  push    r14
0x18001e181  push    r15
0x18001e183  sub     rsp, 48h
0x18001e187  xor     r12d, r12d
0x18001e18a  mov     eax, 0C8h
0x18001e18f  cmp     ax, dx
0x18001e192  mov     [r11-58h], r12
0x18001e196  movzx   r15d, dx
0x18001e19a  mov     r13, rcx
0x18001e19d  cmovb   r15w, ax
0x18001e1a2  lea     rcx, [r11+30h]
0x18001e1a6  mov     eax, [r11+28h]
0x18001e1aa  lea     ebx, [r12+2]
0x18001e1af  movzx   r14d, r15w
0x18001e1b3  mov     edi, r12d
0x18001e1b6  mov     [rsp+88h+var_58], eax
0x18001e1ba  mov     ebp, r12d
0x18001e1bd  lea     r8d, [r14+3]
0x18001e1c1  lea     r8d, [r8+r8*4]
0x18001e1c5  test    eax, eax
0x18001e1c7  jz      short loc_18001E1DB
0x18001e1c9  mov     edx, eax
0x18001e1cb  add     ebx, 4
0x18001e1ce  add     ebx, [rcx+8]
0x18001e1d1  lea     rcx, [rcx+18h]
0x18001e1d5  sub     rdx, 1
0x18001e1d9  jnz     short loc_18001E1CB
0x18001e1db  or      ecx, 0FFFFFFFFh
0x18001e1de  cmp     r8d, 0Fh
0x18001e1e2  mov     eax, ecx
0x18001e1e4  cmovnb  eax, r8d
0x18001e1e8  jnb     short loc_18001E1F7
0x18001e1ea  sbb     ebx, ebx
0x18001e1ec  and     ebx, 216h
0x18001e1f2  jmp     loc_18001E2AB
0x18001e1f7  lea     r8d, [rbx+rax]
0x18001e1fb  mov     edx, ecx
0x18001e1fd  cmp     r8d, eax
0x18001e200  cmovnb  edx, r8d
0x18001e204  jb      short loc_18001E1EA
0x18001e206  mov     r8d, [r13+64h]
0x18001e20a  add     r8d, edx
0x18001e20d  cmp     r8d, edx
0x18001e210  cmovnb  ecx, r8d; unsigned int
0x18001e214  jb      short loc_18001E1EA
0x18001e216  cmp     ecx, 0FFFFh
0x18001e21c  jbe     short loc_18001E228
0x18001e21e  mov     ebx, 6Fh ; 'o'
0x18001e223  jmp     loc_18001E37F
0x18001e228  call    ?TptMemoryBufferAllocate@@YAPEAVCMemoryBuffer@@K@Z; TptMemoryBufferAllocate(ulong)
0x18001e22d  mov     rsi, rax
0x18001e230  test    rax, rax
0x18001e233  jnz     short loc_18001E23D
0x18001e235  lea     ebx, [rax+8]
0x18001e238  jmp     loc_18001E37F
0x18001e23d  mov     rax, [rax+28h]
0x18001e241  mov     ecx, 4457h
0x18001e246  mov     [rax], cx
0x18001e249  mov     [rax+3], r12w
0x18001e24e  mov     r12d, [r13+64h]
0x18001e252  mov     ecx, [r13+4]; hostlong
0x18001e256  add     r12, [rsi+28h]
0x18001e25a  call    cs:__imp_htonl
0x18001e260  lea     rcx, [r13+68h]; this
0x18001e264  mov     byte ptr [r12+4], 0Eh
0x18001e26a  mov     [r12], eax
0x18001e26e  call    ?CurrentMs@CStopwatch@@QEAA_KXZ; CStopwatch::CurrentMs(void)
0x18001e273  mov     rcx, rax; unsigned __int64
0x18001e276  call    ?HostToNetworkByteOrder@CNetworkAddress@@SA_K_K@Z; CNetworkAddress::HostToNetworkByteOrder(unsigned __int64)
0x18001e27b  mov     ecx, [rsp+88h+var_58]; unsigned int
0x18001e27f  lea     r8d, [r14+r14*4]
0x18001e283  add     r8, 0Fh
0x18001e287  mov     [r12+5], rax
0x18001e28c  add     r8, r12; struct _WDSMCTP_OPTIONS *
0x18001e28f  lea     rdx, [rsp+88h+arg_28]; char *
0x18001e297  mov     r9d, ebx; unsigned int
0x18001e29a  call    ?CreateOptions@CMcTpOptions@@SAKKPEADPEAU_WDSMCTP_OPTIONS@@K@Z; CMcTpOptions::CreateOptions(ulong,char *,_WDSMCTP_OPTIONS *,ulong)
0x18001e29f  mov     ebx, eax
0x18001e2a1  test    eax, eax
0x18001e2a3  jnz     short loc_18001E2B2
0x18001e2a5  mov     rdi, rsi
0x18001e2a8  mov     rbp, r12
0x18001e2ab  mov     rsi, rdi
0x18001e2ae  test    ebx, ebx
0x18001e2b0  jz      short loc_18001E2CF
0x18001e2b2  test    rsi, rsi
0x18001e2b5  jz      short loc_18001E2C7
0x18001e2b7  mov     rax, [rsi]
0x18001e2ba  mov     rcx, rsi
0x18001e2bd  mov     rax, [rax+8]
0x18001e2c1  call    cs:__guard_dispatch_icall_fptr
0x18001e2c7  test    ebx, ebx
0x18001e2c9  jnz     loc_18001E36A
0x18001e2cf  movzx   ecx, r15w; hostshort
0x18001e2d3  call    cs:__imp_htons
0x18001e2d9  mov     [rbp+0Dh], ax
0x18001e2dd  test    r14d, r14d
0x18001e2e0  jz      short loc_18001E311
0x18001e2e2  mov     rax, [rsp+88h+arg_10]
0x18001e2ea  mov     rsi, r14
0x18001e2ed  sub     rbp, rax
0x18001e2f0  lea     rbx, [rax+4]
0x18001e2f4  mov     ecx, [rbx-4]; hostlong
0x18001e2f7  call    cs:__imp_htonl
0x18001e2fd  mov     [rbx+rbp+0Bh], eax
0x18001e301  mov     al, [rbx]
0x18001e303  mov     [rbx+rbp+0Fh], al
0x18001e307  lea     rbx, [rbx+5]
0x18001e30b  sub     rsi, 1
0x18001e30f  jnz     short loc_18001E2F4
0x18001e311  mov     rdx, rdi; struct CMemoryBuffer *
0x18001e314  mov     rcx, r13; this
0x18001e317  call    ?ServerSecurePacket@CMcTpConstructor@@AEAAKPEAVCMemoryBuffer@@@Z; CMcTpConstructor::ServerSecurePacket(CMemoryBuffer *)
0x18001e31c  mov     r9d, 0ADDh; unsigned int
0x18001e322  lea     r8, aBaseEcoWdsTran_17; "base\\eco\\wds\\transport\\lib\\mctpcon"...
0x18001e329  mov     ecx, eax; unsigned int
0x18001e32b  mov     ebx, eax
0x18001e32d  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001e332  test    eax, eax
0x18001e334  jnz     short loc_18001E366
0x18001e336  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001e33d  test    rax, rax
0x18001e340  jz      short loc_18001E35B
0x18001e342  mov     r8d, [r13+4]
0x18001e346  lea     rdx, aMctpconstructK; "MCTPConstruct[KICK]: Session=0x%x, Clie"...
0x18001e34d  mov     r9d, r14d
0x18001e350  mov     ecx, 400000h
0x18001e355  call    cs:__guard_dispatch_icall_fptr
0x18001e35b  mov     rax, [rsp+88h+arg_18]
0x18001e363  mov     [rax], rdi
0x18001e366  test    ebx, ebx
0x18001e368  jz      short loc_18001E37F
0x18001e36a  test    rdi, rdi
0x18001e36d  jz      short loc_18001E37F
0x18001e36f  mov     rax, [rdi]
0x18001e372  mov     rcx, rdi
0x18001e375  mov     rax, [rax+8]
0x18001e379  call    cs:__guard_dispatch_icall_fptr
0x18001e37f  mov     eax, ebx
0x18001e381  add     rsp, 48h
0x18001e385  pop     r15
0x18001e387  pop     r14
0x18001e389  pop     r13
0x18001e38b  pop     r12
0x18001e38d  pop     rdi
0x18001e38e  pop     rsi
0x18001e38f  pop     rbp
0x18001e390  pop     rbx
0x18001e391  retn
```
