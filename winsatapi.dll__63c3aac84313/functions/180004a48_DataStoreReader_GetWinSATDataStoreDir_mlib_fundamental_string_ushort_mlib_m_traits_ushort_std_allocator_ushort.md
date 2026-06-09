# DataStoreReader::GetWinSATDataStoreDir(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180004a48`
- end: `0x180004b09`
- name: `?GetWinSATDataStoreDir@DataStoreReader@@SAJAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@Z`
- size: `193`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x180001a70`
- `0x180004e00`
- `0x18001f070`

## callees

- `0x180001944`
- `0x180002d48`
- `0x18000305c`
- `0x180004040`
- `0x180004a48`
- `0x180005370`
- `0x1800071d0`
- `0x18001c71c`
- `0x18001cf28`

## import_xrefs

- `SHELL32!SHGetFolderPathW` at `0x180004ac8`
- `SHELL32!SHGetFolderPathW` at `0x180004ac8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DataStoreReader::GetWinSATDataStoreDir(__int64 *a1)
{
  void *v2; // rax
  __int64 v3; // rdi
  HRESULT v4; // edi

  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::cow(a1);
  if ( *(_QWORD *)(*a1 + 8) < 0x104u )
  {
    v2 = mlib::mstring_buf<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::operator new();
    if ( v2 )
      v3 = mlib::mstring_buf<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::mstring_buf<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
             v2,
             *(_QWORD *)(*a1 + 24),
             *(_QWORD *)*a1,
             260);
    else
      v3 = 0;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)a1);
    *a1 = v3;
  }
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::clear((__int64)a1);
  v4 = SHGetFolderPathW(0, 36, 0, 0, *(LPWSTR *)(*a1 + 24));
  if ( v4 >= 0 )
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::resize(a1);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::ensure_trailing_slash(a1);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::append(
      a1,
      L"Performance\\WinSAT\\DataStore");
    return 0;
  }
  else
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::clear((__int64)a1);
    return (unsigned int)v4;
  }
}

```

## disassembly

```asm
0x180004a48  push    rdi
0x180004a4a  sub     rsp, 40h
0x180004a4e  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x180004a57  mov     [rsp+48h+arg_8], rbx
0x180004a5c  mov     rbx, rcx
0x180004a5f  call    ?cow@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::cow(void)
0x180004a64  mov     rax, [rbx]
0x180004a67  mov     edi, 104h
0x180004a6c  cmp     [rax+8], rdi
0x180004a70  jnb     short loc_180004AA8
0x180004a72  call    ??2?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@CAPEAX_K@Z; mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::operator new(unsigned __int64)
0x180004a77  mov     [rsp+48h+var_10], rax
0x180004a7c  test    rax, rax
0x180004a7f  jz      short loc_180004A9B
0x180004a81  mov     rdx, [rbx]
0x180004a84  mov     r9d, edi
0x180004a87  mov     r8, [rdx]
0x180004a8a  mov     rdx, [rdx+18h]
0x180004a8e  mov     rcx, rax
0x180004a91  call    ??0?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@AEAA@PEBG_K1AEBV?$allocator@G@std@@@Z; mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *,unsigned __int64,unsigned __int64,std::allocator<ushort> const &)
0x180004a96  mov     rdi, rax
0x180004a99  jmp     short loc_180004A9D
0x180004a9b  xor     edi, edi
0x180004a9d  mov     rcx, rbx
0x180004aa0  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180004aa5  mov     [rbx], rdi
0x180004aa8  mov     rcx, rbx
0x180004aab  call    ?clear@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::clear(void)
0x180004ab0  mov     rax, [rbx]
0x180004ab3  mov     rdx, [rax+18h]
0x180004ab7  mov     [rsp+48h+pszPath], rdx; pszPath
0x180004abc  xor     r9d, r9d; dwFlags
0x180004abf  xor     r8d, r8d; hToken
0x180004ac2  lea     edx, [r9+24h]; csidl
0x180004ac6  xor     ecx, ecx; hwnd
0x180004ac8  call    cs:__imp_SHGetFolderPathW
0x180004ace  mov     edi, eax
0x180004ad0  mov     rcx, rbx
0x180004ad3  test    eax, eax
0x180004ad5  jns     short loc_180004AE0
0x180004ad7  call    ?clear@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::clear(void)
0x180004adc  mov     eax, edi
0x180004ade  jmp     short loc_180004AFE
0x180004ae0  call    ?resize@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::resize(void)
0x180004ae5  mov     rcx, rbx
0x180004ae8  call    ?ensure_trailing_slash@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::ensure_trailing_slash(void)
0x180004aed  lea     rdx, aPerformanceWin; "Performance\\WinSAT\\DataStore"
0x180004af4  mov     rcx, rbx
0x180004af7  call    ?append@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::append(ushort const *)
0x180004afc  xor     eax, eax
0x180004afe  mov     rbx, [rsp+48h+arg_8]
0x180004b03  add     rsp, 40h
0x180004b07  pop     rdi
0x180004b08  retn
```
