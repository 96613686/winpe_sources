# UdfTearDownRmwSupport

- ea: `0x14002c250`
- end: `0x14002c2f1`
- name: `UdfTearDownRmwSupport`
- size: `161`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140003148`
- `0x14002c008`
- `0x140049f80`

## callees

- `0x140004340`
- `0x14002c250`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x14002c272`
- `ntoskrnl!ExDeleteResourceLite` at `0x14002c272`
- `ntoskrnl!IoFreeIrp` at `0x14002c287`
- `ntoskrnl!IoFreeIrp` at `0x14002c287`

## pseudocode

```c
__int64 __fastcall UdfTearDownRmwSupport(__int64 a1, __int64 a2)
{
  __int64 v3; // rdi
  IRP *v4; // rcx
  __int64 i; // rbp
  __int64 result; // rax

  if ( (*(_DWORD *)(a2 + 48) & 0x2000) != 0 )
  {
    v3 = *(_QWORD *)(a2 + 104);
    ExDeleteResourceLite((PERESOURCE)(v3 + 128));
    v4 = *(IRP **)(v3 + 16);
    if ( v4 )
      IoFreeIrp(v4);
    UdfFreePool(v3 + 24);
    if ( *(_QWORD *)(v3 + 32) )
    {
      for ( i = 0; (unsigned int)i < *(_DWORD *)(v3 + 8); i = (unsigned int)(i + 1) )
        UdfFreePool(*(_QWORD *)(v3 + 32) + 8 * (i + 8 * i + 2));
      UdfFreePool(v3 + 32);
    }
    result = UdfFreePool(a2 + 104);
    *(_DWORD *)(a2 + 48) &= ~0x2000u;
  }
  return result;
}

```

## disassembly

```asm
0x14002c250  push    rbx
0x14002c252  push    rbp
0x14002c253  push    rsi
0x14002c254  push    rdi
0x14002c255  push    r14
0x14002c257  sub     rsp, 20h
0x14002c25b  test    dword ptr [rdx+30h], 2000h
0x14002c262  mov     rbx, rdx
0x14002c265  jz      short loc_14002C2E5
0x14002c267  mov     rdi, [rdx+68h]
0x14002c26b  lea     rcx, [rdi+80h]; Resource
0x14002c272  call    cs:__imp_ExDeleteResourceLite
0x14002c279  nop     dword ptr [rax+rax+00h]
0x14002c27e  mov     rcx, [rdi+10h]; Irp
0x14002c282  test    rcx, rcx
0x14002c285  jz      short loc_14002C293
0x14002c287  call    cs:__imp_IoFreeIrp
0x14002c28e  nop     dword ptr [rax+rax+00h]
0x14002c293  lea     rcx, [rdi+18h]
0x14002c297  call    UdfFreePool
0x14002c29c  lea     rsi, [rdi+20h]
0x14002c2a0  cmp     qword ptr [rsi], 0
0x14002c2a4  jz      short loc_14002C2D7
0x14002c2a6  xor     ebp, ebp
0x14002c2a8  cmp     [rdi+8], ebp
0x14002c2ab  jbe     short loc_14002C2CF
0x14002c2ad  mov     rax, [rsi]
0x14002c2b0  lea     rdx, ds:0[rbp*8]
0x14002c2b8  add     rdx, 2
0x14002c2bc  add     rdx, rbp
0x14002c2bf  lea     rcx, [rax+rdx*8]
0x14002c2c3  call    UdfFreePool
0x14002c2c8  inc     ebp
0x14002c2ca  cmp     ebp, [rdi+8]
0x14002c2cd  jb      short loc_14002C2AD
0x14002c2cf  mov     rcx, rsi
0x14002c2d2  call    UdfFreePool
0x14002c2d7  lea     rcx, [rbx+68h]
0x14002c2db  call    UdfFreePool
0x14002c2e0  btr     dword ptr [rbx+30h], 0Dh
0x14002c2e5  add     rsp, 20h
0x14002c2e9  pop     r14
0x14002c2eb  pop     rdi
0x14002c2ec  pop     rsi
0x14002c2ed  pop     rbp
0x14002c2ee  pop     rbx
0x14002c2ef  retn
```
