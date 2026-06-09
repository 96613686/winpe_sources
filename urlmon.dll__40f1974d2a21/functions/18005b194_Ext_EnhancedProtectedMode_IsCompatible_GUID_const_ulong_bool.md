# Ext_EnhancedProtectedMode_IsCompatible(_GUID const &,ulong,bool)

- ea: `0x18005b194`
- end: `0x18005b2e7`
- name: `?Ext_EnhancedProtectedMode_IsCompatible@@YAHAEBU_GUID@@K_N@Z`
- size: `339`
- prototype: `__int64 __fastcall(const struct _GUID *, unsigned int, bool)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18005afe0`
- `0x180096f60`

## callees

- `0x18005b194`
- `0x18005b884`
- `0x18010d620`
- `0x18010d97c`
- `0x18010de30`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18005b1c5`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18005b1d4`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18005b1f7`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18005b206`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18005b26a`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18005b28b`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18005b2b7`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18005b2c6`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18005b1c5`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18005b1d4`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18005b1f7`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18005b206`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18005b26a`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18005b28b`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18005b2b7`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18005b2c6`

## pseudocode

```c
__int64 __fastcall Ext_EnhancedProtectedMode_IsCompatible(const struct _GUID *a1, unsigned int a2, char a3)
{
  unsigned int v6; // edi
  unsigned int v7; // edx
  int v8; // eax
  bool v9; // zf
  int v11; // [rsp+68h] [rbp+10h] BYREF

  v6 = 1;
  if ( (a2 - 1 <= 2 || a2 == 10 || a3)
    && ((unsigned __int8)IEConfiguration_GetBool(268435479) || (unsigned __int8)IEConfiguration_GetBool(268435517))
    && Ext_IsInstalled(a1, v7) )
  {
    if ( (unsigned __int8)IEConfiguration_GetBool(268435479) || (unsigned __int8)IEConfiguration_GetBool(268435478) )
    {
      v11 = 0;
      v8 = a2 == 4
         ? Ext_GetArchitectureBrowserExt(a1, (enum _EXT_ARCHITECTURE *)&v11)
         : Ext_GetModulePath(a1, 0, 0, 0x17u, (enum _EXT_ARCHITECTURE *)&v11);
      if ( v8 >= 0 )
      {
        if ( ((a2 - 2) & 0xFFFFFFF6) != 0 || a2 == 11 )
        {
          if ( (unsigned __int8)IEConfiguration_GetBool(536870914) && (a3 || a2 == 1) && (v11 & 2) == 0 )
            v6 = 0;
        }
        else if ( v11 != 3 )
        {
          v6 = 0;
        }
      }
    }
    if ( (unsigned __int8)IEConfiguration_GetBool(268435517) && v6 )
    {
      if ( a3 || a2 == 1 )
      {
        if ( !(unsigned __int8)IEConfiguration_GetBool(536870914) )
          return v6;
        v9 = (unsigned __int8)IEConfiguration_GetBool(536870915) == 0;
      }
      else
      {
        if ( ((a2 - 2) & 0xFFFFFFF6) != 0 )
          return v6;
        v9 = a2 == 11;
      }
      if ( !v9 )
        return (unsigned int)IsAppContainerCompatible(a1, a2);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18005b194  push    rbx
0x18005b196  push    rbp
0x18005b197  push    rsi
0x18005b198  push    rdi
0x18005b199  sub     rsp, 38h
0x18005b19d  lea     eax, [rdx-1]
0x18005b1a0  mov     sil, r8b
0x18005b1a3  mov     ebx, edx
0x18005b1a5  mov     rbp, rcx
0x18005b1a8  mov     edi, 1
0x18005b1ad  cmp     eax, 2
0x18005b1b0  jbe     short loc_18005B1C0
0x18005b1b2  cmp     edx, 0Ah
0x18005b1b5  jz      short loc_18005B1C0
0x18005b1b7  test    r8b, r8b
0x18005b1ba  jz      loc_18005B2DC
0x18005b1c0  mov     ecx, 10000017h
0x18005b1c5  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18005b1cb  test    al, al
0x18005b1cd  jnz     short loc_18005B1E2
0x18005b1cf  mov     ecx, 1000003Dh
0x18005b1d4  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18005b1da  test    al, al
0x18005b1dc  jz      loc_18005B2DC
0x18005b1e2  mov     rcx, rbp; struct _GUID *
0x18005b1e5  call    ?Ext_IsInstalled@@YA_NAEBU_GUID@@K@Z; Ext_IsInstalled(_GUID const &,ulong)
0x18005b1ea  test    al, al
0x18005b1ec  jz      loc_18005B2DC
0x18005b1f2  mov     ecx, 10000017h
0x18005b1f7  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18005b1fd  test    al, al
0x18005b1ff  jnz     short loc_18005B210
0x18005b201  mov     ecx, 10000016h
0x18005b206  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18005b20c  test    al, al
0x18005b20e  jz      short loc_18005B286
0x18005b210  mov     [rsp+58h+arg_8], 0
0x18005b218  mov     rcx, rbp; struct _GUID *
0x18005b21b  cmp     ebx, 4
0x18005b21e  jnz     short loc_18005B22C
0x18005b220  lea     rdx, [rsp+58h+arg_8]; enum _EXT_ARCHITECTURE *
0x18005b225  call    ?Ext_GetArchitectureBrowserExt@@YAJAEBU_GUID@@PEAW4_EXT_ARCHITECTURE@@@Z; Ext_GetArchitectureBrowserExt(_GUID const &,_EXT_ARCHITECTURE *)
0x18005b22a  jmp     short loc_18005B246
0x18005b22c  lea     rax, [rsp+58h+arg_8]
0x18005b231  mov     r9d, 17h; unsigned int
0x18005b237  xor     r8d, r8d; unsigned __int64
0x18005b23a  mov     [rsp+58h+var_38], rax; enum _EXT_ARCHITECTURE *
0x18005b23f  xor     edx, edx; unsigned __int16 *
0x18005b241  call    ?Ext_GetModulePath@@YAJAEBU_GUID@@PEAG_KKPEAW4_EXT_ARCHITECTURE@@@Z; Ext_GetModulePath(_GUID const &,ushort *,unsigned __int64,ulong,_EXT_ARCHITECTURE *)
0x18005b246  test    eax, eax
0x18005b248  js      short loc_18005B286
0x18005b24a  lea     eax, [rbx-2]
0x18005b24d  test    eax, 0FFFFFFF6h
0x18005b252  jnz     short loc_18005B265
0x18005b254  cmp     ebx, 0Bh
0x18005b257  jz      short loc_18005B265
0x18005b259  xor     eax, eax
0x18005b25b  cmp     [rsp+58h+arg_8], 3
0x18005b260  cmovnz  edi, eax
0x18005b263  jmp     short loc_18005B286
0x18005b265  mov     ecx, 20000002h
0x18005b26a  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18005b270  test    al, al
0x18005b272  jz      short loc_18005B286
0x18005b274  test    sil, sil
0x18005b277  jnz     short loc_18005B27D
0x18005b279  cmp     ebx, edi
0x18005b27b  jnz     short loc_18005B286
0x18005b27d  test    byte ptr [rsp+58h+arg_8], 2
0x18005b282  jnz     short loc_18005B286
0x18005b284  xor     edi, edi
0x18005b286  mov     ecx, 1000003Dh
0x18005b28b  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18005b291  test    al, al
0x18005b293  jz      short loc_18005B2DC
0x18005b295  test    edi, edi
0x18005b297  jz      short loc_18005B2DC
0x18005b299  test    sil, sil
0x18005b29c  jnz     short loc_18005B2B2
0x18005b29e  cmp     ebx, 1
0x18005b2a1  jz      short loc_18005B2B2
0x18005b2a3  lea     eax, [rbx-2]
0x18005b2a6  test    eax, 0FFFFFFF6h
0x18005b2ab  jnz     short loc_18005B2DC
0x18005b2ad  cmp     ebx, 0Bh
0x18005b2b0  jmp     short loc_18005B2CE
0x18005b2b2  mov     ecx, 20000002h
0x18005b2b7  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18005b2bd  test    al, al
0x18005b2bf  jz      short loc_18005B2DC
0x18005b2c1  mov     ecx, 20000003h
0x18005b2c6  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18005b2cc  test    al, al
0x18005b2ce  jz      short loc_18005B2DC
0x18005b2d0  mov     edx, ebx; unsigned int
0x18005b2d2  mov     rcx, rbp; struct _GUID *
0x18005b2d5  call    ?IsAppContainerCompatible@@YAHAEBU_GUID@@K@Z; IsAppContainerCompatible(_GUID const &,ulong)
0x18005b2da  mov     edi, eax
0x18005b2dc  mov     eax, edi
0x18005b2de  add     rsp, 38h
0x18005b2e2  pop     rdi
0x18005b2e3  pop     rsi
0x18005b2e4  pop     rbp
0x18005b2e5  pop     rbx
0x18005b2e6  retn
```
