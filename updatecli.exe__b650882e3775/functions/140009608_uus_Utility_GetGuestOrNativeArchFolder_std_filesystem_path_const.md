# uus::Utility::GetGuestOrNativeArchFolder(std::filesystem::path const &)

- ea: `0x140009608`
- end: `0x140009695`
- name: `?GetGuestOrNativeArchFolder@Utility@uus@@SA?AVpath@filesystem@std@@AEBV345@@Z`
- size: `141`
- prototype: `void *__fastcall(void *, struct std::filesystem::path *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1400091e4`
- `0x14000a6a8`

## callees

- `0x140002130`
- `0x140007168`
- `0x1400087c4`
- `0x140008a34`
- `0x140009608`

## pseudocode

```c
void *__fastcall uus::Utility::GetGuestOrNativeArchFolder(void *a1, struct std::filesystem::path *a2)
{
  __int64 v4; // rcx
  _BYTE v6[32]; // [rsp+38h] [rbp-30h] BYREF

  v4 = -1;
  do
    ++v4;
  while ( uus::Const::archX64[v4] );
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v6);
  std::filesystem::operator/(a1, a2, (std::filesystem *)v6);
  std::wstring::~wstring(v6);
  return a1;
}

```

## disassembly

```asm
0x140009608  mov     [rsp+arg_10], rbx
0x14000960d  push    rdi
0x14000960e  sub     rsp, 60h
0x140009612  mov     rax, cs:__security_cookie
0x140009619  xor     rax, rsp
0x14000961c  mov     [rsp+68h+var_10], rax
0x140009621  mov     rdi, rdx
0x140009624  mov     rbx, rcx
0x140009627  mov     [rsp+68h+var_48], rcx
0x14000962c  xor     edx, edx
0x14000962e  mov     rax, cs:?archX64@Const@uus@@2PEBGEB; ushort const * const uus::Const::archX64
0x140009635  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140009639  inc     rcx
0x14000963c  cmp     [rax+rcx*2], dx
0x140009640  jnz     short loc_140009639
0x140009642  mov     [rsp+68h+var_48], rax
0x140009647  mov     [rsp+68h+var_40], rcx
0x14000964c  lea     rdx, [rsp+68h+var_48]
0x140009651  lea     rcx, [rsp+68h+var_30]; void *
0x140009656  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort>,std::filesystem::_Normal_conversion)
0x14000965b  nop
0x14000965c  lea     r8, [rsp+68h+var_30]; this
0x140009661  mov     rdx, rdi; struct std::filesystem::path *
0x140009664  mov     rcx, rbx; Src
0x140009667  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x14000966c  nop
0x14000966d  lea     rcx, [rsp+68h+var_30]
0x140009672  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140009677  mov     rax, rbx
0x14000967a  mov     rcx, [rsp+68h+var_10]
0x14000967f  xor     rcx, rsp; StackCookie
0x140009682  call    __security_check_cookie
0x140009687  mov     rbx, [rsp+68h+arg_10]
0x14000968f  add     rsp, 60h
0x140009693  pop     rdi
0x140009694  retn
```
