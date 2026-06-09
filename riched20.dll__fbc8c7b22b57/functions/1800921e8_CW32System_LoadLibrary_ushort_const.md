# CW32System::LoadLibrary(ushort const *)

- ea: `0x1800921e8`
- end: `0x180092262`
- name: `?LoadLibrary@CW32System@@SAPEAUHINSTANCE__@@PEBG@Z`
- size: `122`
- prototype: `HINSTANCE __fastcall(const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18005decc`
- `0x180092fb0`
- `0x1800931b0`

## callees

- `0x18008f3e4`
- `0x1800903d4`
- `0x1800921e8`
- `0x180093c00`

## import_xrefs

- `KERNEL32!LoadLibraryA` at `0x18009222c`
- `KERNEL32!LoadLibraryA` at `0x18009222c`
- `KERNEL32!LoadLibraryW` at `0x18009220c`
- `KERNEL32!LoadLibraryW` at `0x18009220c`

## pseudocode

```c
HINSTANCE __fastcall CW32System::LoadLibrary(const unsigned __int16 *a1, __int64 a2, unsigned int a3)
{
  HMODULE LibraryA; // rbx
  LPCSTR lpLibFileName[68]; // [rsp+20h] [rbp-238h] BYREF

  if ( CW32System::_dwPlatformId != 1 )
    return LoadLibraryW(a1);
  CStrIn::CStrIn((CStrIn *)lpLibFileName, a1, a3);
  LibraryA = LoadLibraryA(lpLibFileName[0]);
  CConvertStr::Free((CConvertStr *)lpLibFileName);
  return LibraryA;
}

```

## disassembly

```asm
0x1800921e8  push    rbx
0x1800921ea  sub     rsp, 250h
0x1800921f1  mov     rax, cs:__security_cookie
0x1800921f8  xor     rax, rsp
0x1800921fb  mov     [rsp+258h+var_18], rax
0x180092203  cmp     cs:?_dwPlatformId@CW32System@@0KA, 1; ulong CW32System::_dwPlatformId
0x18009220a  jz      short loc_18009221A
0x18009220c  call    cs:__imp_LoadLibraryW
0x180092213  nop     dword ptr [rax+rax+00h]
0x180092218  jmp     short loc_180092248
0x18009221a  mov     rdx, rcx; unsigned __int16 *
0x18009221d  lea     rcx, [rsp+258h+lpLibFileName]; this
0x180092222  call    ??0CStrIn@@QEAA@PEBGI@Z; CStrIn::CStrIn(ushort const *,uint)
0x180092227  mov     rcx, [rsp+258h+lpLibFileName]; lpLibFileName
0x18009222c  call    cs:__imp_LoadLibraryA
0x180092233  nop     dword ptr [rax+rax+00h]
0x180092238  lea     rcx, [rsp+258h+lpLibFileName]; this
0x18009223d  mov     rbx, rax
0x180092240  call    ?Free@CConvertStr@@IEAAXXZ; CConvertStr::Free(void)
0x180092245  mov     rax, rbx
0x180092248  mov     rcx, [rsp+258h+var_18]
0x180092250  xor     rcx, rsp; StackCookie
0x180092253  call    __security_check_cookie
0x180092258  add     rsp, 250h
0x18009225f  pop     rbx
0x180092260  retn
```
