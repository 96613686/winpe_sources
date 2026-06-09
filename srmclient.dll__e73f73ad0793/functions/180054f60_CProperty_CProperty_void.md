# CProperty::~CProperty(void)

- ea: `0x180054f60`
- end: `0x1800551fd`
- name: `??1CProperty@@QEAA@XZ`
- size: `669`
- prototype: `void __fastcall(CProperty *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180055230`
- `0x1800c19bd`
- `0x1800c1cd3`

## callees

- `0x180001350`
- `0x18000266c`
- `0x18000a320`
- `0x180043dac`
- `0x180054f60`
- `0x1800d5010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180055079`
- `OLEAUT32!__imp_SysFreeString` at `0x1800551b5`
- `OLEAUT32!__imp_SysFreeString` at `0x180055079`
- `OLEAUT32!__imp_SysFreeString` at `0x1800551b5`
- `KERNEL32!DeleteCriticalSection` at `0x180054f89`
- `KERNEL32!DeleteCriticalSection` at `0x180054fa3`
- `KERNEL32!DeleteCriticalSection` at `0x180054fbd`
- `KERNEL32!DeleteCriticalSection` at `0x1800551c8`
- `KERNEL32!DeleteCriticalSection` at `0x1800551eb`
- `KERNEL32!DeleteCriticalSection` at `0x180054f89`
- `KERNEL32!DeleteCriticalSection` at `0x180054fa3`
- `KERNEL32!DeleteCriticalSection` at `0x180054fbd`
- `KERNEL32!DeleteCriticalSection` at `0x1800551c8`
- `KERNEL32!DeleteCriticalSection` at `0x1800551eb`

## pseudocode

```c
// Hidden C++ exception states: #wind=12 #try_helpers=1
void __fastcall CProperty::~CProperty(CProperty *this)
{
  char *v2; // rbx
  __int64 v3; // rbx
  __int64 *v4; // rsi
  __int64 v5; // rbp
  __int64 v6; // rcx
  __int64 v7; // rbx
  __int64 *v8; // rsi
  __int64 v9; // rbp
  __int64 v10; // rcx
  __int64 v11; // rbx
  __int64 *v12; // rsi
  __int64 v13; // rbp
  __int64 v14; // rbx
  __int64 *v15; // rsi
  __int64 v16; // rbp
  __int64 v17; // rbx
  __int64 *v18; // rsi
  __int64 v19; // rbp
  __int64 v20; // rbx
  __int64 *v21; // rsi
  __int64 v22; // rbp
  __int64 v23; // rcx

  *((_QWORD *)this + 8) = 0;
  v2 = (char *)this + 496;
  if ( *((_BYTE *)this + 536) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 496));
    v2[40] = 0;
  }
  if ( *((_BYTE *)this + 488) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 448));
    *((_BYTE *)this + 488) = 0;
  }
  if ( *((_BYTE *)this + 440) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)this + 10);
    *((_BYTE *)this + 440) = 0;
  }
  v3 = *((_QWORD *)this + 45);
  v4 = (__int64 *)((char *)this + 368);
  if ( v3 )
  {
    v5 = *v4;
    while ( v3 != v5 )
    {
      std::_Dest_val<std::allocator<std::wstring>,std::wstring>((__int64)this, v3);
      v3 += 40;
    }
    operator delete(*((void **)this + 45));
  }
  *((_QWORD *)this + 45) = 0;
  *v4 = 0;
  *((_QWORD *)this + 47) = 0;
  std::_Tree<std::_Tset_traits<std::wstring,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::wstring>,0>>::clear((char *)this + 328);
  operator delete(*((void **)this + 42));
  v7 = *((_QWORD *)this + 36);
  v8 = (__int64 *)((char *)this + 296);
  if ( v7 )
  {
    v9 = *v8;
    while ( v7 != v9 )
    {
      std::_Dest_val<std::allocator<std::wstring>,std::wstring>(v6, v7);
      v7 += 40;
    }
    operator delete(*((void **)this + 36));
  }
  *((_QWORD *)this + 36) = 0;
  *v8 = 0;
  *((_QWORD *)this + 38) = 0;
  SysFreeString(*((BSTR *)this + 34));
  v11 = *((_QWORD *)this + 29);
  v12 = (__int64 *)((char *)this + 240);
  if ( v11 )
  {
    v13 = *v12;
    while ( v11 != v13 )
    {
      std::_Dest_val<std::allocator<CPropertyValue>,CPropertyValue>(v10, v11);
      v11 += 96;
    }
    operator delete(*((void **)this + 29));
  }
  *((_QWORD *)this + 29) = 0;
  *v12 = 0;
  *((_QWORD *)this + 31) = 0;
  v14 = *((_QWORD *)this + 25);
  v15 = (__int64 *)((char *)this + 208);
  if ( v14 )
  {
    v16 = *v15;
    while ( v14 != v16 )
    {
      std::_Dest_val<std::allocator<CPropertyValue>,CPropertyValue>(v10, v14);
      v14 += 96;
    }
    operator delete(*((void **)this + 25));
  }
  *((_QWORD *)this + 25) = 0;
  *v15 = 0;
  *((_QWORD *)this + 27) = 0;
  v17 = *((_QWORD *)this + 21);
  v18 = (__int64 *)((char *)this + 176);
  if ( v17 )
  {
    v19 = *v18;
    while ( v17 != v19 )
    {
      std::_Dest_val<std::allocator<CPropertyValue>,CPropertyValue>(v10, v17);
      v17 += 96;
    }
    operator delete(*((void **)this + 21));
  }
  *((_QWORD *)this + 21) = 0;
  *v18 = 0;
  *((_QWORD *)this + 23) = 0;
  v20 = *((_QWORD *)this + 17);
  v21 = (__int64 *)((char *)this + 144);
  if ( v20 )
  {
    v22 = *v21;
    while ( v20 != v22 )
    {
      std::_Dest_val<std::allocator<CPropertyValue>,CPropertyValue>(v10, v20);
      v20 += 96;
    }
    operator delete(*((void **)this + 17));
  }
  *((_QWORD *)this + 17) = 0;
  *v21 = 0;
  *((_QWORD *)this + 19) = 0;
  v23 = *((_QWORD *)this + 16);
  if ( v23 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 8LL))(v23);
  SysFreeString(*((BSTR *)this + 15));
  if ( *((_DWORD *)this + 28) == 1 )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  if ( *((_BYTE *)this + 56) )
  {
    *((_BYTE *)this + 56) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  }
}

```

