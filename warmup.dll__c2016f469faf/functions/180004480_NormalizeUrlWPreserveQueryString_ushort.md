# NormalizeUrlWPreserveQueryString(ushort *)

- ea: `0x180004480`
- end: `0x180004566`
- name: `?NormalizeUrlWPreserveQueryString@@YAJPEAG@Z`
- size: `230`
- prototype: `__int64 __fastcall(wchar_t *Destination)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x180003818`

## callees

- `0x180004480`
- `0x180004fe0`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18000450d`
- `msvcrt!wcscat_s` at `0x18000450d`
- `msvcrt!wcschr` at `0x1800044c6`
- `msvcrt!wcschr` at `0x1800044c6`
- `iisutil!NormalizeUrlW` at `0x1800044ef`
- `iisutil!NormalizeUrlW` at `0x1800044ef`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000452d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000453c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000452d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000453c`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800044b8`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800044b8`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800044dc`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800044dc`

## pseudocode

```c
__int64 __fastcall NormalizeUrlWPreserveQueryString(wchar_t *Destination)
{
  __int64 v1; // rdi
  wchar_t *v3; // rax
  wchar_t *v4; // r14
  signed int v5; // ebx
  errno_t v6; // eax
  _BYTE v8[32]; // [rsp+20h] [rbp-58h] BYREF
  wchar_t *Source; // [rsp+40h] [rbp-38h]
  int v10; // [rsp+50h] [rbp-28h]

  v1 = -1;
  do
    ++v1;
  while ( Destination[v1] );
  STRU::STRU((STRU *)v8);
  v3 = wcschr(Destination, 0x3Fu);
  v4 = v3;
  if ( v3 )
  {
    v5 = STRU::Copy((STRU *)v8, v3);
    if ( v5 < 0 )
      goto LABEL_13;
    *v4 = 0;
  }
  v5 = NormalizeUrlW(Destination);
  if ( v5 >= 0 )
  {
    if ( !v10 )
      goto LABEL_12;
    v6 = wcscat_s(Destination, v1 + 1, Source);
    v5 = v6;
    if ( !v6 )
      goto LABEL_12;
    if ( v6 > 0 )
      v5 = (unsigned __int16)v6 | 0x80070000;
    if ( v5 >= 0 )
    {
LABEL_12:
      STRU::~STRU((STRU *)v8);
      return 0;
    }
  }
LABEL_13:
  STRU::~STRU((STRU *)v8);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180004480  mov     [rsp+arg_8], rbx
0x180004485  mov     [rsp+arg_10], rbp
0x18000448a  push    rsi
0x18000448b  push    rdi
0x18000448c  push    r14
0x18000448e  sub     rsp, 60h
0x180004492  mov     rax, cs:__security_cookie
0x180004499  xor     rax, rsp
0x18000449c  mov     [rsp+78h+var_20], rax
0x1800044a1  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800044a5  mov     rsi, rcx
0x1800044a8  xor     ebp, ebp
0x1800044aa  inc     rdi
0x1800044ad  cmp     [rcx+rdi*2], bp
0x1800044b1  jnz     short loc_1800044AA
0x1800044b3  lea     rcx, [rsp+78h+var_58]
0x1800044b8  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800044be  mov     edx, 3Fh ; '?'; Ch
0x1800044c3  mov     rcx, rsi; Str
0x1800044c6  call    cs:__imp_wcschr
0x1800044cc  mov     r14, rax
0x1800044cf  test    rax, rax
0x1800044d2  jz      short loc_1800044EC
0x1800044d4  mov     rdx, rax
0x1800044d7  lea     rcx, [rsp+78h+var_58]
0x1800044dc  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800044e2  mov     ebx, eax
0x1800044e4  test    eax, eax
0x1800044e6  js      short loc_180004537
0x1800044e8  mov     [r14], bp
0x1800044ec  mov     rcx, rsi
0x1800044ef  call    cs:__imp_?NormalizeUrlW@@YAJPEAG@Z; NormalizeUrlW(ushort *)
0x1800044f5  mov     ebx, eax
0x1800044f7  test    eax, eax
0x1800044f9  js      short loc_180004537
0x1800044fb  cmp     [rsp+78h+var_28], ebp
0x1800044ff  jz      short loc_180004528
0x180004501  mov     r8, [rsp+78h+Source]; Source
0x180004506  lea     rdx, [rdi+1]; SizeInWords
0x18000450a  mov     rcx, rsi; Destination
0x18000450d  call    cs:__imp_wcscat_s
0x180004513  mov     ebx, eax
0x180004515  test    eax, eax
0x180004517  jz      short loc_180004528
0x180004519  jle     short loc_180004524
0x18000451b  movzx   ebx, ax
0x18000451e  or      ebx, 80070000h
0x180004524  test    ebx, ebx
0x180004526  js      short loc_180004537
0x180004528  lea     rcx, [rsp+78h+var_58]
0x18000452d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180004533  xor     eax, eax
0x180004535  jmp     short loc_180004544
0x180004537  lea     rcx, [rsp+78h+var_58]
0x18000453c  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180004542  mov     eax, ebx
0x180004544  mov     rcx, [rsp+78h+var_20]
0x180004549  xor     rcx, rsp; StackCookie
0x18000454c  call    __security_check_cookie
0x180004551  lea     r11, [rsp+78h+var_18]
0x180004556  mov     rbx, [r11+28h]
0x18000455a  mov     rbp, [r11+30h]
0x18000455e  mov     rsp, r11
0x180004561  pop     r14
0x180004563  pop     rdi
0x180004564  pop     rsi
0x180004565  retn
```
