# XML_RENDERER::AppendLockToken(ushort const *)

- ea: `0x1800142bc`
- end: `0x18001437f`
- name: `?AppendLockToken@XML_RENDERER@@AEAAJPEBG@Z`
- size: `195`
- prototype: `__int64 __fastcall(XML_RENDERER *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180013bb0`

## callees

- `0x1800142bc`
- `0x18001c550`
- `0x180022520`

## import_xrefs

- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z` at `0x1800142ff`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z` at `0x1800142ff`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x18001433e`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x18001433e`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18001434b`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180014356`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18001434b`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180014356`
- `iisutil!??0STRA@@QEAA@XZ` at `0x1800142e6`
- `iisutil!??0STRA@@QEAA@XZ` at `0x1800142f1`
- `iisutil!??0STRA@@QEAA@XZ` at `0x1800142e6`
- `iisutil!??0STRA@@QEAA@XZ` at `0x1800142f1`

## string_xrefs

- `0x18001430f`: `<D:locktoken>%s<D:href>%s</D:href>%s</D:locktoken>%s`

## pseudocode

```c
__int64 __fastcall XML_RENDERER::AppendLockToken(const char **this, const unsigned __int16 *a2)
{
  int v4; // ebx
  _BYTE v6[32]; // [rsp+30h] [rbp-88h] BYREF
  const char *v7; // [rsp+50h] [rbp-68h]
  _BYTE v8[56]; // [rsp+68h] [rbp-50h] BYREF

  STRA::STRA((STRA *)v8);
  STRA::STRA((STRA *)v6);
  v4 = STRA::CopyWToUTF8Unescaped((STRA *)v6, a2);
  if ( v4 >= 0 )
  {
    v4 = SAFE_snprintf(
           (struct STRA *)v8,
           "<D:locktoken>%s<D:href>%s</D:href>%s</D:locktoken>%s",
           this[1],
           v7,
           this[1],
           this[1]);
    if ( v4 >= 0 )
      v4 = STRA::Append((STRA *)(this + 3), (const struct STRA *)v8);
  }
  STRA::~STRA((STRA *)v6);
  STRA::~STRA((STRA *)v8);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800142bc  mov     [rsp+arg_10], rbx
0x1800142c1  push    rdi
0x1800142c2  sub     rsp, 0B0h
0x1800142c9  mov     rax, cs:__security_cookie
0x1800142d0  xor     rax, rsp
0x1800142d3  mov     [rsp+0B8h+var_18], rax
0x1800142db  mov     rdi, rcx
0x1800142de  mov     rbx, rdx
0x1800142e1  lea     rcx, [rsp+0B8h+var_50]
0x1800142e6  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x1800142ec  lea     rcx, [rsp+0B8h+var_88]
0x1800142f1  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x1800142f7  mov     rdx, rbx
0x1800142fa  lea     rcx, [rsp+0B8h+var_88]
0x1800142ff  call    cs:__imp_?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z; STRA::CopyWToUTF8Unescaped(ushort const *)
0x180014305  mov     ebx, eax
0x180014307  test    eax, eax
0x180014309  js      short loc_180014346
0x18001430b  mov     r8, [rdi+8]
0x18001430f  lea     rdx, aDLocktokenSDHr; "<D:locktoken>%s<D:href>%s</D:href>%s</D"...
0x180014316  mov     r9, [rsp+0B8h+var_68]
0x18001431b  lea     rcx, [rsp+0B8h+var_50]; struct STRA *
0x180014320  mov     [rsp+0B8h+var_90], r8
0x180014325  mov     [rsp+0B8h+var_98], r8
0x18001432a  call    ?SAFE_snprintf@@YAJPEAVSTRA@@PEBDZZ; SAFE_snprintf(STRA *,char const *,...)
0x18001432f  mov     ebx, eax
0x180014331  test    eax, eax
0x180014333  js      short loc_180014346
0x180014335  lea     rcx, [rdi+18h]
0x180014339  lea     rdx, [rsp+0B8h+var_50]
0x18001433e  call    cs:__imp_?Append@STRA@@QEAAJAEBV1@@Z; STRA::Append(STRA const &)
0x180014344  mov     ebx, eax
0x180014346  lea     rcx, [rsp+0B8h+var_88]
0x18001434b  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180014351  lea     rcx, [rsp+0B8h+var_50]
0x180014356  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18001435c  mov     eax, ebx
0x18001435e  mov     rcx, [rsp+0B8h+var_18]
0x180014366  xor     rcx, rsp; StackCookie
0x180014369  call    __security_check_cookie
0x18001436e  mov     rbx, [rsp+0B8h+arg_10]
0x180014376  add     rsp, 0B0h
0x18001437d  pop     rdi
0x18001437e  retn
```
