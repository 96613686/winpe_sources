# Windows::UI::Composition::StringBuilder::Append(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x1800061b0`
- end: `0x180006409`
- name: `?Append@StringBuilder@Composition@UI@Windows@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `601`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `33`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800010b0`
- `0x180001200`
- `0x180001410`
- `0x180001950`
- `0x180001da0`
- `0x180002080`
- `0x180006470`
- `0x1800066e0`
- `0x180007394`
- `0x180008220`
- `0x180008320`
- `0x180008550`
- `0x180008730`
- `0x1800088a0`
- `0x18001f220`
- `0x18001f800`
- `0x18001fc70`
- `0x180020150`
- `0x180020570`
- `0x1800259f0`
- `0x180025e20`
- `0x180026770`
- `0x180026c40`
- `0x180027090`
- `0x180027170`
- `0x1800274d0`
- `0x180027810`
- `0x180027920`
- `0x180027ad0`
- `0x180027cd0`
- `0x180027de0`
- `0x180028920`
- `0x180028ba0`

## callees

- `0x1800061b0`
- `0x180006410`
- `0x180007bc0`
- `0x180028b20`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::UI::Composition::StringBuilder::Append(__int64 a1, unsigned __int8 *a2)
{
  unsigned __int8 *v2; // rsi
  __int64 result; // rax
  unsigned __int8 *v5; // r15
  unsigned __int64 v6; // rdi
  __int64 v7; // rdx
  __int64 v8; // rcx
  unsigned __int64 v9; // rdi
  __int64 v10; // r14
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rbp
  unsigned __int64 v15; // r14
  __int64 v16; // r12
  __int64 v17; // rsi
  unsigned __int64 v18; // rdi
  __int64 v19; // [rsp+20h] [rbp-58h] BYREF
  __int64 v20; // [rsp+28h] [rbp-50h]
  __int64 v21; // [rsp+30h] [rbp-48h] BYREF
  unsigned __int64 v22; // [rsp+38h] [rbp-40h]

  v2 = a2;
  result = *((_QWORD *)a2 + 2);
  if ( *((_QWORD *)a2 + 3) > 0xFu )
    v2 = *(unsigned __int8 **)a2;
  v5 = &v2[result];
  if ( v2 != &v2[result] )
  {
    v6 = *(_QWORD *)(a1 + 32);
    v21 = a1;
    v22 = v6;
    if ( v6 <= v6 >> 1 )
    {
      v11 = v6;
      do
      {
        --v5;
        if ( (*(_BYTE *)(a1 + 24) & 0xF) == 0 && *(_QWORD *)(a1 + 16) <= (unsigned __int64)(v11 + 16) >> 4 )
          std::deque<char>::_Growmap(a1);
        v12 = *(_QWORD *)(a1 + 16);
        v13 = *(_QWORD *)(a1 + 24) & (16 * v12 - 1);
        *(_QWORD *)(a1 + 24) = v13;
        if ( !v13 )
          v13 = 16 * v12;
        v14 = v13 - 1;
        v15 = (unsigned __int64)(v13 - 1) >> 4;
        v16 = 8 * (v15 & (v12 - 1));
        if ( !*(_QWORD *)(v16 + *(_QWORD *)(a1 + 8)) )
          *(_QWORD *)(v16 + *(_QWORD *)(a1 + 8)) = operator new(0x10u);
        *(_BYTE *)((v14 & 0xF) + *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * (v15 & (*(_QWORD *)(a1 + 16) - 1LL)))) = *v5;
        *(_QWORD *)(a1 + 24) = v14;
        v11 = *(_QWORD *)(a1 + 32) + 1LL;
        *(_QWORD *)(a1 + 32) = v11;
      }
      while ( v5 != v2 );
      result = v11 - v6;
      v17 = result + v14;
      if ( v14 != result + v14 )
      {
        v18 = v17 + v6;
        if ( v17 != v18 )
        {
          v19 = a1;
          v20 = result + v14;
          v21 = a1;
          v22 = v14;
          std::reverse<std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>>(&v21, &v19);
          v21 = a1;
          v22 = v18;
          v19 = a1;
          v20 = v17;
          std::reverse<std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>>(&v19, &v21);
          v21 = a1;
          v22 = v18;
          v19 = a1;
          v20 = v14;
          return std::reverse<std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>>(
                   &v19,
                   &v21);
        }
      }
    }
    else
    {
      do
      {
        if ( ((*(_BYTE *)(a1 + 24) + (_BYTE)v6) & 0xF) == 0 && *(_QWORD *)(a1 + 16) <= (v6 + 16) >> 4 )
          std::deque<char>::_Growmap(a1);
        v7 = *(_QWORD *)(a1 + 16);
        v8 = *(_QWORD *)(a1 + 24) & (16 * v7 - 1);
        *(_QWORD *)(a1 + 24) = v8;
        v9 = v8 + *(_QWORD *)(a1 + 32);
        v10 = 8 * ((v9 >> 4) & (v7 - 1));
        if ( !*(_QWORD *)(v10 + *(_QWORD *)(a1 + 8)) )
          *(_QWORD *)(v10 + *(_QWORD *)(a1 + 8)) = operator new(0x10u);
        result = *v2;
        *(_BYTE *)((v9 & 0xF) + *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * ((v9 >> 4) & (*(_QWORD *)(a1 + 16) - 1LL)))) = result;
        v6 = *(_QWORD *)(a1 + 32) + 1LL;
        *(_QWORD *)(a1 + 32) = v6;
        ++v2;
      }
      while ( v2 != v5 );
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800061b0  push    rbx
0x1800061b2  push    rbp
0x1800061b3  push    rsi
0x1800061b4  push    rdi
0x1800061b5  push    r12
0x1800061b7  push    r14
0x1800061b9  push    r15
0x1800061bb  sub     rsp, 40h
0x1800061bf  mov     rsi, rdx
0x1800061c2  mov     rbx, rcx
0x1800061c5  mov     rax, [rdx+10h]
0x1800061c9  cmp     qword ptr [rdx+18h], 0Fh
0x1800061ce  jbe     short loc_1800061D3
0x1800061d0  mov     rsi, [rdx]
0x1800061d3  lea     r15, [rax+rsi]
0x1800061d7  cmp     rsi, r15
0x1800061da  jz      loc_18000627B
0x1800061e0  mov     rdi, [rcx+20h]
0x1800061e4  mov     rax, rdi
0x1800061e7  shr     rax, 1
0x1800061ea  mov     [rsp+78h+var_48], rbx
0x1800061ef  mov     [rsp+78h+var_40], rdi
0x1800061f4  cmp     rdi, rax
0x1800061f7  jbe     loc_18000629E
0x1800061fd  nop     dword ptr [rax]
0x180006200  movzx   eax, dil
0x180006204  add     al, [rbx+18h]
0x180006207  test    al, 0Fh
0x180006209  jz      loc_1800063B3
0x18000620f  mov     rdx, [rbx+10h]
0x180006213  mov     rcx, rdx
0x180006216  shl     rcx, 4
0x18000621a  dec     rcx
0x18000621d  and     rcx, [rbx+18h]
0x180006221  mov     [rbx+18h], rcx
0x180006225  mov     rdi, [rbx+20h]
0x180006229  add     rdi, rcx
0x18000622c  mov     rbp, rdi
0x18000622f  shr     rbp, 4
0x180006233  lea     rax, [rdx-1]
0x180006237  and     rax, rbp
0x18000623a  lea     r14, ds:0[rax*8]
0x180006242  mov     rax, [rbx+8]
0x180006246  cmp     qword ptr [r14+rax], 0
0x18000624b  jz      short loc_18000628A
0x18000624d  mov     rax, [rbx+10h]
0x180006251  dec     rax
0x180006254  and     rax, rbp
0x180006257  mov     rcx, [rbx+8]
0x18000625b  and     edi, 0Fh
0x18000625e  mov     rcx, [rcx+rax*8]
0x180006262  movzx   eax, byte ptr [rsi]
0x180006265  mov     [rdi+rcx], al
0x180006268  mov     rdi, [rbx+20h]
0x18000626c  inc     rdi
0x18000626f  mov     [rbx+20h], rdi
0x180006273  inc     rsi
0x180006276  cmp     rsi, r15
0x180006279  jnz     short loc_180006200
0x18000627b  add     rsp, 40h
0x18000627f  pop     r15
0x180006281  pop     r14
0x180006283  pop     r12
0x180006285  pop     rdi
0x180006286  pop     rsi
0x180006287  pop     rbp
0x180006288  pop     rbx
0x180006289  retn
0x18000628a  mov     ecx, 10h; dwBytes
0x18000628f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006294  mov     rcx, [rbx+8]
0x180006298  mov     [r14+rcx], rax
0x18000629c  jmp     short loc_18000624D
0x18000629e  mov     rax, rdi
0x1800062a1  dec     r15
0x1800062a4  test    byte ptr [rbx+18h], 0Fh
0x1800062a8  jz      loc_1800063D2
0x1800062ae  mov     rdx, [rbx+10h]
0x1800062b2  mov     rcx, rdx
0x1800062b5  shl     rcx, 4
0x1800062b9  lea     rax, [rcx-1]
0x1800062bd  and     rax, [rbx+18h]
0x1800062c1  mov     [rbx+18h], rax
0x1800062c5  cmovz   rax, rcx
0x1800062c9  lea     rbp, [rax-1]
0x1800062cd  mov     r14, rbp
0x1800062d0  shr     r14, 4
0x1800062d4  lea     rax, [rdx-1]
0x1800062d8  and     rax, r14
0x1800062db  lea     r12, ds:0[rax*8]
0x1800062e3  mov     rax, [rbx+8]
0x1800062e7  cmp     qword ptr [r12+rax], 0
0x1800062ec  jz      loc_1800063F1
0x1800062f2  mov     rax, [rbx+10h]
0x1800062f6  dec     rax
0x1800062f9  and     rax, r14
0x1800062fc  mov     rcx, [rbx+8]
0x180006300  mov     rdx, rbp
0x180006303  and     edx, 0Fh
0x180006306  mov     rcx, [rcx+rax*8]
0x18000630a  movzx   eax, byte ptr [r15]
0x18000630e  mov     [rdx+rcx], al
0x180006311  mov     [rbx+18h], rbp
0x180006315  mov     rax, [rbx+20h]
0x180006319  inc     rax
0x18000631c  mov     [rbx+20h], rax
0x180006320  cmp     r15, rsi
0x180006323  jnz     loc_1800062A1
0x180006329  sub     rax, rdi
0x18000632c  lea     rsi, [rax+rbp]
0x180006330  cmp     rbp, rsi
0x180006333  jz      loc_18000627B
0x180006339  add     rdi, rsi
0x18000633c  cmp     rsi, rdi
0x18000633f  jz      loc_18000627B
0x180006345  mov     [rsp+78h+var_58], rbx
0x18000634a  mov     [rsp+78h+var_50], rsi
0x18000634f  mov     [rsp+78h+var_48], rbx
0x180006354  mov     [rsp+78h+var_40], rbp
0x180006359  lea     rdx, [rsp+78h+var_58]
0x18000635e  lea     rcx, [rsp+78h+var_48]
0x180006363  call    ??$reverse@V?$_Deque_unchecked_iterator@V?$_Deque_val@U?$_Deque_simple_types@D@std@@@std@@@std@@@std@@YAXV?$_Deque_unchecked_iterator@V?$_Deque_val@U?$_Deque_simple_types@D@std@@@std@@@0@0@Z; std::reverse<std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>>(std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>,std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>)
0x180006368  mov     [rsp+78h+var_48], rbx
0x18000636d  mov     [rsp+78h+var_40], rdi
0x180006372  mov     [rsp+78h+var_58], rbx
0x180006377  mov     [rsp+78h+var_50], rsi
0x18000637c  lea     rdx, [rsp+78h+var_48]
0x180006381  lea     rcx, [rsp+78h+var_58]
0x180006386  call    ??$reverse@V?$_Deque_unchecked_iterator@V?$_Deque_val@U?$_Deque_simple_types@D@std@@@std@@@std@@@std@@YAXV?$_Deque_unchecked_iterator@V?$_Deque_val@U?$_Deque_simple_types@D@std@@@std@@@0@0@Z; std::reverse<std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>>(std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>,std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>)
0x18000638b  mov     [rsp+78h+var_48], rbx
0x180006390  mov     [rsp+78h+var_40], rdi
0x180006395  mov     [rsp+78h+var_58], rbx
0x18000639a  mov     [rsp+78h+var_50], rbp
0x18000639f  lea     rdx, [rsp+78h+var_48]
0x1800063a4  lea     rcx, [rsp+78h+var_58]
0x1800063a9  call    ??$reverse@V?$_Deque_unchecked_iterator@V?$_Deque_val@U?$_Deque_simple_types@D@std@@@std@@@std@@@std@@YAXV?$_Deque_unchecked_iterator@V?$_Deque_val@U?$_Deque_simple_types@D@std@@@std@@@0@0@Z; std::reverse<std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>>(std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>,std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>)
0x1800063ae  jmp     loc_18000627B
0x1800063b3  lea     rax, [rdi+10h]
0x1800063b7  shr     rax, 4
0x1800063bb  cmp     [rbx+10h], rax
0x1800063bf  ja      loc_18000620F
0x1800063c5  mov     rcx, rbx
0x1800063c8  call    ?_Growmap@?$deque@DV?$allocator@D@std@@@std@@AEAAX_K@Z; std::deque<char>::_Growmap(unsigned __int64)
0x1800063cd  jmp     loc_18000620F
0x1800063d2  add     rax, 10h
0x1800063d6  shr     rax, 4
0x1800063da  cmp     [rbx+10h], rax
0x1800063de  ja      loc_1800062AE
0x1800063e4  mov     rcx, rbx
0x1800063e7  call    ?_Growmap@?$deque@DV?$allocator@D@std@@@std@@AEAAX_K@Z; std::deque<char>::_Growmap(unsigned __int64)
0x1800063ec  jmp     loc_1800062AE
0x1800063f1  mov     ecx, 10h; dwBytes
0x1800063f6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800063fb  mov     rcx, [rbx+8]
0x1800063ff  mov     [r12+rcx], rax
0x180006403  jmp     loc_1800062F2
```
