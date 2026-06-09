# uus::Utility::GetGuestOrNativeArchFolder(std::filesystem::path const &)

- ea: `0x1400095d8`
- end: `0x140009665`
- name: `?GetGuestOrNativeArchFolder@Utility@uus@@SA?AVpath@filesystem@std@@AEBV345@@Z`
- size: `141`
- prototype: `std::filesystem::path *__fastcall(std::filesystem::path *, struct std::filesystem::path *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1400091b4`
- `0x14000a678`

## callees

- `0x140002120`
- `0x140007188`
- `0x1400087e4`
- `0x140008a04`
- `0x1400095d8`

## pseudocode

```c
std::filesystem::path *__fastcall uus::Utility::GetGuestOrNativeArchFolder(
        std::filesystem::path *a1,
        struct std::filesystem::path *a2)
{
  __int64 v4; // rcx
  _QWORD v6[3]; // [rsp+20h] [rbp-48h] BYREF
  char *v7[4]; // [rsp+38h] [rbp-30h] BYREF

  v6[0] = a1;
  v4 = -1;
  do
    ++v4;
  while ( uus::Const::archX64[v4] );
  v6[0] = uus::Const::archX64;
  v6[1] = v4;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v7, (__int64)v6);
  std::filesystem::operator/(a1, a2, (std::filesystem *)v7);
  std::wstring::~wstring(v7);
  return a1;
}

```

## disassembly

```asm
0x1400095d8  mov     [rsp+arg_10], rbx
0x1400095dd  push    rdi
0x1400095de  sub     rsp, 60h
0x1400095e2  mov     rax, cs:__security_cookie
0x1400095e9  xor     rax, rsp
0x1400095ec  mov     [rsp+68h+var_10], rax
0x1400095f1  mov     rdi, rdx
0x1400095f4  mov     rbx, rcx
0x1400095f7  mov     [rsp+68h+var_48], rcx
0x1400095fc  xor     edx, edx
0x1400095fe  mov     rax, cs:?archX64@Const@uus@@2PEBGEB; ushort const * const uus::Const::archX64
0x140009605  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140009609  inc     rcx
0x14000960c  cmp     [rax+rcx*2], dx
0x140009610  jnz     short loc_140009609
0x140009612  mov     [rsp+68h+var_48], rax
0x140009617  mov     [rsp+68h+var_40], rcx
0x14000961c  lea     rdx, [rsp+68h+var_48]
0x140009621  lea     rcx, [rsp+68h+var_30]; void *
0x140009626  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort>,std::filesystem::_Normal_conversion)
0x14000962b  nop
0x14000962c  lea     r8, [rsp+68h+var_30]; this
0x140009631  mov     rdx, rdi; struct std::filesystem::path *
0x140009634  mov     rcx, rbx; Src
0x140009637  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x14000963c  nop
0x14000963d  lea     rcx, [rsp+68h+var_30]
0x140009642  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140009647  mov     rax, rbx
0x14000964a  mov     rcx, [rsp+68h+var_10]
0x14000964f  xor     rcx, rsp; StackCookie
0x140009652  call    __security_check_cookie
0x140009657  mov     rbx, [rsp+68h+arg_10]
0x14000965f  add     rsp, 60h
0x140009663  pop     rdi
0x140009664  retn
```
