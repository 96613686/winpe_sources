# _CWLIDQueue::WLIDThreadFunc_::_1_::catch$3

- ea: `0x18001121b`
- end: `0x18001124d`
- name: `_CWLIDQueue::WLIDThreadFunc_::_1_::catch$3`
- size: `50`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CWLIDQueue::WLIDThreadFunc_::_1_::catch_3(__int64 a1, __int64 a2)
{
  int v2; // ecx

  v2 = *(_DWORD *)(*(_QWORD *)(a2 + 48) + 32LL);
  if ( v2 >= 0 )
    v2 = -2147418113;
  *(_DWORD *)(a2 + 112) = v2;
  return 0;
}

```

## disassembly

```asm
0x18001121b  mov     [rsp+arg_8], rdx
0x180011220  push    rbp
0x180011221  sub     rsp, 20h
0x180011225  mov     rbp, rdx
0x180011228  mov     rax, [rbp+30h]
0x18001122c  mov     ecx, [rax+20h]
0x18001122f  mov     eax, 8000FFFFh
0x180011234  test    ecx, ecx
0x180011236  cmovns  ecx, eax
0x180011239  mov     [rbp+70h], ecx
0x18001123c  mov     rax, 0
0x180011246  add     rsp, 20h
0x18001124a  pop     rbp
0x18001124b  retn
```
