# std::_Tree<std::_Tmap_traits<ulong,wmi::AutoRef<Object>,std::less<ulong>,std::allocator<std::pair<ulong const,wmi::AutoRef<Object>>>,0>>::_Insert_at<std::pair<ulong const,wmi::AutoRef<Object>> &,std::_Tree_node<std::pair<ulong const,wmi::AutoRef<Object>>,void *> *>(bool,std::_Tree_node<std::pair<ulong const,wmi::AutoRef<Object>>,void *> *,std::pair<ulong const,wmi::AutoRef<Object>> &,std::_Tree_node<std::pair<ulong const,wmi::AutoRef<Object>>,void *> *)

- ea: `0x180002b60`
- end: `0x180002ddc`
- name: `??$_Insert_at@AEAU?$pair@$$CBKV?$AutoRef@VObject@@@wmi@@@std@@PEAU?$_Tree_node@U?$pair@$$CBKV?$AutoRef@VObject@@@wmi@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@KV?$AutoRef@VObject@@@wmi@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKV?$AutoRef@VObject@@@wmi@@@std@@@4@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$AutoRef@VObject@@@wmi@@@std@@@std@@@std@@@1@_NPEAU?$_Tree_node@U?$pair@$$CBKV?$AutoRef@VObject@@@wmi@@@std@@PEAX@1@AEAU?$pair@$$CBKV?$AutoRef@VObject@@@wmi@@@1@1@Z`
- size: `636`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180002de4`
- `0x180002fdc`

## callees

- `0x180001300`
- `0x180002b60`
- `0x180003c98`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<unsigned long,wmi::AutoRef<Object>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,wmi::AutoRef<Object>>>,0>>::_Insert_at<std::pair<unsigned long const,wmi::AutoRef<Object>> &,std::_Tree_node<std::pair<unsigned long const,wmi::AutoRef<Object>>,void *> *>(
        _QWORD *a1,
        _QWORD *a2,
        char a3,
        _QWORD *a4,
        int a5,
        __int64 a6)
{
  unsigned __int64 v6; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 *v12; // rcx
  __int64 *v13; // r8
  __int64 *v14; // rax
  __int64 *v15; // r8
  __int64 **v16; // rax
  _QWORD *v17; // rcx
  _QWORD *v18; // r8
  __int64 v19; // rax
  _QWORD *v20; // rax
  __int64 v21; // r8
  __int64 v22; // rax
  _QWORD *v23; // rax
  _QWORD *v24; // rax
  __int64 v25; // rax
  __int64 v26; // rcx
  _QWORD *result; // rax

  v6 = a1[1];
  if ( v6 >= 0x555555555555554LL )
  {
    std::_Tree<std::_Tmap_traits<unsigned long,wmi::AutoRef<Object>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,wmi::AutoRef<Object>>>,0>>::_Destroy_if_not_nil(
      0x555555555555554LL,
      a6);
    std::_Xlength_error("map/set<T> too long");
  }
  a1[1] = v6 + 1;
  *(_QWORD *)(a6 + 8) = a4;
  if ( a4 == (_QWORD *)*a1 )
  {
    *(_QWORD *)(*a1 + 8LL) = a6;
    *(_QWORD *)*a1 = a6;
    v9 = *a1;
LABEL_8:
    *(_QWORD *)(v9 + 16) = a6;
    goto LABEL_9;
  }
  if ( a3 )
  {
    *a4 = a6;
    if ( a4 == *(_QWORD **)*a1 )
      *(_QWORD *)*a1 = a6;
    goto LABEL_9;
  }
  a4[2] = a6;
  v9 = *a1;
  if ( a4 == *(_QWORD **)(*a1 + 16LL) )
    goto LABEL_8;
LABEL_9:
  v10 = *(_QWORD *)(a6 + 8);
  v11 = a6;
  while ( !*(_BYTE *)(v10 + 24) )
  {
    v12 = *(__int64 **)(v11 + 8);
    v13 = (__int64 *)v12[1];
    v14 = (__int64 *)*v13;
    if ( v12 == (__int64 *)*v13 )
    {
      v14 = (__int64 *)v13[2];
      if ( !*((_BYTE *)v14 + 24) )
        goto LABEL_30;
      v15 = (__int64 *)v12[2];
      if ( (__int64 *)v11 == v15 )
      {
        v11 = *(_QWORD *)(v11 + 8);
        v12[2] = *v15;
        if ( !*(_BYTE *)(*v15 + 25) )
          *(_QWORD *)(*v15 + 8) = v12;
        v15[1] = v12[1];
        if ( v12 == *(__int64 **)(*a1 + 8LL) )
        {
          *(_QWORD *)(*a1 + 8LL) = v15;
        }
        else
        {
          v16 = (__int64 **)v12[1];
          if ( v12 == *v16 )
            *v16 = v15;
          else
            v16[2] = v15;
        }
        *v15 = (__int64)v12;
        v12[1] = (__int64)v15;
      }
      *(_BYTE *)(*(_QWORD *)(v11 + 8) + 24LL) = 1;
      *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v11 + 8) + 8LL) + 24LL) = 0;
      v17 = *(_QWORD **)(*(_QWORD *)(v11 + 8) + 8LL);
      v18 = (_QWORD *)*v17;
      *v17 = *(_QWORD *)(*v17 + 16LL);
      v19 = v18[2];
      if ( !*(_BYTE *)(v19 + 25) )
        *(_QWORD *)(v19 + 8) = v17;
      v18[1] = v17[1];
      if ( v17 == *(_QWORD **)(*a1 + 8LL) )
      {
        *(_QWORD *)(*a1 + 8LL) = v18;
      }
      else
      {
        v20 = (_QWORD *)v17[1];
        if ( v17 == (_QWORD *)v20[2] )
          v20[2] = v18;
        else
          *v20 = v18;
      }
      v18[2] = v17;
    }
    else
    {
      if ( !*((_BYTE *)v14 + 24) )
      {
LABEL_30:
        *((_BYTE *)v12 + 24) = 1;
        *((_BYTE *)v14 + 24) = 1;
        *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v11 + 8) + 8LL) + 24LL) = 0;
        v11 = *(_QWORD *)(*(_QWORD *)(v11 + 8) + 8LL);
        goto LABEL_49;
      }
      v21 = *v12;
      if ( v11 == *v12 )
      {
        v11 = *(_QWORD *)(v11 + 8);
        *v12 = *(_QWORD *)(v21 + 16);
        v22 = *(_QWORD *)(v21 + 16);
        if ( !*(_BYTE *)(v22 + 25) )
          *(_QWORD *)(v22 + 8) = v12;
        *(_QWORD *)(v21 + 8) = v12[1];
        if ( v12 == *(__int64 **)(*a1 + 8LL) )
        {
          *(_QWORD *)(*a1 + 8LL) = v21;
        }
        else
        {
          v23 = (_QWORD *)v12[1];
          if ( v12 == (__int64 *)v23[2] )
            v23[2] = v21;
          else
            *v23 = v21;
        }
        *(_QWORD *)(v21 + 16) = v12;
        v12[1] = v21;
      }
      *(_BYTE *)(*(_QWORD *)(v11 + 8) + 24LL) = 1;
      *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v11 + 8) + 8LL) + 24LL) = 0;
      v17 = *(_QWORD **)(*(_QWORD *)(v11 + 8) + 8LL);
      v18 = (_QWORD *)v17[2];
      v17[2] = *v18;
      if ( !*(_BYTE *)(*v18 + 25LL) )
        *(_QWORD *)(*v18 + 8LL) = v17;
      v18[1] = v17[1];
      if ( v17 == *(_QWORD **)(*a1 + 8LL) )
      {
        *(_QWORD *)(*a1 + 8LL) = v18;
      }
      else
      {
        v24 = (_QWORD *)v17[1];
        if ( v17 == (_QWORD *)*v24 )
          *v24 = v18;
        else
          v24[2] = v18;
      }
      *v18 = v17;
    }
    v17[1] = v18;
LABEL_49:
    v10 = *(_QWORD *)(v11 + 8);
  }
  v25 = *a1;
  *a2 = a6;
  v26 = *(_QWORD *)(v25 + 8);
  result = a2;
  *(_BYTE *)(v26 + 24) = 1;
  return result;
}

```

