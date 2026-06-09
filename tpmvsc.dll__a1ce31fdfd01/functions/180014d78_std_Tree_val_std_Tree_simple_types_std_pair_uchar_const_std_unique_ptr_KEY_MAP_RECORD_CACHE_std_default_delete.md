# std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE,std::default_delete<KEY_MAP_RECORD_CACHE>>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE,std::default_delete<KEY_MAP_RECORD_CACHE>>>>>,std::_Iterator_base0>)

- ea: `0x180014d78`
- end: `0x180014ffc`
- name: `?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z`
- size: `644`
- prototype: `__int64 *__fastcall(__int64 **, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180014cbc`

## callees

- `0x18000dd9c`
- `0x180014d78`
- `0x1800152f0`
- `0x180015340`
- `0x1800153a4`

## pseudocode

```c
__int64 *__fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>::_Extract(
        __int64 **a1,
        __int64 a2)
{
  __int64 v3; // rdx
  __int64 *v4; // r11
  __int64 v5; // r10
  __int64 v6; // r9
  __int64 *v7; // r8
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rax
  _QWORD *v11; // rax
  __int64 *v12; // rcx
  char v13; // cl
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 *v16; // rcx
  __int64 *v18; // [rsp+38h] [rbp+10h] BYREF

  v18 = (__int64 *)a2;
  std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>,std::_Iterator_base0>::operator++((__int64 *)&v18);
  v5 = v4[2];
  if ( *(_BYTE *)(*v4 + 25) )
    goto LABEL_5;
  if ( *(_BYTE *)(v5 + 25) )
  {
    v5 = *v4;
LABEL_5:
    v6 = v4[1];
    if ( !*(_BYTE *)(v5 + 25) )
      *(_QWORD *)(v5 + 8) = v6;
    if ( (__int64 *)(*a1)[1] == v4 )
    {
      (*a1)[1] = v5;
    }
    else if ( *(__int64 **)v6 == v4 )
    {
      *(_QWORD *)v6 = v5;
    }
    else
    {
      *(_QWORD *)(v6 + 16) = v5;
    }
    v7 = *a1;
    if ( (__int64 *)**a1 == v4 )
    {
      if ( *(_BYTE *)(v5 + 25) )
        v8 = v6;
      else
        v8 = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>::_Min(
               v5,
               v3,
               v7);
      *v7 = v8;
    }
    if ( (__int64 *)(*a1)[2] == v4 )
    {
      if ( *(_BYTE *)(v5 + 25) )
      {
        v9 = v6;
      }
      else
      {
        v10 = *(_QWORD *)(v5 + 16);
        v9 = v5;
        while ( !*(_BYTE *)(v10 + 25) )
        {
          v9 = *(_QWORD *)(v9 + 16);
          v10 = *(_QWORD *)(v9 + 16);
        }
      }
      (*a1)[2] = v9;
    }
    goto LABEL_35;
  }
  v3 = (__int64)v18;
  v5 = v18[2];
  if ( v18 == v4 )
    goto LABEL_5;
  *(_QWORD *)(*v4 + 8) = v18;
  *(_QWORD *)v3 = *v4;
  if ( v3 == v4[2] )
  {
    v6 = v3;
  }
  else
  {
    v6 = *(_QWORD *)(v3 + 8);
    if ( !*(_BYTE *)(v5 + 25) )
      *(_QWORD *)(v5 + 8) = v6;
    *(_QWORD *)v6 = v5;
    *(_QWORD *)(v3 + 16) = v4[2];
    *(_QWORD *)(v4[2] + 8) = v3;
  }
  if ( (__int64 *)(*a1)[1] == v4 )
  {
    (*a1)[1] = v3;
    v11 = v4 + 1;
  }
  else
  {
    v11 = v4 + 1;
    v12 = (__int64 *)v4[1];
    if ( (__int64 *)*v12 == v4 )
      *v12 = v3;
    else
      v12[2] = v3;
  }
  *(_QWORD *)(v3 + 8) = *v11;
  v13 = *(_BYTE *)(v3 + 24);
  *(_BYTE *)(v3 + 24) = *((_BYTE *)v4 + 24);
  *((_BYTE *)v4 + 24) = v13;
LABEL_35:
  if ( *((_BYTE *)v4 + 24) != 1 )
    goto LABEL_58;
  while ( v5 != (*a1)[1] && *(_BYTE *)(v5 + 24) == 1 )
  {
    v14 = *(_QWORD *)v6;
    if ( v5 == *(_QWORD *)v6 )
    {
      v14 = *(_QWORD *)(v6 + 16);
      if ( !*(_BYTE *)(v14 + 24) )
      {
        *(_BYTE *)(v14 + 24) = 1;
        *(_BYTE *)(v6 + 24) = 0;
        std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>::_Lrotate(a1);
        v14 = *(_QWORD *)(v6 + 16);
      }
      if ( !*(_BYTE *)(v14 + 25) )
      {
        if ( *(_BYTE *)(*(_QWORD *)v14 + 24LL) != 1 || *(_BYTE *)(*(_QWORD *)(v14 + 16) + 24LL) != 1 )
        {
          if ( *(_BYTE *)(*(_QWORD *)(v14 + 16) + 24LL) == 1 )
          {
            *(_BYTE *)(*(_QWORD *)v14 + 24LL) = 1;
            *(_BYTE *)(v14 + 24) = 0;
            std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>::_Rrotate(
              a1,
              v14);
            v14 = *(_QWORD *)(v6 + 16);
          }
          *(_BYTE *)(v14 + 24) = *(_BYTE *)(v6 + 24);
          *(_BYTE *)(v6 + 24) = 1;
          *(_BYTE *)(*(_QWORD *)(v14 + 16) + 24LL) = 1;
          std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>::_Lrotate(a1);
          break;
        }
LABEL_52:
        *(_BYTE *)(v14 + 24) = 0;
      }
    }
    else
    {
      if ( !*(_BYTE *)(v14 + 24) )
      {
        *(_BYTE *)(v14 + 24) = 1;
        *(_BYTE *)(v6 + 24) = 0;
        std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>::_Rrotate(
          a1,
          v6);
        v14 = *(_QWORD *)v6;
      }
      if ( !*(_BYTE *)(v14 + 25) )
      {
        v15 = *(_QWORD *)(v14 + 16);
        if ( *(_BYTE *)(v15 + 24) != 1 || *(_BYTE *)(*(_QWORD *)v14 + 24LL) != 1 )
        {
          if ( *(_BYTE *)(*(_QWORD *)v14 + 24LL) == 1 )
          {
            *(_BYTE *)(v15 + 24) = 1;
            *(_BYTE *)(v14 + 24) = 0;
            std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>::_Lrotate(a1);
            v14 = *(_QWORD *)v6;
          }
          *(_BYTE *)(v14 + 24) = *(_BYTE *)(v6 + 24);
          *(_BYTE *)(v6 + 24) = 1;
          *(_BYTE *)(*(_QWORD *)v14 + 24LL) = 1;
          std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>::_Rrotate(
            a1,
            v6);
          break;
        }
        goto LABEL_52;
      }
    }
    v5 = v6;
    v6 = *(_QWORD *)(v6 + 8);
  }
  *(_BYTE *)(v5 + 24) = 1;
LABEL_58:
  v16 = a1[1];
  if ( v16 )
    a1[1] = (__int64 *)((char *)v16 - 1);
  return v4;
}

```

