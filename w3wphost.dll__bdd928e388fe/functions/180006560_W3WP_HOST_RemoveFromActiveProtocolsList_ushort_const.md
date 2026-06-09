# W3WP_HOST::RemoveFromActiveProtocolsList(ushort const *)

- ea: `0x180006560`
- end: `0x1800065e8`
- name: `?RemoveFromActiveProtocolsList@W3WP_HOST@@AEAAHPEBG@Z`
- size: `136`
- prototype: `int(W3WP_HOST *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006f04`

## callees

- `0x180003c88`
- `0x180006560`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800065a4`
- `msvcrt!_wcsicmp` at `0x1800065a4`

## pseudocode

```c
__int64 __fastcall W3WP_HOST::RemoveFromActiveProtocolsList(W3WP_HOST *this, const unsigned __int16 *a2)
{
  __int64 i; // rbx
  const wchar_t *v5; // rdx
  __int64 v6; // rdi

  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= *((_DWORD *)this + 88) )
      return 0;
    v5 = &dword_18000EB74;
    v6 = *(_QWORD *)(*((_QWORD *)this + 43) + 8 * i);
    if ( *(_QWORD *)(v6 + 8) )
      v5 = *(const wchar_t **)(v6 + 8);
    if ( !_wcsicmp(a2, v5) )
      break;
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v6 + 16), 0xFFFFFFFF) == 1 )
    ARRAY_LIST::DeleteEntry((W3WP_HOST *)((char *)this + 344), i);
  return 1;
}

```

## disassembly

```asm
0x180006560  mov     [rsp+arg_8], rbx
0x180006565  mov     [rsp+arg_10], rbp
0x18000656a  push    rsi
0x18000656b  push    rdi
0x18000656c  push    r14
0x18000656e  sub     rsp, 20h
0x180006572  mov     rbp, rdx
0x180006575  mov     rsi, rcx
0x180006578  xor     ebx, ebx
0x18000657a  cmp     ebx, [rsi+160h]
0x180006580  jnb     short loc_1800065D3
0x180006582  lea     r14, [rsi+158h]
0x180006589  mov     rcx, rbp; String1
0x18000658c  mov     rax, [r14]
0x18000658f  lea     rdx, dword_18000EB74
0x180006596  mov     rdi, [rax+rbx*8]
0x18000659a  cmp     qword ptr [rdi+8], 0
0x18000659f  cmovnz  rdx, [rdi+8]; String2
0x1800065a4  call    cs:__imp__wcsicmp
0x1800065aa  test    eax, eax
0x1800065ac  jz      short loc_1800065B2
0x1800065ae  inc     ebx
0x1800065b0  jmp     short loc_18000657A
0x1800065b2  or      r8d, 0FFFFFFFFh
0x1800065b6  lock xadd [rdi+10h], r8d
0x1800065bc  cmp     r8d, 1
0x1800065c0  jnz     short loc_1800065CC
0x1800065c2  mov     edx, ebx; unsigned int
0x1800065c4  mov     rcx, r14; this
0x1800065c7  call    ?DeleteEntry@ARRAY_LIST@@QEAAJK@Z; ARRAY_LIST::DeleteEntry(ulong)
0x1800065cc  mov     eax, 1
0x1800065d1  jmp     short loc_1800065D5
0x1800065d3  xor     eax, eax
0x1800065d5  mov     rbx, [rsp+38h+arg_8]
0x1800065da  mov     rbp, [rsp+38h+arg_10]
0x1800065df  add     rsp, 20h
0x1800065e3  pop     r14
0x1800065e5  pop     rdi
0x1800065e6  pop     rsi
0x1800065e7  retn
```
