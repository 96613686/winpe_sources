# uus::Utility::FindFileInSubFolder(std::filesystem::path const &,ushort const *)

- ea: `0x180009540`
- end: `0x1800095f8`
- name: `?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@PEBG@Z`
- size: `184`
- prototype: `std::filesystem::path *__fastcall(std::filesystem::path *this, struct std::filesystem::path *)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180009364`
- `0x18000946c`

## callees

- `0x1800026d0`
- `0x1800074ac`
- `0x1800087e8`
- `0x180008b08`
- `0x180008c74`
- `0x180009540`
- `0x18000a498`

## string_xrefs

- `0x18000956d`: `uusbrain.dll`

## pseudocode

```c
std::filesystem::path *__fastcall uus::Utility::FindFileInSubFolder(
        std::filesystem::path *this,
        struct std::filesystem::path *a2)
{
  const struct std::filesystem::path *v4; // rdx
  _BYTE Src[32]; // [rsp+38h] [rbp-48h] BYREF
  _BYTE v7[32]; // [rsp+58h] [rbp-28h] BYREF

  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v7);
  std::filesystem::operator/(Src, a2, (std::filesystem *)v7);
  std::wstring::~wstring(v7);
  if ( std::filesystem::exists((std::filesystem *)Src, v4) )
  {
    std::filesystem::path::path(this, (const struct std::filesystem::path *)Src);
    *((_BYTE *)this + 32) = 1;
  }
  else
  {
    *((_BYTE *)this + 32) = 0;
  }
  std::wstring::~wstring(Src);
  return this;
}

```

## disassembly

```asm
0x180009540  mov     [rsp-8+arg_10], rbx
0x180009545  mov     [rsp-8+arg_18], rdi
0x18000954a  push    rbp
0x18000954b  mov     rbp, rsp
0x18000954e  sub     rsp, 80h
0x180009555  mov     rax, cs:__security_cookie
0x18000955c  xor     rax, rsp
0x18000955f  mov     [rbp+var_8], rax
0x180009563  mov     rbx, rdx
0x180009566  mov     rdi, rcx
0x180009569  mov     [rbp+var_60], rcx
0x18000956d  lea     rax, aUusbrainDll; "uusbrain.dll"
0x180009574  mov     [rbp+var_60], rax
0x180009578  mov     [rbp+var_58], 0Ch
0x180009580  lea     rdx, [rbp+var_60]
0x180009584  lea     rcx, [rbp+var_28]; void *
0x180009588  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort>,std::filesystem::_Normal_conversion)
0x18000958d  nop
0x18000958e  lea     r8, [rbp+var_28]; this
0x180009592  mov     rdx, rbx; struct std::filesystem::path *
0x180009595  lea     rcx, [rbp+Src]; Src
0x180009599  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x18000959e  nop
0x18000959f  lea     rcx, [rbp+var_28]
0x1800095a3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800095a8  lea     rcx, [rbp+Src]; this
0x1800095ac  call    ?exists@filesystem@std@@YA_NAEBVpath@12@@Z; std::filesystem::exists(std::filesystem::path const &)
0x1800095b1  test    al, al
0x1800095b3  jz      short loc_1800095C7
0x1800095b5  lea     rdx, [rbp+Src]; struct std::filesystem::path *
0x1800095b9  mov     rcx, rdi; this
0x1800095bc  call    ??0path@filesystem@std@@QEAA@AEBV012@@Z; std::filesystem::path::path(std::filesystem::path const &)
0x1800095c1  mov     byte ptr [rdi+20h], 1
0x1800095c5  jmp     short loc_1800095CB
0x1800095c7  mov     byte ptr [rdi+20h], 0
0x1800095cb  lea     rcx, [rbp+Src]
0x1800095cf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800095d4  mov     rax, rdi
0x1800095d7  mov     rcx, [rbp+var_8]
0x1800095db  xor     rcx, rsp; StackCookie
0x1800095de  call    __security_check_cookie
0x1800095e3  lea     r11, [rsp+80h+var_s0]
0x1800095eb  mov     rbx, [r11+20h]
0x1800095ef  mov     rdi, [r11+28h]
0x1800095f3  mov     rsp, r11
0x1800095f6  pop     rbp
0x1800095f7  retn
```
