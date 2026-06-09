# STATIC_META_STORED_CONTEXT::SelectMimeMappingForFileExt(ushort const *,STRA *,int *,int *)

- ea: `0x18000bb20`
- end: `0x18000bc2c`
- name: `?SelectMimeMappingForFileExt@STATIC_META_STORED_CONTEXT@@QEAAJPEBGPEAVSTRA@@PEAH2@Z`
- size: `268`
- prototype: `int(STATIC_META_STORED_CONTEXT *__hidden this, const unsigned __int16 *, struct STRA *, int *, int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000b3b0`
- `0x180016708`

## callees

- `0x1800043b0`
- `0x18000bb20`

## import_xrefs

- `msvcrt!wcschr` at `0x18000bb88`
- `msvcrt!wcschr` at `0x18000bbb1`
- `msvcrt!wcschr` at `0x18000bb88`
- `msvcrt!wcschr` at `0x18000bbb1`
- `msvcrt!wcsrchr` at `0x18000bb5d`
- `msvcrt!wcsrchr` at `0x18000bb6d`
- `msvcrt!wcsrchr` at `0x18000bb5d`
- `msvcrt!wcsrchr` at `0x18000bb6d`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18000bbf6`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18000bbf6`

## pseudocode

```c
int __fastcall STATIC_META_STORED_CONTEXT::SelectMimeMappingForFileExt(
        STATIC_META_STORED_CONTEXT *this,
        wchar_t *a2,
        struct STRA *a3,
        int *a4,
        int *a5)
{
  __int64 v8; // rbp
  wchar_t *v9; // rbx
  wchar_t *v10; // rax
  wchar_t *v11; // rax
  int v12; // r8d
  const unsigned __int16 *v13; // rbx
  struct STATIC_WSTRING_HASH_RECORD *Key; // rax
  wchar_t *v15; // rax
  int result; // eax

  *a4 = 0;
  if ( a2 && *a2 )
  {
    v8 = *((_QWORD *)this + 32);
    v9 = wcsrchr(a2, 0x2Fu);
    v10 = wcsrchr(a2, 0x5Cu);
    if ( v9 > v10 )
      v10 = v9;
    if ( !v10 )
      v10 = a2;
    v11 = wcschr(v10, 0x2Eu);
    if ( v11 )
    {
      v13 = v11 + 1;
      goto LABEL_12;
    }
    v13 = &Src;
    do
    {
      Key = STATIC_WSTRING_HASH::FindKey((STATIC_WSTRING_HASH *)(v8 + 8), v13, v12);
      if ( Key )
      {
        if ( a5 )
          *a5 = 0;
        goto LABEL_16;
      }
      v15 = wcschr(v13, 0x2Eu);
      v13 = v15 + 1;
      if ( !v15 )
        v13 = 0;
LABEL_12:
      ;
    }
    while ( v13 );
    Key = STATIC_WSTRING_HASH::FindKey((STATIC_WSTRING_HASH *)(v8 + 8), L"*", v12);
    if ( a5 )
      *a5 = 1;
    if ( Key )
    {
LABEL_16:
      result = STRA::Copy(a3, *((const char **)Key + 14));
      *a4 = 1;
      return result;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000bb20  push    rbx
0x18000bb22  push    rbp
0x18000bb23  push    rsi
0x18000bb24  push    rdi
0x18000bb25  push    r14
0x18000bb27  push    r15
0x18000bb29  sub     rsp, 28h
0x18000bb2d  xor     r15d, r15d
0x18000bb30  mov     rsi, r9
0x18000bb33  mov     [r9], r15d
0x18000bb36  mov     r14, r8
0x18000bb39  mov     rdi, rdx
0x18000bb3c  test    rdx, rdx
0x18000bb3f  jz      loc_18000BC1C
0x18000bb45  cmp     [rdx], r15w
0x18000bb49  jz      loc_18000BC1C
0x18000bb4f  mov     rbp, [rcx+100h]
0x18000bb56  lea     edx, [r15+2Fh]; Ch
0x18000bb5a  mov     rcx, rdi; Str
0x18000bb5d  call    cs:__imp_wcsrchr
0x18000bb63  lea     edx, [r15+5Ch]; Ch
0x18000bb67  mov     rcx, rdi; Str
0x18000bb6a  mov     rbx, rax
0x18000bb6d  call    cs:__imp_wcsrchr
0x18000bb73  cmp     rbx, rax
0x18000bb76  lea     edx, [r15+2Eh]; Ch
0x18000bb7a  cmova   rax, rbx
0x18000bb7e  test    rax, rax
0x18000bb81  cmovz   rax, rdi
0x18000bb85  mov     rcx, rax; Str
0x18000bb88  call    cs:__imp_wcschr
0x18000bb8e  test    rax, rax
0x18000bb91  jnz     short loc_18000BC04
0x18000bb93  lea     rbx, Src
0x18000bb9a  mov     rdx, rbx; unsigned __int16 *
0x18000bb9d  lea     rcx, [rbp+8]; this
0x18000bba1  call    ?FindKey@STATIC_WSTRING_HASH@@QEAAPEAUSTATIC_WSTRING_HASH_RECORD@@PEBGH@Z; STATIC_WSTRING_HASH::FindKey(ushort const *,int)
0x18000bba6  test    rax, rax
0x18000bba9  jnz     short loc_18000BC0A
0x18000bbab  lea     edx, [rax+2Eh]; Ch
0x18000bbae  mov     rcx, rbx; Str
0x18000bbb1  call    cs:__imp_wcschr
0x18000bbb7  test    rax, rax
0x18000bbba  lea     rbx, [rax+2]
0x18000bbbe  cmovz   rbx, rax
0x18000bbc2  test    rbx, rbx
0x18000bbc5  jnz     short loc_18000BB9A
0x18000bbc7  lea     rcx, [rbp+8]; this
0x18000bbcb  lea     rdx, asc_180026D28; "*"
0x18000bbd2  call    ?FindKey@STATIC_WSTRING_HASH@@QEAAPEAUSTATIC_WSTRING_HASH_RECORD@@PEBGH@Z; STATIC_WSTRING_HASH::FindKey(ushort const *,int)
0x18000bbd7  mov     rcx, [rsp+58h+arg_20]
0x18000bbdf  test    rcx, rcx
0x18000bbe2  jz      short loc_18000BBEA
0x18000bbe4  mov     dword ptr [rcx], 1
0x18000bbea  test    rax, rax
0x18000bbed  jz      short loc_18000BC1C
0x18000bbef  mov     rdx, [rax+70h]
0x18000bbf3  mov     rcx, r14
0x18000bbf6  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x18000bbfc  mov     dword ptr [rsi], 1
0x18000bc02  jmp     short loc_18000BC1F
0x18000bc04  lea     rbx, [rax+2]
0x18000bc08  jmp     short loc_18000BBC2
0x18000bc0a  mov     rcx, [rsp+58h+arg_20]
0x18000bc12  test    rcx, rcx
0x18000bc15  jz      short loc_18000BBEF
0x18000bc17  mov     [rcx], r15d
0x18000bc1a  jmp     short loc_18000BBEF
0x18000bc1c  mov     eax, r15d
0x18000bc1f  add     rsp, 28h
0x18000bc23  pop     r15
0x18000bc25  pop     r14
0x18000bc27  pop     rdi
0x18000bc28  pop     rsi
0x18000bc29  pop     rbp
0x18000bc2a  pop     rbx
0x18000bc2b  retn
```
