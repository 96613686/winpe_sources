# VidThreadPoolThreadRemove

- ea: `0x1400f85dc`
- end: `0x1400f8629`
- name: `VidThreadPoolThreadRemove`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140011dd0`
- `0x14001c9f0`
- `0x14008d084`
- `0x140098864`
- `0x140098958`

## callees

- `0x1400f7568`
- `0x1400f85dc`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400f85ec`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400f85ec`
- `ntoskrnl!KeSetEvent` at `0x1400f8604`
- `ntoskrnl!KeSetEvent` at `0x1400f8604`

## pseudocode

```c
LONG __fastcall VidThreadPoolThreadRemove(union _SLIST_HEADER *a1, char a2)
{
  PSLIST_ENTRY v3; // rdi
  LONG result; // eax

  v3 = ExpInterlockedPopEntrySList(a1 + 5);
  result = KeSetEvent((PRKEVENT)&v3[-2], 0, 0);
  if ( a2 )
    return VidThreadWaitForExit(*((_QWORD *)&v3[-3].Next + 1));
  return result;
}

```

## disassembly

```asm
0x1400f85dc  mov     [rsp+arg_0], rbx
0x1400f85e1  push    rdi
0x1400f85e2  sub     rsp, 20h
0x1400f85e6  add     rcx, 50h ; 'P'; ListHead
0x1400f85ea  mov     bl, dl
0x1400f85ec  call    cs:__imp_ExpInterlockedPopEntrySList
0x1400f85f3  nop     dword ptr [rax+rax+00h]
0x1400f85f8  xor     r8d, r8d; Wait
0x1400f85fb  xor     edx, edx; Increment
0x1400f85fd  mov     rdi, rax
0x1400f8600  lea     rcx, [rax-20h]; Event
0x1400f8604  call    cs:__imp_KeSetEvent
0x1400f860b  nop     dword ptr [rax+rax+00h]
0x1400f8610  test    bl, bl
0x1400f8612  jz      short loc_1400F861D
0x1400f8614  mov     rcx, [rdi-28h]
0x1400f8618  call    VidThreadWaitForExit
0x1400f861d  mov     rbx, [rsp+28h+arg_0]
0x1400f8622  add     rsp, 20h
0x1400f8626  pop     rdi
0x1400f8627  retn
```
