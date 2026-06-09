# std::_Hash<std::_Umap_traits<_WHESVC_SCENARIOS,_WNF_STATE_NAME,std::_Uhash_compare<_WHESVC_SCENARIOS,std::hash<_WHESVC_SCENARIOS>,std::equal_to<_WHESVC_SCENARIOS>>,std::allocator<std::pair<_WHESVC_SCENARIOS const,_WNF_STATE_NAME>>,0>>::_Unchecked_erase(std::_List_node<std::pair<_WHESVC_SCENARIOS const,_WNF_STATE_NAME>,void *> *,std::_List_node<std::pair<_WHESVC_SCENARIOS const,_WNF_STATE_NAME>,void *> * const)

- ea: `0x180017180`
- end: `0x1800172ea`
- name: `?_Unchecked_erase@?$_Hash@V?$_Umap_traits@W4_WHESVC_SCENARIOS@@U_WNF_STATE_NAME@@V?$_Uhash_compare@W4_WHESVC_SCENARIOS@@U?$hash@W4_WHESVC_SCENARIOS@@@std@@U?$equal_to@W4_WHESVC_SCENARIOS@@@3@@std@@V?$allocator@U?$pair@$$CBW4_WHESVC_SCENARIOS@@U_WNF_STATE_NAME@@@std@@@4@$0A@@std@@@std@@AEAAPEAU?$_List_node@U?$pair@$$CBW4_WHESVC_SCENARIOS@@U_WNF_STATE_NAME@@@std@@PEAX@2@PEAU32@QEAU32@@Z`
- size: `362`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180017864`

## callees

- `0x180003304`
- `0x180017180`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Umap_traits<enum _WHESVC_SCENARIOS,_WNF_STATE_NAME,std::_Uhash_compare<enum _WHESVC_SCENARIOS,std::hash<enum _WHESVC_SCENARIOS>,std::equal_to<enum _WHESVC_SCENARIOS>>,std::allocator<std::pair<enum _WHESVC_SCENARIOS const,_WNF_STATE_NAME>>,0>>::_Unchecked_erase(
        _QWORD *a1,
        _QWORD *a2,
        _QWORD *a3)
{
  _QWORD *v6; // rax
  _QWORD *v7; // rdi
  __int64 v8; // r12
  __int64 v9; // r15
  _QWORD *v10; // r14
  unsigned __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // r15
  void *v14; // rcx
  _QWORD *v15; // rbx
  _QWORD *v17; // rax
  __int64 v18; // rcx
  unsigned __int64 i; // rdx
  __int64 v20; // rax
  void *v21; // rcx
  _QWORD *v22; // rbx
  _QWORD *v23; // [rsp+68h] [rbp+10h]
  _QWORD *v24; // [rsp+70h] [rbp+18h]
  _QWORD *v25; // [rsp+70h] [rbp+18h]
  _QWORD *v26; // [rsp+78h] [rbp+20h]

  if ( a2 != a3 )
  {
    v6 = (_QWORD *)a1[1];
    v7 = a2;
    v8 = a1[3];
    v9 = 0xCBF29CE484222325uLL;
    v10 = (_QWORD *)a2[1];
    v11 = 0;
    v23 = v6;
    do
    {
      v12 = *((unsigned __int8 *)a2 + v11 + 16);
      ++v11;
      v9 = 0x100000001B3LL * (v12 ^ v9);
    }
    while ( v11 < 4 );
    v13 = 2 * (a1[6] & v9);
    v24 = *(_QWORD **)(v8 + 8 * v13);
    v26 = *(_QWORD **)(v8 + 8 * v13 + 8);
    while ( 1 )
    {
      v14 = v7;
      v15 = v7;
      v7 = (_QWORD *)*v7;
      operator delete(v14);
      --a1[2];
      if ( v15 == v26 )
        break;
      if ( v7 == a3 )
      {
        if ( v24 == a2 )
LABEL_8:
          *(_QWORD *)(v8 + 8 * v13) = v7;
        goto LABEL_9;
      }
    }
    if ( v24 == a2 )
    {
      *(_QWORD *)(v8 + 8 * v13) = v23;
      v17 = v23;
    }
    else
    {
      v17 = v10;
    }
    *(_QWORD *)(v8 + 8 * v13 + 8) = v17;
    while ( v7 != a3 )
    {
      v18 = 0xCBF29CE484222325uLL;
      for ( i = 0; i < 4; ++i )
      {
        v20 = *((unsigned __int8 *)v7 + i + 16);
        v18 = 0x100000001B3LL * (v20 ^ v18);
      }
      v13 = 2 * (v18 & a1[6]);
      v25 = *(_QWORD **)(v8 + 16 * (v18 & a1[6]) + 8);
      while ( 1 )
      {
        v21 = v7;
        v22 = v7;
        v7 = (_QWORD *)*v7;
        operator delete(v21);
        --a1[2];
        if ( v22 == v25 )
          break;
        if ( v7 == a3 )
          goto LABEL_8;
      }
      *(_QWORD *)(v8 + 8 * v13) = v23;
      *(_QWORD *)(v8 + 8 * v13 + 8) = v23;
    }
LABEL_9:
    *v10 = v7;
    v7[1] = v10;
  }
  return a3;
}

```

