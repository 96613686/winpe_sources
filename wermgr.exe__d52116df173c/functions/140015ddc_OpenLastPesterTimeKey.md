# OpenLastPesterTimeKey

- ea: `0x140015ddc`
- end: `0x140015e40`
- name: `OpenLastPesterTimeKey`
- size: `100`
- prototype: `LSTATUS __fastcall(HKEY *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140015f18`
- `0x140016060`

## callees

- `0x14000470c`
- `0x140015ddc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140015e29`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140015e29`

## pseudocode

```c
LSTATUS __fastcall OpenLastPesterTimeKey(HKEY *a1)
{
  HKEY *phkResult; // rax
  LSTATUS result; // eax
  DWORD dwDisposition; // [rsp+68h] [rbp+10h] BYREF

  dwDisposition = 0;
  phkResult = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(a1);
  result = RegCreateKeyExW(
             HKEY_CURRENT_USER,
             L"Software\\Microsoft\\Windows\\Windows Error Reporting",
             0,
             0,
             0,
             0x2001Bu,
             0,
             phkResult,
             &dwDisposition);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140015ddc  sub     rsp, 58h
0x140015de0  mov     [rsp+58h+dwDisposition], 0
0x140015de8  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140015ded  lea     rcx, [rsp+58h+dwDisposition]
0x140015df2  xor     r9d, r9d; lpClass
0x140015df5  mov     [rsp+58h+lpdwDisposition], rcx; lpdwDisposition
0x140015dfa  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\Windows E"...
0x140015e01  mov     [rsp+58h+phkResult], rax; phkResult
0x140015e06  xor     r8d, r8d; Reserved
0x140015e09  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140015e12  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140015e19  mov     [rsp+58h+samDesired], 2001Bh; samDesired
0x140015e21  mov     [rsp+58h+dwOptions], 0; dwOptions
0x140015e29  call    cs:__imp_RegCreateKeyExW
0x140015e2f  test    eax, eax
0x140015e31  jle     short loc_140015E3B
0x140015e33  movzx   eax, ax
0x140015e36  or      eax, 80070000h
0x140015e3b  add     rsp, 58h
0x140015e3f  retn
```
