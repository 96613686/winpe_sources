# DeleteLinkCount(tagCL_INSTANCE_INFO *,tagLINK_COUNT *)

- ea: `0x180091030`
- end: `0x1800910a9`
- name: `?DeleteLinkCount@@YAXPEAUtagCL_INSTANCE_INFO@@PEAUtagLINK_COUNT@@@Z`
- size: `121`
- prototype: `void __fastcall(struct tagCL_INSTANCE_INFO *, struct tagLINK_COUNT *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18005e380`
- `0x180090768`

## callees

- `0x180091030`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180091093`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180091093`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x18009106f`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x180091079`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x18009106f`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x180091079`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180091065`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180091065`

## pseudocode

```c
void __fastcall DeleteLinkCount(struct tagCL_INSTANCE_INFO *a1, struct tagLINK_COUNT *a2)
{
  struct tagLINK_COUNT *v4; // rbx
  struct tagLINK_COUNT *v5; // rdi
  struct tagLINK_COUNT *v6; // rax

  if ( (*((_WORD *)a2 + 8))-- == 1 )
  {
    v4 = (struct tagLINK_COUNT *)*((_QWORD *)a1 + 14);
    v5 = 0;
    while ( v4 )
    {
      if ( v4 == a2 )
      {
        GlobalDeleteAtom(*((_WORD *)v4 + 5));
        DeleteAtom(*((_WORD *)v4 + 6));
        DeleteAtom(*((_WORD *)v4 + 4));
        v6 = *(struct tagLINK_COUNT **)v4;
        if ( v5 )
          *(_QWORD *)v5 = v6;
        else
          *((_QWORD *)a1 + 14) = v6;
        LocalFree(v4);
        return;
      }
      v5 = v4;
      v4 = *(struct tagLINK_COUNT **)v4;
    }
  }
}

```

## disassembly

```asm
0x180091030  mov     [rsp+arg_0], rbx
0x180091035  mov     [rsp+arg_10], rsi
0x18009103a  push    rdi
0x18009103b  sub     rsp, 20h
0x18009103f  sub     word ptr [rdx+10h], 1
0x180091044  mov     rsi, rcx
0x180091047  jnz     short loc_180091099
0x180091049  mov     rbx, [rcx+70h]
0x18009104d  xor     edi, edi
0x18009104f  test    rbx, rbx
0x180091052  jz      short loc_180091099
0x180091054  cmp     rbx, rdx
0x180091057  jz      short loc_180091061
0x180091059  mov     rdi, rbx
0x18009105c  mov     rbx, [rbx]
0x18009105f  jmp     short loc_18009104F
0x180091061  movzx   ecx, word ptr [rbx+0Ah]; nAtom
0x180091065  call    cs:__imp_GlobalDeleteAtom
0x18009106b  movzx   ecx, word ptr [rbx+0Ch]; nAtom
0x18009106f  call    cs:__imp_DeleteAtom
0x180091075  movzx   ecx, word ptr [rbx+8]; nAtom
0x180091079  call    cs:__imp_DeleteAtom
0x18009107f  mov     rax, [rbx]
0x180091082  test    rdi, rdi
0x180091085  jnz     short loc_18009108D
0x180091087  mov     [rsi+70h], rax
0x18009108b  jmp     short loc_180091090
0x18009108d  mov     [rdi], rax
0x180091090  mov     rcx, rbx; hMem
0x180091093  call    cs:__imp_LocalFree
0x180091099  mov     rbx, [rsp+28h+arg_0]
0x18009109e  mov     rsi, [rsp+28h+arg_10]
0x1800910a3  add     rsp, 20h
0x1800910a7  pop     rdi
0x1800910a8  retn
```
