# std::_Tree_val<std::_Tree_simple_types<ComTaskHost *>>::_Min(std::_Tree_node<ComTaskHost *,void *> *)

- ea: `0x14000733c`
- end: `0x140007358`
- name: `?_Min@?$_Tree_val@U?$_Tree_simple_types@PEAVComTaskHost@@@std@@@std@@SAPEAU?$_Tree_node@PEAVComTaskHost@@PEAX@2@PEAU32@@Z`
- size: `28`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400042d4`
- `0x140004570`
- `0x1400045d0`

## callees

- `0x14000733c`

## pseudocode

```c
_QWORD *__fastcall std::_Tree_val<std::_Tree_simple_types<ComTaskHost *>>::_Min(_QWORD *a1)
{
  __int64 *v1; // rdx

  v1 = (__int64 *)*a1;
  if ( !*(_BYTE *)(*a1 + 25LL) )
  {
    do
    {
      a1 = v1;
      v1 = (__int64 *)*v1;
    }
    while ( !*((_BYTE *)v1 + 25) );
  }
  return a1;
}

```

## disassembly

```asm
0x14000733c  mov     rdx, [rcx]
0x14000733f  cmp     byte ptr [rdx+19h], 0
0x140007343  jnz     short loc_140007354
0x140007345  mov     rax, [rdx]
0x140007348  mov     rcx, rdx
0x14000734b  mov     rdx, rax
0x14000734e  cmp     byte ptr [rax+19h], 0
0x140007352  jz      short loc_140007345
0x140007354  mov     rax, rcx
0x140007357  retn
```
