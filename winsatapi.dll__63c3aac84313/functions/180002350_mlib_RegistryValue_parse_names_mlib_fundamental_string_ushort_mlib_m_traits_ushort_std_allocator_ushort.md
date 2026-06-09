# mlib::RegistryValue::parse_names(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180002350`
- end: `0x1800024b2`
- name: `?parse_names@RegistryValue@mlib@@IEAAHV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z`
- size: `354`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x180006148`
- `0x18000f774`

## callees

- `0x1800019d0`
- `0x180002350`
- `0x1800024b8`
- `0x18000305c`
- `0x180006070`
- `0x1800071d0`
- `0x18000fe00`
- `0x180011718`
- `0x180011800`
- `0x18001cfc0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800023ff`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002408`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800023ff`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002408`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall mlib::RegistryValue::parse_names(__int64 a1, __int64 *a2)
{
  __int64 v4; // rax
  __int64 v5; // rdi
  __int64 v6; // r9
  __int64 v7; // rax
  void *v9; // rdi
  void *v10; // rcx
  __int64 *v11; // rax
  __int64 v12; // rax
  _QWORD *v13; // rax
  _QWORD *v15; // [rsp+60h] [rbp+18h] BYREF

  if ( *(_WORD *)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::begin(a2) == 92 )
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::erase(
      a2,
      0,
      1);
  v4 = mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::rfind(a2);
  v5 = v4;
  v6 = *(_QWORD *)*a2;
  if ( v4 == v6 - 1 )
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::clear(a1 + 48);
    v7 = mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::substr(
           a2,
           &v15,
           0,
           *(_QWORD *)*a2 - 1LL);
    mlib::RegistryKey::setSubKeyName(a1, v7);
    if ( v15[2]-- == 1 )
    {
      v9 = v15;
      if ( v15 )
      {
        v10 = (void *)v15[3];
        if ( v10 )
          operator delete(v10);
        operator delete(v9);
      }
    }
  }
  else if ( v4 == -1 )
  {
    v13 = mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(&v15);
    mlib::RegistryKey::setSubKeyName(a1, v13);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v15);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
      (_QWORD *)(a1 + 48),
      *a2);
  }
  else
  {
    v11 = (__int64 *)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::substr(
                       a2,
                       &v15,
                       v4 + 1,
                       v6 - v4);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
      (_QWORD *)(a1 + 48),
      *v11);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v15);
    v12 = mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::substr(
            a2,
            &v15,
            0,
            v5);
    mlib::RegistryKey::setSubKeyName(a1, v12);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v15);
  }
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)a2);
  return 0;
}

