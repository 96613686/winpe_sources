# RemoveMatchingIrpFromQueue

- ea: `0x140012cc4`
- end: `0x140012d16`
- name: `RemoveMatchingIrpFromQueue`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14003a830`

## callees

- `0x140012cc4`

## import_xrefs

- `ntoskrnl!IoCsqRemoveIrp` at `0x140012d00`
- `ntoskrnl!IoCsqRemoveIrp` at `0x140012d00`

## pseudocode

```c
PIRP __fastcall RemoveMatchingIrpFromQueue(__int64 a1, __int64 a2)
{
  _QWORD *v2; // r9
  _QWORD *i; // r8
  __int64 v5; // rdx

  v2 = (_QWORD *)(a2 + 496);
  for ( i = *(_QWORD **)(a2 + 496); i != v2; i = (_QWORD *)*i )
  {
    v5 = *(i - 6);
    if ( *(_DWORD *)(v5 + 4) == *(unsigned __int8 *)(a1 + 1) && *(_DWORD *)(v5 + 8) == *(unsigned __int8 *)(a1 + 3) )
      return IoCsqRemoveIrp((PIO_CSQ)(a2 + 432), (PIO_CSQ_IRP_CONTEXT)(v5 + 48));
  }
  return 0;
}

```

## disassembly

```asm
0x140012cc4  sub     rsp, 28h
0x140012cc8  lea     r9, [rdx+1F0h]
0x140012ccf  mov     r10, rdx
0x140012cd2  mov     r8, [r9]
0x140012cd5  cmp     r8, r9
0x140012cd8  jz      short loc_140012D0E
0x140012cda  mov     rdx, [r8-30h]
0x140012cde  movzx   eax, byte ptr [rcx+1]
0x140012ce2  cmp     [rdx+4], eax
0x140012ce5  jnz     short loc_140012CF0
0x140012ce7  movzx   eax, byte ptr [rcx+3]
0x140012ceb  cmp     [rdx+8], eax
0x140012cee  jz      short loc_140012CF5
0x140012cf0  mov     r8, [r8]
0x140012cf3  jmp     short loc_140012CD5
0x140012cf5  add     rdx, 30h ; '0'; Context
0x140012cf9  lea     rcx, [r10+1B0h]; Csq
0x140012d00  call    cs:__imp_IoCsqRemoveIrp
0x140012d07  nop     dword ptr [rax+rax+00h]
0x140012d0c  jmp     short loc_140012D10
0x140012d0e  xor     eax, eax
0x140012d10  add     rsp, 28h
0x140012d14  retn
```
