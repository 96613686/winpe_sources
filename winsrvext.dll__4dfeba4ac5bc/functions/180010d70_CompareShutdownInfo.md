# CompareShutdownInfo

- ea: `0x180010d70`
- end: `0x180010da9`
- name: `CompareShutdownInfo`
- size: `57`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800113d0`
- `0x180011694`

## callees

- `0x180010d70`

## pseudocode

```c
__int64 __fastcall CompareShutdownInfo(_DWORD **a1, _QWORD *a2)
{
  _DWORD *v2; // rcx
  _DWORD *v3; // r8
  unsigned int v4; // eax
  unsigned int v5; // ecx

  v2 = *a1;
  v3 = (_DWORD *)*a2;
  if ( *v2 <= *(_DWORD *)*a2 )
  {
    if ( *v2 < *(_DWORD *)*a2 )
      return 1;
    v4 = v2[1];
    if ( v4 <= v3[1] )
    {
      if ( v4 >= v3[1] )
      {
        v5 = v2[2];
        if ( v5 >= v3[2] )
          return v5 > v3[2];
        return 0xFFFFFFFFLL;
      }
      return 1;
    }
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x180010d70  mov     rcx, [rcx]
0x180010d73  mov     r8, [rdx]
0x180010d76  mov     eax, [rcx]
0x180010d78  cmp     eax, [r8]
0x180010d7b  ja      short loc_180010DA5
0x180010d7d  jb      short loc_180010D9E
0x180010d7f  mov     eax, [rcx+4]
0x180010d82  cmp     eax, [r8+4]
0x180010d86  ja      short loc_180010DA5
0x180010d88  jb      short loc_180010D9E
0x180010d8a  mov     ecx, [rcx+8]
0x180010d8d  cmp     ecx, [r8+8]
0x180010d91  jb      short loc_180010DA5
0x180010d93  xor     eax, eax
0x180010d95  cmp     ecx, [r8+8]
0x180010d99  setnbe  al
0x180010d9c  retn
0x180010d9e  mov     eax, 1
0x180010da3  retn
0x180010da5  or      eax, 0FFFFFFFFh
0x180010da8  retn
```
