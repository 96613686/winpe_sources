# IsCoreChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)

- ea: `0x140019348`
- end: `0x1400193e9`
- name: `?IsCoreChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z`
- size: `161`
- prototype: ``
- caller_count: `14`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140006de0`
- `0x14000750c`
- `0x140013658`
- `0x140015b0c`
- `0x140019248`
- `0x14001b398`
- `0x14001d828`
- `0x1400201e8`
- `0x1400203a8`
- `0x14002ab70`
- `0x14002bd08`
- `0x14002ddb0`
- `0x14002e0cc`
- `0x14002efbc`

## callees

- `0x140008b40`
- `0x14000a670`
- `0x140019348`

## string_xrefs

- `0x1400193ab`: `Security`

## pseudocode

```c
char __fastcall IsCoreChannel(const wchar_t **a1)
{
  __int64 v1; // rbx
  const wchar_t *v2; // rdi
  char result; // al
  const wchar_t *v4; // [rsp+20h] [rbp-20h] BYREF
  __int64 v5; // [rsp+28h] [rbp-18h]
  const wchar_t *v6; // [rsp+30h] [rbp-10h] BYREF
  __int64 v7; // [rsp+38h] [rbp-8h]

  v1 = (__int64)a1[1];
  v2 = *a1;
  if ( v1 == 11
    && !(unsigned int)tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>::compare(*a1, L"Application", 11) )
  {
    return 1;
  }
  v5 = 6;
  v4 = L"System";
  v6 = v2;
  v7 = v1;
  if ( (unsigned __int8)utl::operator==<wchar_t,tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>>(&v6, &v4) )
    return 1;
  v7 = 8;
  v6 = L"Security";
  v4 = v2;
  v5 = v1;
  result = utl::operator==<wchar_t,tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>>(&v4, &v6);
  if ( result )
    return 1;
  return result;
}

```

## disassembly

```asm
0x140019348  mov     [rsp-8+arg_0], rbx
0x14001934d  mov     [rsp-8+arg_8], rdi
0x140019352  push    rbp
0x140019353  mov     rbp, rsp
0x140019356  sub     rsp, 40h
0x14001935a  mov     rbx, [rcx+8]
0x14001935e  mov     r8d, 0Bh
0x140019364  mov     rdi, [rcx]
0x140019367  cmp     rbx, r8
0x14001936a  jnz     short loc_14001937F
0x14001936c  lea     rdx, aApplication; "Application"
0x140019373  mov     rcx, rdi
0x140019376  call    ?compare@?$transform_traits@_WUascii_toupper_transform@tlx@@@tlx@@SAHPEB_W0_K@Z; tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>::compare(wchar_t const *,wchar_t const *,unsigned __int64)
0x14001937b  test    eax, eax
0x14001937d  jz      short loc_1400193D7
0x14001937f  lea     rax, aSystem; "System"
0x140019386  mov     [rbp+var_18], 6
0x14001938e  lea     rdx, [rbp+var_20]
0x140019392  mov     [rbp+var_20], rax
0x140019396  lea     rcx, [rbp+var_10]
0x14001939a  mov     [rbp+var_10], rdi
0x14001939e  mov     [rbp+var_8], rbx
0x1400193a2  call    ??$?8_WU?$transform_traits@_WUascii_toupper_transform@tlx@@@tlx@@@utl@@YA_NV?$basic_string_view@_WU?$transform_traits@_WUascii_toupper_transform@tlx@@@tlx@@@0@0@Z; utl::operator==<wchar_t,tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>>(utl::basic_string_view<wchar_t,tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>>,utl::basic_string_view<wchar_t,tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>>)
0x1400193a7  test    al, al
0x1400193a9  jnz     short loc_1400193D7
0x1400193ab  lea     rax, aSecurity; "Security"
0x1400193b2  mov     [rbp+var_8], 8
0x1400193ba  lea     rdx, [rbp+var_10]
0x1400193be  mov     [rbp+var_10], rax
0x1400193c2  lea     rcx, [rbp+var_20]
0x1400193c6  mov     [rbp+var_20], rdi
0x1400193ca  mov     [rbp+var_18], rbx
0x1400193ce  call    ??$?8_WU?$transform_traits@_WUascii_toupper_transform@tlx@@@tlx@@@utl@@YA_NV?$basic_string_view@_WU?$transform_traits@_WUascii_toupper_transform@tlx@@@tlx@@@0@0@Z; utl::operator==<wchar_t,tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>>(utl::basic_string_view<wchar_t,tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>>,utl::basic_string_view<wchar_t,tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>>)
0x1400193d3  test    al, al
0x1400193d5  jz      short loc_1400193D9
0x1400193d7  mov     al, 1
0x1400193d9  mov     rbx, [rsp+40h+arg_0]
0x1400193de  mov     rdi, [rsp+40h+arg_8]
0x1400193e3  add     rsp, 40h
0x1400193e7  pop     rbp
0x1400193e8  retn
```
