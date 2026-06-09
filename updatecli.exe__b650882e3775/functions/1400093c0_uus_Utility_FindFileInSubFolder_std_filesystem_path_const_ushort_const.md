# uus::Utility::FindFileInSubFolder(std::filesystem::path const &,ushort const *)

- ea: `0x1400093c0`
- end: `0x140009535`
- name: `?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@PEBG@Z`
- size: `373`
- prototype: `std::filesystem::path *__fastcall(std::filesystem::path *this, struct std::filesystem::path *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1400091e4`
- `0x1400092ec`

## callees

- `0x14000193c`
- `0x140002130`
- `0x140007168`
- `0x1400084a4`
- `0x1400087c4`
- `0x140008a34`
- `0x1400093c0`
- `0x14000a200`

## string_xrefs

- `0x1400093ef`: `uusbrain.dll`

## pseudocode

```c
std::filesystem::path *__fastcall uus::Utility::FindFileInSubFolder(
        std::filesystem::path *this,
        struct std::filesystem::path *a2)
{
  const WCHAR *v4; // rcx
  int stats; // eax
  const struct std::filesystem::path *v6; // r9
  int v7; // edx
  __int64 v8; // rcx
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  bool v15; // al
  char v17[16]; // [rsp+30h] [rbp-19h] BYREF
  __int128 v18; // [rsp+40h] [rbp-9h]
  LPCWSTR lpFileName[4]; // [rsp+50h] [rbp+7h] BYREF
  _BYTE v20[32]; // [rsp+70h] [rbp+27h] BYREF

  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v20);
  std::filesystem::operator/(lpFileName, a2, (std::filesystem *)v20);
  std::wstring::~wstring(v20);
  *(_OWORD *)v17 = 0;
  v18 = 0;
  v4 = (const WCHAR *)lpFileName;
  if ( lpFileName[3] > (LPCWSTR)7 )
    v4 = lpFileName[0];
  stats = _std_fs_get_stats(v4);
  v7 = stats;
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
              v14 = v13 - 38;
              if ( v14 )
              {
                if ( v14 != 106 )
                  v8 = 0;
              }
            }
          }
        }
      }
    }
  }
  else
  {
    if ( (v18 & 0x400) == 0 )
      goto LABEL_9;
    if ( DWORD1(v18) == -1610612724 )
    {
      v8 = 4;
      goto LABEL_19;
    }
    if ( DWORD1(v18) == -1610612733 )
      v8 = 10;
    else
LABEL_9:
      v8 = (unsigned __int128)(v18 & 0x10 | 0x20) >> 4;
  }
LABEL_19:
  *(_DWORD *)v17 = v7;
  *(_QWORD *)&v17[8] = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  if ( (_DWORD)v8 )
  {
    v15 = (_DWORD)v8 != 1;
  }
  else
  {
    v15 = 0;
    if ( v7 )
      std::filesystem::_Throw_fs_error((std::filesystem *)v8, v17, (const struct std::error_code *)lpFileName, v6);
  }
  if ( v15 )
  {
    std::filesystem::path::path(this, (const struct std::filesystem::path *)lpFileName);
    *((_BYTE *)this + 32) = 1;
  }
  else
  {
    *((_BYTE *)this + 32) = 0;
  }
  std::wstring::~wstring(lpFileName);
  return this;
}

```

## disassembly

