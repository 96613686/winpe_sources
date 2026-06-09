# std::_Copy_backward<std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>>(std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>)

- ea: `0x180013f80`
- end: `0x180014026`
- name: `??$_Copy_backward@V?$_Vb_iterator@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@std@@V12@@std@@YA?AV?$_Vb_iterator@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@0@V10@00@Z`
- size: `166`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001912c`

## callees

- `0x180013f80`
- `0x1800154f4`

## pseudocode

```c
_QWORD *__fastcall std::_Copy_backward<std::_Vb_iterator<std::_Wrap_alloc<std::allocator<unsigned int>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<unsigned int>>>>(
        _QWORD *a1,
        _QWORD *a2,
        __int64 a3,
        __int64 *a4)
{
  __int64 v4; // rbp
  __int64 v6; // r11
  _DWORD *v7; // rdi
  __int64 v8; // rbx
  _DWORD *v9; // r14
  __int64 v10; // r15
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r11
  bool v14; // zf
  _QWORD *result; // rax
  _QWORD v16[9]; // [rsp+20h] [rbp-48h] BYREF

  v4 = *a4;
  v6 = a4[1];
  v7 = *(_DWORD **)a3;
  v8 = *(_QWORD *)(a3 + 8);
  v9 = (_DWORD *)*a2;
  v10 = a2[1];
  while ( v9 != v7 || v10 != v8 )
  {
    v11 = v6;
    v12 = v8;
    if ( v8 )
      --v8;
    else
      v8 = 31;
    if ( !v12 )
      --v7;
    if ( v6 )
      v13 = v6 - 1;
    else
      v13 = 31;
    v16[1] = v13;
    if ( !v11 )
      v4 -= 4;
    v14 = ((1 << v8) & *v7) == 0;
    v16[0] = v4;
    LOBYTE(v11) = !v14;
    std::_Vb_reference<std::_Wrap_alloc<std::allocator<unsigned int>>>::operator=(v16, v11);
  }
  *a1 = v4;
  result = a1;
  a1[1] = v6;
  return result;
}

```

## disassembly

```asm
0x180013f80  push    rbx
0x180013f82  push    rbp
0x180013f83  push    rsi
0x180013f84  push    rdi
0x180013f85  push    r14
0x180013f87  push    r15
0x180013f89  sub     rsp, 38h
0x180013f8d  mov     rbp, [r9]
0x180013f90  mov     rsi, rcx
0x180013f93  mov     r11, [r9+8]
0x180013f97  mov     rdi, [r8]
0x180013f9a  mov     rbx, [r8+8]
0x180013f9e  mov     r14, [rdx]
0x180013fa1  mov     r15, [rdx+8]
0x180013fa5  cmp     r14, rdi
0x180013fa8  jnz     short loc_180013FAF
0x180013faa  cmp     r15, rbx
0x180013fad  jz      short loc_18001400F
0x180013faf  mov     rdx, r11
0x180013fb2  mov     rcx, rbx
0x180013fb5  test    rbx, rbx
0x180013fb8  jz      short loc_180013FBF
0x180013fba  dec     rbx
0x180013fbd  jmp     short loc_180013FC4
0x180013fbf  mov     ebx, 1Fh
0x180013fc4  test    rcx, rcx
0x180013fc7  lea     rax, [rdi-4]
0x180013fcb  cmovz   rdi, rax
0x180013fcf  test    r11, r11
0x180013fd2  jz      short loc_180013FD9
0x180013fd4  dec     r11
0x180013fd7  jmp     short loc_180013FDF
0x180013fd9  mov     r11d, 1Fh
0x180013fdf  test    rdx, rdx
0x180013fe2  mov     [rsp+68h+var_40], r11
0x180013fe7  lea     rax, [rbp-4]
0x180013feb  mov     rcx, rbx
0x180013fee  cmovz   rbp, rax
0x180013ff2  mov     eax, 1
0x180013ff7  shl     eax, cl
0x180013ff9  lea     rcx, [rsp+68h+var_48]
0x180013ffe  test    [rdi], eax
0x180014000  mov     [rsp+68h+var_48], rbp
0x180014005  setnz   dl
0x180014008  call    ??4?$_Vb_reference@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@std@@QEAAAEAV01@_N@Z; std::_Vb_reference<std::_Wrap_alloc<std::allocator<uint>>>::operator=(bool)
0x18001400d  jmp     short loc_180013FA5
0x18001400f  mov     [rsi], rbp
0x180014012  mov     rax, rsi
0x180014015  mov     [rsi+8], r11
0x180014019  add     rsp, 38h
0x18001401d  pop     r15
0x18001401f  pop     r14
0x180014021  pop     rdi
0x180014022  pop     rsi
0x180014023  pop     rbp
0x180014024  pop     rbx
0x180014025  retn
```
