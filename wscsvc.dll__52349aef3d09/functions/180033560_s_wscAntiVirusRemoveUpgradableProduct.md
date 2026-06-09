# s_wscAntiVirusRemoveUpgradableProduct

- ea: `0x180033560`
- end: `0x180033742`
- name: `s_wscAntiVirusRemoveUpgradableProduct`
- size: `482`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180017b00`
- `0x180018ab0`
- `0x1800287d4`
- `0x180031c30`
- `0x180032508`
- `0x18003280c`
- `0x180033560`
- `0x18003fc30`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800335d2`
- `msvcrt!_wcsicmp` at `0x1800335d2`
- `ADVAPI32!RegDeleteKeyW` at `0x18003367b`
- `ADVAPI32!RegDeleteKeyW` at `0x18003367b`

## string_xrefs

- `0x180033632`: `SOFTWARE\Microsoft\Security Center\ProvidersMigration\WicaUpgradableAVs`

## pseudocode

```c
__int64 __fastcall s_wscAntiVirusRemoveUpgradableProduct(__int64 a1, const wchar_t *a2)
{
  unsigned int v3; // ebx
  _QWORD *v4; // rbx
  const wchar_t *v5; // rdx
  unsigned __int64 v6; // r8
  const unsigned __int16 *v7; // rcx
  __int64 v8; // rcx
  _QWORD *i; // rax
  const WCHAR *v10; // rdx
  LSTATUS v11; // eax
  _BYTE v13[8]; // [rsp+20h] [rbp-E0h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int64 v15; // [rsp+40h] [rbp-C0h]
  unsigned __int16 v16[264]; // [rsp+50h] [rbp-B0h] BYREF

  v15 = 7;
  lpSubKey[2] = 0;
  LOWORD(lpSubKey[0]) = 0;
  if ( a2 )
  {
    v4 = *(_QWORD **)g_UpgradableProducts;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( v4 == (_QWORD *)g_UpgradableProducts )
        {
          v3 = 0;
          goto LABEL_39;
        }
        v5 = (const wchar_t *)(v4 + 4);
        if ( v4[7] >= 8u )
          v5 = *(const wchar_t **)v5;
        if ( _wcsicmp(a2, v5) )
          break;
        v7 = (const unsigned __int16 *)(v4 + 8);
        if ( v4[11] >= 8u )
          v7 = *(const unsigned __int16 **)v7;
        if ( (int)StripInvalidPathCharsFromString(v7, v16, v6) >= 0 )
        {
          std::wstring::assign(lpSubKey, L"SOFTWARE\\Microsoft\\Security Center\\ProvidersMigration\\WicaUpgradableAVs");
          std::wstring::append(lpSubKey, L"\\");
          std::wstring::append(lpSubKey, v16);
          v10 = (const WCHAR *)lpSubKey;
          if ( v15 >= 8 )
            v10 = lpSubKey[0];
          v11 = RegDeleteKeyW(HKEY_LOCAL_MACHINE, v10);
          if ( (v11 & 0xFFFFFFFC) != 0 || v11 == 1 )
          {
            if ( !*((_BYTE *)v4 + 25) )
            {
              v8 = v4[2];
              if ( !*(_BYTE *)(v8 + 25) )
                goto LABEL_32;
              for ( i = (_QWORD *)v4[1]; !*((_BYTE *)i + 25) && v4 == (_QWORD *)i[2]; i = (_QWORD *)i[1] )
                v4 = i;
              goto LABEL_37;
            }
          }
          else
          {
            v4 = *(_QWORD **)std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::erase(
                               &g_UpgradableProducts,
                               v13,
                               v4);
          }
        }
        else if ( !*((_BYTE *)v4 + 25) )
        {
          v8 = v4[2];
          if ( !*(_BYTE *)(v8 + 25) )
            goto LABEL_32;
          for ( i = (_QWORD *)v4[1]; !*((_BYTE *)i + 25) && v4 == (_QWORD *)i[2]; i = (_QWORD *)i[1] )
            v4 = i;
          goto LABEL_37;
        }
      }
      if ( !*((_BYTE *)v4 + 25) )
      {
        v8 = v4[2];
        if ( !*(_BYTE *)(v8 + 25) )
        {
LABEL_32:
          i = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Min((_QWORD *)v8);
          goto LABEL_37;
        }
        for ( i = (_QWORD *)v4[1]; !*((_BYTE *)i + 25) && v4 == (_QWORD *)i[2]; i = (_QWORD *)i[1] )
          v4 = i;
LABEL_37:
        v4 = i;
      }
    }
  }
  v3 = 87;
LABEL_39:
  std::wstring::_Tidy(lpSubKey, 1, 0);
  return v3;
}

```

## disassembly

