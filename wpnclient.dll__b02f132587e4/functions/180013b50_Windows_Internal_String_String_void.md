# Windows::Internal::String::~String(void)

- ea: `0x180013b50`
- end: `0x180013b60`
- name: `??1String@Internal@Windows@@QEAA@XZ`
- size: `16`
- prototype: `void __fastcall(Windows::Internal::String *__hidden this)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180030910`
- `0x180030ab0`
- `0x180030ff0`
- `0x180031060`
- `0x180031140`
- `0x180031571`
- `0x18003162c`
- `0x18003166a`
- `0x18003167c`

## callees

- `0x180013b50`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013b58`

## pseudocode

```c
void __fastcall Windows::Internal::String::~String(HSTRING *this)
{
  HSTRING v1; // rcx

  v1 = *this;
  if ( v1 )
    WindowsDeleteString(v1);
}

```

## disassembly

```asm
0x180013b50  mov     rcx, [rcx]
0x180013b53  test    rcx, rcx
0x180013b56  jz      short locret_180013B5F
0x180013b58  jmp     cs:__imp_WindowsDeleteString
0x180013b5f  retn
```
