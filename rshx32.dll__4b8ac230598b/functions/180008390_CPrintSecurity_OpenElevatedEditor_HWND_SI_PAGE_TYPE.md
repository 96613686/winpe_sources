# CPrintSecurity::OpenElevatedEditor(HWND__ *,_SI_PAGE_TYPE)

- ea: `0x180008390`
- end: `0x180008396`
- name: `?OpenElevatedEditor@CPrintSecurity@@UEAAJPEAUHWND__@@W4_SI_PAGE_TYPE@@@Z`
- size: `6`
- prototype: `__int64 __fastcall(CPrintSecurity *__hidden this, HWND, enum _SI_PAGE_TYPE)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CPrintSecurity::OpenElevatedEditor(CPrintSecurity *this, HWND a2, enum _SI_PAGE_TYPE a3)
{
  return 2147500033LL;
}

```

## disassembly

```asm
0x180008390  mov     eax, 80004001h
0x180008395  retn
```