```

## disassembly

```asm
0x180002350  mov     [rsp+arg_8], rdx
0x180002355  push    rbp
0x180002356  push    rsi
0x180002357  push    rdi
0x180002358  sub     rsp, 30h
0x18000235c  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x180002365  mov     [rsp+48h+arg_0], rbx
0x18000236a  mov     rbx, rdx
0x18000236d  mov     rsi, rcx
0x180002370  mov     rcx, rdx
0x180002373  call    ?begin@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAPEAGXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::begin(void)
0x180002378  cmp     word ptr [rax], 5Ch ; '\'
0x18000237c  jnz     short loc_18000238C
0x18000237e  xor     edx, edx
0x180002380  lea     r8d, [rdx+1]
0x180002384  mov     rcx, rbx
0x180002387  call    ?erase@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@_K0@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::erase(unsigned __int64,unsigned __int64)
0x18000238c  mov     rcx, rbx
0x18000238f  call    ?rfind@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEBA_KG_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::rfind(ushort,unsigned __int64)
0x180002394  mov     rdi, rax
0x180002397  mov     rcx, [rbx]
0x18000239a  mov     r9, [rcx]
0x18000239d  lea     rbp, [rsi+30h]
0x1800023a1  lea     rdx, [r9-1]
0x1800023a5  cmp     rax, rdx
0x1800023a8  jnz     short loc_180002413
0x1800023aa  mov     rcx, rbp
0x1800023ad  call    ?clear@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::clear(void)
0x1800023b2  mov     rax, [rbx]
0x1800023b5  mov     r9, [rax]
0x1800023b8  dec     r9
0x1800023bb  xor     r8d, r8d
0x1800023be  lea     rdx, [rsp+48h+arg_10]
0x1800023c3  mov     rcx, rbx
0x1800023c6  call    ?substr@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEBA?AV12@_K0@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::substr(unsigned __int64,unsigned __int64)
0x1800023cb  nop
0x1800023cc  mov     rdx, rax
0x1800023cf  mov     rcx, rsi
0x1800023d2  call    ?setSubKeyName@RegistryKey@mlib@@QEAAXAEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::RegistryKey::setSubKeyName(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x1800023d7  nop
0x1800023d8  mov     rax, [rsp+48h+arg_10]
0x1800023dd  sub     qword ptr [rax+10h], 1
0x1800023e2  jnz     loc_18000249B
0x1800023e8  mov     rdi, [rsp+48h+arg_10]
0x1800023ed  test    rdi, rdi
0x1800023f0  jz      loc_18000249B
0x1800023f6  mov     rcx, [rdi+18h]
0x1800023fa  test    rcx, rcx
0x1800023fd  jz      short loc_180002405
0x1800023ff  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002405  mov     rcx, rdi
0x180002408  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000240e  jmp     loc_18000249B
0x180002413  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180002417  jz      short loc_18000246E
0x180002419  sub     r9, rdi
0x18000241c  lea     r8, [rax+1]
0x180002420  lea     rdx, [rsp+48h+arg_10]
0x180002425  mov     rcx, rbx
0x180002428  call    ?substr@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEBA?AV12@_K0@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::substr(unsigned __int64,unsigned __int64)
0x18000242d  mov     rdx, [rax]
0x180002430  mov     rcx, rbp
0x180002433  call    ?attach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXPEAV?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::attach_buf(mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x180002438  lea     rcx, [rsp+48h+arg_10]
0x18000243d  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180002442  mov     r9, rdi
0x180002445  xor     r8d, r8d
0x180002448  lea     rdx, [rsp+48h+arg_10]
0x18000244d  mov     rcx, rbx
0x180002450  call    ?substr@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEBA?AV12@_K0@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::substr(unsigned __int64,unsigned __int64)
0x180002455  nop
0x180002456  mov     rdx, rax
0x180002459  mov     rcx, rsi
0x18000245c  call    ?setSubKeyName@RegistryKey@mlib@@QEAAXAEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::RegistryKey::setSubKeyName(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x180002461  nop
0x180002462  lea     rcx, [rsp+48h+arg_10]
0x180002467  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18000246c  jmp     short loc_18000249B
0x18000246e  lea     rcx, [rsp+48h+arg_10]
0x180002473  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(void)
0x180002478  nop
0x180002479  mov     rdx, rax
0x18000247c  mov     rcx, rsi
0x18000247f  call    ?setSubKeyName@RegistryKey@mlib@@QEAAXAEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::RegistryKey::setSubKeyName(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x180002484  nop
0x180002485  lea     rcx, [rsp+48h+arg_10]
0x18000248a  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18000248f  mov     rdx, [rbx]
0x180002492  mov     rcx, rbp
0x180002495  call    ?attach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXPEAV?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::attach_buf(mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x18000249a  nop
0x18000249b  mov     rcx, rbx
0x18000249e  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x1800024a3  xor     eax, eax
0x1800024a5  mov     rbx, [rsp+48h+arg_0]
0x1800024aa  add     rsp, 30h
0x1800024ae  pop     rdi
0x1800024af  pop     rsi
0x1800024b0  pop     rbp
0x1800024b1  retn
```
