# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x18000abfc`
- end: `0x18000acd5`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `217`
- prototype: `const void **__fastcall(const void **Src, unsigned __int64, size_t)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000ada4`

## callees

- `0x180002986`
- `0x180003d0c`
- `0x18000abfc`
- `0x18000ae9c`

## pseudocode

```c
const void **__fastcall std::string::_Copy(const void **Src, unsigned __int64 a2, size_t a3)
{
  size_t v3; // rsi
  unsigned __int64 v4; // rdi
  const void **v5; // rbx
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  void *v10; // r14
  const void *v11; // rdx
  __int64 v12; // rdx
  const void **result; // rax
  __int64 *v14; // rdx
  __int64 v15; // [rsp+0h] [rbp-48h] BYREF
  __int64 v23; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  v5 = Src;
  v6 = a2 | 0xF;
  if ( v6 != -1 )
  {
    v4 = v6;
    v7 = (unsigned __int64)Src[3];
    v8 = v7 >> 1;
    v9 = v6 / 3;
    if ( v7 >> 1 > v9 )
    {
      v4 = v8 + v7;
      if ( v7 > -2LL - v8 )
        v4 = -2;
    }
  }
  try
  {
    v10 = (void *)std::_Allocate<char>(v4 + 1, 0);
  }
  catch ( ... )
  {
    try
    {
      v23 = std::_Allocate<char>(a2 + 1, 0);
    }
    catch ( ... )
    {
      v14 = &v15;
      LOBYTE(v14) = 1;
      std::string::_Tidy(Src, v14, 0);
      throw;
    }
    v5 = Src;
    v3 = a3;
    v4 = a2;
    v10 = (void *)v23;
  }
  if ( v3 )
  {
    if ( (unsigned __int64)v5[3] < 0x10 )
      v11 = v5;
    else
      v11 = *v5;
    memcpy_0(v10, v11, v3);
  }
  LOBYTE(v12) = 1;
  std::string::_Tidy(v5, v12, 0);
  *v5 = v10;
  v5[3] = (const void *)v4;
  result = v5;
  if ( v4 >= 0x10 )
    result = (const void **)v10;
  v5[2] = (const void *)v3;
  *((_BYTE *)result + v3) = 0;
  return result;
}

```

## disassembly

```asm
0x18000abfc  mov     [rsp+arg_10], r8
0x18000ac01  mov     [rsp+arg_8], rdx
0x18000ac06  mov     [rsp+arg_0], rcx
0x18000ac0b  push    rbx
0x18000ac0c  push    rsi
0x18000ac0d  push    rdi
0x18000ac0e  push    r14
0x18000ac10  sub     rsp, 28h
0x18000ac14  mov     rsi, r8
0x18000ac17  mov     rdi, rdx
0x18000ac1a  mov     rbx, rcx
0x18000ac1d  or      rdx, 0Fh
0x18000ac21  mov     r9, 0FFFFFFFFFFFFFFFEh
0x18000ac28  cmp     rdx, r9
0x18000ac2b  ja      short loc_18000AC61
0x18000ac2d  mov     rdi, rdx
0x18000ac30  mov     r8, [rcx+18h]
0x18000ac34  mov     rcx, r8
0x18000ac37  shr     rcx, 1
0x18000ac3a  mov     rax, 0AAAAAAAAAAAAAAABh
0x18000ac44  mul     rdx
0x18000ac47  shr     rdx, 1
0x18000ac4a  cmp     rcx, rdx
0x18000ac4d  jbe     short loc_18000AC61
0x18000ac4f  mov     rax, r9
0x18000ac52  sub     rax, rcx
0x18000ac55  cmp     r8, rax
0x18000ac58  lea     rdi, [rcx+r8]
0x18000ac5c  jbe     short loc_18000AC61
0x18000ac5e  mov     rdi, r9
0x18000ac61  lea     rcx, [rdi+1]
0x18000ac65  xor     edx, edx
0x18000ac67  call    ??$_Allocate@D@std@@YAPEAD_KPEAD@Z; std::_Allocate<char>(unsigned __int64,char *)
0x18000ac6c  mov     r14, rax
0x18000ac6f  jmp     short loc_18000AC85
0x18000ac71  mov     rbx, [rsp+48h+arg_0]
0x18000ac76  mov     rsi, [rsp+48h+arg_10]
0x18000ac7b  mov     rdi, [rsp+48h+arg_8]
0x18000ac80  mov     r14, [rsp+48h+arg_18]
0x18000ac85  test    rsi, rsi
0x18000ac88  jz      short loc_18000ACA4
0x18000ac8a  cmp     qword ptr [rbx+18h], 10h
0x18000ac8f  jb      short loc_18000AC96
0x18000ac91  mov     rdx, [rbx]
0x18000ac94  jmp     short loc_18000AC99
0x18000ac96  mov     rdx, rbx; Src
0x18000ac99  mov     r8, rsi; Size
0x18000ac9c  mov     rcx, r14; void *
0x18000ac9f  call    memcpy_0
0x18000aca4  xor     r8d, r8d
0x18000aca7  mov     dl, 1
0x18000aca9  mov     rcx, rbx
0x18000acac  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x18000acb1  mov     [rbx], r14
0x18000acb4  mov     [rbx+18h], rdi
0x18000acb8  mov     rax, rbx
0x18000acbb  cmp     rdi, 10h
0x18000acbf  cmovnb  rax, r14
0x18000acc3  mov     [rbx+10h], rsi
0x18000acc7  mov     byte ptr [rax+rsi], 0
0x18000accb  add     rsp, 28h
0x18000accf  pop     r14
0x18000acd1  pop     rdi
0x18000acd2  pop     rsi
0x18000acd3  pop     rbx
0x18000acd4  retn
```
