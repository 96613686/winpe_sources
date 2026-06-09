# WriteComponentData

- ea: `0x180006504`
- end: `0x180006542`
- name: `WriteComponentData`
- size: `62`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004e10`
- `0x18000a650`

## callees

- `0x180006504`

## import_xrefs

- `msvcrt!longjmp` at `0x180006526`
- `msvcrt!longjmp` at `0x180006526`

## pseudocode

```c
__int64 __fastcall WriteComponentData(__int64 a1, __int16 a2)
{
  __int64 result; // rax

  if ( *(_WORD *)(a1 + 66) >= *(_WORD *)(a1 + 64) )
    longjmp((_JBTYPE *)(*(_QWORD *)(a1 + 136) + 48LL), 3362);
  result = *(_QWORD *)(a1 + 56);
  *(_WORD *)(result + 2LL * (__int16)(*(_WORD *)(a1 + 66))++) = a2;
  return result;
}

```

## disassembly

```asm
0x180006504  sub     rsp, 28h
0x180006508  movsx   rax, word ptr [rcx+42h]
0x18000650d  mov     r8, rcx
0x180006510  cmp     ax, [rcx+40h]
0x180006514  jl      short loc_18000652D
0x180006516  mov     rcx, [rcx+88h]
0x18000651d  mov     edx, 0D22h; Value
0x180006522  add     rcx, 30h ; '0'; Buf
0x180006526  call    cs:__imp_longjmp
0x18000652d  mov     rcx, rax
0x180006530  mov     rax, [r8+38h]
0x180006534  mov     [rax+rcx*2], dx
0x180006538  inc     word ptr [r8+42h]
0x18000653d  add     rsp, 28h
0x180006541  retn
```
