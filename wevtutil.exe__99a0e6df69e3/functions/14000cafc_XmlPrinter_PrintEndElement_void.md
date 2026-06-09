# XmlPrinter::PrintEndElement(void)

- ea: `0x14000cafc`
- end: `0x14000cbfd`
- name: `?PrintEndElement@XmlPrinter@@QEAAXXZ`
- size: `257`
- prototype: `void __fastcall(XmlPrinter *__hidden this)`
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x14000db10`
- `0x14000e550`
- `0x1400100dc`
- `0x140026680`

## callees

- `0x14000cabc`
- `0x14000cafc`
- `0x14000cc04`
- `0x14000d144`
- `0x14000d868`
- `0x14000d88c`
- `0x140021b00`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall XmlPrinter::PrintEndElement(XmlPrinter *this)
{
  void *v2; // rax
  _QWORD *v3; // rbx
  void *v4; // rax
  __int128 v5; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v6[16]; // [rsp+30h] [rbp-48h] BYREF
  _BYTE Src[32]; // [rsp+40h] [rbp-38h] BYREF

  if ( *((_BYTE *)this + 32) )
  {
    std::wstring::wstring(Src, 2 * ((__int64)(*((_QWORD *)this + 2) - *((_QWORD *)this + 1)) >> 5) - 2);
    v2 = (void *)std::wstring::_Append<wchar_t>(Src);
    v3 = (_QWORD *)((char *)this + 16);
    v4 = (void *)std::wstring::_Append<wchar_t>(v2);
    std::wstring::_Append<wchar_t>(v4);
    v5 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v6);
    FilePuts(*(HANDLE *)this, &v5);
    std::wstring::_Tidy_deallocate(Src);
  }
  else
  {
    v3 = (_QWORD *)((char *)this + 16);
  }
  std::wstring::_Tidy_deallocate(*v3 - 32LL);
  *v3 -= 32LL;
}

```

## disassembly

```asm
0x14000cafc  mov     [rsp+arg_8], rbx
0x14000cb01  push    rdi
0x14000cb02  sub     rsp, 70h
0x14000cb06  mov     rax, cs:__security_cookie
0x14000cb0d  xor     rax, rsp
0x14000cb10  mov     [rsp+78h+var_18], rax
0x14000cb15  mov     rdi, rcx
0x14000cb18  cmp     byte ptr [rcx+20h], 0
0x14000cb1c  jz      loc_14000CBCE
0x14000cb22  mov     rdx, [rcx+10h]
0x14000cb26  sub     rdx, [rcx+8]
0x14000cb2a  sar     rdx, 5
0x14000cb2e  lea     rdx, ds:0FFFFFFFFFFFFFFFEh[rdx*2]
0x14000cb36  lea     rcx, [rsp+78h+Src]
0x14000cb3b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@_K_W@Z; std::wstring::wstring(unsigned __int64,wchar_t)
0x14000cb40  nop
0x14000cb41  mov     r8d, 2
0x14000cb47  lea     rdx, asc_140037994; "</"
0x14000cb4e  lea     rcx, [rsp+78h+Src]; Src
0x14000cb53  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x14000cb58  mov     rdx, [rdi+8]
0x14000cb5c  lea     rbx, [rdi+10h]
0x14000cb60  mov     rcx, [rbx]
0x14000cb63  sub     rcx, rdx
0x14000cb66  and     rcx, 0FFFFFFFFFFFFFFE0h
0x14000cb6a  add     rdx, 0FFFFFFFFFFFFFFE0h
0x14000cb6e  add     rdx, rcx
0x14000cb71  mov     r8, [rdx+10h]
0x14000cb75  cmp     qword ptr [rdx+18h], 7
0x14000cb7a  jbe     short loc_14000CB7F
0x14000cb7c  mov     rdx, [rdx]
0x14000cb7f  mov     rcx, rax; Src
0x14000cb82  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x14000cb87  mov     r8d, 3
0x14000cb8d  lea     rdx, asc_140037988; ">\r\n"
0x14000cb94  mov     rcx, rax; Src
0x14000cb97  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x14000cb9c  lea     rdx, [rsp+78h+var_48]
0x14000cba1  lea     rcx, [rsp+78h+Src]
0x14000cba6  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x14000cbab  movups  xmm0, xmmword ptr [rax]
0x14000cbae  movdqu  [rsp+78h+var_58], xmm0
0x14000cbb4  lea     rdx, [rsp+78h+var_58]
0x14000cbb9  mov     rcx, [rdi]; hFile
0x14000cbbc  call    ?FilePuts@@YAJPEAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; FilePuts(void *,std::wstring_view)
0x14000cbc1  nop
0x14000cbc2  lea     rcx, [rsp+78h+Src]
0x14000cbc7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000cbcc  jmp     short loc_14000CBD2
0x14000cbce  lea     rbx, [rcx+10h]
0x14000cbd2  mov     rcx, [rbx]
0x14000cbd5  sub     rcx, 20h ; ' '
0x14000cbd9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000cbde  add     qword ptr [rbx], 0FFFFFFFFFFFFFFE0h
0x14000cbe2  mov     rcx, [rsp+78h+var_18]
0x14000cbe7  xor     rcx, rsp; StackCookie
0x14000cbea  call    __security_check_cookie
0x14000cbef  mov     rbx, [rsp+78h+arg_8]
0x14000cbf7  add     rsp, 70h
0x14000cbfb  pop     rdi
0x14000cbfc  retn
```
