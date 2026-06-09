# SubscriptionConfigWriter::SetAllExistingBookmarksToFuture(void)

- ea: `0x18001764c`
- end: `0x180017805`
- name: `?SetAllExistingBookmarksToFuture@SubscriptionConfigWriter@@AEAAXXZ`
- size: `441`
- prototype: `void __fastcall(HKEY *this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x1800165c0`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x180003810`
- `0x180003e6c`
- `0x1800062d4`
- `0x180011c24`
- `0x180011d6c`
- `0x180011e68`
- `0x180011f40`
- `0x1800128c0`
- `0x180012b94`
- `0x18001764c`
- `0x18001fe50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017691`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017691`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SubscriptionConfigWriter::SetAllExistingBookmarksToFuture(HKEY *this)
{
  unsigned int v1; // eax
  unsigned int v2; // ebx
  HKEY CurrentSubKey; // rbx
  HKEY phkResult; // [rsp+30h] [rbp-59h] BYREF
  HKEY v5; // [rsp+38h] [rbp-51h] BYREF
  HKEY v6[7]; // [rsp+40h] [rbp-49h] BYREF
  void **pExceptionObject; // [rsp+78h] [rbp-11h] BYREF
  char v8; // [rsp+80h] [rbp-9h]
  const char *v9; // [rsp+88h] [rbp-1h]
  __int64 v10; // [rsp+90h] [rbp+7h]
  __int64 v11; // [rsp+98h] [rbp+Fh]
  unsigned int v12; // [rsp+A0h] [rbp+17h]
  int v13; // [rsp+A4h] [rbp+1Bh]
  int v14; // [rsp+A8h] [rbp+1Fh]
  _QWORD v15[4]; // [rsp+B0h] [rbp+27h] BYREF

  phkResult = 0;
  v1 = RegOpenKeyExW(this[2], L"EventSources", 0, 0x2001Fu, &phkResult);
  v2 = v1;
  if ( v1 != 2 )
  {
    if ( v1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids, v1);
      }
      v8 = 0;
      v9 = "admin\\wmi\\events\\forwarding\\collector\\store\\store.cpp";
      v10 = 0;
      v11 = 0;
      v12 = v2;
      v13 = -1;
      v14 = 722;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&pExceptionObject;
    }
    RegistryKeyEnumerator::RegistryKeyEnumerator((RegistryKeyEnumerator *)v6, phkResult);
    while ( !RegistryKeyEnumerator::MoveNext((RegistryKeyEnumerator *)v6) )
    {
      CurrentSubKey = RegistryKeyEnumerator::GetCurrentSubKey((RegistryKeyEnumerator *)v6, 0x2001Fu);
      v5 = CurrentSubKey;
      v15[3] = 7;
      v15[2] = 0;
      LOWORD(v15[0]) = 0;
      if ( RegReadStringValue(CurrentSubKey, L"Bookmark", (__int64)v15) )
      {
        std::wstring::wstring((__int64)&pExceptionObject, (__int64)&word_180026AD8);
        RegWriteStringValue(CurrentSubKey, L"Bookmark", (__int64 *)&pExceptionObject);
        std::wstring::_Tidy(&pExceptionObject, 1, 0);
      }
      std::wstring::_Tidy(v15, 1, 0);
      wmi::AutoRegKey::Close(&v5);
    }
    RegistryKeyEnumerator::~RegistryKeyEnumerator(v6);
  }
}

