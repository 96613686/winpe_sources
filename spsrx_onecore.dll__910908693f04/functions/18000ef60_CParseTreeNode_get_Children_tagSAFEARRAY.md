# CParseTreeNode::get_Children(tagSAFEARRAY * *)

- ea: `0x18000ef60`
- end: `0x18000ef92`
- name: `?get_Children@CParseTreeNode@@UEAAJPEAPEAUtagSAFEARRAY@@@Z`
- size: `50`
- prototype: `__int64 __fastcall(CParseTreeNode *__hidden this, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000ef60`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCopy` at `0x18000ef87`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18000ef87`

## pseudocode

```c
HRESULT __fastcall CParseTreeNode::get_Children(CParseTreeNode *this, struct tagSAFEARRAY **a2)
{
  if ( *((_BYTE *)this + 64) )
    return -2147418113;
  if ( a2 )
    return SafeArrayCopy(*((SAFEARRAY **)this + 12), a2);
  return -2147024809;
}

```

## disassembly

```asm
0x18000ef60  sub     rsp, 28h
0x18000ef64  cmp     byte ptr [rcx+40h], 0
0x18000ef68  jz      short loc_18000EF74
0x18000ef6a  mov     eax, 8000FFFFh
0x18000ef6f  add     rsp, 28h
0x18000ef73  retn
0x18000ef74  test    rdx, rdx
0x18000ef77  jnz     short loc_18000EF83
0x18000ef79  mov     eax, 80070057h
0x18000ef7e  add     rsp, 28h
0x18000ef82  retn
0x18000ef83  mov     rcx, [rcx+60h]; psa
0x18000ef87  call    cs:__imp_SafeArrayCopy
0x18000ef8d  add     rsp, 28h
0x18000ef91  retn
```
