# Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)

- ea: `0x18000e310`
- end: `0x18000e380`
- name: `??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z`
- size: `112`
- prototype: `HSTRING_HEADER *__fastcall(HSTRING_HEADER *, const WCHAR **, unsigned int)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d590`
- `0x180011484`
- `0x1800116a0`
- `0x18001e7e4`
- `0x18001e9e8`

## callees

- `0x18000e310`
- `0x18000fd94`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000e34a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000e34a`

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
    JUMPOUT(0x18000E37FLL);
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
0x18000e310  mov     [rsp+arg_0], rbx
0x18000e315  push    rdi
0x18000e316  sub     rsp, 20h
0x18000e31a  lea     r9, [rcx+18h]; string
0x18000e31e  xor     edi, edi
0x18000e320  mov     [r9], rdi
0x18000e323  mov     rbx, rcx
0x18000e326  mov     rcx, [rdx]; sourceString
0x18000e329  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000e32d  inc     rdx; int
0x18000e330  cmp     [rcx+rdx*2], di
0x18000e334  jnz     short loc_18000E32D
0x18000e336  mov     eax, 0FFFFFFFFh
0x18000e33b  cmp     rdx, rax
0x18000e33e  ja      short loc_18000E36A
0x18000e340  lea     eax, [rdx+1]
0x18000e343  cmp     eax, edx
0x18000e345  jb      short loc_18000E375
0x18000e347  mov     r8, rbx; hstringHeader
0x18000e34a  call    cs:__imp_WindowsCreateStringReference
0x18000e350  test    eax, eax
0x18000e352  js      short loc_18000E362
0x18000e354  mov     rax, rbx
0x18000e357  mov     rbx, [rsp+28h+arg_0]
0x18000e35c  add     rsp, 20h
0x18000e360  pop     rdi
0x18000e361  retn
0x18000e362  mov     ecx, eax; this
0x18000e364  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18000e369  int     3; Trap to Debugger
0x18000e36a  mov     ecx, 80070216h; this
0x18000e36f  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18000e374  int     3; Trap to Debugger
0x18000e375  mov     ecx, 80070216h; this
0x18000e37a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
