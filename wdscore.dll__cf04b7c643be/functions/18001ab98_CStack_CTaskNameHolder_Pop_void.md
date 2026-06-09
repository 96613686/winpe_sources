# CStack<CTaskNameHolder *>::Pop(void)

- ea: `0x18001ab98`
- end: `0x18001abc5`
- name: `?Pop@?$CStack@PEAVCTaskNameHolder@@@@QEAAPEAVCTaskNameHolder@@XZ`
- size: `45`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180019d70`
- `0x18001a5d8`
- `0x18001b900`
- `0x18001b940`

## callees

- `0x180018020`
- `0x18001ab98`

## pseudocode

```c
__int64 __fastcall CStack<CTaskNameHolder *>::Pop(_QWORD *a1)
{
  __int64 v1; // rdx
  __int64 v3; // rbx

  v1 = a1[1];
  if ( !v1 )
    return 0;
  v3 = *(_QWORD *)(*a1 + 8 * v1 - 8);
  CDynamicArray<CTaskNameCollection *,CTaskNameCollection * *>::SetSize((__int64)a1, v1 - 1);
  return v3;
}

```

## disassembly

```asm
0x18001ab98  push    rbx
0x18001ab9a  sub     rsp, 20h
0x18001ab9e  mov     rdx, [rcx+8]
0x18001aba2  test    rdx, rdx
0x18001aba5  jnz     short loc_18001ABAB
0x18001aba7  xor     eax, eax
0x18001aba9  jmp     short loc_18001ABBE
0x18001abab  mov     rax, [rcx]
0x18001abae  mov     rbx, [rax+rdx*8-8]
0x18001abb3  dec     rdx
0x18001abb6  call    ?SetSize@?$CDynamicArray@PEAVCTaskNameCollection@@PEAPEAV1@@@QEAAH_K@Z; CDynamicArray<CTaskNameCollection *,CTaskNameCollection * *>::SetSize(unsigned __int64)
0x18001abbb  mov     rax, rbx
0x18001abbe  add     rsp, 20h
0x18001abc2  pop     rbx
0x18001abc3  retn
```
