# SXReader::getValueFromAttribute(AttributeBase *,wchar_t const * *,int *)

- ea: `0x100406150`
- end: `0x100406406`
- name: `?getValueFromAttribute@SXReader@@QEAAXPEAVAttributeBase@@PEAPEB_WPEAH@Z`
- size: `694`
- prototype: `void __fastcall(SXReader *__hidden this, struct AttributeBase *, const wchar_t **, int *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x100411de0`
- `0x100411e60`
- `0x100411f20`

## callees

- `0x100401350`
- `0x100406150`
- `0x100413a50`
- `0x100415d60`
- `0x100424580`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1004062ce`
- `KERNEL32!HeapAlloc` at `0x1004062ce`

## pseudocode

```c
void __fastcall SXReader::getValueFromAttribute(SXReader *this, const wchar_t **a2, const wchar_t **a3, int *a4)
{
  __int64 v4; // r14
  struct AttributeBase *v5; // rdi
  unsigned int v6; // edx
  unsigned int v7; // esi
  int v9; // r15d
  int v10; // r12d
  __int64 v11; // rcx
  unsigned int v12; // eax
  const wchar_t *v13; // rax
  unsigned int v14; // ebx
  unsigned int v15; // ebp
  __int64 v16; // rcx
  unsigned int v17; // eax
  int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // r15d
  struct IMalloc *v21; // rcx
  SIZE_T v22; // r8
  wchar_t *v23; // rbx
  char v24; // r12
  _varray_base *v25; // rbp
  unsigned int v26; // r13d
  __int64 v27; // rdx
  unsigned int v28; // eax
  int v29; // ecx
  __int64 v30; // rdi
  unsigned int v31; // [rsp+20h] [rbp-48h]
  __int64 v32; // [rsp+28h] [rbp-40h]

  v4 = 0;
  v5 = (struct AttributeBase *)a2;
  v6 = *((_DWORD *)a2 + 11);
  v7 = 1;
  v32 = 0;
  v31 = v6;
  v9 = 0;
  v10 = 16924672;
  if ( v6 == 1 && (v11 = *((_QWORD *)v5 + 6), v12 = *(_DWORD *)(v11 + 12), v12 <= 0x18) && _bittest(&v10, v12) )
  {
    *a3 = *(const wchar_t **)v11;
    *a4 = *(_DWORD *)(v11 + 8) >> 1;
  }
  else
  {
    v13 = (const wchar_t *)*((_QWORD *)v5 + 8);
    if ( !v13 )
    {
      if ( v6 )
      {
        v14 = 1;
        do
        {
          v15 = v14;
          if ( v14 - 1 >= *((_DWORD *)v5 + 11) )
          {
            if ( v14 < v14 - 1 )
            {
LABEL_44:
              MXRRaiseException(-2147352566);
              JUMPOUT(0x100406405LL);
            }
            if ( v14 > *((_DWORD *)v5 + 10) )
            {
              _mm_lfence();
              _varray_base::_ensureCapacity_((struct AttributeBase *)((char *)v5 + 24), v14, 0x10u);
              v6 = v31;
            }
            *((_DWORD *)v5 + 11) = v14;
          }
          v16 = *((_QWORD *)v5 + 6);
          v17 = *(_DWORD *)(v16 + v4 + 12);
          if ( v17 > 0x18 || !_bittest(&v10, v17) )
          {
LABEL_42:
            MXRRaiseException(-2147467259);
            __debugbreak();
          }
          ++v14;
          v18 = *(_DWORD *)(v16 + v4 + 8) >> 1;
          v4 += 16;
          v9 += v18;
        }
        while ( v15 < v6 );
        v5 = (struct AttributeBase *)a2;
        v4 = 0;
      }
      v19 = v6 + v9;
      v20 = v6 + v9 - 1;
      *((_DWORD *)v5 + 18) = v20;
      v21 = (struct IMalloc *)*((_QWORD *)this + 1);
      v22 = 2LL * v19;
      if ( !is_mul_ok(v19, 2u) )
        v22 = -1;
      if ( v21 || (v21 = g_pMalloc) != 0 )
        v13 = (const wchar_t *)((__int64 (__fastcall *)(struct IMalloc *, SIZE_T))v21->lpVtbl->Alloc)(v21, v22);
      else
        v13 = (const wchar_t *)HeapAlloc(g_hHeap, 0, v22);
      v23 = (wchar_t *)v13;
      if ( !v13 )
      {
        MXRRaiseException(-2147024882);
        __debugbreak();
      }
      v24 = 1;
      *((_QWORD *)v5 + 8) = v13;
      if ( v31 )
      {
        v25 = (struct AttributeBase *)((char *)v5 + 24);
        do
        {
          v26 = v7;
          if ( v7 - 1 >= *((_DWORD *)v25 + 5) )
          {
            if ( v7 < v7 - 1 )
              goto LABEL_44;
            if ( v7 > *((_DWORD *)v25 + 4) )
            {
              _mm_lfence();
              _varray_base::_ensureCapacity_(v25, v7, 0x10u);
            }
            *((_DWORD *)v25 + 5) = v7;
          }
          v27 = v4 + *((_QWORD *)v25 + 3);
          v28 = *(_DWORD *)(v27 + 12);
          if ( v24 )
          {
            v24 = 0;
          }
          else
          {
            *v23++ = 32;
            --v20;
          }
          if ( v28 > 0x18 )
            goto LABEL_42;
          v29 = 16924672;
          if ( !_bittest(&v29, v28) )
            goto LABEL_42;
          v30 = *(_DWORD *)(v27 + 8) >> 1;
          if ( v20 < (unsigned int)v30 || 2 * v30 < (unsigned __int64)(unsigned int)v30 )
            goto LABEL_42;
          memmove(v23, *(const void **)v27, 2 * v30);
          v23 += v30;
          v20 -= v30;
          ++v7;
          v4 = v32 + 16;
          v32 += 16;
        }
        while ( v26 < v31 );
        v5 = (struct AttributeBase *)a2;
        v13 = a2[8];
      }
      *((_DWORD *)v5 + 18) = v23 - v13;
    }
    *a3 = v13;
    *a4 = *((_DWORD *)v5 + 18);
  }
}

