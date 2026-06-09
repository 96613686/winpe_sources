# CSxRefMap<CGroupMap,CGroupEntry>::DeleteAll(void)

- ea: `0x180007a24`
- end: `0x180007a6c`
- name: `?DeleteAll@?$CSxRefMap@VCGroupMap@@VCGroupEntry@@@@QEAAXXZ`
- size: `72`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800027f8`
- `0x1800071f0`
- `0x18000a02c`

## callees

- `0x180007a24`
- `0x18000e184`

## import_xrefs

- `ntdll!RtlEnumerateGenericTableAvl` at `0x180007a56`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180007a56`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180007a43`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180007a43`

## pseudocode

```c
CGroupEntry **__fastcall CSxRefMap<CGroupMap,CGroupEntry>::DeleteAll(__int64 a1)
{
  struct _RTL_AVL_TABLE *i; // rcx
  CGroupEntry *v3; // rbx
  CGroupEntry **result; // rax

  _InterlockedIncrement((volatile signed __int32 *)(a1 + 8));
  for ( i = *(struct _RTL_AVL_TABLE **)a1; ; i = *(struct _RTL_AVL_TABLE **)a1 )
  {
    result = (CGroupEntry **)RtlEnumerateGenericTableAvl(i, 1u);
    if ( !result )
      break;
    v3 = *result;
    RtlDeleteElementGenericTableAvl(*(PRTL_AVL_TABLE *)a1, result);
    CGroupEntry::Release(v3);
  }
  return result;
}

```

## disassembly

```asm
0x180007a24  mov     [rsp+arg_0], rbx
0x180007a29  push    rdi
0x180007a2a  sub     rsp, 20h
0x180007a2e  mov     rdi, rcx
0x180007a31  lock inc dword ptr [rcx+8]
0x180007a35  mov     rcx, [rcx]
0x180007a38  jmp     short loc_180007A54
0x180007a3a  mov     rcx, [rdi]; Table
0x180007a3d  mov     rdx, rax; Buffer
0x180007a40  mov     rbx, [rax]
0x180007a43  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180007a49  mov     rcx, rbx; this
0x180007a4c  call    ?Release@CGroupEntry@@QEAAKXZ; CGroupEntry::Release(void)
0x180007a51  mov     rcx, [rdi]; Table
0x180007a54  mov     dl, 1; Restart
0x180007a56  call    cs:__imp_RtlEnumerateGenericTableAvl
0x180007a5c  test    rax, rax
0x180007a5f  jnz     short loc_180007A3A
0x180007a61  mov     rbx, [rsp+28h+arg_0]
0x180007a66  add     rsp, 20h
0x180007a6a  pop     rdi
0x180007a6b  retn
```
