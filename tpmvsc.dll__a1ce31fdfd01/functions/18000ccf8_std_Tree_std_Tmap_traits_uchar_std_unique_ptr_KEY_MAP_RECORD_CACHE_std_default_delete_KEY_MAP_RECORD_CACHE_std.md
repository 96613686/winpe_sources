# std::_Tree<std::_Tmap_traits<uchar,std::unique_ptr<KEY_MAP_RECORD_CACHE,std::default_delete<KEY_MAP_RECORD_CACHE>>,std::less<uchar>,std::allocator<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE,std::default_delete<KEY_MAP_RECORD_CACHE>>>>,0>>::_Find_lower_bound<uchar>(uchar const &)

- ea: `0x18000ccf8`
- end: `0x18000cd42`
- name: `??$_Find_lower_bound@E@?$_Tree@V?$_Tmap_traits@EV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@U?$less@E@2@V?$allocator@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@std@@@1@AEBE@Z`
- size: `74`
- prototype: `_QWORD *__fastcall(__int64 *, _QWORD *, _BYTE *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d1b4`
- `0x18000f6a0`

## callees

- `0x18000ccf8`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<unsigned char,std::unique_ptr<KEY_MAP_RECORD_CACHE>,std::less<unsigned char>,std::allocator<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>,0>>::_Find_lower_bound<unsigned char>(
        __int64 *a1,
        _QWORD *a2,
        _BYTE *a3)
{
  __int64 v3; // rax
  __int64 *v4; // rcx
  int v5; // eax

  *a2 = *(_QWORD *)(*a1 + 8);
  a2[1] = 0;
  v3 = *a1;
  v4 = (__int64 *)*a2;
  a2[2] = v3;
  while ( !*((_BYTE *)v4 + 25) )
  {
    *a2 = v4;
    if ( *((_BYTE *)v4 + 32) >= *a3 )
    {
      a2[2] = v4;
      v5 = 1;
    }
    else
    {
      v4 += 2;
      v5 = 0;
    }
    *((_DWORD *)a2 + 2) = v5;
    v4 = (__int64 *)*v4;
  }
  return a2;
}

```

## disassembly

```asm
0x18000ccf8  mov     rax, [rcx]
0x18000ccfb  mov     r9, [rax+8]
0x18000ccff  mov     [rdx], r9
0x18000cd02  xor     r9d, r9d
0x18000cd05  mov     [rdx+8], r9
0x18000cd09  mov     rax, [rcx]
0x18000cd0c  mov     rcx, [rdx]
0x18000cd0f  mov     [rdx+10h], rax
0x18000cd13  jmp     short loc_18000CD38
0x18000cd15  mov     [rdx], rcx
0x18000cd18  mov     al, [r8]
0x18000cd1b  cmp     [rcx+20h], al
0x18000cd1e  jnb     short loc_18000CD29
0x18000cd20  add     rcx, 10h
0x18000cd24  mov     eax, r9d
0x18000cd27  jmp     short loc_18000CD32
0x18000cd29  mov     [rdx+10h], rcx
0x18000cd2d  mov     eax, 1
0x18000cd32  mov     [rdx+8], eax
0x18000cd35  mov     rcx, [rcx]
0x18000cd38  cmp     [rcx+19h], r9b
0x18000cd3c  jz      short loc_18000CD15
0x18000cd3e  mov     rax, rdx
0x18000cd41  retn
```
