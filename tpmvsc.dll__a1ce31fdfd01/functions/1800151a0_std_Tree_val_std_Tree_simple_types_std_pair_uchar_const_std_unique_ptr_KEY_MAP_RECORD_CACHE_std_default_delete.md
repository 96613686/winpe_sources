# std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE,std::default_delete<KEY_MAP_RECORD_CACHE>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE,std::default_delete<KEY_MAP_RECORD_CACHE>>>,void *> *>,std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE,std::default_delete<KEY_MAP_RECORD_CACHE>>>,void *> * const)

- ea: `0x1800151a0`
- end: `0x1800152c9`
- name: `?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@std@@@2@QEAU32@@Z`
- size: `297`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d1b4`

## callees

- `0x1800151a0`
- `0x1800152f0`
- `0x1800153a4`

## pseudocode

```c
__int64 __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>::_Insert_node(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // r9
  _QWORD *v4; // r11
  _QWORD *v6; // rax
  __int64 v7; // rax
  __int64 i; // r10
  __int64 v9; // rdx
  __int64 *v10; // rcx
  __int64 v11; // rax

  ++*(_QWORD *)(a1 + 8);
  v3 = a3;
  v4 = *(_QWORD **)a1;
  v6 = *(_QWORD **)a2;
  *(_QWORD *)(a3 + 8) = *(_QWORD *)a2;
  if ( v6 != v4 )
  {
    if ( *(_DWORD *)(a2 + 8) )
    {
      *v6 = a3;
      if ( v6 == (_QWORD *)*v4 )
        *v4 = a3;
    }
    else
    {
      v6[2] = a3;
      if ( v6 == (_QWORD *)v4[2] )
        v4[2] = a3;
    }
    v7 = *(_QWORD *)(a3 + 8);
    for ( i = a3; ; v7 = *(_QWORD *)(i + 8) )
    {
      if ( *(_BYTE *)(v7 + 24) )
      {
        *(_BYTE *)(v4[1] + 24LL) = 1;
        return v3;
      }
      v9 = *(_QWORD *)(i + 8);
      v10 = *(__int64 **)(v9 + 8);
      v11 = *v10;
      if ( v9 == *v10 )
      {
        v11 = v10[2];
        if ( !*(_BYTE *)(v11 + 24) )
          goto LABEL_15;
        if ( i == *(_QWORD *)(v9 + 16) )
          std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>::_Lrotate(a1);
        *(_BYTE *)(*(_QWORD *)(i + 8) + 24LL) = 1;
        *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(i + 8) + 8LL) + 24LL) = 0;
        std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>::_Rrotate(
          a1,
          *(_QWORD *)(*(_QWORD *)(i + 8) + 8LL));
      }
      else
      {
        if ( !*(_BYTE *)(v11 + 24) )
        {
LABEL_15:
          *(_BYTE *)(v9 + 24) = 1;
          *(_BYTE *)(v11 + 24) = 1;
          *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(i + 8) + 8LL) + 24LL) = 0;
          i = *(_QWORD *)(*(_QWORD *)(i + 8) + 8LL);
          continue;
        }
        if ( i == *(_QWORD *)v9 )
          std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>::_Rrotate(
            a1,
            v9);
        *(_BYTE *)(*(_QWORD *)(i + 8) + 24LL) = 1;
        *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(i + 8) + 8LL) + 24LL) = 0;
        std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>::_Lrotate(a1);
      }
    }
  }
  *v4 = a3;
  v4[1] = a3;
  v4[2] = a3;
  *(_BYTE *)(a3 + 24) = 1;
  return v3;
}

