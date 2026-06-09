# RAII::CAutoDismDelete<_DismPackage *>::Release(void)

- ea: `0x1800036c0`
- end: `0x1800036e6`
- name: `?Release@?$CAutoDismDelete@PEAU_DismPackage@@@RAII@@UEAAXXZ`
- size: `38`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800036c0`

## import_xrefs

- `DismApi!DismDelete` at `0x1800036d2`
- `DismApi!DismDelete` at `0x1800036d2`

## pseudocode

```c
__int64 __fastcall RAII::CAutoDismDelete<_DismPackage *>::Release(__int64 a1)
{
  __int64 result; // rax

  if ( *(_QWORD *)(a1 + 8) )
  {
    result = DismDelete();
    *(_QWORD *)(a1 + 8) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800036c0  push    rbx
0x1800036c2  sub     rsp, 20h
0x1800036c6  mov     rbx, rcx
0x1800036c9  mov     rcx, [rcx+8]
0x1800036cd  test    rcx, rcx
0x1800036d0  jz      short loc_1800036E0
0x1800036d2  call    cs:__imp_DismDelete
0x1800036d8  mov     qword ptr [rbx+8], 0
0x1800036e0  add     rsp, 20h
0x1800036e4  pop     rbx
0x1800036e5  retn
```
