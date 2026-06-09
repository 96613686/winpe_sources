# CWlanProfileStore::GetLogoLocation(CProfile const &)

- ea: `0x18002a7a0`
- end: `0x18002a7df`
- name: `?GetLogoLocation@CWlanProfileStore@@UEBA?AVCString@WTL@@AEBVCProfile@@@Z`
- size: `63`
- prototype: `struct WTL::CString __high(const struct CProfile *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000cf1c`
- `0x18002a7a0`

## string_xrefs

- `0x18002a7ba`: `wlanpref.dll,2`
- `0x18002a7c7`: `wlanpref.dll,1`

## pseudocode

```c
WTL::CString *__fastcall CWlanProfileStore::GetLogoLocation(__int64 a1, WTL::CString *a2, __int64 a3)
{
  const unsigned __int16 *v4; // rdx

  if ( *(_BYTE *)(a3 + 80) )
  {
    v4 = &word_180034F94;
  }
  else
  {
    v4 = L"wlanpref.dll,2";
    if ( !*(_BYTE *)(a3 + 82) )
      v4 = L"wlanpref.dll,1";
  }
  WTL::CString::CString(a2, v4);
  return a2;
}

```

## disassembly

```asm
0x18002a7a0  push    rbx
0x18002a7a2  sub     rsp, 30h
0x18002a7a6  xor     eax, eax
0x18002a7a8  mov     rbx, rdx
0x18002a7ab  cmp     [r8+50h], al
0x18002a7af  jz      short loc_18002A7BA
0x18002a7b1  lea     rdx, word_180034F94
0x18002a7b8  jmp     short loc_18002A7CE
0x18002a7ba  lea     rdx, aWlanprefDll2; "wlanpref.dll,2"
0x18002a7c1  cmp     [r8+52h], al
0x18002a7c5  jnz     short loc_18002A7CE
0x18002a7c7  lea     rdx, aWlanprefDll1; "wlanpref.dll,1"
0x18002a7ce  mov     rcx, rbx; this
0x18002a7d1  call    ??0CString@WTL@@QEAA@PEBG@Z; WTL::CString::CString(ushort const *)
0x18002a7d6  mov     rax, rbx
0x18002a7d9  add     rsp, 30h
0x18002a7dd  pop     rbx
0x18002a7de  retn
```
