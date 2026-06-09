# std::_Tree<std::_Tmap_traits<uchar,std::unique_ptr<KEY_MAP_RECORD_CACHE,std::default_delete<KEY_MAP_RECORD_CACHE>>,std::less<uchar>,std::allocator<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE,std::default_delete<KEY_MAP_RECORD_CACHE>>>>,0>>::erase(uchar const &)

- ea: `0x1800157a0`
- end: `0x18001582d`
- name: `?erase@?$_Tree@V?$_Tmap_traits@EV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@U?$less@E@2@V?$allocator@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA_KAEBE@Z`
- size: `141`
- prototype: `__int64 __fastcall(__int64 *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f6a0`

## callees

- `0x180014cbc`
- `0x1800157a0`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tmap_traits<unsigned char,std::unique_ptr<KEY_MAP_RECORD_CACHE>,std::less<unsigned char>,std::allocator<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>,0>>::erase(
        __int64 *a1,
        unsigned __int8 *a2)
{
  __int64 v2; // r10
  __int64 v3; // r9
  __int64 v4; // rax
  __int64 v5; // r8
  unsigned __int8 v6; // r11
  __int64 v8[3]; // [rsp+20h] [rbp-18h] BYREF

  v2 = *a1;
  v3 = *a1;
  v4 = *(_QWORD *)(*a1 + 8);
  v5 = v4;
  if ( !*(_BYTE *)(v4 + 25) )
  {
    v6 = *a2;
    do
    {
      if ( *(_BYTE *)(v5 + 32) >= v6 )
      {
        if ( *(_BYTE *)(v3 + 25) && v6 < *(_BYTE *)(v5 + 32) )
          v3 = v5;
        v2 = v5;
      }
      else
      {
        v5 += 16;
      }
      v5 = *(_QWORD *)v5;
    }
    while ( !*(_BYTE *)(v5 + 25) );
  }
  if ( !*(_BYTE *)(v3 + 25) )
    v4 = *(_QWORD *)v3;
  while ( !*(_BYTE *)(v4 + 25) )
  {
    if ( *a2 >= *(_BYTE *)(v4 + 32) )
    {
      v4 = *(_QWORD *)(v4 + 16);
    }
    else
    {
      v3 = v4;
      v4 = *(_QWORD *)v4;
    }
  }
  v8[0] = v2;
  v8[1] = v3;
  return std::_Tree<std::_Tmap_traits<unsigned char,std::unique_ptr<KEY_MAP_RECORD_CACHE>,std::less<unsigned char>,std::allocator<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>,0>>::_Erase(
           a1,
           v8);
}

```

## disassembly

```asm
0x1800157a0  push    rbx
0x1800157a2  sub     rsp, 30h
0x1800157a6  mov     r10, [rcx]
0x1800157a9  mov     rbx, rcx
0x1800157ac  mov     r9, r10
0x1800157af  mov     rax, [r10+8]
0x1800157b3  mov     r8, rax
0x1800157b6  cmp     byte ptr [rax+19h], 0
0x1800157ba  jnz     short loc_1800157E7
0x1800157bc  mov     r11b, [rdx]
0x1800157bf  cmp     [r8+20h], r11b
0x1800157c3  jnb     short loc_1800157CB
0x1800157c5  add     r8, 10h
0x1800157c9  jmp     short loc_1800157DD
0x1800157cb  cmp     byte ptr [r9+19h], 0
0x1800157d0  jz      short loc_1800157DA
0x1800157d2  cmp     r11b, [r8+20h]
0x1800157d6  cmovb   r9, r8
0x1800157da  mov     r10, r8
0x1800157dd  mov     r8, [r8]
0x1800157e0  cmp     byte ptr [r8+19h], 0
0x1800157e5  jz      short loc_1800157BF
0x1800157e7  cmp     byte ptr [r9+19h], 0
0x1800157ec  jnz     short loc_1800157F1
0x1800157ee  mov     rax, [r9]
0x1800157f1  cmp     byte ptr [rax+19h], 0
0x1800157f5  jnz     short loc_180015810
0x1800157f7  mov     cl, [rdx]
0x1800157f9  cmp     cl, [rax+20h]
0x1800157fc  jnb     short loc_180015806
0x1800157fe  mov     r9, rax
0x180015801  mov     rax, [rax]
0x180015804  jmp     short loc_18001580A
0x180015806  mov     rax, [rax+10h]
0x18001580a  cmp     byte ptr [rax+19h], 0
0x18001580e  jz      short loc_1800157F9
0x180015810  lea     rdx, [rsp+38h+var_18]
0x180015815  mov     [rsp+38h+var_18], r10
0x18001581a  mov     rcx, rbx
0x18001581d  mov     [rsp+38h+var_10], r9
0x180015822  call    ?_Erase@?$_Tree@V?$_Tmap_traits@EV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@U?$less@E@2@V?$allocator@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@@2@$0A@@std@@@std@@AEAA_KU?$pair@PEAU?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@std@@PEAU12@@2@@Z; std::_Tree<std::_Tmap_traits<uchar,std::unique_ptr<KEY_MAP_RECORD_CACHE>,std::less<uchar>,std::allocator<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>,0>>::_Erase(std::pair<std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *> *,std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *> *>)
0x180015827  add     rsp, 30h
0x18001582b  pop     rbx
0x18001582c  retn
```
