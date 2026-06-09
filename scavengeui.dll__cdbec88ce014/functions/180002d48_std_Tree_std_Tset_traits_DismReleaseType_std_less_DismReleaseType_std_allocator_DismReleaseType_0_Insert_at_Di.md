# std::_Tree<std::_Tset_traits<_DismReleaseType,std::less<_DismReleaseType>,std::allocator<_DismReleaseType>,0>>::_Insert_at<_DismReleaseType,std::_Nil>(bool,std::_Tree_node<_DismReleaseType,void *> *,_DismReleaseType &&,std::_Nil)

- ea: `0x180002d48`
- end: `0x180002fc3`
- name: `??$_Insert_at@W4_DismReleaseType@@U_Nil@std@@@?$_Tree@V?$_Tset_traits@W4_DismReleaseType@@U?$less@W4_DismReleaseType@@@std@@V?$allocator@W4_DismReleaseType@@@3@$0A@@std@@@std@@IEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@W4_DismReleaseType@@@std@@@std@@@1@_NPEAU?$_Tree_node@W4_DismReleaseType@@PEAX@1@$$QEAW4_DismReleaseType@@U_Nil@1@@Z`
- size: `635`
- prototype: `__int64 *__fastcall(_QWORD *, __int64 *, char, __int64 *, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180002fcc`

## callees

- `0x1800013d8`
- `0x180002d1c`
- `0x180002d48`

## pseudocode

