# WldpCheckSipAgainstHost

- ea: `0x18002c64c`
- end: `0x18002c9cb`
- name: `WldpCheckSipAgainstHost`
- size: `895`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *, char)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18001e1d4`

## callees

- `0x18001e628`
- `0x18002c64c`
- `0x18002d8b8`

## string_xrefs

- `0x18002c9b4`: `onecore\base\ngscb\wldp\dll\filetrust.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WldpCheckSipAgainstHost(_QWORD *a1, _QWORD *a2, char a3)
{
  __int64 v5; // r9
  __int64 v6; // rdx
  unsigned int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a3 )
  {
    if ( *a1 == WLDP_HOST_CMD && a1[1] == 0x7F06C5A57F349084LL
      || *a1 == WLDP_HOST_HTML && a1[1] == 0x66EDCD0EFF2D4395LL
      || *a1 == WLDP_HOST_XML && a1[1] == 0x363A0ED294D4F482LL )
    {
      if ( *a2 == 0x11D08E78C689AAB8LL && a2[1] == 0xEE95C24FC000478CuLL
        || *a2 == 0x11D08E78C689AABALL && a2[1] == 0xEE95C24FC000478CuLL
        || *a2 == 0x11D08E59DE351A43LL && a2[1] == 0xEE95C24FC000478CuLL
        || *a2 == 0x11D0E73A9BA61D3FLL && a2[1] == 0xEE95C24FC000D28CuLL
        || *a2 == 790769 && a2[1] == 0x46000000000000C0LL )
      {
        v5 = 8233;
        v6 = 1523;
        return wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)v6,
                 (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\filetrust.cpp",
                 (const char *)v5,
                 v8);
      }
    }
    else if ( (*a1 != WLDP_HOST_OTHER || a1[1] != 0x7CCF740221ED0098LL)
           && (!(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime>::GetImpl'::`2'::impl)
            || *a1 != WLDP_HOST_MCPB
            || a1[1] != 0x5FC1B7B9D6833AABLL) )
    {
      if ( *a1 == WLDP_HOST_WINDOWS_SCRIPT_HOST && a1[1] == 0x492EA80700A3EC86LL )
      {
        if ( (*a2 != 0x4DB527991629F04ELL || a2[1] != 0xABEB170FE1ACE58FuLL)
          && (*a2 != 0x11D438CE1A610570LL || a2[1] != 0x9050D34B1000A3A2uLL)
          && (*a2 != 0x11D438CE06C9E010LL || a2[1] != 0x9050D34B1000A3A2uLL) )
        {
          v5 = 8233;
          v6 = 1553;
          return wil::details::in1diag3::Return_Win32(
                   retaddr,
                   (void *)v6,
                   (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\filetrust.cpp",
                   (const char *)v5,
                   v8);
        }
      }
      else if ( *a1 == WLDP_HOST_JAVASCRIPT && a1[1] == 0xC0748DC1A836A3A1uLL )
      {
        if ( *a2 != 0x11D438CE06C9E010LL || a2[1] != 0x9050D34B1000A3A2uLL )
        {
          v5 = 8233;
          v6 = 1563;
          return wil::details::in1diag3::Return_Win32(
                   retaddr,
                   (void *)v6,
                   (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\filetrust.cpp",
                   (const char *)v5,
                   v8);
        }
      }
      else if ( *a1 == WLDP_HOST_POWERSHELL && a1[1] == 0x5864AD470DA541AELL )
      {
        if ( *a2 != 0x4E084B59603BCC1FLL || a2[1] != 0x51F37E29C6D224B7LL )
        {
          v5 = 8233;
          v6 = 1573;
          return wil::details::in1diag3::Return_Win32(
                   retaddr,
                   (void *)v6,
                   (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\filetrust.cpp",
                   (const char *)v5,
                   v8);
        }
      }
      else if ( *a1 == WLDP_HOST_MSI && a1[1] == 0x90F3FCDBECF0FE9BuLL )
      {
        if ( *a2 != 790769 || a2[1] != 0x46000000000000C0LL )
        {
          v5 = 8233;
          v6 = 1583;
          return wil::details::in1diag3::Return_Win32(
                   retaddr,
                   (void *)v6,
                   (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\filetrust.cpp",
                   (const char *)v5,
                   v8);
        }
      }
      else if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime>::GetImpl'::`2'::impl)
             && *a1 == WLDP_HOST_MSIX
             && a1[1] == 0xE7904DFC823B54BBuLL )
      {
        if ( *a2 != 0x11D08E59DE351A43LL || a2[1] != 0xEE95C24FC000478CuLL )
        {
          v5 = 8233;
          v6 = 1595;
          return wil::details::in1diag3::Return_Win32(
                   retaddr,
                   (void *)v6,
                   (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\filetrust.cpp",
                   (const char *)v5,
                   v8);
        }
      }
      else
      {
        if ( *a1 != WLDP_HOST_PYTHON || a1[1] != 0x4A2D35099F0D0B81LL )
        {
          v5 = 2147942487LL;
          v6 = 1610;
          return wil::details::in1diag3::Return_Win32(
                   retaddr,
                   (void *)v6,
                   (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\filetrust.cpp",
                   (const char *)v5,
                   v8);
        }
        if ( *a2 != 0x4AE881D91001EFB1LL || a2[1] != 0x820660245D684792uLL )
        {
          v5 = 8233;
          v6 = 1606;
          return wil::details::in1diag3::Return_Win32(
                   retaddr,
                   (void *)v6,
                   (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\filetrust.cpp",
                   (const char *)v5,
                   v8);
        }
      }
    }
    return 0;
  }
  if ( *a2 == 0x11D08E59DE351A42LL && a2[1] == 0xEE95C24FC000478CuLL )
    return 0;
  v5 = 8233;
  v6 = 1503;
  return wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v6,
           (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\filetrust.cpp",
           (const char *)v5,
           v8);
}

```

## disassembly

```asm
0x18002c64c  mov     [rsp+arg_0], rbx
0x18002c651  push    rdi; unsigned int
0x18002c652  sub     rsp, 20h
0x18002c656  mov     rbx, rdx
0x18002c659  mov     rdi, rcx
0x18002c65c  test    r8b, r8b
0x18002c65f  jnz     short loc_18002C68E
0x18002c661  mov     rax, [rdx]
0x18002c664  cmp     rax, cs:qword_18004BCD8
0x18002c66b  jnz     short loc_18002C67E
0x18002c66d  mov     rax, [rdx+8]
0x18002c671  cmp     rax, cs:qword_18004BCE0
0x18002c678  jz      loc_18002C993
0x18002c67e  mov     r9d, 2029h
0x18002c684  mov     edx, 5DFh
0x18002c689  jmp     loc_18002C9AF
0x18002c68e  mov     rax, [rcx]
0x18002c691  cmp     rax, cs:WLDP_HOST_CMD
0x18002c698  jnz     short loc_18002C6A7
0x18002c69a  mov     rax, [rcx+8]
0x18002c69e  cmp     rax, cs:qword_180048B98
0x18002c6a5  jz      short loc_18002C6E1
0x18002c6a7  mov     rax, [rcx]
0x18002c6aa  cmp     rax, cs:WLDP_HOST_HTML
0x18002c6b1  jnz     short loc_18002C6C0
0x18002c6b3  mov     rax, [rcx+8]
0x18002c6b7  cmp     rax, cs:qword_180048DB8
0x18002c6be  jz      short loc_18002C6E1
0x18002c6c0  mov     rax, [rcx]
0x18002c6c3  cmp     rax, cs:WLDP_HOST_XML
0x18002c6ca  jnz     loc_18002C776
0x18002c6d0  mov     rax, [rcx+8]
0x18002c6d4  cmp     rax, cs:qword_180048B60
0x18002c6db  jnz     loc_18002C776
0x18002c6e1  mov     rax, [rdx]
0x18002c6e4  cmp     rax, cs:qword_18004BD48
0x18002c6eb  jnz     short loc_18002C6FA
0x18002c6ed  mov     rax, [rdx+8]
0x18002c6f1  cmp     rax, cs:qword_18004BD50
0x18002c6f8  jz      short loc_18002C766
0x18002c6fa  mov     rax, [rdx]
0x18002c6fd  cmp     rax, cs:qword_18004BD18
0x18002c704  jnz     short loc_18002C713
0x18002c706  mov     rax, [rdx+8]
0x18002c70a  cmp     rax, cs:qword_18004BD20
0x18002c711  jz      short loc_18002C766
0x18002c713  mov     rax, [rdx]
0x18002c716  cmp     rax, cs:qword_18004BCC8
0x18002c71d  jnz     short loc_18002C72C
0x18002c71f  mov     rax, [rdx+8]
0x18002c723  cmp     rax, cs:qword_18004BCD0
0x18002c72a  jz      short loc_18002C766
0x18002c72c  mov     rax, [rdx]
0x18002c72f  cmp     rax, cs:qword_18004BCA8
0x18002c736  jnz     short loc_18002C745
0x18002c738  mov     rax, [rdx+8]
0x18002c73c  cmp     rax, cs:qword_18004BCB0
0x18002c743  jz      short loc_18002C766
0x18002c745  mov     rax, [rdx]
0x18002c748  cmp     rax, cs:qword_18004BD68
0x18002c74f  jnz     loc_18002C993
0x18002c755  mov     rax, [rdx+8]
0x18002c759  cmp     rax, cs:qword_18004BD70
0x18002c760  jnz     loc_18002C993
0x18002c766  mov     r9d, 2029h
0x18002c76c  mov     edx, 5F3h
0x18002c771  jmp     loc_18002C9AF
0x18002c776  mov     rax, [rcx]
0x18002c779  cmp     rax, cs:WLDP_HOST_OTHER
0x18002c780  jnz     short loc_18002C793
0x18002c782  mov     rax, [rcx+8]
0x18002c786  cmp     rax, cs:qword_180048D78
0x18002c78d  jz      loc_18002C993
0x18002c793  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime> `wil::Feature<__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime>::GetImpl(void)'::`2'::impl
0x18002c79a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime>::__private_IsEnabled(void)
0x18002c79f  test    al, al
0x18002c7a1  jz      short loc_18002C7C0
0x18002c7a3  mov     rax, [rdi]
0x18002c7a6  cmp     rax, cs:WLDP_HOST_MCPB
0x18002c7ad  jnz     short loc_18002C7C0
0x18002c7af  mov     rax, [rdi+8]
0x18002c7b3  cmp     rax, cs:qword_180048CC0
0x18002c7ba  jz      loc_18002C993
0x18002c7c0  mov     rax, [rdi]
0x18002c7c3  cmp     rax, cs:WLDP_HOST_WINDOWS_SCRIPT_HOST
0x18002c7ca  jnz     short loc_18002C840
0x18002c7cc  mov     rax, [rdi+8]
0x18002c7d0  cmp     rax, cs:qword_180048AF0
0x18002c7d7  jnz     short loc_18002C840
0x18002c7d9  mov     rax, [rbx]
0x18002c7dc  cmp     rax, cs:qword_18004BCB8
0x18002c7e3  jnz     short loc_18002C7F6
0x18002c7e5  mov     rax, [rbx+8]
0x18002c7e9  cmp     rax, cs:qword_18004BCC0
0x18002c7f0  jz      loc_18002C993
0x18002c7f6  mov     rax, [rbx]
0x18002c7f9  cmp     rax, cs:qword_18004BD58
0x18002c800  jnz     short loc_18002C813
0x18002c802  mov     rax, [rbx+8]
0x18002c806  cmp     rax, cs:qword_18004BD60
0x18002c80d  jz      loc_18002C993
0x18002c813  mov     rax, [rbx]
0x18002c816  cmp     rax, cs:qword_18004BD28
0x18002c81d  jnz     short loc_18002C830
0x18002c81f  mov     rax, [rbx+8]
0x18002c823  cmp     rax, cs:qword_18004BD30
0x18002c82a  jz      loc_18002C993
0x18002c830  mov     r9d, 2029h
0x18002c836  mov     edx, 611h
0x18002c83b  jmp     loc_18002C9AF
0x18002c840  mov     rax, [rdi]
0x18002c843  cmp     rax, cs:WLDP_HOST_JAVASCRIPT
0x18002c84a  jnz     short loc_18002C886
0x18002c84c  mov     rax, [rdi+8]
0x18002c850  cmp     rax, cs:qword_180048C38
0x18002c857  jnz     short loc_18002C886
0x18002c859  mov     rax, [rbx]
0x18002c85c  cmp     rax, cs:qword_18004BD28
0x18002c863  jnz     short loc_18002C876
0x18002c865  mov     rax, [rbx+8]
0x18002c869  cmp     rax, cs:qword_18004BD30
0x18002c870  jz      loc_18002C993
0x18002c876  mov     r9d, 2029h
0x18002c87c  mov     edx, 61Bh
0x18002c881  jmp     loc_18002C9AF
0x18002c886  mov     rax, [rdi]
0x18002c889  cmp     rax, cs:WLDP_HOST_POWERSHELL
0x18002c890  jnz     short loc_18002C8CC
0x18002c892  mov     rax, [rdi+8]
0x18002c896  cmp     rax, cs:qword_180048C98
0x18002c89d  jnz     short loc_18002C8CC
0x18002c89f  mov     rax, [rbx]
0x18002c8a2  cmp     rax, cs:qword_18004BD38
0x18002c8a9  jnz     short loc_18002C8BC
0x18002c8ab  mov     rax, [rbx+8]
0x18002c8af  cmp     rax, cs:qword_18004BD40
0x18002c8b6  jz      loc_18002C993
0x18002c8bc  mov     r9d, 2029h
0x18002c8c2  mov     edx, 625h
0x18002c8c7  jmp     loc_18002C9AF
0x18002c8cc  mov     rax, [rdi]
0x18002c8cf  cmp     rax, cs:WLDP_HOST_MSI
0x18002c8d6  jnz     short loc_18002C912
0x18002c8d8  mov     rax, [rdi+8]
0x18002c8dc  cmp     rax, cs:qword_180048D98
0x18002c8e3  jnz     short loc_18002C912
0x18002c8e5  mov     rax, [rbx]
0x18002c8e8  cmp     rax, cs:qword_18004BD68
0x18002c8ef  jnz     short loc_18002C902
0x18002c8f1  mov     rax, [rbx+8]
0x18002c8f5  cmp     rax, cs:qword_18004BD70
0x18002c8fc  jz      loc_18002C993
0x18002c902  mov     r9d, 2029h
0x18002c908  mov     edx, 62Fh
0x18002c90d  jmp     loc_18002C9AF
0x18002c912  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime> `wil::Feature<__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime>::GetImpl(void)'::`2'::impl
0x18002c919  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime>::__private_IsEnabled(void)
0x18002c91e  test    al, al
0x18002c920  jz      short loc_18002C961
0x18002c922  mov     rax, [rdi]
0x18002c925  cmp     rax, cs:WLDP_HOST_MSIX
0x18002c92c  jnz     short loc_18002C961
0x18002c92e  mov     rax, [rdi+8]
0x18002c932  cmp     rax, cs:qword_180048BD8
0x18002c939  jnz     short loc_18002C961
0x18002c93b  mov     rax, [rbx]
0x18002c93e  cmp     rax, cs:qword_18004BCC8
0x18002c945  jnz     short loc_18002C954
0x18002c947  mov     rax, [rbx+8]
0x18002c94b  cmp     rax, cs:qword_18004BCD0
0x18002c952  jz      short loc_18002C993
0x18002c954  mov     r9d, 2029h
0x18002c95a  mov     edx, 63Bh
0x18002c95f  jmp     short loc_18002C9AF
0x18002c961  mov     rax, [rdi]
0x18002c964  cmp     rax, cs:WLDP_HOST_PYTHON
0x18002c96b  jnz     short loc_18002C9A4
0x18002c96d  mov     rax, [rdi+8]
0x18002c971  cmp     rax, cs:qword_180048CD0
0x18002c978  jnz     short loc_18002C9A4
0x18002c97a  mov     rax, [rbx]
0x18002c97d  cmp     rax, cs:qword_18004BD08
0x18002c984  jnz     short loc_18002C997
0x18002c986  mov     rax, [rbx+8]
0x18002c98a  cmp     rax, cs:qword_18004BD10
0x18002c991  jnz     short loc_18002C997
0x18002c993  xor     eax, eax
0x18002c995  jmp     short loc_18002C9C0
0x18002c997  mov     r9d, 2029h
0x18002c99d  mov     edx, 646h
0x18002c9a2  jmp     short loc_18002C9AF
0x18002c9a4  mov     r9d, 80070057h; char *
0x18002c9aa  mov     edx, 64Ah; void *
0x18002c9af  mov     rcx, [rsp+28h]; this
0x18002c9b4  lea     r8, aOnecoreBaseNgs_4; "onecore\\base\\ngscb\\wldp\\dll\\filetr"...
0x18002c9bb  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002c9c0  mov     rbx, [rsp+28h+arg_0]
0x18002c9c5  add     rsp, 20h
0x18002c9c9  pop     rdi
0x18002c9ca  retn
```