## disassembly

```asm
0x180017180  mov     [rsp+arg_0], rbx
0x180017185  push    rbp
0x180017186  push    rsi
0x180017187  push    rdi
0x180017188  push    r12
0x18001718a  push    r13
0x18001718c  push    r14
0x18001718e  push    r15
0x180017190  sub     rsp, 20h
0x180017194  mov     rsi, r8
0x180017197  mov     rbp, rdx
0x18001719a  mov     r13, rcx
0x18001719d  cmp     rdx, r8
0x1800171a0  jz      loc_180017234
0x1800171a6  mov     rax, [rcx+8]
0x1800171aa  mov     rdi, rdx
0x1800171ad  mov     r12, [rcx+18h]
0x1800171b1  mov     r15, 0CBF29CE484222325h
0x1800171bb  mov     r14, [rdx+8]
0x1800171bf  xor     ecx, ecx
0x1800171c1  mov     [rsp+58h+arg_8], rax
0x1800171c6  mov     rdx, 100000001B3h
0x1800171d0  movzx   eax, byte ptr [rcx+rbp+10h]
0x1800171d5  inc     rcx
0x1800171d8  xor     r15, rax
0x1800171db  imul    r15, rdx
0x1800171df  cmp     rcx, 4
0x1800171e3  jb      short loc_1800171D0
0x1800171e5  and     r15, [r13+30h]
0x1800171e9  add     r15, r15
0x1800171ec  mov     rax, [r12+r15*8]
0x1800171f0  mov     [rsp+58h+arg_10], rax
0x1800171f5  mov     rax, [r12+r15*8+8]
0x1800171fa  mov     [rsp+58h+arg_18], rax
0x1800171ff  mov     rcx, rdi; void *
0x180017202  mov     rbx, rdi
0x180017205  mov     rdi, [rdi]
0x180017208  mov     edx, 20h ; ' '; unsigned __int64
0x18001720d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180017212  dec     qword ptr [r13+10h]
0x180017216  cmp     rbx, [rsp+58h+arg_18]
0x18001721b  jz      short loc_18001724C
0x18001721d  cmp     rdi, rsi
0x180017220  jnz     short loc_1800171FF
0x180017222  cmp     [rsp+58h+arg_10], rbp
0x180017227  jnz     short loc_18001722D
0x180017229  mov     [r12+r15*8], rdi
0x18001722d  mov     [r14], rdi
0x180017230  mov     [rdi+8], r14
0x180017234  mov     rbx, [rsp+58h+arg_0]
0x180017239  mov     rax, rsi
0x18001723c  add     rsp, 20h
0x180017240  pop     r15
0x180017242  pop     r14
0x180017244  pop     r13
0x180017246  pop     r12
0x180017248  pop     rdi
0x180017249  pop     rsi
0x18001724a  pop     rbp
0x18001724b  retn
0x18001724c  cmp     [rsp+58h+arg_10], rbp
0x180017251  jnz     short loc_180017261
0x180017253  mov     rbp, [rsp+58h+arg_8]
0x180017258  mov     [r12+r15*8], rbp
0x18001725c  mov     rax, rbp
0x18001725f  jmp     short loc_180017264
0x180017261  mov     rax, r14
0x180017264  mov     [r12+r15*8+8], rax
0x180017269  jmp     short loc_1800172E0
0x18001726b  mov     rcx, 0CBF29CE484222325h
0x180017275  xor     edx, edx
0x180017277  mov     rbp, 100000001B3h
0x180017281  movzx   eax, byte ptr [rdi+rdx+10h]
0x180017286  inc     rdx
0x180017289  xor     rcx, rax
0x18001728c  imul    rcx, rbp
0x180017290  cmp     rdx, 4
0x180017294  jb      short loc_180017281
0x180017296  mov     r15, [r13+30h]
0x18001729a  mov     rbp, [rsp+58h+arg_8]
0x18001729f  and     r15, rcx
0x1800172a2  add     r15, r15
0x1800172a5  mov     rax, [r12+r15*8+8]
0x1800172aa  mov     [rsp+58h+arg_10], rax
0x1800172af  mov     rcx, rdi; void *
0x1800172b2  mov     rbx, rdi
0x1800172b5  mov     rdi, [rdi]
0x1800172b8  mov     edx, 20h ; ' '; unsigned __int64
0x1800172bd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800172c2  dec     qword ptr [r13+10h]
0x1800172c6  cmp     rbx, [rsp+58h+arg_10]
0x1800172cb  jz      short loc_1800172D7
0x1800172cd  cmp     rdi, rsi
0x1800172d0  jnz     short loc_1800172AF
0x1800172d2  jmp     loc_180017229
0x1800172d7  mov     [r12+r15*8], rbp
0x1800172db  mov     [r12+r15*8+8], rbp
0x1800172e0  cmp     rdi, rsi
0x1800172e3  jnz     short loc_18001726B
0x1800172e5  jmp     loc_18001722D
```
