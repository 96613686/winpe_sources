# CopyProxyResolveUrl(tagProxyResolveUrl const *,tagProxyResolveUrl * *)

- ea: `0x18003fad0`
- end: `0x180040002`
- name: `?CopyProxyResolveUrl@@YAJPEBUtagProxyResolveUrl@@PEAPEAU1@@Z`
- size: `1330`
- prototype: `__int64 __fastcall(const struct tagProxyResolveUrl *, struct tagProxyResolveUrl **)`
- caller_count: `5`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003ee10`
- `0x18004f4e0`
- `0x180067640`
- `0x18006a0f0`
- `0x1800bf524`

## callees

- `0x18003fad0`
- `0x1800403d4`
- `0x1800a2660`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003fb5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003fc2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003fd02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003fdaf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003fb5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003fc2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003fd02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003fdaf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003feb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fec5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fed7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ff1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ff39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ff58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003feb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fec5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fed7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ff1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ff39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ff58`

## pseudocode

```c
__int64 __fastcall CopyProxyResolveUrl(const struct tagProxyResolveUrl *a1, struct tagProxyResolveUrl **a2)
{
  _WORD *v2; // rbx
  void *v3; // rsi
  __int64 v4; // r13
  __int64 v5; // r14
  bool v6; // zf
  _WORD *v7; // rax
  _WORD *v8; // rdi
  __int64 v9; // r12
  __int64 v10; // r8
  __int64 v11; // rdx
  void *v12; // rax
  _WORD *v13; // rdx
  int v14; // ebx
  const struct tagProxyResolveUrl *v15; // r15
  void *v16; // rdi
  _WORD *v17; // rbx
  __int64 v18; // r15
  _WORD *v19; // rax
  _WORD *v20; // r14
  __int64 v21; // r8
  __int64 v22; // rdx
  void *v23; // rax
  _WORD *v24; // rdx
  int v25; // ebx
  _WORD *v26; // r14
  void *v27; // rbx
  unsigned int v28; // r13d
  _WORD *v29; // rax
  _WORD *v30; // r15
  unsigned __int64 v31; // r8
  void *v32; // rax
  _WORD *v33; // rdx
  int v34; // r14d
  _QWORD *v35; // rax
  struct tagProxyResolveUrl *v38; // [rsp+30h] [rbp-58h]
  __int64 v39; // [rsp+38h] [rbp-50h]
  struct tagProxyResolveUrl **v40; // [rsp+40h] [rbp-48h]

  v40 = a2;
  v38 = 0;
  if ( !a1 )
    return (unsigned int)-2147024809;
  v2 = (_WORD *)*((_QWORD *)a1 + 1);
  if ( !v2 )
    return (unsigned int)-2147024809;
  if ( !*(_QWORD *)a1 )
    return (unsigned int)-2147024809;
  v3 = 0;
  v4 = -1;
  v5 = -1;
  do
    v6 = v2[++v5] == 0;
  while ( !v6 );
  v7 = CoTaskMemAlloc((unsigned int)(2 * v5 + 2));
  v8 = v7;
  v9 = 2147483646;
  if ( !v7 )
  {
    v14 = -2147024882;
    goto LABEL_18;
  }
  memset_0(v7, 0, (unsigned int)(2 * v5 + 2));
  v10 = (unsigned int)(v5 + 1);
  if ( (_DWORD)v5 == -1 )
  {
    v14 = -2147024809;
    v12 = v8;
    goto LABEL_16;
  }
  if ( (unsigned int)(v5 + 1) <= 0x7FFFFFFFuLL )
  {
    v11 = 2147483646;
    v12 = v8;
    do
    {
      if ( !v11 )
        break;
      if ( !*v2 )
        break;
      *v8++ = *v2++;
      --v11;
      --v10;
    }
    while ( v10 );
    v13 = v8 - 1;
    v14 = -2147024774;
    if ( v10 )
    {
      v13 = v8;
      v14 = 0;
    }
    *v13 = 0;
LABEL_16:
    if ( v14 >= 0 )
    {
      v3 = v12;
      goto LABEL_18;
    }
    goto LABEL_73;
  }
  v14 = -2147024809;
  *v8 = 0;
  v12 = v8;
LABEL_73:
  if ( v12 )
    CoTaskMemFree(v12);
LABEL_18:
  if ( v14 >= 0 )
  {
    v15 = a1;
    v16 = 0;
    v17 = *(_WORD **)a1;
    if ( !*(_QWORD *)a1 )
      goto LABEL_36;
    v18 = -1;
    do
      v6 = v17[++v18] == 0;
    while ( !v6 );
    v19 = CoTaskMemAlloc((unsigned int)(2 * v18 + 2));
    v20 = v19;
    if ( !v19 )
    {
      v25 = -2147024882;
      goto LABEL_34;
    }
    memset_0(v19, 0, (unsigned int)(2 * v18 + 2));
    v21 = (unsigned int)(v18 + 1);
    if ( (_DWORD)v18 == -1 )
    {
      v25 = -2147024809;
      v23 = v20;
    }
    else
    {
      if ( (unsigned int)(v18 + 1) > 0x7FFFFFFFuLL )
      {
        v25 = -2147024809;
        *v20 = 0;
        v23 = v20;
        goto LABEL_71;
      }
      v22 = 2147483646;
      v23 = v20;
      do
      {
        if ( !v22 )
          break;
        if ( !*v17 )
          break;
        *v20++ = *v17++;
        --v22;
        --v21;
      }
      while ( v21 );
      v24 = v20 - 1;
      v25 = -2147024774;
      if ( v21 )
      {
        v24 = v20;
        v25 = 0;
      }
      *v24 = 0;
    }
    if ( v25 >= 0 )
    {
      v16 = v23;
LABEL_34:
      if ( v25 < 0 )
      {
        v34 = v25;
LABEL_62:
        if ( v16 )
          CoTaskMemFree(v16);
        goto LABEL_64;
      }
      v15 = a1;
      v4 = -1;
LABEL_36:
      v26 = (_WORD *)*((_QWORD *)v15 + 2);
      v27 = 0;
      if ( !v26 )
        goto LABEL_52;
      do
        ++v4;
      while ( v26[v4] );
      v39 = v4;
      v28 = 2 * v4 + 2;
      v29 = CoTaskMemAlloc(v28);
      v30 = v29;
      if ( !v29 )
      {
        v34 = -2147024882;
        goto LABEL_50;
      }
      memset_0(v29, 0, v28);
      v31 = (unsigned int)(v39 + 1);
      if ( (_DWORD)v39 == -1 )
      {
        v34 = -2147024809;
        v32 = v30;
      }
      else
      {
        if ( v31 > 0x7FFFFFFF )
        {
          v34 = -2147024809;
          *v30 = 0;
          v32 = v30;
          goto LABEL_69;
        }
        v32 = v30;
        do
        {
          if ( !v9 )
            break;
          if ( !*v26 )
            break;
          *v30++ = *v26++;
          --v9;
          --v31;
        }
        while ( v31 );
        v33 = v30 - 1;
        v34 = -2147024774;
        if ( v31 )
        {
          v33 = v30;
          v34 = 0;
        }
        *v33 = 0;
      }
      if ( v34 >= 0 )
      {
        v27 = v32;
LABEL_50:
        if ( v34 < 0 )
        {
LABEL_60:
          if ( v27 )
            CoTaskMemFree(v27);
          goto LABEL_62;
        }
        v15 = a1;
LABEL_52:
        HIDWORD(v39) = 0;
        v38 = 0;
        v35 = CoTaskMemAlloc(0x20u);
        if ( v35 )
        {
          *v35 = 0;
          v35[3] = 0;
          v35[1] = v3;
          *v35 = v16;
          v34 = 0;
          v35[2] = v27;
          *((_WORD *)v35 + 14) = *((_WORD *)v15 + 14);
          *((_DWORD *)v35 + 6) = *((_DWORD *)v15 + 6);
          v38 = 0;
          *v40 = (struct tagProxyResolveUrl *)v35;
          return (unsigned int)v34;
        }
        HIDWORD(v39) = 76;
        v34 = -2147024882;
        goto LABEL_60;
      }
LABEL_69:
      if ( v32 )
        CoTaskMemFree(v32);
      goto LABEL_50;
    }
LABEL_71:
    if ( v23 )
      CoTaskMemFree(v23);
    goto LABEL_34;
  }
  v34 = v14;
LABEL_64:
  if ( v3 )
    CoTaskMemFree(v3);
  return (unsigned int)v34;
}

```

