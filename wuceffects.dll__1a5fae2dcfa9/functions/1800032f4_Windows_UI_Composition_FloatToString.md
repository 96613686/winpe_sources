# Windows::UI::Composition::FloatToString

- ea: `0x1800032f4`
- end: `0x18000341f`
- name: `Windows::UI::Composition::FloatToString`
- size: `299`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000303c`

## callees

- `0x1800032f4`
- `0x180003470`
- `0x180004db8`
- `0x18001de54`
- `0x180021060`
- `0x180021650`
- `0x1800216b8`
- `0x180021d70`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x1800033e4`
- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x1800033e4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::UI::Composition::FloatToString(__int64 a1, float a2)
{
  int v3; // eax
  __int64 v5; // rcx
  char v6[32]; // [rsp+40h] [rbp-68h] BYREF
  char Buffer[32]; // [rsp+60h] [rbp-48h] BYREF

  if ( dword_180042DB0 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180042DB0);
    if ( dword_180042DB0 == -1 )
    {
      Locale = _create_locale(4, "C");
      Init_thread_footer(&dword_180042DB0);
    }
  }
  v3 = sprintf_s_l(Buffer, 0x20u, "%f", Locale, a2);
  if ( v3 <= 0 )
  {
    std::wstring::wstring(v6, L"Invalid float value");
    Windows::UI::Composition::OriginateException(v5, v6);
  }
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  std::string::_Construct<1,char const *>(a1, Buffer, v3);
  return a1;
}

```

## disassembly

```asm
0x1800032f4  mov     rax, rsp
0x1800032f7  push    rbx
0x1800032f8  sub     rsp, 0A0h
0x1800032ff  movaps  xmmword ptr [rax-18h], xmm6
0x180003303  mov     rax, cs:__security_cookie
0x18000330a  xor     rax, rsp
0x18000330d  mov     [rsp+0A8h+var_28], rax
0x180003315  movaps  xmm6, xmm1
0x180003318  mov     rbx, rcx
0x18000331b  mov     [rsp+0A8h+var_70], rcx
0x180003320  mov     ecx, cs:_tls_index
0x180003326  mov     rax, gs:58h
0x18000332f  mov     edx, 4
0x180003334  mov     rax, [rax+rcx*8]
0x180003338  mov     ecx, [rdx+rax]
0x18000333b  cmp     cs:dword_180042DB0, ecx
0x180003341  jg      short loc_1800033BF
0x180003343  xorps   xmm0, xmm0
0x180003346  cvtss2sd xmm0, xmm6
0x18000334a  movsd   [rsp+0A8h+var_88], xmm0
0x180003350  mov     r9, cs:Locale; Locale
0x180003357  lea     r8, Format; "%f"
0x18000335e  mov     edx, 20h ; ' '; BufferCount
0x180003363  lea     rcx, [rsp+0A8h+Buffer]; Buffer
0x180003368  call    _sprintf_s_l
0x18000336d  test    eax, eax
0x18000336f  jle     loc_180003402
0x180003375  xorps   xmm0, xmm0
0x180003378  movups  xmmword ptr [rbx], xmm0
0x18000337b  mov     qword ptr [rbx+10h], 0
0x180003383  mov     qword ptr [rbx+18h], 0
0x18000338b  movsxd  r8, eax
0x18000338e  lea     rdx, [rsp+0A8h+Buffer]
0x180003393  mov     rcx, rbx
0x180003396  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18000339b  mov     rax, rbx
0x18000339e  mov     rcx, [rsp+0A8h+var_28]
0x1800033a6  xor     rcx, rsp; StackCookie
0x1800033a9  call    __security_check_cookie
0x1800033ae  movaps  xmm6, [rsp+0A8h+var_18]
0x1800033b6  add     rsp, 0A0h
0x1800033bd  pop     rbx
0x1800033be  retn
0x1800033bf  lea     rcx, dword_180042DB0
0x1800033c6  call    _Init_thread_header
0x1800033cb  cmp     cs:dword_180042DB0, 0FFFFFFFFh
0x1800033d2  jnz     loc_180003343
0x1800033d8  lea     rdx, aC; "C"
0x1800033df  mov     ecx, 4; Category
0x1800033e4  call    cs:__imp__create_locale
0x1800033ea  mov     cs:Locale, rax
0x1800033f1  lea     rcx, dword_180042DB0
0x1800033f8  call    _Init_thread_footer
0x1800033fd  jmp     loc_180003343
0x180003402  lea     rdx, aInvalidFloatVa; "Invalid float value"
0x180003409  lea     rcx, [rsp+0A8h+var_68]
0x18000340e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003413  nop
0x180003414  lea     rdx, [rsp+0A8h+var_68]
0x180003419  call    ?OriginateException@Composition@UI@Windows@@YAXJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::UI::Composition::OriginateException(long,std::wstring const &)
```