```

## disassembly

```asm
0x1800151a0  push    rbx
0x1800151a2  sub     rsp, 20h
0x1800151a6  inc     qword ptr [rcx+8]
0x1800151aa  mov     r9, r8
0x1800151ad  mov     r11, [rcx]
0x1800151b0  mov     rbx, rcx
0x1800151b3  mov     rax, [rdx]
0x1800151b6  mov     [r8+8], rax
0x1800151ba  cmp     rax, r11
0x1800151bd  jnz     short loc_1800151D4
0x1800151bf  mov     [r11], r8
0x1800151c2  mov     [r11+8], r8
0x1800151c6  mov     [r11+10h], r8
0x1800151ca  mov     byte ptr [r8+18h], 1
0x1800151cf  jmp     loc_1800152C0
0x1800151d4  cmp     dword ptr [rdx+8], 0
0x1800151d8  jnz     short loc_1800151EA
0x1800151da  mov     [rax+10h], r9
0x1800151de  cmp     rax, [r11+10h]
0x1800151e2  jnz     short loc_1800151F5
0x1800151e4  mov     [r11+10h], r9
0x1800151e8  jmp     short loc_1800151F5
0x1800151ea  mov     [rax], r9
0x1800151ed  cmp     rax, [r11]
0x1800151f0  jnz     short loc_1800151F5
0x1800151f2  mov     [r11], r9
0x1800151f5  mov     rax, [r8+8]
0x1800151f9  mov     r10, r9
0x1800151fc  jmp     loc_1800152AE
0x180015201  mov     rdx, [r10+8]
0x180015205  mov     rcx, [rdx+8]
0x180015209  mov     rax, [rcx]
0x18001520c  cmp     rdx, rax
0x18001520f  jnz     short loc_180015252
0x180015211  mov     rax, [rcx+10h]
0x180015215  cmp     byte ptr [rax+18h], 0
0x180015219  jz      short loc_180015258
0x18001521b  cmp     r10, [rdx+10h]
0x18001521f  jnz     short loc_18001522C
0x180015221  mov     rcx, rbx
0x180015224  mov     r10, rdx
0x180015227  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>::_Lrotate(std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *> *)
0x18001522c  mov     rax, [r10+8]
0x180015230  mov     byte ptr [rax+18h], 1
0x180015234  mov     rax, [r10+8]
0x180015238  mov     rcx, [rax+8]
0x18001523c  mov     byte ptr [rcx+18h], 0
0x180015240  mov     rcx, rbx
0x180015243  mov     rdx, [r10+8]
0x180015247  mov     rdx, [rdx+8]
0x18001524b  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>::_Rrotate(std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *> *)
0x180015250  jmp     short loc_1800152AA
0x180015252  cmp     byte ptr [rax+18h], 0
0x180015256  jnz     short loc_180015276
0x180015258  mov     byte ptr [rdx+18h], 1
0x18001525c  mov     byte ptr [rax+18h], 1
0x180015260  mov     rax, [r10+8]
0x180015264  mov     rcx, [rax+8]
0x180015268  mov     byte ptr [rcx+18h], 0
0x18001526c  mov     rax, [r10+8]
0x180015270  mov     r10, [rax+8]
0x180015274  jmp     short loc_1800152AA
0x180015276  cmp     r10, [rdx]
0x180015279  jnz     short loc_180015286
0x18001527b  mov     rcx, rbx
0x18001527e  mov     r10, rdx
0x180015281  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>::_Rrotate(std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *> *)
0x180015286  mov     rax, [r10+8]
0x18001528a  mov     byte ptr [rax+18h], 1
0x18001528e  mov     rax, [r10+8]
0x180015292  mov     rcx, [rax+8]
0x180015296  mov     byte ptr [rcx+18h], 0
0x18001529a  mov     rcx, rbx
0x18001529d  mov     rdx, [r10+8]
0x1800152a1  mov     rdx, [rdx+8]
0x1800152a5  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>::_Lrotate(std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *> *)
0x1800152aa  mov     rax, [r10+8]
0x1800152ae  cmp     byte ptr [rax+18h], 0
0x1800152b2  jz      loc_180015201
0x1800152b8  mov     rax, [r11+8]
0x1800152bc  mov     byte ptr [rax+18h], 1
0x1800152c0  mov     rax, r9
0x1800152c3  add     rsp, 20h
0x1800152c7  pop     rbx
0x1800152c8  retn
```
