# CDeleteMe<QL_LEVEL_1_RPN_EXPRESSION>::~CDeleteMe<QL_LEVEL_1_RPN_EXPRESSION>(void)

- ea: `0x18000bb54`
- end: `0x18000bb6a`
- name: `??1?$CDeleteMe@UQL_LEVEL_1_RPN_EXPRESSION@@@@QEAA@XZ`
- size: `22`
- prototype: `void *__fastcall(QL_LEVEL_1_RPN_EXPRESSION **, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180006740`
- `0x180007100`
- `0x180015e10`
- `0x180015fd0`

## callees

- `0x18000ae94`
- `0x18000bb54`

## pseudocode

```c
void *__fastcall CDeleteMe<QL_LEVEL_1_RPN_EXPRESSION>::~CDeleteMe<QL_LEVEL_1_RPN_EXPRESSION>(
        QL_LEVEL_1_RPN_EXPRESSION **a1,
        unsigned int a2)
{
  QL_LEVEL_1_RPN_EXPRESSION *v2; // rcx
  void *result; // rax

  v2 = *a1;
  if ( v2 )
    return QL_LEVEL_1_RPN_EXPRESSION::`scalar deleting destructor'(v2, a2);
  return result;
}

```

## disassembly

```asm
0x18000bb54  sub     rsp, 28h
0x18000bb58  mov     rcx, [rcx]; this
0x18000bb5b  test    rcx, rcx
0x18000bb5e  jz      short loc_18000BB65
0x18000bb60  call    ??_GQL_LEVEL_1_RPN_EXPRESSION@@QEAAPEAXI@Z; QL_LEVEL_1_RPN_EXPRESSION::`scalar deleting destructor'(uint)
0x18000bb65  add     rsp, 28h
0x18000bb69  retn
```