```c
__int64 *__fastcall std::_Tree<std::_Tset_traits<enum _DismReleaseType,std::less<enum _DismReleaseType>,std::allocator<enum _DismReleaseType>,0>>::_Insert_at<enum _DismReleaseType,std::_Nil>(
        _QWORD *a1,
        __int64 *a2,
        char a3,
        __int64 *a4,
        _DWORD *a5)
{
  __int64 v9; // rax
  __int64 v10; // r9
  __int64 v11; // rax
  _QWORD *v12; // rdx
  __int64 v13; // rcx
  __int64 *v14; // r8
  __int64 v15; // rax
  _QWORD *v16; // r8
  _QWORD *v17; // rax
  _QWORD *v18; // rcx
  _QWORD *v19; // r8
  __int64 v20; // rax
  _QWORD *v21; // rax
  _QWORD *v22; // r8
  __int64 v23; // rax
  _QWORD *v24; // rax
  _QWORD *v25; // rax
  __int64 v26; // rax
  __int64 v27; // rcx
  __int64 *result; // rax

  if ( a1[1] >= 0x7FFFFFFFFFFFFFEuLL )
    std::_Xlength_error("map/set<T> too long");
  v9 = std::_Tree_buy<enum _DismReleaseType>::_Buynode<enum _DismReleaseType>((__int64)a1, a5);
  ++a1[1];
  v10 = v9;
  *(_QWORD *)(v9 + 8) = a4;
  if ( a4 == (__int64 *)*a1 )
  {
    *(_QWORD *)(*a1 + 8LL) = v9;
    *(_QWORD *)*a1 = v9;
    *(_QWORD *)(*a1 + 16LL) = v9;
  }
  else if ( a3 )
  {
    *a4 = v9;
    if ( a4 == *(__int64 **)*a1 )
      *(_QWORD *)*a1 = v9;
  }
  else
  {
    a4[2] = v9;
    if ( a4 == *(__int64 **)(*a1 + 16LL) )
      *(_QWORD *)(*a1 + 16LL) = v9;
  }
  v11 = *(_QWORD *)(v9 + 8);
  v12 = (_QWORD *)v10;
  while ( !*(_BYTE *)(v11 + 24) )
  {
    v13 = v12[1];
    v14 = *(__int64 **)(v13 + 8);
    v15 = *v14;
    if ( v13 == *v14 )
    {
      v15 = v14[2];
      if ( !*(_BYTE *)(v15 + 24) )
        goto LABEL_30;
      v16 = *(_QWORD **)(v13 + 16);
      if ( v12 == v16 )
      {
        v12 = (_QWORD *)v12[1];
        *(_QWORD *)(v13 + 16) = *v16;
        if ( !*(_BYTE *)(*v16 + 25LL) )
          *(_QWORD *)(*v16 + 8LL) = v13;
        v16[1] = *(_QWORD *)(v13 + 8);
        if ( v13 == *(_QWORD *)(*a1 + 8LL) )
        {
          *(_QWORD *)(*a1 + 8LL) = v16;
        }
        else
        {
          v17 = *(_QWORD **)(v13 + 8);
          if ( v13 == *v17 )
            *v17 = v16;
          else
            v17[2] = v16;
        }
        *v16 = v13;
        *(_QWORD *)(v13 + 8) = v16;
      }
      *(_BYTE *)(v12[1] + 24LL) = 1;
      *(_BYTE *)(*(_QWORD *)(v12[1] + 8LL) + 24LL) = 0;
      v18 = *(_QWORD **)(v12[1] + 8LL);
      v19 = (_QWORD *)*v18;
      *v18 = *(_QWORD *)(*v18 + 16LL);
      v20 = v19[2];
      if ( !*(_BYTE *)(v20 + 25) )
        *(_QWORD *)(v20 + 8) = v18;
      v19[1] = v18[1];
      if ( v18 == *(_QWORD **)(*a1 + 8LL) )
      {
        *(_QWORD *)(*a1 + 8LL) = v19;
      }
      else
      {
        v21 = (_QWORD *)v18[1];
        if ( v18 == (_QWORD *)v21[2] )
          v21[2] = v19;
        else
          *v21 = v19;
      }
      v19[2] = v18;
    }
    else
    {
      if ( !*(_BYTE *)(v15 + 24) )
      {
LABEL_30:
        *(_BYTE *)(v13 + 24) = 1;
        *(_BYTE *)(v15 + 24) = 1;
        *(_BYTE *)(*(_QWORD *)(v12[1] + 8LL) + 24LL) = 0;
        v12 = *(_QWORD **)(v12[1] + 8LL);
        goto LABEL_49;
      }
      v22 = *(_QWORD **)v13;
      if ( v12 == *(_QWORD **)v13 )
      {
        v12 = (_QWORD *)v12[1];
        *(_QWORD *)v13 = v22[2];
        v23 = v22[2];
        if ( !*(_BYTE *)(v23 + 25) )
          *(_QWORD *)(v23 + 8) = v13;
        v22[1] = *(_QWORD *)(v13 + 8);
        if ( v13 == *(_QWORD *)(*a1 + 8LL) )
        {
          *(_QWORD *)(*a1 + 8LL) = v22;
        }
        else
        {
          v24 = *(_QWORD **)(v13 + 8);
          if ( v13 == v24[2] )
            v24[2] = v22;
          else
            *v24 = v22;
        }
        v22[2] = v13;
        *(_QWORD *)(v13 + 8) = v22;
      }
      *(_BYTE *)(v12[1] + 24LL) = 1;
      *(_BYTE *)(*(_QWORD *)(v12[1] + 8LL) + 24LL) = 0;
      v18 = *(_QWORD **)(v12[1] + 8LL);
      v19 = (_QWORD *)v18[2];
      v18[2] = *v19;
      if ( !*(_BYTE *)(*v19 + 25LL) )
        *(_QWORD *)(*v19 + 8LL) = v18;
      v19[1] = v18[1];
      if ( v18 == *(_QWORD **)(*a1 + 8LL) )
      {
        *(_QWORD *)(*a1 + 8LL) = v19;
      }
      else
      {
        v25 = (_QWORD *)v18[1];
        if ( v18 == (_QWORD *)*v25 )
          *v25 = v19;
        else
          v25[2] = v19;
      }
      *v19 = v18;
    }
    v18[1] = v19;
LABEL_49:
    v11 = v12[1];
  }
  v26 = *a1;
  *a2 = v10;
  v27 = *(_QWORD *)(v26 + 8);
  result = a2;
  *(_BYTE *)(v27 + 24) = 1;
  return result;
}

```

## disassembly

