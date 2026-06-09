# _anonymous_namespace_::IsSupportedAT

- ea: `0x140020ea8`
- end: `0x140020f7c`
- name: `_anonymous_namespace_::IsSupportedAT`
- size: `212`
- prototype: `__int64 __fastcall(wchar_t *Str)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140022b10`

## callees

- `0x140020ea8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x140020eb8`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x140020ed7`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x140020ef6`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x140020f11`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x140020f2c`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x140020f47`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x140020f62`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x140020eb8`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x140020ed7`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x140020ef6`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x140020f11`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x140020f2c`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x140020f47`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x140020f62`

## string_xrefs

- `0x140020f58`: `voiceaccess`

## pseudocode

```c
char __fastcall anonymous_namespace_::IsSupportedAT(wchar_t *Str)
{
  wchar_t *v2; // rax

  if ( wcsstr(Str, L"narrator")
    || wcsstr(Str, L"magnifierpane")
    || wcsstr(Str, L"osk")
    || wcsstr(Str, L"stickykeys")
    || wcsstr(Str, L"filterkeys")
    || wcsstr(Str, L"highcontrast")
    || (v2 = wcsstr(Str, L"voiceaccess")) != 0 )
  {
    LOBYTE(v2) = 1;
  }
  return (char)v2;
}

```

## disassembly

```asm
0x140020ea8  push    rbx
0x140020eaa  sub     rsp, 20h
0x140020eae  lea     rdx, aNarrator_1; "narrator"
0x140020eb5  mov     rbx, rcx
0x140020eb8  call    cs:__imp_wcsstr
0x140020ebf  nop     dword ptr [rax+rax+00h]
0x140020ec4  test    rax, rax
0x140020ec7  jnz     loc_140020F73
0x140020ecd  lea     rdx, aMagnifierpane_1; "magnifierpane"
0x140020ed4  mov     rcx, rbx; Str
0x140020ed7  call    cs:__imp_wcsstr
0x140020ede  nop     dword ptr [rax+rax+00h]
0x140020ee3  test    rax, rax
0x140020ee6  jnz     loc_140020F73
0x140020eec  lea     rdx, aOsk_1; "osk"
0x140020ef3  mov     rcx, rbx; Str
0x140020ef6  call    cs:__imp_wcsstr
0x140020efd  nop     dword ptr [rax+rax+00h]
0x140020f02  test    rax, rax
0x140020f05  jnz     short loc_140020F73
0x140020f07  lea     rdx, aStickykeys_0; "stickykeys"
0x140020f0e  mov     rcx, rbx; Str
0x140020f11  call    cs:__imp_wcsstr
0x140020f18  nop     dword ptr [rax+rax+00h]
0x140020f1d  test    rax, rax
0x140020f20  jnz     short loc_140020F73
0x140020f22  lea     rdx, aFilterkeys_0; "filterkeys"
0x140020f29  mov     rcx, rbx; Str
0x140020f2c  call    cs:__imp_wcsstr
0x140020f33  nop     dword ptr [rax+rax+00h]
0x140020f38  test    rax, rax
0x140020f3b  jnz     short loc_140020F73
0x140020f3d  lea     rdx, aHighcontrast_0; "highcontrast"
0x140020f44  mov     rcx, rbx; Str
0x140020f47  call    cs:__imp_wcsstr
0x140020f4e  nop     dword ptr [rax+rax+00h]
0x140020f53  test    rax, rax
0x140020f56  jnz     short loc_140020F73
0x140020f58  lea     rdx, aVoiceaccess; "voiceaccess"
0x140020f5f  mov     rcx, rbx; Str
0x140020f62  call    cs:__imp_wcsstr
0x140020f69  nop     dword ptr [rax+rax+00h]
0x140020f6e  test    rax, rax
0x140020f71  jz      short loc_140020F75
0x140020f73  mov     al, 1
0x140020f75  add     rsp, 20h
0x140020f79  pop     rbx
0x140020f7a  retn
```
