# DavCloseContext

- ea: `0x1800283fc`
- end: `0x180028439`
- name: `DavCloseContext`
- size: `61`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800049bc`
- `0x18001507c`
- `0x18001a5a0`
- `0x18001ad0c`
- `0x18001dcb4`
- `0x1800206bc`
- `0x1800229b0`

## callees

- `0x1800283fc`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002842d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002842d`

## pseudocode

```c
void __fastcall DavCloseContext(__int64 a1, __int64 a2)
{
  if ( a2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 16LL))(a2);
  if ( a1 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
    CoUninitialize();
  }
}

```

## disassembly

```asm
0x1800283fc  push    rbx
0x1800283fe  sub     rsp, 20h
0x180028402  mov     rbx, rcx
0x180028405  test    rdx, rdx
0x180028408  jz      short loc_180028419
0x18002840a  mov     rax, [rdx]
0x18002840d  mov     rcx, rdx
0x180028410  mov     rax, [rax+10h]
0x180028414  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028419  test    rbx, rbx
0x18002841c  jz      short loc_180028433
0x18002841e  mov     rax, [rbx]
0x180028421  mov     rcx, rbx
0x180028424  mov     rax, [rax+10h]
0x180028428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002842d  call    cs:__imp_CoUninitialize
0x180028433  add     rsp, 20h
0x180028437  pop     rbx
0x180028438  retn
```
