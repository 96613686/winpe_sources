# TdipBuildProviderList

- ea: `0x140002200`
- end: `0x14000222d`
- name: `TdipBuildProviderList`
- size: `45`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001df0`

## callees

- `0x140002240`

## pseudocode

```c
bool __fastcall TdipBuildProviderList(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  _QWORD *v4; // rbx
  __int64 v6; // [rsp+20h] [rbp-18h]

  v4 = (_QWORD *)(a1 + 88);
  TdipGetMultiSZList((_QWORD *)(a1 + 88), a2, (const UNICODE_STRING *)(a1 + 32), a4, v6, (unsigned int *)(a1 + 96));
  return *v4 != 0;
}

```

## disassembly

```asm
0x140002200  push    rbx
0x140002202  sub     rsp, 30h
0x140002206  lea     rax, [rcx+60h]
0x14000220a  lea     rbx, [rcx+58h]
0x14000220e  mov     [rsp+38h+var_10], rax
0x140002213  lea     r8, [rcx+20h]
0x140002217  mov     rcx, rbx
0x14000221a  call    TdipGetMultiSZList
0x14000221f  cmp     qword ptr [rbx], 0
0x140002223  setnz   al
0x140002226  add     rsp, 30h
0x14000222a  pop     rbx
0x14000222b  retn
```
