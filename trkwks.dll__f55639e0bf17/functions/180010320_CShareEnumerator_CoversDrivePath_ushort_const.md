# CShareEnumerator::CoversDrivePath(ushort const *)

- ea: `0x180010320`
- end: `0x18001039e`
- name: `?CoversDrivePath@CShareEnumerator@@QEAAHPEBG@Z`
- size: `126`
- prototype: `_BOOL8 __fastcall(CShareEnumerator *this, wchar_t *String2)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000fa10`

## callees

- `0x18000fc64`
- `0x180010320`
- `0x180010d6c`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18001037b`
- `msvcrt!_wcsnicmp` at `0x18001037b`

## pseudocode

```c
_BOOL8 __fastcall CShareEnumerator::CoversDrivePath(CShareEnumerator *this, wchar_t *String2)
{
  __int64 v4; // r9
  unsigned int CCHSharePath; // eax
  unsigned __int64 v6; // r9
  unsigned int v7; // eax

  if ( !(unsigned int)CShareEnumerator::_IsValidShare(this) )
    return 0;
  v4 = -1;
  do
    ++v4;
  while ( String2[v4] );
  CCHSharePath = CShareEnumerator::QueryCCHSharePath(this);
  if ( CCHSharePath > v6 )
    return 0;
  v7 = CShareEnumerator::QueryCCHSharePath(this);
  return _wcsnicmp(*(const wchar_t **)(*((_QWORD *)this + 7) + 72LL * *((unsigned int *)this + 12) + 40), String2, v7) == 0;
}

```

## disassembly

```asm
0x180010320  mov     [rsp+arg_0], rbx
0x180010325  mov     [rsp+arg_8], rsi
0x18001032a  push    rdi
0x18001032b  sub     rsp, 20h
0x18001032f  mov     rdi, rdx
0x180010332  mov     rbx, rcx
0x180010335  call    ?_IsValidShare@CShareEnumerator@@AEAAHXZ; CShareEnumerator::_IsValidShare(void)
0x18001033a  xor     esi, esi
0x18001033c  test    eax, eax
0x18001033e  jz      short loc_18001038C
0x180010340  or      r9, 0FFFFFFFFFFFFFFFFh
0x180010344  inc     r9
0x180010347  cmp     [rdi+r9*2], si
0x18001034c  jnz     short loc_180010344
0x18001034e  mov     rcx, rbx; this
0x180010351  call    ?QueryCCHSharePath@CShareEnumerator@@QEAAKXZ; CShareEnumerator::QueryCCHSharePath(void)
0x180010356  mov     ecx, eax
0x180010358  cmp     rcx, r9
0x18001035b  ja      short loc_18001038C
0x18001035d  mov     rcx, rbx; this
0x180010360  call    ?QueryCCHSharePath@CShareEnumerator@@QEAAKXZ; CShareEnumerator::QueryCCHSharePath(void)
0x180010365  mov     rcx, [rbx+38h]
0x180010369  mov     rdx, rdi; String2
0x18001036c  mov     r8d, eax; MaxCount
0x18001036f  mov     eax, [rbx+30h]
0x180010372  lea     r9, [rax+rax*8]
0x180010376  mov     rcx, [rcx+r9*8+28h]; String1
0x18001037b  call    cs:__imp__wcsnicmp
0x180010381  test    eax, eax
0x180010383  mov     ecx, esi
0x180010385  setz    cl
0x180010388  mov     eax, ecx
0x18001038a  jmp     short loc_18001038E
0x18001038c  xor     eax, eax
0x18001038e  mov     rbx, [rsp+28h+arg_0]
0x180010393  mov     rsi, [rsp+28h+arg_8]
0x180010398  add     rsp, 20h
0x18001039c  pop     rdi
0x18001039d  retn
```
