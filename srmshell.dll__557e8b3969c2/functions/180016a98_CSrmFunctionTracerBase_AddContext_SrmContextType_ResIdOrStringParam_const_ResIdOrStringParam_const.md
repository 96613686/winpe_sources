# CSrmFunctionTracerBase::AddContext(_SrmContextType,ResIdOrStringParam const &,ResIdOrStringParam const &)

- ea: `0x180016a98`
- end: `0x180016dc8`
- name: `?AddContext@CSrmFunctionTracerBase@@QEAAXW4_SrmContextType@@AEBUResIdOrStringParam@@1@Z`
- size: `816`
- prototype: `void __fastcall(_QWORD *, __int64, void **, UINT *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180016dd0`

## callees

- `0x1800104a8`
- `0x180010548`
- `0x1800106fc`
- `0x180016048`
- `0x180016454`
- `0x180016a98`
- `0x180017e90`
- `0x180018af0`
- `0x1800195f0`
- `0x18001a008`
- `0x18001b420`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180016bd8`
- `msvcrt!??3@YAXPEAX@Z` at `0x180016d6a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180016d93`
- `msvcrt!??3@YAXPEAX@Z` at `0x180016bd8`
- `msvcrt!??3@YAXPEAX@Z` at `0x180016d6a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180016d93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016b25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016b25`

## pseudocode

```c
void __fastcall CSrmFunctionTracerBase::AddContext(_QWORD *a1, __int64 a2, void **a3, UINT *a4)
{
  _WORD *v6; // rdx
  _WORD *v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r8
  _WORD *v10; // rdx
  __int64 v11; // r8
  void *StringW; // rax
  void **v13; // rcx
  void **v14; // rax
  _QWORD *v15; // rbx
  __int64 v16; // rcx
  unsigned __int64 v17; // r8
  __int64 v18; // rsi
  _WORD *v19; // r8
  int v20; // [rsp+30h] [rbp-118h]
  int v21; // [rsp+44h] [rbp-104h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-100h] BYREF
  void *v23[2]; // [rsp+50h] [rbp-F8h] BYREF
  __int64 v24; // [rsp+60h] [rbp-E8h]
  unsigned __int64 v25; // [rsp+68h] [rbp-E0h]
  void *v26[2]; // [rsp+78h] [rbp-D0h] BYREF
  __int64 v27; // [rsp+88h] [rbp-C0h]
  unsigned __int64 v28; // [rsp+90h] [rbp-B8h]
  _WORD Src[8]; // [rsp+A0h] [rbp-A8h] BYREF
  __int64 v30; // [rsp+B0h] [rbp-98h]
  __int64 v31; // [rsp+B8h] [rbp-90h]
  _WORD v32[8]; // [rsp+C8h] [rbp-80h] BYREF
  __int64 v33; // [rsp+D8h] [rbp-70h]
  __int64 v34; // [rsp+E0h] [rbp-68h]
  void *v35[3]; // [rsp+F0h] [rbp-58h] BYREF
  unsigned __int64 v36; // [rsp+108h] [rbp-40h]

  try
  {
    v25 = 7;
    v24 = 0;
    LOWORD(v23[0]) = 0;
    v6 = *a3;
    if ( *a3 )
    {
      if ( (unsigned __int64)v6 >= 0x10000 )
      {
        v9 = -1;
        do
          ++v9;
        while ( v6[v9] );
        std::wstring::assign(v23, v6);
      }
      else
      {
        v7 = *(_WORD **)SrmFormatString(&pv, &Format, (unsigned int)v6);
        v8 = -1;
        do
          ++v8;
        while ( v7[v8] );
        std::wstring::assign(v23, v7);
        CoTaskMemFree(pv);
        pv = 0;
      }
    }
    else
    {
      std::wstring::assign(v23, &qword_180023088);
    }
    v28 = 7;
    v27 = 0;
    LOWORD(v26[0]) = 0;
    v10 = *(_WORD **)a4;
    if ( *(_QWORD *)a4 < 0x10000u )
    {
      StringW = (void *)CSrmResource::LoadStringW(v35, *a4);
      std::wstring::assign(v26, StringW);
      if ( v36 >= 8 )
        operator delete(v35[0]);
      v36 = 7;
      v35[2] = 0;
      LOWORD(v35[0]) = 0;
    }
    else
    {
      v11 = -1;
      do
        ++v11;
      while ( v10[v11] );
      std::wstring::assign(v26, v10);
    }
    v13 = v26;
    if ( v28 >= 8 )
      v13 = (void **)v26[0];
    v14 = v23;
    if ( v25 >= 8 )
      v14 = (void **)v23[0];
    v20 = 2;
    CSrmFunctionTracerBase::TraceInternalWithFormat(
      (CSrmFunctionTracerBase *)a1,
      L"CONTEXT",
      0x78u,
      L"Adding context: '%s' = '%s' (%d)",
      v14,
      v13,
      v20);
    v31 = 7;
    v30 = 0;
    Src[0] = 0;
    std::wstring::assign(Src);
    v15 = a1 + 17;
    v34 = 7;
    v33 = 0;
    v32[0] = 0;
    std::wstring::assign(v32);
    v17 = a1[18];
    if ( (unsigned __int64)Src >= v17 || *v15 > (unsigned __int64)Src )
    {
      if ( v17 == a1[19] )
        std::vector<std::pair<std::wstring,std::wstring>>::_Reserve(a1 + 17);
      v19 = Src;
    }
    else
    {
      v16 = (__int64)Src - *v15;
      v18 = v16 / 80;
      if ( v17 == v15[2] )
        std::vector<std::pair<std::wstring,std::wstring>>::_Reserve(v15);
      v19 = (_WORD *)(*v15 + 80 * v18);
    }
    std::_Cons_val<std::allocator<std::pair<std::wstring,std::wstring>>,std::pair<std::wstring,std::wstring>,std::pair<std::wstring,std::wstring>>(
      v16,
      v15[1],
      v19);
    v15[1] += 80LL;
    std::pair<std::wstring,std::wstring>::~pair<std::wstring,std::wstring>(Src);
    if ( v28 >= 8 )
      operator delete(v26[0]);
    v28 = 7;
    v27 = 0;
    LOWORD(v26[0]) = 0;
    if ( v25 >= 8 )
      operator delete(v23[0]);
    v25 = 7;
    v24 = 0;
    LOWORD(v23[0]) = 0;
  }
  catch ( std::bad_alloc )
  {
    v21 = -2147024882;
    throw (long *)&v21;
  }
}

