# WcClearUnionTable

- ea: `0x14001d56c`
- end: `0x14001d5a8`
- name: `WcClearUnionTable`
- size: `60`
- prototype: `PVOID __fastcall(PRTL_AVL_TABLE Table)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14001d360`
- `0x1400300b0`

## callees

- `0x14001d56c`

## import_xrefs

- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14001d57f`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14001d57f`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14001d590`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14001d590`

## pseudocode

```c
PVOID __fastcall WcClearUnionTable(PRTL_AVL_TABLE Table)
{
  struct _RTL_AVL_TABLE *v1; // rbx
  BOOLEAN i; // dl
  PVOID result; // rax

  v1 = Table;
  for ( i = 1; ; i = 0 )
  {
    result = RtlEnumerateGenericTableAvl(Table, i);
    if ( !result )
      break;
    RtlDeleteElementGenericTableAvl(v1, result);
    Table = v1;
  }
  return result;
}

```

## disassembly

```asm
0x14001d56c  push    rbx
0x14001d56e  sub     rsp, 20h
0x14001d572  mov     rbx, rcx
0x14001d575  mov     dl, 1
0x14001d577  jmp     short loc_14001D590
0x14001d579  mov     rdx, rax; Buffer
0x14001d57c  mov     rcx, rbx; Table
0x14001d57f  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x14001d586  nop     dword ptr [rax+rax+00h]
0x14001d58b  xor     edx, edx; Restart
0x14001d58d  mov     rcx, rbx; Table
0x14001d590  call    cs:__imp_RtlEnumerateGenericTableAvl
0x14001d597  nop     dword ptr [rax+rax+00h]
0x14001d59c  test    rax, rax
0x14001d59f  jnz     short loc_14001D579
0x14001d5a1  add     rsp, 20h
0x14001d5a5  pop     rbx
0x14001d5a6  retn
```