## disassembly

```asm
0x18003fad0  mov     r11, rsp
0x18003fad3  push    r14
0x18003fad5  sub     rsp, 80h
0x18003fadc  mov     rax, rcx
0x18003fadf  mov     [rsp+88h+var_60], rcx
0x18003fae4  xor     ecx, ecx
0x18003fae6  mov     [r11-10h], rbp
0x18003faea  mov     [rsp+88h+var_48], rdx
0x18003faef  mov     ebp, ecx
0x18003faf1  mov     [rsp+88h+var_64], ecx
0x18003faf5  mov     [rsp+88h+var_58], rcx
0x18003fafa  test    rax, rax
0x18003fafd  jz      loc_18003FF63
0x18003fb03  mov     [r11+18h], rbx
0x18003fb07  mov     rbx, [rax+8]
0x18003fb0b  test    rbx, rbx
0x18003fb0e  jz      loc_18003FE3C
0x18003fb14  cmp     [rax], rcx
0x18003fb17  jz      loc_18003FF76
0x18003fb1d  mov     [r11-18h], rsi
0x18003fb21  mov     esi, ecx
0x18003fb23  mov     [r11-20h], rdi
0x18003fb27  mov     [r11-28h], r12
0x18003fb2b  mov     [r11-30h], r13
0x18003fb2f  mov     r13, 0FFFFFFFFFFFFFFFFh
0x18003fb36  mov     r14, r13
0x18003fb39  mov     [r11-38h], r15
0x18003fb3d  mov     [rsp+88h+var_64], ecx
0x18003fb41  cmp     [rbx+r14*2+2], cx
0x18003fb47  lea     r14, [r14+1]
0x18003fb4b  jnz     short loc_18003FB41
0x18003fb4d  lea     eax, ds:2[r14*2]
0x18003fb55  mov     [rsp+88h+var_64], ecx
0x18003fb59  mov     ecx, eax; cb
0x18003fb5b  mov     r15d, eax
0x18003fb5e  call    cs:__imp_CoTaskMemAlloc
0x18003fb64  mov     rdi, rax
0x18003fb67  mov     r12d, 7FFFFFFEh
0x18003fb6d  test    rax, rax
0x18003fb70  jz      loc_18003FE88
0x18003fb76  mov     r8d, r15d; Size
0x18003fb79  xor     edx, edx; Val
0x18003fb7b  mov     rcx, rax; void *
0x18003fb7e  call    memset_0
0x18003fb83  lea     eax, [r14+1]
0x18003fb87  mov     r8d, eax
0x18003fb8a  test    eax, eax
0x18003fb8c  jz      loc_18003FF9F
0x18003fb92  cmp     r8, 7FFFFFFFh
0x18003fb99  ja      loc_18003FF90
0x18003fb9f  mov     edx, r12d
0x18003fba2  mov     rax, rdi
0x18003fba5  test    rdx, rdx
0x18003fba8  jz      short loc_18003FBC6
0x18003fbaa  movzx   ecx, word ptr [rbx]
0x18003fbad  test    cx, cx
0x18003fbb0  jz      short loc_18003FBC6
0x18003fbb2  mov     [rdi], cx
0x18003fbb5  add     rbx, 2
0x18003fbb9  add     rdi, 2
0x18003fbbd  dec     rdx
0x18003fbc0  sub     r8, 1
0x18003fbc4  jnz     short loc_18003FBA5
0x18003fbc6  test    r8, r8
0x18003fbc9  lea     rdx, [rdi-2]
0x18003fbcd  mov     ebx, 8007007Ah
0x18003fbd2  cmovnz  rdx, rdi
0x18003fbd6  xor     ecx, ecx
0x18003fbd8  test    r8, r8
0x18003fbdb  cmovnz  ebx, ecx
0x18003fbde  mov     [rdx], cx
0x18003fbe1  test    ebx, ebx
0x18003fbe3  js      loc_18003FF44
0x18003fbe9  mov     rsi, rax
0x18003fbec  test    ebx, ebx
0x18003fbee  js      loc_18003FEE2
0x18003fbf4  mov     r15, [rsp+88h+var_60]
0x18003fbf9  xor     eax, eax
0x18003fbfb  mov     edi, eax
0x18003fbfd  mov     rbx, [r15]
0x18003fc00  test    rbx, rbx
0x18003fc03  jz      loc_18003FCCE
0x18003fc09  mov     [rsp+88h+var_64], eax
0x18003fc0d  mov     r15, r13
0x18003fc10  cmp     [rbx+r15*2+2], ax
0x18003fc16  lea     r15, [r15+1]
0x18003fc1a  jnz     short loc_18003FC10
0x18003fc1c  mov     [rsp+88h+var_64], eax
0x18003fc20  lea     eax, ds:2[r15*2]
0x18003fc28  mov     ecx, eax; cb
0x18003fc2a  mov     r13d, eax
0x18003fc2d  call    cs:__imp_CoTaskMemAlloc
0x18003fc33  mov     r14, rax
0x18003fc36  test    rax, rax
0x18003fc39  jz      loc_18003FE6E
0x18003fc3f  mov     r8d, r13d; Size
0x18003fc42  xor     edx, edx; Val
0x18003fc44  mov     rcx, rax; void *
0x18003fc47  call    memset_0
0x18003fc4c  lea     eax, [r15+1]
0x18003fc50  mov     r8d, eax
0x18003fc53  test    eax, eax
0x18003fc55  jz      loc_18003FFBF
0x18003fc5b  cmp     r8, 7FFFFFFFh
0x18003fc62  ja      loc_18003FFAC
0x18003fc68  mov     rdx, r12
0x18003fc6b  mov     rax, r14
0x18003fc6e  xchg    ax, ax
0x18003fc70  test    rdx, rdx
0x18003fc73  jz      short loc_18003FC92
0x18003fc75  movzx   ecx, word ptr [rbx]
0x18003fc78  test    cx, cx
0x18003fc7b  jz      short loc_18003FC92
0x18003fc7d  mov     [r14], cx
0x18003fc81  add     rbx, 2
0x18003fc85  add     r14, 2
0x18003fc89  dec     rdx
0x18003fc8c  sub     r8, 1
0x18003fc90  jnz     short loc_18003FC70
0x18003fc92  test    r8, r8
0x18003fc95  lea     rdx, [r14-2]
0x18003fc99  mov     ebx, 8007007Ah
0x18003fc9e  cmovnz  rdx, r14
0x18003fca2  xor     ecx, ecx
0x18003fca4  test    r8, r8
0x18003fca7  cmovnz  ebx, ecx
0x18003fcaa  mov     [rdx], cx
0x18003fcad  test    ebx, ebx
0x18003fcaf  js      loc_18003FF25
0x18003fcb5  mov     rdi, rax
0x18003fcb8  test    ebx, ebx
0x18003fcba  js      loc_18003FEA2
0x18003fcc0  mov     r15, [rsp+88h+var_60]
0x18003fcc5  mov     r13, 0FFFFFFFFFFFFFFFFh
0x18003fccc  xor     eax, eax
0x18003fcce  mov     r14, [r15+10h]
0x18003fcd2  mov     rbx, rax
0x18003fcd5  test    r14, r14
0x18003fcd8  jz      loc_18003FD9E
0x18003fcde  mov     [rsp+88h+var_64], eax
0x18003fce2  inc     r13
0x18003fce5  cmp     [r14+r13*2], bp
0x18003fcea  jnz     short loc_18003FCE2
0x18003fcec  mov     [rsp+88h+var_64], eax
0x18003fcf0  lea     eax, ds:2[r13*2]
0x18003fcf8  mov     ecx, eax; cb
0x18003fcfa  mov     [rsp+88h+var_50], r13
0x18003fcff  mov     r13d, eax
0x18003fd02  call    cs:__imp_CoTaskMemAlloc
0x18003fd08  mov     r15, rax
0x18003fd0b  test    rax, rax
0x18003fd0e  jz      loc_18003FE53
0x18003fd14  mov     r8d, r13d; Size
0x18003fd17  xor     edx, edx; Val
0x18003fd19  mov     rcx, rax; void *
0x18003fd1c  call    memset_0
0x18003fd21  mov     rax, [rsp+88h+var_50]
0x18003fd26  add     eax, 1
0x18003fd29  mov     r8d, eax
0x18003fd2c  jz      loc_18003FEEF
0x18003fd32  cmp     r8, 7FFFFFFFh
0x18003fd39  ja      loc_18003FEF7
0x18003fd3f  mov     rax, r15
0x18003fd42  test    r12, r12
0x18003fd45  jz      short loc_18003FD65
0x18003fd47  movzx   ecx, word ptr [r14]
0x18003fd4b  test    cx, cx
0x18003fd4e  jz      short loc_18003FD65
0x18003fd50  mov     [r15], cx
0x18003fd54  add     r14, 2
0x18003fd58  add     r15, 2
0x18003fd5c  dec     r12
0x18003fd5f  sub     r8, 1
0x18003fd63  jnz     short loc_18003FD42
0x18003fd65  test    r8, r8
0x18003fd68  lea     rdx, [r15-2]
0x18003fd6c  mov     r14d, 8007007Ah
0x18003fd72  cmovnz  rdx, r15
0x18003fd76  xor     ecx, ecx
0x18003fd78  test    r8, r8
0x18003fd7b  cmovnz  r14d, ecx
0x18003fd7f  mov     [rdx], cx
0x18003fd82  test    r14d, r14d
0x18003fd85  js      loc_18003FF06
0x18003fd8b  mov     rbx, rax
0x18003fd8e  test    r14d, r14d
0x18003fd91  js      loc_18003FFDA
0x18003fd97  mov     r15, [rsp+88h+var_60]
0x18003fd9c  xor     eax, eax
0x18003fd9e  mov     ecx, 20h ; ' '; cb
0x18003fda3  mov     dword ptr [rsp+88h+var_50+4], eax
0x18003fda7  mov     rbp, rax
0x18003fdaa  mov     [rsp+88h+var_58], rax
0x18003fdaf  call    cs:__imp_CoTaskMemAlloc
0x18003fdb5  test    rax, rax
0x18003fdb8  jz      loc_18003FFE7
0x18003fdbe  mov     qword ptr [rax], 0
0x18003fdc5  mov     qword ptr [rax+18h], 0
0x18003fdcd  mov     [rax+8], rsi
0x18003fdd1  xor     ebp, ebp
0x18003fdd3  mov     [rax], rdi
0x18003fdd6  xor     r14d, r14d
0x18003fdd9  mov     [rax+10h], rbx
0x18003fddd  movzx   ecx, word ptr [r15+1Ch]
0x18003fde2  mov     [rax+1Ch], cx
0x18003fde6  mov     ecx, [r15+18h]
0x18003fdea  mov     [rax+18h], ecx
0x18003fded  mov     rcx, [rsp+88h+var_48]
0x18003fdf2  mov     [rsp+88h+var_58], rbp
0x18003fdf7  mov     [rcx], rax
0x18003fdfa  mov     r13, [rsp+88h+var_30]
0x18003fdff  mov     r12, [rsp+88h+var_28]
0x18003fe04  mov     rdi, [rsp+88h+var_20]
0x18003fe09  mov     rsi, [rsp+88h+var_18]
0x18003fe0e  mov     r15, [rsp+88h+var_38]
0x18003fe13  mov     rbx, [rsp+88h+arg_10]
0x18003fe1b  test    rbp, rbp
0x18003fe1e  mov     rbp, [rsp+88h+var_10]
0x18003fe23  jz      short loc_18003FE2F
0x18003fe25  lea     rcx, [rsp+88h+var_58]; struct tagProxyResolveUrl **
0x18003fe2a  call    ?FreeProxyResolveUrl@@YAXPEAPEAUtagProxyResolveUrl@@@Z; FreeProxyResolveUrl(tagProxyResolveUrl * *)
0x18003fe2f  mov     eax, r14d
0x18003fe32  add     rsp, 80h
0x18003fe39  pop     r14
0x18003fe3b  retn
0x18003fe3c  mov     [rsp+88h+var_68], 80070057h
0x18003fe44  mov     r14d, [rsp+88h+var_68]
0x18003fe49  mov     [rsp+88h+var_64], 171h
0x18003fe51  jmp     short loc_18003FE13
0x18003fe53  mov     [rsp+88h+var_64], 4Ch ; 'L'
0x18003fe5b  mov     r14d, 8007000Eh
0x18003fe61  mov     [rsp+88h+var_64], 220h
0x18003fe69  jmp     loc_18003FD8E
0x18003fe6e  mov     [rsp+88h+var_64], 4Ch ; 'L'
0x18003fe76  mov     ebx, 8007000Eh
0x18003fe7b  mov     [rsp+88h+var_64], 220h
0x18003fe83  jmp     loc_18003FCB8
0x18003fe88  mov     [rsp+88h+var_64], 4Ch ; 'L'
0x18003fe90  mov     ebx, 8007000Eh
0x18003fe95  mov     [rsp+88h+var_64], 220h
0x18003fe9d  jmp     loc_18003FBEC
0x18003fea2  mov     [rsp+88h+var_64], 17Bh
0x18003feaa  mov     r14d, ebx
0x18003fead  jmp     short loc_18003FEBD
0x18003feaf  test    rbx, rbx
0x18003feb2  jz      short loc_18003FEBD
0x18003feb4  mov     rcx, rbx; pv
0x18003feb7  call    cs:__imp_CoTaskMemFree
0x18003febd  test    rdi, rdi
0x18003fec0  jz      short loc_18003FECB
0x18003fec2  mov     rcx, rdi; pv
0x18003fec5  call    cs:__imp_CoTaskMemFree
0x18003fecb  test    rsi, rsi
0x18003fece  jz      loc_18003FDFA
0x18003fed4  mov     rcx, rsi; pv
0x18003fed7  call    cs:__imp_CoTaskMemFree
0x18003fedd  jmp     loc_18003FDFA
0x18003fee2  mov     [rsp+88h+var_64], 176h
0x18003feea  mov     r14d, ebx
0x18003feed  jmp     short loc_18003FECB
0x18003feef  test    eax, eax
0x18003fef1  jz      loc_18003FFCC
0x18003fef7  xor     eax, eax
0x18003fef9  mov     r14d, 80070057h
0x18003feff  mov     [r15], ax
0x18003ff03  mov     rax, r15
0x18003ff06  mov     [rsp+88h+var_64], 224h
0x18003ff0e  test    rax, rax
0x18003ff11  jz      loc_18003FD8E
0x18003ff17  mov     rcx, rax; pv
0x18003ff1a  call    cs:__imp_CoTaskMemFree
0x18003ff20  jmp     loc_18003FD8E
0x18003ff25  mov     [rsp+88h+var_64], 224h
0x18003ff2d  test    rax, rax
0x18003ff30  jz      loc_18003FCB8
0x18003ff36  mov     rcx, rax; pv
0x18003ff39  call    cs:__imp_CoTaskMemFree
0x18003ff3f  jmp     loc_18003FCB8
0x18003ff44  mov     [rsp+88h+var_64], 224h
0x18003ff4c  test    rax, rax
0x18003ff4f  jz      loc_18003FBEC
0x18003ff55  mov     rcx, rax; pv
0x18003ff58  call    cs:__imp_CoTaskMemFree
0x18003ff5e  jmp     loc_18003FBEC
0x18003ff63  mov     [rsp+88h+var_64], 170h
0x18003ff6b  mov     r14d, 80070057h
0x18003ff71  jmp     loc_18003FE1B
0x18003ff76  mov     [rsp+88h+var_68], 80070057h
0x18003ff7e  mov     r14d, [rsp+88h+var_68]
0x18003ff83  mov     [rsp+88h+var_64], 172h
0x18003ff8b  jmp     loc_18003FE13
0x18003ff90  xor     eax, eax
0x18003ff92  mov     ebx, 80070057h
0x18003ff97  mov     [rdi], ax
0x18003ff9a  mov     rax, rdi
0x18003ff9d  jmp     short loc_18003FF44
0x18003ff9f  mov     ebx, 80070057h
0x18003ffa4  mov     rax, rdi
0x18003ffa7  jmp     loc_18003FBE1
0x18003ffac  xor     eax, eax
  ... truncated ...
```