## disassembly

```asm
0x180002b60  mov     [rsp+arg_0], rbx
0x180002b65  push    rdi
0x180002b66  sub     rsp, 20h
0x180002b6a  mov     rax, [rcx+8]
0x180002b6e  mov     r11, rcx
0x180002b71  mov     rcx, 555555555555554h
0x180002b7b  mov     r10, r9
0x180002b7e  mov     rbx, rdx
0x180002b81  cmp     rax, rcx
0x180002b84  jnb     loc_180002DC5
0x180002b8a  mov     r9, [rsp+28h+arg_28]
0x180002b8f  inc     rax
0x180002b92  mov     [r11+8], rax
0x180002b96  xor     edi, edi
0x180002b98  mov     [r9+8], r10
0x180002b9c  mov     rax, [r11]
0x180002b9f  cmp     r10, rax
0x180002ba2  jnz     short loc_180002BB3
0x180002ba4  mov     [rax+8], r9
0x180002ba8  mov     rax, [r11]
0x180002bab  mov     [rax], r9
0x180002bae  mov     rax, [r11]
0x180002bb1  jmp     short loc_180002BD5
0x180002bb3  test    r8b, r8b
0x180002bb6  jz      short loc_180002BC8
0x180002bb8  mov     [r10], r9
0x180002bbb  mov     rax, [r11]
0x180002bbe  cmp     r10, [rax]
0x180002bc1  jnz     short loc_180002BD9
0x180002bc3  mov     [rax], r9
0x180002bc6  jmp     short loc_180002BD9
0x180002bc8  mov     [r10+10h], r9
0x180002bcc  mov     rax, [r11]
0x180002bcf  cmp     r10, [rax+10h]
0x180002bd3  jnz     short loc_180002BD9
0x180002bd5  mov     [rax+10h], r9
0x180002bd9  mov     rax, [r9+8]
0x180002bdd  mov     rdx, r9
0x180002be0  jmp     loc_180002D9F
0x180002be5  mov     rcx, [rdx+8]
0x180002be9  mov     r8, [rcx+8]
0x180002bed  mov     rax, [r8]
0x180002bf0  cmp     rcx, rax
0x180002bf3  jnz     loc_180002CBE
0x180002bf9  mov     rax, [r8+10h]
0x180002bfd  cmp     [rax+18h], dil
0x180002c01  jz      loc_180002CC4
0x180002c07  mov     r8, [rcx+10h]
0x180002c0b  cmp     rdx, r8
0x180002c0e  jnz     short loc_180002C57
0x180002c10  mov     rax, [r8]
0x180002c13  mov     rdx, rcx
0x180002c16  mov     [rcx+10h], rax
0x180002c1a  mov     rax, [r8]
0x180002c1d  cmp     [rax+19h], dil
0x180002c21  jnz     short loc_180002C27
0x180002c23  mov     [rax+8], rcx
0x180002c27  mov     rax, [rcx+8]
0x180002c2b  mov     [r8+8], rax
0x180002c2f  mov     rax, [r11]
0x180002c32  cmp     rcx, [rax+8]
0x180002c36  jnz     short loc_180002C3E
0x180002c38  mov     [rax+8], r8
0x180002c3c  jmp     short loc_180002C50
0x180002c3e  mov     rax, [rcx+8]
0x180002c42  cmp     rcx, [rax]
0x180002c45  jnz     short loc_180002C4C
0x180002c47  mov     [rax], r8
0x180002c4a  jmp     short loc_180002C50
0x180002c4c  mov     [rax+10h], r8
0x180002c50  mov     [r8], rcx
0x180002c53  mov     [rcx+8], r8
0x180002c57  mov     rax, [rdx+8]
0x180002c5b  mov     byte ptr [rax+18h], 1
0x180002c5f  mov     rax, [rdx+8]
0x180002c63  mov     rcx, [rax+8]
0x180002c67  mov     [rcx+18h], dil
0x180002c6b  mov     rax, [rdx+8]
0x180002c6f  mov     rcx, [rax+8]
0x180002c73  mov     r8, [rcx]
0x180002c76  mov     rax, [r8+10h]
0x180002c7a  mov     [rcx], rax
0x180002c7d  mov     rax, [r8+10h]
0x180002c81  cmp     [rax+19h], dil
0x180002c85  jnz     short loc_180002C8B
0x180002c87  mov     [rax+8], rcx
0x180002c8b  mov     rax, [rcx+8]
0x180002c8f  mov     [r8+8], rax
0x180002c93  mov     rax, [r11]
0x180002c96  cmp     rcx, [rax+8]
0x180002c9a  jnz     short loc_180002CA2
0x180002c9c  mov     [rax+8], r8
0x180002ca0  jmp     short loc_180002CB5
0x180002ca2  mov     rax, [rcx+8]
0x180002ca6  cmp     rcx, [rax+10h]
0x180002caa  jnz     short loc_180002CB2
0x180002cac  mov     [rax+10h], r8
0x180002cb0  jmp     short loc_180002CB5
0x180002cb2  mov     [rax], r8
0x180002cb5  mov     [r8+10h], rcx
0x180002cb9  jmp     loc_180002D97
0x180002cbe  cmp     [rax+18h], dil
0x180002cc2  jnz     short loc_180002CE5
0x180002cc4  mov     byte ptr [rcx+18h], 1
0x180002cc8  mov     byte ptr [rax+18h], 1
0x180002ccc  mov     rax, [rdx+8]
0x180002cd0  mov     rcx, [rax+8]
0x180002cd4  mov     [rcx+18h], dil
0x180002cd8  mov     rax, [rdx+8]
0x180002cdc  mov     rdx, [rax+8]
0x180002ce0  jmp     loc_180002D9B
0x180002ce5  mov     r8, [rcx]
0x180002ce8  cmp     rdx, r8
0x180002ceb  jnz     short loc_180002D37
0x180002ced  mov     rax, [r8+10h]
0x180002cf1  mov     rdx, rcx
0x180002cf4  mov     [rcx], rax
0x180002cf7  mov     rax, [r8+10h]
0x180002cfb  cmp     [rax+19h], dil
0x180002cff  jnz     short loc_180002D05
0x180002d01  mov     [rax+8], rcx
0x180002d05  mov     rax, [rcx+8]
0x180002d09  mov     [r8+8], rax
0x180002d0d  mov     rax, [r11]
0x180002d10  cmp     rcx, [rax+8]
0x180002d14  jnz     short loc_180002D1C
0x180002d16  mov     [rax+8], r8
0x180002d1a  jmp     short loc_180002D2F
0x180002d1c  mov     rax, [rcx+8]
0x180002d20  cmp     rcx, [rax+10h]
0x180002d24  jnz     short loc_180002D2C
0x180002d26  mov     [rax+10h], r8
0x180002d2a  jmp     short loc_180002D2F
0x180002d2c  mov     [rax], r8
0x180002d2f  mov     [r8+10h], rcx
0x180002d33  mov     [rcx+8], r8
0x180002d37  mov     rax, [rdx+8]
0x180002d3b  mov     byte ptr [rax+18h], 1
0x180002d3f  mov     rax, [rdx+8]
0x180002d43  mov     rcx, [rax+8]
0x180002d47  mov     [rcx+18h], dil
0x180002d4b  mov     rax, [rdx+8]
0x180002d4f  mov     rcx, [rax+8]
0x180002d53  mov     r8, [rcx+10h]
0x180002d57  mov     rax, [r8]
0x180002d5a  mov     [rcx+10h], rax
0x180002d5e  mov     rax, [r8]
0x180002d61  cmp     [rax+19h], dil
0x180002d65  jnz     short loc_180002D6B
0x180002d67  mov     [rax+8], rcx
0x180002d6b  mov     rax, [rcx+8]
0x180002d6f  mov     [r8+8], rax
0x180002d73  mov     rax, [r11]
0x180002d76  cmp     rcx, [rax+8]
0x180002d7a  jnz     short loc_180002D82
0x180002d7c  mov     [rax+8], r8
0x180002d80  jmp     short loc_180002D94
0x180002d82  mov     rax, [rcx+8]
0x180002d86  cmp     rcx, [rax]
0x180002d89  jnz     short loc_180002D90
0x180002d8b  mov     [rax], r8
0x180002d8e  jmp     short loc_180002D94
0x180002d90  mov     [rax+10h], r8
0x180002d94  mov     [r8], rcx
0x180002d97  mov     [rcx+8], r8
0x180002d9b  mov     rax, [rdx+8]
0x180002d9f  cmp     [rax+18h], dil
0x180002da3  jz      loc_180002BE5
0x180002da9  mov     rax, [r11]
0x180002dac  mov     [rbx], r9
0x180002daf  mov     rcx, [rax+8]
0x180002db3  mov     rax, rbx
0x180002db6  mov     rbx, [rsp+28h+arg_0]
0x180002dbb  mov     byte ptr [rcx+18h], 1
0x180002dbf  add     rsp, 20h
0x180002dc3  pop     rdi
0x180002dc4  retn
0x180002dc5  mov     rdx, [rsp+28h+arg_28]
0x180002dca  call    ?_Destroy_if_not_nil@?$_Tree@V?$_Tmap_traits@KV?$AutoRef@VObject@@@wmi@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKV?$AutoRef@VObject@@@wmi@@@std@@@4@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBKV?$AutoRef@VObject@@@wmi@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<ulong,wmi::AutoRef<Object>,std::less<ulong>,std::allocator<std::pair<ulong const,wmi::AutoRef<Object>>>,0>>::_Destroy_if_not_nil(std::_Tree_node<std::pair<ulong const,wmi::AutoRef<Object>>,void *> *)
0x180002dcf  lea     rcx, aMapSetTTooLong; "map/set<T> too long"
0x180002dd6  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
