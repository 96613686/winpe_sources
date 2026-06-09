# VmQueryDynamicExtension(void *,void *)

- ea: `0x140016640`
- end: `0x140016675`
- name: `?VmQueryDynamicExtension@@YAPEAXPEAX0@Z`
- size: `53`
- prototype: `void *__fastcall(void *, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140016640`

## pseudocode

```c
_QWORD *__fastcall VmQueryDynamicExtension(_QWORD *a1, void *a2)
{
  _QWORD *i; // rax

  for ( i = (_QWORD *)a1[26]; ; i = (_QWORD *)*i )
  {
    if ( i == a1 + 26 )
      return 0;
    if ( *((_BYTE *)i + 394) && (void *)i[50] == a2 )
      break;
  }
  return i - 4;
}

```

## disassembly

```asm
0x140016640  lea     r8, [rcx+0D0h]
0x140016647  mov     rax, [r8]
0x14001664a  nop     word ptr [rax+rax+00h]
0x140016650  cmp     rax, r8
0x140016653  jz      short loc_140016663
0x140016655  cmp     byte ptr [rax+18Ah], 0
0x14001665c  jnz     short loc_140016667
0x14001665e  mov     rax, [rax]
0x140016661  jmp     short loc_140016650
0x140016663  xor     eax, eax
0x140016665  retn
0x140016667  cmp     [rax+190h], rdx
0x14001666e  jnz     short loc_14001665E
0x140016670  add     rax, 0FFFFFFFFFFFFFFE0h
0x140016674  retn
```
