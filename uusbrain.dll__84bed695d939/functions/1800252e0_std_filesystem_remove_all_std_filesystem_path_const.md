# std::filesystem::remove_all(std::filesystem::path const &)

- ea: `0x1800252e0`
- end: `0x180025370`
- name: `?remove_all@filesystem@std@@YA_KAEBVpath@12@@Z`
- size: `144`
- prototype: `__int64 __fastcall(std::filesystem *this, const struct std::filesystem::path *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18000c510`
- `0x18000cdfc`
- `0x18000cf18`

## callees

- `0x1800250d0`
- `0x1800252e0`
- `0x1800286d0`
- `0x180040158`

## string_xrefs

- `0x180025363`: `remove_all`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall std::filesystem::remove_all(std::filesystem *this, const struct std::filesystem::path *a2)
{
  std::filesystem *v2; // rbx
  __int64 v3; // rax
  unsigned __int64 *v4; // r9
  __int64 v5; // rcx
  char v7[16]; // [rsp+20h] [rbp-28h] BYREF
  _QWORD v8[3]; // [rsp+30h] [rbp-18h] BYREF

  v2 = this;
  if ( *((_QWORD *)this + 3) > 7u )
    this = *(std::filesystem **)this;
  v3 = _std_fs_remove(this);
  v5 = (unsigned __int8)v3;
  *(_DWORD *)v7 = HIDWORD(v3);
  *(_QWORD *)&v7[8] = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  v8[0] = (unsigned __int8)v3;
  if ( HIDWORD(v3) == 145 )
  {
    std::filesystem::_Remove_all_dir(v2, (const struct std::filesystem::path *)v7, (struct std::error_code *)v8, v4);
    v5 = v8[0];
  }
  if ( *(_DWORD *)v7 )
    std::filesystem::_Throw_fs_error((std::filesystem *)"remove_all", v7, v2, (const struct std::filesystem::path *)v4);
  return v5;
}

```

## disassembly

```asm
0x1800252e0  push    rbx
0x1800252e2  sub     rsp, 40h
0x1800252e6  cmp     qword ptr [rcx+18h], 7
0x1800252eb  mov     rbx, rcx
0x1800252ee  jbe     short loc_1800252F3
0x1800252f0  mov     rcx, [rcx]
0x1800252f3  call    __std_fs_remove
0x1800252f8  movzx   ecx, al
0x1800252fb  lea     rdx, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4U?$_Constexpr_immortalize_impl@V_System_error_category@std@@@1@A; std::_Constexpr_immortalize_impl<std::_System_error_category> `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x180025302  shr     rax, 20h
0x180025306  mov     dword ptr [rsp+48h+var_28], eax
0x18002530a  mov     qword ptr [rsp+48h+var_28+8], rdx
0x18002530f  movaps  xmm0, xmmword ptr [rsp+48h+var_28]
0x180025314  movdqa  xmmword ptr [rsp+48h+var_28], xmm0
0x18002531a  mov     [rsp+48h+var_18], rcx
0x18002531f  cmp     eax, 91h
0x180025324  jnz     short loc_18002533D
0x180025326  lea     r8, [rsp+48h+var_18]; struct std::error_code *
0x18002532b  mov     rcx, rbx; this
0x18002532e  lea     rdx, [rsp+48h+var_28]; struct std::filesystem::path *
0x180025333  call    ?_Remove_all_dir@filesystem@std@@YAXAEBVpath@12@AEAVerror_code@2@AEA_K@Z; std::filesystem::_Remove_all_dir(std::filesystem::path const &,std::error_code &,unsigned __int64 &)
0x180025338  mov     rcx, [rsp+48h+var_18]
0x18002533d  mov     eax, dword ptr [rsp+48h+var_28]
0x180025341  test    eax, eax
0x180025343  setnz   dl
0x180025346  test    eax, eax
0x180025348  jz      short loc_18002534E
0x18002534a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002534e  test    dl, dl
0x180025350  jnz     short loc_18002535B
0x180025352  mov     rax, rcx
0x180025355  add     rsp, 40h
0x180025359  pop     rbx
0x18002535a  retn
0x18002535b  mov     r8, rbx; struct std::error_code *
0x18002535e  lea     rdx, [rsp+48h+var_28]; char *
0x180025363  lea     rcx, aRemoveAll; "remove_all"
0x18002536a  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDAEBVerror_code@2@AEBVpath@12@@Z; std::filesystem::_Throw_fs_error(char const *,std::error_code const &,std::filesystem::path const &)
```
