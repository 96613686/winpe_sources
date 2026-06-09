# CMcTpConstructor::CreateDemote(ulong,tagWDS_ENDPOINT *,tagWDS_ENDPOINT *,ushort,ulong *,CMemoryBuffer * *,ulong,...)

- ea: `0x18001e398`
- end: `0x18001e733`
- name: `?CreateDemote@CMcTpConstructor@@QEAAKKPEAUtagWDS_ENDPOINT@@0GPEAKPEAPEAVCMemoryBuffer@@KZZ`
- size: `923`
- prototype: `unsigned int(CMcTpConstructor *__hidden this, unsigned int, struct tagWDS_ENDPOINT *, struct tagWDS_ENDPOINT *, unsigned __int16, unsigned int *, struct CMemoryBuffer **, unsigned int, ...)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18000ec74`

## callees

- `0x180003c0c`
- `0x180008f4c`
- `0x18001d4f4`
- `0x18001e398`
- `0x180020258`
- `0x180023b28`
- `0x1800247d4`
- `0x180025850`
- `0x180026670`
- `0x180026d3a`
- `0x180026d70`

## import_xrefs

- `WS2_32!__imp_htonl` at `0x18001e4d2`
- `WS2_32!__imp_htonl` at `0x18001e550`
- `WS2_32!__imp_htonl` at `0x18001e57e`
- `WS2_32!__imp_htonl` at `0x18001e4d2`
- `WS2_32!__imp_htonl` at `0x18001e550`
- `WS2_32!__imp_htonl` at `0x18001e57e`
- `WS2_32!__imp_htons` at `0x18001e55e`
- `WS2_32!__imp_htons` at `0x18001e59d`
- `WS2_32!__imp_htons` at `0x18001e5ca`
- `WS2_32!__imp_htons` at `0x18001e55e`
- `WS2_32!__imp_htons` at `0x18001e59d`
- `WS2_32!__imp_htons` at `0x18001e5ca`

## pseudocode

