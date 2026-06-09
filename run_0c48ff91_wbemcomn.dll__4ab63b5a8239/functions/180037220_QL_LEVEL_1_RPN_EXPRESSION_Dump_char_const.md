# QL_LEVEL_1_RPN_EXPRESSION::Dump(char const *)

- ea: `0x180037220`
- end: `0x18003733a`
- name: `?Dump@QL_LEVEL_1_RPN_EXPRESSION@@QEAAXPEBD@Z`
- size: `282`
- prototype: `void(QL_LEVEL_1_RPN_EXPRESSION *__hidden this, const char *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180024a40`
- `0x180037220`
- `0x180037340`

## import_xrefs

- `msvcrt!fprintf` at `0x18003725b`
- `msvcrt!fprintf` at `0x18003726f`
- `msvcrt!fprintf` at `0x18003727f`
- `msvcrt!fprintf` at `0x180037296`
- `msvcrt!fprintf` at `0x1800372c3`
- `msvcrt!fprintf` at `0x1800372da`
- `msvcrt!fprintf` at `0x1800372ea`
- `msvcrt!fprintf` at `0x18003731b`
- `msvcrt!fprintf` at `0x18003725b`
- `msvcrt!fprintf` at `0x18003726f`
- `msvcrt!fprintf` at `0x18003727f`
- `msvcrt!fprintf` at `0x180037296`
- `msvcrt!fprintf` at `0x1800372c3`
- `msvcrt!fprintf` at `0x1800372da`
- `msvcrt!fprintf` at `0x1800372ea`
- `msvcrt!fprintf` at `0x18003731b`
- `msvcrt!fopen` at `0x18003723f`
- `msvcrt!fopen` at `0x18003723f`
- `msvcrt!fclose` at `0x180037324`
- `msvcrt!fclose` at `0x180037324`

## string_xrefs

- `0x1800372e0`: `Tokens:\n`

## pseudocode

```c
void __fastcall QL_LEVEL_1_RPN_EXPRESSION::Dump(const wchar_t **this, const char *a2)
{
  FILE *v3; // rax
  FILE *v4; // rbx
  int v5; // eax
  int v6; // esi
  const wchar_t *StringAt; // rax
  int i; // esi

  v3 = fopen(a2, "wt");
  v4 = v3;
  if ( v3 )
  {
    fprintf(v3, "----RPN Expression----\n");
    fprintf(v4, "Class name = %S\n", this[3]);
    fprintf(v4, "Properties selected: ");
    v5 = *((_DWORD *)this + 12);
    if ( v5 )
    {
      v6 = 0;
      if ( v5 > 0 )
      {
        do
        {
          StringAt = CPropertyName::GetStringAt((CPropertyName *)&this[8][16 * v6], 0);
          fprintf(v4, "%S ", StringAt);
          ++v6;
        }
        while ( v6 < *((_DWORD *)this + 12) );
      }
    }
    else
    {
      fprintf(v4, "* = all properties selected\n");
    }
    fprintf(v4, "\n------------------\n");
    fprintf(v4, "Tokens:\n");
    for ( i = 0; i < *((_DWORD *)this + 2); ++i )
      QL_LEVEL_1_TOKEN::Dump((QL_LEVEL_1_TOKEN *)&this[2][64 * (__int64)i], v4);
    fprintf(v4, "---end of expression---\n");
    fclose(v4);
  }
}

```

## disassembly

```asm
0x180037220  mov     [rsp+arg_0], rbx
0x180037225  mov     [rsp+arg_8], rsi
0x18003722a  push    rdi
0x18003722b  sub     rsp, 20h
0x18003722f  mov     rax, rdx
0x180037232  mov     rdi, rcx
0x180037235  mov     rcx, rax; FileName
0x180037238  lea     rdx, Mode; "wt"
0x18003723f  call    cs:__imp_fopen
0x180037245  mov     rbx, rax
0x180037248  test    rax, rax
0x18003724b  jz      loc_18003732A
0x180037251  lea     rdx, aRpnExpression; "----RPN Expression----\n"
0x180037258  mov     rcx, rax; Stream
0x18003725b  call    cs:__imp_fprintf
0x180037261  mov     r8, [rdi+18h]
0x180037265  lea     rdx, aClassNameS; "Class name = %S\n"
0x18003726c  mov     rcx, rbx; Stream
0x18003726f  call    cs:__imp_fprintf
0x180037275  lea     rdx, aPropertiesSele; "Properties selected: "
0x18003727c  mov     rcx, rbx; Stream
0x18003727f  call    cs:__imp_fprintf
0x180037285  mov     eax, [rdi+30h]
0x180037288  test    eax, eax
0x18003728a  jnz     short loc_18003729E
0x18003728c  lea     rdx, aAllPropertiesS; "* = all properties selected\n"
0x180037293  mov     rcx, rbx; Stream
0x180037296  call    cs:__imp_fprintf
0x18003729c  jmp     short loc_1800372D0
0x18003729e  xor     esi, esi
0x1800372a0  test    eax, eax
0x1800372a2  jle     short loc_1800372D0
0x1800372a4  movsxd  rcx, esi
0x1800372a7  xor     edx, edx; int
0x1800372a9  shl     rcx, 5
0x1800372ad  add     rcx, [rdi+40h]; this
0x1800372b1  call    ?GetStringAt@CPropertyName@@QEBAPEBGJ@Z; CPropertyName::GetStringAt(long)
0x1800372b6  mov     r8, rax
0x1800372b9  lea     rdx, aS; "%S "
0x1800372c0  mov     rcx, rbx; Stream
0x1800372c3  call    cs:__imp_fprintf
0x1800372c9  inc     esi
0x1800372cb  cmp     esi, [rdi+30h]
0x1800372ce  jl      short loc_1800372A4
0x1800372d0  lea     rdx, asc_18004D0B8; "\n------------------\n"
0x1800372d7  mov     rcx, rbx; Stream
0x1800372da  call    cs:__imp_fprintf
0x1800372e0  lea     rdx, aTokens; "Tokens:\n"
0x1800372e7  mov     rcx, rbx; Stream
0x1800372ea  call    cs:__imp_fprintf
0x1800372f0  xor     esi, esi
0x1800372f2  cmp     [rdi+8], esi
0x1800372f5  jle     short loc_180037311
0x1800372f7  movsxd  rcx, esi
0x1800372fa  mov     rdx, rbx; struct _iobuf *
0x1800372fd  shl     rcx, 7
0x180037301  add     rcx, [rdi+10h]; this
0x180037305  call    ?Dump@QL_LEVEL_1_TOKEN@@QEAAXPEAU_iobuf@@@Z; QL_LEVEL_1_TOKEN::Dump(_iobuf *)
0x18003730a  inc     esi
0x18003730c  cmp     esi, [rdi+8]
0x18003730f  jl      short loc_1800372F7
0x180037311  lea     rdx, aEndOfExpressio; "---end of expression---\n"
0x180037318  mov     rcx, rbx; Stream
0x18003731b  call    cs:__imp_fprintf
0x180037321  mov     rcx, rbx; Stream
0x180037324  call    cs:__imp_fclose
0x18003732a  mov     rbx, [rsp+28h+arg_0]
0x18003732f  mov     rsi, [rsp+28h+arg_8]
0x180037334  add     rsp, 20h
0x180037338  pop     rdi
0x180037339  retn
```
