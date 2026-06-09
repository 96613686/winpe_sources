# SmpFreeSavedRegistryEntry

- ea: `0x14000d494`
- end: `0x14000d4b9`
- name: `SmpFreeSavedRegistryEntry`
- size: `37`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140007e50`
- `0x140008470`
- `0x140009930`
- `0x14000c638`
- `0x14000eb40`
- `0x14000f3ec`
- `0x14000f9c8`
- `0x14000fcf8`
- `0x140014c70`
- `0x140015ae8`

## callees

- `0x14000b408`
- `0x14000d494`

## pseudocode

```c
__int64 __fastcall SmpFreeSavedRegistryEntry(_QWORD *a1)
{
  __int64 v1; // rdx
  _QWORD *v2; // rax

  v1 = *a1;
  if ( *(_QWORD **)(*a1 + 8LL) != a1 || (v2 = (_QWORD *)a1[1], (_QWORD *)*v2 != a1) )
    __fastfail(3u);
  *v2 = v1;
  *(_QWORD *)(v1 + 8) = v2;
  return SmpDeallocSavedRegistryEntry(a1);
}

```

## disassembly

```asm
0x14000d494  mov     rdx, [rcx]
0x14000d497  cmp     [rdx+8], rcx
0x14000d49b  jnz     short loc_14000D4B2
0x14000d49d  mov     rax, [rcx+8]
0x14000d4a1  cmp     [rax], rcx
0x14000d4a4  jnz     short loc_14000D4B2
0x14000d4a6  mov     [rax], rdx
0x14000d4a9  mov     [rdx+8], rax
0x14000d4ad  jmp     SmpDeallocSavedRegistryEntry
0x14000d4b2  mov     ecx, 3
0x14000d4b7  int     29h; Win8: RtlFailFast(ecx)
```
