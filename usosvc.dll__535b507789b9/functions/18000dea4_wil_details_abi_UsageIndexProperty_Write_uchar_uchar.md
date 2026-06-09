# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18000dea4`
- end: `0x18000df8c`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000cba8`

## callees

- `0x18000313a`
- `0x180006a98`
- `0x18000dea4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000df07`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000df07`

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
0x18000dea4  push    rbx
0x18000dea6  push    rbp
0x18000dea7  push    rsi
0x18000dea8  push    rdi
0x18000dea9  push    r14
0x18000deab  push    r15
0x18000dead  sub     rsp, 28h
0x18000deb1  mov     al, [rcx+2]
0x18000deb4  xor     ebp, ebp
0x18000deb6  mov     r9, [rdx]
0x18000deb9  mov     rdi, r8
0x18000debc  mov     r15, rdx
0x18000debf  mov     rsi, rcx
0x18000dec2  cmp     al, 1
0x18000dec4  jnz     short loc_18000DEE2
0x18000dec6  lea     rbx, [r9+2]
0x18000deca  cmp     rbx, r8
0x18000decd  ja      loc_18000DF5D
0x18000ded3  test    r9, r9
0x18000ded6  jz      short loc_18000DF07
0x18000ded8  movzx   eax, word ptr [rcx+4]
0x18000dedc  mov     [r9], ax
0x18000dee0  jmp     short loc_18000DF1D
0x18000dee2  cmp     al, 2
0x18000dee4  jnz     short loc_18000DF1A
0x18000dee6  lea     rbx, [r9+4]
0x18000deea  cmp     rbx, rdi
0x18000deed  ja      short loc_18000DF5D
0x18000deef  test    r9, r9
0x18000def2  jz      short loc_18000DF07
0x18000def4  lea     rax, [rcx+4]
0x18000def8  test    rax, rax
0x18000defb  jz      short loc_18000DF04
0x18000defd  mov     eax, [rax]
0x18000deff  mov     [r9], eax
0x18000df02  jmp     short loc_18000DF1D
0x18000df04  mov     [r9], eax
0x18000df07  call    cs:__imp__o__errno
0x18000df0d  mov     dword ptr [rax], 16h
0x18000df13  call    _invalid_parameter_noinfo
0x18000df18  jmp     short loc_18000DF1D
0x18000df1a  mov     rbx, r9
0x18000df1d  cmp     [rsi], bp
0x18000df20  jnz     short loc_18000DF4B
0x18000df22  lea     r14, [rbx+2]
0x18000df26  cmp     r14, rdi
0x18000df29  ja      short loc_18000DF5D
0x18000df2b  lea     rbp, [rsi+8]
0x18000df2f  mov     rdx, rdi
0x18000df32  sub     rdx, rbx; DestinationSize
0x18000df35  mov     r8, rbp; Source
0x18000df38  mov     r9d, 2; SourceSize
0x18000df3e  mov     rcx, rbx; Destination
0x18000df41  call    memcpy_s
0x18000df46  mov     rbx, r14
0x18000df49  jmp     short loc_18000DF4F
0x18000df4b  lea     rbp, [rsi+8]
0x18000df4f  movzx   r9d, word ptr [rbp+0]; SourceSize
0x18000df54  lea     rax, [r9+rbx]
0x18000df58  cmp     rax, rdi
0x18000df5b  jbe     short loc_18000DF61
0x18000df5d  xor     al, al
0x18000df5f  jmp     short loc_18000DF7F
0x18000df61  mov     r8, [rsi+18h]; Source
0x18000df65  sub     rdi, rbx
0x18000df68  mov     rdx, rdi; DestinationSize
0x18000df6b  mov     rcx, rbx; Destination
0x18000df6e  call    memcpy_s
0x18000df73  movzx   ecx, word ptr [rbp+0]
0x18000df77  mov     al, 1
0x18000df79  add     rcx, rbx
0x18000df7c  mov     [r15], rcx
0x18000df7f  add     rsp, 28h
0x18000df83  pop     r15
0x18000df85  pop     r14
0x18000df87  pop     rdi
0x18000df88  pop     rsi
0x18000df89  pop     rbp
0x18000df8a  pop     rbx
0x18000df8b  retn
```
