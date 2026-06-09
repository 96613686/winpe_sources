# psaMakeOneDim(long)

- ea: `0x1800261b8`
- end: `0x1800261e7`
- name: `?psaMakeOneDim@@YAPEAUtagSAFEARRAY@@J@Z`
- size: `47`
- prototype: `struct tagSAFEARRAY *__fastcall(ULONG)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180017c30`
- `0x180025df0`
- `0x180073ea0`
- `0x180075400`
- `0x180075dd4`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800261d5`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800261d5`

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
0x1800261b8  sub     rsp, 28h
0x1800261bc  mov     [rsp+28h+rgsabound.cElements], ecx
0x1800261c0  lea     r8, [rsp+28h+rgsabound]; rgsabound
0x1800261c5  mov     ecx, 0Ch; vt
0x1800261ca  mov     [rsp+28h+rgsabound.lLbound], 0
0x1800261d2  lea     edx, [rcx-0Bh]; cDims
0x1800261d5  call    cs:__imp_SafeArrayCreate
0x1800261dc  nop     dword ptr [rax+rax+00h]
0x1800261e1  add     rsp, 28h
0x1800261e5  retn
```
