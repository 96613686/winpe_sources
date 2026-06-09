# Cache::ValueProxy<bool>::SetValue(bool const &)

- ea: `0x180011e2c`
- end: `0x180011e56`
- name: `?SetValue@?$ValueProxy@_N@Cache@@QEAAXAEB_N@Z`
- size: `42`
- prototype: `char __fastcall(_QWORD *, _BYTE *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180010784`
- `0x180010afc`
- `0x18001126c`
- `0x180012178`
- `0x180012628`
- `0x180012d38`

## callees

- `0x180011e2c`

## pseudocode

```c
char __fastcall Cache::ValueProxy<bool>::SetValue(_QWORD *a1, _BYTE *a2)
{
  _BYTE *v2; // r8
  __int64 v3; // rax

  v2 = (_BYTE *)*a1;
  if ( !*(_BYTE *)(*a1 + 1LL) || (LOBYTE(v3) = *v2, *a2 != *v2) )
  {
    v2[1] = 1;
    *(_BYTE *)*a1 = *a2;
    v3 = a1[1];
    *(_BYTE *)(v3 + 120) = 1;
  }
  return v3;
}

```

## disassembly

```asm
0x180011e2c  mov     r8, [rcx]
0x180011e2f  mov     r9, rdx
0x180011e32  cmp     byte ptr [r8+1], 0
0x180011e37  jz      short loc_180011E40
0x180011e39  mov     al, [r8]
0x180011e3c  cmp     [rdx], al
0x180011e3e  jz      short locret_180011E55
0x180011e40  mov     byte ptr [r8+1], 1
0x180011e45  mov     al, [r9]
0x180011e48  mov     rdx, [rcx]
0x180011e4b  mov     [rdx], al
0x180011e4d  mov     rax, [rcx+8]
0x180011e51  mov     byte ptr [rax+78h], 1
0x180011e55  retn
```
