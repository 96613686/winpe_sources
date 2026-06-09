# CVPtrList::RemoveAll(void)

- ea: `0x180029bb8`
- end: `0x180029bf7`
- name: `?RemoveAll@CVPtrList@@QEAAXXZ`
- size: `63`
- prototype: `void __fastcall(CVPtrList *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180011d34`
- `0x18001326c`

## callees

- `0x180029bb8`

## pseudocode

```c
void __fastcall CVPtrList::RemoveAll(CVPtrList *this)
{
  __int64 v1; // r8
  __int64 v2; // rdx

  v1 = *((_QWORD *)this + 53);
  if ( v1 )
  {
    do
    {
      v2 = *(_QWORD *)(v1 + 8);
      *(_QWORD *)(v1 + 8) = *(_QWORD *)this;
      *(_QWORD *)this = v1;
      v1 = v2;
      *((_QWORD *)this + 53) = v2;
    }
    while ( v2 );
  }
  *((_DWORD *)this + 110) = 0;
  *((_QWORD *)this + 54) = 0;
}

```

## disassembly

```asm
0x180029bb8  mov     r8, [rcx+1A8h]
0x180029bbf  test    r8, r8
0x180029bc2  jz      short loc_180029BE1
0x180029bc4  mov     rdx, [r8+8]
0x180029bc8  mov     rax, [rcx]
0x180029bcb  mov     [r8+8], rax
0x180029bcf  mov     [rcx], r8
0x180029bd2  mov     r8, rdx
0x180029bd5  mov     [rcx+1A8h], rdx
0x180029bdc  test    rdx, rdx
0x180029bdf  jnz     short loc_180029BC4
0x180029be1  mov     dword ptr [rcx+1B8h], 0
0x180029beb  mov     qword ptr [rcx+1B0h], 0
0x180029bf6  retn
```
