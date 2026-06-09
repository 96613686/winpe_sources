# ATL::CAtlPlex::Create(ATL::CAtlPlex * &,unsigned __int64,unsigned __int64)

- ea: `0x18000dad8`
- end: `0x18000db2b`
- name: `?Create@CAtlPlex@ATL@@SAPEAU12@AEAPEAU12@_K1@Z`
- size: `83`
- prototype: `struct ATL::CAtlPlex *__fastcall(struct ATL::CAtlPlex **, unsigned __int64, unsigned __int64)`
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x180010450`
- `0x180010500`
- `0x180012d70`
- `0x180025f7c`
- `0x180027e28`
- `0x1800290e0`
- `0x1800291dc`
- `0x1800292e0`
- `0x18002b430`
- `0x18002b4e0`
- `0x18002d348`

## callees

- `0x180002760`
- `0x18000dad8`

## import_xrefs

- `msvcrt!malloc` at `0x18000db0d`
- `msvcrt!malloc` at `0x18000db0d`

## pseudocode

```c
struct ATL::CAtlPlex *__fastcall ATL::CAtlPlex::Create(struct ATL::CAtlPlex **a1)
{
  struct ATL::CAtlPlex *result; // rax
  __int64 v3; // [rsp+48h] [rbp+20h] BYREF

  v3 = 0;
  if ( (int)ATL::AtlMultiply<unsigned __int64>(&v3) < 0 )
    return 0;
  if ( (unsigned __int64)~v3 < 8 )
    return 0;
  result = (struct ATL::CAtlPlex *)malloc(v3 + 8);
  if ( !result )
    return 0;
  *(_QWORD *)result = *a1;
  *a1 = result;
  return result;
}

```

## disassembly

```asm
0x18000dad8  push    rbx
0x18000dada  sub     rsp, 20h
0x18000dade  mov     rbx, rcx
0x18000dae1  mov     [rsp+28h+arg_18], 0
0x18000daea  lea     rcx, [rsp+28h+arg_18]
0x18000daef  call    ??$AtlMultiply@_K@ATL@@YAJPEA_K_K1@Z; ATL::AtlMultiply<unsigned __int64>(unsigned __int64 *,unsigned __int64,unsigned __int64)
0x18000daf4  test    eax, eax
0x18000daf6  js      short loc_18000DB23
0x18000daf8  mov     rcx, [rsp+28h+arg_18]
0x18000dafd  mov     rax, rcx
0x18000db00  not     rax
0x18000db03  cmp     rax, 8
0x18000db07  jb      short loc_18000DB23
0x18000db09  add     rcx, 8; Size
0x18000db0d  call    cs:__imp_malloc
0x18000db13  test    rax, rax
0x18000db16  jz      short loc_18000DB23
0x18000db18  mov     rcx, [rbx]
0x18000db1b  mov     [rax], rcx
0x18000db1e  mov     [rbx], rax
0x18000db21  jmp     short loc_18000DB25
0x18000db23  xor     eax, eax
0x18000db25  add     rsp, 20h
0x18000db29  pop     rbx
0x18000db2a  retn
```
