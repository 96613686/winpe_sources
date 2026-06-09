# _KeyList::Remove(ushort *)

- ea: `0x18000a05c`
- end: `0x18000a086`
- name: `?Remove@_KeyList@@QEAAJPEAG@Z`
- size: `42`
- prototype: `__int64 __fastcall(_KeyList *__hidden this, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005048`
- `0x18001a310`

## callees

- `0x18000a05c`

## import_xrefs

- `wbemcomn!?FindStr@CWStringArray@@QEAAHPEBGH@Z` at `0x18000a068`
- `wbemcomn!?FindStr@CWStringArray@@QEAAHPEBGH@Z` at `0x18000a068`
- `wbemcomn!?RemoveAt@CWStringArray@@QEAAHH@Z` at `0x18000a078`
- `wbemcomn!?RemoveAt@CWStringArray@@QEAAHH@Z` at `0x18000a078`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall _KeyList::Remove(_KeyList *this, unsigned __int16 *a2)
{
  int Str; // eax

  Str = CWStringArray::FindStr(this, a2, 0);
  if ( Str > -1 )
    CWStringArray::RemoveAt(this, Str);
  return 0;
}

```

## disassembly

```asm
0x18000a05c  push    rbx
0x18000a05e  sub     rsp, 20h
0x18000a062  xor     r8d, r8d
0x18000a065  mov     rbx, rcx
0x18000a068  call    cs:__imp_?FindStr@CWStringArray@@QEAAHPEBGH@Z; CWStringArray::FindStr(ushort const *,int)
0x18000a06e  cmp     eax, 0FFFFFFFFh
0x18000a071  jle     short loc_18000A07E
0x18000a073  mov     edx, eax
0x18000a075  mov     rcx, rbx
0x18000a078  call    cs:__imp_?RemoveAt@CWStringArray@@QEAAHH@Z; CWStringArray::RemoveAt(int)
0x18000a07e  xor     eax, eax
0x18000a080  add     rsp, 20h
0x18000a084  pop     rbx
0x18000a085  retn
```
