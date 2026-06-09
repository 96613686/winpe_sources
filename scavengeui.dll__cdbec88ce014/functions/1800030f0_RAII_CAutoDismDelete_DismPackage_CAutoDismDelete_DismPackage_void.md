# RAII::CAutoDismDelete<_DismPackage *>::~CAutoDismDelete<_DismPackage *>(void)

- ea: `0x1800030f0`
- end: `0x180003120`
- name: `??1?$CAutoDismDelete@PEAU_DismPackage@@@RAII@@UEAA@XZ`
- size: `48`
- prototype: `void **__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003fa9`

## callees

- `0x1800030f0`

## import_xrefs

- `DismApi!DismDelete` at `0x18000310c`
- `DismApi!DismDelete` at `0x18000310c`

## pseudocode

```c
void **__fastcall RAII::CAutoDismDelete<_DismPackage *>::~CAutoDismDelete<_DismPackage *>(_QWORD *a1)
{
  void **result; // rax

  result = &RAII::CAutoDismDelete<_DismPackage *>::`vftable';
  *a1 = &RAII::CAutoDismDelete<_DismPackage *>::`vftable';
  if ( a1[1] )
  {
    result = (void **)DismDelete();
    a1[1] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800030f0  push    rbx
0x1800030f2  sub     rsp, 20h
0x1800030f6  lea     rax, ??_7?$CAutoDismDelete@PEAU_DismPackage@@@RAII@@6B@; const RAII::CAutoDismDelete<_DismPackage *>::`vftable'
0x1800030fd  mov     rbx, rcx
0x180003100  mov     [rcx], rax
0x180003103  mov     rcx, [rcx+8]
0x180003107  test    rcx, rcx
0x18000310a  jz      short loc_18000311A
0x18000310c  call    cs:__imp_DismDelete
0x180003112  mov     qword ptr [rbx+8], 0
0x18000311a  add     rsp, 20h
0x18000311e  pop     rbx
0x18000311f  retn
```
