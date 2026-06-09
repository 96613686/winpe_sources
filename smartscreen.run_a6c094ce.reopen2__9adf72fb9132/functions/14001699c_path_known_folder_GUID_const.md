# path::known_folder(_GUID const &)

- ea: `0x14001699c`
- end: `0x140016a45`
- name: `?known_folder@path@@SA?AV1@AEBU_GUID@@@Z`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x140003ea0`

## callees

- `0x140002830`
- `0x1400055ac`
- `0x14001699c`
- `0x140016ca8`
- `0x140026c20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140016a22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140016a22`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1400169d3`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1400169d3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall path::known_folder(__int64 a1)
{
  HRESULT v2; // eax
  __int64 v3; // rax
  int v5; // [rsp+20h] [rbp-48h]
  _BYTE v6[32]; // [rsp+30h] [rbp-38h] BYREF
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
      v5);
  v3 = std::wstring::wstring(v6, ppszPath);
  path::from_string(a1, v3);
  if ( ppszPath )
    CoTaskMemFree(ppszPath);
  return a1;
}

```

## disassembly

```asm
0x14001699c  push    rbx
0x14001699e  sub     rsp, 60h
0x1400169a2  mov     rax, cs:__security_cookie
0x1400169a9  xor     rax, rsp
0x1400169ac  mov     [rsp+68h+var_10], rax
0x1400169b1  mov     rbx, rcx
0x1400169b4  mov     [rsp+68h+ppszPath], rcx
0x1400169b9  mov     [rsp+68h+ppszPath], 0
0x1400169c2  lea     r9, [rsp+68h+ppszPath]; ppszPath
0x1400169c7  xor     r8d, r8d; hToken
0x1400169ca  xor     edx, edx; dwFlags
0x1400169cc  lea     rcx, FOLDERID_LocalAppData; rfid
0x1400169d3  call    cs:__imp_SHGetKnownFolderPath
0x1400169da  nop     dword ptr [rax+rax+00h]
0x1400169df  mov     rcx, [rsp+68h]; this
0x1400169e4  test    eax, eax
0x1400169e6  jns     short loc_1400169FD
0x1400169e8  mov     r9d, eax; char *
0x1400169eb  lea     r8, aOnecoreAmcoreS_9; "onecore\\amcore\\smartscreen\\src\\clie"...
0x1400169f2  mov     edx, 18Bh; void *
0x1400169f7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400169fd  mov     rdx, [rsp+68h+ppszPath]
0x140016a02  lea     rcx, [rsp+68h+var_38]
0x140016a07  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140016a0c  mov     rdx, rax
0x140016a0f  mov     rcx, rbx
0x140016a12  call    ?from_string@path@@SA?AV1@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; path::from_string(std::wstring)
0x140016a17  nop
0x140016a18  mov     rcx, [rsp+68h+ppszPath]; pv
0x140016a1d  test    rcx, rcx
0x140016a20  jz      short loc_140016A2E
0x140016a22  call    cs:__imp_CoTaskMemFree
0x140016a29  nop     dword ptr [rax+rax+00h]
0x140016a2e  mov     rax, rbx
0x140016a31  mov     rcx, [rsp+68h+var_10]
0x140016a36  xor     rcx, rsp; StackCookie
0x140016a39  call    __security_check_cookie
0x140016a3e  add     rsp, 60h
0x140016a42  pop     rbx
0x140016a43  retn
```
