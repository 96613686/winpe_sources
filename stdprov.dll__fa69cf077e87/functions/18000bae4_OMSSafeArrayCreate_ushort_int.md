# OMSSafeArrayCreate(ushort,int)

- ea: `0x18000bae4`
- end: `0x18000bb27`
- name: `?OMSSafeArrayCreate@@YAPEAUtagSAFEARRAY@@GH@Z`
- size: `67`
- prototype: `struct tagSAFEARRAY *__fastcall(__int16)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800094b0`
- `0x18000d6a4`

## callees

- `0x1800096f0`
- `0x18000bae4`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x18000bb18`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18000bb18`

## pseudocode

```c
struct tagSAFEARRAY *__fastcall OMSSafeArrayCreate(__int16 a1)
{
  signed int v1; // r8d
  VARTYPE v2; // r9
  SAFEARRAYBOUND rgsabound; // [rsp+40h] [rbp+18h] BYREF

  if ( (int)iTypeSize(a1) < 1 || v1 < 1 )
    return 0;
  rgsabound.cElements = v1;
  rgsabound.lLbound = 0;
  return SafeArrayCreate(v2, 1u, &rgsabound);
}

```

## disassembly

```asm
0x18000bae4  sub     rsp, 28h
0x18000bae8  mov     r8d, edx
0x18000baeb  movzx   r9d, cx
0x18000baef  call    ?iTypeSize@@YAHG@Z; iTypeSize(ushort)
0x18000baf4  mov     edx, 1; cDims
0x18000baf9  cmp     eax, edx
0x18000bafb  jl      short loc_18000BB20
0x18000bafd  cmp     r8d, edx
0x18000bb00  jl      short loc_18000BB20
0x18000bb02  mov     [rsp+28h+rgsabound.cElements], r8d
0x18000bb07  movzx   ecx, r9w; vt
0x18000bb0b  lea     r8, [rsp+28h+rgsabound]; rgsabound
0x18000bb10  mov     [rsp+28h+rgsabound.lLbound], 0
0x18000bb18  call    cs:__imp_SafeArrayCreate
0x18000bb1e  jmp     short loc_18000BB22
0x18000bb20  xor     eax, eax
0x18000bb22  add     rsp, 28h
0x18000bb26  retn
```
