# CSpObjectTokenAttributeParser::CSpObjectTokenAttributeParser(ushort const *,int)

- ea: `0x180017fd0`
- end: `0x18001851c`
- name: `??0CSpObjectTokenAttributeParser@@QEAA@PEBGH@Z`
- size: `1356`
- prototype: `CSpObjectTokenAttributeParser *(CSpObjectTokenAttributeParser *__hidden this, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180017d30`
- `0x180017ee0`

## callees

- `0x180017fd0`
- `0x180018530`
- `0x18007a2dc`
- `0x18007a350`
- `0x18007d7b1`
- `0x18007d7bd`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x1800182b1`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x1800182ce`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x1800184ce`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x1800182b1`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x1800182ce`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x1800184ce`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800180b3`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800181dd`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800180b3`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800181dd`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18001811b`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18001839d`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18001811b`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18001839d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001810d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001838f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001810d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001838f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018175`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018185`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018378`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018175`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018185`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018378`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001814b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800183cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001814b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800183cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018057`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001825a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018057`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001825a`

## pseudocode

```c
CSpObjectTokenAttributeParser *__fastcall CSpObjectTokenAttributeParser::CSpObjectTokenAttributeParser(
        CSpObjectTokenAttributeParser *this,
        const unsigned __int16 *a2,
        int a3)
{
  int v3; // r13d
  CSpObjectTokenAttributeParser *result; // rax
  __int64 v6; // rdi
  SIZE_T v7; // rcx
  wchar_t *v8; // rax
  wchar_t *v9; // rsi
  int v10; // r12d
  _QWORD *v11; // rbx
  _QWORD *v12; // r15
  _QWORD *v13; // rbp
  _QWORD *v14; // r14
  wchar_t *v15; // rdi
  __int64 v16; // rbx
  _QWORD *v17; // rdi
  HANDLE v18; // rax
  SIZE_T v19; // rax
  unsigned __int64 v20; // rax
  wchar_t *v21; // rdi
  __int64 j; // rcx
  _QWORD *v23; // rax
  unsigned __int16 *v24; // rbx
  _WORD *v25; // rbp
  __int64 v26; // rdi
  SIZE_T v27; // rcx
  __int64 v28; // rax
  unsigned __int16 *v29; // rdi
  unsigned __int16 *v30; // r15
  unsigned __int16 *v31; // rbp
  unsigned __int16 *v32; // r15
  struct CSpAttribCondition *v33; // rax
  CSpObjectTokenAttributeParser *v34; // r8
  struct CSpAttribCondition *v35; // rbp
  __int64 v36; // r15
  __int64 v37; // rdi
  unsigned int v38; // ecx
  _DWORD *v39; // rax
  _QWORD *v40; // rdx
  _QWORD *v41; // rax
  DWORD v42; // ecx
  HANDLE ProcessHeap; // rax
  SIZE_T v44; // rax
  SIZE_T v45; // rax
  __int64 v46; // rcx
  unsigned __int16 *v47; // rdi
  int v48; // edi
  _QWORD *i; // rcx
  int v50; // ecx
  _QWORD *v51; // rax
  _QWORD *v52; // rcx
  wchar_t **v53; // rax
  __int64 v54; // rcx
  __int64 v55; // rdi
  size_t v56; // rdi
  _QWORD *v57; // [rsp+20h] [rbp-58h]
  _QWORD *v58; // [rsp+28h] [rbp-50h]
  wchar_t *Context; // [rsp+88h] [rbp+10h] BYREF
  wchar_t *v61; // [rsp+98h] [rbp+20h]

  v3 = 0;
  *(_DWORD *)this = a3;
  *((_DWORD *)this + 6) = 0;
  *((_QWORD *)this + 4) = 0;
  result = this;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 12) = 10;
  if ( !a2 )
    return result;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  if ( (unsigned int)v6 >= 0x4FFFFFFF || (v7 = 2LL * (unsigned int)(v6 + 1), v7 <= (unsigned int)v6) )
  {
    SetLastError(0x216u);
    v9 = 0;
    v61 = 0;
  }
  else
  {
    v8 = (wchar_t *)CoTaskMemAlloc(v7);
    v61 = v8;
    v9 = v8;
    if ( v8 )
    {
      v8[(unsigned int)v6] = 0;
      memcpy_0(v8, a2, 2 * v6);
    }
    else
    {
      SetLastError(0xEu);
    }
  }
  v57 = 0;
  Context = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  v15 = wcstok_s(v9, L";", &Context);
  if ( v15 )
  {
    do
    {
      if ( v11 )
        goto LABEL_71;
      v23 = operator new[](0x100u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v23 )
      {
        *v23 = v14;
        v50 = 9;
        v14 = v23;
        v23[1] = 10;
        v51 = v23 + 29;
        do
        {
          *v51 = v11;
          v11 = v51;
          v51 -= 3;
          --v50;
        }
        while ( v50 >= 0 );
      }
      if ( v11 )
      {
LABEL_71:
        v52 = v11;
        v53 = (wchar_t **)(v11 + 2);
        v11 = (_QWORD *)*v11;
        ++v10;
        v52[1] = v12;
        *v52 = 0;
        *v53 = v15;
        if ( v12 )
          *v12 = v52;
        else
          v13 = v52;
        v12 = v52;
      }
      v15 = wcstok_s(0, L";", &Context);
    }
    while ( v15 );
    v57 = v14;
  }
  v16 = 8;
  if ( v10 > 0 )
  {
    while ( 1 )
    {
      v24 = 0;
      v58 = (_QWORD *)*v13;
      v25 = (_WORD *)v13[2];
      if ( v25 )
      {
        v26 = -1;
        do
          ++v26;
        while ( v25[v26] );
        if ( (unsigned int)v26 >= 0x4FFFFFFF || (v27 = 2LL * (unsigned int)(v26 + 1), v27 <= (unsigned int)v26) )
        {
          v42 = 534;
          goto LABEL_51;
        }
        v24 = (unsigned __int16 *)CoTaskMemAlloc(v27);
        if ( !v24 )
        {
          v42 = 14;
LABEL_51:
          SetLastError(v42);
          goto LABEL_43;
        }
        v24[(unsigned int)v26] = 0;
        memcpy_0(v24, v25, 2 * v26);
        v28 = -1;
        do
          ++v28;
        while ( v24[v28] );
        v29 = &v24[(unsigned int)v28];
        v30 = v29;
        if ( v29 > v24 )
        {
          do
          {
            v31 = v30 - 1;
            if ( !(unsigned int)_o_iswspace(*(v30 - 1)) )
              break;
            --v30;
          }
          while ( v31 > v24 );
          if ( v30 != v29 )
            *v30 = 0;
        }
        v32 = v24;
        if ( (unsigned int)_o_iswspace(*v24) )
        {
          do
          {
            v54 = v32[1];
            ++v32;
          }
          while ( (unsigned int)_o_iswspace(v54) );
          if ( v32 != v24 )
          {
            v55 = -1;
            do
              ++v55;
            while ( v32[v55] );
            v56 = v55;
            memmove_0(v24, v32, v56 * 2);
            v24[v56] = 0;
          }
        }
      }
LABEL_43:
      v33 = CSpAttribCondition::ParseNewAttribCondition(v24);
      v34 = this;
      v35 = v33;
      v36 = *((_QWORD *)this + 2);
      if ( !*((_QWORD *)this + 4) )
      {
        v37 = *((unsigned int *)this + 12);
        v38 = 24 * v37;
        if ( (unsigned __int64)(24 * v37) <= 0xFFFFFFFF && v38 + 16 >= v38 )
        {
          v39 = operator new[](v38 + 16, (const struct std::nothrow_t *)&std::nothrow);
          v34 = this;
          if ( v39 )
          {
            v39[2] = v37;
            v39[3] = 0;
            *(_QWORD *)v39 = *((_QWORD *)this + 5);
            *((_QWORD *)this + 5) = v39;
            v48 = *((_DWORD *)this + 12) - 1;
            for ( i = &v39[6 * v48 + 4]; v48 >= 0; --v48 )
            {
              *i = *((_QWORD *)this + 4);
              *((_QWORD *)this + 4) = i;
              i -= 3;
            }
          }
        }
      }
      v40 = (_QWORD *)*((_QWORD *)v34 + 4);
      if ( v40 )
      {
        v40[2] = 0;
        *((_QWORD *)v34 + 4) = **((_QWORD **)v34 + 4);
        v40[1] = v36;
        *v40 = 0;
        ++*((_DWORD *)v34 + 6);
        v40[2] = v35;
        v41 = (_QWORD *)*((_QWORD *)v34 + 2);
        if ( v41 )
          *v41 = v40;
        else
          *((_QWORD *)v34 + 1) = v40;
        *((_QWORD *)v34 + 2) = v40;
      }
      if ( !v24 )
        goto LABEL_61;
      ProcessHeap = GetProcessHeap();
      v44 = HeapSize(ProcessHeap, 0, v24);
      if ( v44 - 3 <= 0xFFFFFFFFFFFFFFFBuLL )
      {
        v45 = v44 >> 1;
        v46 = v45 - 1;
        if ( v45 - 1 >= 8 )
        {
          v46 = 8;
LABEL_57:
          v47 = v24;
          while ( v46 )
          {
            *v47++ = -8531;
            --v46;
          }
          goto LABEL_60;
        }
        if ( v45 != 1 )
          goto LABEL_57;
      }
LABEL_60:
      CoTaskMemFree(v24);
LABEL_61:
      v13 = v58;
      if ( ++v3 >= v10 )
      {
        v9 = v61;
        v16 = 8;
        v14 = v57;
        break;
      }
    }
  }
  if ( v14 )
  {
    do
    {
      v17 = (_QWORD *)*v14;
      operator delete(v14);
      v14 = v17;
    }
    while ( v17 );
  }
  if ( v9 )
  {
    v18 = GetProcessHeap();
    v19 = HeapSize(v18, 0, v9);
    if ( v19 - 3 <= 0xFFFFFFFFFFFFFFFBuLL )
    {
      v20 = (v19 >> 1) - 1;
      if ( v20 >= 8 || (v16 = v20) != 0 )
      {
        v21 = v9;
        for ( j = v16; j; --j )
          *v21++ = -8531;
      }
    }
    CoTaskMemFree(v9);
  }
  return this;
}

```

