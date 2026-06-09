# W3WP_HOST::RemoveFromActiveProtocolsList(ushort const *)

- ea: `0x180006bb0`
- end: `0x180006c3f`
- name: `?RemoveFromActiveProtocolsList@W3WP_HOST@@AEAAHPEBG@Z`
- size: `143`
- prototype: `int(W3WP_HOST *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800075dc`

## callees

- `0x180003f88`
- `0x180006bb0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180006bf4`
- `msvcrt!_wcsicmp` at `0x180006bf4`

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
    v5 = &dword_18000FB84;
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
0x180006bb0  mov     [rsp+arg_8], rbx
0x180006bb5  mov     [rsp+arg_10], rbp
0x180006bba  push    rsi
0x180006bbb  push    rdi
0x180006bbc  push    r14
0x180006bbe  sub     rsp, 20h
0x180006bc2  mov     rbp, rdx
0x180006bc5  mov     rsi, rcx
0x180006bc8  xor     ebx, ebx
0x180006bca  cmp     ebx, [rsi+160h]
0x180006bd0  jnb     short loc_180006C29
0x180006bd2  lea     r14, [rsi+158h]
0x180006bd9  mov     rcx, rbp; String1
0x180006bdc  mov     rax, [r14]
0x180006bdf  lea     rdx, dword_18000FB84
0x180006be6  mov     rdi, [rax+rbx*8]
0x180006bea  cmp     qword ptr [rdi+8], 0
0x180006bef  cmovnz  rdx, [rdi+8]; String2
0x180006bf4  call    cs:__imp__wcsicmp
0x180006bfb  nop     dword ptr [rax+rax+00h]
0x180006c00  test    eax, eax
0x180006c02  jz      short loc_180006C08
0x180006c04  inc     ebx
0x180006c06  jmp     short loc_180006BCA
0x180006c08  or      r8d, 0FFFFFFFFh
0x180006c0c  lock xadd [rdi+10h], r8d
0x180006c12  cmp     r8d, 1
0x180006c16  jnz     short loc_180006C22
0x180006c18  mov     edx, ebx; unsigned int
0x180006c1a  mov     rcx, r14; this
0x180006c1d  call    ?DeleteEntry@ARRAY_LIST@@QEAAJK@Z; ARRAY_LIST::DeleteEntry(ulong)
0x180006c22  mov     eax, 1
0x180006c27  jmp     short loc_180006C2B
0x180006c29  xor     eax, eax
0x180006c2b  mov     rbx, [rsp+38h+arg_8]
0x180006c30  mov     rbp, [rsp+38h+arg_10]
0x180006c35  add     rsp, 20h
0x180006c39  pop     r14
0x180006c3b  pop     rdi
0x180006c3c  pop     rsi
0x180006c3d  retn
```
