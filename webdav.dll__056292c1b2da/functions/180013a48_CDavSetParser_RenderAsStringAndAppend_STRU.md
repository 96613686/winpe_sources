# CDavSetParser::RenderAsStringAndAppend(STRU *)

- ea: `0x180013a48`
- end: `0x180013ba9`
- name: `?RenderAsStringAndAppend@CDavSetParser@@QEAAJPEAVSTRU@@@Z`
- size: `353`
- prototype: `__int64 __fastcall(CDavSetParser *__hidden this, struct STRU *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001317c`

## callees

- `0x180013a48`
- `0x1800224e6`
- `0x180022520`

## import_xrefs

- `iisutil!SAFE_snwprintf` at `0x180013ad7`
- `iisutil!SAFE_snwprintf` at `0x180013b16`
- `iisutil!SAFE_snwprintf` at `0x180013b43`
- `iisutil!SAFE_snwprintf` at `0x180013ad7`
- `iisutil!SAFE_snwprintf` at `0x180013b16`
- `iisutil!SAFE_snwprintf` at `0x180013b43`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180013a98`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180013aa3`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180013a98`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180013aa3`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180013b67`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180013b75`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180013b67`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180013b75`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180013b5a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180013b5a`

## string_xrefs

- `0x180013acb`: ` xmlns="%s"`

## pseudocode

```c
__int64 __fastcall CDavSetParser::RenderAsStringAndAppend(CDavSetParser *this, struct STRU *a2)
{
  const wchar_t *v2; // rbx
  __int64 v4; // rdi
  _WORD *v5; // rsi
  __int64 v6; // rbp
  __int64 v7; // r14
  const wchar_t *v8; // r8
  int v9; // ebx
  int v10; // eax
  _BYTE v12[32]; // [rsp+50h] [rbp-A8h] BYREF
  __int64 v13; // [rsp+70h] [rbp-88h]
  _BYTE v14[32]; // [rsp+88h] [rbp-70h] BYREF
  const unsigned __int16 *v15; // [rsp+A8h] [rbp-50h]

  v2 = (const wchar_t *)*((_QWORD *)this + 15);
  v4 = *((_QWORD *)this + 8);
  v5 = (_WORD *)*((_QWORD *)this + 29);
  v6 = *((_QWORD *)this + 22);
  v7 = *((_QWORD *)this + 36);
  STRU::STRU((STRU *)v14);
  STRU::STRU((STRU *)v12);
  if ( !wcscmp_0(v2, L"DAV:") )
  {
    v8 = L"D:";
  }
  else
  {
    v9 = SAFE_snwprintf((struct STRU *)v12, L" xmlns=\"%s\"", v2);
    if ( v9 < 0 )
      goto LABEL_10;
    v8 = &Src;
  }
  if ( *v5 )
    v10 = SAFE_snwprintf((struct STRU *)v14, L"<%s%s%s%s%s>%s</%s%s>", v8, v4, v13, v6, v7, v5, v8, v4);
  else
    v10 = SAFE_snwprintf((struct STRU *)v14, L"<%s%s%s%s%s/>", v8, v4, v13, v6, v7);
  v9 = v10;
  if ( v10 >= 0 )
    v9 = STRU::Append(a2, v15);
LABEL_10:
  STRU::~STRU((STRU *)v12);
  STRU::~STRU((STRU *)v14);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180013a48  mov     r11, rsp
0x180013a4b  mov     [r11+18h], rbx
0x180013a4f  mov     [r11+20h], rbp
0x180013a53  push    rsi
0x180013a54  push    rdi
0x180013a55  push    r12
0x180013a57  push    r14
0x180013a59  push    r15
0x180013a5b  sub     rsp, 0D0h
0x180013a62  mov     rax, cs:__security_cookie
0x180013a69  xor     rax, rsp
0x180013a6c  mov     [rsp+0F8h+var_38], rax
0x180013a74  mov     rbx, [rcx+78h]
0x180013a78  mov     r15, rdx
0x180013a7b  mov     rdi, [rcx+40h]
0x180013a7f  mov     rsi, [rcx+0E8h]
0x180013a86  mov     rbp, [rcx+0B0h]
0x180013a8d  mov     r14, [rcx+120h]
0x180013a94  lea     rcx, [r11-70h]
0x180013a98  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180013a9e  lea     rcx, [rsp+0F8h+var_A8]
0x180013aa3  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180013aa9  lea     rdx, aDav; "DAV:"
0x180013ab0  mov     rcx, rbx; String1
0x180013ab3  call    wcscmp_0
0x180013ab8  xor     r12d, r12d
0x180013abb  test    eax, eax
0x180013abd  jnz     short loc_180013AC8
0x180013abf  lea     r8, aD; "D:"
0x180013ac6  jmp     short loc_180013AEA
0x180013ac8  mov     r8, rbx
0x180013acb  lea     rdx, aXmlnsS; " xmlns=\"%s\""
0x180013ad2  lea     rcx, [rsp+0F8h+var_A8]
0x180013ad7  call    cs:__imp_?SAFE_snwprintf@@YAJPEAVSTRU@@PEBGZZ; SAFE_snwprintf(STRU *,ushort const *,...)
0x180013add  mov     ebx, eax
0x180013adf  test    eax, eax
0x180013ae1  js      short loc_180013B62
0x180013ae3  lea     r8, Src
0x180013aea  lea     rcx, [rsp+0F8h+var_70]
0x180013af2  mov     rax, [rsp+0F8h+var_88]
0x180013af7  mov     r9, rdi
0x180013afa  cmp     [rsi], r12w
0x180013afe  jnz     short loc_180013B1E
0x180013b00  mov     [rsp+0F8h+var_C8], r14
0x180013b05  lea     rdx, aSSSSS; "<%s%s%s%s%s/>"
0x180013b0c  mov     [rsp+0F8h+var_D0], rbp
0x180013b11  mov     [rsp+0F8h+var_D8], rax
0x180013b16  call    cs:__imp_?SAFE_snwprintf@@YAJPEAVSTRU@@PEBGZZ; SAFE_snwprintf(STRU *,ushort const *,...)
0x180013b1c  jmp     short loc_180013B49
0x180013b1e  mov     [rsp+0F8h+var_B0], rdi
0x180013b23  lea     rdx, aSSSSSSSS; "<%s%s%s%s%s>%s</%s%s>"
0x180013b2a  mov     [rsp+0F8h+var_B8], r8
0x180013b2f  mov     [rsp+0F8h+var_C0], rsi
0x180013b34  mov     [rsp+0F8h+var_C8], r14
0x180013b39  mov     [rsp+0F8h+var_D0], rbp
0x180013b3e  mov     [rsp+0F8h+var_D8], rax
0x180013b43  call    cs:__imp_?SAFE_snwprintf@@YAJPEAVSTRU@@PEBGZZ; SAFE_snwprintf(STRU *,ushort const *,...)
0x180013b49  mov     ebx, eax
0x180013b4b  test    eax, eax
0x180013b4d  js      short loc_180013B62
0x180013b4f  mov     rdx, [rsp+0F8h+var_50]
0x180013b57  mov     rcx, r15
0x180013b5a  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180013b60  mov     ebx, eax
0x180013b62  lea     rcx, [rsp+0F8h+var_A8]
0x180013b67  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180013b6d  lea     rcx, [rsp+0F8h+var_70]
0x180013b75  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180013b7b  mov     eax, ebx
0x180013b7d  mov     rcx, [rsp+0F8h+var_38]
0x180013b85  xor     rcx, rsp; StackCookie
0x180013b88  call    __security_check_cookie
0x180013b8d  lea     r11, [rsp+0F8h+var_28]
0x180013b95  mov     rbx, [r11+40h]
0x180013b99  mov     rbp, [r11+48h]
0x180013b9d  mov     rsp, r11
0x180013ba0  pop     r15
0x180013ba2  pop     r14
0x180013ba4  pop     r12
0x180013ba6  pop     rdi
0x180013ba7  pop     rsi
0x180013ba8  retn
```
