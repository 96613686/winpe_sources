# uus::Utility::FindFileInSubFolder(std::filesystem::path const &,wchar_t const *)

- ea: `0x180008148`
- end: `0x1800082b7`
- name: `?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@PEB_W@Z`
- size: `367`
- prototype: `std::filesystem::path *__fastcall(std::filesystem::path *this, struct std::filesystem::path *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1800082c0`
- `0x180008848`

## callees

- `0x1800080ec`
- `0x180008148`
- `0x1800090a0`
- `0x1800098b8`
- `0x18000a620`
- `0x18000a98c`
- `0x18000f30c`
- `0x18000fc90`

## string_xrefs

- `0x180008194`: `uusbrain.dll`

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
0x180008148  mov     [rsp-8+arg_10], rbx
0x18000814d  mov     [rsp-8+arg_18], rdi
0x180008152  push    rbp
0x180008153  lea     rbp, [rsp-57h]
0x180008158  sub     rsp, 90h
0x18000815f  mov     rax, cs:__security_cookie
0x180008166  xor     rax, rsp
0x180008169  mov     [rbp+57h+var_8], rax
0x18000816d  mov     rbx, rdx
0x180008170  mov     rdi, rcx
0x180008173  mov     qword ptr [rbp+57h+var_70], rcx
0x180008177  xorps   xmm0, xmm0
0x18000817a  movups  [rbp+57h+var_48], xmm0
0x18000817e  mov     [rbp+57h+var_38], 0
0x180008186  mov     [rbp+57h+var_30], 0
0x18000818e  mov     r8d, 0Ch
0x180008194  lea     rdx, aUusbrainDll; "uusbrain.dll"
0x18000819b  lea     rcx, [rbp+57h+var_48]
0x18000819f  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800081a4  nop
0x1800081a5  lea     r8, [rbp+57h+var_48]; void *
0x1800081a9  mov     rdx, rbx; struct std::filesystem::path *
0x1800081ac  lea     rcx, [rbp+57h+lpFileName]; Src
0x1800081b0  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x1800081b5  nop
0x1800081b6  lea     rcx, [rbp+57h+var_48]
0x1800081ba  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800081bf  xorps   xmm0, xmm0
0x1800081c2  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x1800081c6  movups  [rbp+57h+var_60], xmm0
0x1800081ca  lea     rcx, [rbp+57h+lpFileName]
0x1800081ce  cmp     [rbp+57h+var_10], 7
0x1800081d3  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x1800081d8  lea     rdx, [rbp+57h+var_70]
0x1800081dc  call    __std_fs_get_stats
0x1800081e1  mov     ecx, eax; this
0x1800081e3  test    eax, eax
0x1800081e5  jnz     short loc_180008219
0x1800081e7  mov     eax, dword ptr [rbp+57h+var_60]
0x1800081ea  bt      eax, 0Ah
0x1800081ee  jnb     short loc_18000820E
0x1800081f0  cmp     dword ptr [rbp+57h+var_60+4], 0A000000Ch
0x1800081f7  jnz     short loc_1800081FE
0x1800081f9  lea     eax, [rcx+4]
0x1800081fc  jmp     short loc_180008242
0x1800081fe  cmp     dword ptr [rbp+57h+var_60+4], 0A0000003h
0x180008205  jnz     short loc_18000820E
0x180008207  mov     eax, 0Ah
0x18000820c  jmp     short loc_180008242
0x18000820e  and     eax, 10h
0x180008211  or      eax, 20h
0x180008214  shr     eax, 4
0x180008217  jmp     short loc_180008242
0x180008219  sub     eax, 2
0x18000821c  jz      short loc_18000823D
0x18000821e  sub     eax, 1
0x180008221  jz      short loc_18000823D
0x180008223  sub     eax, 32h ; '2'
0x180008226  jz      short loc_18000823D
0x180008228  sub     eax, 0Bh
0x18000822b  jz      short loc_18000823D
0x18000822d  sub     eax, 3Bh ; ';'
0x180008230  jz      short loc_18000823D
0x180008232  cmp     eax, 90h
0x180008237  jz      short loc_18000823D
0x180008239  xor     eax, eax
0x18000823b  jmp     short loc_180008242
0x18000823d  mov     eax, 1
0x180008242  mov     dword ptr [rbp+57h+var_70], ecx
0x180008245  lea     rdx, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4U?$_Constexpr_immortalize_impl@V_System_error_category@std@@@1@A; std::_Constexpr_immortalize_impl<std::_System_error_category> `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x18000824c  mov     qword ptr [rbp+57h+var_70+8], rdx
0x180008250  movaps  xmm0, xmmword ptr [rbp+57h+var_70]
0x180008254  movdqa  xmmword ptr [rbp+57h+var_70], xmm0
0x180008259  test    eax, eax
0x18000825b  jnz     short loc_180008292
0x18000825d  test    ecx, ecx
0x18000825f  jnz     short loc_1800082A9
0x180008261  mov     byte ptr [rdi+20h], 0
0x180008265  lea     rcx, [rbp+57h+lpFileName]
0x180008269  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000826e  mov     rax, rdi
0x180008271  mov     rcx, [rbp+57h+var_8]
0x180008275  xor     rcx, rsp; StackCookie
0x180008278  call    __security_check_cookie
0x18000827d  lea     r11, [rsp+90h+var_s0]
0x180008285  mov     rbx, [r11+20h]
0x180008289  mov     rdi, [r11+28h]
0x18000828d  mov     rsp, r11
0x180008290  pop     rbp
0x180008291  retn
0x180008292  cmp     eax, 1
0x180008295  jz      short loc_180008261
0x180008297  lea     rdx, [rbp+57h+lpFileName]; struct std::filesystem::path *
0x18000829b  mov     rcx, rdi; this
0x18000829e  call    ??0path@filesystem@std@@QEAA@AEBV012@@Z; std::filesystem::path::path(std::filesystem::path const &)
0x1800082a3  mov     byte ptr [rdi+20h], 1
0x1800082a7  jmp     short loc_180008265
0x1800082a9  lea     r8, [rbp+57h+lpFileName]; struct std::error_code *
0x1800082ad  lea     rdx, [rbp+57h+var_70]; char *
0x1800082b1  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDAEBVerror_code@2@AEBVpath@12@@Z; std::filesystem::_Throw_fs_error(char const *,std::error_code const &,std::filesystem::path const &)
```
