# DataStore::RemoveFilesFromDataStore(std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>,std::allocator<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>>> &,unsigned __int64)

- ea: `0x14001f494`
- end: `0x14001f5ef`
- name: `?RemoveFilesFromDataStore@DataStore@@CAKAEAV?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@_K@Z`
- size: `347`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x14001f5f8`
- `0x14001f9cc`

## callees

- `0x140004348`
- `0x140007f14`
- `0x1400085b4`
- `0x140016480`
- `0x140016d04`
- `0x140017af0`
- `0x14001f494`
- `0x140020858`
- `0x14004fe00`
- `0x1400530a8`
- `0x140113220`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x14001f505`
- `KERNEL32!DeleteFileW` at `0x14001f505`
- `KERNEL32!GetLastError` at `0x14001f51b`
- `KERNEL32!GetLastError` at `0x14001f51b`
- `KERNEL32!SetLastError` at `0x14001f5af`
- `KERNEL32!SetLastError` at `0x14001f5af`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DataStore::RemoveFilesFromDataStore(_QWORD *a1, unsigned __int64 a2)
{
  __int64 v4; // rdx
  __int64 *v5; // rbx
  unsigned __int16 v6; // r9
  const unsigned __int16 *v7; // rax
  __int64 *v8; // rax
  __int64 *v9; // rax
  __int64 *v10; // rax
  __int64 *v11; // rax
  _QWORD v13[2]; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD Buffer[64]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD dwErrCode; // [rsp+230h] [rbp+130h]
  char v16; // [rsp+234h] [rbp+134h]
  __int64 v17; // [rsp+238h] [rbp+138h]

  while ( 1 )
  {
    v4 = a1[1];
    if ( (v4 - *a1) >> 3 <= a2 )
      break;
    v13[0] = 0;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
      v13,
      *(_QWORD *)(v4 - 8));
    std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>::pop_back(a1);
    if ( !DeleteFileW(*(LPCWSTR *)(v13[0] + 24LL)) )
    {
      dwErrCode = GetLastError();
      v16 = 1;
      v17 = 0;
      mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
      v5 = (__int64 *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&mlib::stderrw)
                     + 240);
      v7 = mlib::MUIStr_((mlib *)"base\\winsat\\exe\\datastore.cpp", (const char *)0x378, 10034, v6);
      v8 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v5, (__int64)v7);
      v9 = (__int64 *)std::basic_ostream<unsigned short>::operator<<(v8, 10);
      v10 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v9, (__int64)L"       ");
      v11 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v10, (__int64)Buffer);
      std::endl(v11);
      SetLastError(dwErrCode);
      LODWORD(v5) = dwErrCode;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v13);
      return (unsigned int)v5;
    }
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v13);
  }
  return 0;
}

```

## disassembly

```asm
0x14001f494  mov     [rsp-8+arg_8], rbx
0x14001f499  mov     [rsp-8+arg_10], rdi
0x14001f49e  push    rbp
0x14001f49f  lea     rbp, [rsp-150h]
0x14001f4a7  sub     rsp, 250h
0x14001f4ae  mov     rax, cs:__security_cookie
0x14001f4b5  xor     rax, rsp
0x14001f4b8  mov     [rbp+150h+var_10], rax
0x14001f4bf  mov     rdi, rdx
0x14001f4c2  mov     rbx, rcx
0x14001f4c5  mov     rdx, [rbx+8]
0x14001f4c9  mov     rax, rdx
0x14001f4cc  sub     rax, [rbx]
0x14001f4cf  sar     rax, 3
0x14001f4d3  cmp     rax, rdi
0x14001f4d6  jbe     loc_14001F5C9
0x14001f4dc  mov     [rsp+250h+var_230], 0
0x14001f4e5  mov     rdx, [rdx-8]
0x14001f4e9  lea     rcx, [rsp+250h+var_230]
0x14001f4ee  call    ?attach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXPEAV?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::attach_buf(mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x14001f4f3  nop
0x14001f4f4  mov     rcx, rbx
0x14001f4f7  call    ?pop_back@?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@QEAAXXZ; std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>>::pop_back(void)
0x14001f4fc  mov     rcx, [rsp+250h+var_230]
0x14001f501  mov     rcx, [rcx+18h]; lpFileName
0x14001f505  call    cs:__imp_DeleteFileW
0x14001f50b  test    eax, eax
0x14001f50d  jz      short loc_14001F51B
0x14001f50f  lea     rcx, [rsp+250h+var_230]
0x14001f514  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14001f519  jmp     short loc_14001F4C5
0x14001f51b  call    cs:__imp_GetLastError
0x14001f521  mov     [rbp+150h+dwErrCode], eax
0x14001f527  mov     [rbp+150h+var_1C], 1
0x14001f52e  mov     [rbp+150h+var_18], 0
0x14001f539  lea     rcx, [rsp+250h+Buffer]; lpBuffer
0x14001f53e  call    ?fmt_desc@?$WinErrorT@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>>::fmt_desc(void)
0x14001f543  lea     rcx, ?stderrw@mlib@@3V?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@A; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>> mlib::stderrw
0x14001f54a  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14001f54f  lea     rbx, [rax+0F0h]
0x14001f556  mov     edx, 378h; char *
0x14001f55b  mov     r8d, 2732h; int
0x14001f561  lea     rcx, aBaseWinsatExeD; "base\\winsat\\exe\\datastore.cpp"
0x14001f568  call    ?MUIStr_@mlib@@YAPEBGPEBDHG@Z; mlib::MUIStr_(char const *,int,ushort)
0x14001f56d  mov     rdx, rax
0x14001f570  mov     rcx, rbx
0x14001f573  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14001f578  mov     edx, 0Ah
0x14001f57d  mov     rcx, rax
0x14001f580  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x14001f585  mov     rcx, rax
0x14001f588  lea     rdx, asc_14012C5C8; "       "
0x14001f58f  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14001f594  lea     rdx, [rsp+250h+Buffer]
0x14001f599  mov     rcx, rax
0x14001f59c  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14001f5a1  mov     rcx, rax
0x14001f5a4  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x14001f5a9  mov     ecx, [rbp+150h+dwErrCode]; dwErrCode
0x14001f5af  call    cs:__imp_SetLastError
0x14001f5b5  mov     ebx, [rbp+150h+dwErrCode]
0x14001f5bb  lea     rcx, [rsp+250h+var_230]
0x14001f5c0  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14001f5c5  mov     eax, ebx
0x14001f5c7  jmp     short loc_14001F5CB
0x14001f5c9  xor     eax, eax
0x14001f5cb  mov     rcx, [rbp+150h+var_10]
0x14001f5d2  xor     rcx, rsp; StackCookie
0x14001f5d5  call    __security_check_cookie
0x14001f5da  lea     r11, [rsp+250h+var_s0]
0x14001f5e2  mov     rbx, [r11+18h]
0x14001f5e6  mov     rdi, [r11+20h]
0x14001f5ea  mov     rsp, r11
0x14001f5ed  pop     rbp
0x14001f5ee  retn
```
