# uus::Utility::GetGuestOrNativeArchFolder(std::filesystem::path const &)

- ea: `0x1800097fc`
- end: `0x180009889`
- name: `?GetGuestOrNativeArchFolder@Utility@uus@@SA?AVpath@filesystem@std@@AEBV345@@Z`
- size: `141`
- prototype: `void *__fastcall(void *, struct std::filesystem::path *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180009364`
- `0x1800096cc`

## callees

- `0x1800026d0`
- `0x1800074ac`
- `0x180008b08`
- `0x180008c74`
- `0x1800097fc`

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
0x1800097fc  mov     [rsp+arg_10], rbx
0x180009801  push    rdi
0x180009802  sub     rsp, 60h
0x180009806  mov     rax, cs:__security_cookie
0x18000980d  xor     rax, rsp
0x180009810  mov     [rsp+68h+var_10], rax
0x180009815  mov     rdi, rdx
0x180009818  mov     rbx, rcx
0x18000981b  mov     [rsp+68h+var_48], rcx
0x180009820  xor     edx, edx
0x180009822  mov     rax, cs:?archX64@Const@uus@@2PEBGEB; ushort const * const uus::Const::archX64
0x180009829  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000982d  inc     rcx
0x180009830  cmp     [rax+rcx*2], dx
0x180009834  jnz     short loc_18000982D
0x180009836  mov     [rsp+68h+var_48], rax
0x18000983b  mov     [rsp+68h+var_40], rcx
0x180009840  lea     rdx, [rsp+68h+var_48]
0x180009845  lea     rcx, [rsp+68h+var_30]; void *
0x18000984a  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort>,std::filesystem::_Normal_conversion)
0x18000984f  nop
0x180009850  lea     r8, [rsp+68h+var_30]; this
0x180009855  mov     rdx, rdi; struct std::filesystem::path *
0x180009858  mov     rcx, rbx; Src
0x18000985b  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x180009860  nop
0x180009861  lea     rcx, [rsp+68h+var_30]
0x180009866  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000986b  mov     rax, rbx
0x18000986e  mov     rcx, [rsp+68h+var_10]
0x180009873  xor     rcx, rsp; StackCookie
0x180009876  call    __security_check_cookie
0x18000987b  mov     rbx, [rsp+68h+arg_10]
0x180009883  add     rsp, 60h
0x180009887  pop     rdi
0x180009888  retn
```
