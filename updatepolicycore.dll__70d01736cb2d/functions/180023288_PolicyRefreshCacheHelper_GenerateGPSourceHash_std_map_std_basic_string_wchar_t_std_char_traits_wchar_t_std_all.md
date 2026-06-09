# PolicyRefreshCacheHelper::GenerateGPSourceHash(std::map<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x180023288`
- end: `0x180023456`
- name: `?GenerateGPSourceHash@PolicyRefreshCacheHelper@@CAJV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@std@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@@Z`
- size: `462`
- prototype: `__int64 __fastcall(_QWORD **, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x1800236b8`

## callees

- `0x18000aac0`
- `0x18000e7e4`
- `0x18000fb4c`
- `0x180010260`
- `0x1800191d4`
- `0x18001eea4`
- `0x180022fc4`
- `0x180023288`
- `0x18002436c`
- `0x180024464`
- `0x1800246ac`
- `0x18002ffd0`

## string_xrefs

- `0x1800233f0`: `C:\__w\1\s\src\Client\policy\src\helpers\PolicyRefreshCacheHelper.cpp`

## pseudocode

```c
__int64 __fastcall PolicyRefreshCacheHelper::GenerateGPSourceHash(_QWORD **a1, __int64 a2)
{
  __int64 *v4; // rbx
  __int64 v5; // rcx
  __int64 v6; // rax
  __int64 **v7; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  _QWORD *v10; // rax
  int Hash; // eax
  unsigned int v12; // ebx
  int v14; // [rsp+20h] [rbp-79h]
  _BYTE v15[32]; // [rsp+48h] [rbp-51h] BYREF
  _BYTE v16[32]; // [rsp+68h] [rbp-31h] BYREF
  _BYTE v17[32]; // [rsp+88h] [rbp-11h] BYREF
  _QWORD **v18; // [rsp+A8h] [rbp+Fh]
  _OWORD v19[2]; // [rsp+B0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v18 = a1;
  v19[0] = 0;
  v19[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v19[0]) = 0;
  v4 = (__int64 *)**a1;
  while ( !*((_BYTE *)v4 + 25) )
  {
    v5 = v4[6];
    if ( v5 == 0x7FFFFFFFFFFFFFFELL )
      std::_Xlen_string();
    std::wstring::wstring(v16, v5, L"=", 1);
    v6 = std::operator+<wchar_t>(v15, v16, v4 + 8);
    std::operator+<wchar_t>(v17, v6, L";");
    std::wstring::operator+=(v19);
    std::wstring::~wstring(v17);
    std::wstring::~wstring(v15);
    std::wstring::~wstring(v16);
    v7 = (__int64 **)v4[2];
    if ( *((_BYTE *)v7 + 25) )
    {
      for ( i = (__int64 *)v4[1]; !*((_BYTE *)i + 25) && v4 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v4 = i;
      v4 = i;
    }
    else
    {
      v4 = (__int64 *)v4[2];
      for ( j = *v7; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v4 = j;
    }
  }
  v10 = (_QWORD *)std::wstring::wstring(v15, v19);
  Hash = PolicyRefreshCacheHelper::GenerateHash(v10, a2);
  v12 = Hash;
  if ( Hash >= 0 )
  {
    std::wstring::~wstring(v19);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(a1);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\helpers\\PolicyRefreshCacheHelper.cpp",
      (const char *)(unsigned int)Hash,
      v14);
    std::wstring::~wstring(v19);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(a1);
    return v12;
  }
}

```

## disassembly

