# StripInvalidPathCharsFromString(ushort const *,ushort *,unsigned __int64)

- ea: `0x180031c30`
- end: `0x180031cc8`
- name: `?StripInvalidPathCharsFromString@@YAJPEBGPEAG_K@Z`
- size: `152`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180021128`
- `0x180033560`

## callees

- `0x180002db0`
- `0x18001b3a0`
- `0x180031c30`
- `0x18003fc30`

## import_xrefs

- `msvcrt!wcstok_s` at `0x180031c9a`
- `msvcrt!wcstok_s` at `0x180031c9a`

## pseudocode

```c
__int64 __fastcall StripInvalidPathCharsFromString(unsigned __int16 *a1, unsigned __int16 *a2)
{
  int v3; // ebx
  unsigned __int16 *i; // rcx
  wchar_t *v5; // rax
  unsigned __int64 v6; // rdx
  wchar_t *Context; // [rsp+20h] [rbp-238h] BYREF
  unsigned __int16 v9[264]; // [rsp+30h] [rbp-228h] BYREF

  *a2 = 0;
  Context = 0;
  v3 = StringCchCopyW(v9, 0x104u, a1);
  if ( v3 >= 0 )
  {
    for ( i = v9; ; i = 0 )
    {
      v5 = wcstok_s(i, L"\\/:*?#\"<>|", &Context);
      if ( !v5 )
        break;
      v3 = StringCchCatW(a2, v6, v5);
      if ( v3 < 0 )
        break;
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180031c30  mov     [rsp+arg_10], rbx
0x180031c35  push    rdi
0x180031c36  sub     rsp, 250h
0x180031c3d  mov     rax, cs:__security_cookie
0x180031c44  xor     rax, rsp
0x180031c47  mov     [rsp+258h+var_18], rax
0x180031c4f  xor     eax, eax
0x180031c51  mov     rdi, rdx
0x180031c54  mov     [rdx], ax
0x180031c57  mov     r8, rcx; unsigned __int16 *
0x180031c5a  mov     edx, 104h; unsigned __int64
0x180031c5f  mov     [rsp+258h+Context], rax
0x180031c64  lea     rcx, [rsp+258h+var_228]; unsigned __int16 *
0x180031c69  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180031c6e  mov     ebx, eax
0x180031c70  test    eax, eax
0x180031c72  js      short loc_180031CA5
0x180031c74  lea     rcx, [rsp+258h+var_228]
0x180031c79  jmp     short loc_180031C8E
0x180031c7b  mov     r8, rax; unsigned __int16 *
0x180031c7e  mov     rcx, rdi; unsigned __int16 *
0x180031c81  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180031c86  mov     ebx, eax
0x180031c88  test    eax, eax
0x180031c8a  js      short loc_180031CA5
0x180031c8c  xor     ecx, ecx; String
0x180031c8e  lea     r8, [rsp+258h+Context]; Context
0x180031c93  lea     rdx, Delimiter; "\\/:*?#\"<>|"
0x180031c9a  call    cs:__imp_wcstok_s
0x180031ca0  test    rax, rax
0x180031ca3  jnz     short loc_180031C7B
0x180031ca5  mov     eax, ebx
0x180031ca7  mov     rcx, [rsp+258h+var_18]
0x180031caf  xor     rcx, rsp; StackCookie
0x180031cb2  call    __security_check_cookie
0x180031cb7  mov     rbx, [rsp+258h+arg_10]
0x180031cbf  add     rsp, 250h
0x180031cc6  pop     rdi
0x180031cc7  retn
```
