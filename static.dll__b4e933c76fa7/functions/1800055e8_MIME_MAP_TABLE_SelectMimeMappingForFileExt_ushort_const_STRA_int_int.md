# MIME_MAP_TABLE::SelectMimeMappingForFileExt(ushort const *,STRA *,int *,int *)

- ea: `0x1800055e8`
- end: `0x1800056f9`
- name: `?SelectMimeMappingForFileExt@MIME_MAP_TABLE@@QEAAJPEBGPEAVSTRA@@PEAH2@Z`
- size: `273`
- prototype: `int __fastcall(MIME_MAP_TABLE *this, wchar_t *, struct STRA *, int *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180002dd8`

## callees

- `0x180005448`
- `0x1800055e8`

## import_xrefs

- `msvcrt!wcschr` at `0x18000564c`
- `msvcrt!wcschr` at `0x18000568b`
- `msvcrt!wcschr` at `0x18000564c`
- `msvcrt!wcschr` at `0x18000568b`
- `msvcrt!wcsrchr` at `0x180005621`
- `msvcrt!wcsrchr` at `0x180005631`
- `msvcrt!wcsrchr` at `0x180005621`
- `msvcrt!wcsrchr` at `0x180005631`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x1800056e0`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x1800056e0`
- `iisutil!?QueryStr@STRA@@QEBAPEBDXZ` at `0x1800056d4`
- `iisutil!?QueryStr@STRA@@QEBAPEBDXZ` at `0x1800056d4`

## pseudocode

```c
int __fastcall MIME_MAP_TABLE::SelectMimeMappingForFileExt(
        MIME_MAP_TABLE *this,
        wchar_t *a2,
        struct STRA *a3,
        int *a4,
        int *a5)
{
  wchar_t *v9; // rbx
  wchar_t *v10; // rax
  wchar_t *v11; // rax
  int v12; // r8d
  const unsigned __int16 *v13; // rbx
  STATIC_WSTRING_HASH *v14; // rdi
  struct STATIC_WSTRING_HASH_RECORD *Key; // rax
  wchar_t *v16; // rax
  const char *Str; // rax
  int result; // eax

  *a4 = 0;
  if ( a2 && *a2 )
  {
    v9 = wcsrchr(a2, 0x2Fu);
    v10 = wcsrchr(a2, 0x5Cu);
    if ( v9 > v10 )
      v10 = v9;
    if ( !v10 )
      v10 = a2;
    v11 = wcschr(v10, 0x2Eu);
    if ( v11 )
      v13 = v11 + 1;
    else
      v13 = &::Str;
    v14 = (MIME_MAP_TABLE *)((char *)this + 8);
    while ( v13 )
    {
      Key = STATIC_WSTRING_HASH::FindKey(v14, v13, v12);
      if ( Key )
      {
        if ( a5 )
          *a5 = 0;
LABEL_21:
        Str = STRA::QueryStr((struct STATIC_WSTRING_HASH_RECORD *)((char *)Key + 80));
        result = STRA::Copy(a3, Str);
        *a4 = 1;
        return result;
      }
      v16 = wcschr(v13, 0x2Eu);
      v13 = v16 + 1;
      if ( !v16 )
        v13 = 0;
    }
    Key = STATIC_WSTRING_HASH::FindKey(v14, L"*", v12);
    if ( a5 )
      *a5 = 1;
    if ( Key )
      goto LABEL_21;
  }
  return 0;
}

```

## disassembly

