# CreatePseudoExpiredProductsList(void)

- ea: `0x180031228`
- end: `0x180031497`
- name: `?CreatePseudoExpiredProductsList@@YAJXZ`
- size: `623`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180021128`

## callees

- `0x180008e48`
- `0x180017a48`
- `0x180017b00`
- `0x180018ab0`
- `0x180029158`
- `0x1800310e8`
- `0x180031228`
- `0x18003fbf2`
- `0x18003fc30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180031333`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18003141d`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180031333`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18003141d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031281`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031281`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031472`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031472`

## string_xrefs

- `0x180031273`: `SOFTWARE\Microsoft\Security Center\ProvidersMigration\WicaAvPathsExpiredSetup`

## pseudocode

```c
__int64 CreatePseudoExpiredProductsList(void)
{
  unsigned int v0; // ebx
  unsigned int v1; // eax
  int v2; // esi
  LSTATUS i; // eax
  __int64 v4; // rax
  DWORD v5; // edx
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchValueName; // [rsp+44h] [rbp-BCh] BYREF
  DWORD Type; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v11[5]; // [rsp+58h] [rbp-A8h] BYREF
  BYTE Data[528]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR ValueName[264]; // [rsp+290h] [rbp+190h] BYREF

  v0 = 0;
  hKey = 0;
  cchValueName = 0;
  cbData = 0;
  Type = 0;
  v1 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Security Center\\ProvidersMigration\\WicaAvPathsExpiredSetup",
         0,
         1u,
         &hKey);
  if ( v1 )
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids, v1);
    }
  }
  else
  {
    cchValueName = 260;
    cbData = 520;
    memset_0(ValueName, 0, 0x208u);
    memset_0(Data, 0, 0x208u);
    v2 = 1;
    for ( i = RegEnumValueW(hKey, 0, ValueName, &cchValueName, 0, &Type, Data, &cbData);
          !i;
          i = RegEnumValueW(hKey, v5, ValueName, &cchValueName, 0, &Type, Data, &cbData) )
    {
      if ( Type == 1 )
      {
        std::wstring::wstring(v11, Data);
        v4 = std::map<std::wstring,std::wstring>::operator[](&g_ExpiredProducts, v11);
        std::wstring::assign(v4, L"Expired");
        std::wstring::_Tidy(v11, 1, 0);
        if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids, Data);
        }
      }
      cchValueName = 260;
      cbData = 520;
      memset_0(ValueName, 0, 0x208u);
      memset_0(Data, 0, 0x208u);
      v5 = v2++;
    }
    if ( i != 259 )
    {
      v0 = i > 0 ? (unsigned __int16)i | 0x80070000 : i;
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids, v0);
      }
    }
  }
  RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x180031228  push    rbp
