# COleAuto::_SafeArrayCopy(tagSAFEARRAY *,tagSAFEARRAY * *)

- ea: `0x18002856c`
- end: `0x180028588`
- name: `?_SafeArrayCopy@COleAuto@@SAJPEAUtagSAFEARRAY@@PEAPEAU2@@Z`
- size: `28`
- prototype: `__int64 __fastcall(struct tagSAFEARRAY *, struct tagSAFEARRAY **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800061e0`

## callees

- `0x1800056c0`
- `0x18002856c`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCopy` at `0x180028570`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180028570`

## pseudocode

```c
HRESULT __fastcall COleAuto::_SafeArrayCopy(struct tagSAFEARRAY *a1, struct tagSAFEARRAY **a2)
{
  HRESULT result; // eax

  result = SafeArrayCopy(a1, a2);
  if ( result == -2147024882 )
    _ThrowMemoryException_();
  return result;
}

```

## disassembly

```asm
0x18002856c  sub     rsp, 28h
0x180028570  call    cs:__imp_SafeArrayCopy
0x180028576  cmp     eax, 8007000Eh
0x18002857b  jz      short loc_180028582
0x18002857d  add     rsp, 28h
0x180028581  retn
0x180028582  call    ?_ThrowMemoryException_@@YAXXZ; _ThrowMemoryException_(void)
```
