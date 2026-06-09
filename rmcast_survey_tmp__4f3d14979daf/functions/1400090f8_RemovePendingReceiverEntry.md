# RemovePendingReceiverEntry

- ea: `0x1400090f8`
- end: `0x140009149`
- name: `RemovePendingReceiverEntry`
- size: `81`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000e03c`
- `0x14000f2d8`
- `0x1400142e8`

## callees

- `0x1400090f8`

## pseudocode

```c
_QWORD *__fastcall RemovePendingReceiverEntry(_QWORD *a1)
{
  _QWORD *v1; // rax
  __int64 v2; // rdx
  _QWORD *v3; // r8
  _QWORD *result; // rax
  __int64 v5; // rdx
  _QWORD *v6; // rcx

  v1 = a1 + 10;
  v2 = a1[10];
  if ( *(_QWORD **)(v2 + 8) != a1 + 10 )
    goto LABEL_6;
  v3 = (_QWORD *)a1[11];
  if ( (_QWORD *)*v3 != v1
    || (*v3 = v2,
        *(_QWORD *)(v2 + 8) = v3,
        a1[11] = a1 + 10,
        *v1 = v1,
        result = a1 + 8,
        v5 = a1[8],
        *(_QWORD **)(v5 + 8) != a1 + 8)
    || (v6 = (_QWORD *)a1[9], (_QWORD *)*v6 != result) )
  {
LABEL_6:
    __fastfail(3u);
  }
  *v6 = v5;
  *(_QWORD *)(v5 + 8) = v6;
  result[1] = result;
  *result = result;
  return result;
}

```

## disassembly

```asm
0x1400090f8  lea     rax, [rcx+50h]
0x1400090fc  mov     rdx, [rax]
0x1400090ff  cmp     [rdx+8], rax
0x140009103  jnz     short loc_140009142
0x140009105  mov     r8, [rax+8]
0x140009109  cmp     [r8], rax
0x14000910c  jnz     short loc_140009142
0x14000910e  mov     [r8], rdx
0x140009111  mov     [rdx+8], r8
0x140009115  mov     [rax+8], rax
0x140009119  mov     [rax], rax
0x14000911c  lea     rax, [rcx+40h]
0x140009120  mov     rdx, [rax]
0x140009123  cmp     [rdx+8], rax
0x140009127  jnz     short loc_140009142
0x140009129  mov     rcx, [rax+8]
0x14000912d  cmp     [rcx], rax
0x140009130  jnz     short loc_140009142
0x140009132  mov     [rcx], rdx
0x140009135  mov     [rdx+8], rcx
0x140009139  mov     [rax+8], rax
0x14000913d  mov     [rax], rax
0x140009140  retn
0x140009142  mov     ecx, 3
0x140009147  int     29h; Win8: RtlFailFast(ecx)
```
