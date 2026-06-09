# Cache::ValueProxy<int>::SetValue(int const &)

- ea: `0x180012e50`
- end: `0x180012e7a`
- name: `?SetValue@?$ValueProxy@H@Cache@@QEAAXAEBH@Z`
- size: `42`
- prototype: `__int64 __fastcall(_QWORD *, _DWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180012e80`
- `0x18001307c`

## callees

- `0x180012e50`

## pseudocode

```c
__int64 __fastcall Cache::ValueProxy<int>::SetValue(_QWORD *a1, _DWORD *a2)
{
  unsigned int *v2; // r8
  __int64 result; // rax

  v2 = (unsigned int *)*a1;
  if ( !*(_BYTE *)(*a1 + 4LL) || (result = *v2, *a2 != (_DWORD)result) )
  {
    *((_BYTE *)v2 + 4) = 1;
    *(_DWORD *)*a1 = *a2;
    result = a1[1];
    *(_BYTE *)(result + 120) = 1;
  }
  return result;
}

```

## disassembly

```asm
0x180012e50  mov     r8, [rcx]
0x180012e53  mov     r9, rdx
0x180012e56  cmp     byte ptr [r8+4], 0
0x180012e5b  jz      short loc_180012E64
0x180012e5d  mov     eax, [r8]
0x180012e60  cmp     [rdx], eax
0x180012e62  jz      short locret_180012E79
0x180012e64  mov     byte ptr [r8+4], 1
0x180012e69  mov     eax, [r9]
0x180012e6c  mov     rdx, [rcx]
0x180012e6f  mov     [rdx], eax
0x180012e71  mov     rax, [rcx+8]
0x180012e75  mov     byte ptr [rax+78h], 1
0x180012e79  retn
```
