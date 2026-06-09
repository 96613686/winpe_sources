# IsValidInterfaceNumber(_HW_DEVICE_EXTENSION *,uchar)

- ea: `0x14005c6d0`
- end: `0x14005c706`
- name: `?IsValidInterfaceNumber@@YAEPEAU_HW_DEVICE_EXTENSION@@E@Z`
- size: `54`
- prototype: `unsigned __int8 __fastcall(struct _HW_DEVICE_EXTENSION *, unsigned __int8)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14005a134`
- `0x14005a378`
- `0x14005a820`
- `0x14005c594`

## callees

- `0x14005c6d0`

## pseudocode

```c
unsigned __int8 __fastcall IsValidInterfaceNumber(struct _HW_DEVICE_EXTENSION *a1, char a2)
{
  int i; // r8d

  for ( i = 0; i < *(unsigned __int8 *)(*((_QWORD *)a1 + 4) + 4LL); ++i )
  {
    if ( a2 == *(_BYTE *)(*(_QWORD *)(*((_QWORD *)a1 + 83) + 16LL * i) + 2LL) )
      return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x14005c6d0  mov     rax, [rcx+20h]
0x14005c6d4  mov     r9, rcx
0x14005c6d7  xor     r8d, r8d
0x14005c6da  movzx   r10d, byte ptr [rax+4]
0x14005c6df  cmp     r8d, r10d
0x14005c6e2  jge     short loc_14005C703
0x14005c6e4  mov     rax, [r9+298h]
0x14005c6eb  movsxd  rcx, r8d
0x14005c6ee  add     rcx, rcx
0x14005c6f1  mov     rcx, [rax+rcx*8]
0x14005c6f5  cmp     dl, [rcx+2]
0x14005c6f8  jz      short loc_14005C6FF
0x14005c6fa  inc     r8d
0x14005c6fd  jmp     short loc_14005C6DF
0x14005c6ff  mov     al, 1
0x14005c701  retn
0x14005c703  xor     al, al
0x14005c705  retn
```
