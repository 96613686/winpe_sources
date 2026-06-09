# ReadAllocFormat12CharGlyphMapList

- ea: `0x180017694`
- end: `0x180017914`
- name: `ReadAllocFormat12CharGlyphMapList`
- size: `640`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001d5f8`

## callees

- `0x1800134a0`
- `0x180013dac`
- `0x1800164a0`
- `0x180017694`
- `0x18001e7c4`
- `0x18002a590`

## pseudocode

```c
__int64 __fastcall ReadAllocFormat12CharGlyphMapList(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int16 a4,
        void **a5,
        unsigned int *a6)
{
  unsigned int v7; // r15d
  __int64 result; // rax
  __int64 v9; // rbx
  unsigned int v10; // esi
  unsigned int i; // edx
  unsigned __int64 v12; // rax
  __int64 v13; // rax
  unsigned int v14; // edx
  unsigned int v15; // r11d
  __int64 v16; // r9
  unsigned int v17; // r8d
  int v18; // ecx
  unsigned int v19; // r10d
  _QWORD *v20; // rbx
  unsigned int v21; // eax
  unsigned int v22; // ecx
  unsigned int v23; // r8d
  __int64 v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rcx
  unsigned int v27; // edx
  __int64 v28; // r8
  unsigned int v29; // r9d
  __int64 v30; // [rsp+20h] [rbp-48h] BYREF
  __int128 v31; // [rsp+28h] [rbp-40h] BYREF

  v7 = a4;
  v30 = 0;
  *a5 = 0;
  *a6 = 0;
  v31 = 0;
  result = ReadAllocCmapFormat12(a1, a2, &v31, &v30);
  if ( !(_WORD)result )
  {
    v9 = v30;
    v10 = 0;
    for ( i = 0; i < HIDWORD(v31); ++i )
    {
      v23 = *(_DWORD *)(v30 + 12LL * i + 4);
      if ( v23 >= *(_DWORD *)(v30 + 12LL * i) )
      {
        v21 = v23 - *(_DWORD *)(v30 + 12LL * i);
        v22 = v21 + 1;
        if ( v21 + 1 < v21 || v22 + v10 < v10 || v23 == -1 )
          goto LABEL_21;
        v10 += v22;
      }
    }
    if ( !v10 )
    {
      v24 = Mem_Alloc(8u);
      *a5 = (void *)v24;
      v25 = v9;
      if ( v24 )
      {
        Mem_Free(v9);
        *(_DWORD *)*a5 = 0;
        *((_DWORD *)*a5 + 1) = 0;
        *a6 = 1;
        return 0;
      }
      goto LABEL_33;
    }
    v12 = 8LL * v10;
    if ( v12 <= 0xFFFFFFFF )
    {
      v13 = Mem_Alloc((unsigned int)v12);
      *a5 = (void *)v13;
      if ( v13 )
      {
        v14 = 0;
        *a6 = v10;
        v15 = 0;
        if ( !HIDWORD(v31) )
          goto LABEL_34;
        v16 = 0;
        do
        {
          v17 = *(_DWORD *)(v9 + 12 * v16);
          if ( *(_DWORD *)(v9 + 12 * v16 + 4) >= v17 )
          {
            v18 = *(_DWORD *)(v9 + 12 * v16);
            do
            {
              v19 = v17 + *(_DWORD *)(v9 + 12 * v16 + 8) - v18;
              if ( (_WORD)v17 + *(_WORD *)(v9 + 12 * v16 + 8) - (_WORD)v18
                && v19 < v7
                && *(_BYTE *)((unsigned __int16)v19 + a3) )
              {
                v26 = v14++;
                *((_DWORD *)*a5 + 2 * v26) = v17;
                *((_DWORD *)*a5 + 2 * v26 + 1) = v19;
                v18 = *(_DWORD *)(v9 + 12 * v16);
              }
              ++v17;
            }
            while ( v17 <= *(_DWORD *)(v9 + 12 * v16 + 4) );
          }
          ++v15;
          ++v16;
        }
        while ( v15 < HIDWORD(v31) );
        if ( !v14 )
        {
LABEL_34:
          v14 = 1;
          *(_DWORD *)*a5 = 0;
          *((_DWORD *)*a5 + 1) = 0;
        }
        *a6 = v14;
        Mem_Free(v9);
        v20 = *a5;
        if ( *a5 && *a6 )
        {
          qsort_0(*a5, *a6, 8u, AscendingTagCompare);
          v27 = *a6;
          LODWORD(v28) = 0;
          if ( *a6 > 1 )
          {
            v29 = 1;
            do
            {
              if ( LODWORD(v20[(unsigned int)v28]) != LODWORD(v20[v29]) )
              {
                v28 = (unsigned int)(v28 + 1);
                if ( v29 > (unsigned int)v28 )
                {
                  v20[v28] = v20[v29];
                  v27 = *a6;
                }
              }
              ++v29;
            }
            while ( v29 < v27 );
          }
          *a6 = v28 + 1;
        }
        return 0;
      }
      v25 = v9;
LABEL_33:
      Mem_Free(v25);
      return 1005;
    }
LABEL_21:
    Mem_Free(v30);
    return 1006;
  }
  return result;
}

