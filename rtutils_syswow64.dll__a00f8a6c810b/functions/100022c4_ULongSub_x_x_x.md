# ULongSub(x,x,x)

- ea: `0x100022c4`
- end: `0x100022ea`
- name: `_ULongSub@12`
- size: `38`
- prototype: `HRESULT __stdcall(ULONG ulMinuend, ULONG ulSubtrahend, ULONG *pulResult)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x10002160`
- `0x10005dd0`
- `0x10006770`

## callees

- `0x100022c4`

## pseudocode

```c
HRESULT __stdcall ULongSub(ULONG ulMinuend, ULONG ulSubtrahend, ULONG *pulResult)
{
  unsigned int v3; // edx
  unsigned int v4; // ecx
  int v5; // esi
  HRESULT result; // eax

  if ( v4 < v3 )
    v5 = -1;
  else
    v5 = v4 - v3;
  result = v4 < v3 ? 0x80070216 : 0;
  *(_DWORD *)ulMinuend = v5;
  return result;
}

```

## disassembly

```asm
0x100022c4  mov     edi, edi
0x100022c6  push    ebp
0x100022c7  mov     ebp, esp
0x100022c9  push    esi
0x100022ca  cmp     ecx, edx
0x100022cc  jb      short loc_100022E5
0x100022ce  mov     esi, ecx
0x100022d0  sub     esi, edx
0x100022d2  cmp     ecx, edx
0x100022d4  mov     ecx, [ebp+ulMinuend]
0x100022d7  sbb     eax, eax
0x100022d9  and     eax, 80070216h
0x100022de  mov     [ecx], esi
0x100022e0  pop     esi
0x100022e1  pop     ebp
0x100022e2  retn    4
0x100022e5  or      esi, 0FFFFFFFFh
0x100022e8  jmp     short loc_100022D2
```
