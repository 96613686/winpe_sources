# std::_Copy_impl<std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>>(std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>,std::_Nonscalar_ptr_iterator_tag)

- ea: `0x18001da98`
- end: `0x18001db44`
- name: `??$_Copy_impl@V?$_Vb_iterator@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@std@@V12@@std@@YA?AV?$_Vb_iterator@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@0@V10@00U_Nonscalar_ptr_iterator_tag@0@@Z`
- size: `172`
- prototype: `_OWORD *__fastcall(_OWORD *, __int64, __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001f5b4`

## callees

- `0x1800154f4`
- `0x18001da98`

## pseudocode

```c
_OWORD *__fastcall std::_Copy_impl<std::_Vb_iterator<std::_Wrap_alloc<std::allocator<unsigned int>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<unsigned int>>>>(
        _OWORD *a1,
        __int64 a2,
        __int64 *a3,
        __int64 *a4)
{
  __int64 v4; // r12
  __int64 v6; // r13
  __int64 v7; // rdi
  unsigned __int64 i; // r11
  _DWORD *v10; // rsi
  __int64 v11; // r15
  unsigned __int64 v12; // r14
  bool v13; // zf
  unsigned __int64 v14; // r11
  unsigned __int64 v15; // rax
  _OWORD *result; // rax
  _QWORD v17[11]; // [rsp+20h] [rbp-58h] BYREF

  v4 = *a3;
  v6 = a3[1];
  v7 = a2;
  for ( i = *(_QWORD *)(a2 + 8); ; *(_QWORD *)(v7 + 8) = i )
  {
    v10 = *(_DWORD **)v7;
    if ( *(_QWORD *)v7 == v4 && i == v6 )
      break;
    v11 = *a4;
    v12 = a4[1];
    v13 = ((1 << i) & *v10) == 0;
    v17[0] = *a4;
    LOBYTE(a2) = !v13;
    v17[1] = v12;
    std::_Vb_reference<std::_Wrap_alloc<std::allocator<unsigned int>>>::operator=(v17, a2);
    if ( v12 >= 0x1F )
    {
      *a4 = v11 + 4;
      v15 = 0;
    }
    else
    {
      v15 = v12 + 1;
    }
    a4[1] = v15;
    if ( v14 >= 0x1F )
    {
      i = 0;
      *(_QWORD *)v7 = v10 + 1;
    }
    else
    {
      i = v14 + 1;
    }
  }
  result = a1;
  *a1 = *(_OWORD *)a4;
  return result;
}

```

## disassembly

```asm
0x18001da98  push    rbx
0x18001da9a  push    rbp
0x18001da9b  push    rsi
0x18001da9c  push    rdi
0x18001da9d  push    r12
0x18001da9f  push    r13
0x18001daa1  push    r14
0x18001daa3  push    r15
0x18001daa5  sub     rsp, 38h
0x18001daa9  mov     r12, [r8]
0x18001daac  mov     rbx, r9
0x18001daaf  mov     r13, [r8+8]
0x18001dab3  mov     rdi, rdx
0x18001dab6  mov     r11, [rdx+8]
0x18001daba  mov     rbp, rcx
0x18001dabd  mov     rsi, [rdi]
0x18001dac0  cmp     rsi, r12
0x18001dac3  jnz     short loc_18001DACA
0x18001dac5  cmp     r11, r13
0x18001dac8  jz      short loc_18001DB28
0x18001daca  mov     r15, [rbx]
0x18001dacd  mov     rcx, r11
0x18001dad0  mov     r14, [rbx+8]
0x18001dad4  mov     eax, 1
0x18001dad9  shl     eax, cl
0x18001dadb  lea     rcx, [rsp+78h+var_58]
0x18001dae0  test    [rsi], eax
0x18001dae2  mov     [rsp+78h+var_58], r15
0x18001dae7  setnz   dl
0x18001daea  mov     [rsp+78h+var_50], r14
0x18001daef  call    ??4?$_Vb_reference@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@std@@QEAAAEAV01@_N@Z; std::_Vb_reference<std::_Wrap_alloc<std::allocator<uint>>>::operator=(bool)
0x18001daf4  cmp     r14, 1Fh
0x18001daf8  jnb     short loc_18001DB00
0x18001dafa  lea     rax, [r14+1]
0x18001dafe  jmp     short loc_18001DB09
0x18001db00  lea     rax, [r15+4]
0x18001db04  mov     [rbx], rax
0x18001db07  xor     eax, eax
0x18001db09  mov     [rbx+8], rax
0x18001db0d  cmp     r11, 1Fh
0x18001db11  jnb     short loc_18001DB18
0x18001db13  inc     r11
0x18001db16  jmp     short loc_18001DB22
0x18001db18  lea     rax, [rsi+4]
0x18001db1c  xor     r11d, r11d
0x18001db1f  mov     [rdi], rax
0x18001db22  mov     [rdi+8], r11
0x18001db26  jmp     short loc_18001DABD
0x18001db28  movaps  xmm0, xmmword ptr [rbx]
0x18001db2b  mov     rax, rbp
0x18001db2e  movdqu  xmmword ptr [rbp+0], xmm0
0x18001db33  add     rsp, 38h
0x18001db37  pop     r15
0x18001db39  pop     r14
0x18001db3b  pop     r13
0x18001db3d  pop     r12
0x18001db3f  pop     rdi
0x18001db40  pop     rsi
0x18001db41  pop     rbp
0x18001db42  pop     rbx
0x18001db43  retn
```
