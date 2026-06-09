# CspCacheDeleteFileProc(void *,ushort *,ulong)

- ea: `0x18002f440`
- end: `0x18002f4de`
- name: `?CspCacheDeleteFileProc@@YAKPEAXPEAGK@Z`
- size: `158`
- prototype: `unsigned int __fastcall(void *, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x180009e82`
- `0x18002cda8`
- `0x1800308f4`
- `0x18003c240`

## string_xrefs

- `0x18002f477`: `Cached_CardmodFile`

## pseudocode

```c
__int64 __fastcall CspCacheDeleteFileProc(void *a1, unsigned __int16 *a2)
{
  void *v5; // [rsp+30h] [rbp-258h] BYREF
  int v6; // [rsp+38h] [rbp-250h]
  int v7; // [rsp+3Ch] [rbp-24Ch]
  int v8; // [rsp+40h] [rbp-248h]
  unsigned __int16 v9[278]; // [rsp+44h] [rbp-244h] BYREF

  memset_0(&v5, 0, 0x238u);
  StringCbPrintfW(v9, 0x104u, L"%s\\%s", L"Cached_CardmodFile", a2);
  v6 = 7;
  v8 = 1;
  v7 = 1;
  v5 = a1;
  return MyCacheDeleteItem(&v5);
}

```

## disassembly

```asm
0x18002f440  mov     [rsp+arg_0], rbx
0x18002f445  push    rdi
0x18002f446  sub     rsp, 280h
0x18002f44d  mov     rax, cs:__security_cookie
0x18002f454  xor     rax, rsp
0x18002f457  mov     [rsp+288h+var_18], rax
0x18002f45f  mov     rbx, rdx
0x18002f462  mov     rdi, rcx
0x18002f465  xor     edx, edx; Val
0x18002f467  lea     rcx, [rsp+288h+var_258]; void *
0x18002f46c  mov     r8d, 238h; Size
0x18002f472  call    memset_0
0x18002f477  lea     r9, aCachedCardmodf; "Cached_CardmodFile"
0x18002f47e  mov     [rsp+288h+var_268], rbx
0x18002f483  lea     r8, aSS; "%s\\%s"
0x18002f48a  mov     edx, 104h; unsigned __int64
0x18002f48f  lea     rcx, [rsp+288h+var_244]; unsigned __int16 *
0x18002f494  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002f499  mov     eax, 1
0x18002f49e  mov     [rsp+288h+var_250], 7
0x18002f4a6  lea     rcx, [rsp+288h+var_258]
0x18002f4ab  mov     [rsp+288h+var_248], eax
0x18002f4af  mov     [rsp+288h+var_24C], eax
0x18002f4b3  mov     [rsp+288h+var_258], rdi
0x18002f4b8  call    MyCacheDeleteItem
0x18002f4bd  mov     rcx, [rsp+288h+var_18]
0x18002f4c5  xor     rcx, rsp; StackCookie
0x18002f4c8  call    __security_check_cookie
0x18002f4cd  mov     rbx, [rsp+288h+arg_0]
0x18002f4d5  add     rsp, 280h
0x18002f4dc  pop     rdi
0x18002f4dd  retn
```
