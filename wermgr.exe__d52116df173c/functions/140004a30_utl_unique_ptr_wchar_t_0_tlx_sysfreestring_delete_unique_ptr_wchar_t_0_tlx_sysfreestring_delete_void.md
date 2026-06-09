# utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::~unique_ptr<wchar_t [0],tlx::sysfreestring_delete>(void)

- ea: `0x140004a30`
- end: `0x140004a47`
- name: `??1?$unique_ptr@$$BY0A@_WUsysfreestring_delete@tlx@@@utl@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(OLECHAR **)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001cd37`

## callees

- `0x140004a30`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140004a3c`
- `OLEAUT32!__imp_SysFreeString` at `0x140004a3c`

## pseudocode

```c
void __fastcall utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::~unique_ptr<wchar_t [0],tlx::sysfreestring_delete>(
        OLECHAR **a1)
{
  OLECHAR *v1; // rcx

  v1 = *a1;
  if ( v1 )
    SysFreeString(v1);
}

```

## disassembly

```asm
0x140004a30  sub     rsp, 28h
0x140004a34  mov     rcx, [rcx]; bstrString
0x140004a37  test    rcx, rcx
0x140004a3a  jz      short loc_140004A42
0x140004a3c  call    cs:__imp_SysFreeString
0x140004a42  add     rsp, 28h
0x140004a46  retn
```
