# XML_RENDERER::OpenOrCloseXmlTag(char const *,int)

- ea: `0x180014ef4`
- end: `0x180014f9a`
- name: `?OpenOrCloseXmlTag@XML_RENDERER@@AEAAJPEBDH@Z`
- size: `166`
- prototype: `__int64 __fastcall(XML_RENDERER *__hidden this, const char *, int)`
- caller_count: `10`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180013bb0`
- `0x180014388`
- `0x1800145a8`
- `0x180014ae8`
- `0x180014fa0`
- `0x1800153ac`
- `0x180015430`
- `0x1800155d4`
- `0x180015790`
- `0x1800158a8`

## callees

- `0x180014ef4`
- `0x18001c550`
- `0x180022520`

## import_xrefs

- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x180014f66`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x180014f66`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180014f73`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180014f73`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180014f20`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180014f20`

## pseudocode

```c
__int64 __fastcall XML_RENDERER::OpenOrCloseXmlTag(const char **this, const char *a2, int a3)
{
  const char *v6; // r8
  int v7; // ebx
  _BYTE v9[56]; // [rsp+30h] [rbp-48h] BYREF

  STRA::STRA((STRA *)v9);
  v6 = "/";
  if ( !a3 )
    v6 = (const char *)&word_1800263B2;
  v7 = SAFE_snprintf((struct STRA *)v9, "<%sD:%s>%s", v6, a2, this[1]);
  if ( v7 >= 0 )
    v7 = STRA::Append((STRA *)(this + 3), (const struct STRA *)v9);
  STRA::~STRA((STRA *)v9);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180014ef4  mov     [rsp+arg_10], rbx
0x180014ef9  mov     [rsp+arg_18], rsi
0x180014efe  push    rdi
0x180014eff  sub     rsp, 70h
0x180014f03  mov     rax, cs:__security_cookie
0x180014f0a  xor     rax, rsp
0x180014f0d  mov     [rsp+78h+var_10], rax
0x180014f12  mov     rsi, rcx
0x180014f15  mov     ebx, r8d
0x180014f18  lea     rcx, [rsp+78h+var_48]
0x180014f1d  mov     rdi, rdx
0x180014f20  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180014f26  lea     rax, word_1800263B2
0x180014f2d  test    ebx, ebx
0x180014f2f  lea     r8, asc_1800266F4; "/"
0x180014f36  mov     r9, rdi
0x180014f39  cmovz   r8, rax
0x180014f3d  lea     rdx, aSdSS; "<%sD:%s>%s"
0x180014f44  mov     rax, [rsi+8]
0x180014f48  lea     rcx, [rsp+78h+var_48]; struct STRA *
0x180014f4d  mov     [rsp+78h+var_58], rax
0x180014f52  call    ?SAFE_snprintf@@YAJPEAVSTRA@@PEBDZZ; SAFE_snprintf(STRA *,char const *,...)
0x180014f57  mov     ebx, eax
0x180014f59  test    eax, eax
0x180014f5b  js      short loc_180014F6E
0x180014f5d  lea     rcx, [rsi+18h]
0x180014f61  lea     rdx, [rsp+78h+var_48]
0x180014f66  call    cs:__imp_?Append@STRA@@QEAAJAEBV1@@Z; STRA::Append(STRA const &)
0x180014f6c  mov     ebx, eax
0x180014f6e  lea     rcx, [rsp+78h+var_48]
0x180014f73  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180014f79  mov     eax, ebx
0x180014f7b  mov     rcx, [rsp+78h+var_10]
0x180014f80  xor     rcx, rsp; StackCookie
0x180014f83  call    __security_check_cookie
0x180014f88  lea     r11, [rsp+78h+var_8]
0x180014f8d  mov     rbx, [r11+20h]
0x180014f91  mov     rsi, [r11+28h]
0x180014f95  mov     rsp, r11
0x180014f98  pop     rdi
0x180014f99  retn
```
