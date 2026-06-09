# uus::Utility::FindFileInSubFolder(std::filesystem::path const &,wchar_t const *)

- ea: `0x180006d98`
- end: `0x180006f07`
- name: `?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@PEB_W@Z`
- size: `367`
- prototype: `std::filesystem::path *__fastcall(std::filesystem::path *this, struct std::filesystem::path *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180006cd0`
- `0x180006f90`

## callees

- `0x1800061a4`
- `0x180006358`
- `0x180006948`
- `0x180006d98`
- `0x1800085e8`
- `0x180008868`
- `0x18000f35c`
- `0x18000fce0`

## string_xrefs

- `0x180006de4`: `uusbrain.dll`

## pseudocode

```c
std::filesystem::path *__fastcall uus::Utility::FindFileInSubFolder(
        std::filesystem::path *this,
        struct std::filesystem::path *a2)
{
  const WCHAR *v4; // rcx
  unsigned int stats; // eax
  const struct std::filesystem::path *v6; // r9
  std::filesystem *v7; // rcx
  int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  char v15[16]; // [rsp+20h] [rbp-19h] BYREF
  __int128 v16; // [rsp+30h] [rbp-9h]
  __int128 v17; // [rsp+48h] [rbp+Fh] BYREF
  __int64 v18; // [rsp+58h] [rbp+1Fh]
  __int64 v19; // [rsp+60h] [rbp+27h]
  LPCWSTR lpFileName[4]; // [rsp+68h] [rbp+2Fh] BYREF

  v17 = 0;
  v18 = 0;
  v19 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v17, L"uusbrain.dll", 12);
  std::filesystem::operator/(lpFileName, a2, &v17);
  std::wstring::~wstring(&v17);
  *(_OWORD *)v15 = 0;
  v16 = 0;
  v4 = (const WCHAR *)lpFileName;
  if ( lpFileName[3] > (LPCWSTR)7 )
    v4 = lpFileName[0];
  stats = _std_fs_get_stats(v4);
  v7 = (std::filesystem *)stats;
  if ( stats )
  {
    v9 = stats - 2;
    v8 = 1;
    if ( v9 )
    {
      v10 = v9 - 1;
      if ( v10 )
      {
        v11 = v10 - 50;
        if ( v11 )
        {
          v12 = v11 - 11;
          if ( v12 )
          {
            v13 = v12 - 59;
            if ( v13 )
            {
              if ( v13 != 144 )
                v8 = 0;
            }
          }
        }
      }
    }
  }
  else
  {
    if ( (v16 & 0x400) == 0 )
      goto LABEL_9;
    if ( DWORD1(v16) == -1610612724 )
    {
      v8 = stats + 4;
      goto LABEL_18;
    }
    if ( DWORD1(v16) == -1610612733 )
      v8 = 10;
    else
LABEL_9:
      v8 = (unsigned __int128)(v16 & 0x10 | 0x20) >> 4;
  }
LABEL_18:
  *(_DWORD *)v15 = (_DWORD)v7;
  *(_QWORD *)&v15[8] = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  if ( v8 )
  {
    if ( v8 != 1 )
    {
      std::filesystem::path::path(this, (const struct std::filesystem::path *)lpFileName);
      *((_BYTE *)this + 32) = 1;
      goto LABEL_21;
    }
  }
  else if ( (_DWORD)v7 )
  {
    std::filesystem::_Throw_fs_error(v7, v15, (const struct std::error_code *)lpFileName, v6);
  }
  *((_BYTE *)this + 32) = 0;
LABEL_21:
  std::wstring::~wstring(lpFileName);
  return this;
}

```

## disassembly

