# XML_RENDERER::AppendProperty(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x180014b90`
- end: `0x180014e3e`
- name: `?AppendProperty@XML_RENDERER@@AEAAJPEBG0000@Z`
- size: `686`
- prototype: `__int64 __fastcall(XML_RENDERER *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800145a8`

## callees

- `0x180014b90`
- `0x18001c550`
- `0x180022520`

## import_xrefs

- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z` at `0x180014c28`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z` at `0x180014c3b`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z` at `0x180014c87`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z` at `0x180014cb8`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z` at `0x180014d1d`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z` at `0x180014d3c`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z` at `0x180014c28`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z` at `0x180014c3b`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z` at `0x180014c87`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z` at `0x180014cb8`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z` at `0x180014d1d`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z` at `0x180014d3c`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x180014df6`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x180014df6`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180014c66`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180014c71`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180014ce0`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180014da8`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180014db2`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180014e02`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180014e0c`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180014e16`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180014c66`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180014c71`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180014ce0`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180014da8`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180014db2`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180014e02`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180014e0c`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180014e16`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180014bda`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180014be4`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180014bee`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180014c10`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180014c1a`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180014caa`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180014d05`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180014d10`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180014bda`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180014be4`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180014bee`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180014c10`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180014c1a`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180014caa`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180014d05`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180014d10`

## string_xrefs

- `0x180014c80`: ` xmlns=""`
- `0x180014cc9`: ` xml:lang="%s"`

## pseudocode

