# _anonymous_namespace_::cab_file::close

- ea: `0x1800402d4`
- end: `0x1800403ac`
- name: `_anonymous_namespace_::cab_file::close`
- size: `216`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003f484`
- `0x18003f620`
- `0x18003ff00`
- `0x18003ff60`
- `0x18003ff90`

## callees

- `0x18003b0bc`
- `0x1800402d4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x180040334`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x180040334`
- `Cabinet!__imp_FCIFlushCabinet` at `0x180040303`
- `Cabinet!__imp_FCIFlushCabinet` at `0x180040303`
- `Cabinet!__imp_FCIDestroy` at `0x18004030d`
- `Cabinet!__imp_FCIDestroy` at `0x18004030d`

## pseudocode

```c
_BYTE *__fastcall anonymous_namespace_::cab_file::close(__int64 a1, char a2)
{
  void *v3; // rcx
  __int64 v4; // rsi
  __int64 i; // rdi
  const CHAR *v6; // rcx
  __int64 v7; // rsi
  __int64 v8; // rdi
  _BYTE *result; // rax
  _QWORD *v10; // rbx

  v3 = *(void **)(a1 + 72);
  if ( v3 )
  {
    if ( a2 )
      FCIFlushCabinet(v3, 0, anonymous_namespace_::cab_file::fci_get_next_cab, _scrt_stub_for_is_c_termination_complete);
    FCIDestroy(*(HFCI *)(a1 + 72));
    *(_QWORD *)(a1 + 72) = 0;
  }
  v4 = *(_QWORD *)(a1 + 88);
  for ( i = *(_QWORD *)(a1 + 80); i != v4; i += 32 )
  {
    if ( *(_QWORD *)(i + 24) <= 0xFu )
      v6 = (const CHAR *)i;
    else
      v6 = *(const CHAR **)i;
    DeleteFileA(v6);
  }
  v7 = *(_QWORD *)(a1 + 88);
  v8 = *(_QWORD *)(a1 + 80);
  if ( v8 != v7 )
  {
    do
    {
      std::string::~string(v8);
      v8 += 32;
    }
    while ( v8 != v7 );
    *(_QWORD *)(a1 + 88) = *(_QWORD *)(a1 + 80);
  }
  *(_QWORD *)(a1 + 16) = 0;
  if ( *(_QWORD *)(a1 + 24) <= 0xFu )
    result = (_BYTE *)a1;
  else
    result = *(_BYTE **)a1;
  v10 = (_QWORD *)(a1 + 32);
  *result = 0;
  v10[2] = 0;
  if ( v10[3] > 0xFu )
    v10 = (_QWORD *)*v10;
  *(_BYTE *)v10 = 0;
  return result;
}

```

## disassembly

```asm
0x1800402d4  mov     [rsp+arg_0], rbx
0x1800402d9  mov     [rsp+arg_8], rsi
0x1800402de  push    rdi
0x1800402df  sub     rsp, 20h
0x1800402e3  mov     rbx, rcx
0x1800402e6  mov     rcx, [rcx+48h]; hfci
0x1800402ea  test    rcx, rcx
0x1800402ed  jz      short loc_18004031B
0x1800402ef  test    dl, dl
0x1800402f1  jz      short loc_180040309
0x1800402f3  lea     r9, __scrt_stub_for_is_c_termination_complete; pfnfcis
0x1800402fa  xor     edx, edx; fGetNextCab
0x1800402fc  lea     r8, _anonymous_namespace___cab_file__fci_get_next_cab; pfnfcignc
0x180040303  call    cs:__imp_FCIFlushCabinet
0x180040309  mov     rcx, [rbx+48h]; hfci
0x18004030d  call    cs:__imp_FCIDestroy
0x180040313  mov     qword ptr [rbx+48h], 0
0x18004031b  mov     rsi, [rbx+58h]
0x18004031f  mov     rdi, [rbx+50h]
0x180040323  jmp     short loc_18004033E
0x180040325  cmp     qword ptr [rdi+18h], 0Fh
0x18004032a  jbe     short loc_180040331
0x18004032c  mov     rcx, [rdi]
0x18004032f  jmp     short loc_180040334
0x180040331  mov     rcx, rdi; lpFileName
0x180040334  call    cs:__imp_DeleteFileA
0x18004033a  add     rdi, 20h ; ' '
0x18004033e  cmp     rdi, rsi
0x180040341  jnz     short loc_180040325
0x180040343  mov     rsi, [rbx+58h]
0x180040347  mov     rdi, [rbx+50h]
0x18004034b  cmp     rdi, rsi
0x18004034e  jz      short loc_180040369
0x180040350  mov     rcx, rdi
0x180040353  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180040358  add     rdi, 20h ; ' '
0x18004035c  cmp     rdi, rsi
0x18004035f  jnz     short loc_180040350
0x180040361  mov     rax, [rbx+50h]
0x180040365  mov     [rbx+58h], rax
0x180040369  mov     qword ptr [rbx+10h], 0
0x180040371  cmp     qword ptr [rbx+18h], 0Fh
0x180040376  jbe     short loc_18004037D
0x180040378  mov     rax, [rbx]
0x18004037b  jmp     short loc_180040380
0x18004037d  mov     rax, rbx
0x180040380  add     rbx, 20h ; ' '
0x180040384  mov     byte ptr [rax], 0
0x180040387  mov     qword ptr [rbx+10h], 0
0x18004038f  cmp     qword ptr [rbx+18h], 0Fh
0x180040394  jbe     short loc_180040399
0x180040396  mov     rbx, [rbx]
0x180040399  mov     rsi, [rsp+28h+arg_8]
0x18004039e  mov     byte ptr [rbx], 0
0x1800403a1  mov     rbx, [rsp+28h+arg_0]
0x1800403a6  add     rsp, 20h
0x1800403aa  pop     rdi
0x1800403ab  retn
```
