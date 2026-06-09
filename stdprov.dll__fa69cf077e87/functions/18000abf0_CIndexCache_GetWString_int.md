# CIndexCache::GetWString(int)

- ea: `0x18000abf0`
- end: `0x18000ac70`
- name: `?GetWString@CIndexCache@@QEAAPEAGH@Z`
- size: `128`
- prototype: `unsigned __int16 *__fastcall(CIndexCache *__hidden this, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800040c8`

## callees

- `0x180002e10`
- `0x18000abf0`

## import_xrefs

- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18000ac07`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18000ac07`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000ac3d`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000ac3d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
unsigned __int16 *__fastcall CIndexCache::GetWString(CIndexCache *this, int a2)
{
  CFlexArray *v2; // rcx
  _QWORD *v3; // rax
  _QWORD *v4; // rbx
  __int64 v5; // rcx
  __int64 v6; // rax
  unsigned int v7; // edi
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // r10

  v2 = (CIndexCache *)((char *)this + 8);
  if ( a2 >= *(_DWORD *)v2 )
    return 0;
  v3 = CFlexArray::GetAt(v2, a2);
  v4 = v3;
  if ( !v3 )
    return 0;
  v5 = v3[3];
  v6 = -1;
  do
    ++v6;
  while ( *(_WORD *)(v5 + 2 * v6) );
  v7 = v6 + 1;
  v8 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul((unsigned int)(v6 + 1), 2u));
  v9 = v8;
  if ( v8 )
    StringCchCopyW(v8, v7, (const unsigned __int16 *)v4[3]);
  return v9;
}

```

## disassembly

```asm
0x18000abf0  mov     [rsp+arg_0], rbx
0x18000abf5  mov     [rsp+arg_8], rsi
0x18000abfa  push    rdi
0x18000abfb  sub     rsp, 20h
0x18000abff  add     rcx, 8
0x18000ac03  cmp     edx, [rcx]
0x18000ac05  jge     short loc_18000AC5E
0x18000ac07  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x18000ac0d  xor     esi, esi
0x18000ac0f  mov     rbx, rax
0x18000ac12  test    rax, rax
0x18000ac15  jz      short loc_18000AC5E
0x18000ac17  mov     rcx, [rax+18h]
0x18000ac1b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000ac1f  mov     rax, r8
0x18000ac22  inc     rax
0x18000ac25  cmp     [rcx+rax*2], si
0x18000ac29  jnz     short loc_18000AC22
0x18000ac2b  lea     edi, [rax+1]
0x18000ac2e  mov     eax, 2
0x18000ac33  mul     rdi
0x18000ac36  cmovb   rax, r8
0x18000ac3a  mov     rcx, rax
0x18000ac3d  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000ac43  mov     r10, rax
0x18000ac46  test    rax, rax
0x18000ac49  jz      short loc_18000AC59
0x18000ac4b  mov     r8, [rbx+18h]; unsigned __int16 *
0x18000ac4f  mov     edx, edi; unsigned __int64
0x18000ac51  mov     rcx, rax; unsigned __int16 *
0x18000ac54  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ac59  mov     rax, r10
0x18000ac5c  jmp     short loc_18000AC60
0x18000ac5e  xor     eax, eax
0x18000ac60  mov     rbx, [rsp+28h+arg_0]
0x18000ac65  mov     rsi, [rsp+28h+arg_8]
0x18000ac6a  add     rsp, 20h
0x18000ac6e  pop     rdi
0x18000ac6f  retn
```
