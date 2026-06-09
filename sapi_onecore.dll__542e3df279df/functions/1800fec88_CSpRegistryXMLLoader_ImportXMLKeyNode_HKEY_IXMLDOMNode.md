# CSpRegistryXMLLoader::ImportXMLKeyNode(HKEY__ *,IXMLDOMNode *)

- ea: `0x1800fec88`
- end: `0x1800fedef`
- name: `?ImportXMLKeyNode@CSpRegistryXMLLoader@@AEAAJPEAUHKEY__@@PEAUIXMLDOMNode@@@Z`
- size: `359`
- prototype: `__int64 __fastcall(CSpRegistryXMLLoader *__hidden this, HKEY hKey, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800171c0`

## callees

- `0x1800171c0`
- `0x1800177e0`
- `0x1800fec88`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800fed61`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800fed61`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fed9a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fedd2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fed9a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fedd2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800fed1b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800fed1b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fedc7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fedc7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800fed85`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800fed85`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSpRegistryXMLLoader::ImportXMLKeyNode(
        CSpRegistryXMLLoader *this,
        HKEY hKey,
        struct IXMLDOMNode *a3)
{
  signed int NamedAttributeTextFromNode; // ebx
  const WCHAR *v7; // rdx
  LSTATUS v8; // eax
  CSpRegistryXMLLoader *v9; // rcx
  int v10; // eax
  LSTATUS v11; // eax
  LPCWSTR lpSubKey; // [rsp+50h] [rbp-10h] BYREF
  wchar_t *Source; // [rsp+90h] [rbp+30h] BYREF
  HKEY hKeya; // [rsp+98h] [rbp+38h] BYREF

  NamedAttributeTextFromNode = -2147024809;
  if ( a3 )
    NamedAttributeTextFromNode = 0;
  v7 = 0;
  lpSubKey = 0;
  if ( a3 )
  {
    NamedAttributeTextFromNode = CSpRegistryXMLLoader::GetNamedAttributeTextFromNode(
                                   this,
                                   a3,
                                   L"name",
                                   (unsigned __int16 **)&lpSubKey);
    v7 = lpSubKey;
  }
  hKeya = 0;
  if ( NamedAttributeTextFromNode >= 0 )
  {
    v8 = RegCreateKeyExW(hKey, v7, 0, 0, 0, 0xF003Fu, 0, &hKeya, 0);
    NamedAttributeTextFromNode = v8;
    if ( v8 > 0 )
      NamedAttributeTextFromNode = (unsigned __int16)v8 | 0x80070000;
    if ( NamedAttributeTextFromNode >= 0 )
    {
      Source = 0;
      if ( CSpRegistryXMLLoader::GetNamedAttributeTextFromNode(v9, a3, L"defaultValue", &Source) >= 0 )
      {
        v10 = wcsnlen(Source, 0x104u);
        v11 = RegSetValueExW(hKeya, 0, 0, 1u, (const BYTE *)Source, 2 * v10);
        NamedAttributeTextFromNode = v11;
        if ( v11 > 0 )
          NamedAttributeTextFromNode = (unsigned __int16)v11 | 0x80070000;
      }
      SysFreeString(Source);
      if ( NamedAttributeTextFromNode >= 0 )
        NamedAttributeTextFromNode = CSpRegistryXMLLoader::ImportXMLTokenChildren(this, hKeya, a3, 1, 0);
    }
  }
  RegCloseKey(hKeya);
  SysFreeString((BSTR)lpSubKey);
  return (unsigned int)NamedAttributeTextFromNode;
}