```c
__int64 CMcTpConstructor::CreateDemote(
        CMcTpConstructor *this,
        u_long a2,
        struct tagWDS_ENDPOINT *a3,
        struct tagWDS_ENDPOINT *a4,
        u_short a5,
        unsigned int *a6,
        struct CMemoryBuffer **a7,
        unsigned int a8,
        ...)
{
  u_short v9; // r13
  u_long *v10; // r15
  va_list v11; // rcx
  unsigned int v12; // edi
  struct CMemoryBuffer *v13; // rsi
  unsigned int v14; // r8d
  __int64 v15; // r14
  __int64 v16; // rdx
  unsigned int v17; // edx
  bool v18; // cf
  unsigned int Options; // edi
  unsigned int v20; // r8d
  unsigned int v21; // edx
  unsigned int v22; // r8d
  struct CMemoryBuffer *v23; // rax
  struct CMemoryBuffer *v24; // rbx
  _WORD *v25; // rax
  __int64 v26; // r12
  LONGLONG v27; // rax
  __int64 v28; // rdi
  const char *v29; // rdx
  size_t v30; // r8
  const unsigned __int16 *v31; // rbx
  const unsigned __int16 *v32; // r9
  __int64 v38; // [rsp+80h] [rbp-80h] BYREF
  __int64 v39; // [rsp+88h] [rbp-78h]
  unsigned int v40; // [rsp+90h] [rbp-70h]
  int v41; // [rsp+A0h] [rbp-60h] BYREF
  char v42; // [rsp+A4h] [rbp-5Ch] BYREF
  int v43; // [rsp+130h] [rbp+30h] BYREF
  char v44; // [rsp+134h] [rbp+34h] BYREF
  va_list va; // [rsp+260h] [rbp+160h] BYREF

  va_start(va, a8);
  v9 = a5;
  v10 = a6;
  va_copy(v11, va);
  if ( a5 > 0xFAu )
    v9 = 250;
  v12 = 2;
  v13 = 0;
  v14 = 4 * v9;
  v15 = 0;
  if ( a8 )
  {
    v16 = a8;
    do
    {
      v12 += *((_DWORD *)v11 + 2) + 4;
      v11 += 24;
      --v16;
    }
    while ( v16 );
  }
  v17 = v14 + 57;
  v18 = v14 >= 0xFFFFFFC7;
  if ( v14 >= 0xFFFFFFC7
    || (v20 = v12 + v17, v18 = v12 + v17 < v17)
    || (v21 = v12 + v17, v22 = v20 + *((_DWORD *)this + 25), v18 = v22 < v21) )
  {
    Options = v18 ? 0x216 : 0;
  }
  else
  {
    if ( v22 > 0xFFFF )
      return 111;
    v23 = TptMemoryBufferAllocate(v22);
    v24 = v23;
    if ( !v23 )
      return 8;
    v25 = (_WORD *)*((_QWORD *)v23 + 5);
    *v25 = 17495;
    *(_WORD *)((char *)v25 + 3) = 0;
    v26 = *((_QWORD *)v24 + 5) + *((unsigned int *)this + 25);
    *(_DWORD *)v26 = htonl(*((_DWORD *)this + 1));
    *(_BYTE *)(v26 + 4) = 15;
    v27 = CStopwatch::CurrentMs((CMcTpConstructor *)((char *)this + 104));
    *(_QWORD *)(v26 + 5) = CNetworkAddress::HostToNetworkByteOrder(v27);
    Options = CMcTpOptions::CreateOptions(a8, va, (struct _WDSMCTP_OPTIONS *)(v26 + 4 * (unsigned int)v9 + 57LL), v12);
    if ( Options )
      goto LABEL_17;
    v13 = v24;
    v15 = v26;
  }
  v24 = v13;
  if ( Options )
  {
LABEL_17:
    if ( v24 )
      (*(void (__fastcall **)(struct CMemoryBuffer *))(*(_QWORD *)v24 + 8LL))(v24);
LABEL_32:
    if ( v13 )
      (*(void (__fastcall **)(struct CMemoryBuffer *))(*(_QWORD *)v13 + 8LL))(v13);
    return Options;
  }
  *(_DWORD *)(v15 + 13) = htonl(a2);
  *(_WORD *)(v15 + 55) = htons(v9);
  if ( v9 )
  {
    v28 = v9;
    do
    {
      *(u_long *)((char *)v10 + v15 - (_QWORD)a6 + 57) = htonl(*v10);
      ++v10;
      --v28;
    }
    while ( v28 );
  }
  *(_WORD *)(v15 + 34) = htons(*((_WORD *)a3 + 6));
  *(_BYTE *)(v15 + 17) = *((_BYTE *)a3 + 32);
  memmove_0((void *)(v15 + 18), (char *)a3 + 16, *((unsigned int *)a3 + 8));
  *(_WORD *)(v15 + 53) = htons(*((_WORD *)a4 + 6));
  *(_BYTE *)(v15 + 36) = *((_BYTE *)a4 + 32);
  memmove_0((void *)(v15 + 37), (char *)a4 + 16, *((unsigned int *)a4 + 8));
  Options = CMcTpConstructor::ServerSecurePacket(this, v13);
  if ( !ElValidateWin32(Options, v29, "base\\eco\\wds\\transport\\lib\\mctpconstructor.cpp", 0xB47u) )
  {
    if ( g_ErrLibTraceFunctionEx )
    {
      v38 = 0;
      v39 = 0;
      v40 = *((_DWORD *)a4 + 8);
      memmove_0(&v38, (char *)a4 + 16, v40);
      CIPString::Initialize((CIPString *)&v41, (struct tagWDS_IP_ADDRESS6 *)&v38);
      v30 = *((unsigned int *)a3 + 8);
      v31 = (const unsigned __int16 *)&v42;
      v40 = *((_DWORD *)a3 + 8);
      if ( v41 )
        v31 = L"<<Failed>>";
      v38 = 0;
      v39 = 0;
      memmove_0(&v38, (char *)a3 + 16, v30);
      CIPString::Initialize((CIPString *)&v43, (struct tagWDS_IP_ADDRESS6 *)&v38);
      v32 = (const unsigned __int16 *)&v44;
      if ( v43 )
        v32 = L"<<Failed>>";
      g_ErrLibTraceFunctionEx(
        0x400000u,
        L"MCTPConstruct[DEMOTE]: Session=0x%x, MAddr=%s:%u, UAddr:%s:%u, ClientCount=%u",
        *((unsigned int *)this + 1),
        v32,
        *((unsigned __int16 *)a3 + 6),
        v31,
        *((unsigned __int16 *)a4 + 6),
        v9);
    }
    *a7 = v13;
  }
  if ( Options )
    goto LABEL_32;
  return Options;
}

```

## disassembly