0x18003122a  push    rbx
0x18003122b  push    rsi
0x18003122c  push    rdi
0x18003122d  push    r12
0x18003122f  lea     rbp, [rsp-3B0h]
0x180031237  sub     rsp, 4B0h
0x18003123e  mov     rax, cs:__security_cookie
0x180031245  xor     rax, rsp
0x180031248  mov     [rbp+3D0h+var_30], rax
0x18003124f  xor     ebx, ebx
0x180031251  mov     [rsp+4D0h+hKey], rbx
0x180031256  mov     [rsp+4D0h+cchValueName], ebx
0x18003125a  mov     [rsp+4D0h+cbData], ebx
0x18003125e  mov     [rsp+4D0h+Type], ebx
0x180031262  lea     rax, [rsp+4D0h+hKey]
0x180031267  mov     [rsp+4D0h+phkResult], rax; phkResult
0x18003126c  lea     r9d, [rbx+1]; samDesired
0x180031270  xor     r8d, r8d; ulOptions
0x180031273  lea     rdx, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\Security Center\\P"...
0x18003127a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180031281  call    cs:__imp_RegOpenKeyExW
0x180031287  test    eax, eax
0x180031289  jz      short loc_1800312C7
0x18003128b  lea     rdi, WPP_GLOBAL_Control
0x180031292  mov     rcx, cs:WPP_GLOBAL_Control
0x180031299  cmp     rcx, rdi
0x18003129c  jz      loc_18003146D
0x1800312a2  test    byte ptr [rcx+1Ch], 4
0x1800312a6  jz      loc_18003146D
0x1800312ac  lea     edx, [rbx+20h]
0x1800312af  mov     r9d, eax
0x1800312b2  lea     r8, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids
0x1800312b9  mov     rcx, [rcx+10h]
0x1800312bd  call    WPP_SF_d
0x1800312c2  jmp     loc_18003146D
0x1800312c7  mov     [rsp+4D0h+cchValueName], 104h
0x1800312cf  mov     r12d, 208h
0x1800312d5  mov     [rsp+4D0h+cbData], r12d
0x1800312da  mov     r8d, r12d; Size
0x1800312dd  xor     edx, edx; Val
0x1800312df  lea     rcx, [rbp+3D0h+ValueName]; void *
0x1800312e6  call    memset_0
0x1800312eb  mov     r8d, r12d; Size
0x1800312ee  xor     edx, edx; Val
0x1800312f0  lea     rcx, [rbp+3D0h+Data]; void *
0x1800312f4  call    memset_0
0x1800312f9  mov     esi, 1
0x1800312fe  lea     rax, [rsp+4D0h+cbData]
0x180031303  mov     [rsp+4D0h+lpcbData], rax; lpcbData
0x180031308  lea     rax, [rbp+3D0h+Data]
0x18003130c  mov     [rsp+4D0h+lpData], rax; lpData
0x180031311  lea     rax, [rsp+4D0h+Type]
0x180031316  mov     [rsp+4D0h+lpType], rax; lpType
0x18003131b  mov     [rsp+4D0h+phkResult], rbx; lpReserved
0x180031320  lea     r9, [rsp+4D0h+cchValueName]; lpcchValueName
0x180031325  lea     r8, [rbp+3D0h+ValueName]; lpValueName
0x18003132c  xor     edx, edx; dwIndex
0x18003132e  mov     rcx, [rsp+4D0h+hKey]; hKey
0x180031333  call    cs:__imp_RegEnumValueW
0x180031339  lea     rdi, WPP_GLOBAL_Control
0x180031340  jmp     loc_180031423
0x180031345  cmp     [rsp+4D0h+Type], 1
0x18003134a  jnz     short loc_1800313B6
0x18003134c  lea     rdx, [rbp+3D0h+Data]
0x180031350  lea     rcx, [rsp+4D0h+var_478]
0x180031355  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18003135a  nop
0x18003135b  lea     rdx, [rsp+4D0h+var_478]
0x180031360  lea     rcx, ?g_ExpiredProducts@@3V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@A; std::map<std::wstring,std::wstring> g_ExpiredProducts
0x180031367  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x18003136c  lea     rdx, String1; "Expired"
0x180031373  mov     rcx, rax
0x180031376  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18003137b  nop
0x18003137c  xor     r8d, r8d
0x18003137f  mov     dl, 1
0x180031381  lea     rcx, [rsp+4D0h+var_478]
0x180031386  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18003138b  mov     rcx, cs:WPP_GLOBAL_Control
0x180031392  cmp     rcx, rdi
0x180031395  jz      short loc_1800313B6
0x180031397  test    byte ptr [rcx+1Ch], 4
0x18003139b  jz      short loc_1800313B6
0x18003139d  mov     edx, 22h ; '"'
0x1800313a2  lea     r9, [rbp+3D0h+Data]
0x1800313a6  lea     r8, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids
0x1800313ad  mov     rcx, [rcx+10h]
0x1800313b1  call    WPP_SF_S
0x1800313b6  mov     [rsp+4D0h+cchValueName], 104h
0x1800313be  mov     [rsp+4D0h+cbData], r12d
0x1800313c3  mov     r8, r12; Size
0x1800313c6  xor     edx, edx; Val
0x1800313c8  lea     rcx, [rbp+3D0h+ValueName]; void *
0x1800313cf  call    memset_0
0x1800313d4  mov     r8, r12; Size
0x1800313d7  xor     edx, edx; Val
0x1800313d9  lea     rcx, [rbp+3D0h+Data]; void *
0x1800313dd  call    memset_0
0x1800313e2  mov     edx, esi; dwIndex
0x1800313e4  inc     esi
0x1800313e6  lea     rax, [rsp+4D0h+cbData]
0x1800313eb  mov     [rsp+4D0h+lpcbData], rax; lpcbData
0x1800313f0  lea     rax, [rbp+3D0h+Data]
0x1800313f4  mov     [rsp+4D0h+lpData], rax; lpData
0x1800313f9  lea     rax, [rsp+4D0h+Type]
0x1800313fe  mov     [rsp+4D0h+lpType], rax; lpType
0x180031403  mov     [rsp+4D0h+phkResult], 0; lpReserved
0x18003140c  lea     r9, [rsp+4D0h+cchValueName]; lpcchValueName
0x180031411  lea     r8, [rbp+3D0h+ValueName]; lpValueName
0x180031418  mov     rcx, [rsp+4D0h+hKey]; hKey
0x18003141d  call    cs:__imp_RegEnumValueW
0x180031423  test    eax, eax
0x180031425  jz      loc_180031345
0x18003142b  cmp     eax, 103h
0x180031430  jz      short loc_18003146D
0x180031432  test    eax, eax
0x180031434  jg      short loc_18003143A
0x180031436  mov     ebx, eax
0x180031438  jmp     short loc_180031443
0x18003143a  movzx   ebx, ax
0x18003143d  or      ebx, 80070000h
0x180031443  mov     rcx, cs:WPP_GLOBAL_Control
0x18003144a  cmp     rcx, rdi
0x18003144d  jz      short loc_18003146D
0x18003144f  test    byte ptr [rcx+1Ch], 1
0x180031453  jz      short loc_18003146D
0x180031455  mov     edx, 21h ; '!'
0x18003145a  mov     r9d, ebx
0x18003145d  lea     r8, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids
0x180031464  mov     rcx, [rcx+10h]
0x180031468  call    WPP_SF_d
0x18003146d  mov     rcx, [rsp+4D0h+hKey]; hKey
0x180031472  call    cs:__imp_RegCloseKey
0x180031478  mov     eax, ebx
0x18003147a  mov     rcx, [rbp+3D0h+var_30]
0x180031481  xor     rcx, rsp; StackCookie
0x180031484  call    __security_check_cookie
0x180031489  add     rsp, 4B0h
0x180031490  pop     r12
0x180031492  pop     rdi
0x180031493  pop     rsi
0x180031494  pop     rbx
0x180031495  pop     rbp
0x180031496  retn
```
