# XML_RENDERER::AppendHRef(ushort const *,ushort const *)

- ea: `0x180013fd4`
- end: `0x1800140fb`
- name: `?AppendHRef@XML_RENDERER@@AEAAJPEBG0@Z`
- size: `295`
- prototype: `__int64 __fastcall(XML_RENDERER *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `8`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013bb0`
- `0x180014388`
- `0x180014ae8`
- `0x180014fa0`
- `0x180015430`
- `0x1800155d4`
- `0x180015790`
- `0x1800158a8`

## callees

- `0x180005dec`
- `0x180005f6c`
- `0x180013fd4`
- `0x18001c550`
- `0x180022520`

## import_xrefs

- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z` at `0x180014035`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z` at `0x180014035`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x1800140a8`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x1800140a8`
- `iisutil!?CopyWToUTF8Escaped@STRA@@QEAAJPEBG@Z` at `0x180014049`
- `iisutil!?CopyWToUTF8Escaped@STRA@@QEAAJPEBG@Z` at `0x180014049`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800140b5`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800140c0`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800140ca`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800140d4`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800140b5`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800140c0`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800140ca`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800140d4`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180014003`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18001400d`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180014018`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180014023`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180014003`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18001400d`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180014018`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180014023`

## pseudocode

```c
__int64 __fastcall XML_RENDERER::AppendHRef(const char **this, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  int EscapedUriStem; // ebx
  const char *v7; // r9
  _BYTE v9[32]; // [rsp+30h] [rbp-D0h] BYREF
  const char *v10; // [rsp+50h] [rbp-B0h]
  _BYTE v11[32]; // [rsp+68h] [rbp-98h] BYREF
  char *v12; // [rsp+88h] [rbp-78h]
  _BYTE v13[32]; // [rsp+A0h] [rbp-60h] BYREF
  const char *v14; // [rsp+C0h] [rbp-40h]
  _BYTE v15[56]; // [rsp+D8h] [rbp-28h] BYREF

  STRA::STRA((STRA *)v15);
  STRA::STRA((STRA *)v13);
  STRA::STRA((STRA *)v11);
  STRA::STRA((STRA *)v9);
  if ( !a2 || (EscapedUriStem = STRA::CopyWToUTF8Unescaped((STRA *)v13, a2), EscapedUriStem >= 0) )
  {
    EscapedUriStem = STRA::CopyWToUTF8Escaped((STRA *)v11, a3);
    if ( EscapedUriStem >= 0 )
    {
      if ( !(unsigned int)IsValidUriStem(v12) )
      {
        EscapedUriStem = MakeEscapedUriStem(v7, (struct STRA *)v9);
        if ( EscapedUriStem < 0 )
          goto LABEL_9;
        v7 = v10;
      }
      EscapedUriStem = SAFE_snprintf((struct STRA *)v15, "<D:href>%s%s</D:href>%s", v14, v7, this[1]);
      if ( EscapedUriStem >= 0 )
        EscapedUriStem = STRA::Append((STRA *)(this + 3), (const struct STRA *)v15);
    }
  }
LABEL_9:
  STRA::~STRA((STRA *)v9);
  STRA::~STRA((STRA *)v11);
  STRA::~STRA((STRA *)v13);
  STRA::~STRA((STRA *)v15);
  return (unsigned int)EscapedUriStem;
}

```

## disassembly

