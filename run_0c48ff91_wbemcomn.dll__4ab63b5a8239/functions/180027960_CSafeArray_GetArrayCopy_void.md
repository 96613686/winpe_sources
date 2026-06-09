# CSafeArray::GetArrayCopy(void)

- ea: `0x180027960`
- end: `0x18002799d`
- name: `?GetArrayCopy@CSafeArray@@QEAAPEAUtagSAFEARRAY@@XZ`
- size: `61`
- prototype: `struct tagSAFEARRAY *__fastcall(CSafeArray *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800056c0`
- `0x180027960`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCopy` at `0x180027976`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180027976`

## pseudocode

```c
struct tagSAFEARRAY *__fastcall CSafeArray::GetArrayCopy(CSafeArray *this)
{
  SAFEARRAY *v1; // rcx
  HRESULT v2; // edx
  struct tagSAFEARRAY *result; // rax
  SAFEARRAY *ppsaOut; // [rsp+30h] [rbp+8h] BYREF

  v1 = (SAFEARRAY *)*((_QWORD *)this + 4);
  ppsaOut = 0;
  v2 = SafeArrayCopy(v1, &ppsaOut);
  if ( v2 == -2147024882 )
    _ThrowMemoryException_();
  result = ppsaOut;
  if ( v2 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x180027960  sub     rsp, 28h
0x180027964  mov     rcx, [rcx+20h]; psa
0x180027968  lea     rdx, [rsp+28h+ppsaOut]; ppsaOut
0x18002796d  mov     [rsp+28h+ppsaOut], 0
0x180027976  call    cs:__imp_SafeArrayCopy
0x18002797c  mov     edx, eax
0x18002797e  cmp     eax, 8007000Eh
0x180027983  jz      short loc_180027997
0x180027985  mov     rax, [rsp+28h+ppsaOut]
0x18002798a  xor     ecx, ecx
0x18002798c  test    edx, edx
0x18002798e  cmovnz  rax, rcx
0x180027992  add     rsp, 28h
0x180027996  retn
0x180027997  call    ?_ThrowMemoryException_@@YAXXZ; _ThrowMemoryException_(void)
```
