# NCoreLibrary::TLink::Link(NCoreLibrary::TLink *)

- ea: `0x1400140b8`
- end: `0x14001410a`
- name: `?Link@TLink@NCoreLibrary@@QEAAJPEAV12@@Z`
- size: `82`
- prototype: `__int64 __fastcall(NCoreLibrary::TLink *__hidden this, struct NCoreLibrary::TLink *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14001200c`
- `0x1400138cc`
- `0x1400139b0`

## callees

- `0x1400140b8`

## pseudocode

```c
__int64 __fastcall NCoreLibrary::TLink::Link(NCoreLibrary::TLink *this, struct NCoreLibrary::TLink *a2)
{
  __int64 result; // rax
  struct NCoreLibrary::TLink *v4; // rcx
  char *v5; // r8

  result = 2147500037LL;
  if ( a2 )
  {
    v4 = (struct NCoreLibrary::TLink *)*((_QWORD *)a2 + 2);
    v5 = (char *)a2 + 24;
    if ( v4 != a2 && *(struct NCoreLibrary::TLink **)v5 != a2 )
    {
      *((_QWORD *)v4 + 3) = *(_QWORD *)v5;
      *(_QWORD *)(*(_QWORD *)v5 + 16LL) = *((_QWORD *)a2 + 2);
      *((_QWORD *)a2 + 2) = a2;
      *(_QWORD *)v5 = a2;
    }
    *(_QWORD *)(*((_QWORD *)this + 2) + 24LL) = a2;
    *((_QWORD *)a2 + 2) = *((_QWORD *)this + 2);
    result = 0;
    *(_QWORD *)v5 = this;
    *((_QWORD *)this + 2) = a2;
  }
  return result;
}

```

## disassembly

```asm
0x1400140b8  mov     r9, rcx
0x1400140bb  mov     eax, 80004005h
0x1400140c0  test    rdx, rdx
0x1400140c3  jz      short locret_140014109
0x1400140c5  mov     rcx, [rdx+10h]
0x1400140c9  lea     r8, [rdx+18h]
0x1400140cd  cmp     rcx, rdx
0x1400140d0  jz      short loc_1400140F0
0x1400140d2  mov     rax, [r8]
0x1400140d5  cmp     rax, rdx
0x1400140d8  jz      short loc_1400140F0
0x1400140da  mov     [rcx+18h], rax
0x1400140de  mov     rcx, [r8]
0x1400140e1  mov     rax, [rdx+10h]
0x1400140e5  mov     [rcx+10h], rax
0x1400140e9  mov     [rdx+10h], rdx
0x1400140ed  mov     [r8], rdx
0x1400140f0  mov     rax, [r9+10h]
0x1400140f4  mov     [rax+18h], rdx
0x1400140f8  mov     rax, [r9+10h]
0x1400140fc  mov     [rdx+10h], rax
0x140014100  xor     eax, eax
0x140014102  mov     [r8], r9
0x140014105  mov     [r9+10h], rdx
0x140014109  retn
```
