# DeleteOutInterfaceEntry

- ea: `0x18001db88`
- end: `0x18001dbc7`
- name: `DeleteOutInterfaceEntry`
- size: `63`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180019de0`
- `0x18001d378`
- `0x18001d908`
- `0x18001decc`

## callees

- `0x18001db88`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18001dbb9`

## pseudocode

```c
BOOL __fastcall DeleteOutInterfaceEntry(_QWORD *a1)
{
  _QWORD *v1; // rax
  _QWORD *v2; // rdx

  v1 = (_QWORD *)*a1;
  if ( a1 != (_QWORD *)*a1 )
  {
    if ( (_QWORD *)v1[1] != a1 || (v2 = (_QWORD *)a1[1], (_QWORD *)*v2 != a1) )
      __fastfail(3u);
    *v2 = v1;
    v1[1] = v2;
    *a1 = a1;
    a1[1] = a1;
  }
  return HeapFree(hHeap, 0, a1);
}

```

## disassembly

```asm
0x18001db88  mov     rax, [rcx]
0x18001db8b  cmp     rcx, rax
0x18001db8e  jz      short loc_18001DBAD
0x18001db90  cmp     [rax+8], rcx
0x18001db94  jnz     short loc_18001DBC0
0x18001db96  mov     rdx, [rcx+8]
0x18001db9a  cmp     [rdx], rcx
0x18001db9d  jnz     short loc_18001DBC0
0x18001db9f  mov     [rdx], rax
0x18001dba2  mov     [rax+8], rdx
0x18001dba6  mov     [rcx], rcx
0x18001dba9  mov     [rcx+8], rcx
0x18001dbad  mov     r8, rcx
0x18001dbb0  xor     edx, edx
0x18001dbb2  mov     rcx, cs:hHeap
0x18001dbb9  jmp     cs:__imp_HeapFree
0x18001dbc0  mov     ecx, 3
0x18001dbc5  int     29h; Win8: RtlFailFast(ecx)
```
