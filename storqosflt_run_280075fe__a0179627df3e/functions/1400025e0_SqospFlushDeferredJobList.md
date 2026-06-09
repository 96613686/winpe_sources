# SqospFlushDeferredJobList

- ea: `0x1400025e0`
- end: `0x140002616`
- name: `SqospFlushDeferredJobList`
- size: `54`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140001010`
- `0x1400011c0`
- `0x140002300`
- `0x140002550`

## callees

- `0x1400025e0`

## import_xrefs

- `ntoskrnl!ExpInterlockedFlushSList` at `0x1400025e4`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x1400025e4`

## pseudocode

```c
_QWORD *__fastcall SqospFlushDeferredJobList(union _SLIST_HEADER *a1)
{
  PSLIST_ENTRY v1; // r8
  _QWORD *result; // rax
  _QWORD *p_Next; // rdx

  v1 = ExpInterlockedFlushSList(a1);
  for ( result = 0; v1; result = p_Next )
  {
    p_Next = &v1->Next;
    v1 = v1->Next;
    *p_Next = result;
  }
  return result;
}

```

## disassembly

```asm
0x1400025e0  sub     rsp, 28h
0x1400025e4  call    cs:__imp_ExpInterlockedFlushSList
0x1400025eb  nop     dword ptr [rax+rax+00h]
0x1400025f0  mov     r8, rax
0x1400025f3  xor     eax, eax
0x1400025f5  test    r8, r8
0x1400025f8  jnz     short loc_140002600
0x1400025fa  add     rsp, 28h
0x1400025fe  retn
0x140002600  mov     rdx, r8
0x140002603  mov     rcx, r8
0x140002606  mov     r8, [r8]
0x140002609  mov     [rdx], rax
0x14000260c  mov     rax, rdx
0x14000260f  test    r8, r8
0x140002612  jnz     short loc_140002600
0x140002614  jmp     short loc_1400025FA
```