## disassembly

```asm
0x180054f60  mov     [rsp+arg_0], rcx
0x180054f65  push    rbx
0x180054f66  push    rbp
0x180054f67  push    rsi
0x180054f68  push    rdi
0x180054f69  push    r14
0x180054f6b  sub     rsp, 30h
0x180054f6f  mov     rdi, rcx
0x180054f72  xor     r14d, r14d
0x180054f75  mov     [rcx+40h], r14
0x180054f79  lea     rbx, [rcx+1F0h]
0x180054f80  cmp     [rbx+28h], r14b
0x180054f84  jz      short loc_180054F93
0x180054f86  mov     rcx, rbx; lpCriticalSection
0x180054f89  call    cs:__imp_DeleteCriticalSection
0x180054f8f  mov     [rbx+28h], r14b
0x180054f93  lea     rbx, [rdi+1C0h]
0x180054f9a  cmp     [rbx+28h], r14b
0x180054f9e  jz      short loc_180054FAD
0x180054fa0  mov     rcx, rbx; lpCriticalSection
0x180054fa3  call    cs:__imp_DeleteCriticalSection
0x180054fa9  mov     [rbx+28h], r14b
0x180054fad  lea     rbx, [rdi+190h]
0x180054fb4  cmp     [rbx+28h], r14b
0x180054fb8  jz      short loc_180054FC7
0x180054fba  mov     rcx, rbx; lpCriticalSection
0x180054fbd  call    cs:__imp_DeleteCriticalSection
0x180054fc3  mov     [rbx+28h], r14b
0x180054fc7  mov     rbx, [rdi+168h]
0x180054fce  lea     rsi, [rdi+170h]
0x180054fd5  test    rbx, rbx
0x180054fd8  jz      short loc_180054FFC
0x180054fda  mov     rbp, [rsi]
0x180054fdd  jmp     short loc_180054FEB
0x180054fdf  mov     rdx, rbx
0x180054fe2  call    ??$_Dest_val@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@std@@YAXAEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::_Dest_val<std::allocator<std::wstring>,std::wstring>(std::allocator<std::wstring> &,std::wstring *)
0x180054fe7  add     rbx, 28h ; '('
0x180054feb  cmp     rbx, rbp
0x180054fee  jnz     short loc_180054FDF
0x180054ff0  mov     rcx, [rdi+168h]; Block
0x180054ff7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180054ffc  mov     [rdi+168h], r14
0x180055003  mov     [rsi], r14
0x180055006  mov     [rdi+178h], r14
0x18005500d  lea     rbx, [rdi+148h]
0x180055014  mov     [rsp+58h+var_38], rbx
0x180055019  mov     rcx, rbx
0x18005501c  call    ?clear@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tset_traits<std::wstring,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::wstring>,0>>::clear(void)
0x180055021  nop
0x180055022  mov     rcx, [rbx+8]; Block
0x180055026  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005502b  nop
0x18005502c  mov     rbx, [rdi+120h]
0x180055033  lea     rsi, [rdi+128h]
0x18005503a  test    rbx, rbx
0x18005503d  jz      short loc_180055061
0x18005503f  mov     rbp, [rsi]
0x180055042  jmp     short loc_180055050
0x180055044  mov     rdx, rbx
0x180055047  call    ??$_Dest_val@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@std@@YAXAEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::_Dest_val<std::allocator<std::wstring>,std::wstring>(std::allocator<std::wstring> &,std::wstring *)
0x18005504c  add     rbx, 28h ; '('
0x180055050  cmp     rbx, rbp
0x180055053  jnz     short loc_180055044
0x180055055  mov     rcx, [rdi+120h]; Block
0x18005505c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180055061  mov     [rdi+120h], r14
0x180055068  mov     [rsi], r14
0x18005506b  mov     [rdi+130h], r14
0x180055072  mov     rcx, [rdi+110h]; bstrString
0x180055079  call    cs:__imp_SysFreeString
0x18005507f  nop
0x180055080  mov     rbx, [rdi+0E8h]
0x180055087  lea     rsi, [rdi+0F0h]
0x18005508e  test    rbx, rbx
0x180055091  jz      short loc_1800550B5
0x180055093  mov     rbp, [rsi]
0x180055096  jmp     short loc_1800550A4
0x180055098  mov     rdx, rbx
0x18005509b  call    ??$_Dest_val@V?$allocator@VCPropertyValue@@@std@@VCPropertyValue@@@std@@YAXAEAV?$allocator@VCPropertyValue@@@0@PEAVCPropertyValue@@@Z; std::_Dest_val<std::allocator<CPropertyValue>,CPropertyValue>(std::allocator<CPropertyValue> &,CPropertyValue *)
0x1800550a0  add     rbx, 60h ; '`'
0x1800550a4  cmp     rbx, rbp
0x1800550a7  jnz     short loc_180055098
0x1800550a9  mov     rcx, [rdi+0E8h]; Block
0x1800550b0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800550b5  mov     [rdi+0E8h], r14
0x1800550bc  mov     [rsi], r14
0x1800550bf  mov     [rdi+0F8h], r14
0x1800550c6  mov     rbx, [rdi+0C8h]
0x1800550cd  lea     rsi, [rdi+0D0h]
0x1800550d4  test    rbx, rbx
0x1800550d7  jz      short loc_1800550FB
0x1800550d9  mov     rbp, [rsi]
0x1800550dc  jmp     short loc_1800550EA
0x1800550de  mov     rdx, rbx
0x1800550e1  call    ??$_Dest_val@V?$allocator@VCPropertyValue@@@std@@VCPropertyValue@@@std@@YAXAEAV?$allocator@VCPropertyValue@@@0@PEAVCPropertyValue@@@Z; std::_Dest_val<std::allocator<CPropertyValue>,CPropertyValue>(std::allocator<CPropertyValue> &,CPropertyValue *)
0x1800550e6  add     rbx, 60h ; '`'
0x1800550ea  cmp     rbx, rbp
0x1800550ed  jnz     short loc_1800550DE
0x1800550ef  mov     rcx, [rdi+0C8h]; Block
0x1800550f6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800550fb  mov     [rdi+0C8h], r14
0x180055102  mov     [rsi], r14
0x180055105  mov     [rdi+0D8h], r14
0x18005510c  mov     rbx, [rdi+0A8h]
0x180055113  lea     rsi, [rdi+0B0h]
0x18005511a  test    rbx, rbx
0x18005511d  jz      short loc_180055141
0x18005511f  mov     rbp, [rsi]
0x180055122  jmp     short loc_180055130
0x180055124  mov     rdx, rbx
0x180055127  call    ??$_Dest_val@V?$allocator@VCPropertyValue@@@std@@VCPropertyValue@@@std@@YAXAEAV?$allocator@VCPropertyValue@@@0@PEAVCPropertyValue@@@Z; std::_Dest_val<std::allocator<CPropertyValue>,CPropertyValue>(std::allocator<CPropertyValue> &,CPropertyValue *)
0x18005512c  add     rbx, 60h ; '`'
0x180055130  cmp     rbx, rbp
0x180055133  jnz     short loc_180055124
0x180055135  mov     rcx, [rdi+0A8h]; Block
0x18005513c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180055141  mov     [rdi+0A8h], r14
0x180055148  mov     [rsi], r14
0x18005514b  mov     [rdi+0B8h], r14
0x180055152  mov     rbx, [rdi+88h]
0x180055159  lea     rsi, [rdi+90h]
0x180055160  test    rbx, rbx
0x180055163  jz      short loc_180055187
0x180055165  mov     rbp, [rsi]
0x180055168  jmp     short loc_180055176
0x18005516a  mov     rdx, rbx
0x18005516d  call    ??$_Dest_val@V?$allocator@VCPropertyValue@@@std@@VCPropertyValue@@@std@@YAXAEAV?$allocator@VCPropertyValue@@@0@PEAVCPropertyValue@@@Z; std::_Dest_val<std::allocator<CPropertyValue>,CPropertyValue>(std::allocator<CPropertyValue> &,CPropertyValue *)
0x180055172  add     rbx, 60h ; '`'
0x180055176  cmp     rbx, rbp
0x180055179  jnz     short loc_18005516A
0x18005517b  mov     rcx, [rdi+88h]; Block
0x180055182  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180055187  mov     [rdi+88h], r14
0x18005518e  mov     [rsi], r14
0x180055191  mov     [rdi+98h], r14
0x180055198  mov     rcx, [rdi+80h]
0x18005519f  test    rcx, rcx
0x1800551a2  jz      short loc_1800551B1
0x1800551a4  mov     rax, [rcx]
0x1800551a7  mov     rax, [rax+8]
0x1800551ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800551b0  nop
0x1800551b1  mov     rcx, [rdi+78h]; bstrString
0x1800551b5  call    cs:__imp_SysFreeString
0x1800551bb  nop
0x1800551bc  lea     rcx, [rdi+48h]; lpCriticalSection
0x1800551c0  mov     eax, [rcx+28h]
0x1800551c3  cmp     eax, 1
0x1800551c6  jnz     short loc_1800551CF
0x1800551c8  call    cs:__imp_DeleteCriticalSection
0x1800551ce  nop
0x1800551cf  lea     rax, [rdi+8]
0x1800551d3  mov     [rsp+58h+arg_8], rax
0x1800551d8  lea     rcx, [rax+8]; lpCriticalSection
0x1800551dc  mov     [rsp+58h+arg_10], rcx
0x1800551e1  cmp     [rcx+28h], r14b
0x1800551e5  jz      short loc_1800551F2
0x1800551e7  mov     [rcx+28h], r14b
0x1800551eb  call    cs:__imp_DeleteCriticalSection
0x1800551f1  nop
0x1800551f2  add     rsp, 30h
0x1800551f6  pop     r14
0x1800551f8  pop     rdi
0x1800551f9  pop     rsi
0x1800551fa  pop     rbp
0x1800551fb  pop     rbx
0x1800551fc  retn
```