```

## disassembly

```asm
0x180017694  mov     r11, rsp
0x180017697  mov     [r11+18h], rbx
0x18001769b  mov     [r11+20h], rsi
0x18001769f  push    rdi
0x1800176a0  push    r12
0x1800176a2  push    r13
0x1800176a4  push    r14
0x1800176a6  push    r15
0x1800176a8  sub     rsp, 40h
0x1800176ac  mov     rax, cs:__security_cookie
0x1800176b3  xor     rax, rsp
0x1800176b6  mov     [rsp+68h+var_30], rax
0x1800176bb  mov     rdi, [rsp+68h+arg_20]
0x1800176c3  xor     r13d, r13d
0x1800176c6  mov     r14, [rsp+68h+arg_28]
0x1800176ce  mov     r12, r8
0x1800176d1  movzx   r15d, r9w
0x1800176d5  lea     r8, [r11-40h]
0x1800176d9  xorps   xmm0, xmm0
0x1800176dc  mov     [r11-48h], r13
0x1800176e0  mov     [rdi], r13
0x1800176e3  lea     r9, [r11-48h]
0x1800176e7  mov     [r14], r13d
0x1800176ea  movups  [rsp+68h+var_40], xmm0
0x1800176ef  call    ReadAllocCmapFormat12
0x1800176f4  test    ax, ax
0x1800176f7  jnz     loc_1800177DE
0x1800176fd  mov     rbx, [rsp+68h+var_48]
0x180017702  mov     esi, r13d
0x180017705  mov     edx, r13d
0x180017708  mov     r9d, 0FFFFFFFFh
0x18001770e  cmp     edx, dword ptr [rsp+68h+var_40+0Ch]
0x180017712  jb      loc_180017814
0x180017718  test    esi, esi
0x18001771a  jz      loc_180017835
0x180017720  mov     eax, esi
0x180017722  shl     rax, 3
0x180017726  cmp     rax, r9
0x180017729  ja      loc_1800177D1
0x18001772f  mov     ecx, eax; Size
0x180017731  call    Mem_Alloc
0x180017736  mov     [rdi], rax
0x180017739  test    rax, rax
0x18001773c  jz      loc_180017868
0x180017742  mov     edx, r13d
0x180017745  mov     [r14], esi
0x180017748  mov     r11d, r13d
0x18001774b  cmp     dword ptr [rsp+68h+var_40+0Ch], r13d
0x180017750  jbe     loc_180017895
0x180017756  mov     r9, r13
0x180017759  lea     rsi, [r9+r9*2]
0x18001775d  mov     r8d, [rbx+rsi*4]
0x180017761  cmp     [rbx+rsi*4+4], r8d
0x180017766  jb      short loc_180017799
0x180017768  mov     ecx, r8d
0x18001776b  mov     r10d, [rbx+rsi*4+8]
0x180017770  sub     r10d, ecx
0x180017773  add     r10d, r8d
0x180017776  test    r10w, r10w
0x18001777a  jz      short loc_18001778F
0x18001777c  cmp     r10d, r15d
0x18001777f  jnb     short loc_18001778F
0x180017781  movzx   eax, r10w
0x180017785  cmp     [rax+r12], r13b
0x180017789  jnz     loc_18001787A
0x18001778f  inc     r8d
0x180017792  cmp     r8d, [rbx+rsi*4+4]
0x180017797  jbe     short loc_18001776B
0x180017799  inc     r11d
0x18001779c  inc     r9
0x18001779f  cmp     r11d, dword ptr [rsp+68h+var_40+0Ch]
0x1800177a4  jb      short loc_180017759
0x1800177a6  test    edx, edx
0x1800177a8  jz      loc_180017895
0x1800177ae  mov     rcx, rbx
0x1800177b1  mov     [r14], edx
0x1800177b4  call    Mem_Free
0x1800177b9  mov     rbx, [rdi]
0x1800177bc  test    rbx, rbx
0x1800177bf  jnz     loc_1800178AC
0x1800177c5  mov     eax, r13d
0x1800177c8  jmp     short loc_1800177DE
0x1800177ca  lea     eax, [rcx+rsi]
0x1800177cd  cmp     eax, esi
0x1800177cf  jnb     short loc_180017827
0x1800177d1  mov     rcx, rbx
0x1800177d4  call    Mem_Free
0x1800177d9  mov     eax, 3EEh
0x1800177de  mov     rcx, [rsp+68h+var_30]
0x1800177e3  xor     rcx, rsp; StackCookie
0x1800177e6  call    __security_check_cookie
0x1800177eb  lea     r11, [rsp+68h+var_28]
0x1800177f0  mov     rbx, [r11+40h]
0x1800177f4  mov     rsi, [r11+48h]
0x1800177f8  mov     rsp, r11
0x1800177fb  pop     r15
0x1800177fd  pop     r14
0x1800177ff  pop     r13
0x180017801  pop     r12
0x180017803  pop     rdi
0x180017804  retn
0x180017805  mov     eax, r8d
0x180017808  sub     eax, [rbx+rcx*4]
0x18001780b  lea     ecx, [rax+1]
0x18001780e  cmp     ecx, eax
0x180017810  jb      short loc_1800177D1
0x180017812  jmp     short loc_1800177CA
0x180017814  mov     eax, edx
0x180017816  lea     rcx, [rax+rax*2]
0x18001781a  mov     r8d, [rbx+rcx*4+4]
0x18001781f  cmp     r8d, [rbx+rcx*4]
0x180017823  jb      short loc_18001782E
0x180017825  jmp     short loc_180017805
0x180017827  cmp     r8d, r9d
0x18001782a  jz      short loc_1800177D1
0x18001782c  mov     esi, eax
0x18001782e  inc     edx
0x180017830  jmp     loc_18001770E
0x180017835  mov     ecx, 8; Size
0x18001783a  call    Mem_Alloc
0x18001783f  mov     [rdi], rax
0x180017842  mov     rcx, rbx
0x180017845  test    rax, rax
0x180017848  jz      short loc_18001786B
0x18001784a  call    Mem_Free
0x18001784f  mov     rax, [rdi]
0x180017852  mov     [rax], r13d
0x180017855  mov     rax, [rdi]
0x180017858  mov     [rax+4], r13d
0x18001785c  mov     dword ptr [r14], 1
0x180017863  jmp     loc_1800177C5
0x180017868  mov     rcx, rbx
0x18001786b  call    Mem_Free
0x180017870  mov     eax, 3EDh
0x180017875  jmp     loc_1800177DE
0x18001787a  mov     rax, [rdi]
0x18001787d  mov     ecx, edx
0x18001787f  inc     edx
0x180017881  mov     [rax+rcx*8], r8d
0x180017885  mov     rax, [rdi]
0x180017888  mov     [rax+rcx*8+4], r10d
0x18001788d  mov     ecx, [rbx+rsi*4]
0x180017890  jmp     loc_18001778F
0x180017895  mov     rax, [rdi]
0x180017898  mov     edx, 1
0x18001789d  mov     [rax], r13d
0x1800178a0  mov     rax, [rdi]
0x1800178a3  mov     [rax+4], r13d
0x1800178a7  jmp     loc_1800177AE
0x1800178ac  cmp     [r14], r13d
0x1800178af  jz      loc_1800177C5
0x1800178b5  mov     edx, [r14]; NumOfElements
0x1800178b8  lea     r9, AscendingTagCompare; CompareFunction
0x1800178bf  mov     r8d, 8; SizeOfElements
0x1800178c5  mov     rcx, rbx; Base
0x1800178c8  call    qsort_0
0x1800178cd  mov     edx, [r14]
0x1800178d0  mov     r8d, r13d
0x1800178d3  cmp     edx, 1
0x1800178d6  jbe     short loc_180017908
0x1800178d8  mov     r9d, 1
0x1800178de  mov     r10d, r9d
0x1800178e1  mov     ecx, r8d
0x1800178e4  mov     eax, [rbx+r10*8]
0x1800178e8  cmp     [rbx+rcx*8], eax
0x1800178eb  jz      short loc_180017900
0x1800178ed  inc     r8d
0x1800178f0  cmp     r9d, r8d
0x1800178f3  jbe     short loc_180017900
0x1800178f5  mov     rax, [rbx+r10*8]
0x1800178f9  mov     [rbx+r8*8], rax
0x1800178fd  mov     edx, [r14]
0x180017900  inc     r9d
0x180017903  cmp     r9d, edx
0x180017906  jb      short loc_1800178DE
0x180017908  lea     eax, [r8+1]
0x18001790c  mov     [r14], eax
0x18001790f  jmp     loc_1800177C5
```
