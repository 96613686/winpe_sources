# UusPackage::GetUpdateInfo(void)

- ea: `0x18000af34`
- end: `0x18000b01c`
- name: `?GetUpdateInfo@UusPackage@@QEBA?AVUusPackageUpdateInfo@@XZ`
- size: `232`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x18000c510`
- `0x180036ab4`

## callees

- `0x180009f40`
- `0x180028728`
- `0x180029158`
- `0x1800295e8`
- `0x180029644`
- `0x1800296cc`
- `0x180042bfc`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
_QWORD *__fastcall UusPackage::GetUpdateInfo(__int64 a1, _QWORD *a2)
{
  __int64 *v3; // rax
  _QWORD *v4; // rax
  __int64 v5; // rdx
  struct std::error_code *v6; // r8
  _QWORD v8[6]; // [rsp+20h] [rbp-19h] BYREF
  _QWORD v9[4]; // [rsp+50h] [rbp+17h] BYREF
  _QWORD v10[4]; // [rsp+70h] [rbp+37h] BYREF

  v8[4] = a2;
  std::wstring::wstring((__int64)v10, a1 + 8);
  *a2 = &UusPackageUpdateInfo::`vftable';
  v3 = &UusPackageUpdateInfo::_filename;
  if ( (unsigned __int64)qword_1800637A8 > 7 )
    v3 = (__int64 *)UusPackageUpdateInfo::_filename;
  v8[0] = v3;
  v8[1] = qword_1800637A0;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v9, (__int64)v8);
  std::filesystem::operator/((std::filesystem *)(a2 + 1), v10, v9);
  std::wstring::_Tidy_deallocate((__int64)v9);
  a2[5] = 0;
  a2[6] = 0;
  v4 = operator new(0x60u);
  *v4 = v4;
  v4[1] = v4;
  v4[2] = v4;
  *((_WORD *)v4 + 12) = 257;
  a2[5] = v4;
  web::json::value::value((web::json::value *)(a2 + 7));
  UusPackageUpdateInfo::Load((UusPackageUpdateInfo *)a2, v5, v6);
  std::wstring::_Tidy_deallocate((__int64)v10);
  return a2;
}

```

## disassembly

```asm
0x18000af34  mov     [rsp-8+arg_10], rbx
0x18000af39  mov     [rsp-8+arg_18], rdi
0x18000af3e  push    rbp
0x18000af3f  lea     rbp, [rsp-57h]
0x18000af44  sub     rsp, 90h
0x18000af4b  mov     rdi, rdx
0x18000af4e  mov     [rbp+57h+var_50], rdx
0x18000af52  lea     rdx, [rcx+8]
0x18000af56  lea     rcx, [rbp+57h+var_20]
0x18000af5a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000af5f  nop
0x18000af60  lea     rax, ??_7UusPackageUpdateInfo@@6B@; const UusPackageUpdateInfo::`vftable'
0x18000af67  mov     [rdi], rax
0x18000af6a  mov     rcx, cs:qword_1800637A0
0x18000af71  lea     rax, ?_filename@UusPackageUpdateInfo@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusPackageUpdateInfo::_filename
0x18000af78  cmp     cs:qword_1800637A8, 7
0x18000af80  cmova   rax, cs:?_filename@UusPackageUpdateInfo@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusPackageUpdateInfo::_filename
0x18000af88  mov     [rbp+57h+var_70], rax
0x18000af8c  mov     [rbp+57h+var_68], rcx
0x18000af90  lea     rdx, [rbp+57h+var_70]
0x18000af94  lea     rcx, [rbp+57h+var_40]
0x18000af98  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x18000af9d  nop
0x18000af9e  lea     rcx, [rdi+8]; Src
0x18000afa2  lea     r8, [rbp+57h+var_40]; void *
0x18000afa6  lea     rdx, [rbp+57h+var_20]; void *
0x18000afaa  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x18000afaf  nop
0x18000afb0  lea     rcx, [rbp+57h+var_40]
0x18000afb4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000afb9  mov     qword ptr [rdi+28h], 0
0x18000afc1  mov     qword ptr [rdi+30h], 0
0x18000afc9  mov     ecx, 60h ; '`'; Size
0x18000afce  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000afd3  mov     [rax], rax
0x18000afd6  mov     [rax+8], rax
0x18000afda  mov     [rax+10h], rax
0x18000afde  mov     word ptr [rax+18h], 101h
0x18000afe4  mov     [rdi+28h], rax
0x18000afe8  lea     rcx, [rdi+38h]; this
0x18000afec  call    ??0value@json@web@@QEAA@XZ; web::json::value::value(void)
0x18000aff1  nop
0x18000aff2  mov     rcx, rdi; this
0x18000aff5  call    ?Load@UusPackageUpdateInfo@@QEAAXXZ; UusPackageUpdateInfo::Load(void)
0x18000affa  nop
0x18000affb  lea     rcx, [rbp+57h+var_20]
0x18000afff  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000b004  mov     rax, rdi
0x18000b007  lea     r11, [rsp+90h+var_s0]
0x18000b00f  mov     rbx, [r11+20h]
0x18000b013  mov     rdi, [r11+28h]
0x18000b017  mov     rsp, r11
0x18000b01a  pop     rbp
0x18000b01b  retn
```
