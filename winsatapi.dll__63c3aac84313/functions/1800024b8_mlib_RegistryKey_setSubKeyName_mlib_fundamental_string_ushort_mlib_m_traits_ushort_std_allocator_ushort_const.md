# mlib::RegistryKey::setSubKeyName(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800024b8`
- end: `0x180002590`
- name: `?setSubKeyName@RegistryKey@mlib@@QEAAXAEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z`
- size: `216`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x180002350`

## callees

- `0x1800020a0`
- `0x1800024b8`
- `0x180004b10`
- `0x1800071d0`
- `0x18001040c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002544`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000254d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002544`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000254d`

## pseudocode

```c
void __fastcall mlib::RegistryKey::setSubKeyName(_QWORD *a1, _QWORD *a2)
{
  _QWORD *v2; // rbx
  _QWORD **v3; // rdi
  __int64 v5; // rdx
  _QWORD *v6; // rbx
  _QWORD *v7; // rbx
  _QWORD **v8; // rsi
  __int64 v9; // rax
  void *v10; // rcx

  v2 = (_QWORD *)*a2;
  v3 = (_QWORD **)(a1 + 2);
  if ( a1[2] )
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)v3);
  *v3 = v2;
  ++v2[2];
  mlib::RegistryBaseKey::cleanup(v3);
  v6 = (_QWORD *)a1[5];
  if ( *v6 )
  {
    ++v6[2];
    v8 = (_QWORD **)(a1 + 3);
    if ( *v8 )
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)v8);
    *v8 = v6;
    v9 = v6[2];
    v6[2] = v9;
    if ( !v9 )
    {
      v10 = (void *)v6[3];
      if ( v10 )
        operator delete(v10);
      operator delete(v6);
    }
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::append(
      v8,
      v5,
      92);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::munge(
      v8,
      0,
      **v8);
  }
  else
  {
    v7 = *v3;
    if ( a1[3] )
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)(a1 + 3));
    a1[3] = v7;
    ++v7[2];
  }
}

```

## disassembly

```asm
0x1800024b8  mov     [rsp+arg_0], rbx
0x1800024bd  mov     [rsp+arg_8], rsi
0x1800024c2  push    rdi
0x1800024c3  sub     rsp, 30h
0x1800024c7  mov     rbx, [rdx]
0x1800024ca  lea     rdi, [rcx+10h]
0x1800024ce  cmp     qword ptr [rdi], 0
0x1800024d2  mov     rsi, rcx
0x1800024d5  jz      short loc_1800024DF
0x1800024d7  mov     rcx, rdi
0x1800024da  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x1800024df  mov     [rdi], rbx
0x1800024e2  mov     rcx, rdi
0x1800024e5  inc     qword ptr [rbx+10h]
0x1800024e9  call    ?cleanup@RegistryBaseKey@mlib@@SAXAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::RegistryBaseKey::cleanup(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)
0x1800024ee  mov     rbx, [rsi+28h]
0x1800024f2  cmp     qword ptr [rbx], 0
0x1800024f6  jnz     short loc_180002515
0x1800024f8  cmp     qword ptr [rsi+18h], 0
0x1800024fd  mov     rbx, [rdi]
0x180002500  jz      short loc_18000250B
0x180002502  lea     rcx, [rsi+18h]
0x180002506  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18000250b  mov     [rsi+18h], rbx
0x18000250f  inc     qword ptr [rbx+10h]
0x180002513  jmp     short loc_180002580
0x180002515  inc     qword ptr [rbx+10h]
0x180002519  add     rsi, 18h
0x18000251d  cmp     qword ptr [rsi], 0
0x180002521  jz      short loc_18000252B
0x180002523  mov     rcx, rsi
0x180002526  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18000252b  mov     [rsi], rbx
0x18000252e  mov     rax, [rbx+10h]
0x180002532  mov     [rbx+10h], rax
0x180002536  test    rax, rax
0x180002539  jnz     short loc_180002553
0x18000253b  mov     rcx, [rbx+18h]
0x18000253f  test    rcx, rcx
0x180002542  jz      short loc_18000254A
0x180002544  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000254a  mov     rcx, rbx
0x18000254d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002553  mov     r8d, 5Ch ; '\'
0x180002559  mov     rcx, rsi
0x18000255c  call    ?append@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@_KG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::append(unsigned __int64,ushort)
0x180002561  mov     r9, [rdi]
0x180002564  xor     edx, edx
0x180002566  mov     r8, [rsi]
0x180002569  mov     rcx, rsi
0x18000256c  mov     rax, [r9]
0x18000256f  mov     r9, [r9+18h]
0x180002573  mov     r8, [r8]
0x180002576  mov     [rsp+38h+var_18], rax
0x18000257b  call    ?munge@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAX_K0PEBG0@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::munge(unsigned __int64,unsigned __int64,ushort const *,unsigned __int64)
0x180002580  mov     rbx, [rsp+38h+arg_0]
0x180002585  mov     rsi, [rsp+38h+arg_8]
0x18000258a  add     rsp, 30h
0x18000258e  pop     rdi
0x18000258f  retn
```
