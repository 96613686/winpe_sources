# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180001e4c`
- end: `0x180001f25`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `217`
- prototype: `const void **__fastcall(const void **Src, unsigned __int64, size_t)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180001f2c`

## callees

- `0x180001976`
- `0x180001dbc`
- `0x180001e4c`
- `0x180001fec`

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
0x180001e4c  mov     [rsp+arg_10], r8
0x180001e51  mov     [rsp+arg_8], rdx
0x180001e56  mov     [rsp+arg_0], rcx
0x180001e5b  push    rbx
0x180001e5c  push    rsi
0x180001e5d  push    rdi
0x180001e5e  push    r14
0x180001e60  sub     rsp, 28h
0x180001e64  mov     rsi, r8
0x180001e67  mov     rdi, rdx
0x180001e6a  mov     rbx, rcx
0x180001e6d  or      rdx, 0Fh
0x180001e71  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180001e78  cmp     rdx, r9
0x180001e7b  ja      short loc_180001EB1
0x180001e7d  mov     rdi, rdx
0x180001e80  mov     r8, [rcx+18h]
0x180001e84  mov     rcx, r8
0x180001e87  shr     rcx, 1
0x180001e8a  mov     rax, 0AAAAAAAAAAAAAAABh
0x180001e94  mul     rdx
0x180001e97  shr     rdx, 1
0x180001e9a  cmp     rcx, rdx
0x180001e9d  jbe     short loc_180001EB1
0x180001e9f  mov     rax, r9
0x180001ea2  sub     rax, rcx
0x180001ea5  cmp     r8, rax
0x180001ea8  lea     rdi, [rcx+r8]
0x180001eac  jbe     short loc_180001EB1
0x180001eae  mov     rdi, r9
0x180001eb1  lea     rcx, [rdi+1]
0x180001eb5  xor     edx, edx
0x180001eb7  call    ??$_Allocate@D@std@@YAPEAD_KPEAD@Z; std::_Allocate<char>(unsigned __int64,char *)
0x180001ebc  mov     r14, rax
0x180001ebf  jmp     short loc_180001ED5
0x180001ec1  mov     rbx, [rsp+48h+arg_0]
0x180001ec6  mov     rsi, [rsp+48h+arg_10]
0x180001ecb  mov     rdi, [rsp+48h+arg_8]
0x180001ed0  mov     r14, [rsp+48h+arg_18]
0x180001ed5  test    rsi, rsi
0x180001ed8  jz      short loc_180001EF4
0x180001eda  cmp     qword ptr [rbx+18h], 10h
0x180001edf  jb      short loc_180001EE6
0x180001ee1  mov     rdx, [rbx]
0x180001ee4  jmp     short loc_180001EE9
0x180001ee6  mov     rdx, rbx; Src
0x180001ee9  mov     r8, rsi; Size
0x180001eec  mov     rcx, r14; void *
0x180001eef  call    memcpy_0
0x180001ef4  xor     r8d, r8d
0x180001ef7  mov     dl, 1
0x180001ef9  mov     rcx, rbx
0x180001efc  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x180001f01  mov     [rbx], r14
0x180001f04  mov     [rbx+18h], rdi
0x180001f08  mov     rax, rbx
0x180001f0b  cmp     rdi, 10h
0x180001f0f  cmovnb  rax, r14
0x180001f13  mov     [rbx+10h], rsi
0x180001f17  mov     byte ptr [rax+rsi], 0
0x180001f1b  add     rsp, 28h
0x180001f1f  pop     r14
0x180001f21  pop     rdi
0x180001f22  pop     rsi
0x180001f23  pop     rbx
0x180001f24  retn
```
