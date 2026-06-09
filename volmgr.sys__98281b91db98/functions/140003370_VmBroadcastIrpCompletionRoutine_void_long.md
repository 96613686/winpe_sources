# VmBroadcastIrpCompletionRoutine(void *,long)

- ea: `0x140003370`
- end: `0x140003393`
- name: `?VmBroadcastIrpCompletionRoutine@@YAXPEAXJ@Z`
- size: `35`
- prototype: `void __fastcall(void *, int)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140003381`
- `ntoskrnl!IofCompleteRequest` at `0x140003381`

## pseudocode

```c
void __fastcall VmBroadcastIrpCompletionRoutine(_DWORD *a1, int a2)
{
  a1[12] = a2;
  *((_QWORD *)a1 + 7) = 0;
  IofCompleteRequest((PIRP)a1, 1);
}

```

## disassembly

```asm
0x140003370  sub     rsp, 28h
0x140003374  mov     [rcx+30h], edx
0x140003377  mov     dl, 1; PriorityBoost
0x140003379  mov     qword ptr [rcx+38h], 0
0x140003381  call    cs:__imp_IofCompleteRequest
0x140003388  nop     dword ptr [rax+rax+00h]
0x14000338d  add     rsp, 28h
0x140003391  retn
```