```

## disassembly

```asm
0x180016a98  push    rbx
0x180016a9a  push    rsi
0x180016a9b  push    rdi
0x180016a9c  push    r14
0x180016a9e  push    r15
0x180016aa0  sub     rsp, 120h
0x180016aa7  mov     rax, cs:__security_cookie
0x180016aae  xor     rax, rsp
0x180016ab1  mov     [rsp+148h+var_30], rax
0x180016ab9  mov     rbx, r9
0x180016abc  mov     rsi, rcx
0x180016abf  xor     r14d, r14d
0x180016ac2  mov     [rsp+148h+var_108], r14d
0x180016ac7  lea     r15d, [r14+7]
0x180016acb  mov     [rsp+148h+var_E0], r15
0x180016ad0  mov     [rsp+148h+var_E8], r14
0x180016ad5  mov     word ptr [rsp+148h+var_F8], r14w
0x180016adb  mov     rdx, [r8]; void *
0x180016ade  test    rdx, rdx
0x180016ae1  jz      short loc_180016B54
0x180016ae3  cmp     rdx, 10000h
0x180016aea  jnb     short loc_180016B37
0x180016aec  mov     r8d, edx
0x180016aef  lea     rdx, Format
0x180016af6  lea     rcx, [rsp+148h+pv]
0x180016afb  call    ?SrmFormatString@@YA?AVCSrmAutoPWSZ@@PEBGZZ; SrmFormatString(ushort const *,...)
0x180016b00  nop
0x180016b01  mov     rdx, [rax]; void *
0x180016b04  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180016b08  mov     r8, rdi
0x180016b0b  inc     r8
0x180016b0e  cmp     [rdx+r8*2], r14w
0x180016b13  jnz     short loc_180016B0B
0x180016b15  lea     rcx, [rsp+148h+var_F8]; Src
0x180016b1a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180016b1f  nop
0x180016b20  mov     rcx, [rsp+148h+pv]; pv
0x180016b25  call    cs:__imp_CoTaskMemFree
0x180016b2b  mov     [rsp+148h+pv], r14
0x180016b30  mov     [rsp+148h+pv], r14
0x180016b35  jmp     short loc_180016B6C
0x180016b37  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180016b3b  mov     r8, rdi
0x180016b3e  inc     r8
0x180016b41  cmp     [rdx+r8*2], r14w
0x180016b46  jnz     short loc_180016B3E
0x180016b48  lea     rcx, [rsp+148h+var_F8]; Src
0x180016b4d  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180016b52  jmp     short loc_180016B6C
0x180016b54  xor     r8d, r8d
0x180016b57  lea     rdx, qword_180023088; void *
0x180016b5e  lea     rcx, [rsp+148h+var_F8]; Src
0x180016b63  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180016b68  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180016b6c  mov     [rsp+148h+var_B8], r15
0x180016b74  mov     [rsp+148h+var_C0], r14
0x180016b7c  mov     word ptr [rsp+148h+var_D0], r14w
0x180016b82  mov     rdx, [rbx]; void *
0x180016b85  cmp     rdx, 10000h
0x180016b8c  jb      short loc_180016BA7
0x180016b8e  mov     r8, rdi
0x180016b91  inc     r8
0x180016b94  cmp     [rdx+r8*2], r14w
0x180016b99  jnz     short loc_180016B91
0x180016b9b  lea     rcx, [rsp+148h+var_D0]; Src
0x180016ba0  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180016ba5  jmp     short loc_180016BF7
0x180016ba7  mov     edx, [rbx]; uID
0x180016ba9  lea     rcx, [rsp+148h+var_58]; Src
0x180016bb1  call    ?LoadStringW@CSrmResource@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; CSrmResource::LoadStringW(uint)
0x180016bb6  nop
0x180016bb7  mov     rdx, rax; Src
0x180016bba  lea     rcx, [rsp+148h+var_D0]; void *
0x180016bbf  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@$$QEAV12@@Z; std::wstring::assign(std::wstring &&)
0x180016bc4  nop
0x180016bc5  cmp     [rsp+148h+var_40], 8
0x180016bce  jb      short loc_180016BDE
0x180016bd0  mov     rcx, [rsp+148h+var_58]
0x180016bd8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180016bde  mov     [rsp+148h+var_40], r15
0x180016be6  mov     [rsp+148h+var_48], r14
0x180016bee  mov     word ptr [rsp+148h+var_58], r14w
0x180016bf7  lea     rcx, [rsp+148h+var_D0]
0x180016bfc  cmp     [rsp+148h+var_B8], 8
0x180016c05  cmovnb  rcx, [rsp+148h+var_D0]
0x180016c0b  lea     rax, [rsp+148h+var_F8]
0x180016c10  cmp     [rsp+148h+var_E0], 8
0x180016c16  cmovnb  rax, [rsp+148h+var_F8]
0x180016c1c  mov     [rsp+148h+var_118], 2
0x180016c24  mov     [rsp+148h+var_120], rcx
0x180016c29  mov     [rsp+148h+var_128], rax
0x180016c2e  lea     r9, aAddingContextS; "Adding context: '%s' = '%s' (%d)"
0x180016c35  mov     r8d, 78h ; 'x'; unsigned int
0x180016c3b  lea     rdx, aContext; "CONTEXT"
0x180016c42  mov     rcx, rsi; this
0x180016c45  call    ?TraceInternalWithFormat@CSrmFunctionTracerBase@@QEAAXPEBGK0ZZ; CSrmFunctionTracerBase::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x180016c4a  nop
0x180016c4b  mov     [rsp+148h+var_90], r15
0x180016c53  mov     [rsp+148h+var_98], r14
0x180016c5b  mov     [rsp+148h+Src], r14w
0x180016c64  mov     r9, rdi
0x180016c67  xor     r8d, r8d
0x180016c6a  lea     rdx, [rsp+148h+var_F8]
0x180016c6f  lea     rcx, [rsp+148h+Src]; Src
0x180016c77  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180016c7c  nop
0x180016c7d  lea     rbx, [rsi+88h]
0x180016c84  mov     [rsp+148h+var_68], r15
0x180016c8c  mov     [rsp+148h+var_70], r14
0x180016c94  mov     [rsp+148h+var_80], r14w
0x180016c9d  mov     r9, rdi
0x180016ca0  xor     r8d, r8d
0x180016ca3  lea     rdx, [rsp+148h+var_D0]
0x180016ca8  lea     rcx, [rsp+148h+var_80]; Src
0x180016cb0  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180016cb5  nop
0x180016cb6  mov     edi, 1
0x180016cbb  mov     [rsp+148h+var_108], edi
0x180016cbf  mov     r8, [rbx+8]
0x180016cc3  lea     rax, [rsp+148h+Src]
0x180016ccb  cmp     rax, r8
0x180016cce  jnb     short loc_180016D21
0x180016cd0  lea     rax, [rsp+148h+Src]
0x180016cd8  cmp     [rbx], rax
0x180016cdb  ja      short loc_180016D21
0x180016cdd  lea     rcx, [rsp+148h+Src]
0x180016ce5  sub     rcx, [rbx]
0x180016ce8  mov     rax, 6666666666666667h
0x180016cf2  imul    rcx
0x180016cf5  mov     rsi, rdx
0x180016cf8  sar     rsi, 5
0x180016cfc  mov     rax, rsi
0x180016cff  shr     rax, 3Fh
0x180016d03  add     rsi, rax
0x180016d06  cmp     r8, [rbx+10h]
0x180016d0a  jnz     short loc_180016D14
0x180016d0c  mov     rcx, rbx
0x180016d0f  call    ?_Reserve@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::pair<std::wstring,std::wstring>>::_Reserve(unsigned __int64)
0x180016d14  lea     r8, [rsi+rsi*4]
0x180016d18  shl     r8, 4
0x180016d1c  add     r8, [rbx]
0x180016d1f  jmp     short loc_180016D37
0x180016d21  cmp     r8, [rbx+10h]
0x180016d25  jnz     short loc_180016D2F
0x180016d27  mov     rcx, rbx
0x180016d2a  call    ?_Reserve@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::pair<std::wstring,std::wstring>>::_Reserve(unsigned __int64)
0x180016d2f  lea     r8, [rsp+148h+Src]
0x180016d37  mov     rdx, [rbx+8]
0x180016d3b  call    ??$_Cons_val@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@2@U32@@std@@YAXAEAV?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@0@PEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@0@$$QEAU20@@Z; std::_Cons_val<std::allocator<std::pair<std::wstring,std::wstring>>,std::pair<std::wstring,std::wstring>,std::pair<std::wstring,std::wstring>>(std::allocator<std::pair<std::wstring,std::wstring>> &,std::pair<std::wstring,std::wstring> *,std::pair<std::wstring,std::wstring> &&)
0x180016d40  add     qword ptr [rbx+8], 50h ; 'P'
0x180016d45  and     edi, 0FFFFFFFEh
0x180016d48  mov     [rsp+148h+var_108], edi
0x180016d4c  lea     rcx, [rsp+148h+Src]
0x180016d54  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::pair<std::wstring,std::wstring>::~pair<std::wstring,std::wstring>(void)
0x180016d59  nop
0x180016d5a  cmp     [rsp+148h+var_B8], 8
0x180016d63  jb      short loc_180016D70
0x180016d65  mov     rcx, [rsp+148h+var_D0]
0x180016d6a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180016d70  mov     [rsp+148h+var_B8], r15
0x180016d78  mov     [rsp+148h+var_C0], r14
0x180016d80  mov     word ptr [rsp+148h+var_D0], r14w
0x180016d86  cmp     [rsp+148h+var_E0], 8
0x180016d8c  jb      short loc_180016D99
0x180016d8e  mov     rcx, [rsp+148h+var_F8]
0x180016d93  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180016d99  mov     [rsp+148h+var_E0], r15
0x180016d9e  mov     [rsp+148h+var_E8], r14
0x180016da3  mov     word ptr [rsp+148h+var_F8], r14w
0x180016da9  mov     rcx, [rsp+148h+var_30]
0x180016db1  xor     rcx, rsp; StackCookie
0x180016db4  call    __security_check_cookie
0x180016db9  add     rsp, 120h
0x180016dc0  pop     r15
0x180016dc2  pop     r14
0x180016dc4  pop     rdi
0x180016dc5  pop     rsi
0x180016dc6  pop     rbx
0x180016dc7  retn
```