```asm
0x180023288  mov     [rsp-8+arg_10], rbx
0x18002328d  mov     [rsp-8+arg_18], rsi
0x180023292  push    rbp
0x180023293  push    rdi
0x180023294  push    r14
0x180023296  lea     rbp, [rsp-47h]
0x18002329b  sub     rsp, 0E0h
0x1800232a2  mov     rax, cs:__security_cookie
0x1800232a9  xor     rax, rsp
0x1800232ac  mov     [rbp+57h+var_20], rax
0x1800232b0  mov     rsi, rdx
0x1800232b3  mov     rdi, rcx
0x1800232b6  mov     [rbp+57h+var_48], rcx
0x1800232ba  xor     r14d, r14d
0x1800232bd  xorps   xmm0, xmm0
0x1800232c0  movups  [rbp+57h+var_40], xmm0
0x1800232c4  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800232cc  movdqu  [rbp+57h+var_30], xmm1
0x1800232d1  mov     word ptr [rbp+57h+var_40], r14w
0x1800232d6  mov     rbx, [rcx]
0x1800232d9  mov     rbx, [rbx]
0x1800232dc  jmp     loc_1800233C1
0x1800232e1  lea     r9, [rbx+20h]
0x1800232e5  mov     rcx, [rbx+30h]
0x1800232e9  mov     rax, 7FFFFFFFFFFFFFFEh
0x1800232f3  sub     rax, rcx
0x1800232f6  cmp     rax, 1
0x1800232fa  jb      loc_180023450
0x180023300  cmp     qword ptr [r9+18h], 7
0x180023305  jbe     short loc_18002330A
0x180023307  mov     r9, [r9]
0x18002330a  mov     [rsp+0F0h+var_C0], 1; __int64
0x180023313  lea     rax, asc_18003F434; "="
0x18002331a  mov     [rsp+0F0h+Src], rax; Src
0x18002331f  mov     [rsp+0F0h+var_D0], rcx; int
0x180023324  lea     rcx, [rbp+57h+var_88]; void *
0x180023328  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEB_W_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x18002332d  nop
0x18002332e  lea     r8, [rbx+40h]
0x180023332  lea     rdx, [rbp+57h+var_88]
0x180023336  lea     rcx, [rbp+57h+var_A8]
0x18002333a  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring const &)
0x18002333f  nop
0x180023340  lea     r8, asc_18003F430; ";"
0x180023347  mov     rdx, rax
0x18002334a  lea     rcx, [rbp+57h+var_68]
0x18002334e  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x180023353  nop
0x180023354  mov     rdx, rax
0x180023357  lea     rcx, [rbp+57h+var_40]; Src
0x18002335b  call    ??Y?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator+=(std::wstring const &)
0x180023360  nop
0x180023361  lea     rcx, [rbp+57h+var_68]; void *
0x180023365  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002336a  nop
0x18002336b  lea     rcx, [rbp+57h+var_A8]; void *
0x18002336f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023374  nop
0x180023375  lea     rcx, [rbp+57h+var_88]; void *
0x180023379  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002337e  mov     rcx, [rbx+10h]
0x180023382  cmp     [rcx+19h], r14b
0x180023386  jz      short loc_1800233A6
0x180023388  mov     rax, [rbx+8]
0x18002338c  jmp     short loc_18002339B
0x18002338e  cmp     rbx, [rax+10h]
0x180023392  jnz     short loc_1800233A1
0x180023394  mov     rbx, rax
0x180023397  mov     rax, [rax+8]
0x18002339b  cmp     [rax+19h], r14b
0x18002339f  jz      short loc_18002338E
0x1800233a1  mov     rbx, rax
0x1800233a4  jmp     short loc_1800233C1
0x1800233a6  mov     rbx, rcx
0x1800233a9  mov     rcx, [rcx]
0x1800233ac  cmp     [rcx+19h], r14b
0x1800233b0  jnz     short loc_1800233C1
0x1800233b2  mov     rbx, rcx
0x1800233b5  mov     rax, [rcx]
0x1800233b8  mov     rcx, rax
0x1800233bb  cmp     [rax+19h], r14b
0x1800233bf  jz      short loc_1800233B2
0x1800233c1  cmp     [rbx+19h], r14b
0x1800233c5  jz      loc_1800232E1
0x1800233cb  lea     rdx, [rbp+57h+var_40]
0x1800233cf  lea     rcx, [rbp+57h+var_A8]
0x1800233d3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800233d8  mov     rdx, rsi
0x1800233db  mov     rcx, rax; void *
0x1800233de  call    ?GenerateHash@PolicyRefreshCacheHelper@@CAJV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV23@@Z; PolicyRefreshCacheHelper::GenerateHash(std::wstring,std::wstring &)
0x1800233e3  mov     ebx, eax
0x1800233e5  test    eax, eax
0x1800233e7  jns     short loc_180023418
0x1800233e9  mov     rcx, [rbp+5Fh]; this
0x1800233ed  mov     r9d, eax; char *
0x1800233f0  lea     r8, aCW1SSrcClientP_1; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x1800233f7  mov     edx, 0E8h; void *
0x1800233fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023401  nop
0x180023402  lea     rcx, [rbp+57h+var_40]; void *
0x180023406  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002340b  nop
0x18002340c  mov     rcx, rdi
0x18002340f  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x180023414  mov     eax, ebx
0x180023416  jmp     short loc_18002342C
0x180023418  lea     rcx, [rbp+57h+var_40]; void *
0x18002341c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023421  nop
0x180023422  mov     rcx, rdi
0x180023425  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x18002342a  xor     eax, eax
0x18002342c  mov     rcx, [rbp+57h+var_20]
0x180023430  xor     rcx, rsp; StackCookie
0x180023433  call    __security_check_cookie
0x180023438  lea     r11, [rsp+0F0h+var_10]
0x180023440  mov     rbx, [r11+30h]
0x180023444  mov     rsi, [r11+38h]
0x180023448  mov     rsp, r11
0x18002344b  pop     r14
0x18002344d  pop     rdi
0x18002344e  pop     rbp
0x18002344f  retn
0x180023450  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
