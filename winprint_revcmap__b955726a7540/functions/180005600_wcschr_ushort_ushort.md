# wcschr(ushort *,ushort)

- ea: `0x180005600`
- end: `0x180005607`
- name: `?wcschr@@YAPEAGPEAGG@Z`
- size: `7`
- prototype: `wchar_t *__cdecl(const wchar_t *Str, wchar_t Ch)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180003d80`
- `0x1800042a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180005600`

## pseudocode

```c
// attributes: thunk
wchar_t *__cdecl wcschr(const wchar_t *Str, wchar_t Ch)
{
  return __imp_wcschr(Str, Ch);
}

```

## disassembly

```asm
0x180005600  jmp     cs:__imp_wcschr
```
