# CWdsMetadataEntry::ToString(ushort * *)

- ea: `0x18000a3f0`
- end: `0x18000a546`
- name: `?ToString@CWdsMetadataEntry@@QEBAKPEAPEAG@Z`
- size: `342`
- prototype: `__int64 __fastcall(CWdsMetadataEntry *this, unsigned __int16 **)`
- caller_count: `7`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000af78`
- `0x18000b228`
- `0x18000b834`
- `0x18000b92c`
- `0x18000dab4`
- `0x1800114a4`
- `0x180012480`

## callees

- `0x1800085fc`
- `0x18000a3f0`
- `0x180014ee0`
- `0x1800150b8`
- `0x1800157a4`

## pseudocode

```c
__int64 __fastcall CWdsMetadataEntry::ToString(CWdsMetadataEntry *this, unsigned __int16 **a2)
{
  __int64 v3; // rcx
  __int64 v4; // rax
  unsigned int v6; // esi
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rcx
  unsigned __int64 v10; // rbp
  unsigned __int64 v11; // rax
  wchar_t *v12; // rbx
  const wchar_t *v13; // r9
  const OLECHAR *v14; // r8
  const unsigned __int16 *v15; // rcx
  int v16; // edi
  const char *v17; // rdx

  v3 = *(_QWORD *)this;
  v4 = -1;
  v6 = 0;
  do
    ++v4;
  while ( *(_WORD *)(v3 + 2 * v4) );
  v7 = *((_QWORD *)this + 2);
  if ( v7 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)(v7 + 2 * v8) );
    v4 += v8 + 2;
  }
  v9 = -1;
  do
    ++v9;
  while ( *(_WORD *)(*((_QWORD *)this + 1) + 2 * v9) );
  v10 = v4 + v9 + 2;
  v11 = 2 * v10;
  if ( !is_mul_ok(v10, 2u) )
    v11 = -1;
  v12 = (wchar_t *)operator new[](v11, (const struct std::nothrow_t *)&std::nothrow);
  if ( v12 )
  {
    v13 = &word_18001870C;
    v14 = &word_18001870C;
    v15 = &word_18001870C;
    if ( *((_QWORD *)this + 2) )
    {
      v15 = L"]";
      v14 = (const OLECHAR *)*((_QWORD *)this + 2);
      v13 = L"[";
    }
    v16 = StringCchPrintfW(v12, v10, L"%s%s%s%s=%s", *(_QWORD *)this, v13, v14, v15, *((_QWORD *)this + 1));
    if ( (int)ElValidateHr(v16, v17, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x9F1u) >= 0 )
    {
      *a2 = v12;
      v12 = 0;
    }
    else if ( v16 < 0 && (v16 & 0x1FFF0000) == 0x70000 )
    {
      v6 = (unsigned __int16)v16;
    }
    else
    {
      v6 = v16;
    }
    if ( v12 )
      operator delete(v12);
  }
  else
  {
    return 8;
  }
  return v6;
}

```

## disassembly

```asm
0x18000a3f0  mov     [rsp+arg_0], rbx
0x18000a3f5  mov     [rsp+arg_8], rbp
0x18000a3fa  mov     [rsp+arg_10], rsi
0x18000a3ff  push    rdi
0x18000a400  push    r14
0x18000a402  push    r15
0x18000a404  sub     rsp, 40h
0x18000a408  xor     r15d, r15d
0x18000a40b  mov     rdi, rcx
0x18000a40e  mov     rcx, [rcx]
0x18000a411  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000a415  mov     rax, r8
0x18000a418  mov     r14, rdx
0x18000a41b  mov     esi, r15d
0x18000a41e  inc     rax
0x18000a421  cmp     [rcx+rax*2], r15w
0x18000a426  jnz     short loc_18000A41E
0x18000a428  mov     rdx, [rdi+10h]
0x18000a42c  test    rdx, rdx
0x18000a42f  jz      short loc_18000A445
0x18000a431  mov     rcx, r8
0x18000a434  inc     rcx
0x18000a437  cmp     [rdx+rcx*2], r15w
0x18000a43c  jnz     short loc_18000A434
0x18000a43e  add     rax, 2
0x18000a442  add     rax, rcx
0x18000a445  mov     rdx, [rdi+8]
0x18000a449  mov     rcx, r8
0x18000a44c  inc     rcx
0x18000a44f  cmp     [rdx+rcx*2], r15w
0x18000a454  jnz     short loc_18000A44C
0x18000a456  lea     rbp, [rcx+2]
0x18000a45a  add     rbp, rax
0x18000a45d  mov     eax, 2
0x18000a462  mul     rbp
0x18000a465  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a46c  cmovo   rax, r8
0x18000a470  mov     rcx, rax; unsigned __int64
0x18000a473  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000a478  mov     rbx, rax
0x18000a47b  test    rax, rax
0x18000a47e  jnz     short loc_18000A488
0x18000a480  lea     esi, [rax+8]
0x18000a483  jmp     loc_18000A52B
0x18000a488  mov     rax, [rdi+10h]
0x18000a48c  lea     r9, word_18001870C
0x18000a493  test    rax, rax
0x18000a496  lea     rdx, asc_180018D04; "]"
0x18000a49d  mov     r8, r9
0x18000a4a0  mov     rcx, r9
0x18000a4a3  cmovnz  rcx, rdx
0x18000a4a7  cmovnz  r8, rax
0x18000a4ab  mov     rax, [rdi+8]
0x18000a4af  lea     rdx, asc_180018D08; "["
0x18000a4b6  mov     [rsp+58h+var_20], rax
0x18000a4bb  cmovnz  r9, rdx
0x18000a4bf  mov     [rsp+58h+var_28], rcx
0x18000a4c4  mov     rdx, rbp; unsigned __int64
0x18000a4c7  mov     [rsp+58h+var_30], r8
0x18000a4cc  mov     rcx, rbx; Buffer
0x18000a4cf  mov     [rsp+58h+var_38], r9
0x18000a4d4  lea     r8, aSSSSS; "%s%s%s%s=%s"
0x18000a4db  mov     r9, [rdi]
0x18000a4de  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a4e3  mov     r9d, 9F1h; unsigned int
0x18000a4e9  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000a4f0  mov     ecx, eax; int
0x18000a4f2  mov     edi, eax
0x18000a4f4  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000a4f9  test    eax, eax
0x18000a4fb  jns     short loc_18000A518
0x18000a4fd  test    edi, edi
0x18000a4ff  jns     short loc_18000A514
0x18000a501  mov     eax, edi
0x18000a503  and     eax, 1FFF0000h
0x18000a508  cmp     eax, 70000h
0x18000a50d  jnz     short loc_18000A514
0x18000a50f  movzx   esi, di
0x18000a512  jmp     short loc_18000A51E
0x18000a514  mov     esi, edi
0x18000a516  jmp     short loc_18000A51E
0x18000a518  mov     [r14], rbx
0x18000a51b  mov     rbx, r15
0x18000a51e  test    rbx, rbx
0x18000a521  jz      short loc_18000A52B
0x18000a523  mov     rcx, rbx; Block
0x18000a526  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a52b  mov     rbx, [rsp+58h+arg_0]
0x18000a530  mov     eax, esi
0x18000a532  mov     rsi, [rsp+58h+arg_10]
0x18000a537  mov     rbp, [rsp+58h+arg_8]
0x18000a53c  add     rsp, 40h
0x18000a540  pop     r15
0x18000a542  pop     r14
0x18000a544  pop     rdi
0x18000a545  retn
```
