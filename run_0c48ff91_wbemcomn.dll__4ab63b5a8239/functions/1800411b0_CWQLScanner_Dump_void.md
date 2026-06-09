# CWQLScanner::Dump(void)

- ea: `0x1800411b0`
- end: `0x1800412a0`
- name: `?Dump@CWQLScanner@@QEAAXXZ`
- size: `240`
- prototype: `void __fastcall(CWQLScanner *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180007e30`
- `0x180041048`
- `0x1800411b0`

## import_xrefs

- `msvcrt!printf` at `0x1800411c9`
- `msvcrt!printf` at `0x1800411f3`
- `msvcrt!printf` at `0x180041206`
- `msvcrt!printf` at `0x180041234`
- `msvcrt!printf` at `0x18004124d`
- `msvcrt!printf` at `0x18004127d`
- `msvcrt!printf` at `0x1800411c9`
- `msvcrt!printf` at `0x1800411f3`
- `msvcrt!printf` at `0x180041206`
- `msvcrt!printf` at `0x180041234`
- `msvcrt!printf` at `0x18004124d`
- `msvcrt!printf` at `0x18004127d`
- `msvcrt!printf` at `0x180041299`

## string_xrefs

- `0x1800411c2`: `---Token Stream----\n`
- `0x1800411e3`: `Token %d <%S>\n`

## pseudocode

```c
void __fastcall CWQLScanner::Dump(CWQLScanner *this)
{
  int i; // esi
  _DWORD **v3; // rax
  int j; // esi
  const wchar_t ***v5; // rax
  int k; // edi
  SWQLColRef **v7; // rax

  printf("---Token Stream----\n");
  for ( i = 0; i < *((_DWORD *)this + 8); ++i )
  {
    v3 = (_DWORD **)CFlexArray::operator[]((__int64)this + 32, i);
    printf("Token %d <%S>\n", **v3, *((const wchar_t **)*v3 + 1));
  }
  printf("---Table Refs---\n");
  for ( j = 0; j < *((_DWORD *)this + 52); ++j )
  {
    v5 = (const wchar_t ***)CFlexArray::operator[]((__int64)this + 208, j);
    printf("Table = %S  Alias = %S\n", **v5, (*v5)[1]);
  }
  if ( *((_DWORD *)this + 7) )
  {
    printf(" -> COUNT query\n");
  }
  else
  {
    printf("---Select List---\n");
    for ( k = 0; k < *((_DWORD *)this + 30); ++k )
    {
      v7 = (SWQLColRef **)CFlexArray::operator[]((__int64)this + 120, k);
      SWQLColRef::DebugDump(*v7);
    }
  }
  printf("\n\n---<end of dump>---\n\n");
}

```

## disassembly

```asm
0x1800411b0  mov     [rsp+arg_0], rbx
0x1800411b5  mov     [rsp+arg_8], rsi
0x1800411ba  push    rdi
0x1800411bb  sub     rsp, 20h
0x1800411bf  mov     rbx, rcx
0x1800411c2  lea     rcx, aTokenStream; "---Token Stream----\n"
0x1800411c9  call    cs:__imp_printf
0x1800411cf  xor     esi, esi
0x1800411d1  lea     rdi, [rbx+20h]
0x1800411d5  cmp     [rdi], esi
0x1800411d7  jle     short loc_1800411FF
0x1800411d9  mov     edx, esi
0x1800411db  mov     rcx, rdi
0x1800411de  call    ??ACFlexArray@@QEAAAEAPEAXH@Z; CFlexArray::operator[](int)
0x1800411e3  lea     rcx, aTokenDS; "Token %d <%S>\n"
0x1800411ea  mov     rdx, [rax]
0x1800411ed  mov     r8, [rdx+8]
0x1800411f1  mov     edx, [rdx]
0x1800411f3  call    cs:__imp_printf
0x1800411f9  inc     esi
0x1800411fb  cmp     esi, [rdi]
0x1800411fd  jl      short loc_1800411D9
0x1800411ff  lea     rcx, aTableRefs; "---Table Refs---\n"
0x180041206  call    cs:__imp_printf
0x18004120c  xor     esi, esi
0x18004120e  lea     rdi, [rbx+0D0h]
0x180041215  cmp     [rdi], esi
0x180041217  jle     short loc_180041240
0x180041219  mov     edx, esi
0x18004121b  mov     rcx, rdi
0x18004121e  call    ??ACFlexArray@@QEAAAEAPEAXH@Z; CFlexArray::operator[](int)
0x180041223  lea     rcx, aTableSAliasS; "Table = %S  Alias = %S\n"
0x18004122a  mov     rdx, [rax]
0x18004122d  mov     r8, [rdx+8]
0x180041231  mov     rdx, [rdx]
0x180041234  call    cs:__imp_printf
0x18004123a  inc     esi
0x18004123c  cmp     esi, [rdi]
0x18004123e  jl      short loc_180041219
0x180041240  cmp     dword ptr [rbx+1Ch], 0
0x180041244  jnz     short loc_180041276
0x180041246  lea     rcx, aSelectList; "---Select List---\n"
0x18004124d  call    cs:__imp_printf
0x180041253  xor     edi, edi
0x180041255  cmp     [rbx+78h], edi
0x180041258  jle     short loc_180041283
0x18004125a  mov     edx, edi
0x18004125c  lea     rcx, [rbx+78h]
0x180041260  call    ??ACFlexArray@@QEAAAEAPEAXH@Z; CFlexArray::operator[](int)
0x180041265  mov     rcx, [rax]; this
0x180041268  call    ?DebugDump@SWQLColRef@@QEAAXXZ; SWQLColRef::DebugDump(void)
0x18004126d  inc     edi
0x18004126f  cmp     edi, [rbx+78h]
0x180041272  jl      short loc_18004125A
0x180041274  jmp     short loc_180041283
0x180041276  lea     rcx, aCountQuery; " -> COUNT query\n"
0x18004127d  call    cs:__imp_printf
0x180041283  lea     rcx, aEndOfDump; "\n\n---<end of dump>---\n\n"
0x18004128a  mov     rbx, [rsp+28h+arg_0]
0x18004128f  mov     rsi, [rsp+28h+arg_8]
0x180041294  add     rsp, 20h
0x180041298  pop     rdi
0x180041299  jmp     cs:__imp_printf
```