## disassembly

```asm
0x180017fd0  mov     r11, rsp
0x180017fd3  mov     [r11+8], rcx
0x180017fd7  push    rbx
0x180017fd8  push    r13
0x180017fda  sub     rsp, 68h
0x180017fde  xor     r13d, r13d
0x180017fe1  mov     [rcx], r8d
0x180017fe4  mov     [rcx+18h], r13d
0x180017fe8  mov     rbx, rdx
0x180017feb  mov     [rcx+20h], r13
0x180017fef  mov     rax, rcx
0x180017ff2  mov     [rcx+10h], r13
0x180017ff6  mov     [rcx+8], r13
0x180017ffa  mov     [rcx+28h], r13
0x180017ffe  mov     dword ptr [rcx+30h], 0Ah
0x180018005  test    rdx, rdx
0x180018008  jz      loc_180018168
0x18001800e  mov     [r11+18h], rbp
0x180018012  mov     [r11-18h], rsi
0x180018016  mov     [r11-20h], rdi
0x18001801a  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180018021  mov     [r11-28h], r12
0x180018025  mov     [r11-30h], r14
0x180018029  mov     [r11-38h], r15
0x18001802d  nop     dword ptr [rax]
0x180018030  inc     rdi
0x180018033  cmp     [rdx+rdi*2], r13w
0x180018038  jnz     short loc_180018030
0x18001803a  cmp     edi, 4FFFFFFFh
0x180018040  jnb     loc_180018180
0x180018046  lea     ecx, [rdi+1]
0x180018049  mov     ebp, edi
0x18001804b  add     rcx, rcx; cb
0x18001804e  cmp     rcx, rbp
0x180018051  jbe     loc_180018180
0x180018057  call    cs:__imp_CoTaskMemAlloc
0x18001805d  mov     [rsp+78h+arg_18], rax
0x180018065  mov     rsi, rax
0x180018068  test    rax, rax
0x18001806b  jz      loc_180018170
0x180018071  lea     r8, [rdi+rdi]; Size
0x180018075  mov     [rax+rbp*2], r13w
0x18001807a  mov     rdx, rbx; Src
0x18001807d  mov     rcx, rax; void *
0x180018080  call    memcpy_0
0x180018085  lea     r8, [rsp+78h+Context]; Context
0x18001808d  mov     [rsp+78h+var_58], r13
0x180018092  lea     rdx, Delimiter; ";"
0x180018099  mov     [rsp+78h+Context], r13
0x1800180a1  mov     rcx, rsi; String
0x1800180a4  mov     r12d, r13d
0x1800180a7  mov     rbx, r13
0x1800180aa  mov     r15, r13
0x1800180ad  mov     rbp, r13
0x1800180b0  mov     r14, r13
0x1800180b3  call    cs:__imp_wcstok_s
0x1800180b9  mov     rdi, rax
0x1800180bc  test    rax, rax
0x1800180bf  jnz     loc_1800181A0
0x1800180c5  mov     ebx, 8
0x1800180ca  mov     r15d, 0DEADh
0x1800180d0  test    r12d, r12d
0x1800180d3  jg      loc_180018206
0x1800180d9  mov     r12, [rsp+78h+var_28]
0x1800180de  mov     rbp, [rsp+78h+arg_10]
0x1800180e6  test    r14, r14
0x1800180e9  jz      short loc_180018103
0x1800180eb  nop     dword ptr [rax+rax+00h]
0x1800180f0  mov     rdi, [r14]
0x1800180f3  mov     rcx, r14; Block
0x1800180f6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800180fb  mov     r14, rdi
0x1800180fe  test    rdi, rdi
0x180018101  jnz     short loc_1800180F0
0x180018103  mov     r14, [rsp+78h+var_30]
0x180018108  test    rsi, rsi
0x18001810b  jz      short loc_180018151
0x18001810d  call    cs:__imp_GetProcessHeap
0x180018113  mov     r8, rsi; lpMem
0x180018116  xor     edx, edx; dwFlags
0x180018118  mov     rcx, rax; hHeap
0x18001811b  call    cs:__imp_HeapSize
0x180018121  lea     rcx, [rax-3]
0x180018125  cmp     rcx, 0FFFFFFFFFFFFFFFBh
0x180018129  ja      short loc_180018148
0x18001812b  shr     rax, 1
0x18001812e  dec     rax
0x180018131  cmp     rax, 8
0x180018135  jb      loc_1800181F5
0x18001813b  movzx   eax, r15w
0x18001813f  mov     rdi, rsi
0x180018142  mov     rcx, rbx
0x180018145  rep stosw
0x180018148  mov     rcx, rsi; pv
0x18001814b  call    cs:__imp_CoTaskMemFree
0x180018151  mov     rax, [rsp+78h+arg_0]
0x180018159  mov     rdi, [rsp+78h+var_20]
0x18001815e  mov     rsi, [rsp+78h+var_18]
0x180018163  mov     r15, [rsp+78h+var_38]
0x180018168  add     rsp, 68h
0x18001816c  pop     r13
0x18001816e  pop     rbx
0x18001816f  retn
0x180018170  mov     ecx, 0Eh; dwErrCode
0x180018175  call    cs:__imp_SetLastError
0x18001817b  jmp     loc_180018085
0x180018180  mov     ecx, 216h; dwErrCode
0x180018185  call    cs:__imp_SetLastError
0x18001818b  mov     rsi, r13
0x18001818e  mov     [rsp+78h+arg_18], r13
0x180018196  jmp     loc_180018085
0x1800181a0  test    rbx, rbx
0x1800181a3  jnz     loc_18001847D
0x1800181a9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800181b0  mov     ecx, 100h; unsigned __int64
0x1800181b5  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800181ba  test    rax, rax
0x1800181bd  jnz     loc_180018450
0x1800181c3  test    rbx, rbx
0x1800181c6  jnz     loc_18001847D
0x1800181cc  lea     r8, [rsp+78h+Context]; Context
0x1800181d4  xor     ecx, ecx; String
0x1800181d6  lea     rdx, Delimiter; ";"
0x1800181dd  call    cs:__imp_wcstok_s
0x1800181e3  mov     rdi, rax
0x1800181e6  test    rax, rax
0x1800181e9  jnz     short loc_1800181A0
0x1800181eb  mov     [rsp+78h+var_58], r14
0x1800181f0  jmp     loc_1800180C5
0x1800181f5  mov     rbx, rax
0x1800181f8  test    rax, rax
0x1800181fb  jz      loc_180018148
0x180018201  jmp     loc_18001813B
0x180018206  mov     esi, r15d
0x180018209  mov     r14d, 0FFFFFFFFh
0x18001820f  lea     rax, [rbp+0]
0x180018213  xor     ebx, ebx
0x180018215  mov     rbp, [rbp+0]
0x180018219  mov     [rsp+78h+var_50], rbp
0x18001821e  mov     rbp, [rax+10h]
0x180018222  test    rbp, rbp
0x180018225  jz      loc_1800182DC
0x18001822b  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180018232  inc     rdi
0x180018235  cmp     [rbp+rdi*2+0], bx
0x18001823a  jnz     short loc_180018232
0x18001823c  cmp     edi, 4FFFFFFFh
0x180018242  jnb     loc_180018383
0x180018248  lea     ecx, [rdi+1]
0x18001824b  mov     r15d, edi
0x18001824e  add     rcx, rcx; cb
0x180018251  cmp     rcx, r15
0x180018254  jbe     loc_180018383
0x18001825a  call    cs:__imp_CoTaskMemAlloc
0x180018260  mov     rbx, rax
0x180018263  test    rax, rax
0x180018266  jz      loc_180018373
0x18001826c  xor     eax, eax
0x18001826e  lea     r8, [rdi+rdi]; Size
0x180018272  mov     rdx, rbp; Src
0x180018275  mov     [rbx+r15*2], ax
0x18001827a  mov     rcx, rbx; void *
0x18001827d  call    memcpy_0
0x180018282  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180018289  nop     dword ptr [rax+00000000h]
0x180018290  inc     rax
0x180018293  cmp     word ptr [rbx+rax*2], 0
0x180018298  jnz     short loc_180018290
0x18001829a  mov     eax, eax
0x18001829c  lea     rdi, [rbx+rax*2]
0x1800182a0  mov     r15, rdi
0x1800182a3  cmp     rdi, rbx
0x1800182a6  jbe     short loc_1800182C8
0x1800182a8  movzx   ecx, word ptr [r15-2]
0x1800182ad  lea     rbp, [r15-2]
0x1800182b1  call    cs:__imp__o_iswspace
0x1800182b7  test    eax, eax
0x1800182b9  jnz     loc_1800184A9
0x1800182bf  cmp     r15, rdi
0x1800182c2  jnz     loc_1800184BA
0x1800182c8  movzx   ecx, word ptr [rbx]
0x1800182cb  mov     r15, rbx
0x1800182ce  call    cs:__imp__o_iswspace
0x1800182d4  test    eax, eax
0x1800182d6  jnz     loc_1800184C5
0x1800182dc  mov     rcx, rbx; Src
0x1800182df  call    ?ParseNewAttribCondition@CSpAttribCondition@@SAPEAV1@PEBG@Z; CSpAttribCondition::ParseNewAttribCondition(ushort const *)
0x1800182e4  mov     r8, [rsp+78h+arg_0]
0x1800182ec  mov     rbp, rax
0x1800182ef  cmp     qword ptr [r8+20h], 0
0x1800182f4  mov     r15, [r8+10h]
0x1800182f8  jnz     short loc_180018331
0x1800182fa  mov     edi, [r8+30h]
0x1800182fe  lea     rcx, [rdi+rdi*2]
0x180018302  shl     rcx, 3
0x180018306  cmp     rcx, r14
0x180018309  ja      short loc_180018331
0x18001830b  lea     eax, [rcx+10h]
0x18001830e  cmp     eax, ecx
0x180018310  jb      short loc_180018331
0x180018312  mov     ecx, eax; unsigned __int64
0x180018314  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001831b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180018320  mov     r8, [rsp+78h+arg_0]
0x180018328  test    rax, rax
0x18001832b  jnz     loc_180018406
0x180018331  mov     rdx, [r8+20h]
0x180018335  test    rdx, rdx
0x180018338  jz      short loc_18001838A
0x18001833a  xor     eax, eax
0x18001833c  mov     [rdx+10h], rax
0x180018340  mov     rax, [r8+20h]
0x180018344  mov     rcx, [rax]
0x180018347  mov     [r8+20h], rcx
0x18001834b  mov     [rdx+8], r15
0x18001834f  mov     qword ptr [rdx], 0
0x180018356  inc     dword ptr [r8+18h]
0x18001835a  mov     [rdx+10h], rbp
0x18001835e  mov     rax, [r8+10h]
0x180018362  test    rax, rax
0x180018365  jz      loc_18001850F
0x18001836b  mov     [rax], rdx
0x18001836e  jmp     loc_180018513
0x180018373  mov     ecx, 0Eh; dwErrCode
0x180018378  call    cs:__imp_SetLastError
0x18001837e  jmp     loc_1800182DC
0x180018383  mov     ecx, 216h
0x180018388  jmp     short loc_180018378
0x18001838a  test    rbx, rbx
0x18001838d  jz      short loc_1800183D1
0x18001838f  call    cs:__imp_GetProcessHeap
0x180018395  mov     r8, rbx; lpMem
0x180018398  xor     edx, edx; dwFlags
0x18001839a  mov     rcx, rax; hHeap
0x18001839d  call    cs:__imp_HeapSize
0x1800183a3  lea     rcx, [rax-3]
0x1800183a7  cmp     rcx, 0FFFFFFFFFFFFFFFBh
0x1800183ab  ja      short loc_1800183C8
0x1800183ad  shr     rax, 1
0x1800183b0  lea     rcx, [rax-1]
0x1800183b4  cmp     rcx, 8
0x1800183b8  jb      short loc_1800183FF
0x1800183ba  mov     ecx, 8
0x1800183bf  movzx   eax, si
0x1800183c2  mov     rdi, rbx
0x1800183c5  rep stosw
0x1800183c8  mov     rcx, rbx; pv
0x1800183cb  call    cs:__imp_CoTaskMemFree
0x1800183d1  mov     rbp, [rsp+78h+var_50]
0x1800183d6  inc     r13d
0x1800183d9  cmp     r13d, r12d
0x1800183dc  jl      loc_18001820F
0x1800183e2  mov     rsi, [rsp+78h+arg_18]
0x1800183ea  mov     ebx, 8
0x1800183ef  mov     r14, [rsp+78h+var_58]
0x1800183f4  mov     r15d, 0DEADh
0x1800183fa  jmp     loc_1800180D9
0x1800183ff  test    rcx, rcx
0x180018402  jz      short loc_1800183C8
0x180018404  jmp     short loc_1800183BF
0x180018406  mov     [rax+8], edi
0x180018409  mov     dword ptr [rax+0Ch], 0
0x180018410  mov     rcx, [r8+28h]
0x180018414  mov     [rax], rcx
0x180018417  mov     [r8+28h], rax
0x18001841b  mov     edi, [r8+30h]
0x18001841f  sub     edi, 1
0x180018422  movsxd  rcx, edi
0x180018425  lea     rcx, [rcx+rcx*2]
0x180018429  lea     rcx, [rcx+2]
0x18001842d  lea     rcx, [rax+rcx*8]
0x180018431  js      loc_180018331
0x180018437  mov     rax, [r8+20h]
0x18001843b  mov     [rcx], rax
0x18001843e  mov     [r8+20h], rcx
0x180018442  sub     rcx, 18h
0x180018446  sub     edi, 1
0x180018449  jns     short loc_180018437
0x18001844b  jmp     loc_180018331
0x180018450  mov     [rax], r14
0x180018453  mov     ecx, 9
0x180018458  mov     r14, rax
0x18001845b  mov     qword ptr [rax+8], 0Ah
0x180018463  add     rax, 0E8h
0x180018469  mov     [rax], rbx
0x18001846c  mov     rbx, rax
0x18001846f  sub     rax, 18h
0x180018473  sub     ecx, 1
0x180018476  jns     short loc_180018469
0x180018478  jmp     loc_1800181C3
0x18001847d  mov     rcx, rbx
0x180018480  lea     rax, [rbx+10h]
0x180018484  mov     rbx, [rbx]
0x180018487  inc     r12d
0x18001848a  mov     [rcx+8], r15
0x18001848e  mov     [rcx], r13
0x180018491  mov     [rax], rdi
0x180018494  test    r15, r15
0x180018497  jz      short loc_18001849E
0x180018499  mov     [r15], rcx
  ... truncated ...
```