```asm
0x1400093c0  mov     [rsp-8+arg_10], rbx
0x1400093c5  mov     [rsp-8+arg_18], rdi
0x1400093ca  push    rbp
0x1400093cb  lea     rbp, [rsp-57h]
0x1400093d0  sub     rsp, 0A0h
0x1400093d7  mov     rax, cs:__security_cookie
0x1400093de  xor     rax, rsp
0x1400093e1  mov     [rbp+57h+var_10], rax
0x1400093e5  mov     rbx, rdx
0x1400093e8  mov     rdi, rcx
0x1400093eb  mov     qword ptr [rbp+57h+var_70], rcx
0x1400093ef  lea     rax, aUusbrainDll; "uusbrain.dll"
0x1400093f6  mov     qword ptr [rbp+57h+var_70], rax
0x1400093fa  mov     qword ptr [rbp+57h+var_70+8], 0Ch
0x140009402  lea     rdx, [rbp+57h+var_70]
0x140009406  lea     rcx, [rbp+57h+var_30]; void *
0x14000940a  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort>,std::filesystem::_Normal_conversion)
0x14000940f  nop
0x140009410  lea     r8, [rbp+57h+var_30]; this
0x140009414  mov     rdx, rbx; struct std::filesystem::path *
0x140009417  lea     rcx, [rbp+57h+lpFileName]; Src
0x14000941b  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x140009420  nop
0x140009421  lea     rcx, [rbp+57h+var_30]
0x140009425  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000942a  xorps   xmm0, xmm0
0x14000942d  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x140009431  movups  [rbp+57h+var_60], xmm0
0x140009435  lea     rcx, [rbp+57h+lpFileName]
0x140009439  cmp     [rbp+57h+var_38], 7
0x14000943e  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x140009443  or      r9d, 0FFFFFFFFh
0x140009447  mov     r8d, 3
0x14000944d  lea     rdx, [rbp+57h+var_70]
0x140009451  call    __std_fs_get_stats
0x140009456  mov     edx, eax
0x140009458  test    eax, eax
0x14000945a  jnz     short loc_14000948E
0x14000945c  mov     ecx, dword ptr [rbp+57h+var_60]
0x14000945f  bt      ecx, 0Ah
0x140009463  jnb     short loc_140009483
0x140009465  cmp     dword ptr [rbp+57h+var_60+4], 0A000000Ch
0x14000946c  jnz     short loc_140009473
0x14000946e  lea     ecx, [rax+4]
0x140009471  jmp     short loc_1400094BA
0x140009473  cmp     dword ptr [rbp+57h+var_60+4], 0A0000003h
0x14000947a  jnz     short loc_140009483
0x14000947c  mov     ecx, 0Ah
0x140009481  jmp     short loc_1400094BA
0x140009483  and     ecx, 10h
0x140009486  or      ecx, 20h
0x140009489  shr     ecx, 4
0x14000948c  jmp     short loc_1400094BA
0x14000948e  sub     eax, 2
0x140009491  jz      short loc_1400094B5
0x140009493  sub     eax, 1
0x140009496  jz      short loc_1400094B5
0x140009498  sub     eax, 32h ; '2'
0x14000949b  jz      short loc_1400094B5
0x14000949d  sub     eax, 0Bh
0x1400094a0  jz      short loc_1400094B5
0x1400094a2  sub     eax, 3Bh ; ';'
0x1400094a5  jz      short loc_1400094B5
0x1400094a7  sub     eax, 26h ; '&'
0x1400094aa  jz      short loc_1400094B5
0x1400094ac  cmp     eax, 6Ah ; 'j'
0x1400094af  jz      short loc_1400094B5
0x1400094b1  xor     ecx, ecx
0x1400094b3  jmp     short loc_1400094BA
0x1400094b5  mov     ecx, 1; this
0x1400094ba  mov     dword ptr [rbp+57h+var_70], edx
0x1400094bd  mov     eax, dword ptr [rbp+57h+var_70+4]
0x1400094c0  mov     dword ptr [rbp+57h+var_70+4], eax
0x1400094c3  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4U?$_Constexpr_immortalize_impl@V_System_error_category@std@@@1@A; std::_Constexpr_immortalize_impl<std::_System_error_category> `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x1400094ca  mov     qword ptr [rbp+57h+var_70+8], rax
0x1400094ce  test    ecx, ecx
0x1400094d0  jz      short loc_1400094EE
0x1400094d2  cmp     ecx, 1
0x1400094d5  setnz   al
0x1400094d8  test    al, al
0x1400094da  jz      short loc_1400094F6
0x1400094dc  lea     rdx, [rbp+57h+lpFileName]; struct std::filesystem::path *
0x1400094e0  mov     rcx, rdi; this
0x1400094e3  call    ??0path@filesystem@std@@QEAA@AEBV012@@Z; std::filesystem::path::path(std::filesystem::path const &)
0x1400094e8  mov     byte ptr [rdi+20h], 1
0x1400094ec  jmp     short loc_1400094FA
0x1400094ee  xor     al, al
0x1400094f0  test    edx, edx
0x1400094f2  jnz     short loc_140009527
0x1400094f4  jmp     short loc_1400094D8
0x1400094f6  mov     byte ptr [rdi+20h], 0
0x1400094fa  lea     rcx, [rbp+57h+lpFileName]
0x1400094fe  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140009503  mov     rax, rdi
0x140009506  mov     rcx, [rbp+57h+var_10]
0x14000950a  xor     rcx, rsp; StackCookie
0x14000950d  call    __security_check_cookie
0x140009512  lea     r11, [rsp+0A0h+var_s0]
0x14000951a  mov     rbx, [r11+20h]
0x14000951e  mov     rdi, [r11+28h]
0x140009522  mov     rsp, r11
0x140009525  pop     rbp
0x140009526  retn
0x140009527  lea     r8, [rbp+57h+lpFileName]; struct std::error_code *
0x14000952b  lea     rdx, [rbp+57h+var_70]; char *
0x14000952f  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDAEBVerror_code@2@AEBVpath@12@@Z; std::filesystem::_Throw_fs_error(char const *,std::error_code const &,std::filesystem::path const &)
```
