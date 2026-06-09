# wcschr(ushort *,ushort)

- ea: `0x180017580`
- end: `0x180017587`
- name: `?wcschr@@YAPEAGPEAGG@Z`
- size: `7`
- prototype: `wchar_t *__cdecl(const wchar_t *Str, wchar_t Ch)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800059a8`
- `0x180006650`
- `0x180009cac`
- `0x180016b38`
- `0x180016eec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180017580`

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
0x180017580  jmp     cs:__imp_wcschr
```
