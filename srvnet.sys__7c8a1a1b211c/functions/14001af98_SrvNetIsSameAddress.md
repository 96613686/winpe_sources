# SrvNetIsSameAddress

- ea: `0x14001af98`
- end: `0x14001afea`
- name: `SrvNetIsSameAddress`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140046c1c`

## callees

- `0x14001af98`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14001afcd`
- `ntoskrnl!RtlCompareMemory` at `0x14001afcd`

## pseudocode

```c
bool __fastcall SrvNetIsSameAddress(_WORD *a1, _WORD *a2)
{
  __int64 v2; // rax
  __int64 v3; // rbx

  if ( *a1 != *a2 )
    return 0;
  v2 = 2;
  v3 = 4;
  if ( *a1 != 2 )
  {
    v3 = 16;
    v2 = 4;
  }
  return RtlCompareMemory(&a1[v2], &a2[v2], (unsigned int)v3) == v3;
}

```

## disassembly

```asm
0x14001af98  push    rbx
0x14001af9a  sub     rsp, 20h
0x14001af9e  movzx   r8d, word ptr [rcx]
0x14001afa2  cmp     r8w, [rdx]
0x14001afa6  jnz     short loc_14001AFE1
0x14001afa8  mov     eax, 4
0x14001afad  cmp     r8w, 2
0x14001afb2  mov     ebx, eax
0x14001afb4  lea     r9d, [rax+0Ch]
0x14001afb8  cmovnz  ebx, r9d
0x14001afbc  lea     r9d, [rax+4]
0x14001afc0  cmovnz  eax, r9d
0x14001afc4  mov     r8d, ebx; Length
0x14001afc7  add     rdx, rax; Source2
0x14001afca  add     rcx, rax; Source1
0x14001afcd  call    cs:__imp_RtlCompareMemory
0x14001afd4  nop     dword ptr [rax+rax+00h]
0x14001afd9  cmp     rax, rbx
0x14001afdc  setz    al
0x14001afdf  jmp     short loc_14001AFE3
0x14001afe1  xor     al, al
0x14001afe3  add     rsp, 20h
0x14001afe7  pop     rbx
0x14001afe8  retn
```
