# WMNewOpenResizerWithFullCropping

- ea: `0x180012e30`
- end: `0x18001321c`
- name: `WMNewOpenResizerWithFullCropping`
- size: `1004`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180007e90`
- `0x180012dd0`

## callees

- `0x180001968`
- `0x1800019b4`
- `0x180011b40`
- `0x180011bc0`
- `0x180012e30`
- `0x180013560`
- `0x180013a00`

## pseudocode

```c
__int64 __fastcall WMNewOpenResizerWithFullCropping(
        __int64 a1,
        WMSDKRESIZER **a2,
        int a3,
        int a4,
        int a5,
        int a6,
        int a7,
        int a8,
        int a9,
        int a10,
        int a11,
        int a12,
        int a13,
        int a14)
{
  unsigned int v14; // r10d
  int v15; // esi
  int v19; // edx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // r9d
  int v25; // ecx
  int v26; // r9d
  int v27; // ecx
  int v28; // r9d
  int v29; // r11d
  int v30; // ecx
  int v31; // r9d
  int v32; // ecx
  int v33; // r9d
  int v34; // r10d
  unsigned int v35; // ebp
  int v36; // ebx
  bool v37; // zf
  __int64 result; // rax
  unsigned __int64 v39; // rdx
  WMSDKRESIZER *v40; // rdi
  int v41; // ecx
  int v42; // ecx
  bool v43; // cc
  void *v44; // rcx
  void *v45; // rcx
  unsigned __int64 v46; // rbx
  unsigned __int64 v47; // r9
  void *v48; // rax
  void *v49; // rax

  v14 = *(_DWORD *)(a1 + 16);
  v15 = a4;
  if ( v14 > 3 )
  {
    v15 = -a4;
    if ( a4 > 0 )
      v15 = a4;
  }
  if ( v14
    && v14 != 3
    && v14 != 1448433985
    && v14 != 1498831189
    && v14 != 844715353
    && v14 != 909193814
    && v14 != 1448433993
    && v14 != 808596553
    && v14 != 842094169
    && v14 != 842150992 )
  {
    goto LABEL_69;
  }
  if ( !a2 )
    return 1;
  if ( a3 < 0 || a5 < 0 || a6 < 0 || a7 < 1 || a8 < 1 || a9 < 0 || a10 < 0 || a11 < 1 || a12 < 1 )
    goto LABEL_69;
  v19 = *(_DWORD *)(a1 + 4);
  v20 = -v19;
  if ( v19 > 0 )
    v20 = v19;
  if ( a5 + a7 > v20 )
    goto LABEL_69;
  v21 = -*(_DWORD *)(a1 + 8);
  if ( *(int *)(a1 + 8) > 0 )
    v21 = *(_DWORD *)(a1 + 8);
  if ( a8 + a6 > v21 || a9 + a11 > a3 )
    goto LABEL_69;
  v22 = -v15;
  if ( v15 > 0 )
    v22 = v15;
  if ( a10 + a12 > v22
    || CheckSize(v14, v19, *(_DWORD *)(a1 + 8), a14)
    || CheckSize(v23, a3, v15, v24)
    || CheckSize(v25, a7, a8, v26)
    || CheckSize(v27, v29, a12, v28)
    || CheckSize(v30, a5, a6, v31)
    || CheckSize(v32, a9, a10, v33) )
  {
LABEL_69:
    *a2 = 0;
    return 1;
  }
  v35 = 0;
  if ( v34 == 825308240 )
  {
    v36 = 1;
    goto LABEL_53;
  }
  if ( v34 != 1448433993 && v34 != 808596553 && v34 != 842094169 )
  {
    if ( !v34 )
    {
      v37 = *(_WORD *)(a1 + 14) == 32;
      goto LABEL_51;
    }
    if ( v34 != 1498831189 && v34 != 844715353 && v34 != 1448433985 )
    {
      v37 = v34 == 842150992;
LABEL_51:
      v36 = 0;
      if ( !v37 )
        goto LABEL_53;
    }
  }
  v36 = a13;
LABEL_53:
  result = WMOpenResizer_old((__int128 *)a1, a2, a3, v15, v36);
  if ( !(_DWORD)result )
  {
    v40 = *a2;
    v41 = -*(_DWORD *)(a1 + 4);
    if ( *(int *)(a1 + 4) > 0 )
      v41 = *(_DWORD *)(a1 + 4);
    *((_DWORD *)v40 + 12) = v41;
    v42 = *(_DWORD *)(a1 + 8);
    if ( *(_DWORD *)(a1 + 16) > 3u )
    {
      v42 = -v42;
      if ( v42 < 0 )
        v42 = *(_DWORD *)(a1 + 8);
    }
    *((_DWORD *)v40 + 13) = v42;
    *((_DWORD *)v40 + 14) = a3;
    v43 = v42 <= 0;
    *((_DWORD *)v40 + 270) = v36;
    v44 = (void *)*((_QWORD *)v40 + 137);
    if ( v43 )
      v15 = -v15;
    *((_DWORD *)v40 + 271) = a14;
    *((_DWORD *)v40 + 15) = v15;
    if ( v44 )
    {
      operator delete(v44, v39);
      *((_QWORD *)v40 + 137) = 0;
    }
    v45 = (void *)*((_QWORD *)v40 + 138);
    if ( v45 )
    {
      operator delete(v45, v39);
      *((_QWORD *)v40 + 138) = 0;
    }
    WMSDKRESIZER::BMPSize(v40, *((_DWORD *)v40 + 12), *((_DWORD *)v40 + 13));
    v46 = (int)WMSDKRESIZER::BMPSize(v40, *((_DWORD *)v40 + 14), *((_DWORD *)v40 + 15));
    v48 = operator new[](v47);
    *((_QWORD *)v40 + 137) = v48;
    if ( v48 && (v49 = operator new[](v46), (*((_QWORD *)v40 + 138) = v49) != 0) )
    {
      LOBYTE(v35) = (unsigned int)WMResetCropping(
                                    a2,
                                    (unsigned int)a5,
                                    (unsigned int)a6,
                                    (unsigned int)a7,
                                    a8,
                                    a9,
                                    a10,
                                    a11,
                                    a12) != 0;
      return v35;
    }
    else
    {
      return 2147500037LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180012e30  push    rsi
0x180012e32  push    r12
0x180012e34  push    r13
0x180012e36  push    r14
0x180012e38  sub     rsp, 58h
0x180012e3c  mov     r10d, [rcx+10h]
0x180012e40  mov     esi, r9d
0x180012e43  mov     r13d, r8d
0x180012e46  mov     r12, rdx
0x180012e49  mov     r14, rcx
0x180012e4c  cmp     r10d, 3
0x180012e50  jbe     short loc_180012E58
0x180012e52  neg     esi
0x180012e54  cmovs   esi, r9d
0x180012e58  mov     [rsp+78h+arg_0], rbx
0x180012e60  mov     [rsp+78h+arg_8], rbp
0x180012e68  mov     [rsp+78h+arg_10], rdi
0x180012e70  mov     [rsp+78h+var_28], r15
0x180012e75  test    r10d, r10d
0x180012e78  jz      short loc_180012ECC
0x180012e7a  cmp     r10d, 3
0x180012e7e  jz      short loc_180012ECC
0x180012e80  cmp     r10d, 56555941h
0x180012e87  jz      short loc_180012ECC
0x180012e89  cmp     r10d, 59565955h
0x180012e90  jz      short loc_180012ECC
0x180012e92  cmp     r10d, 32595559h
0x180012e99  jz      short loc_180012ECC
0x180012e9b  cmp     r10d, 36313256h
0x180012ea2  jz      short loc_180012ECC
0x180012ea4  cmp     r10d, 56555949h
0x180012eab  jz      short loc_180012ECC
0x180012ead  cmp     r10d, 30323449h
0x180012eb4  jz      short loc_180012ECC
0x180012eb6  cmp     r10d, 32315659h
0x180012ebd  jz      short loc_180012ECC
0x180012ebf  cmp     r10d, 32323450h
0x180012ec6  jnz     loc_1800131E8
0x180012ecc  test    r12, r12
0x180012ecf  jz      loc_1800131EE
0x180012ed5  test    r13d, r13d
0x180012ed8  js      loc_1800131E8
0x180012ede  mov     edi, [rsp+78h+arg_20]
0x180012ee5  test    edi, edi
0x180012ee7  js      loc_1800131E8
0x180012eed  cmp     [rsp+78h+arg_28], 0
0x180012ef5  jl      loc_1800131E8
0x180012efb  mov     eax, [rsp+78h+arg_30]
0x180012f02  cmp     eax, 1
0x180012f05  jl      loc_1800131E8
0x180012f0b  mov     r15d, [rsp+78h+arg_38]
0x180012f13  cmp     r15d, 1
0x180012f17  jl      loc_1800131E8
0x180012f1d  mov     ebx, [rsp+78h+arg_40]
0x180012f24  test    ebx, ebx
0x180012f26  js      loc_1800131E8
0x180012f2c  mov     r9d, [rsp+78h+arg_48]
0x180012f34  test    r9d, r9d
0x180012f37  js      loc_1800131E8
0x180012f3d  mov     r11d, [rsp+78h+arg_50]
0x180012f45  cmp     r11d, 1
0x180012f49  jl      loc_1800131E8
0x180012f4f  mov     ebp, [rsp+78h+arg_58]
0x180012f56  cmp     ebp, 1
0x180012f59  jl      loc_1800131E8
0x180012f5f  mov     edx, [rcx+4]; int
0x180012f62  mov     ecx, edx
0x180012f64  neg     ecx
0x180012f66  cmovs   ecx, edx
0x180012f69  add     eax, edi
0x180012f6b  cmp     eax, ecx
0x180012f6d  jg      loc_1800131E8
0x180012f73  mov     r8d, [r14+8]; int
0x180012f77  mov     ecx, r8d
0x180012f7a  mov     eax, [rsp+78h+arg_28]
0x180012f81  neg     ecx
0x180012f83  cmovs   ecx, r8d
0x180012f87  add     eax, r15d
0x180012f8a  cmp     eax, ecx
0x180012f8c  jg      loc_1800131E8
0x180012f92  lea     eax, [rbx+r11]
0x180012f96  cmp     eax, r13d
0x180012f99  jg      loc_1800131E8
0x180012f9f  mov     ecx, esi
0x180012fa1  lea     eax, [r9+rbp]
0x180012fa5  neg     ecx
0x180012fa7  cmovs   ecx, esi
0x180012faa  cmp     eax, ecx
0x180012fac  jg      loc_1800131E8
0x180012fb2  mov     r15d, [rsp+78h+arg_68]
0x180012fba  mov     ecx, r10d; int
0x180012fbd  mov     r9d, r15d; int
0x180012fc0  call    ?CheckSize@@YAJJJJH@Z; CheckSize(long,long,long,int)
0x180012fc5  test    eax, eax
0x180012fc7  jnz     loc_1800131E8
0x180012fcd  mov     r8d, esi; int
0x180012fd0  mov     edx, r13d; int
0x180012fd3  call    ?CheckSize@@YAJJJJH@Z; CheckSize(long,long,long,int)
0x180012fd8  test    eax, eax
0x180012fda  jnz     loc_1800131E8
0x180012fe0  mov     r8d, [rsp+78h+arg_38]; int
0x180012fe8  mov     edx, [rsp+78h+arg_30]; int
0x180012fef  call    ?CheckSize@@YAJJJJH@Z; CheckSize(long,long,long,int)
0x180012ff4  test    eax, eax
0x180012ff6  jnz     loc_1800131E8
0x180012ffc  mov     r8d, ebp; int
0x180012fff  mov     edx, r11d; int
0x180013002  call    ?CheckSize@@YAJJJJH@Z; CheckSize(long,long,long,int)
0x180013007  test    eax, eax
0x180013009  jnz     loc_1800131E8
0x18001300f  mov     r8d, [rsp+78h+arg_28]; int
0x180013017  mov     edx, edi; int
0x180013019  call    ?CheckSize@@YAJJJJH@Z; CheckSize(long,long,long,int)
0x18001301e  test    eax, eax
0x180013020  jnz     loc_1800131E8
0x180013026  mov     r8d, [rsp+78h+arg_48]; int
0x18001302e  mov     edx, ebx; int
0x180013030  call    ?CheckSize@@YAJJJJH@Z; CheckSize(long,long,long,int)
0x180013035  test    eax, eax
0x180013037  jnz     loc_1800131E8
0x18001303d  xor     ebp, ebp
0x18001303f  cmp     r10d, 31313450h
0x180013046  jnz     short loc_18001304F
0x180013048  mov     ebx, 1
0x18001304d  jmp     short loc_1800130A4
0x18001304f  cmp     r10d, 56555949h
0x180013056  jz      short loc_18001309D
0x180013058  cmp     r10d, 30323449h
0x18001305f  jz      short loc_18001309D
0x180013061  cmp     r10d, 32315659h
0x180013068  jz      short loc_18001309D
0x18001306a  test    r10d, r10d
0x18001306d  jnz     short loc_180013077
0x18001306f  cmp     word ptr [r14+0Eh], 20h ; ' '
0x180013075  jmp     short loc_180013099
0x180013077  cmp     r10d, 59565955h
0x18001307e  jz      short loc_18001309D
0x180013080  cmp     r10d, 32595559h
0x180013087  jz      short loc_18001309D
0x180013089  cmp     r10d, 56555941h
0x180013090  jz      short loc_18001309D
0x180013092  cmp     r10d, 32323450h
0x180013099  mov     ebx, ebp
0x18001309b  jnz     short loc_1800130A4
0x18001309d  mov     ebx, [rsp+78h+arg_60]
0x1800130a4  mov     r9d, esi
0x1800130a7  mov     [rsp+78h+var_58], ebx
0x1800130ab  mov     r8d, r13d
0x1800130ae  mov     rdx, r12
0x1800130b1  mov     rcx, r14
0x1800130b4  call    WMOpenResizer_old
0x1800130b9  test    eax, eax
0x1800130bb  jnz     loc_1800131F3
0x1800130c1  mov     ecx, [r14+4]
0x1800130c5  mov     rdi, [r12]
0x1800130c9  neg     ecx
0x1800130cb  cmovs   ecx, [r14+4]
0x1800130d0  mov     [rdi+30h], ecx
0x1800130d3  cmp     dword ptr [r14+10h], 3
0x1800130d8  mov     ecx, [r14+8]
0x1800130dc  jbe     short loc_1800130E5
0x1800130de  mov     eax, ecx
0x1800130e0  neg     ecx
0x1800130e2  cmovs   ecx, eax
0x1800130e5  mov     eax, esi
0x1800130e7  mov     [rdi+34h], ecx
0x1800130ea  neg     eax
0x1800130ec  mov     [rdi+38h], r13d
0x1800130f0  test    ecx, ecx
0x1800130f2  mov     [rdi+438h], ebx
0x1800130f8  mov     rcx, [rdi+448h]; void *
0x1800130ff  cmovle  esi, eax
0x180013102  mov     [rdi+43Ch], r15d
0x180013109  mov     [rdi+3Ch], esi
0x18001310c  test    rcx, rcx
0x18001310f  jz      short loc_18001311D
0x180013111  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180013116  mov     [rdi+448h], rbp
0x18001311d  mov     rcx, [rdi+450h]; void *
0x180013124  test    rcx, rcx
0x180013127  jz      short loc_180013135
0x180013129  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001312e  mov     [rdi+450h], rbp
0x180013135  mov     edx, [rdi+30h]; int
0x180013138  mov     rcx, rdi; this
0x18001313b  mov     r8d, [rdi+34h]; int
0x18001313f  call    ?BMPSize@WMSDKRESIZER@@QEAAJJJ@Z; WMSDKRESIZER::BMPSize(long,long)
0x180013144  mov     edx, [rdi+38h]; int
0x180013147  mov     rcx, rdi; this
0x18001314a  mov     r8d, [rdi+3Ch]; int
0x18001314e  movsxd  r9, eax
0x180013151  call    ?BMPSize@WMSDKRESIZER@@QEAAJJJ@Z; WMSDKRESIZER::BMPSize(long,long)
0x180013156  mov     rcx, r9; unsigned __int64
0x180013159  movsxd  rbx, eax
0x18001315c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180013161  mov     [rdi+448h], rax
0x180013168  test    rax, rax
0x18001316b  jz      short loc_1800131E1
0x18001316d  mov     rcx, rbx; unsigned __int64
0x180013170  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180013175  mov     [rdi+450h], rax
0x18001317c  test    rax, rax
0x18001317f  jz      short loc_1800131E1
0x180013181  mov     eax, [rsp+78h+arg_58]
0x180013188  mov     rcx, r12
0x18001318b  mov     r9d, [rsp+78h+arg_30]
0x180013193  mov     r8d, [rsp+78h+arg_28]
0x18001319b  mov     edx, [rsp+78h+arg_20]
0x1800131a2  mov     [rsp+78h+var_38], eax
0x1800131a6  mov     eax, [rsp+78h+arg_50]
0x1800131ad  mov     [rsp+78h+var_40], eax
0x1800131b1  mov     eax, [rsp+78h+arg_48]
0x1800131b8  mov     [rsp+78h+var_48], eax
0x1800131bc  mov     eax, [rsp+78h+arg_40]
0x1800131c3  mov     [rsp+78h+var_50], eax
0x1800131c7  mov     eax, [rsp+78h+arg_38]
0x1800131ce  mov     [rsp+78h+var_58], eax
0x1800131d2  call    WMResetCropping
0x1800131d7  test    eax, eax
0x1800131d9  setnz   bpl
0x1800131dd  mov     eax, ebp
0x1800131df  jmp     short loc_1800131F3
0x1800131e1  mov     eax, 80004005h
0x1800131e6  jmp     short loc_1800131F3
0x1800131e8  xor     ebp, ebp
0x1800131ea  mov     [r12], rbp
0x1800131ee  mov     eax, 1
0x1800131f3  mov     r15, [rsp+78h+var_28]
0x1800131f8  mov     rdi, [rsp+78h+arg_10]
0x180013200  mov     rbp, [rsp+78h+arg_8]
0x180013208  mov     rbx, [rsp+78h+arg_0]
0x180013210  add     rsp, 58h
0x180013214  pop     r14
0x180013216  pop     r13
0x180013218  pop     r12
0x18001321a  pop     rsi
0x18001321b  retn
```