```c
__int64 __fastcall XML_RENDERER::AppendProperty(
        const char **this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6)
{
  const char *v9; // r12
  const char *v10; // r13
  int v11; // ebx
  const char **v12; // rdi
  _BYTE v15[32]; // [rsp+58h] [rbp-A8h] BYREF
  const char *v16; // [rsp+78h] [rbp-88h]
  _BYTE v17[32]; // [rsp+90h] [rbp-70h] BYREF
  const char *v18; // [rsp+B0h] [rbp-50h]
  _BYTE v19[32]; // [rsp+C8h] [rbp-38h] BYREF
  const char *v20; // [rsp+E8h] [rbp-18h]
  _BYTE v21[56]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v22[32]; // [rsp+138h] [rbp+38h] BYREF
  const char *v23; // [rsp+158h] [rbp+58h]

  STRA::STRA((STRA *)v22);
  STRA::STRA((STRA *)v19);
  STRA::STRA((STRA *)v21);
  v9 = (const char *)&word_1800263B2;
  if ( a2 && *a2 )
  {
    v10 = (const char *)&word_1800263B2;
    STRA::STRA((STRA *)v15);
    STRA::STRA((STRA *)v17);
    v11 = STRA::CopyWToUTF8Unescaped((STRA *)v15, a3);
    if ( v11 >= 0 )
    {
      v11 = STRA::CopyWToUTF8Unescaped((STRA *)v17, a2);
      if ( v11 >= 0 )
        v11 = SAFE_snprintf((struct STRA *)v19, "%s:%s", v18, v16);
    }
    STRA::~STRA((STRA *)v17);
    STRA::~STRA((STRA *)v15);
  }
  else
  {
    v10 = " xmlns=\"\"";
    v11 = STRA::CopyWToUTF8Unescaped((STRA *)v19, a3);
  }
  if ( v11 >= 0 )
  {
    if ( !a5 || !*a5 )
      goto LABEL_30;
    STRA::STRA((STRA *)v15);
    v11 = STRA::CopyWToUTF8Unescaped((STRA *)v15, a5);
    if ( v11 >= 0 )
      v11 = SAFE_snprintf((struct STRA *)v22, " xml:lang=\"%s\"", v16);
    STRA::~STRA((STRA *)v15);
    if ( v11 >= 0 )
    {
LABEL_30:
      if ( !a4 || !*a4 )
      {
        v12 = this;
        v11 = SAFE_snprintf((struct STRA *)v21, "<%s%s%s/>%s", v20, v10, v23, this[1]);
LABEL_25:
        if ( v11 >= 0 )
          v11 = STRA::Append((STRA *)(v12 + 3), (const struct STRA *)v21);
        goto LABEL_27;
      }
      STRA::STRA((STRA *)v17);
      STRA::STRA((STRA *)v15);
      v11 = STRA::CopyWToUTF8Unescaped((STRA *)v17, a4);
      if ( v11 >= 0 )
      {
        if ( !a6 || !*a6 )
          goto LABEL_21;
        v11 = STRA::CopyWToUTF8Unescaped((STRA *)v15, a6);
        if ( v11 >= 0 )
        {
          v9 = " ";
LABEL_21:
          v12 = this;
          v11 = SAFE_snprintf((struct STRA *)v21, "<%s%s%s%s%s>%s</%s>%s", v20, v10, v23, v9, v16, v18, v20, this[1]);
LABEL_23:
          STRA::~STRA((STRA *)v15);
          STRA::~STRA((STRA *)v17);
          goto LABEL_25;
        }
      }
      v12 = this;
      goto LABEL_23;
    }
  }
LABEL_27:
  STRA::~STRA((STRA *)v21);
  STRA::~STRA((STRA *)v19);
  STRA::~STRA((STRA *)v22);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180014b90  push    rbp
0x180014b92  push    rbx
0x180014b93  push    rsi
0x180014b94  push    rdi
0x180014b95  push    r12
0x180014b97  push    r13
0x180014b99  push    r14
0x180014b9b  push    r15
0x180014b9d  lea     rbp, [rsp-88h]
0x180014ba5  sub     rsp, 188h
0x180014bac  mov     rax, cs:__security_cookie
0x180014bb3  xor     rax, rsp
0x180014bb6  mov     [rbp+0C0h+var_50], rax
0x180014bba  mov     rdi, [rbp+0C0h+arg_20]
0x180014bc1  mov     r14, r9
0x180014bc4  mov     rsi, [rbp+0C0h+arg_28]
0x180014bcb  mov     rbx, r8
0x180014bce  mov     [rsp+1C0h+var_170], rcx
0x180014bd3  mov     r15, rdx
0x180014bd6  lea     rcx, [rbp+0C0h+var_88]
0x180014bda  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180014be0  lea     rcx, [rbp+0C0h+var_F8]
0x180014be4  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180014bea  lea     rcx, [rbp+0C0h+var_C0]
0x180014bee  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180014bf4  xor     eax, eax
0x180014bf6  lea     r12, word_1800263B2
0x180014bfd  test    r15, r15
0x180014c00  jz      short loc_180014C79
0x180014c02  cmp     [r15], ax
0x180014c06  jz      short loc_180014C79
0x180014c08  lea     rcx, [rsp+1C0h+var_168]
0x180014c0d  mov     r13, r12
0x180014c10  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180014c16  lea     rcx, [rbp+0C0h+var_130]
0x180014c1a  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180014c20  mov     rdx, rbx
0x180014c23  lea     rcx, [rsp+1C0h+var_168]
0x180014c28  call    cs:__imp_?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z; STRA::CopyWToUTF8Unescaped(ushort const *)
0x180014c2e  mov     ebx, eax
0x180014c30  test    eax, eax
0x180014c32  js      short loc_180014C62
0x180014c34  mov     rdx, r15
0x180014c37  lea     rcx, [rbp+0C0h+var_130]
0x180014c3b  call    cs:__imp_?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z; STRA::CopyWToUTF8Unescaped(ushort const *)
0x180014c41  mov     ebx, eax
0x180014c43  test    eax, eax
0x180014c45  js      short loc_180014C62
0x180014c47  mov     r9, [rsp+1C0h+var_148]
0x180014c4c  lea     rdx, aSS; "%s:%s"
0x180014c53  mov     r8, [rbp+0C0h+var_110]
0x180014c57  lea     rcx, [rbp+0C0h+var_F8]; struct STRA *
0x180014c5b  call    ?SAFE_snprintf@@YAJPEAVSTRA@@PEBDZZ; SAFE_snprintf(STRA *,char const *,...)
0x180014c60  mov     ebx, eax
0x180014c62  lea     rcx, [rbp+0C0h+var_130]
0x180014c66  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180014c6c  lea     rcx, [rsp+1C0h+var_168]
0x180014c71  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180014c77  jmp     short loc_180014C8F
0x180014c79  mov     rdx, rbx
0x180014c7c  lea     rcx, [rbp+0C0h+var_F8]
0x180014c80  lea     r13, aXmlns_0; " xmlns=\"\""
0x180014c87  call    cs:__imp_?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z; STRA::CopyWToUTF8Unescaped(ushort const *)
0x180014c8d  mov     ebx, eax
0x180014c8f  xor     r15d, r15d
0x180014c92  test    ebx, ebx
0x180014c94  js      loc_180014DFE
0x180014c9a  test    rdi, rdi
0x180014c9d  jz      short loc_180014CEE
0x180014c9f  cmp     [rdi], r15w
0x180014ca3  jz      short loc_180014CEE
0x180014ca5  lea     rcx, [rsp+1C0h+var_168]
0x180014caa  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180014cb0  mov     rdx, rdi
0x180014cb3  lea     rcx, [rsp+1C0h+var_168]
0x180014cb8  call    cs:__imp_?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z; STRA::CopyWToUTF8Unescaped(ushort const *)
0x180014cbe  mov     ebx, eax
0x180014cc0  test    eax, eax
0x180014cc2  js      short loc_180014CDB
0x180014cc4  mov     r8, [rsp+1C0h+var_148]
0x180014cc9  lea     rdx, aXmlLangS; " xml:lang=\"%s\""
0x180014cd0  lea     rcx, [rbp+0C0h+var_88]; struct STRA *
0x180014cd4  call    ?SAFE_snprintf@@YAJPEAVSTRA@@PEBDZZ; SAFE_snprintf(STRA *,char const *,...)
0x180014cd9  mov     ebx, eax
0x180014cdb  lea     rcx, [rsp+1C0h+var_168]
0x180014ce0  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180014ce6  test    ebx, ebx
0x180014ce8  js      loc_180014DFE
0x180014cee  test    r14, r14
0x180014cf1  jz      loc_180014DBA
0x180014cf7  cmp     [r14], r15w
0x180014cfb  jz      loc_180014DBA
0x180014d01  lea     rcx, [rbp+0C0h+var_130]
0x180014d05  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180014d0b  lea     rcx, [rsp+1C0h+var_168]
0x180014d10  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180014d16  mov     rdx, r14
0x180014d19  lea     rcx, [rbp+0C0h+var_130]
0x180014d1d  call    cs:__imp_?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z; STRA::CopyWToUTF8Unescaped(ushort const *)
0x180014d23  mov     ebx, eax
0x180014d25  test    eax, eax
0x180014d27  js      short loc_180014D9E
0x180014d29  test    rsi, rsi
0x180014d2c  jz      short loc_180014D4F
0x180014d2e  cmp     [rsi], r15w
0x180014d32  jz      short loc_180014D4F
0x180014d34  mov     rdx, rsi
0x180014d37  lea     rcx, [rsp+1C0h+var_168]
0x180014d3c  call    cs:__imp_?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z; STRA::CopyWToUTF8Unescaped(ushort const *)
0x180014d42  mov     ebx, eax
0x180014d44  test    eax, eax
0x180014d46  js      short loc_180014D9E
0x180014d48  lea     r12, asc_180028B9C; " "
0x180014d4f  mov     rcx, [rbp+0C0h+var_110]
0x180014d53  mov     r9, r13
0x180014d56  mov     rdx, [rsp+1C0h+var_148]
0x180014d5b  mov     r8, [rbp+0C0h+var_D8]
0x180014d5f  mov     r10, [rbp+0C0h+var_68]
0x180014d63  mov     rdi, [rsp+1C0h+var_170]
0x180014d68  mov     rax, [rdi+8]
0x180014d6c  mov     [rsp+1C0h+var_178], rax
0x180014d71  mov     [rsp+1C0h+var_180], r8
0x180014d76  mov     [rsp+1C0h+var_188], rcx
0x180014d7b  lea     rcx, [rbp+0C0h+var_C0]; struct STRA *
0x180014d7f  mov     [rsp+1C0h+var_190], rdx
0x180014d84  lea     rdx, aSSSSSSSS_0; "<%s%s%s%s%s>%s</%s>%s"
0x180014d8b  mov     [rsp+1C0h+var_198], r12
0x180014d90  mov     [rsp+1C0h+var_1A0], r10
0x180014d95  call    ?SAFE_snprintf@@YAJPEAVSTRA@@PEBDZZ; SAFE_snprintf(STRA *,char const *,...)
0x180014d9a  mov     ebx, eax
0x180014d9c  jmp     short loc_180014DA3
0x180014d9e  mov     rdi, [rsp+1C0h+var_170]
0x180014da3  lea     rcx, [rsp+1C0h+var_168]
0x180014da8  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180014dae  lea     rcx, [rbp+0C0h+var_130]
0x180014db2  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180014db8  jmp     short loc_180014DEA
0x180014dba  mov     rcx, [rbp+0C0h+var_68]
0x180014dbe  lea     rdx, aSSSS; "<%s%s%s/>%s"
0x180014dc5  mov     rdi, [rsp+1C0h+var_170]
0x180014dca  mov     r9, r13
0x180014dcd  mov     r8, [rbp+0C0h+var_D8]
0x180014dd1  mov     rax, [rdi+8]
0x180014dd5  mov     [rsp+1C0h+var_198], rax
0x180014dda  mov     [rsp+1C0h+var_1A0], rcx
0x180014ddf  lea     rcx, [rbp+0C0h+var_C0]; struct STRA *
0x180014de3  call    ?SAFE_snprintf@@YAJPEAVSTRA@@PEBDZZ; SAFE_snprintf(STRA *,char const *,...)
0x180014de8  mov     ebx, eax
0x180014dea  test    ebx, ebx
0x180014dec  js      short loc_180014DFE
0x180014dee  lea     rcx, [rdi+18h]
0x180014df2  lea     rdx, [rbp+0C0h+var_C0]
0x180014df6  call    cs:__imp_?Append@STRA@@QEAAJAEBV1@@Z; STRA::Append(STRA const &)
0x180014dfc  mov     ebx, eax
0x180014dfe  lea     rcx, [rbp+0C0h+var_C0]
0x180014e02  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180014e08  lea     rcx, [rbp+0C0h+var_F8]
0x180014e0c  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180014e12  lea     rcx, [rbp+0C0h+var_88]
0x180014e16  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180014e1c  mov     eax, ebx
0x180014e1e  mov     rcx, [rbp+0C0h+var_50]
0x180014e22  xor     rcx, rsp; StackCookie
0x180014e25  call    __security_check_cookie
0x180014e2a  add     rsp, 188h
0x180014e31  pop     r15
0x180014e33  pop     r14
0x180014e35  pop     r13
0x180014e37  pop     r12
0x180014e39  pop     rdi
0x180014e3a  pop     rsi
0x180014e3b  pop     rbx
0x180014e3c  pop     rbp
0x180014e3d  retn
```
