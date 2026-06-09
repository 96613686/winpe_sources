# std::filesystem::exists(std::filesystem::path const &)

- ea: `0x18000a498`
- end: `0x18000a58b`
- name: `?exists@filesystem@std@@YA_NAEBVpath@12@@Z`
- size: `243`
- prototype: `bool __fastcall(std::filesystem *__hidden this, const struct std::filesystem::path *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180009540`
- `0x180009bf0`

## callees

- `0x180001e20`
- `0x1800026d0`
- `0x18000a26c`
- `0x18000a498`

## pseudocode

```c
bool __fastcall std::filesystem::exists(std::filesystem *this, const struct std::filesystem::path *a2)
{
  bool v2; // cc
  const struct std::error_code *v3; // rbx
  int stats; // eax
  const struct std::filesystem::path *v5; // r9
  int v6; // edx
  __int64 v7; // rcx
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  bool result; // al
  char v15[16]; // [rsp+20h] [rbp-38h] BYREF
  __int128 v16; // [rsp+30h] [rbp-28h]

  v2 = *((_QWORD *)this + 3) <= 7u;
  *(_OWORD *)v15 = 0;
  v3 = this;
  v16 = 0;
  if ( !v2 )
    this = *(std::filesystem **)this;
  stats = _std_fs_get_stats((LPCWSTR)this);
  v6 = stats;
  if ( stats )
  {
    v8 = stats - 2;
    v7 = 1;
    if ( v8 )
    {
      v9 = v8 - 1;
      if ( v9 )
      {
        v10 = v9 - 50;
        if ( v10 )
        {
          v11 = v10 - 11;
          if ( v11 )
          {
            v12 = v11 - 59;
            if ( v12 )
            {
              v13 = v12 - 38;
              if ( v13 )
              {
                if ( v13 != 106 )
                  v7 = 0;
              }
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
      v7 = 4;
      goto LABEL_19;
    }
    if ( DWORD1(v16) == -1610612733 )
      v7 = 10;
    else
LABEL_9:
      v7 = (unsigned __int128)(v16 & 0x10 | 0x20) >> 4;
  }
LABEL_19:
  *(_QWORD *)&v15[8] = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  *(_DWORD *)v15 = v6;
  if ( (_DWORD)v7 )
    return (_DWORD)v7 != 1;
  result = 0;
  if ( v6 )
    std::filesystem::_Throw_fs_error((std::filesystem *)v7, v15, v3, v5);
  return result;
}

```

## disassembly

```asm
0x18000a498  push    rbx
0x18000a49a  sub     rsp, 50h
0x18000a49e  mov     rax, cs:__security_cookie
0x18000a4a5  xor     rax, rsp
0x18000a4a8  mov     [rsp+58h+var_18], rax
0x18000a4ad  cmp     qword ptr [rcx+18h], 7
0x18000a4b2  xorps   xmm0, xmm0
0x18000a4b5  movups  xmmword ptr [rsp+58h+var_38], xmm0
0x18000a4ba  mov     rbx, rcx
0x18000a4bd  movups  [rsp+58h+var_28], xmm0
0x18000a4c2  jbe     short loc_18000A4C7
0x18000a4c4  mov     rcx, [rcx]; lpFileName
0x18000a4c7  or      r9d, 0FFFFFFFFh
0x18000a4cb  lea     rdx, [rsp+58h+var_38]
0x18000a4d0  mov     r8d, 3
0x18000a4d6  call    __std_fs_get_stats
0x18000a4db  mov     edx, eax
0x18000a4dd  test    eax, eax
0x18000a4df  jnz     short loc_18000A516
0x18000a4e1  mov     ecx, dword ptr [rsp+58h+var_28]
0x18000a4e5  bt      ecx, 0Ah
0x18000a4e9  jnb     short loc_18000A50B
0x18000a4eb  cmp     dword ptr [rsp+58h+var_28+4], 0A000000Ch
0x18000a4f3  jnz     short loc_18000A4FA
0x18000a4f5  lea     ecx, [rax+4]
0x18000a4f8  jmp     short loc_18000A542
0x18000a4fa  cmp     dword ptr [rsp+58h+var_28+4], 0A0000003h
0x18000a502  jnz     short loc_18000A50B
0x18000a504  mov     ecx, 0Ah
0x18000a509  jmp     short loc_18000A542
0x18000a50b  and     ecx, 10h
0x18000a50e  or      ecx, 20h
0x18000a511  shr     ecx, 4
0x18000a514  jmp     short loc_18000A542
0x18000a516  sub     eax, 2
0x18000a519  jz      short loc_18000A53D
0x18000a51b  sub     eax, 1
0x18000a51e  jz      short loc_18000A53D
0x18000a520  sub     eax, 32h ; '2'
0x18000a523  jz      short loc_18000A53D
0x18000a525  sub     eax, 0Bh
0x18000a528  jz      short loc_18000A53D
0x18000a52a  sub     eax, 3Bh ; ';'
0x18000a52d  jz      short loc_18000A53D
0x18000a52f  sub     eax, 26h ; '&'
0x18000a532  jz      short loc_18000A53D
0x18000a534  cmp     eax, 6Ah ; 'j'
0x18000a537  jz      short loc_18000A53D
0x18000a539  xor     ecx, ecx
0x18000a53b  jmp     short loc_18000A542
0x18000a53d  mov     ecx, 1; this
0x18000a542  mov     eax, dword ptr [rsp+58h+var_38+4]
0x18000a546  mov     dword ptr [rsp+58h+var_38+4], eax
0x18000a54a  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4U?$_Constexpr_immortalize_impl@V_System_error_category@std@@@1@A; std::_Constexpr_immortalize_impl<std::_System_error_category> `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x18000a551  mov     qword ptr [rsp+58h+var_38+8], rax
0x18000a556  mov     dword ptr [rsp+58h+var_38], edx
0x18000a55a  test    ecx, ecx
0x18000a55c  jz      short loc_18000A577
0x18000a55e  cmp     ecx, 1
0x18000a561  setnz   al
0x18000a564  mov     rcx, [rsp+58h+var_18]
0x18000a569  xor     rcx, rsp; StackCookie
0x18000a56c  call    __security_check_cookie
0x18000a571  add     rsp, 50h
0x18000a575  pop     rbx
0x18000a576  retn
0x18000a577  xor     al, al
0x18000a579  test    edx, edx
0x18000a57b  jz      short loc_18000A564
0x18000a57d  mov     r8, rbx; struct std::error_code *
0x18000a580  lea     rdx, [rsp+58h+var_38]; char *
0x18000a585  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDAEBVerror_code@2@AEBVpath@12@@Z; std::filesystem::_Throw_fs_error(char const *,std::error_code const &,std::filesystem::path const &)
```
