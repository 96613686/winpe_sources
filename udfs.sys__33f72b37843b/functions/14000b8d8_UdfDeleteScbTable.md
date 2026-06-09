# UdfDeleteScbTable

- ea: `0x14000b8d8`
- end: `0x14000b931`
- name: `UdfDeleteScbTable`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400537b0`

## callees

- `0x14000b8d8`

## import_xrefs

- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14000b917`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14000b917`

## pseudocode

```c
char __fastcall UdfDeleteScbTable(__int64 a1, __int64 a2)
{
  int v2; // eax
  _QWORD Buffer[3]; // [rsp+20h] [rbp-18h] BYREF

  v2 = *(_DWORD *)(a2 + 212);
  Buffer[1] = 0;
  if ( (v2 & 0x40) != 0 )
  {
    Buffer[0] = *(_QWORD *)(a2 + 192);
    LOBYTE(v2) = RtlDeleteElementGenericTableAvl(
                   (PRTL_AVL_TABLE)(*(_QWORD *)(*(_QWORD *)(a2 + 136) + 8LL) + 1736LL),
                   Buffer);
    *(_DWORD *)(a2 + 212) &= ~0x40u;
  }
  return v2;
}

```

## disassembly

```asm
0x14000b8d8  push    rbx
0x14000b8da  sub     rsp, 30h
0x14000b8de  mov     eax, [rdx+0D4h]
0x14000b8e4  mov     rbx, rdx
0x14000b8e7  mov     [rsp+38h+var_10], 0
0x14000b8f0  test    al, 40h
0x14000b8f2  jz      short loc_14000B92A
0x14000b8f4  mov     rax, [rdx+0C0h]
0x14000b8fb  mov     [rsp+38h+Buffer], rax
0x14000b900  mov     rax, [rdx+88h]
0x14000b907  lea     rdx, [rsp+38h+Buffer]; Buffer
0x14000b90c  mov     rcx, [rax+8]
0x14000b910  add     rcx, 6C8h; Table
0x14000b917  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x14000b91e  nop     dword ptr [rax+rax+00h]
0x14000b923  and     dword ptr [rbx+0D4h], 0FFFFFFBFh
0x14000b92a  add     rsp, 30h
0x14000b92e  pop     rbx
0x14000b92f  retn
```
