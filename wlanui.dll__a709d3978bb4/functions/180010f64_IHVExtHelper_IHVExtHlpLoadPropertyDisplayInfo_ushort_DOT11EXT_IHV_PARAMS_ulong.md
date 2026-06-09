# IHVExtHelper::IHVExtHlpLoadPropertyDisplayInfo(ushort *,_DOT11EXT_IHV_PARAMS *,ulong)

- ea: `0x180010f64`
- end: `0x180011181`
- name: `?IHVExtHlpLoadPropertyDisplayInfo@IHVExtHelper@@QEAAJPEAGPEAU_DOT11EXT_IHV_PARAMS@@K@Z`
- size: `541`
- prototype: `__int64 __fastcall(IHVExtHelper *__hidden this, unsigned __int16 *, struct _DOT11EXT_IHV_PARAMS *, unsigned int)`
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000a29c`
- `0x18000b63c`
- `0x18000ba98`
- `0x18000df1c`
- `0x180011188`

## callees

- `0x180001d8c`
- `0x180001d98`
- `0x180010f64`
- `0x18001d010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180010fb3`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001115d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180010fb3`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001115d`

## pseudocode

```c
__int64 __fastcall IHVExtHelper::IHVExtHlpLoadPropertyDisplayInfo(
        IHVExtHelper *this,
        unsigned __int16 *a2,
        struct _DOT11EXT_IHV_PARAMS *a3,
        int a4)
{
  int v8; // edi
  bool v9; // of
  unsigned __int64 v10; // rax
  void *v11; // rax
  unsigned int v12; // r14d
  __int64 v13; // rax
  __int64 v14; // r15
  __int64 v15; // rax
  int v16; // eax
  __int64 v17; // rcx
  int v18; // eax
  int v19; // ecx
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // rcx
  int v23; // eax
  _QWORD *v24; // rax
  _QWORD *v25; // rsi
  int v26; // r10d
  int v27; // r11d
  int v28; // r9d
  int v29; // ecx
  int v30; // r8d
  int v31; // [rsp+40h] [rbp-20h] BYREF
  int v32; // [rsp+44h] [rbp-1Ch] BYREF
  int v33; // [rsp+48h] [rbp-18h] BYREF
  int v34; // [rsp+4Ch] [rbp-14h] BYREF
  int v35; // [rsp+50h] [rbp-10h] BYREF
  __int64 v36; // [rsp+58h] [rbp-8h] BYREF
  int v37; // [rsp+A0h] [rbp+40h] BYREF
  int v38; // [rsp+B8h] [rbp+58h]

  v38 = a4;
  v33 = 0;
  v37 = 0;
  v36 = 0;
  v32 = 0;
  v35 = 0;
  v34 = 0;
  v31 = 0;
  if ( !*((_DWORD *)this + 8) )
    return 0;
  v8 = 0;
  operator delete[](*((void **)this + 3));
  v10 = 8LL * *((unsigned int *)this + 2);
  v9 = (*((unsigned int *)this + 2) * (unsigned __int128)8uLL) >> 64 != 0;
  *((_QWORD *)this + 3) = 0;
  if ( v9 )
    v10 = -1;
  v11 = operator new[](v10, (const struct std::nothrow_t *)&std::nothrow);
  *((_QWORD *)this + 3) = v11;
  if ( v11 )
  {
    v12 = 0;
    if ( *((_DWORD *)this + 2) )
    {
      while ( 1 )
      {
        v13 = *((_QWORD *)this + 3);
        v33 = 0;
        v37 = 0;
        v36 = 0;
        v32 = 0;
        v14 = v12;
        *(_QWORD *)(v13 + 8LL * v12) = 0;
        v15 = *(_QWORD *)this;
        v31 = 0;
        v16 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)(v15 + 8LL * v12) + 56LL))(
                *(_QWORD *)(v15 + 8LL * v12),
                &v33);
        v8 = 0;
        if ( v16 != -2147467263 )
          v8 = v16;
        if ( v8 < 0 )
          break;
        v17 = *(_QWORD *)(*(_QWORD *)this + 8LL * v12);
        v18 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, struct _DOT11EXT_IHV_PARAMS *, int *))(*(_QWORD *)v17 + 40LL))(
                v17,
                a2,
                a3,
                &v37);
        v19 = 0;
        if ( v18 != -2147467263 )
          v19 = v18;
        if ( v19 < 0 )
          v37 = 1;
        v20 = *(_QWORD *)(*(_QWORD *)this + 8LL * v12);
        v21 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *, struct _DOT11EXT_IHV_PARAMS *, int *, int *, __int64 *))(*(_QWORD *)v20 + 64LL))(
                v20,
                0,
                a2,
                a3,
                &v32,
                &v31,
                &v36);
        v8 = 0;
        if ( v21 != -2147467263 )
          v8 = v21;
        if ( v8 < 0 )
          break;
        v22 = *(_QWORD *)(*(_QWORD *)this + 8LL * v12);
        v23 = (*(__int64 (__fastcall **)(__int64, int *, int *))(*(_QWORD *)v22 + 80LL))(v22, &v35, &v34);
        v8 = 0;
        if ( v23 != -2147467263 )
          v8 = v23;
        if ( v8 < 0 )
          break;
        if ( v37 )
          *((_DWORD *)this + 3) = v12;
        v24 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
        v25 = v24;
        if ( v24 )
        {
          v26 = v34;
          v27 = v31;
          v28 = v35;
          v29 = v32;
          v30 = v33;
          v24[1] = v36;
          *((_DWORD *)v24 + 4) = v29;
          *(_DWORD *)v24 = v30;
          *((_DWORD *)v24 + 6) = v38;
          *((_DWORD *)v24 + 7) = v28;
          *((_DWORD *)v24 + 8) = v26;
          *((_DWORD *)v24 + 5) = v27;
        }
        else
        {
          v25 = 0;
        }
        ++v12;
        *(_QWORD *)(*((_QWORD *)this + 3) + 8 * v14) = v25;
        if ( v12 >= *((_DWORD *)this + 2) )
          return (unsigned int)v8;
      }
      operator delete[](*((void **)this + 3));
      *((_QWORD *)this + 3) = 0;
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180010f64  mov     [rsp-38h+arg_8], rbx
0x180010f69  mov     [rsp-38h+arg_18], r9d
0x180010f6e  push    rbp
0x180010f6f  push    rsi
0x180010f70  push    rdi
0x180010f71  push    r12
0x180010f73  push    r13
0x180010f75  push    r14
0x180010f77  push    r15
0x180010f79  mov     rbp, rsp
0x180010f7c  sub     rsp, 60h
0x180010f80  xor     esi, esi
0x180010f82  mov     r12, r8
0x180010f85  mov     r13, rdx
0x180010f88  mov     rbx, rcx
0x180010f8b  mov     [rbp+var_18], esi
0x180010f8e  mov     [rbp+arg_0], esi
0x180010f91  mov     [rbp+var_8], rsi
0x180010f95  mov     [rbp+var_1C], esi
0x180010f98  mov     [rbp+var_10], esi
0x180010f9b  mov     [rbp+var_14], esi
0x180010f9e  mov     [rbp+var_20], esi
0x180010fa1  cmp     [rcx+20h], esi
0x180010fa4  jnz     short loc_180010FAD
0x180010fa6  xor     eax, eax
0x180010fa8  jmp     loc_180011169
0x180010fad  mov     rcx, [rcx+18h]
0x180010fb1  mov     edi, esi
0x180010fb3  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180010fb9  mov     ecx, [rbx+8]
0x180010fbc  mov     eax, 8
0x180010fc1  mul     rcx
0x180010fc4  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180010fcb  mov     [rbx+18h], rsi
0x180010fcf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180010fd6  cmovb   rax, rcx
0x180010fda  mov     rcx, rax; unsigned __int64
0x180010fdd  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180010fe2  mov     [rbx+18h], rax
0x180010fe6  test    rax, rax
0x180010fe9  jz      loc_180011167
0x180010fef  mov     r14d, esi
0x180010ff2  cmp     [rbx+8], esi
0x180010ff5  jbe     loc_180011167
0x180010ffb  mov     rax, [rbx+18h]
0x180010fff  lea     rdx, [rbp+var_18]
0x180011003  mov     [rbp+var_18], esi
0x180011006  mov     [rbp+arg_0], esi
0x180011009  mov     [rbp+var_8], rsi
0x18001100d  mov     [rbp+var_1C], esi
0x180011010  mov     r15d, r14d
0x180011013  mov     [rax+r15*8], rsi
0x180011017  mov     rax, [rbx]
0x18001101a  mov     [rbp+var_20], esi
0x18001101d  mov     rcx, [rax+r15*8]
0x180011021  mov     rax, [rcx]
0x180011024  mov     rax, [rax+38h]
0x180011028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001102d  cmp     eax, 80004001h
0x180011032  mov     edi, esi
0x180011034  cmovnz  edi, eax
0x180011037  test    edi, edi
0x180011039  js      loc_180011159
0x18001103f  mov     rax, [rbx]
0x180011042  lea     r9, [rbp+arg_0]
0x180011046  mov     r8, r12
0x180011049  mov     rdx, r13
0x18001104c  mov     rcx, [rax+r15*8]
0x180011050  mov     rax, [rcx]
0x180011053  mov     rax, [rax+28h]
0x180011057  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001105c  cmp     eax, 80004001h
0x180011061  mov     ecx, esi
0x180011063  cmovnz  ecx, eax
0x180011066  test    ecx, ecx
0x180011068  jns     short loc_180011071
0x18001106a  mov     [rbp+arg_0], 1
0x180011071  mov     rax, [rbx]
0x180011074  lea     rdx, [rbp+var_8]
0x180011078  mov     [rsp+60h+var_30], rdx
0x18001107d  mov     r9, r12
0x180011080  lea     rdx, [rbp+var_20]
0x180011084  mov     r8, r13
0x180011087  mov     [rsp+60h+var_38], rdx
0x18001108c  lea     rdx, [rbp+var_1C]
0x180011090  mov     rcx, [rax+r15*8]
0x180011094  mov     [rsp+60h+var_40], rdx
0x180011099  xor     edx, edx
0x18001109b  mov     rax, [rcx]
0x18001109e  mov     rax, [rax+40h]
0x1800110a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110a7  cmp     eax, 80004001h
0x1800110ac  mov     edi, esi
0x1800110ae  cmovnz  edi, eax
0x1800110b1  test    edi, edi
0x1800110b3  js      loc_180011159
0x1800110b9  mov     rax, [rbx]
0x1800110bc  lea     r8, [rbp+var_14]
0x1800110c0  lea     rdx, [rbp+var_10]
0x1800110c4  mov     rcx, [rax+r15*8]
0x1800110c8  mov     rax, [rcx]
0x1800110cb  mov     rax, [rax+50h]
0x1800110cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110d4  cmp     eax, 80004001h
0x1800110d9  mov     edi, esi
0x1800110db  cmovnz  edi, eax
0x1800110de  test    edi, edi
0x1800110e0  js      short loc_180011159
0x1800110e2  cmp     [rbp+arg_0], esi
0x1800110e5  jz      short loc_1800110EB
0x1800110e7  mov     [rbx+0Ch], r14d
0x1800110eb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800110f2  mov     ecx, 28h ; '('; unsigned __int64
0x1800110f7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800110fc  mov     rsi, rax
0x1800110ff  test    rax, rax
0x180011102  jz      short loc_180011139
0x180011104  mov     rdx, [rbp+var_8]
0x180011108  mov     r10d, [rbp+var_14]
0x18001110c  mov     r11d, [rbp+var_20]
0x180011110  mov     r9d, [rbp+var_10]
0x180011114  mov     ecx, [rbp+var_1C]
0x180011117  mov     r8d, [rbp+var_18]
0x18001111b  mov     [rax+8], rdx
0x18001111f  mov     [rax+10h], ecx
0x180011122  mov     [rax], r8d
0x180011125  mov     eax, [rbp+arg_18]
0x180011128  mov     [rsi+18h], eax
0x18001112b  mov     [rsi+1Ch], r9d
0x18001112f  mov     [rsi+20h], r10d
0x180011133  mov     [rsi+14h], r11d
0x180011137  jmp     short loc_18001113B
0x180011139  xor     esi, esi
0x18001113b  mov     rax, [rbx+18h]
0x18001113f  inc     r14d
0x180011142  mov     [rax+r15*8], rsi
0x180011146  mov     esi, 0
0x18001114b  cmp     r14d, [rbx+8]
0x18001114f  jb      loc_180010FFB
0x180011155  test    edi, edi
0x180011157  jns     short loc_180011167
0x180011159  mov     rcx, [rbx+18h]
0x18001115d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180011163  mov     [rbx+18h], rsi
0x180011167  mov     eax, edi
0x180011169  mov     rbx, [rsp+60h+arg_8]
0x180011171  add     rsp, 60h
0x180011175  pop     r15
0x180011177  pop     r14
0x180011179  pop     r13
0x18001117b  pop     r12
0x18001117d  pop     rdi
0x18001117e  pop     rsi
0x18001117f  pop     rbp
0x180011180  retn
```
