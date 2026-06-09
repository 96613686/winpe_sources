# TmpRemoveEnlistmentResourceManager

- ea: `0x14001defc`
- end: `0x14001df56`
- name: `TmpRemoveEnlistmentResourceManager`
- size: `90`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000c9ac`
- `0x14000cccc`

## callees

- `0x14000c664`
- `0x14001defc`

## pseudocode

```c
__int64 __fastcall TmpRemoveEnlistmentResourceManager(__int64 a1)
{
  __int64 v2; // rcx
  _QWORD *v3; // rax
  __int64 result; // rax

  TmpNamespaceRemove((PRTL_AVL_TABLE)(*(_QWORD *)(a1 + 152) + 384LL), *(PVOID *)(a1 + 152), a1);
  v2 = *(_QWORD *)(a1 + 136);
  if ( *(_QWORD *)(v2 + 8) != a1 + 136 || (v3 = *(_QWORD **)(a1 + 144), *v3 != a1 + 136) )
    __fastfail(3u);
  *v3 = v2;
  *(_QWORD *)(v2 + 8) = v3;
  result = *(_QWORD *)(a1 + 152);
  --*(_DWORD *)(result + 288);
  return result;
}

```

## disassembly

```asm
0x14001defc  push    rbx
0x14001defe  sub     rsp, 20h
0x14001df02  mov     rdx, [rcx+98h]; Object
0x14001df09  mov     rbx, rcx
0x14001df0c  mov     r8, rbx
0x14001df0f  lea     rcx, [rdx+180h]; Table
0x14001df16  call    TmpNamespaceRemove
0x14001df1b  lea     rdx, [rbx+88h]
0x14001df22  mov     rcx, [rdx]
0x14001df25  cmp     [rcx+8], rdx
0x14001df29  jnz     short loc_14001DF4F
0x14001df2b  mov     rax, [rdx+8]
0x14001df2f  cmp     [rax], rdx
0x14001df32  jnz     short loc_14001DF4F
0x14001df34  mov     [rax], rcx
0x14001df37  mov     [rcx+8], rax
0x14001df3b  mov     rax, [rbx+98h]
0x14001df42  dec     dword ptr [rax+120h]
0x14001df48  add     rsp, 20h
0x14001df4c  pop     rbx
0x14001df4d  retn
0x14001df4f  mov     ecx, 3
0x14001df54  int     29h; Win8: RtlFailFast(ecx)
```