```asm
0x180013fd4  mov     [rsp-8+arg_18], rbx
0x180013fd9  push    rbp
0x180013fda  push    rsi
0x180013fdb  push    rdi
0x180013fdc  lea     rbp, [rsp-20h]
0x180013fe1  sub     rsp, 120h
0x180013fe8  mov     rax, cs:__security_cookie
0x180013fef  xor     rax, rsp
0x180013ff2  mov     [rbp+30h+var_20], rax
0x180013ff6  mov     rdi, rcx
0x180013ff9  mov     rsi, r8
0x180013ffc  lea     rcx, [rbp+30h+var_58]
0x180014000  mov     rbx, rdx
0x180014003  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180014009  lea     rcx, [rbp+30h+var_90]
0x18001400d  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180014013  lea     rcx, [rsp+130h+var_C8]
0x180014018  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x18001401e  lea     rcx, [rsp+130h+var_100]
0x180014023  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180014029  test    rbx, rbx
0x18001402c  jz      short loc_180014041
0x18001402e  mov     rdx, rbx
0x180014031  lea     rcx, [rbp+30h+var_90]
0x180014035  call    cs:__imp_?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z; STRA::CopyWToUTF8Unescaped(ushort const *)
0x18001403b  mov     ebx, eax
0x18001403d  test    eax, eax
0x18001403f  js      short loc_1800140B0
0x180014041  mov     rdx, rsi
0x180014044  lea     rcx, [rsp+130h+var_C8]
0x180014049  call    cs:__imp_?CopyWToUTF8Escaped@STRA@@QEAAJPEBG@Z; STRA::CopyWToUTF8Escaped(ushort const *)
0x18001404f  mov     ebx, eax
0x180014051  test    eax, eax
0x180014053  js      short loc_1800140B0
0x180014055  mov     r9, [rbp+30h+var_A8]
0x180014059  mov     rcx, r9; char *
0x18001405c  call    ?IsValidUriStem@@YAHPEBD@Z; IsValidUriStem(char const *)
0x180014061  test    eax, eax
0x180014063  jnz     short loc_18001407D
0x180014065  lea     rdx, [rsp+130h+var_100]; struct STRA *
0x18001406a  mov     rcx, r9; char *
0x18001406d  call    ?MakeEscapedUriStem@@YAJPEBDPEAVSTRA@@@Z; MakeEscapedUriStem(char const *,STRA *)
0x180014072  mov     ebx, eax
0x180014074  test    eax, eax
0x180014076  js      short loc_1800140B0
0x180014078  mov     r9, [rsp+130h+var_E0]
0x18001407d  mov     rax, [rdi+8]
0x180014081  lea     rdx, aDHrefSSDHrefS; "<D:href>%s%s</D:href>%s"
0x180014088  mov     r8, [rbp+30h+var_70]
0x18001408c  lea     rcx, [rbp+30h+var_58]; struct STRA *
0x180014090  mov     [rsp+130h+var_110], rax
0x180014095  call    ?SAFE_snprintf@@YAJPEAVSTRA@@PEBDZZ; SAFE_snprintf(STRA *,char const *,...)
0x18001409a  mov     ebx, eax
0x18001409c  test    eax, eax
0x18001409e  js      short loc_1800140B0
0x1800140a0  lea     rcx, [rdi+18h]
0x1800140a4  lea     rdx, [rbp+30h+var_58]
0x1800140a8  call    cs:__imp_?Append@STRA@@QEAAJAEBV1@@Z; STRA::Append(STRA const &)
0x1800140ae  mov     ebx, eax
0x1800140b0  lea     rcx, [rsp+130h+var_100]
0x1800140b5  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800140bb  lea     rcx, [rsp+130h+var_C8]
0x1800140c0  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800140c6  lea     rcx, [rbp+30h+var_90]
0x1800140ca  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800140d0  lea     rcx, [rbp+30h+var_58]
0x1800140d4  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800140da  mov     eax, ebx
0x1800140dc  mov     rcx, [rbp+30h+var_20]
0x1800140e0  xor     rcx, rsp; StackCookie
0x1800140e3  call    __security_check_cookie
0x1800140e8  mov     rbx, [rsp+130h+arg_18]
0x1800140f0  add     rsp, 120h
0x1800140f7  pop     rdi
0x1800140f8  pop     rsi
0x1800140f9  pop     rbp
0x1800140fa  retn
```
