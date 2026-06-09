# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18000fe1c`
- end: `0x18000ff04`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e378`

## callees

- `0x180001df8`
- `0x18000fe1c`
- `0x180011764`

## import_xrefs

- `msvcrt!_errno` at `0x18000fe7f`
- `msvcrt!_errno` at `0x18000fe7f`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Write(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  char v3; // al
  _WORD *v4; // r9
  _WORD *v8; // rbx
  _DWORD *v9; // rax
  unsigned __int16 *v10; // rbp
  rsize_t v11; // r9
  bool result; // al

  v3 = *((_BYTE *)this + 2);
  v4 = *a2;
  if ( v3 == 1 )
  {
    v8 = v4 + 1;
    if ( v4 + 1 > (_WORD *)a3 )
      return 0;
    if ( v4 )
    {
      *v4 = *((_WORD *)this + 2);
      goto LABEL_13;
    }
LABEL_11:
    *_errno() = 22;
    invalid_parameter_noinfo();
  }
  if ( v3 == 2 )
  {
    v8 = v4 + 2;
    if ( v4 + 2 > (_WORD *)a3 )
      return 0;
    if ( !v4 )
      goto LABEL_11;
    v9 = (_DWORD *)((char *)this + 4);
    if ( this == (wil::details_abi::UsageIndexProperty *)-4LL )
    {
      *(_DWORD *)v4 = (_DWORD)v9;
      goto LABEL_11;
    }
    *(_DWORD *)v4 = *v9;
  }
  else
  {
    v8 = *a2;
  }
LABEL_13:
  if ( !*(_WORD *)this )
  {
    if ( v8 + 1 <= (_WORD *)a3 )
    {
      v10 = (unsigned __int16 *)((char *)this + 8);
      memcpy_s_0(v8, a3 - (unsigned __int8 *)v8, (char *)this + 8, 2u);
      ++v8;
      goto LABEL_17;
    }
    return 0;
  }
  v10 = (unsigned __int16 *)((char *)this + 8);
LABEL_17:
  v11 = *v10;
  if ( (unsigned __int8 *)((char *)v8 + v11) > a3 )
    return 0;
  memcpy_s_0(v8, a3 - (unsigned __int8 *)v8, *((const void *const *)this + 3), v11);
  result = 1;
  *a2 = (unsigned __int8 *)v8 + *v10;
  return result;
}

```

## disassembly

```asm
0x18000fe1c  push    rbx
0x18000fe1e  push    rbp
0x18000fe1f  push    rsi
0x18000fe20  push    rdi
0x18000fe21  push    r14
0x18000fe23  push    r15
0x18000fe25  sub     rsp, 28h
0x18000fe29  mov     al, [rcx+2]
0x18000fe2c  xor     ebp, ebp
0x18000fe2e  mov     r9, [rdx]
0x18000fe31  mov     rdi, r8
0x18000fe34  mov     r15, rdx
0x18000fe37  mov     rsi, rcx
0x18000fe3a  cmp     al, 1
0x18000fe3c  jnz     short loc_18000FE5A
0x18000fe3e  lea     rbx, [r9+2]
0x18000fe42  cmp     rbx, r8
0x18000fe45  ja      loc_18000FED5
0x18000fe4b  test    r9, r9
0x18000fe4e  jz      short loc_18000FE7F
0x18000fe50  movzx   eax, word ptr [rcx+4]
0x18000fe54  mov     [r9], ax
0x18000fe58  jmp     short loc_18000FE95
0x18000fe5a  cmp     al, 2
0x18000fe5c  jnz     short loc_18000FE92
0x18000fe5e  lea     rbx, [r9+4]
0x18000fe62  cmp     rbx, rdi
0x18000fe65  ja      short loc_18000FED5
0x18000fe67  test    r9, r9
0x18000fe6a  jz      short loc_18000FE7F
0x18000fe6c  lea     rax, [rcx+4]
0x18000fe70  test    rax, rax
0x18000fe73  jz      short loc_18000FE7C
0x18000fe75  mov     eax, [rax]
0x18000fe77  mov     [r9], eax
0x18000fe7a  jmp     short loc_18000FE95
0x18000fe7c  mov     [r9], eax
0x18000fe7f  call    cs:__imp__errno
0x18000fe85  mov     dword ptr [rax], 16h
0x18000fe8b  call    _invalid_parameter_noinfo
0x18000fe90  jmp     short loc_18000FE95
0x18000fe92  mov     rbx, r9
0x18000fe95  cmp     [rsi], bp
0x18000fe98  jnz     short loc_18000FEC3
0x18000fe9a  lea     r14, [rbx+2]
0x18000fe9e  cmp     r14, rdi
0x18000fea1  ja      short loc_18000FED5
0x18000fea3  lea     rbp, [rsi+8]
0x18000fea7  mov     rdx, rdi
0x18000feaa  sub     rdx, rbx; DestinationSize
0x18000fead  mov     r8, rbp; Source
0x18000feb0  mov     r9d, 2; SourceSize
0x18000feb6  mov     rcx, rbx; Destination
0x18000feb9  call    memcpy_s_0
0x18000febe  mov     rbx, r14
0x18000fec1  jmp     short loc_18000FEC7
0x18000fec3  lea     rbp, [rsi+8]
0x18000fec7  movzx   r9d, word ptr [rbp+0]; SourceSize
0x18000fecc  lea     rax, [r9+rbx]
0x18000fed0  cmp     rax, rdi
0x18000fed3  jbe     short loc_18000FED9
0x18000fed5  xor     al, al
0x18000fed7  jmp     short loc_18000FEF7
0x18000fed9  mov     r8, [rsi+18h]; Source
0x18000fedd  sub     rdi, rbx
0x18000fee0  mov     rdx, rdi; DestinationSize
0x18000fee3  mov     rcx, rbx; Destination
0x18000fee6  call    memcpy_s_0
0x18000feeb  movzx   ecx, word ptr [rbp+0]
0x18000feef  mov     al, 1
0x18000fef1  add     rcx, rbx
0x18000fef4  mov     [r15], rcx
0x18000fef7  add     rsp, 28h
0x18000fefb  pop     r15
0x18000fefd  pop     r14
0x18000feff  pop     rdi
0x18000ff00  pop     rsi
0x18000ff01  pop     rbp
0x18000ff02  pop     rbx
0x18000ff03  retn
```
