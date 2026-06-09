# TdiPopulateTriageDumpData

- ea: `0x140005310`
- end: `0x14000535a`
- name: `TdiPopulateTriageDumpData`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140005310`

## import_xrefs

- `ntoskrnl!IoAddBugcheckTriageThread` at `0x140005347`
- `ntoskrnl!IoAddBugcheckTriageThread` at `0x140005347`
- `NETIO!NetioAddTriageDumpDataBlock` at `0x14000531f`
- `NETIO!NetioAddTriageDumpDataBlock` at `0x14000531f`

## pseudocode

```c
__int64 __fastcall TdiPopulateTriageDumpData(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = NetioAddTriageDumpDataBlock(a1, a2, 16);
  if ( (_BYTE)result && *(_DWORD *)a2 == -271729937 && *(_WORD *)(a2 + 4) == 1 )
  {
    if ( *(_QWORD *)(a2 + 8) )
      return IoAddBugcheckTriageThread();
  }
  return result;
}

```

## disassembly

```asm
0x140005310  push    rbx
0x140005312  sub     rsp, 20h
0x140005316  mov     r8d, 10h
0x14000531c  mov     rbx, rdx
0x14000531f  call    cs:__imp_NetioAddTriageDumpDataBlock
0x140005326  nop     dword ptr [rax+rax+00h]
0x14000532b  test    al, al
0x14000532d  jz      short loc_140005353
0x14000532f  cmp     dword ptr [rbx], 0EFCDBAEFh
0x140005335  jnz     short loc_140005353
0x140005337  cmp     word ptr [rbx+4], 1
0x14000533c  jnz     short loc_140005353
0x14000533e  mov     rcx, [rbx+8]
0x140005342  test    rcx, rcx
0x140005345  jz      short loc_140005353
0x140005347  call    cs:__imp_IoAddBugcheckTriageThread
0x14000534e  nop     dword ptr [rax+rax+00h]
0x140005353  add     rsp, 20h
0x140005357  pop     rbx
0x140005358  retn
```
