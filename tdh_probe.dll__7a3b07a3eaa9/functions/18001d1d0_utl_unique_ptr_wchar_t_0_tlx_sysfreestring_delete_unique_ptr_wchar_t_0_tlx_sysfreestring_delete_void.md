# utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::~unique_ptr<wchar_t [0],tlx::sysfreestring_delete>(void)

- ea: `0x18001d1d0`
- end: `0x18001d1e7`
- name: `??1?$unique_ptr@$$BY0A@_WUsysfreestring_delete@tlx@@@utl@@QEAA@XZ`
- size: `23`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x180013ca4`
- `0x180014ff4`
- `0x18001cdcc`
- `0x18001cfb0`
- `0x180029998`
- `0x180029f04`
- `0x18004a246`
- `0x18004a42c`
- `0x18004a686`
- `0x18004ab8e`

## callees

- `0x18001d1d0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001d1dc`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d1dc`

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
0x18001d1d0  sub     rsp, 28h
0x18001d1d4  mov     rcx, [rcx]; bstrString
0x18001d1d7  test    rcx, rcx
0x18001d1da  jz      short loc_18001D1E2
0x18001d1dc  call    cs:__imp_SysFreeString
0x18001d1e2  add     rsp, 28h
0x18001d1e6  retn
```