```asm
0x1800055e8  push    rbx
0x1800055ea  push    rbp
0x1800055eb  push    rsi
0x1800055ec  push    rdi
0x1800055ed  push    r14
0x1800055ef  push    r15
0x1800055f1  sub     rsp, 28h
0x1800055f5  xor     r15d, r15d
0x1800055f8  mov     rsi, r9
0x1800055fb  mov     [r9], r15d
0x1800055fe  mov     r14, r8
0x180005601  mov     rdi, rdx
0x180005604  mov     rbp, rcx
0x180005607  test    rdx, rdx
0x18000560a  jz      loc_1800056EA
0x180005610  cmp     [rdx], r15w
0x180005614  jz      loc_1800056EA
0x18000561a  lea     edx, [r15+2Fh]; Ch
0x18000561e  mov     rcx, rdi; Str
0x180005621  call    cs:__imp_wcsrchr
0x180005627  lea     edx, [r15+5Ch]; Ch
0x18000562b  mov     rcx, rdi; Str
0x18000562e  mov     rbx, rax
0x180005631  call    cs:__imp_wcsrchr
0x180005637  cmp     rbx, rax
0x18000563a  lea     edx, [r15+2Eh]; Ch
0x18000563e  cmova   rax, rbx
0x180005642  test    rax, rax
0x180005645  cmovz   rax, rdi
0x180005649  mov     rcx, rax; Str
0x18000564c  call    cs:__imp_wcschr
0x180005652  mov     rbx, rax
0x180005655  test    rax, rax
0x180005658  jnz     short loc_180005663
0x18000565a  lea     rbx, Str
0x180005661  jmp     short loc_180005667
0x180005663  add     rbx, 2
0x180005667  lea     rdi, [rbp+8]
0x18000566b  mov     ebp, 1
0x180005670  mov     rcx, rdi; this
0x180005673  test    rbx, rbx
0x180005676  jz      short loc_1800056B0
0x180005678  mov     rdx, rbx; unsigned __int16 *
0x18000567b  call    ?FindKey@STATIC_WSTRING_HASH@@QEAAPEAUSTATIC_WSTRING_HASH_RECORD@@PEBGH@Z; STATIC_WSTRING_HASH::FindKey(ushort const *,int)
0x180005680  test    rax, rax
0x180005683  jnz     short loc_18000569E
0x180005685  lea     edx, [rbp+2Dh]; Ch
0x180005688  mov     rcx, rbx; Str
0x18000568b  call    cs:__imp_wcschr
0x180005691  test    rax, rax
0x180005694  lea     rbx, [rax+2]
0x180005698  cmovz   rbx, rax
0x18000569c  jmp     short loc_18000566B
0x18000569e  mov     rcx, [rsp+58h+arg_20]
0x1800056a6  test    rcx, rcx
0x1800056a9  jz      short loc_1800056D0
0x1800056ab  mov     [rcx], r15d
0x1800056ae  jmp     short loc_1800056D0
0x1800056b0  lea     rdx, asc_1800092DC; "*"
0x1800056b7  call    ?FindKey@STATIC_WSTRING_HASH@@QEAAPEAUSTATIC_WSTRING_HASH_RECORD@@PEBGH@Z; STATIC_WSTRING_HASH::FindKey(ushort const *,int)
0x1800056bc  mov     rcx, [rsp+58h+arg_20]
0x1800056c4  test    rcx, rcx
0x1800056c7  jz      short loc_1800056CB
0x1800056c9  mov     [rcx], ebp
0x1800056cb  test    rax, rax
0x1800056ce  jz      short loc_1800056EA
0x1800056d0  lea     rcx, [rax+50h]
0x1800056d4  call    cs:__imp_?QueryStr@STRA@@QEBAPEBDXZ; STRA::QueryStr(void)
0x1800056da  mov     rdx, rax
0x1800056dd  mov     rcx, r14
0x1800056e0  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x1800056e6  mov     [rsi], ebp
0x1800056e8  jmp     short loc_1800056EC
0x1800056ea  xor     eax, eax
0x1800056ec  add     rsp, 28h
0x1800056f0  pop     r15
0x1800056f2  pop     r14
0x1800056f4  pop     rdi
0x1800056f5  pop     rsi
0x1800056f6  pop     rbp
0x1800056f7  pop     rbx
0x1800056f8  retn
```
