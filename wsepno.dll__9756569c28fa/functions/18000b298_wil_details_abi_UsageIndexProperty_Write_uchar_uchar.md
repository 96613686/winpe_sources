# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18000b298`
- end: `0x18000b380`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180009638`

## callees

- `0x18000218a`
- `0x180003a28`
- `0x18000b298`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b2fb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b2fb`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Write(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  char v3; // al
  unsigned __int8 *v4; // r9
  unsigned __int8 *v8; // rbx
  _DWORD *v9; // rax
  unsigned __int16 *v10; // rbp
  rsize_t v11; // r9
  bool result; // al

  v3 = *((_BYTE *)this + 2);
  v4 = *a2;
  if ( v3 == 1 )
  {
    v8 = v4 + 2;
    if ( v4 + 2 > a3 )
      return 0;
    if ( v4 )
    {
      *(_WORD *)v4 = *((_WORD *)this + 2);
      goto LABEL_13;
    }
LABEL_11:
    *(_DWORD *)_o__errno(this, a2, a3) = 22;
    invalid_parameter_noinfo();
    goto LABEL_13;
  }
  if ( v3 == 2 )
  {
    v8 = v4 + 4;
    if ( v4 + 4 > a3 )
      return 0;
    if ( v4 )
    {
      v9 = (_DWORD *)((char *)this + 4);
      if ( this != (wil::details_abi::UsageIndexProperty *)-4LL )
      {
        *(_DWORD *)v4 = *v9;
        goto LABEL_13;
      }
      *(_DWORD *)v4 = (_DWORD)v9;
    }
    goto LABEL_11;
  }
  v8 = *a2;
LABEL_13:
  if ( !*(_WORD *)this )
  {
    if ( v8 + 2 <= a3 )
    {
      v10 = (unsigned __int16 *)((char *)this + 8);
      memcpy_s(v8, a3 - v8, (char *)this + 8, 2u);
      v8 += 2;
      goto LABEL_17;
    }
    return 0;
  }
  v10 = (unsigned __int16 *)((char *)this + 8);
LABEL_17:
  v11 = *v10;
  if ( &v8[v11] > a3 )
    return 0;
  memcpy_s(v8, a3 - v8, *((const void *const *)this + 3), v11);
  result = 1;
  *a2 = &v8[*v10];
  return result;
}

```

## disassembly

```asm
0x18000b298  push    rbx
0x18000b29a  push    rbp
0x18000b29b  push    rsi
0x18000b29c  push    rdi
0x18000b29d  push    r14
0x18000b29f  push    r15
0x18000b2a1  sub     rsp, 28h
0x18000b2a5  mov     al, [rcx+2]
0x18000b2a8  xor     ebp, ebp
0x18000b2aa  mov     r9, [rdx]
0x18000b2ad  mov     rdi, r8
0x18000b2b0  mov     r15, rdx
0x18000b2b3  mov     rsi, rcx
0x18000b2b6  cmp     al, 1
0x18000b2b8  jnz     short loc_18000B2D6
0x18000b2ba  lea     rbx, [r9+2]
0x18000b2be  cmp     rbx, r8
0x18000b2c1  ja      loc_18000B351
0x18000b2c7  test    r9, r9
0x18000b2ca  jz      short loc_18000B2FB
0x18000b2cc  movzx   eax, word ptr [rcx+4]
0x18000b2d0  mov     [r9], ax
0x18000b2d4  jmp     short loc_18000B311
0x18000b2d6  cmp     al, 2
0x18000b2d8  jnz     short loc_18000B30E
0x18000b2da  lea     rbx, [r9+4]
0x18000b2de  cmp     rbx, rdi
0x18000b2e1  ja      short loc_18000B351
0x18000b2e3  test    r9, r9
0x18000b2e6  jz      short loc_18000B2FB
0x18000b2e8  lea     rax, [rcx+4]
0x18000b2ec  test    rax, rax
0x18000b2ef  jz      short loc_18000B2F8
0x18000b2f1  mov     eax, [rax]
0x18000b2f3  mov     [r9], eax
0x18000b2f6  jmp     short loc_18000B311
0x18000b2f8  mov     [r9], eax
0x18000b2fb  call    cs:__imp__o__errno
0x18000b301  mov     dword ptr [rax], 16h
0x18000b307  call    _invalid_parameter_noinfo
0x18000b30c  jmp     short loc_18000B311
0x18000b30e  mov     rbx, r9
0x18000b311  cmp     [rsi], bp
0x18000b314  jnz     short loc_18000B33F
0x18000b316  lea     r14, [rbx+2]
0x18000b31a  cmp     r14, rdi
0x18000b31d  ja      short loc_18000B351
0x18000b31f  lea     rbp, [rsi+8]
0x18000b323  mov     rdx, rdi
0x18000b326  sub     rdx, rbx; DestinationSize
0x18000b329  mov     r8, rbp; Source
0x18000b32c  mov     r9d, 2; SourceSize
0x18000b332  mov     rcx, rbx; Destination
0x18000b335  call    memcpy_s
0x18000b33a  mov     rbx, r14
0x18000b33d  jmp     short loc_18000B343
0x18000b33f  lea     rbp, [rsi+8]
0x18000b343  movzx   r9d, word ptr [rbp+0]; SourceSize
0x18000b348  lea     rax, [r9+rbx]
0x18000b34c  cmp     rax, rdi
0x18000b34f  jbe     short loc_18000B355
0x18000b351  xor     al, al
0x18000b353  jmp     short loc_18000B373
0x18000b355  mov     r8, [rsi+18h]; Source
0x18000b359  sub     rdi, rbx
0x18000b35c  mov     rdx, rdi; DestinationSize
0x18000b35f  mov     rcx, rbx; Destination
0x18000b362  call    memcpy_s
0x18000b367  movzx   ecx, word ptr [rbp+0]
0x18000b36b  mov     al, 1
0x18000b36d  add     rcx, rbx
0x18000b370  mov     [r15], rcx
0x18000b373  add     rsp, 28h
0x18000b377  pop     r15
0x18000b379  pop     r14
0x18000b37b  pop     rdi
0x18000b37c  pop     rsi
0x18000b37d  pop     rbp
0x18000b37e  pop     rbx
0x18000b37f  retn
```
