# CTls13ServerHandshake::ParseClientHello(uchar *,ulong,uchar * const,ulong *,ulong * *,ulong *)

- ea: `0x18005614c`
- end: `0x1800564f9`
- name: `?ParseClientHello@CTls13ServerHandshake@@QEAAKPEAEKQEAEPEAKPEAPEAK2@Z`
- size: `941`
- prototype: `unsigned int(CTls13ServerHandshake *__hidden this, unsigned __int8 *, unsigned int, unsigned __int8 *const, unsigned int *, unsigned int **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180045ed0`

## callees

- `0x18000dc60`
- `0x18001e7e0`
- `0x1800214f0`
- `0x180021da8`
- `0x18005614c`
- `0x18006fcc8`
- `0x180088a54`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x1800561ff`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x1800562bc`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x1800561ff`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x1800562bc`

## pseudocode

```c
__int64 __fastcall CTls13ServerHandshake::ParseClientHello(
        CTls13ServerHandshake *this,
        unsigned __int8 *a2,
        unsigned int a3,
        unsigned __int8 *const a4,
        unsigned int *a5,
        unsigned int **a6,
        unsigned int *a7)
{
  unsigned __int8 *v7; // r13
  unsigned int v9; // ebx
  __int64 v10; // rcx
  __int64 v11; // rdx
  unsigned int v12; // esi
  int v13; // r15d
  unsigned __int8 *v14; // rbx
  unsigned int v15; // esi
  unsigned int v16; // eax
  unsigned int *Memory; // r15
  size_t v19; // rbp
  unsigned int v20; // esi
  unsigned __int16 *v21; // r14
  unsigned int v22; // esi
  unsigned int v23; // edx
  unsigned int v24; // esi
  unsigned __int16 v25; // bx
  unsigned int v26; // ebp
  unsigned __int16 v27; // si
  unsigned __int16 i; // r8
  __int64 v29; // rdx
  __int64 v30; // r9
  unsigned int v31; // ebp
  __int64 v32; // rax
  unsigned __int8 *v33; // rcx
  unsigned __int16 *v34; // rdx
  unsigned int v35; // r8d
  unsigned int v36; // ecx
  unsigned int v37; // eax

  v7 = a4;
  if ( a2 && a3 && a5 && a6 && a7 )
  {
    if ( a3 < 2 )
    {
      v9 = -2146893048;
LABEL_20:
      v16 = 0;
      Memory = 0;
LABEL_21:
      *a6 = Memory;
      *a7 = v16;
      return v9;
    }
    v10 = *((_QWORD *)this + 1);
    if ( (a2[1] | (*a2 << 8)) < 0x300u )
    {
      LOBYTE(a4) = 70;
      v11 = 1201;
LABEL_19:
      v9 = -2146893048;
      CSslContext::SetErrorAndFatalAlert(v10, v11, 2148074248LL, a4);
      goto LABEL_20;
    }
    v12 = a3 - 2;
    if ( a3 - 2 < 0x20 )
      goto LABEL_17;
    v13 = *(_DWORD *)(v10 + 92);
    v14 = a2 + 2;
    if ( v13 == 71 )
    {
      if ( RtlCompareMemory(a2 + 2, (const void *)(v10 + 1992), 0x20u) != 32 )
      {
LABEL_13:
        v10 = *((_QWORD *)this + 1);
        LOBYTE(a4) = 47;
LABEL_18:
        v11 = 1200;
        goto LABEL_19;
      }
    }
    else
    {
      *(_OWORD *)(v10 + 1992) = *(_OWORD *)v14;
      *(_OWORD *)(v10 + 2008) = *(_OWORD *)(a2 + 18);
    }
    v15 = v12 - 32;
    if ( v15 && (v19 = v14[32], (unsigned __int8)v19 <= 0x20u) && (v20 = v15 - 1, v20 >= (unsigned int)v19) )
    {
      if ( v13 == 71 )
      {
        v10 = *((_QWORD *)this + 1);
        if ( *(_BYTE *)(v10 + 3001) != (_BYTE)v19 )
        {
          LOBYTE(a4) = 47;
          goto LABEL_18;
        }
      }
      if ( (_BYTE)v19 )
      {
        if ( v13 == 71 )
        {
          if ( *((_QWORD *)this + 1) == -2969 )
          {
            v9 = -2146893052;
            goto LABEL_20;
          }
          if ( RtlCompareMemory(v14 + 33, (const void *)(*((_QWORD *)this + 1) + 2969LL), v14[32]) != v19 )
            goto LABEL_13;
        }
        memcpy_0(v7, v14 + 33, v19);
      }
      *a5 = v19;
      v21 = (unsigned __int16 *)&v14[v19 + 33];
      v10 = *((_QWORD *)this + 1);
      v22 = v20 - v19;
      if ( *(_BYTE *)(v10 + 1953) )
      {
        if ( !v22 )
          goto LABEL_17;
        if ( *(_BYTE *)v21 > 0x20u )
          goto LABEL_17;
        v23 = *(unsigned __int8 *)v21;
        v24 = v22 - 1;
        if ( v24 < v23 )
          goto LABEL_17;
        v21 = (unsigned __int16 *)((char *)v21 + *(unsigned __int8 *)v21 + 1);
        v22 = v24 - v23;
      }
      if ( v22 >= 2 )
      {
        v25 = _byteswap_ushort(*v21);
        if ( v25 >= 2u && (v25 & 1) == 0 )
        {
          v26 = v22 - 2;
          if ( v22 - 2 >= v25 )
          {
            v27 = v25 >> 1;
            Memory = (unsigned int *)CSslContext::GetMemory((CSslContext *)v10, 4LL * (v25 >> 1), 0);
            if ( !Memory )
            {
              if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  35,
                  WPP_ca7b144d2da03908b1ea89985908c21d_Traceguids,
                  4 * (unsigned int)v27);
              }
              v9 = 14;
              goto LABEL_20;
            }
            for ( i = 0; i < v27; Memory[v29] = HIBYTE(v21[v29 + 1]) | (LOBYTE(v21[v29 + 1]) << 8) )
              v29 = i++;
            CSchannelTelemetryContext::LogClientCiphers(
              (CSchannelTelemetryContext *)(*((_QWORD *)this + 1) + 144LL),
              Memory,
              v27);
            v31 = v26 - v25;
            if ( !v31 )
              goto LABEL_50;
            v32 = *((unsigned __int8 *)v21 + v25 + 2);
            if ( !(_BYTE)v32 )
            {
              v9 = -2146893048;
LABEL_67:
              (*(void (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)this + 1) + 16LL))(
                *((_QWORD *)this + 1),
                Memory);
              goto LABEL_20;
            }
            v30 = *((unsigned __int8 *)v21 + v25 + 2);
            if ( v31 - 1 >= (unsigned int)v32 )
            {
              v33 = (unsigned __int8 *)v21 + v25 + 3;
              v34 = (unsigned __int16 *)&v33[v32];
              while ( *v33 )
              {
                if ( v33 == (unsigned __int8 *)((char *)v34 - 1) )
                  goto LABEL_50;
                ++v33;
              }
              v9 = 0;
              v35 = v31 - 1 - v32;
              if ( v35 < 2
                || (v36 = (*(unsigned __int8 *)v34 << 8) | *((unsigned __int8 *)v34 + 1), v35 - 2 < v36)
                || (LOBYTE(v30) = 1,
                    v37 = CTlsExt::ParseTlsExtensions(*((__int64 **)this + 2), v34 + 1, v36, v30),
                    (v9 = v37) == 0) )
              {
                v16 = v27;
                goto LABEL_21;
              }
              if ( v37 == -2146892986
                || v37 == -2146892953
                || v37 == -2146893018 && *(_BYTE *)(*((_QWORD *)this + 1) + 121LL) == 47 )
              {
                goto LABEL_67;
              }
              LOBYTE(v30) = 10;
            }
            else
            {
LABEL_50:
              LOBYTE(v30) = 50;
            }
            v9 = -2146893048;
            CSslContext::SetErrorAndFatalAlert(*((_QWORD *)this + 1), 1200, 2148074248LL, v30);
            goto LABEL_67;
          }
        }
      }
    }
    else
    {
      v10 = *((_QWORD *)this + 1);
    }
LABEL_17:
    LOBYTE(a4) = 50;
    goto LABEL_18;
  }
  return 87;
}

```

