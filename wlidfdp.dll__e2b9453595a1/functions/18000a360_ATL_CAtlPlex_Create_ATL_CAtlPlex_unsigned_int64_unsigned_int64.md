# ATL::CAtlPlex::Create(ATL::CAtlPlex * &,unsigned __int64,unsigned __int64)

- ea: `0x18000a360`
- end: `0x18000a3b3`
- name: `?Create@CAtlPlex@ATL@@SAPEAU12@AEAPEAU12@_K1@Z`
- size: `83`
- prototype: `struct ATL::CAtlPlex *__fastcall(struct ATL::CAtlPlex **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ac5c`
- `0x18000ad0c`

## callees

- `0x180009bac`
- `0x18000a360`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000a395`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000a395`

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
0x18000a360  push    rbx
0x18000a362  sub     rsp, 20h
0x18000a366  mov     rbx, rcx
0x18000a369  mov     [rsp+28h+arg_18], 0
0x18000a372  lea     rcx, [rsp+28h+arg_18]
0x18000a377  call    ??$AtlMultiply@_K@ATL@@YAJPEA_K_K1@Z; ATL::AtlMultiply<unsigned __int64>(unsigned __int64 *,unsigned __int64,unsigned __int64)
0x18000a37c  test    eax, eax
0x18000a37e  js      short loc_18000A3AB
0x18000a380  mov     rcx, [rsp+28h+arg_18]
0x18000a385  mov     rax, rcx
0x18000a388  not     rax
0x18000a38b  cmp     rax, 8
0x18000a38f  jb      short loc_18000A3AB
0x18000a391  add     rcx, 8; Size
0x18000a395  call    cs:__imp_malloc
0x18000a39b  test    rax, rax
0x18000a39e  jz      short loc_18000A3AB
0x18000a3a0  mov     rcx, [rbx]
0x18000a3a3  mov     [rax], rcx
0x18000a3a6  mov     [rbx], rax
0x18000a3a9  jmp     short loc_18000A3AD
0x18000a3ab  xor     eax, eax
0x18000a3ad  add     rsp, 20h
0x18000a3b1  pop     rbx
0x18000a3b2  retn
```
