# EventManParser::ElementMatches(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)

- ea: `0x180035858`
- end: `0x1800358ec`
- name: `?ElementMatches@EventManParser@@AEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@00@Z`
- size: `148`
- prototype: `__int64 __fastcall(XmlReader *this)`
- caller_count: `26`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011b30`
- `0x18001d810`
- `0x18002c2fc`
- `0x18002c650`
- `0x18003479c`
- `0x180034cbc`
- `0x180035780`
- `0x180036020`
- `0x1800360b4`
- `0x180036d30`
- `0x1800380ec`
- `0x180038228`
- `0x180038498`
- `0x1800386fc`
- `0x18003889c`
- `0x180038a44`
- `0x180038c30`
- `0x180038d38`
- `0x180039780`
- `0x180039878`
- `0x180039cdc`
- `0x18003b29c`
- `0x18003b4dc`
- `0x18003b6f8`
- `0x18003b7e0`
- `0x18003bae4`

## callees

- `0x18001ed1c`
- `0x18001ee78`
- `0x180035858`
- `0x18004c010`

## string_xrefs

- `0x1800358b2`: `GetNamespaceUri`

## pseudocode

```c
bool __fastcall EventManParser::ElementMatches(XmlReader *this, _QWORD *a2, _QWORD *a3, _QWORD *a4)
{
  __int64 v6; // rcx
  int v7; // eax
  bool result; // al
  unsigned int v9; // [rsp+38h] [rbp+10h] BYREF
  __int64 v10; // [rsp+48h] [rbp+20h] BYREF

  result = 0;
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(*a2, a2[1], *a4, a4[1]) )
  {
    v6 = *(_QWORD *)this;
    v10 = 0;
    v9 = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, __int64 *, unsigned int *))(*(_QWORD *)v6 + 104LL))(v6, &v10, &v9);
    XmlReader::ThrowIfFailed(this, "GetNamespaceUri", v7);
    if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(*a3, a3[1], v10, v9) )
      return 1;
  }
  return result;
}

```

## disassembly

```asm
0x180035858  mov     [rsp+arg_0], rbx
0x18003585d  push    rdi
0x18003585e  sub     rsp, 20h
0x180035862  mov     rax, r9
0x180035865  mov     r10, rdx
0x180035868  mov     r9, [r9+8]
0x18003586c  mov     rbx, r8
0x18003586f  mov     rdx, [rdx+8]
0x180035873  mov     rdi, rcx
0x180035876  mov     r8, [rax]
0x180035879  mov     rcx, [r10]
0x18003587c  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x180035881  test    al, al
0x180035883  jz      short loc_1800358DF
0x180035885  mov     rcx, [rdi]
0x180035888  lea     r8, [rsp+28h+arg_8]
0x18003588d  mov     [rsp+28h+arg_18], 0
0x180035896  lea     rdx, [rsp+28h+arg_18]
0x18003589b  mov     [rsp+28h+arg_8], 0
0x1800358a3  mov     rax, [rcx]
0x1800358a6  mov     rax, [rax+68h]
0x1800358aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800358af  mov     r8d, eax; int
0x1800358b2  lea     rdx, aGetnamespaceur; "GetNamespaceUri"
0x1800358b9  mov     rcx, rdi; this
0x1800358bc  call    ?ThrowIfFailed@XmlReader@@AEBAXPEBDJ@Z; XmlReader::ThrowIfFailed(char const *,long)
0x1800358c1  mov     r9d, [rsp+28h+arg_8]
0x1800358c6  mov     r8, [rsp+28h+arg_18]
0x1800358cb  mov     rdx, [rbx+8]
0x1800358cf  mov     rcx, [rbx]
0x1800358d2  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1800358d7  test    al, al
0x1800358d9  jz      short loc_1800358DF
0x1800358db  mov     al, 1
0x1800358dd  jmp     short loc_1800358E1
0x1800358df  xor     al, al
0x1800358e1  mov     rbx, [rsp+28h+arg_0]
0x1800358e6  add     rsp, 20h
0x1800358ea  pop     rdi
0x1800358eb  retn
```