```

## disassembly

```asm
0x1800fec88  mov     [rsp-18h+arg_0], rbx
0x1800fec8d  mov     [rsp-18h+arg_8], rsi
0x1800fec92  push    rbp
0x1800fec93  push    rdi
0x1800fec94  push    r14
0x1800fec96  mov     rbp, rsp
0x1800fec99  sub     rsp, 60h
0x1800fec9d  mov     rdi, r8
0x1800feca0  mov     rsi, rdx
0x1800feca3  mov     r14, rcx
0x1800feca6  mov     ebx, 80070057h
0x1800fecab  xor     eax, eax
0x1800fecad  test    r8, r8
0x1800fecb0  cmovnz  ebx, eax
0x1800fecb3  xor     edx, edx
0x1800fecb5  mov     [rbp+lpSubKey], rdx
0x1800fecb9  test    r8, r8
0x1800fecbc  jz      short loc_1800FECD7
0x1800fecbe  lea     r9, [rbp+lpSubKey]; unsigned __int16 **
0x1800fecc2  lea     r8, psz; "name"
0x1800fecc9  mov     rdx, rdi; struct IXMLDOMNode *
0x1800feccc  call    ?GetNamedAttributeTextFromNode@CSpRegistryXMLLoader@@AEAAJPEAUIXMLDOMNode@@PEBGPEAPEAG@Z; CSpRegistryXMLLoader::GetNamedAttributeTextFromNode(IXMLDOMNode *,ushort const *,ushort * *)
0x1800fecd1  mov     ebx, eax
0x1800fecd3  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x1800fecd7  mov     [rbp+hKey], 0
0x1800fecdf  test    ebx, ebx
0x1800fece1  js      loc_1800FEDC3
0x1800fece7  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x1800fecf0  lea     rax, [rbp+hKey]
0x1800fecf4  mov     [rsp+60h+phkResult], rax; phkResult
0x1800fecf9  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800fed02  mov     [rsp+60h+samDesired], 0F003Fh; samDesired
0x1800fed0a  mov     [rsp+60h+dwOptions], 0; dwOptions
0x1800fed12  xor     r9d, r9d; lpClass
0x1800fed15  xor     r8d, r8d; Reserved
0x1800fed18  mov     rcx, rsi; hKey
0x1800fed1b  call    cs:__imp_RegCreateKeyExW
0x1800fed21  mov     ebx, eax
0x1800fed23  mov     esi, 80070000h
0x1800fed28  test    eax, eax
0x1800fed2a  jle     short loc_1800FED31
0x1800fed2c  movzx   ebx, ax
0x1800fed2f  or      ebx, esi
0x1800fed31  test    ebx, ebx
0x1800fed33  js      loc_1800FEDC3
0x1800fed39  mov     [rbp+Source], 0
0x1800fed41  lea     r9, [rbp+Source]; unsigned __int16 **
0x1800fed45  lea     r8, aDefaultvalue; "defaultValue"
0x1800fed4c  mov     rdx, rdi; struct IXMLDOMNode *
0x1800fed4f  call    ?GetNamedAttributeTextFromNode@CSpRegistryXMLLoader@@AEAAJPEAUIXMLDOMNode@@PEBGPEAPEAG@Z; CSpRegistryXMLLoader::GetNamedAttributeTextFromNode(IXMLDOMNode *,ushort const *,ushort * *)
0x1800fed54  test    eax, eax
0x1800fed56  js      short loc_1800FED96
0x1800fed58  mov     edx, 104h; MaxCount
0x1800fed5d  mov     rcx, [rbp+Source]; Source
0x1800fed61  call    cs:__imp_wcsnlen
0x1800fed67  add     eax, eax
0x1800fed69  mov     rdx, [rbp+Source]
0x1800fed6d  mov     [rsp+60h+samDesired], eax; cbData
0x1800fed71  mov     qword ptr [rsp+60h+dwOptions], rdx; lpData
0x1800fed76  mov     r9d, 1; dwType
0x1800fed7c  xor     r8d, r8d; Reserved
0x1800fed7f  xor     edx, edx; lpValueName
0x1800fed81  mov     rcx, [rbp+hKey]; hKey
0x1800fed85  call    cs:__imp_RegSetValueExW
0x1800fed8b  mov     ebx, eax
0x1800fed8d  test    eax, eax
0x1800fed8f  jle     short loc_1800FED96
0x1800fed91  movzx   ebx, ax
0x1800fed94  or      ebx, esi
0x1800fed96  mov     rcx, [rbp+Source]; bstrString
0x1800fed9a  call    cs:__imp_SysFreeString
0x1800feda0  test    ebx, ebx
0x1800feda2  js      short loc_1800FEDC3
0x1800feda4  mov     [rsp+60h+dwOptions], 0; int
0x1800fedac  mov     r9d, 1; int
0x1800fedb2  mov     r8, rdi; struct IXMLDOMNode *
0x1800fedb5  mov     rdx, [rbp+hKey]; HKEY
0x1800fedb9  mov     rcx, r14; this
0x1800fedbc  call    ?ImportXMLTokenChildren@CSpRegistryXMLLoader@@AEAAJPEAUHKEY__@@PEAUIXMLDOMNode@@HH@Z; CSpRegistryXMLLoader::ImportXMLTokenChildren(HKEY__ *,IXMLDOMNode *,int,int)
0x1800fedc1  mov     ebx, eax
0x1800fedc3  mov     rcx, [rbp+hKey]; hKey
0x1800fedc7  call    cs:__imp_RegCloseKey
0x1800fedcd  nop
0x1800fedce  mov     rcx, [rbp+lpSubKey]; bstrString
0x1800fedd2  call    cs:__imp_SysFreeString
0x1800fedd8  mov     eax, ebx
0x1800fedda  lea     r11, [rsp+60h+var_s0]
0x1800feddf  mov     rbx, [r11+20h]
0x1800fede3  mov     rsi, [r11+28h]
0x1800fede7  mov     rsp, r11
0x1800fedea  pop     r14
0x1800fedec  pop     rdi
0x1800feded  pop     rbp
0x1800fedee  retn
```
