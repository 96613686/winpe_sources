# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180005f68`
- end: `0x18000606f`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `263`
- prototype: `_QWORD *__fastcall(_QWORD *, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800060e8`

## callees

- `0x180001238`
- `0x180003430`
- `0x180005f68`
- `0x1800062d4`
- `0x180006780`

## pseudocode

```c
_QWORD *__fastcall std::wstring::_Copy(_QWORD *a1, unsigned __int64 a2, __int64 a3)
{
  __int64 v3; // r15
  unsigned __int64 v4; // rbx
  _QWORD *v5; // rdi
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  _QWORD *v10; // r14
  _QWORD *v11; // rdx
  _QWORD *result; // rax
  _QWORD *v13; // rax
  unsigned __int64 v14; // rcx
  _BYTE *v15; // rdx
  _BYTE v16[72]; // [rsp+0h] [rbp-48h] BYREF
  _QWORD *v20; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  v5 = a1;
  v6 = a2 | 7;
  if ( v6 <= 0x7FFFFFFFFFFFFFFELL )
  {
    v4 = v6;
    v7 = a1[3];
    v8 = v7 >> 1;
    v6 /= 3u;
    if ( v7 >> 1 > v6 )
    {
      v4 = v8 + v7;
      if ( v7 > 0x7FFFFFFFFFFFFFFELL - v8 )
        v4 = 0x7FFFFFFFFFFFFFFELL;
    }
  }
  try
  {
    v9 = v4 + 1;
    if ( v4 == -1 )
    {
      v10 = 0;
    }
    else if ( v9 > 0x7FFFFFFFFFFFFFFFLL || (v10 = operator new(2 * v9)) == 0 )
    {
      std::_Xbad_alloc();
    }
  }
  catch ( ... )
  {
    v6 = (unsigned __int64)v16;
    try
    {
      v13 = 0;
      v14 = a2 + 1;
      if ( a2 != -1 && (v14 > 0x7FFFFFFFFFFFFFFFLL || (v13 = operator new(2 * v14)) == 0) )
        std::_Xbad_alloc();
      v20 = v13;
    }
    catch ( ... )
    {
      v15 = v16;
      LOBYTE(v15) = 1;
      std::wstring::_Tidy(a1, v15, 0);
      throw;
    }
    v5 = a1;
    v3 = a3;
    v4 = a2;
    v10 = v20;
  }
  if ( v3 )
  {
    if ( v5[3] < 8u )
      v11 = v5;
    else
      v11 = (_QWORD *)*v5;
    std::char_traits<unsigned short>::copy(v10, v11, v3);
  }
  LOBYTE(v6) = 1;
  std::wstring::_Tidy(v5, v6, 0);
  *v5 = v10;
  v5[3] = v4;
  result = v5;
  if ( v4 >= 8 )
    result = v10;
  v5[2] = v3;
  *((_WORD *)result + v3) = 0;
  return result;
}

```

## disassembly

```asm
0x180005f68  mov     [rsp+arg_10], r8
0x180005f6d  mov     [rsp+arg_8], rdx
0x180005f72  mov     [rsp+arg_0], rcx
0x180005f77  push    rbx
0x180005f78  push    rsi
0x180005f79  push    rdi
0x180005f7a  push    r14
0x180005f7c  push    r15
0x180005f7e  sub     rsp, 20h
0x180005f82  mov     r15, r8
0x180005f85  mov     rbx, rdx
0x180005f88  mov     rdi, rcx
0x180005f8b  or      rdx, 7
0x180005f8f  mov     r9, 7FFFFFFFFFFFFFFEh
0x180005f99  cmp     rdx, r9
0x180005f9c  ja      short loc_180005FD2
0x180005f9e  mov     rbx, rdx
0x180005fa1  mov     r8, [rcx+18h]
0x180005fa5  mov     rcx, r8
0x180005fa8  shr     rcx, 1
0x180005fab  mov     rax, 0AAAAAAAAAAAAAAABh
0x180005fb5  mul     rdx
0x180005fb8  shr     rdx, 1
0x180005fbb  cmp     rcx, rdx
0x180005fbe  jbe     short loc_180005FD2
0x180005fc0  mov     rax, r9
0x180005fc3  sub     rax, rcx
0x180005fc6  cmp     r8, rax
0x180005fc9  lea     rbx, [rcx+r8]
0x180005fcd  jbe     short loc_180005FD2
0x180005fcf  mov     rbx, r9
0x180005fd2  lea     rcx, [rbx+1]
0x180005fd6  xor     esi, esi
0x180005fd8  test    rcx, rcx
0x180005fdb  jz      short loc_180006001
0x180005fdd  mov     rax, 7FFFFFFFFFFFFFFFh
0x180005fe7  cmp     rcx, rax
0x180005fea  ja      short loc_180005FFC
0x180005fec  add     rcx, rcx; dwBytes
0x180005fef  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005ff4  mov     r14, rax
0x180005ff7  test    rax, rax
0x180005ffa  jnz     short loc_180006004
0x180005ffc  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180006001  mov     r14, rsi
0x180006004  jmp     short loc_18000601C
0x180006006  xor     esi, esi
0x180006008  mov     rdi, [rsp+48h+arg_0]
0x18000600d  mov     r15, [rsp+48h+arg_10]
0x180006012  mov     rbx, [rsp+48h+arg_8]
0x180006017  mov     r14, [rsp+48h+arg_18]
0x18000601c  test    r15, r15
0x18000601f  jz      short loc_18000603B
0x180006021  cmp     qword ptr [rdi+18h], 8
0x180006026  jb      short loc_18000602D
0x180006028  mov     rdx, [rdi]
0x18000602b  jmp     short loc_180006030
0x18000602d  mov     rdx, rdi
0x180006030  mov     r8, r15
0x180006033  mov     rcx, r14
0x180006036  call    ?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)
0x18000603b  xor     r8d, r8d
0x18000603e  mov     dl, 1
0x180006040  mov     rcx, rdi
0x180006043  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180006048  mov     [rdi], r14
0x18000604b  mov     [rdi+18h], rbx
0x18000604f  mov     rax, rdi
0x180006052  cmp     rbx, 8
0x180006056  cmovnb  rax, r14
0x18000605a  mov     [rdi+10h], r15
0x18000605e  mov     [rax+r15*2], si
0x180006063  add     rsp, 20h
0x180006067  pop     r15
0x180006069  pop     r14
0x18000606b  pop     rdi
0x18000606c  pop     rsi
0x18000606d  pop     rbx
0x18000606e  retn
```
