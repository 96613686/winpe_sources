# InitDefaultACL

- ea: `0x180022e40`
- end: `0x180022e5b`
- name: `InitDefaultACL`
- size: `27`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18001bd30`
- `0x18001c350`
- `0x18001cb20`
- `0x180020210`

## callees

- `0x180022e40`

## pseudocode

```c
__int64 __fastcall InitDefaultACL(int a1)
{
  __int64 result; // rax

  result = 1;
  if ( !dword_18003B4CC )
  {
    dword_18003B4CC = 1;
    g_DefaultACL = a1;
  }
  return result;
}

```

## disassembly

```asm
0x180022e40  cmp     cs:dword_18003B4CC, 0
0x180022e47  mov     eax, 1
0x180022e4c  jnz     short locret_180022E5A
0x180022e4e  mov     cs:dword_18003B4CC, eax
0x180022e54  mov     cs:g_DefaultACL, ecx
0x180022e5a  retn
```
