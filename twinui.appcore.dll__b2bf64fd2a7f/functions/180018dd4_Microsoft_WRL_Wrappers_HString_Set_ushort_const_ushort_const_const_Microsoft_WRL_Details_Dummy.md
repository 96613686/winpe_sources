# Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)

- ea: `0x180018dd4`
- end: `0x180018e4b`
- name: `??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z`
- size: `119`
- prototype: `__int64 __fastcall(Microsoft::WRL::Wrappers::HString *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002479c`
- `0x18006e1d0`

## callees

- `0x180016c98`
- `0x180018dd4`
- `0x180024014`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018e25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018e25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180018e3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180018e3a`

## pseudocode

```c
HRESULT __fastcall Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(
        Microsoft::WRL::Wrappers::HString *this,
        __int64 *a2,
        char a3)
{
  __int64 v3; // r9
  unsigned __int64 v5; // rcx
  HRESULT result; // eax
  const unsigned __int16 *v7; // r9
  unsigned int v8; // [rsp+40h] [rbp+18h] BYREF

  LOBYTE(v8) = a3;
  v3 = *a2;
  if ( *a2 )
  {
    v8 = 0;
    v5 = -1;
    do
      ++v5;
    while ( *(_WORD *)(v3 + 2 * v5) );
    result = ULongLongToUInt(v5, &v8);
    if ( result >= 0 )
      return Microsoft::WRL::Wrappers::HString::Set(this, v7, v8);
  }
  else
  {
    WindowsDeleteString(*(HSTRING *)this);
    *(_QWORD *)this = 0;
    return WindowsCreateString(&pszDefault, 0, (HSTRING *)this);
  }
  return result;
}

```

## disassembly

```asm
0x180018dd4  mov     [rsp+arg_0], rbx
0x180018dd9  mov     byte ptr [rsp+arg_10], r8b
0x180018dde  push    rdi
0x180018ddf  sub     rsp, 20h
0x180018de3  mov     r9, [rdx]
0x180018de6  xor     edi, edi
0x180018de8  mov     rbx, rcx
0x180018deb  test    r9, r9
0x180018dee  jz      short loc_180018E22
0x180018df0  mov     [rsp+28h+arg_10], edi
0x180018df4  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180018df8  inc     rcx; unsigned __int64
0x180018dfb  cmp     [r9+rcx*2], di
0x180018e00  jnz     short loc_180018DF8
0x180018e02  lea     rdx, [rsp+28h+arg_10]; unsigned int *
0x180018e07  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180018e0c  test    eax, eax
0x180018e0e  js      short loc_180018E40
0x180018e10  mov     r8d, [rsp+28h+arg_10]; unsigned int
0x180018e15  mov     rdx, r9; unsigned __int16 *
0x180018e18  mov     rcx, rbx; this
0x180018e1b  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180018e20  jmp     short loc_180018E40
0x180018e22  mov     rcx, [rcx]; string
0x180018e25  call    cs:__imp_WindowsDeleteString
0x180018e2b  mov     r8, rbx; string
0x180018e2e  mov     [rbx], rdi
0x180018e31  xor     edx, edx; length
0x180018e33  lea     rcx, pszDefault; sourceString
0x180018e3a  call    cs:__imp_WindowsCreateString
0x180018e40  mov     rbx, [rsp+28h+arg_0]
0x180018e45  add     rsp, 20h
0x180018e49  pop     rdi
0x180018e4a  retn
```