```

## disassembly

```asm
0x18001764c  mov     [rsp-8+arg_8], rbx
0x180017651  push    rbp
0x180017652  lea     rbp, [rsp-57h]
0x180017657  sub     rsp, 0E0h
0x18001765e  mov     rax, cs:__security_cookie
0x180017665  xor     rax, rsp
0x180017668  mov     [rbp+57h+var_10], rax
0x18001766c  mov     [rbp+57h+var_B0], 0
0x180017674  lea     rax, [rbp+57h+var_B0]
0x180017678  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18001767d  mov     r9d, 2001Fh; samDesired
0x180017683  xor     r8d, r8d; ulOptions
0x180017686  lea     rdx, aEventsources; "EventSources"
0x18001768d  mov     rcx, [rcx+10h]; hKey
0x180017691  call    cs:__imp_RegOpenKeyExW
0x180017697  mov     ebx, eax
0x180017699  cmp     eax, 2
0x18001769c  jz      loc_1800177E8
0x1800176a2  test    eax, eax
0x1800176a4  jz      loc_18001772D
0x1800176aa  lea     rax, WPP_GLOBAL_Control
0x1800176b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800176b8  cmp     rcx, rax
0x1800176bb  jz      short loc_1800176E1
0x1800176bd  test    byte ptr [rcx+1Ch], 40h
0x1800176c1  jz      short loc_1800176E1
0x1800176c3  cmp     byte ptr [rcx+19h], 2
0x1800176c7  jb      short loc_1800176E1
0x1800176c9  mov     edx, 1Ah
0x1800176ce  mov     r9d, ebx
0x1800176d1  lea     r8, WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids
0x1800176d8  mov     rcx, [rcx+10h]
0x1800176dc  call    WPP_SF_D
0x1800176e1  mov     [rbp+57h+var_60], 0
0x1800176e5  lea     rax, aAdminWmiEvents_6; "admin\\wmi\\events\\forwarding\\collect"...
0x1800176ec  mov     [rbp+57h+var_58], rax
0x1800176f0  mov     [rbp+57h+var_50], 0
0x1800176f8  mov     [rbp+57h+var_48], 0
0x180017700  mov     [rbp+57h+var_40], ebx
0x180017703  mov     [rbp+57h+var_3C], 0FFFFFFFFh
0x18001770a  mov     [rbp+57h+var_38], 2D2h
0x180017711  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180017718  mov     [rbp+57h+pExceptionObject], rax
0x18001771c  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180017723  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180017727  call    _CxxThrowException_0
0x18001772d  mov     rdx, [rbp+57h+var_B0]; HKEY
0x180017731  lea     rcx, [rbp+57h+var_A0]; this
0x180017735  call    ??0RegistryKeyEnumerator@@QEAA@PEAUHKEY__@@@Z; RegistryKeyEnumerator::RegistryKeyEnumerator(HKEY__ *)
0x18001773a  nop
0x18001773b  jmp     loc_1800177CE
0x180017740  mov     edx, 2001Fh; unsigned int
0x180017745  lea     rcx, [rbp+57h+var_A0]; this
0x180017749  call    ?GetCurrentSubKey@RegistryKeyEnumerator@@QEBAPEAUHKEY__@@K@Z; RegistryKeyEnumerator::GetCurrentSubKey(ulong)
0x18001774e  mov     rbx, rax
0x180017751  mov     [rbp+57h+var_A8], rax
0x180017755  mov     [rbp+57h+var_18], 7
0x18001775d  mov     [rbp+57h+var_20], 0
0x180017765  xor     eax, eax
0x180017767  mov     [rbp+57h+var_30], ax
0x18001776b  lea     r8, [rbp+57h+var_30]
0x18001776f  lea     rdx, aBookmark; "Bookmark"
0x180017776  mov     rcx, rbx
0x180017779  call    ?RegReadStringValue@@YA_NPEAUHKEY__@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegReadStringValue(HKEY__ *,ushort const *,std::wstring &)
0x18001777e  test    al, al
0x180017780  jz      short loc_1800177B6
0x180017782  lea     rdx, word_180026AD8
0x180017789  lea     rcx, [rbp+57h+pExceptionObject]
0x18001778d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180017792  nop
0x180017793  lea     r8, [rbp+57h+pExceptionObject]
0x180017797  lea     rdx, aBookmark; "Bookmark"
0x18001779e  mov     rcx, rbx
0x1800177a1  call    ?RegWriteStringValue@@YAXPEAUHKEY__@@PEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegWriteStringValue(HKEY__ *,ushort const *,std::wstring const &)
0x1800177a6  nop
0x1800177a7  xor     r8d, r8d
0x1800177aa  mov     dl, 1
0x1800177ac  lea     rcx, [rbp+57h+pExceptionObject]
0x1800177b0  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800177b5  nop
0x1800177b6  xor     r8d, r8d
0x1800177b9  mov     dl, 1
0x1800177bb  lea     rcx, [rbp+57h+var_30]
0x1800177bf  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800177c4  nop
0x1800177c5  lea     rcx, [rbp+57h+var_A8]; this
0x1800177c9  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x1800177ce  lea     rcx, [rbp+57h+var_A0]; this
0x1800177d2  call    ?MoveNext@RegistryKeyEnumerator@@QEAAKXZ; RegistryKeyEnumerator::MoveNext(void)
0x1800177d7  test    eax, eax
0x1800177d9  jz      loc_180017740
0x1800177df  lea     rcx, [rbp+57h+var_A0]; this
0x1800177e3  call    ??1RegistryKeyEnumerator@@QEAA@XZ; RegistryKeyEnumerator::~RegistryKeyEnumerator(void)
0x1800177e8  mov     rcx, [rbp+57h+var_10]
0x1800177ec  xor     rcx, rsp; StackCookie
0x1800177ef  call    __security_check_cookie
0x1800177f4  mov     rbx, [rsp+0E0h+arg_8]
0x1800177fc  add     rsp, 0E0h
0x180017803  pop     rbp
0x180017804  retn
```
