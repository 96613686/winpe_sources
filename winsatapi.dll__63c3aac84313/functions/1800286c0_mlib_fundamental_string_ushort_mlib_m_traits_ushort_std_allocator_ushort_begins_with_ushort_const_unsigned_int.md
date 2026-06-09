# mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::begins_with(ushort const *,unsigned __int64)

- ea: `0x1800286c0`
- end: `0x18002878e`
- name: `?begins_with@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA_NPEBG_K@Z`
- size: `206`
- prototype: `bool __fastcall(__int64, const WCHAR *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800240bc`

## callees

- `0x18000ac70`
- `0x18000db1c`
- `0x180011210`
- `0x180013fa3`
- `0x1800286c0`
- `0x18002dec0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180028760`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180028760`

## pseudocode

```c
bool __fastcall mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::begins_with(
        __int64 a1,
        const WCHAR *a2,
        __int64 a3)
{
  char *v5; // rdx
  int cchCount2; // eax
  char pExceptionObject[24]; // [rsp+38h] [rbp-50h] BYREF
  _QWORD v9[4]; // [rsp+50h] [rbp-38h] BYREF

  if ( !a2 )
  {
    v5 = (char *)mlib::_msrse_(v9, (__int64)"str is null", a3, 5791);
    std::out_of_range::out_of_range(pExceptionObject, v5);
    throw (std::invalid_argument *)pExceptionObject;
  }
  if ( !**(_QWORD **)a1 || !*a2 )
    return 0;
  cchCount2 = mlib::m_traits<unsigned short>::CStrlen(a2, 0x10000);
  return CompareStringW(0x400u, 0x1000u, *(PCNZWCH *)(*(_QWORD *)a1 + 24LL), cchCount2, a2, cchCount2) == 2;
}

```

## disassembly

```asm
0x1800286c0  mov     r11, rsp
0x1800286c3  push    rdi
0x1800286c4  sub     rsp, 80h
0x1800286cb  mov     qword ptr [r11-58h], 0FFFFFFFFFFFFFFFEh
0x1800286d3  mov     [r11+18h], rbx
0x1800286d7  mov     rax, cs:__security_cookie
0x1800286de  xor     rax, rsp
0x1800286e1  mov     [rsp+88h+var_18], rax
0x1800286e6  mov     rbx, rdx
0x1800286e9  mov     rdi, rcx
0x1800286ec  xor     ecx, ecx
0x1800286ee  test    rdx, rdx
0x1800286f1  jnz     short loc_180028729
0x1800286f3  mov     r9d, 169Fh
0x1800286f9  lea     rdx, aStrIsNull; "str is null"
0x180028700  lea     rcx, [r11-38h]; void *
0x180028704  call    ?_msrse_@mlib@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD0H@Z; mlib::_msrse_(char const *,char const *,int)
0x180028709  nop
0x18002870a  mov     rdx, rax
0x18002870d  lea     rcx, [rsp+88h+pExceptionObject]
0x180028712  call    ??0out_of_range@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::out_of_range::out_of_range(std::string const &)
0x180028717  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x18002871e  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180028723  call    _CxxThrowException_0
0x180028729  mov     rax, [rdi]
0x18002872c  cmp     [rax], rcx
0x18002872f  jz      short loc_18002876E
0x180028731  cmp     [rdx], cx
0x180028734  jz      short loc_18002876E
0x180028736  mov     edx, 10000h
0x18002873b  mov     rcx, rbx
0x18002873e  call    ?CStrlen@?$m_traits@G@mlib@@SA_KPEBG_K@Z; mlib::m_traits<ushort>::CStrlen(ushort const *,unsigned __int64)
0x180028743  mov     r8, [rdi]
0x180028746  mov     [rsp+88h+cchCount2], eax; cchCount2
0x18002874a  mov     [rsp+88h+lpString2], rbx; lpString2
0x18002874f  mov     r9d, eax; cchCount1
0x180028752  mov     r8, [r8+18h]; lpString1
0x180028756  mov     edx, 1000h; dwCmpFlags
0x18002875b  mov     ecx, 400h; Locale
0x180028760  call    cs:__imp_CompareStringW
0x180028766  cmp     eax, 2
0x180028769  setz    al
0x18002876c  jmp     short loc_180028770
0x18002876e  xor     al, al
0x180028770  mov     rcx, [rsp+88h+var_18]
0x180028775  xor     rcx, rsp; StackCookie
0x180028778  call    __security_check_cookie
0x18002877d  mov     rbx, [rsp+88h+arg_10]
0x180028785  add     rsp, 80h
0x18002878c  pop     rdi
0x18002878d  retn
```
