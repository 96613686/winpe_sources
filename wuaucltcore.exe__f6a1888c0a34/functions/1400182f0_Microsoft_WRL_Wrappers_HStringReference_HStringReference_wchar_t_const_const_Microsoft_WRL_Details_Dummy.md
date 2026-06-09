# Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)

- ea: `0x1400182f0`
- end: `0x140018360`
- name: `??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z`
- size: `112`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400151b8`
- `0x14001593c`
- `0x1400183a0`
- `0x140018528`
- `0x1400186e8`
- `0x1400187e4`
- `0x1400188c8`

## callees

- `0x1400182d8`
- `0x1400182f0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14001832a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14001832a`

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
    JUMPOUT(0x14001835FLL);
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
0x1400182f0  mov     [rsp+arg_0], rbx
0x1400182f5  push    rdi
0x1400182f6  sub     rsp, 20h
0x1400182fa  lea     r9, [rcx+18h]; string
0x1400182fe  xor     edi, edi
0x140018300  mov     [r9], rdi
0x140018303  mov     rbx, rcx
0x140018306  mov     rcx, [rdx]; sourceString
0x140018309  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14001830d  inc     rdx; int
0x140018310  cmp     [rcx+rdx*2], di
0x140018314  jnz     short loc_14001830D
0x140018316  mov     eax, 0FFFFFFFFh
0x14001831b  cmp     rdx, rax
0x14001831e  ja      short loc_14001834A
0x140018320  lea     eax, [rdx+1]
0x140018323  cmp     eax, edx
0x140018325  jb      short loc_140018355
0x140018327  mov     r8, rbx; hstringHeader
0x14001832a  call    cs:__imp_WindowsCreateStringReference
0x140018330  test    eax, eax
0x140018332  js      short loc_140018342
0x140018334  mov     rax, rbx
0x140018337  mov     rbx, [rsp+28h+arg_0]
0x14001833c  add     rsp, 20h
0x140018340  pop     rdi
0x140018341  retn
0x140018342  mov     ecx, eax; this
0x140018344  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x140018349  int     3; Trap to Debugger
0x14001834a  mov     ecx, 80070216h; this
0x14001834f  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x140018354  int     3; Trap to Debugger
0x140018355  mov     ecx, 80070216h; this
0x14001835a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