```asm
0x18001e398  push    rbp
0x18001e39a  push    rbx
0x18001e39b  push    rsi
0x18001e39c  push    rdi
0x18001e39d  push    r12
0x18001e39f  push    r13
0x18001e3a1  push    r14
0x18001e3a3  push    r15
0x18001e3a5  lea     rbp, [rsp-0D8h]
0x18001e3ad  sub     rsp, 1D8h
0x18001e3b4  mov     rax, cs:__security_cookie
0x18001e3bb  xor     rax, rsp
0x18001e3be  mov     [rbp+110h+var_50], rax
0x18001e3c5  mov     rax, [rbp+110h+arg_30]
0x18001e3cc  mov     r12, rcx
0x18001e3cf  movzx   r13d, [rbp+110h+arg_20]
0x18001e3d7  mov     r15, [rbp+110h+arg_28]
0x18001e3de  mov     [rsp+210h+var_198], rax
0x18001e3e3  mov     eax, 0FAh
0x18001e3e8  mov     [rsp+210h+var_1A0], r8
0x18001e3ed  mov     [rsp+210h+var_1B0], r9
0x18001e3f2  xor     r9d, r9d
0x18001e3f5  cmp     ax, r13w
0x18001e3f9  mov     [rsp+210h+var_1B8], rcx
0x18001e3fe  mov     qword ptr [rsp+210h+var_1A8], r9
0x18001e403  lea     rcx, [rbp+110h+arg_40]
0x18001e40a  cmovb   r13w, ax
0x18001e40f  mov     [rsp+210h+hostlong], edx
0x18001e413  mov     eax, [rbp+110h+arg_38]
0x18001e419  lea     edi, [r9+2]
0x18001e41d  movzx   r8d, r13w
0x18001e421  mov     esi, r9d
0x18001e424  shl     r8d, 2
0x18001e428  mov     r14d, r9d
0x18001e42b  mov     [rsp+210h+var_1A8], eax
0x18001e42f  mov     [rsp+210h+var_1C0], r8d
0x18001e434  test    eax, eax
0x18001e436  jz      short loc_18001E44A
0x18001e438  mov     edx, eax
0x18001e43a  add     edi, 4
0x18001e43d  add     edi, [rcx+8]
0x18001e440  lea     rcx, [rcx+18h]
0x18001e444  sub     rdx, 1
0x18001e448  jnz     short loc_18001E43A
0x18001e44a  lea     edx, [r8+39h]
0x18001e44e  or      ecx, 0FFFFFFFFh
0x18001e451  cmp     edx, 39h ; '9'
0x18001e454  mov     eax, ecx
0x18001e456  cmovnb  eax, edx
0x18001e459  jnb     short loc_18001E468
0x18001e45b  sbb     edi, edi
0x18001e45d  and     edi, 216h
0x18001e463  jmp     loc_18001E528
0x18001e468  lea     r8d, [rdi+rax]
0x18001e46c  mov     edx, ecx
0x18001e46e  cmp     r8d, eax
0x18001e471  cmovnb  edx, r8d
0x18001e475  jb      short loc_18001E45B
0x18001e477  mov     r8d, [r12+64h]
0x18001e47c  add     r8d, edx
0x18001e47f  cmp     r8d, edx
0x18001e482  cmovnb  ecx, r8d; unsigned int
0x18001e486  jb      short loc_18001E45B
0x18001e488  cmp     ecx, 0FFFFh
0x18001e48e  jbe     short loc_18001E49A
0x18001e490  mov     edi, 6Fh ; 'o'
0x18001e495  jmp     loc_18001E70E
0x18001e49a  call    ?TptMemoryBufferAllocate@@YAPEAVCMemoryBuffer@@K@Z; TptMemoryBufferAllocate(ulong)
0x18001e49f  xor     edx, edx
0x18001e4a1  mov     rbx, rax
0x18001e4a4  test    rax, rax
0x18001e4a7  jnz     short loc_18001E4B1
0x18001e4a9  lea     edi, [rax+8]
0x18001e4ac  jmp     loc_18001E70E
0x18001e4b1  mov     rax, [rax+28h]
0x18001e4b5  mov     ecx, 4457h
0x18001e4ba  mov     [rax], cx
0x18001e4bd  mov     [rax+3], dx
0x18001e4c1  mov     rax, [rsp+210h+var_1B8]
0x18001e4c6  mov     r12d, [r12+64h]
0x18001e4cb  add     r12, [rbx+28h]
0x18001e4cf  mov     ecx, [rax+4]; hostlong
0x18001e4d2  call    cs:__imp_htonl
0x18001e4d8  mov     rcx, [rsp+210h+var_1B8]
0x18001e4dd  add     rcx, 68h ; 'h'; this
0x18001e4e1  mov     [r12], eax
0x18001e4e5  mov     byte ptr [r12+4], 0Fh
0x18001e4eb  call    ?CurrentMs@CStopwatch@@QEAA_KXZ; CStopwatch::CurrentMs(void)
0x18001e4f0  mov     rcx, rax; unsigned __int64
0x18001e4f3  call    ?HostToNetworkByteOrder@CNetworkAddress@@SA_K_K@Z; CNetworkAddress::HostToNetworkByteOrder(unsigned __int64)
0x18001e4f8  mov     r8d, [rsp+210h+var_1C0]
0x18001e4fd  lea     rdx, [rbp+110h+arg_40]; char *
0x18001e504  mov     ecx, [rsp+210h+var_1A8]; unsigned int
0x18001e508  add     r8, 39h ; '9'
0x18001e50c  add     r8, r12; struct _WDSMCTP_OPTIONS *
0x18001e50f  mov     [r12+5], rax
0x18001e514  mov     r9d, edi; unsigned int
0x18001e517  call    ?CreateOptions@CMcTpOptions@@SAKKPEADPEAU_WDSMCTP_OPTIONS@@K@Z; CMcTpOptions::CreateOptions(ulong,char *,_WDSMCTP_OPTIONS *,ulong)
0x18001e51c  mov     edi, eax
0x18001e51e  test    eax, eax
0x18001e520  jnz     short loc_18001E52F
0x18001e522  mov     rsi, rbx
0x18001e525  mov     r14, r12
0x18001e528  mov     rbx, rsi
0x18001e52b  test    edi, edi
0x18001e52d  jz      short loc_18001E54C
0x18001e52f  test    rbx, rbx
0x18001e532  jz      short loc_18001E544
0x18001e534  mov     rax, [rbx]
0x18001e537  mov     rcx, rbx
0x18001e53a  mov     rax, [rax+8]
0x18001e53e  call    cs:__guard_dispatch_icall_fptr
0x18001e544  test    edi, edi
0x18001e546  jnz     loc_18001E6F9
0x18001e54c  mov     ecx, [rsp+210h+hostlong]; hostlong
0x18001e550  call    cs:__imp_htonl
0x18001e556  movzx   ecx, r13w; hostshort
0x18001e55a  mov     [r14+0Dh], eax
0x18001e55e  call    cs:__imp_htons
0x18001e564  movzx   r12d, r13w
0x18001e568  mov     [r14+37h], ax
0x18001e56d  test    r12d, r12d
0x18001e570  jz      short loc_18001E593
0x18001e572  mov     rbx, r14
0x18001e575  mov     edi, r12d
0x18001e578  sub     rbx, r15
0x18001e57b  mov     ecx, [r15]; hostlong
0x18001e57e  call    cs:__imp_htonl
0x18001e584  mov     [rbx+r15+39h], eax
0x18001e589  lea     r15, [r15+4]
0x18001e58d  sub     rdi, 1
0x18001e591  jnz     short loc_18001E57B
0x18001e593  mov     r13, [rsp+210h+var_1A0]
0x18001e598  movzx   ecx, word ptr [r13+0Ch]; hostshort
0x18001e59d  call    cs:__imp_htons
0x18001e5a3  mov     [r14+22h], ax
0x18001e5a8  lea     rcx, [r14+12h]; void *
0x18001e5ac  mov     al, [r13+20h]
0x18001e5b0  lea     rdx, [r13+10h]; Src
0x18001e5b4  mov     [r14+11h], al
0x18001e5b8  mov     r8d, [r13+20h]; Size
0x18001e5bc  call    memmove_0
0x18001e5c1  mov     rdi, [rsp+210h+var_1B0]
0x18001e5c6  movzx   ecx, word ptr [rdi+0Ch]; hostshort
0x18001e5ca  call    cs:__imp_htons
0x18001e5d0  mov     [r14+35h], ax
0x18001e5d5  lea     rbx, [rdi+10h]
0x18001e5d9  mov     al, [rdi+20h]
0x18001e5dc  lea     rcx, [r14+25h]; void *
0x18001e5e0  mov     [r14+24h], al
0x18001e5e4  mov     rdx, rbx; Src
0x18001e5e7  mov     r8d, [rdi+20h]; Size
0x18001e5eb  call    memmove_0
0x18001e5f0  mov     r14, [rsp+210h+var_1B8]
0x18001e5f5  mov     rdx, rsi; struct CMemoryBuffer *
0x18001e5f8  mov     rcx, r14; this
0x18001e5fb  call    ?ServerSecurePacket@CMcTpConstructor@@AEAAKPEAVCMemoryBuffer@@@Z; CMcTpConstructor::ServerSecurePacket(CMemoryBuffer *)
0x18001e600  mov     r9d, 0B47h; unsigned int
0x18001e606  lea     r8, aBaseEcoWdsTran_17; "base\\eco\\wds\\transport\\lib\\mctpcon"...
0x18001e60d  mov     ecx, eax; unsigned int
0x18001e60f  mov     edi, eax
0x18001e611  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001e616  xor     r9d, r9d
0x18001e619  test    eax, eax
0x18001e61b  jnz     loc_18001E6F5
0x18001e621  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, r9; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001e628  jz      loc_18001E6ED
0x18001e62e  xor     eax, eax
0x18001e630  lea     rcx, [rbp+110h+var_190]; void *
0x18001e634  mov     [rbp+110h+var_190], rax
0x18001e638  mov     rdx, rbx; Src
0x18001e63b  mov     [rbp+110h+var_188], rax
0x18001e63f  mov     rax, [rsp+210h+var_1B0]
0x18001e644  mov     r8d, [rax+20h]; Size
0x18001e648  mov     [rbp+110h+var_180], r8d
0x18001e64c  call    memmove_0
0x18001e651  lea     rdx, [rbp+110h+var_190]; struct tagWDS_IP_ADDRESS6 *
0x18001e655  lea     rcx, [rbp+110h+var_170]; this
0x18001e659  call    ?Initialize@CIPString@@QEAAKPEAUtagWDS_IP_ADDRESS6@@@Z; CIPString::Initialize(tagWDS_IP_ADDRESS6 *)
0x18001e65e  mov     r8d, [r13+20h]; Size
0x18001e662  lea     rax, aFailed; "<<Failed>>"
0x18001e669  cmp     [rbp+110h+var_170], 0
0x18001e66d  lea     rbx, [rbp+110h+var_16C]
0x18001e671  lea     rdx, [r13+10h]; Src
0x18001e675  mov     [rbp+110h+var_180], r8d
0x18001e679  cmovnz  rbx, rax
0x18001e67d  lea     rcx, [rbp+110h+var_190]; void *
0x18001e681  xor     eax, eax
0x18001e683  mov     [rbp+110h+var_190], rax
0x18001e687  mov     [rbp+110h+var_188], rax
0x18001e68b  call    memmove_0
0x18001e690  lea     rdx, [rbp+110h+var_190]; struct tagWDS_IP_ADDRESS6 *
0x18001e694  lea     rcx, [rbp+110h+var_E0]; this
0x18001e698  call    ?Initialize@CIPString@@QEAAKPEAUtagWDS_IP_ADDRESS6@@@Z; CIPString::Initialize(tagWDS_IP_ADDRESS6 *)
0x18001e69d  mov     rax, [rsp+210h+var_1B0]
0x18001e6a2  lea     rdx, aFailed; "<<Failed>>"
0x18001e6a9  cmp     [rbp+110h+var_E0], 0
0x18001e6ad  lea     r9, [rbp+110h+var_DC]
0x18001e6b1  mov     r8d, [r14+4]
0x18001e6b5  mov     [rsp+210h+var_1D8], r12d
0x18001e6ba  cmovnz  r9, rdx
0x18001e6be  movzx   ecx, word ptr [rax+0Ch]
0x18001e6c2  lea     rdx, aMctpconstructD; "MCTPConstruct[DEMOTE]: Session=0x%x, MA"...
0x18001e6c9  movzx   eax, word ptr [r13+0Ch]
0x18001e6ce  mov     [rsp+210h+var_1E0], ecx
0x18001e6d2  mov     ecx, 400000h
0x18001e6d7  mov     [rsp+210h+var_1E8], rbx
0x18001e6dc  mov     [rsp+210h+var_1F0], eax
0x18001e6e0  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001e6e7  call    cs:__guard_dispatch_icall_fptr
0x18001e6ed  mov     rax, [rsp+210h+var_198]
0x18001e6f2  mov     [rax], rsi
0x18001e6f5  test    edi, edi
0x18001e6f7  jz      short loc_18001E70E
0x18001e6f9  test    rsi, rsi
0x18001e6fc  jz      short loc_18001E70E
0x18001e6fe  mov     rax, [rsi]
0x18001e701  mov     rcx, rsi
0x18001e704  mov     rax, [rax+8]
0x18001e708  call    cs:__guard_dispatch_icall_fptr
0x18001e70e  mov     eax, edi
0x18001e710  mov     rcx, [rbp+110h+var_50]
0x18001e717  xor     rcx, rsp; StackCookie
0x18001e71a  call    __security_check_cookie
0x18001e71f  add     rsp, 1D8h
0x18001e726  pop     r15
0x18001e728  pop     r14
0x18001e72a  pop     r13
0x18001e72c  pop     r12
0x18001e72e  pop     rdi
0x18001e72f  pop     rsi
0x18001e730  pop     rbx
0x18001e731  pop     rbp
0x18001e732  retn
```