```asm
0x180006d98  mov     [rsp-8+arg_10], rbx
0x180006d9d  mov     [rsp-8+arg_18], rdi
0x180006da2  push    rbp
0x180006da3  lea     rbp, [rsp-57h]
0x180006da8  sub     rsp, 90h
0x180006daf  mov     rax, cs:__security_cookie
0x180006db6  xor     rax, rsp
0x180006db9  mov     [rbp+57h+var_8], rax
0x180006dbd  mov     rbx, rdx
0x180006dc0  mov     rdi, rcx
0x180006dc3  mov     qword ptr [rbp+57h+var_70], rcx
0x180006dc7  xorps   xmm0, xmm0
0x180006dca  movups  [rbp+57h+var_48], xmm0
0x180006dce  mov     [rbp+57h+var_38], 0
0x180006dd6  mov     [rbp+57h+var_30], 0
0x180006dde  mov     r8d, 0Ch
0x180006de4  lea     rdx, aUusbrainDll; "uusbrain.dll"
0x180006deb  lea     rcx, [rbp+57h+var_48]
0x180006def  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180006df4  nop
0x180006df5  lea     r8, [rbp+57h+var_48]; void *
0x180006df9  mov     rdx, rbx; struct std::filesystem::path *
0x180006dfc  lea     rcx, [rbp+57h+lpFileName]; Src
0x180006e00  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x180006e05  nop
0x180006e06  lea     rcx, [rbp+57h+var_48]
0x180006e0a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180006e0f  xorps   xmm0, xmm0
0x180006e12  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x180006e16  movups  [rbp+57h+var_60], xmm0
0x180006e1a  lea     rcx, [rbp+57h+lpFileName]
0x180006e1e  cmp     [rbp+57h+var_10], 7
0x180006e23  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x180006e28  lea     rdx, [rbp+57h+var_70]
0x180006e2c  call    __std_fs_get_stats
0x180006e31  mov     ecx, eax; this
0x180006e33  test    eax, eax
0x180006e35  jnz     short loc_180006E69
0x180006e37  mov     eax, dword ptr [rbp+57h+var_60]
0x180006e3a  bt      eax, 0Ah
0x180006e3e  jnb     short loc_180006E5E
0x180006e40  cmp     dword ptr [rbp+57h+var_60+4], 0A000000Ch
0x180006e47  jnz     short loc_180006E4E
0x180006e49  lea     eax, [rcx+4]
0x180006e4c  jmp     short loc_180006E92
0x180006e4e  cmp     dword ptr [rbp+57h+var_60+4], 0A0000003h
0x180006e55  jnz     short loc_180006E5E
0x180006e57  mov     eax, 0Ah
0x180006e5c  jmp     short loc_180006E92
0x180006e5e  and     eax, 10h
0x180006e61  or      eax, 20h
0x180006e64  shr     eax, 4
0x180006e67  jmp     short loc_180006E92
0x180006e69  sub     eax, 2
0x180006e6c  jz      short loc_180006E8D
0x180006e6e  sub     eax, 1
0x180006e71  jz      short loc_180006E8D
0x180006e73  sub     eax, 32h ; '2'
0x180006e76  jz      short loc_180006E8D
0x180006e78  sub     eax, 0Bh
0x180006e7b  jz      short loc_180006E8D
0x180006e7d  sub     eax, 3Bh ; ';'
0x180006e80  jz      short loc_180006E8D
0x180006e82  cmp     eax, 90h
0x180006e87  jz      short loc_180006E8D
0x180006e89  xor     eax, eax
0x180006e8b  jmp     short loc_180006E92
0x180006e8d  mov     eax, 1
0x180006e92  mov     dword ptr [rbp+57h+var_70], ecx
0x180006e95  lea     rdx, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4U?$_Constexpr_immortalize_impl@V_System_error_category@std@@@1@A; std::_Constexpr_immortalize_impl<std::_System_error_category> `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x180006e9c  mov     qword ptr [rbp+57h+var_70+8], rdx
0x180006ea0  movaps  xmm0, xmmword ptr [rbp+57h+var_70]
0x180006ea4  movdqa  xmmword ptr [rbp+57h+var_70], xmm0
0x180006ea9  test    eax, eax
0x180006eab  jnz     short loc_180006EE2
0x180006ead  test    ecx, ecx
0x180006eaf  jnz     short loc_180006EF9
0x180006eb1  mov     byte ptr [rdi+20h], 0
0x180006eb5  lea     rcx, [rbp+57h+lpFileName]
0x180006eb9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180006ebe  mov     rax, rdi
0x180006ec1  mov     rcx, [rbp+57h+var_8]
0x180006ec5  xor     rcx, rsp; StackCookie
0x180006ec8  call    __security_check_cookie
0x180006ecd  lea     r11, [rsp+90h+var_s0]
0x180006ed5  mov     rbx, [r11+20h]
0x180006ed9  mov     rdi, [r11+28h]
0x180006edd  mov     rsp, r11
0x180006ee0  pop     rbp
0x180006ee1  retn
0x180006ee2  cmp     eax, 1
0x180006ee5  jz      short loc_180006EB1
0x180006ee7  lea     rdx, [rbp+57h+lpFileName]; struct std::filesystem::path *
0x180006eeb  mov     rcx, rdi; this
0x180006eee  call    ??0path@filesystem@std@@QEAA@AEBV012@@Z; std::filesystem::path::path(std::filesystem::path const &)
0x180006ef3  mov     byte ptr [rdi+20h], 1
0x180006ef7  jmp     short loc_180006EB5
0x180006ef9  lea     r8, [rbp+57h+lpFileName]; struct std::error_code *
0x180006efd  lea     rdx, [rbp+57h+var_70]; char *
0x180006f01  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDAEBVerror_code@2@AEBVpath@12@@Z; std::filesystem::_Throw_fs_error(char const *,std::error_code const &,std::filesystem::path const &)
```
