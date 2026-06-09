# UdfMarkDeletedInScbTable

- ea: `0x140016e98`
- end: `0x140016f60`
- name: `UdfMarkDeletedInScbTable`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400175d0`

## callees

- `0x140016e98`

## import_xrefs

- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140016ee6`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140016ee6`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140016f48`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140016f48`

## pseudocode

```c
PVOID __fastcall UdfMarkDeletedInScbTable(__int64 a1, __int64 a2)
{
  PVOID result; // rax
  __int64 v5; // rax
  signed __int32 v6; // eax
  __int64 v7; // rax
  __int64 Buffer; // [rsp+20h] [rbp-18h] BYREF
  __int64 v9; // [rsp+28h] [rbp-10h]
  unsigned __int8 NewElement; // [rsp+48h] [rbp+10h] BYREF

  result = (PVOID)*(unsigned int *)(a2 + 212);
  v9 = 0;
  if ( ((unsigned __int8)result & 0x40) != 0 )
  {
    Buffer = *(_QWORD *)(a2 + 192);
    v5 = *(_QWORD *)(a2 + 136);
    NewElement = 0;
    RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(*(_QWORD *)(v5 + 8) + 1736LL), &Buffer);
    v6 = _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)(a1 + 16) + 1840LL), 1u);
    *(_DWORD *)(a2 + 196) = 0x40000000;
    *(_DWORD *)(a2 + 192) = v6 + 1;
    Buffer = *(_QWORD *)(a2 + 192);
    v7 = *(_QWORD *)(a2 + 136);
    v9 = a2;
    return RtlInsertElementGenericTableAvl((PRTL_AVL_TABLE)(*(_QWORD *)(v7 + 8) + 1736LL), &Buffer, 0x10u, &NewElement);
  }
  return result;
}

```

## disassembly

```asm
0x140016e98  mov     r11, rsp
0x140016e9b  mov     [r11+8], rbx
0x140016e9f  push    rdi
0x140016ea0  sub     rsp, 30h
0x140016ea4  mov     eax, [rdx+0D4h]
0x140016eaa  mov     rbx, rdx
0x140016ead  mov     qword ptr [r11-10h], 0
0x140016eb5  mov     rdi, rcx
0x140016eb8  test    al, 40h
0x140016eba  jz      loc_140016F54
0x140016ec0  mov     rax, [rdx+0C0h]
0x140016ec7  mov     [r11-18h], rax
0x140016ecb  mov     rax, [rdx+88h]
0x140016ed2  lea     rdx, [r11-18h]; Buffer
0x140016ed6  mov     [rsp+38h+NewElement], 0
0x140016edb  mov     rcx, [rax+8]
0x140016edf  add     rcx, 6C8h; Table
0x140016ee6  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x140016eed  nop     dword ptr [rax+rax+00h]
0x140016ef2  mov     rcx, [rdi+10h]
0x140016ef6  mov     eax, 1
0x140016efb  lock xadd [rcx+730h], eax
0x140016f03  inc     eax
0x140016f05  mov     dword ptr [rbx+0C4h], 40000000h
0x140016f0f  mov     [rbx+0C0h], eax
0x140016f15  lea     r9, [rsp+38h+NewElement]; NewElement
0x140016f1a  mov     rax, [rbx+0C0h]
0x140016f21  lea     rdx, [rsp+38h+Buffer]; Buffer
0x140016f26  mov     [rsp+38h+Buffer], rax
0x140016f2b  mov     r8d, 10h; BufferSize
0x140016f31  mov     rax, [rbx+88h]
0x140016f38  mov     [rsp+38h+var_10], rbx
0x140016f3d  mov     rcx, [rax+8]
0x140016f41  add     rcx, 6C8h; Table
0x140016f48  call    cs:__imp_RtlInsertElementGenericTableAvl
0x140016f4f  nop     dword ptr [rax+rax+00h]
0x140016f54  mov     rbx, [rsp+38h+arg_0]
0x140016f59  add     rsp, 30h
0x140016f5d  pop     rdi
0x140016f5e  retn
```
