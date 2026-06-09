# Ext_EnhancedProtectedMode_IsCompatible(_GUID const &,ulong,bool)

- ea: `0x180060514`
- end: `0x180060698`
- name: `?Ext_EnhancedProtectedMode_IsCompatible@@YAHAEBU_GUID@@K_N@Z`
- size: `388`
- prototype: `__int64 __fastcall(const struct _GUID *, unsigned int, bool)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180060360`
- `0x18009d790`

## callees

- `0x180060514`
- `0x180060c98`
- `0x180119168`
- `0x180119504`
- `0x1801199f4`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180060545`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18006055a`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180060583`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180060598`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180060602`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180060629`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18006065b`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180060670`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180060545`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18006055a`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180060583`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180060598`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180060602`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180060629`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18006065b`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180060670`

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
0x180060514  push    rbx
0x180060516  push    rbp
0x180060517  push    rsi
0x180060518  push    rdi
0x180060519  sub     rsp, 38h
0x18006051d  lea     eax, [rdx-1]
0x180060520  mov     sil, r8b
0x180060523  mov     ebx, edx
0x180060525  mov     rbp, rcx
0x180060528  mov     edi, 1
0x18006052d  cmp     eax, 2
0x180060530  jbe     short loc_180060540
0x180060532  cmp     edx, 0Ah
0x180060535  jz      short loc_180060540
0x180060537  test    r8b, r8b
0x18006053a  jz      loc_18006068C
0x180060540  mov     ecx, 10000017h
0x180060545  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18006054c  nop     dword ptr [rax+rax+00h]
0x180060551  test    al, al
0x180060553  jnz     short loc_18006056E
0x180060555  mov     ecx, 1000003Dh
0x18006055a  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180060561  nop     dword ptr [rax+rax+00h]
0x180060566  test    al, al
0x180060568  jz      loc_18006068C
0x18006056e  mov     rcx, rbp; struct _GUID *
0x180060571  call    ?Ext_IsInstalled@@YA_NAEBU_GUID@@K@Z; Ext_IsInstalled(_GUID const &,ulong)
0x180060576  test    al, al
0x180060578  jz      loc_18006068C
0x18006057e  mov     ecx, 10000017h
0x180060583  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18006058a  nop     dword ptr [rax+rax+00h]
0x18006058f  test    al, al
0x180060591  jnz     short loc_1800605A8
0x180060593  mov     ecx, 10000016h
0x180060598  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18006059f  nop     dword ptr [rax+rax+00h]
0x1800605a4  test    al, al
0x1800605a6  jz      short loc_180060624
0x1800605a8  mov     [rsp+58h+arg_8], 0
0x1800605b0  mov     rcx, rbp; struct _GUID *
0x1800605b3  cmp     ebx, 4
0x1800605b6  jnz     short loc_1800605C4
0x1800605b8  lea     rdx, [rsp+58h+arg_8]; enum _EXT_ARCHITECTURE *
0x1800605bd  call    ?Ext_GetArchitectureBrowserExt@@YAJAEBU_GUID@@PEAW4_EXT_ARCHITECTURE@@@Z; Ext_GetArchitectureBrowserExt(_GUID const &,_EXT_ARCHITECTURE *)
0x1800605c2  jmp     short loc_1800605DE
0x1800605c4  lea     rax, [rsp+58h+arg_8]
0x1800605c9  mov     r9d, 17h; unsigned int
0x1800605cf  xor     r8d, r8d; unsigned __int64
0x1800605d2  mov     [rsp+58h+var_38], rax; enum _EXT_ARCHITECTURE *
0x1800605d7  xor     edx, edx; unsigned __int16 *
0x1800605d9  call    ?Ext_GetModulePath@@YAJAEBU_GUID@@PEAG_KKPEAW4_EXT_ARCHITECTURE@@@Z; Ext_GetModulePath(_GUID const &,ushort *,unsigned __int64,ulong,_EXT_ARCHITECTURE *)
0x1800605de  test    eax, eax
0x1800605e0  js      short loc_180060624
0x1800605e2  lea     eax, [rbx-2]
0x1800605e5  test    eax, 0FFFFFFF6h
0x1800605ea  jnz     short loc_1800605FD
0x1800605ec  cmp     ebx, 0Bh
0x1800605ef  jz      short loc_1800605FD
0x1800605f1  xor     eax, eax
0x1800605f3  cmp     [rsp+58h+arg_8], 3
0x1800605f8  cmovnz  edi, eax
0x1800605fb  jmp     short loc_180060624
0x1800605fd  mov     ecx, 20000002h
0x180060602  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180060609  nop     dword ptr [rax+rax+00h]
0x18006060e  test    al, al
0x180060610  jz      short loc_180060624
0x180060612  test    sil, sil
0x180060615  jnz     short loc_18006061B
0x180060617  cmp     ebx, edi
0x180060619  jnz     short loc_180060624
0x18006061b  test    byte ptr [rsp+58h+arg_8], 2
0x180060620  jnz     short loc_180060624
0x180060622  xor     edi, edi
0x180060624  mov     ecx, 1000003Dh
0x180060629  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180060630  nop     dword ptr [rax+rax+00h]
0x180060635  test    al, al
0x180060637  jz      short loc_18006068C
0x180060639  test    edi, edi
0x18006063b  jz      short loc_18006068C
0x18006063d  test    sil, sil
0x180060640  jnz     short loc_180060656
0x180060642  cmp     ebx, 1
0x180060645  jz      short loc_180060656
0x180060647  lea     eax, [rbx-2]
0x18006064a  test    eax, 0FFFFFFF6h
0x18006064f  jnz     short loc_18006068C
0x180060651  cmp     ebx, 0Bh
0x180060654  jmp     short loc_18006067E
0x180060656  mov     ecx, 20000002h
0x18006065b  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180060662  nop     dword ptr [rax+rax+00h]
0x180060667  test    al, al
0x180060669  jz      short loc_18006068C
0x18006066b  mov     ecx, 20000003h
0x180060670  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180060677  nop     dword ptr [rax+rax+00h]
0x18006067c  test    al, al
0x18006067e  jz      short loc_18006068C
0x180060680  mov     edx, ebx; unsigned int
0x180060682  mov     rcx, rbp; struct _GUID *
0x180060685  call    ?IsAppContainerCompatible@@YAHAEBU_GUID@@K@Z; IsAppContainerCompatible(_GUID const &,ulong)
0x18006068a  mov     edi, eax
0x18006068c  mov     eax, edi
0x18006068e  add     rsp, 38h
0x180060692  pop     rdi
0x180060693  pop     rsi
0x180060694  pop     rbp
0x180060695  pop     rbx
0x180060696  retn
```
