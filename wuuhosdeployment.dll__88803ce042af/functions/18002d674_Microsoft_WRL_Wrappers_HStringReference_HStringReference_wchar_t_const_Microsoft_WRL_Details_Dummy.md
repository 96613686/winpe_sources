# Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t * const &,Microsoft::WRL::Details::Dummy)

- ea: `0x18002d674`
- end: `0x18002d6e4`
- name: `??$?0PEA_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEA_WUDummy@Details@23@@Z`
- size: `112`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002b5a8`
- `0x18002c66c`
- `0x18003e850`
- `0x18003efd4`
- `0x180041970`
- `0x180041af8`
- `0x180041cb8`
- `0x180041db4`
- `0x180041e98`

## callees

- `0x18002d674`
- `0x18002e000`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002d6ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002d6ae`

## pseudocode

```c
HSTRING_HEADER *__fastcall Microsoft::WRL::Wrappers::HStringReference::HStringReference(
        HSTRING_HEADER *a1,
        const WCHAR **a2,
        unsigned int a3)
{
  HSTRING *v3; // r9
  const WCHAR *v5; // rcx
  unsigned __int64 v6; // rdx
  HRESULT StringReference; // eax
  int v8; // edx
  unsigned int v9; // r8d

  v3 = (HSTRING *)&a1[1];
  a1[1].Reserved.Reserved1 = 0;
  v5 = *a2;
  v6 = -1;
  do
    ++v6;
  while ( v5[v6] );
  if ( v6 > 0xFFFFFFFF )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v6, a3);
    __debugbreak();
  }
  if ( (int)v6 + 1 < (unsigned int)v6 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v6, a3);
    JUMPOUT(0x18002D6E3LL);
  }
  StringReference = WindowsCreateStringReference(v5, v6, a1, v3);
  if ( StringReference < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)StringReference, v8, v9);
    __debugbreak();
  }
  return a1;
}

```

## disassembly

```asm
0x18002d674  mov     [rsp+arg_0], rbx
0x18002d679  push    rdi
0x18002d67a  sub     rsp, 20h
0x18002d67e  lea     r9, [rcx+18h]; string
0x18002d682  xor     edi, edi
0x18002d684  mov     [r9], rdi
0x18002d687  mov     rbx, rcx
0x18002d68a  mov     rcx, [rdx]; sourceString
0x18002d68d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002d691  inc     rdx; int
0x18002d694  cmp     [rcx+rdx*2], di
0x18002d698  jnz     short loc_18002D691
0x18002d69a  mov     eax, 0FFFFFFFFh
0x18002d69f  cmp     rdx, rax
0x18002d6a2  ja      short loc_18002D6CE
0x18002d6a4  lea     eax, [rdx+1]
0x18002d6a7  cmp     eax, edx
0x18002d6a9  jb      short loc_18002D6D9
0x18002d6ab  mov     r8, rbx; hstringHeader
0x18002d6ae  call    cs:__imp_WindowsCreateStringReference
0x18002d6b4  test    eax, eax
0x18002d6b6  js      short loc_18002D6C6
0x18002d6b8  mov     rax, rbx
0x18002d6bb  mov     rbx, [rsp+28h+arg_0]
0x18002d6c0  add     rsp, 20h
0x18002d6c4  pop     rdi
0x18002d6c5  retn
0x18002d6c6  mov     ecx, eax; this
0x18002d6c8  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18002d6cd  int     3; Trap to Debugger
0x18002d6ce  mov     ecx, 80070216h; this
0x18002d6d3  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18002d6d8  int     3; Trap to Debugger
0x18002d6d9  mov     ecx, 80070216h; this
0x18002d6de  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
