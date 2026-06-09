# CStack<CTaskNameCollection *>::Peek(void)

- ea: `0x18001ab78`
- end: `0x18001ab8e`
- name: `?Peek@?$CStack@PEAVCTaskNameCollection@@@@QEAAPEAVCTaskNameCollection@@XZ`
- size: `22`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18001b940`
- `0x18001b990`
- `0x18001b9e0`
- `0x18001ba40`
- `0x18001bab0`
- `0x18001bc90`

## callees

- `0x18001ab78`

## pseudocode

```c
__int64 __fastcall CStack<CTaskNameCollection *>::Peek(_QWORD *a1)
{
  __int64 v1; // rdx

  v1 = a1[1];
  if ( v1 )
    return *(_QWORD *)(*a1 + 8 * v1 - 8);
  else
    return 0;
}

```

## disassembly

```asm
0x18001ab78  mov     rdx, [rcx+8]
0x18001ab7c  test    rdx, rdx
0x18001ab7f  jnz     short loc_18001AB85
0x18001ab81  xor     eax, eax
0x18001ab83  retn
0x18001ab85  mov     rax, [rcx]
0x18001ab88  mov     rax, [rax+rdx*8-8]
0x18001ab8d  retn
```
