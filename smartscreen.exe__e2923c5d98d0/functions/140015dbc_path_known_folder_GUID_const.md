# path::known_folder(_GUID const &)

- ea: `0x140015dbc`
- end: `0x140015e58`
- name: `?known_folder@path@@SA?AV1@AEBU_GUID@@@Z`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x140003cd8`

## callees

- `0x140002734`
- `0x140005260`
- `0x140015dbc`
- `0x1400160b4`
- `0x140025aa0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140015e3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140015e3c`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x140015df3`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x140015df3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall path::known_folder(__int64 a1)
{
  HRESULT v2; // eax
  __int64 v3; // rax
  __int64 v4; // r8
  __int64 v5; // r9
  int v7; // [rsp+20h] [rbp-48h]
  _BYTE v8[32]; // [rsp+30h] [rbp-38h] BYREF
  PWSTR ppszPath; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  ppszPath = 0;
  v2 = SHGetKnownFolderPath(&FOLDERID_LocalAppData, 0, 0, &ppszPath);
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18B,
      (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\helpers\\utilities.h",
      (const char *)(unsigned int)v2,
      v7);
  v3 = std::wstring::wstring(v8, ppszPath);
  path::from_string(a1, v3, v4, v5);
  if ( ppszPath )
    CoTaskMemFree(ppszPath);
  return a1;
}

```

## disassembly

```asm
0x140015dbc  push    rbx
0x140015dbe  sub     rsp, 60h
0x140015dc2  mov     rax, cs:__security_cookie
0x140015dc9  xor     rax, rsp
0x140015dcc  mov     [rsp+68h+var_10], rax
0x140015dd1  mov     rbx, rcx
0x140015dd4  mov     [rsp+68h+ppszPath], rcx
0x140015dd9  mov     [rsp+68h+ppszPath], 0
0x140015de2  lea     r9, [rsp+68h+ppszPath]; ppszPath
0x140015de7  xor     r8d, r8d; hToken
0x140015dea  xor     edx, edx; dwFlags
0x140015dec  lea     rcx, FOLDERID_LocalAppData; rfid
0x140015df3  call    cs:__imp_SHGetKnownFolderPath
0x140015df9  mov     rcx, [rsp+68h]; this
0x140015dfe  test    eax, eax
0x140015e00  jns     short loc_140015E17
0x140015e02  mov     r9d, eax; char *
0x140015e05  lea     r8, aOnecoreAmcoreS_9; "onecore\\amcore\\smartscreen\\src\\clie"...
0x140015e0c  mov     edx, 18Bh; void *
0x140015e11  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140015e17  mov     rdx, [rsp+68h+ppszPath]
0x140015e1c  lea     rcx, [rsp+68h+var_38]
0x140015e21  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140015e26  mov     rdx, rax
0x140015e29  mov     rcx, rbx
0x140015e2c  call    ?from_string@path@@SA?AV1@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; path::from_string(std::wstring)
0x140015e31  nop
0x140015e32  mov     rcx, [rsp+68h+ppszPath]; pv
0x140015e37  test    rcx, rcx
0x140015e3a  jz      short loc_140015E42
0x140015e3c  call    cs:__imp_CoTaskMemFree
0x140015e42  mov     rax, rbx
0x140015e45  mov     rcx, [rsp+68h+var_10]
0x140015e4a  xor     rcx, rsp; StackCookie
0x140015e4d  call    __security_check_cookie
0x140015e52  add     rsp, 60h
0x140015e56  pop     rbx
0x140015e57  retn
```
