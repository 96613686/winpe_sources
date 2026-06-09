# IsSecurityChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)

- ea: `0x14001b5b4`
- end: `0x14001b5e2`
- name: `?IsSecurityChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z`
- size: `46`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000750c`
- `0x14000b6d0`
- `0x14001291c`
- `0x140013658`
- `0x1400151ec`
- `0x140015b0c`
- `0x140015cac`
- `0x1400161fc`
- `0x14001aec0`
- `0x1400215a8`
- `0x14002daf0`
- `0x14002dc00`
- `0x14002e0cc`

## callees

- `0x140008b40`
- `0x14001b5b4`

## string_xrefs

- `0x14001b5c7`: `Security`

## pseudocode

```c
bool __fastcall IsSecurityChannel(_QWORD *a1)
{
  return a1[1] == 8
      && !(unsigned int)tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>::compare(*a1, L"Security", 8);
}

```

## disassembly

```asm
0x14001b5b4  sub     rsp, 28h
0x14001b5b8  mov     r8d, 8
0x14001b5be  cmp     [rcx+8], r8
0x14001b5c2  jnz     short loc_14001B5DB
0x14001b5c4  mov     rcx, [rcx]
0x14001b5c7  lea     rdx, aSecurity; "Security"
0x14001b5ce  call    ?compare@?$transform_traits@_WUascii_toupper_transform@tlx@@@tlx@@SAHPEB_W0_K@Z; tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>::compare(wchar_t const *,wchar_t const *,unsigned __int64)
0x14001b5d3  test    eax, eax
0x14001b5d5  jnz     short loc_14001B5DB
0x14001b5d7  mov     al, 1
0x14001b5d9  jmp     short loc_14001B5DD
0x14001b5db  xor     al, al
0x14001b5dd  add     rsp, 28h
0x14001b5e1  retn
```
