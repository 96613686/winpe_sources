# GrowListDeleteItem

- ea: `0x180022160`
- end: `0x1800221e6`
- name: `GrowListDeleteItem`
- size: `134`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180009aec`

## callees

- `0x180020e24`
- `0x180020e70`
- `0x180022160`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800221b4`
- `msvcrt!memmove_s` at `0x1800221b4`

## pseudocode

```c
__int64 __fastcall GrowListDeleteItem(_QWORD **a1, unsigned int a2)
{
  _QWORD *v2; // rbx
  __int64 v3; // r9
  unsigned __int64 v4; // rcx
  unsigned __int64 v5; // rdx
  unsigned __int64 v6; // rdx
  errno_t v7; // eax
  __int64 v9; // [rsp+28h] [rbp-10h] BYREF

  if ( !a1 )
    return 0;
  v2 = *a1;
  if ( !*a1 )
    return 0;
  v3 = a2;
  if ( (unsigned __int64)a2 >= v2[1] )
    return 0;
  v4 = a2 + 1LL;
  if ( v4 < a2 || (v5 = v2[1], v4 > v5) )
    ATL::AtlThrowImpl(-2147024809);
  v6 = v5 - v4;
  if ( v6 )
  {
    v7 = memmove_s((void *const)(*v2 + 8 * v3), 8 * v6, (const void *const)(*v2 + 8 * v4), 8 * v6);
    try
    {
      ATL::AtlCrtErrorCheck(v7);
    }
    catch ( ATL::CAtlException v9 )
    {
      return 0;
    }
  }
  --v2[1];
  return 1;
}

```

## disassembly

```asm
0x180022160  push    rbx
0x180022162  sub     rsp, 30h
0x180022166  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18002216f  test    rcx, rcx
0x180022172  jz      short loc_1800221DD
0x180022174  mov     rbx, [rcx]
0x180022177  test    rbx, rbx
0x18002217a  jz      short loc_1800221DD
0x18002217c  mov     r9d, edx
0x18002217f  cmp     r9, [rbx+8]
0x180022183  jnb     short loc_1800221DD
0x180022185  lea     rcx, [r9+1]
0x180022189  cmp     rcx, r9
0x18002218c  jb      short loc_1800221D2
0x18002218e  cmp     rcx, 1
0x180022192  jb      short loc_1800221D2
0x180022194  mov     rdx, [rbx+8]
0x180022198  cmp     rcx, rdx
0x18002219b  ja      short loc_1800221D2
0x18002219d  sub     rdx, rcx
0x1800221a0  jz      short loc_1800221C7
0x1800221a2  mov     rax, [rbx]
0x1800221a5  shl     rdx, 3; DestinationSize
0x1800221a9  lea     r8, [rax+rcx*8]; Source
0x1800221ad  lea     rcx, [rax+r9*8]; Destination
0x1800221b1  mov     r9, rdx; SourceSize
0x1800221b4  call    cs:__imp_memmove_s
0x1800221bb  nop     dword ptr [rax+rax+00h]
0x1800221c0  mov     ecx, eax; int
0x1800221c2  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800221c7  dec     qword ptr [rbx+8]
0x1800221cb  mov     eax, 1
0x1800221d0  jmp     short loc_1800221DF
0x1800221d2  mov     ecx, 80070057h; int
0x1800221d7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800221dd  xor     eax, eax
0x1800221df  add     rsp, 30h
0x1800221e3  pop     rbx
0x1800221e4  retn
```
