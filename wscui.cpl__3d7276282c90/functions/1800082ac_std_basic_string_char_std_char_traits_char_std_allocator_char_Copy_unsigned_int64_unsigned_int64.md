# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x1800082ac`
- end: `0x180008385`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `217`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000838c`

## callees

- `0x180003372`
- `0x180008098`
- `0x1800082ac`
- `0x18000844c`

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
0x1800082ac  mov     [rsp+arg_10], r8
0x1800082b1  mov     [rsp+arg_8], rdx
0x1800082b6  mov     [rsp+arg_0], rcx
0x1800082bb  push    rbx
0x1800082bc  push    rsi
0x1800082bd  push    rdi
0x1800082be  push    r14
0x1800082c0  sub     rsp, 28h
0x1800082c4  mov     rsi, r8
0x1800082c7  mov     rdi, rdx
0x1800082ca  mov     rbx, rcx
0x1800082cd  or      rdx, 0Fh
0x1800082d1  mov     r9, 0FFFFFFFFFFFFFFFEh
0x1800082d8  cmp     rdx, r9
0x1800082db  ja      short loc_180008311
0x1800082dd  mov     rdi, rdx
0x1800082e0  mov     r8, [rcx+18h]
0x1800082e4  mov     rcx, r8
0x1800082e7  shr     rcx, 1
0x1800082ea  mov     rax, 0AAAAAAAAAAAAAAABh
0x1800082f4  mul     rdx
0x1800082f7  shr     rdx, 1
0x1800082fa  cmp     rcx, rdx
0x1800082fd  jbe     short loc_180008311
0x1800082ff  mov     rax, r9
0x180008302  sub     rax, rcx
0x180008305  cmp     r8, rax
0x180008308  lea     rdi, [rcx+r8]
0x18000830c  jbe     short loc_180008311
0x18000830e  mov     rdi, r9
0x180008311  lea     rcx, [rdi+1]
0x180008315  xor     edx, edx
0x180008317  call    ??$_Allocate@D@std@@YAPEAD_KPEAD@Z; std::_Allocate<char>(unsigned __int64,char *)
0x18000831c  mov     r14, rax
0x18000831f  jmp     short loc_180008335
0x180008321  mov     rbx, [rsp+48h+arg_0]
0x180008326  mov     rsi, [rsp+48h+arg_10]
0x18000832b  mov     rdi, [rsp+48h+arg_8]
0x180008330  mov     r14, [rsp+48h+arg_18]
0x180008335  test    rsi, rsi
0x180008338  jz      short loc_180008354
0x18000833a  cmp     qword ptr [rbx+18h], 10h
0x18000833f  jb      short loc_180008346
0x180008341  mov     rdx, [rbx]
0x180008344  jmp     short loc_180008349
0x180008346  mov     rdx, rbx; Src
0x180008349  mov     r8, rsi; Size
0x18000834c  mov     rcx, r14; void *
0x18000834f  call    memcpy_0
0x180008354  xor     r8d, r8d
0x180008357  mov     dl, 1
0x180008359  mov     rcx, rbx
0x18000835c  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x180008361  mov     [rbx], r14
0x180008364  mov     [rbx+18h], rdi
0x180008368  mov     rax, rbx
0x18000836b  cmp     rdi, 10h
0x18000836f  cmovnb  rax, r14
0x180008373  mov     [rbx+10h], rsi
0x180008377  mov     byte ptr [rax+rsi], 0
0x18000837b  add     rsp, 28h
0x18000837f  pop     r14
0x180008381  pop     rdi
0x180008382  pop     rsi
0x180008383  pop     rbx
0x180008384  retn
```