## disassembly

```asm
0x18005614c  push    rbx
0x18005614e  push    rbp
0x18005614f  push    rsi
0x180056150  push    rdi
0x180056151  push    r12
0x180056153  push    r13
0x180056155  push    r14
0x180056157  push    r15
0x180056159  sub     rsp, 28h
0x18005615d  mov     r13, r9
0x180056160  mov     r10, rdx
0x180056163  mov     rdi, rcx
0x180056166  test    rdx, rdx
0x180056169  jz      loc_1800564E3
0x18005616f  test    r8d, r8d
0x180056172  jz      loc_1800564E3
0x180056178  mov     r12, [rsp+68h+arg_20]
0x180056180  test    r12, r12
0x180056183  jz      loc_1800564E3
0x180056189  cmp     [rsp+68h+arg_28], 0
0x180056192  jz      loc_1800564E3
0x180056198  cmp     [rsp+68h+arg_30], 0
0x1800561a1  jz      loc_1800564E3
0x1800561a7  cmp     r8d, 2
0x1800561ab  jnb     short loc_1800561B7
0x1800561ad  mov     ebx, 80090308h
0x1800561b2  jmp     loc_18005624A
0x1800561b7  movzx   edx, byte ptr [rdx]
0x1800561ba  movzx   eax, byte ptr [r10+1]
0x1800561bf  mov     rcx, [rcx+8]
0x1800561c3  shl     edx, 8
0x1800561c6  or      edx, eax
0x1800561c8  cmp     edx, 300h
0x1800561ce  jnb     short loc_1800561DA
0x1800561d0  mov     r9b, 46h ; 'F'
0x1800561d3  mov     edx, 4B1h
0x1800561d8  jmp     short loc_18005623D
0x1800561da  lea     esi, [r8-2]
0x1800561de  cmp     esi, 20h ; ' '
0x1800561e1  jb      short loc_180056235
0x1800561e3  mov     r15d, [rcx+5Ch]
0x1800561e7  lea     rbx, [r10+2]
0x1800561eb  cmp     r15d, 47h ; 'G'
0x1800561ef  jnz     short loc_180056214
0x1800561f1  lea     rdx, [rcx+7C8h]; Source2
0x1800561f8  mov     rcx, rbx; Source1
0x1800561fb  lea     r8d, [r15-27h]; Length
0x1800561ff  call    cs:__imp_RtlCompareMemory
0x180056205  cmp     rax, 20h ; ' '
0x180056209  jz      short loc_180056229
0x18005620b  mov     rcx, [rdi+8]
0x18005620f  mov     r9b, 2Fh ; '/'
0x180056212  jmp     short loc_180056238
0x180056214  movups  xmm0, xmmword ptr [rbx]
0x180056217  movups  xmmword ptr [rcx+7C8h], xmm0
0x18005621e  movups  xmm1, xmmword ptr [rbx+10h]
0x180056222  movups  xmmword ptr [rcx+7D8h], xmm1
0x180056229  add     esi, 0FFFFFFE0h
0x18005622c  cmp     esi, 1
0x18005622f  jnb     short loc_18005626B
0x180056231  mov     rcx, [rdi+8]
0x180056235  mov     r9b, 32h ; '2'
0x180056238  mov     edx, 4B0h
0x18005623d  mov     ebx, 80090308h
0x180056242  mov     r8d, ebx
0x180056245  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
0x18005624a  xor     eax, eax
0x18005624c  xor     r15d, r15d
0x18005624f  mov     rcx, [rsp+68h+arg_28]
0x180056257  mov     [rcx], r15
0x18005625a  mov     rcx, [rsp+68h+arg_30]
0x180056262  mov     [rcx], eax
0x180056264  mov     eax, ebx
0x180056266  jmp     loc_1800564E8
0x18005626b  movzx   ebp, byte ptr [rbx+20h]
0x18005626f  cmp     bpl, 20h ; ' '
0x180056273  ja      short loc_180056231
0x180056275  dec     esi
0x180056277  cmp     esi, ebp
0x180056279  jb      short loc_180056231
0x18005627b  cmp     r15d, 47h ; 'G'
0x18005627f  jnz     short loc_180056293
0x180056281  mov     rcx, [rdi+8]
0x180056285  cmp     [rcx+0BB9h], bpl
0x18005628c  jz      short loc_180056293
0x18005628e  mov     r9b, 2Fh ; '/'
0x180056291  jmp     short loc_180056238
0x180056293  lea     r14, [rbx+21h]
0x180056297  test    bpl, bpl
0x18005629a  jz      short loc_1800562D9
0x18005629c  cmp     r15d, 47h ; 'G'
0x1800562a0  jnz     short loc_1800562CB
0x1800562a2  mov     rdx, [rdi+8]
0x1800562a6  add     rdx, 0B99h; Source2
0x1800562ad  jnz     short loc_1800562B6
0x1800562af  mov     ebx, 80090304h
0x1800562b4  jmp     short loc_18005624A
0x1800562b6  mov     r8, rbp; Length
0x1800562b9  mov     rcx, r14; Source1
0x1800562bc  call    cs:__imp_RtlCompareMemory
0x1800562c2  cmp     rax, rbp
0x1800562c5  jnz     loc_18005620B
0x1800562cb  mov     r8, rbp; Size
0x1800562ce  mov     rdx, r14; Src
0x1800562d1  mov     rcx, r13; void *
0x1800562d4  call    memcpy_0
0x1800562d9  mov     [r12], ebp
0x1800562dd  add     r14, rbp
0x1800562e0  mov     rcx, [rdi+8]; this
0x1800562e4  sub     esi, ebp
0x1800562e6  mov     r13d, 1
0x1800562ec  cmp     byte ptr [rcx+7A1h], 0
0x1800562f3  jz      short loc_180056322
0x1800562f5  cmp     esi, r13d
0x1800562f8  jb      loc_180056235
0x1800562fe  cmp     byte ptr [r14], 20h ; ' '
0x180056302  ja      loc_180056235
0x180056308  movzx   edx, byte ptr [r14]
0x18005630c  dec     esi
0x18005630e  cmp     esi, edx
0x180056310  jb      loc_180056235
0x180056316  movzx   eax, byte ptr [r14]
0x18005631a  inc     r14
0x18005631d  add     r14, rax
0x180056320  sub     esi, edx
0x180056322  mov     edx, 2
0x180056327  cmp     esi, edx
0x180056329  jb      loc_180056235
0x18005632f  movzx   ebx, byte ptr [r14]
0x180056333  movzx   eax, byte ptr [r14+1]
0x180056338  shl     bx, 8
0x18005633c  or      bx, ax
0x18005633f  cmp     bx, dx
0x180056342  jb      loc_180056235
0x180056348  test    r13b, bl
0x18005634b  jnz     loc_180056235
0x180056351  lea     ebp, [rsi-2]
0x180056354  movzx   r12d, bx
0x180056358  cmp     ebp, r12d
0x18005635b  jb      loc_180056235
0x180056361  movzx   esi, bx
0x180056364  xor     r8d, r8d; unsigned __int8
0x180056367  shr     si, 1
0x18005636a  movzx   edx, si
0x18005636d  shl     rdx, 2; unsigned __int64
0x180056371  call    ?GetMemory@CSslContext@@QEAAPEAX_KE@Z; CSslContext::GetMemory(unsigned __int64,uchar)
0x180056376  mov     r15, rax
0x180056379  test    rax, rax
0x18005637c  jnz     short loc_1800563BD
0x18005637e  mov     rcx, cs:WPP_GLOBAL_Control
0x180056385  lea     rax, WPP_GLOBAL_Control
0x18005638c  cmp     rcx, rax
0x18005638f  jz      short loc_1800563B3
0x180056391  test    [rcx+1Ch], r13b
0x180056395  jz      short loc_1800563B3
0x180056397  mov     rcx, [rcx+10h]
0x18005639b  lea     edx, [r15+23h]
0x18005639f  movzx   r9d, si
0x1800563a3  lea     r8, WPP_ca7b144d2da03908b1ea89985908c21d_Traceguids
0x1800563aa  shl     r9d, 2
0x1800563ae  call    WPP_SF_d
0x1800563b3  mov     ebx, 0Eh
0x1800563b8  jmp     loc_18005624A
0x1800563bd  xor     r8d, r8d
0x1800563c0  xor     eax, eax
0x1800563c2  cmp     ax, si
0x1800563c5  jnb     short loc_1800563EA
0x1800563c7  movzx   edx, r8w
0x1800563cb  add     r8w, r13w
0x1800563cf  movzx   ecx, byte ptr [r14+rdx*2+2]
0x1800563d5  movzx   eax, byte ptr [r14+rdx*2+3]
0x1800563db  shl     ecx, 8
0x1800563de  or      ecx, eax
0x1800563e0  mov     [r15+rdx*4], ecx
0x1800563e4  cmp     r8w, si
0x1800563e8  jb      short loc_1800563C7
0x1800563ea  mov     rcx, [rdi+8]
0x1800563ee  mov     rdx, r15; unsigned int *
0x1800563f1  add     rcx, 90h; this
0x1800563f8  movzx   r8d, si; unsigned int
0x1800563fc  call    ?LogClientCiphers@CSchannelTelemetryContext@@QEAAXPEAKK@Z; CSchannelTelemetryContext::LogClientCiphers(ulong *,ulong)
0x180056401  sub     ebp, r12d
0x180056404  cmp     ebp, r13d
0x180056407  jnb     short loc_180056411
0x180056409  mov     r9b, 32h ; '2'
0x18005640c  jmp     loc_1800564AD
0x180056411  movzx   ecx, bx
0x180056414  movzx   eax, byte ptr [rcx+r14+2]
0x18005641a  cmp     al, r13b
0x18005641d  jnb     short loc_180056429
0x18005641f  mov     ebx, 80090308h
0x180056424  jmp     loc_1800564C3
0x180056429  lea     r8d, [rbp-1]
0x18005642d  mov     r9d, eax
0x180056430  cmp     r8d, eax
0x180056433  jb      short loc_180056409
0x180056435  add     rcx, 3
0x180056439  add     rcx, r14
0x18005643c  lea     rdx, [rcx+rax]
0x180056440  cmp     byte ptr [rcx], 0
0x180056443  jz      short loc_180056453
0x180056445  lea     rax, [rdx-1]
0x180056449  cmp     rcx, rax
0x18005644c  jz      short loc_180056409
0x18005644e  add     rcx, r13
0x180056451  jmp     short loc_180056440
0x180056453  xor     ebx, ebx
0x180056455  sub     r8d, r9d
0x180056458  cmp     r8d, 2
0x18005645c  jb      short loc_1800564DB
0x18005645e  movzx   eax, byte ptr [rdx]
0x180056461  movzx   ecx, byte ptr [rdx+1]
0x180056465  shl     eax, 8
0x180056468  or      ecx, eax
0x18005646a  lea     eax, [r8-2]
0x18005646e  cmp     eax, ecx
0x180056470  jb      short loc_1800564DB
0x180056472  mov     r8d, ecx
0x180056475  add     rdx, 2
0x180056479  mov     rcx, [rdi+10h]
0x18005647d  mov     r9b, r13b
0x180056480  call    ?ParseTlsExtensions@CTlsExt@@QEAAKPEAEKW4eTlsHandshakeType@@@Z; CTlsExt::ParseTlsExtensions(uchar *,ulong,eTlsHandshakeType)
0x180056485  mov     ebx, eax
0x180056487  test    eax, eax
0x180056489  jz      short loc_1800564DB
0x18005648b  cmp     eax, 80090346h
0x180056490  jz      short loc_1800564C3
0x180056492  cmp     eax, 80090367h
0x180056497  jz      short loc_1800564C3
0x180056499  cmp     eax, 80090326h
0x18005649e  jnz     short loc_1800564AA
0x1800564a0  mov     rcx, [rdi+8]
0x1800564a4  cmp     byte ptr [rcx+79h], 2Fh ; '/'
0x1800564a8  jz      short loc_1800564C3
0x1800564aa  mov     r9b, 0Ah
0x1800564ad  mov     rcx, [rdi+8]
0x1800564b1  mov     ebx, 80090308h
0x1800564b6  mov     r8d, ebx
0x1800564b9  mov     edx, 4B0h
0x1800564be  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
0x1800564c3  mov     rcx, [rdi+8]
0x1800564c7  mov     rdx, r15
0x1800564ca  mov     rax, [rcx]
0x1800564cd  mov     rax, [rax+10h]
0x1800564d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800564d6  jmp     loc_18005624A
0x1800564db  movzx   eax, si
0x1800564de  jmp     loc_18005624F
0x1800564e3  mov     eax, 57h ; 'W'
0x1800564e8  add     rsp, 28h
0x1800564ec  pop     r15
0x1800564ee  pop     r14
0x1800564f0  pop     r13
0x1800564f2  pop     r12
0x1800564f4  pop     rdi
0x1800564f5  pop     rsi
0x1800564f6  pop     rbp
0x1800564f7  pop     rbx
0x1800564f8  retn
```
