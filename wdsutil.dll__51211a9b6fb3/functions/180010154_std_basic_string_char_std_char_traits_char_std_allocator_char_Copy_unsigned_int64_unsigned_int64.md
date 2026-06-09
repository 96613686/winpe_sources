# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180010154`
- end: `0x180010253`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `255`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800102f4`
- `0x1800103ec`
- `0x180015ae0`

## callees

- `0x180001374`
- `0x180001518`
- `0x180001d66`
- `0x180010154`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001021a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001021a`

## pseudocode

```c
size_t *__fastcall std::string::_Copy(const void **Src, unsigned __int64 a2, size_t a3)
{
  size_t v3; // r14
  unsigned __int64 v4; // rdi
  const void **v5; // rbx
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  void *v9; // rsi
  const void *v10; // rdx
  size_t *result; // rax
  void *v12; // rax
  _QWORD *v13; // rdx
  _QWORD v14[11]; // [rsp+0h] [rbp-58h] BYREF
  void *v18; // [rsp+78h] [rbp+20h]

  v14[4] = -2;
  v3 = a3;
  v4 = a2;
  v5 = Src;
  v6 = a2 | 0xF;
  if ( v6 != -1 )
  {
    v4 = v6;
    v7 = (unsigned __int64)Src[3];
    v8 = v7 >> 1;
    if ( v7 >> 1 > v6 / 3 )
    {
      v4 = v8 + v7;
      if ( v7 > -2LL - v8 )
        v4 = -2;
    }
  }
  try
  {
    if ( v4 == -1 )
    {
      v9 = 0;
    }
    else
    {
      v9 = operator new(v4 + 1);
      if ( !v9 )
        std::_Xbad_alloc();
    }
  }
  catch ( ... )
  {
    try
    {
      v12 = 0;
      if ( a2 != -1 )
      {
        v12 = operator new(a2 + 1);
        if ( !v12 )
          std::_Xbad_alloc();
      }
      v18 = v12;
    }
    catch ( ... )
    {
      v13 = v14;
      LOBYTE(v13) = 1;
      std::string::_Tidy(Src, v13, 0);
      throw;
    }
    v5 = Src;
    v3 = a3;
    v4 = a2;
    v9 = v18;
  }
  if ( v3 )
  {
    if ( (unsigned __int64)v5[3] < 0x10 )
      v10 = v5;
    else
      v10 = *v5;
    memcpy_0(v9, v10, v3);
  }
  if ( (unsigned __int64)v5[3] >= 0x10 )
    operator delete((void *)*v5);
  result = (size_t *)(v5 + 2);
  *v5 = v9;
  v5[3] = (const void *)v4;
  if ( v4 >= 0x10 )
    v5 = (const void **)v9;
  *result = v3;
  *((_BYTE *)v5 + v3) = 0;
  return result;
}

```

## disassembly

```asm
0x180010154  mov     rax, rsp
0x180010157  mov     [rax+18h], r8
0x18001015b  mov     [rax+10h], rdx
0x18001015f  mov     [rax+8], rcx
0x180010163  push    rbx
0x180010164  push    rsi
0x180010165  push    rdi
0x180010166  push    r14
0x180010168  sub     rsp, 38h
0x18001016c  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x180010174  mov     r14, r8
0x180010177  mov     rdi, rdx
0x18001017a  mov     rbx, rcx
0x18001017d  or      rdx, 0Fh
0x180010181  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180010188  cmp     rdx, r9
0x18001018b  ja      short loc_1800101C1
0x18001018d  mov     rdi, rdx
0x180010190  mov     r8, [rcx+18h]
0x180010194  mov     rcx, r8
0x180010197  shr     rcx, 1
0x18001019a  mov     rax, 0AAAAAAAAAAAAAAABh
0x1800101a4  mul     rdx
0x1800101a7  shr     rdx, 1
0x1800101aa  cmp     rcx, rdx
0x1800101ad  jbe     short loc_1800101C1
0x1800101af  mov     rax, r9
0x1800101b2  sub     rax, rcx
0x1800101b5  cmp     r8, rax
0x1800101b8  lea     rdi, [rcx+r8]
0x1800101bc  jbe     short loc_1800101C1
0x1800101be  mov     rdi, r9
0x1800101c1  lea     rcx, [rdi+1]; Size
0x1800101c5  test    rcx, rcx
0x1800101c8  jz      short loc_1800101D9
0x1800101ca  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800101cf  mov     rsi, rax
0x1800101d2  test    rax, rax
0x1800101d5  jz      short loc_18001024C
0x1800101d7  jmp     short loc_1800101DB
0x1800101d9  xor     esi, esi
0x1800101db  jmp     short loc_1800101F1
0x1800101dd  mov     rbx, [rsp+58h+arg_0]
0x1800101e2  mov     r14, [rsp+58h+arg_10]
0x1800101e7  mov     rdi, [rsp+58h+arg_8]
0x1800101ec  mov     rsi, [rsp+58h+arg_18]
0x1800101f1  test    r14, r14
0x1800101f4  jz      short loc_180010210
0x1800101f6  cmp     qword ptr [rbx+18h], 10h
0x1800101fb  jb      short loc_180010202
0x1800101fd  mov     rdx, [rbx]
0x180010200  jmp     short loc_180010205
0x180010202  mov     rdx, rbx; Src
0x180010205  mov     r8, r14; Size
0x180010208  mov     rcx, rsi; void *
0x18001020b  call    memcpy_0
0x180010210  cmp     qword ptr [rbx+18h], 10h
0x180010215  jb      short loc_180010226
0x180010217  mov     rcx, [rbx]
0x18001021a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180010221  nop     dword ptr [rax+rax+00h]
0x180010226  lea     rax, [rbx+10h]
0x18001022a  mov     [rbx], rsi
0x18001022d  mov     [rbx+18h], rdi
0x180010231  cmp     rdi, 10h
0x180010235  cmovnb  rbx, rsi
0x180010239  mov     [rax], r14
0x18001023c  mov     byte ptr [rbx+r14], 0
0x180010241  add     rsp, 38h
0x180010245  pop     r14
0x180010247  pop     rdi
0x180010248  pop     rsi
0x180010249  pop     rbx
0x18001024a  retn
0x18001024c  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
