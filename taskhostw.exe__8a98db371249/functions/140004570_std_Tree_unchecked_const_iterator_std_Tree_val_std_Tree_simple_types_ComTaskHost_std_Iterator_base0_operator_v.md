# std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<ComTaskHost *>>,std::_Iterator_base0>::operator++(void)

- ea: `0x140004570`
- end: `0x1400045c1`
- name: `??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEAVComTaskHost@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ`
- size: `81`
- prototype: `__int64 *__fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400043a0`

## callees

- `0x140004570`
- `0x14000733c`

## pseudocode

```c
__int64 *__fastcall std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<ComTaskHost *>>,std::_Iterator_base0>::operator++(
        __int64 *a1)
{
  __int64 v1; // rdx
  __int64 *v2; // r8
  __int64 v3; // rcx
  __int64 i; // rax

  v1 = *a1;
  v2 = a1;
  if ( !*(_BYTE *)(*a1 + 25) )
  {
    v3 = *(_QWORD *)(v1 + 16);
    if ( *(_BYTE *)(v3 + 25) )
    {
      for ( i = *(_QWORD *)(v1 + 8); !*(_BYTE *)(i + 25); i = *(_QWORD *)(i + 8) )
      {
        if ( v1 != *(_QWORD *)(i + 16) )
          break;
        *v2 = i;
        v1 = i;
      }
    }
    else
    {
      i = std::_Tree_val<std::_Tree_simple_types<ComTaskHost *>>::_Min(v3, v1, v2);
    }
    *v2 = i;
  }
  return v2;
}

```

## disassembly

```asm
0x140004570  sub     rsp, 28h
0x140004574  mov     rdx, [rcx]
0x140004577  mov     r8, rcx
0x14000457a  cmp     byte ptr [rdx+19h], 0
0x14000457e  jnz     short loc_1400045B9
0x140004580  mov     rcx, [rdx+10h]
0x140004584  cmp     byte ptr [rcx+19h], 0
0x140004588  jnz     short loc_140004591
0x14000458a  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@PEAVComTaskHost@@@std@@@std@@SAPEAU?$_Tree_node@PEAVComTaskHost@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<ComTaskHost *>>::_Min(std::_Tree_node<ComTaskHost *,void *> *)
0x14000458f  jmp     short loc_1400045B6
0x140004591  mov     rax, [rdx+8]
0x140004595  cmp     byte ptr [rax+19h], 0
0x140004599  jnz     short loc_1400045B6
0x14000459b  nop     dword ptr [rax+rax+00h]
0x1400045a0  cmp     rdx, [rax+10h]
0x1400045a4  jnz     short loc_1400045B6
0x1400045a6  mov     [r8], rax
0x1400045a9  mov     rdx, rax
0x1400045ac  mov     rax, [rax+8]
0x1400045b0  cmp     byte ptr [rax+19h], 0
0x1400045b4  jz      short loc_1400045A0
0x1400045b6  mov     [r8], rax
0x1400045b9  mov     rax, r8
0x1400045bc  add     rsp, 28h
0x1400045c0  retn
```