## disassembly

```asm
0x180014d78  mov     [rsp+arg_0], rbx
0x180014d7d  mov     [rsp+arg_8], rdx
0x180014d82  push    rsi
0x180014d83  sub     rsp, 20h
0x180014d87  mov     rbx, rcx
0x180014d8a  mov     r11, rdx
0x180014d8d  lea     rcx, [rsp+28h+arg_8]
0x180014d92  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>,std::_Iterator_base0>::operator++(void)
0x180014d97  mov     r9, [r11]
0x180014d9a  xor     esi, esi
0x180014d9c  mov     r10, [r11+10h]
0x180014da0  cmp     [r9+19h], sil
0x180014da4  jnz     short loc_180014DBF
0x180014da6  cmp     [r10+19h], sil
0x180014daa  jz      short loc_180014DB1
0x180014dac  mov     r10, r9
0x180014daf  jmp     short loc_180014DBF
0x180014db1  mov     rdx, [rsp+28h+arg_8]
0x180014db6  mov     r10, [rdx+10h]
0x180014dba  cmp     rdx, r11
0x180014dbd  jnz     short loc_180014E3D
0x180014dbf  mov     r9, [r11+8]
0x180014dc3  cmp     [r10+19h], sil
0x180014dc7  jnz     short loc_180014DCD
0x180014dc9  mov     [r10+8], r9
0x180014dcd  mov     rax, [rbx]
0x180014dd0  cmp     [rax+8], r11
0x180014dd4  jnz     short loc_180014DDC
0x180014dd6  mov     [rax+8], r10
0x180014dda  jmp     short loc_180014DEA
0x180014ddc  cmp     [r9], r11
0x180014ddf  jnz     short loc_180014DE6
0x180014de1  mov     [r9], r10
0x180014de4  jmp     short loc_180014DEA
0x180014de6  mov     [r9+10h], r10
0x180014dea  mov     r8, [rbx]
0x180014ded  cmp     [r8], r11
0x180014df0  jnz     short loc_180014E08
0x180014df2  cmp     [r10+19h], sil
0x180014df6  jz      short loc_180014DFD
0x180014df8  mov     rax, r9
0x180014dfb  jmp     short loc_180014E05
0x180014dfd  mov     rcx, r10
0x180014e00  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>::_Min(std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *> *)
0x180014e05  mov     [r8], rax
0x180014e08  mov     rdx, [rbx]
0x180014e0b  cmp     [rdx+10h], r11
0x180014e0f  jnz     loc_180014EB0
0x180014e15  cmp     [r10+19h], sil
0x180014e19  jz      short loc_180014E20
0x180014e1b  mov     rcx, r9
0x180014e1e  jmp     short loc_180014E37
0x180014e20  mov     rax, [r10+10h]
0x180014e24  mov     rcx, r10
0x180014e27  jmp     short loc_180014E31
0x180014e29  mov     rcx, [rcx+10h]
0x180014e2d  mov     rax, [rcx+10h]
0x180014e31  cmp     [rax+19h], sil
0x180014e35  jz      short loc_180014E29
0x180014e37  mov     [rdx+10h], rcx
0x180014e3b  jmp     short loc_180014EB0
0x180014e3d  mov     [r9+8], rdx
0x180014e41  mov     rax, [r11]
0x180014e44  mov     [rdx], rax
0x180014e47  cmp     rdx, [r11+10h]
0x180014e4b  jnz     short loc_180014E52
0x180014e4d  mov     r9, rdx
0x180014e50  jmp     short loc_180014E73
0x180014e52  mov     r9, [rdx+8]
0x180014e56  cmp     [r10+19h], sil
0x180014e5a  jnz     short loc_180014E60
0x180014e5c  mov     [r10+8], r9
0x180014e60  mov     [r9], r10
0x180014e63  mov     rax, [r11+10h]
0x180014e67  mov     [rdx+10h], rax
0x180014e6b  mov     rax, [r11+10h]
0x180014e6f  mov     [rax+8], rdx
0x180014e73  mov     rax, [rbx]
0x180014e76  cmp     [rax+8], r11
0x180014e7a  jnz     short loc_180014E86
0x180014e7c  mov     [rax+8], rdx
0x180014e80  lea     rax, [r11+8]
0x180014e84  jmp     short loc_180014E9B
0x180014e86  lea     rax, [r11+8]
0x180014e8a  mov     rcx, [rax]
0x180014e8d  cmp     [rcx], r11
0x180014e90  jnz     short loc_180014E97
0x180014e92  mov     [rcx], rdx
0x180014e95  jmp     short loc_180014E9B
0x180014e97  mov     [rcx+10h], rdx
0x180014e9b  mov     rax, [rax]
0x180014e9e  mov     [rdx+8], rax
0x180014ea2  mov     al, [r11+18h]
0x180014ea6  mov     cl, [rdx+18h]
0x180014ea9  mov     [rdx+18h], al
0x180014eac  mov     [r11+18h], cl
0x180014eb0  cmp     byte ptr [r11+18h], 1
0x180014eb5  jnz     loc_180014FDE
0x180014ebb  mov     rax, [rbx]
0x180014ebe  cmp     r10, [rax+8]
0x180014ec2  jz      loc_180014FD9
0x180014ec8  cmp     byte ptr [r10+18h], 1
0x180014ecd  jnz     loc_180014FD9
0x180014ed3  mov     rdx, [r9]
0x180014ed6  cmp     r10, rdx
0x180014ed9  jnz     short loc_180014F5A
0x180014edb  mov     rdx, [r9+10h]
0x180014edf  cmp     [rdx+18h], sil
0x180014ee3  jnz     short loc_180014EFC
0x180014ee5  mov     byte ptr [rdx+18h], 1
0x180014ee9  mov     rcx, rbx
0x180014eec  mov     rdx, r9
0x180014eef  mov     [r9+18h], sil
0x180014ef3  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>::_Lrotate(std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *> *)
0x180014ef8  mov     rdx, [r9+10h]
0x180014efc  cmp     [rdx+19h], sil
0x180014f00  jnz     loc_180014F93
0x180014f06  mov     r8, [rdx]
0x180014f09  cmp     byte ptr [r8+18h], 1
0x180014f0e  jnz     short loc_180014F1A
0x180014f10  mov     rax, [rdx+10h]
0x180014f14  cmp     byte ptr [rax+18h], 1
0x180014f18  jz      short loc_180014F8F
0x180014f1a  mov     rax, [rdx+10h]
0x180014f1e  cmp     byte ptr [rax+18h], 1
0x180014f22  jnz     short loc_180014F39
0x180014f24  mov     byte ptr [r8+18h], 1
0x180014f29  mov     rcx, rbx
0x180014f2c  mov     [rdx+18h], sil
0x180014f30  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>::_Rrotate(std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *> *)
0x180014f35  mov     rdx, [r9+10h]
0x180014f39  mov     al, [r9+18h]
0x180014f3d  mov     rcx, rbx
0x180014f40  mov     [rdx+18h], al
0x180014f43  mov     byte ptr [r9+18h], 1
0x180014f48  mov     rax, [rdx+10h]
0x180014f4c  mov     rdx, r9
0x180014f4f  mov     byte ptr [rax+18h], 1
0x180014f53  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>::_Lrotate(std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *> *)
0x180014f58  jmp     short loc_180014FD9
0x180014f5a  cmp     [rdx+18h], sil
0x180014f5e  jnz     short loc_180014F76
0x180014f60  mov     byte ptr [rdx+18h], 1
0x180014f64  mov     rcx, rbx
0x180014f67  mov     rdx, r9
0x180014f6a  mov     [r9+18h], sil
0x180014f6e  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>::_Rrotate(std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *> *)
0x180014f73  mov     rdx, [r9]
0x180014f76  cmp     [rdx+19h], sil
0x180014f7a  jnz     short loc_180014F93
0x180014f7c  mov     rcx, [rdx+10h]
0x180014f80  cmp     byte ptr [rcx+18h], 1
0x180014f84  jnz     short loc_180014F9F
0x180014f86  mov     rax, [rdx]
0x180014f89  cmp     byte ptr [rax+18h], 1
0x180014f8d  jnz     short loc_180014F9F
0x180014f8f  mov     [rdx+18h], sil
0x180014f93  mov     r10, r9
0x180014f96  mov     r9, [r9+8]
0x180014f9a  jmp     loc_180014EBB
0x180014f9f  mov     rax, [rdx]
0x180014fa2  cmp     byte ptr [rax+18h], 1
0x180014fa6  jnz     short loc_180014FBB
0x180014fa8  mov     byte ptr [rcx+18h], 1
0x180014fac  mov     rcx, rbx
0x180014faf  mov     [rdx+18h], sil
0x180014fb3  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>::_Lrotate(std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *> *)
0x180014fb8  mov     rdx, [r9]
0x180014fbb  mov     al, [r9+18h]
0x180014fbf  mov     rcx, rbx
0x180014fc2  mov     [rdx+18h], al
0x180014fc5  mov     byte ptr [r9+18h], 1
0x180014fca  mov     rax, [rdx]
0x180014fcd  mov     rdx, r9
0x180014fd0  mov     byte ptr [rax+18h], 1
0x180014fd4  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>::_Rrotate(std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *> *)
0x180014fd9  mov     byte ptr [r10+18h], 1
0x180014fde  mov     rcx, [rbx+8]
0x180014fe2  test    rcx, rcx
0x180014fe5  jz      short loc_180014FEE
0x180014fe7  dec     rcx
0x180014fea  mov     [rbx+8], rcx
0x180014fee  mov     rbx, [rsp+28h+arg_0]
0x180014ff3  mov     rax, r11
0x180014ff6  add     rsp, 20h
0x180014ffa  pop     rsi
0x180014ffb  retn
```