```

## disassembly

```asm
0x100406150  mov     [rsp+arg_18], r9
0x100406155  mov     [rsp+arg_10], r8
0x10040615a  mov     [rsp+arg_8], rdx
0x10040615f  push    rbx
0x100406160  push    rsi
0x100406161  push    rdi
0x100406162  push    r12
0x100406164  push    r13
0x100406166  push    r14
0x100406168  push    r15
0x10040616a  sub     rsp, 30h
0x10040616e  xor     r14d, r14d
0x100406171  mov     rdi, rdx
0x100406174  mov     edx, [rdx+2Ch]
0x100406177  mov     esi, 1
0x10040617c  mov     [rsp+68h+var_40], r14
0x100406181  mov     r13, rcx
0x100406184  mov     [rsp+68h+var_48], edx
0x100406188  mov     r15d, r14d
0x10040618b  mov     r12d, 1024000h
0x100406191  cmp     edx, esi
0x100406193  jnz     short loc_1004061F8
0x100406195  cmp     edx, r14d
0x100406198  ja      short loc_1004061C8
0x10040619a  cmp     [rdi+28h], esi
0x10040619d  jnb     short loc_1004061C5
0x10040619f  lfence
0x1004061a2  lea     r8d, [r14+10h]; unsigned __int64
0x1004061a6  mov     edx, esi; unsigned int
0x1004061a8  lea     rcx, [rdi+18h]; this
0x1004061ac  call    ?_ensureCapacity_@_varray_base@@AEAAXK_K@Z; _varray_base::_ensureCapacity_(ulong,unsigned __int64)
0x1004061b1  mov     edx, [rsp+68h+var_48]
0x1004061b5  mov     r9, [rsp+68h+arg_18]
0x1004061bd  mov     r8, [rsp+68h+arg_10]
0x1004061c5  mov     [rdi+2Ch], esi
0x1004061c8  mov     rcx, [rdi+30h]
0x1004061cc  mov     eax, [rcx+0Ch]
0x1004061cf  cmp     eax, 18h
0x1004061d2  ja      short loc_1004061F8
0x1004061d4  bt      r12d, eax
0x1004061d8  jnb     short loc_1004061F8
0x1004061da  mov     rax, [rcx]
0x1004061dd  mov     [r8], rax
0x1004061e0  mov     eax, [rcx+8]
0x1004061e3  shr     eax, 1
0x1004061e5  mov     [r9], eax
0x1004061e8  add     rsp, 30h
0x1004061ec  pop     r15
0x1004061ee  pop     r14
0x1004061f0  pop     r13
0x1004061f2  pop     r12
0x1004061f4  pop     rdi
0x1004061f5  pop     rsi
0x1004061f6  pop     rbx
0x1004061f7  retn
0x1004061f8  mov     rax, [rdi+40h]
0x1004061fc  mov     [rsp+68h+arg_0], rbp
0x100406201  test    rax, rax
0x100406204  jnz     loc_1004063B8
0x10040620a  test    edx, edx
0x10040620c  jz      short loc_10040627A
0x10040620e  mov     ebx, esi
0x100406210  lea     eax, [rbx-1]
0x100406213  mov     ebp, ebx
0x100406215  cmp     eax, [rdi+2Ch]
0x100406218  jb      short loc_100406242
0x10040621a  cmp     ebx, eax
0x10040621c  jb      loc_1004063FB
0x100406222  cmp     ebx, [rdi+28h]
0x100406225  jbe     short loc_10040623F
0x100406227  lfence
0x10040622a  mov     r8d, 10h; unsigned __int64
0x100406230  lea     rcx, [rdi+18h]; this
0x100406234  mov     edx, ebx; unsigned int
0x100406236  call    ?_ensureCapacity_@_varray_base@@AEAAXK_K@Z; _varray_base::_ensureCapacity_(ulong,unsigned __int64)
0x10040623b  mov     edx, [rsp+68h+var_48]
0x10040623f  mov     [rdi+2Ch], ebx
0x100406242  mov     rcx, [rdi+30h]
0x100406246  mov     eax, [rcx+r14+0Ch]
0x10040624b  cmp     eax, 18h
0x10040624e  ja      loc_1004063E5
0x100406254  bt      r12d, eax
0x100406258  jnb     loc_1004063E5
0x10040625e  mov     eax, [rcx+r14+8]
0x100406263  inc     ebx
0x100406265  shr     eax, 1
0x100406267  add     r14, 10h
0x10040626b  add     r15d, eax
0x10040626e  cmp     ebp, edx
0x100406270  jb      short loc_100406210
0x100406272  mov     rdi, [rsp+68h+arg_8]
0x100406277  xor     r14d, r14d
0x10040627a  lea     eax, [rdx+r15]
0x10040627e  lea     r15d, [rax-1]
0x100406282  mov     edx, eax
0x100406284  mov     eax, 2
0x100406289  mov     [rdi+48h], r15d
0x10040628d  mov     rcx, [r13+8]
0x100406291  mul     rdx
0x100406294  mov     r8, rax
0x100406297  mov     rax, 0FFFFFFFFFFFFFFFFh
0x10040629e  cmovo   r8, rax; dwBytes
0x1004062a2  test    rcx, rcx
0x1004062a5  jz      short loc_1004062B9
0x1004062a7  mov     rax, [rcx]
0x1004062aa  mov     rdx, r8
0x1004062ad  mov     rax, [rax+18h]
0x1004062b1  call    cs:__guard_dispatch_icall_fptr
0x1004062b7  jmp     short loc_1004062D4
0x1004062b9  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x1004062c0  test    rcx, rcx
0x1004062c3  jnz     short loc_1004062A7
0x1004062c5  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x1004062cc  xor     edx, edx; dwFlags
0x1004062ce  call    cs:__imp_HeapAlloc
0x1004062d4  mov     rbx, rax
0x1004062d7  test    rax, rax
0x1004062da  jz      loc_1004063F0
0x1004062e0  cmp     [rsp+68h+var_48], 0
0x1004062e5  movzx   r12d, sil
0x1004062e9  mov     [rdi+40h], rax
0x1004062ed  jbe     loc_1004063AF
0x1004062f3  lea     rbp, [rdi+18h]
0x1004062f7  lea     eax, [rsi-1]
0x1004062fa  mov     ecx, 20h ; ' '
0x1004062ff  mov     r13d, esi
0x100406302  cmp     eax, [rbp+14h]
0x100406305  jb      short loc_10040632D
0x100406307  cmp     esi, eax
0x100406309  jb      loc_1004063FB
0x10040630f  cmp     esi, [rbp+10h]
0x100406312  jbe     short loc_10040632A
0x100406314  lfence
0x100406317  lea     r8d, [rcx-10h]; unsigned __int64
0x10040631b  mov     edx, esi; unsigned int
0x10040631d  mov     rcx, rbp; this
0x100406320  call    ?_ensureCapacity_@_varray_base@@AEAAXK_K@Z; _varray_base::_ensureCapacity_(ulong,unsigned __int64)
0x100406325  mov     ecx, 20h ; ' '
0x10040632a  mov     [rbp+14h], esi
0x10040632d  mov     rdx, [rbp+18h]
0x100406331  add     rdx, r14
0x100406334  mov     eax, [rdx+0Ch]
0x100406337  test    r12b, r12b
0x10040633a  jnz     short loc_100406348
0x10040633c  mov     [rbx], cx
0x10040633f  add     rbx, 2
0x100406343  dec     r15d
0x100406346  jmp     short loc_10040634B
0x100406348  xor     r12b, r12b
0x10040634b  cmp     eax, 18h
0x10040634e  ja      loc_1004063E5
0x100406354  mov     ecx, 1024000h
0x100406359  bt      ecx, eax
0x10040635c  jnb     loc_1004063E5
0x100406362  mov     edi, [rdx+8]
0x100406365  shr     edi, 1
0x100406367  cmp     r15d, edi
0x10040636a  jb      short loc_1004063E5
0x10040636c  mov     eax, edi
0x10040636e  lea     r14, [rdi+rdi]
0x100406372  cmp     r14, rax
0x100406375  jb      short loc_1004063E5
0x100406377  mov     rdx, [rdx]; Src
0x10040637a  mov     r8, r14; Size
0x10040637d  mov     rcx, rbx; void *
0x100406380  call    memmove
0x100406385  add     rbx, r14
0x100406388  sub     r15d, edi
0x10040638b  mov     r14, [rsp+68h+var_40]
0x100406390  inc     esi
0x100406392  add     r14, 10h
0x100406396  mov     [rsp+68h+var_40], r14
0x10040639b  cmp     r13d, [rsp+68h+var_48]
0x1004063a0  jb      loc_1004062F7
0x1004063a6  mov     rdi, [rsp+68h+arg_8]
0x1004063ab  mov     rax, [rdi+40h]
0x1004063af  sub     rbx, rax
0x1004063b2  sar     rbx, 1
0x1004063b5  mov     [rdi+48h], ebx
0x1004063b8  mov     rcx, [rsp+68h+arg_10]
0x1004063c0  mov     rbp, [rsp+68h+arg_0]
0x1004063c5  mov     [rcx], rax
0x1004063c8  mov     rcx, [rsp+68h+arg_18]
0x1004063d0  mov     eax, [rdi+48h]
0x1004063d3  mov     [rcx], eax
0x1004063d5  add     rsp, 30h
0x1004063d9  pop     r15
0x1004063db  pop     r14
0x1004063dd  pop     r13
0x1004063df  pop     r12
0x1004063e1  pop     rdi
0x1004063e2  pop     rsi
0x1004063e3  pop     rbx
0x1004063e4  retn
0x1004063e5  mov     ecx, 80004005h; int
0x1004063ea  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x1004063ef  int     3; Trap to Debugger
0x1004063f0  mov     ecx, 8007000Eh; int
0x1004063f5  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x1004063fa  int     3; Trap to Debugger
0x1004063fb  mov     ecx, 8002000Ah; int
0x100406400  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
