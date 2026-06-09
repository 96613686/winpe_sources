# psaMakeOneDim(long)

- ea: `0x180036c90`
- end: `0x180036cb8`
- name: `?psaMakeOneDim@@YAPEAUtagSAFEARRAY@@J@Z`
- size: `40`
- prototype: `struct tagSAFEARRAY *__fastcall(ULONG)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x18001d9f0`
- `0x18001f348`
- `0x180071970`
- `0x180072e40`
- `0x180073850`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x180036cad`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180036cad`

## pseudocode

```c
struct tagSAFEARRAY *__fastcall psaMakeOneDim(ULONG a1)
{
  SAFEARRAYBOUND rgsabound; // [rsp+38h] [rbp+10h] BYREF

  rgsabound.cElements = a1;
  rgsabound.lLbound = 0;
  return SafeArrayCreate(0xCu, 1u, &rgsabound);
}

```

## disassembly

```asm
0x180036c90  sub     rsp, 28h
0x180036c94  mov     [rsp+28h+rgsabound.cElements], ecx
0x180036c98  lea     r8, [rsp+28h+rgsabound]; rgsabound
0x180036c9d  mov     ecx, 0Ch; vt
0x180036ca2  mov     [rsp+28h+rgsabound.lLbound], 0
0x180036caa  lea     edx, [rcx-0Bh]; cDims
0x180036cad  call    cs:__imp_SafeArrayCreate
0x180036cb3  add     rsp, 28h
0x180036cb7  retn
```