```asm
0x180033560  push    rbp
0x180033562  push    rbx
0x180033563  push    rsi
0x180033564  push    rdi
0x180033565  lea     rbp, [rsp-178h]
0x18003356d  sub     rsp, 278h
0x180033574  mov     rax, cs:__security_cookie
0x18003357b  xor     rax, rsp
0x18003357e  mov     [rbp+190h+var_30], rax
0x180033585  xor     esi, esi
0x180033587  mov     [rsp+290h+var_250], 7
0x180033590  mov     [rsp+290h+var_258], rsi
0x180033595  mov     rdi, rdx
0x180033598  mov     word ptr [rsp+290h+lpSubKey], si
0x18003359d  test    rdx, rdx
0x1800335a0  jnz     short loc_1800335AA
0x1800335a2  lea     ebx, [rdx+57h]
0x1800335a5  jmp     loc_180033716
0x1800335aa  mov     rbx, cs:?g_UpgradableProducts@@3V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@A; std::map<std::wstring,std::wstring> g_UpgradableProducts
0x1800335b1  mov     rbx, [rbx]
0x1800335b4  cmp     rbx, cs:?g_UpgradableProducts@@3V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@A; std::map<std::wstring,std::wstring> g_UpgradableProducts
0x1800335bb  jz      loc_180033714
0x1800335c1  cmp     qword ptr [rbx+38h], 8
0x1800335c6  lea     rdx, [rbx+20h]
0x1800335ca  jb      short loc_1800335CF
0x1800335cc  mov     rdx, [rdx]; String2
0x1800335cf  mov     rcx, rdi; String1
0x1800335d2  call    cs:__imp__wcsicmp
0x1800335d8  test    eax, eax
0x1800335da  jnz     loc_1800336D8
0x1800335e0  cmp     qword ptr [rbx+58h], 8
0x1800335e5  lea     rcx, [rbx+40h]
0x1800335e9  jb      short loc_1800335EE
0x1800335eb  mov     rcx, [rcx]; unsigned __int16 *
0x1800335ee  lea     rdx, [rsp+290h+var_240]; unsigned __int16 *
0x1800335f3  call    ?StripInvalidPathCharsFromString@@YAJPEBGPEAG_K@Z; StripInvalidPathCharsFromString(ushort const *,ushort *,unsigned __int64)
0x1800335f8  test    eax, eax
0x1800335fa  jns     short loc_180033632
0x1800335fc  cmp     [rbx+19h], sil
0x180033600  jnz     short loc_1800335B4
0x180033602  mov     rcx, [rbx+10h]
0x180033606  cmp     [rcx+19h], sil
0x18003360a  jz      loc_1800336EC
0x180033610  mov     rax, [rbx+8]
0x180033614  jmp     short loc_180033627
0x180033616  cmp     rbx, [rax+10h]
0x18003361a  jnz     loc_18003370C
0x180033620  mov     rbx, rax
0x180033623  mov     rax, [rax+8]
0x180033627  cmp     [rax+19h], sil
0x18003362b  jz      short loc_180033616
0x18003362d  jmp     loc_18003370C
0x180033632  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Security Center\\P"...
0x180033639  lea     rcx, [rsp+290h+lpSubKey]
0x18003363e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180033643  lea     rdx, asc_1800465F0; "\\"
0x18003364a  lea     rcx, [rsp+290h+lpSubKey]
0x18003364f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x180033654  lea     rdx, [rsp+290h+var_240]
0x180033659  lea     rcx, [rsp+290h+lpSubKey]
0x18003365e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x180033663  cmp     [rsp+290h+var_250], 8
0x180033669  lea     rdx, [rsp+290h+lpSubKey]
0x18003366e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180033675  cmovnb  rdx, [rsp+290h+lpSubKey]; lpSubKey
0x18003367b  call    cs:__imp_RegDeleteKeyW
0x180033681  test    eax, 0FFFFFFFCh
0x180033686  jnz     short loc_1800336A9
0x180033688  cmp     eax, 1
0x18003368b  jz      short loc_1800336A9
0x18003368d  mov     r8, rbx
0x180033690  lea     rdx, [rsp+290h+var_270]
0x180033695  lea     rcx, ?g_UpgradableProducts@@3V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@A; std::map<std::wstring,std::wstring> g_UpgradableProducts
0x18003369c  call    ?erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>>)
0x1800336a1  mov     rbx, [rax]
0x1800336a4  jmp     loc_1800335B4
0x1800336a9  cmp     [rbx+19h], sil
0x1800336ad  jnz     loc_1800335B4
0x1800336b3  mov     rcx, [rbx+10h]
0x1800336b7  cmp     [rcx+19h], sil
0x1800336bb  jz      short loc_1800336EC
0x1800336bd  mov     rax, [rbx+8]
0x1800336c1  jmp     short loc_1800336D0
0x1800336c3  cmp     rbx, [rax+10h]
0x1800336c7  jnz     short loc_18003370C
0x1800336c9  mov     rbx, rax
0x1800336cc  mov     rax, [rax+8]
0x1800336d0  cmp     [rax+19h], sil
0x1800336d4  jz      short loc_1800336C3
0x1800336d6  jmp     short loc_18003370C
0x1800336d8  cmp     [rbx+19h], sil
0x1800336dc  jnz     loc_1800335B4
0x1800336e2  mov     rcx, [rbx+10h]
0x1800336e6  cmp     [rcx+19h], sil
0x1800336ea  jnz     short loc_1800336F3
0x1800336ec  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Min(std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *)
0x1800336f1  jmp     short loc_18003370C
0x1800336f3  mov     rax, [rbx+8]
0x1800336f7  jmp     short loc_180033706
0x1800336f9  cmp     rbx, [rax+10h]
0x1800336fd  jnz     short loc_18003370C
0x1800336ff  mov     rbx, rax
0x180033702  mov     rax, [rax+8]
0x180033706  cmp     [rax+19h], sil
0x18003370a  jz      short loc_1800336F9
0x18003370c  mov     rbx, rax
0x18003370f  jmp     loc_1800335B4
0x180033714  mov     ebx, esi
0x180033716  xor     r8d, r8d
0x180033719  lea     rcx, [rsp+290h+lpSubKey]
0x18003371e  mov     dl, 1
0x180033720  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180033725  mov     eax, ebx
0x180033727  mov     rcx, [rbp+190h+var_30]
0x18003372e  xor     rcx, rsp; StackCookie
0x180033731  call    __security_check_cookie
0x180033736  add     rsp, 278h
0x18003373d  pop     rdi
0x18003373e  pop     rsi
0x18003373f  pop     rbx
0x180033740  pop     rbp
0x180033741  retn
```
