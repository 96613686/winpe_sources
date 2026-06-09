# CVPtrList::RemoveAt(void *)

- ea: `0x180029c00`
- end: `0x180029c4d`
- name: `?RemoveAt@CVPtrList@@QEAAXPEAX@Z`
- size: `77`
- prototype: `void __fastcall(CVPtrList *__hidden this, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001383c`

## callees

- `0x180029c00`

## pseudocode

```c
void __fastcall CVPtrList::RemoveAt(CVPtrList *this, _QWORD *a2)
{
  __int64 v2; // r8
  __int64 v3; // r8

  v2 = a2[1];
  if ( a2 == *((_QWORD **)this + 53) )
    *((_QWORD *)this + 53) = v2;
  else
    *(_QWORD *)(a2[2] + 8LL) = v2;
  v3 = a2[2];
  if ( a2 == *((_QWORD **)this + 54) )
    *((_QWORD *)this + 54) = v3;
  else
    *(_QWORD *)(a2[1] + 16LL) = v3;
  a2[1] = *(_QWORD *)this;
  *(_QWORD *)this = a2;
  --*((_DWORD *)this + 110);
}

```

## disassembly

```asm
0x180029c00  mov     r8, [rdx+8]
0x180029c04  cmp     rdx, [rcx+1A8h]
0x180029c0b  jnz     short loc_180029C16
0x180029c0d  mov     [rcx+1A8h], r8
0x180029c14  jmp     short loc_180029C1E
0x180029c16  mov     rax, [rdx+10h]
0x180029c1a  mov     [rax+8], r8
0x180029c1e  mov     r8, [rdx+10h]
0x180029c22  cmp     rdx, [rcx+1B0h]
0x180029c29  jnz     short loc_180029C34
0x180029c2b  mov     [rcx+1B0h], r8
0x180029c32  jmp     short loc_180029C3C
0x180029c34  mov     rax, [rdx+8]
0x180029c38  mov     [rax+10h], r8
0x180029c3c  mov     rax, [rcx]
0x180029c3f  mov     [rdx+8], rax
0x180029c43  mov     [rcx], rdx
0x180029c46  dec     dword ptr [rcx+1B8h]
0x180029c4c  retn
```
