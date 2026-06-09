# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18000ed0c`
- end: `0x18000edf4`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000db08`

## callees

- `0x180003d0a`
- `0x180006868`
- `0x18000ed0c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ed6f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ed6f`

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
0x18000ed0c  push    rbx
0x18000ed0e  push    rbp
0x18000ed0f  push    rsi
0x18000ed10  push    rdi
0x18000ed11  push    r14
0x18000ed13  push    r15
0x18000ed15  sub     rsp, 28h
0x18000ed19  mov     al, [rcx+2]
0x18000ed1c  xor     ebp, ebp
0x18000ed1e  mov     r9, [rdx]
0x18000ed21  mov     rdi, r8
0x18000ed24  mov     r15, rdx
0x18000ed27  mov     rsi, rcx
0x18000ed2a  cmp     al, 1
0x18000ed2c  jnz     short loc_18000ED4A
0x18000ed2e  lea     rbx, [r9+2]
0x18000ed32  cmp     rbx, r8
0x18000ed35  ja      loc_18000EDC5
0x18000ed3b  test    r9, r9
0x18000ed3e  jz      short loc_18000ED6F
0x18000ed40  movzx   eax, word ptr [rcx+4]
0x18000ed44  mov     [r9], ax
0x18000ed48  jmp     short loc_18000ED85
0x18000ed4a  cmp     al, 2
0x18000ed4c  jnz     short loc_18000ED82
0x18000ed4e  lea     rbx, [r9+4]
0x18000ed52  cmp     rbx, rdi
0x18000ed55  ja      short loc_18000EDC5
0x18000ed57  test    r9, r9
0x18000ed5a  jz      short loc_18000ED6F
0x18000ed5c  lea     rax, [rcx+4]
0x18000ed60  test    rax, rax
0x18000ed63  jz      short loc_18000ED6C
0x18000ed65  mov     eax, [rax]
0x18000ed67  mov     [r9], eax
0x18000ed6a  jmp     short loc_18000ED85
0x18000ed6c  mov     [r9], eax
0x18000ed6f  call    cs:__imp__o__errno
0x18000ed75  mov     dword ptr [rax], 16h
0x18000ed7b  call    _invalid_parameter_noinfo
0x18000ed80  jmp     short loc_18000ED85
0x18000ed82  mov     rbx, r9
0x18000ed85  cmp     [rsi], bp
0x18000ed88  jnz     short loc_18000EDB3
0x18000ed8a  lea     r14, [rbx+2]
0x18000ed8e  cmp     r14, rdi
0x18000ed91  ja      short loc_18000EDC5
0x18000ed93  lea     rbp, [rsi+8]
0x18000ed97  mov     rdx, rdi
0x18000ed9a  sub     rdx, rbx; DestinationSize
0x18000ed9d  mov     r8, rbp; Source
0x18000eda0  mov     r9d, 2; SourceSize
0x18000eda6  mov     rcx, rbx; Destination
0x18000eda9  call    memcpy_s
0x18000edae  mov     rbx, r14
0x18000edb1  jmp     short loc_18000EDB7
0x18000edb3  lea     rbp, [rsi+8]
0x18000edb7  movzx   r9d, word ptr [rbp+0]; SourceSize
0x18000edbc  lea     rax, [r9+rbx]
0x18000edc0  cmp     rax, rdi
0x18000edc3  jbe     short loc_18000EDC9
0x18000edc5  xor     al, al
0x18000edc7  jmp     short loc_18000EDE7
0x18000edc9  mov     r8, [rsi+18h]; Source
0x18000edcd  sub     rdi, rbx
0x18000edd0  mov     rdx, rdi; DestinationSize
0x18000edd3  mov     rcx, rbx; Destination
0x18000edd6  call    memcpy_s
0x18000eddb  movzx   ecx, word ptr [rbp+0]
0x18000eddf  mov     al, 1
0x18000ede1  add     rcx, rbx
0x18000ede4  mov     [r15], rcx
0x18000ede7  add     rsp, 28h
0x18000edeb  pop     r15
0x18000eded  pop     r14
0x18000edef  pop     rdi
0x18000edf0  pop     rsi
0x18000edf1  pop     rbp
0x18000edf2  pop     rbx
0x18000edf3  retn
```