```asm
0x180002d48  push    rbx
0x180002d4a  push    rsi
0x180002d4b  push    rdi
0x180002d4c  push    r14
0x180002d4e  sub     rsp, 28h
0x180002d52  mov     rax, 7FFFFFFFFFFFFFEh
0x180002d5c  mov     rdi, r9
0x180002d5f  mov     sil, r8b
0x180002d62  mov     r14, rdx
0x180002d65  mov     rbx, rcx
0x180002d68  cmp     [rcx+8], rax
0x180002d6c  jnb     loc_180002FB6
0x180002d72  mov     rdx, [rsp+48h+arg_20]
0x180002d77  call    ??$_Buynode@W4_DismReleaseType@@@?$_Tree_buy@W4_DismReleaseType@@V?$allocator@W4_DismReleaseType@@@std@@@std@@QEAAPEAU?$_Tree_node@W4_DismReleaseType@@PEAX@1@$$QEAW4_DismReleaseType@@@Z; std::_Tree_buy<_DismReleaseType>::_Buynode<_DismReleaseType>(_DismReleaseType &&)
0x180002d7c  inc     qword ptr [rbx+8]
0x180002d80  mov     r9, rax
0x180002d83  xor     r10d, r10d
0x180002d86  mov     [rax+8], rdi
0x180002d8a  mov     rax, [rbx]
0x180002d8d  cmp     rdi, rax
0x180002d90  jnz     short loc_180002DA5
0x180002d92  mov     [rax+8], r9
0x180002d96  mov     rcx, [rbx]
0x180002d99  mov     [rcx], r9
0x180002d9c  mov     rcx, [rbx]
0x180002d9f  mov     [rcx+10h], r9
0x180002da3  jmp     short loc_180002DCB
0x180002da5  test    sil, sil
0x180002da8  jz      short loc_180002DBA
0x180002daa  mov     [rdi], r9
0x180002dad  mov     rax, [rbx]
0x180002db0  cmp     rdi, [rax]
0x180002db3  jnz     short loc_180002DCB
0x180002db5  mov     [rax], r9
0x180002db8  jmp     short loc_180002DCB
0x180002dba  mov     [rdi+10h], r9
0x180002dbe  mov     rax, [rbx]
0x180002dc1  cmp     rdi, [rax+10h]
0x180002dc5  jnz     short loc_180002DCB
0x180002dc7  mov     [rax+10h], r9
0x180002dcb  mov     rax, [r9+8]
0x180002dcf  mov     rdx, r9
0x180002dd2  jmp     loc_180002F91
0x180002dd7  mov     rcx, [rdx+8]
0x180002ddb  mov     r8, [rcx+8]
0x180002ddf  mov     rax, [r8]
0x180002de2  cmp     rcx, rax
0x180002de5  jnz     loc_180002EB0
0x180002deb  mov     rax, [r8+10h]
0x180002def  cmp     [rax+18h], r10b
0x180002df3  jz      loc_180002EB6
0x180002df9  mov     r8, [rcx+10h]
0x180002dfd  cmp     rdx, r8
0x180002e00  jnz     short loc_180002E49
0x180002e02  mov     rax, [r8]
0x180002e05  mov     rdx, rcx
0x180002e08  mov     [rcx+10h], rax
0x180002e0c  mov     rax, [r8]
0x180002e0f  cmp     [rax+19h], r10b
0x180002e13  jnz     short loc_180002E19
0x180002e15  mov     [rax+8], rcx
0x180002e19  mov     rax, [rcx+8]
0x180002e1d  mov     [r8+8], rax
0x180002e21  mov     rax, [rbx]
0x180002e24  cmp     rcx, [rax+8]
0x180002e28  jnz     short loc_180002E30
0x180002e2a  mov     [rax+8], r8
0x180002e2e  jmp     short loc_180002E42
0x180002e30  mov     rax, [rcx+8]
0x180002e34  cmp     rcx, [rax]
0x180002e37  jnz     short loc_180002E3E
0x180002e39  mov     [rax], r8
0x180002e3c  jmp     short loc_180002E42
0x180002e3e  mov     [rax+10h], r8
0x180002e42  mov     [r8], rcx
0x180002e45  mov     [rcx+8], r8
0x180002e49  mov     rax, [rdx+8]
0x180002e4d  mov     byte ptr [rax+18h], 1
0x180002e51  mov     rax, [rdx+8]
0x180002e55  mov     rcx, [rax+8]
0x180002e59  mov     [rcx+18h], r10b
0x180002e5d  mov     rax, [rdx+8]
0x180002e61  mov     rcx, [rax+8]
0x180002e65  mov     r8, [rcx]
0x180002e68  mov     rax, [r8+10h]
0x180002e6c  mov     [rcx], rax
0x180002e6f  mov     rax, [r8+10h]
0x180002e73  cmp     [rax+19h], r10b
0x180002e77  jnz     short loc_180002E7D
0x180002e79  mov     [rax+8], rcx
0x180002e7d  mov     rax, [rcx+8]
0x180002e81  mov     [r8+8], rax
0x180002e85  mov     rax, [rbx]
0x180002e88  cmp     rcx, [rax+8]
0x180002e8c  jnz     short loc_180002E94
0x180002e8e  mov     [rax+8], r8
0x180002e92  jmp     short loc_180002EA7
0x180002e94  mov     rax, [rcx+8]
0x180002e98  cmp     rcx, [rax+10h]
0x180002e9c  jnz     short loc_180002EA4
0x180002e9e  mov     [rax+10h], r8
0x180002ea2  jmp     short loc_180002EA7
0x180002ea4  mov     [rax], r8
0x180002ea7  mov     [r8+10h], rcx
0x180002eab  jmp     loc_180002F89
0x180002eb0  cmp     [rax+18h], r10b
0x180002eb4  jnz     short loc_180002ED7
0x180002eb6  mov     byte ptr [rcx+18h], 1
0x180002eba  mov     byte ptr [rax+18h], 1
0x180002ebe  mov     rax, [rdx+8]
0x180002ec2  mov     rcx, [rax+8]
0x180002ec6  mov     [rcx+18h], r10b
0x180002eca  mov     rax, [rdx+8]
0x180002ece  mov     rdx, [rax+8]
0x180002ed2  jmp     loc_180002F8D
0x180002ed7  mov     r8, [rcx]
0x180002eda  cmp     rdx, r8
0x180002edd  jnz     short loc_180002F29
0x180002edf  mov     rax, [r8+10h]
0x180002ee3  mov     rdx, rcx
0x180002ee6  mov     [rcx], rax
0x180002ee9  mov     rax, [r8+10h]
0x180002eed  cmp     [rax+19h], r10b
0x180002ef1  jnz     short loc_180002EF7
0x180002ef3  mov     [rax+8], rcx
0x180002ef7  mov     rax, [rcx+8]
0x180002efb  mov     [r8+8], rax
0x180002eff  mov     rax, [rbx]
0x180002f02  cmp     rcx, [rax+8]
0x180002f06  jnz     short loc_180002F0E
0x180002f08  mov     [rax+8], r8
0x180002f0c  jmp     short loc_180002F21
0x180002f0e  mov     rax, [rcx+8]
0x180002f12  cmp     rcx, [rax+10h]
0x180002f16  jnz     short loc_180002F1E
0x180002f18  mov     [rax+10h], r8
0x180002f1c  jmp     short loc_180002F21
0x180002f1e  mov     [rax], r8
0x180002f21  mov     [r8+10h], rcx
0x180002f25  mov     [rcx+8], r8
0x180002f29  mov     rax, [rdx+8]
0x180002f2d  mov     byte ptr [rax+18h], 1
0x180002f31  mov     rax, [rdx+8]
0x180002f35  mov     rcx, [rax+8]
0x180002f39  mov     [rcx+18h], r10b
0x180002f3d  mov     rax, [rdx+8]
0x180002f41  mov     rcx, [rax+8]
0x180002f45  mov     r8, [rcx+10h]
0x180002f49  mov     rax, [r8]
0x180002f4c  mov     [rcx+10h], rax
0x180002f50  mov     rax, [r8]
0x180002f53  cmp     [rax+19h], r10b
0x180002f57  jnz     short loc_180002F5D
0x180002f59  mov     [rax+8], rcx
0x180002f5d  mov     rax, [rcx+8]
0x180002f61  mov     [r8+8], rax
0x180002f65  mov     rax, [rbx]
0x180002f68  cmp     rcx, [rax+8]
0x180002f6c  jnz     short loc_180002F74
0x180002f6e  mov     [rax+8], r8
0x180002f72  jmp     short loc_180002F86
0x180002f74  mov     rax, [rcx+8]
0x180002f78  cmp     rcx, [rax]
0x180002f7b  jnz     short loc_180002F82
0x180002f7d  mov     [rax], r8
0x180002f80  jmp     short loc_180002F86
0x180002f82  mov     [rax+10h], r8
0x180002f86  mov     [r8], rcx
0x180002f89  mov     [rcx+8], r8
0x180002f8d  mov     rax, [rdx+8]
0x180002f91  cmp     [rax+18h], r10b
0x180002f95  jz      loc_180002DD7
0x180002f9b  mov     rax, [rbx]
0x180002f9e  mov     [r14], r9
0x180002fa1  mov     rcx, [rax+8]
0x180002fa5  mov     rax, r14
0x180002fa8  mov     byte ptr [rcx+18h], 1
0x180002fac  add     rsp, 28h
0x180002fb0  pop     r14
0x180002fb2  pop     rdi
0x180002fb3  pop     rsi
0x180002fb4  pop     rbx
0x180002fb5  retn
0x180002fb6  lea     rcx, aMapSetTTooLong; "map/set<T> too long"
0x180002fbd  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
