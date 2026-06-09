# CWcnToggleButton::~CWcnToggleButton(void)

- ea: `0x18001d718`
- end: `0x18001d744`
- name: `??1CWcnToggleButton@@QEAA@XZ`
- size: `44`
- prototype: `void __fastcall(CWcnToggleButton *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001405c`

## callees

- `0x18001d718`

## import_xrefs

- `GDI32!DeleteObject` at `0x18001d738`
- `GDI32!DeleteObject` at `0x18001d738`
- `UxTheme!CloseThemeData` at `0x18001d729`
- `UxTheme!CloseThemeData` at `0x18001d729`

## pseudocode

```c
void __fastcall CWcnToggleButton::~CWcnToggleButton(CWcnToggleButton *this)
{
  void *v2; // rcx
  void *v3; // rcx

  v2 = *(void **)this;
  if ( v2 )
    CloseThemeData(v2);
  v3 = (void *)*((_QWORD *)this + 5);
  if ( v3 )
    DeleteObject(v3);
}

```

## disassembly

```asm
0x18001d718  push    rbx
0x18001d71a  sub     rsp, 20h
0x18001d71e  mov     rbx, rcx
0x18001d721  mov     rcx, [rcx]; hTheme
0x18001d724  test    rcx, rcx
0x18001d727  jz      short loc_18001D72F
0x18001d729  call    cs:__imp_CloseThemeData
0x18001d72f  mov     rcx, [rbx+28h]; ho
0x18001d733  test    rcx, rcx
0x18001d736  jz      short loc_18001D73E
0x18001d738  call    cs:__imp_DeleteObject
0x18001d73e  add     rsp, 20h
0x18001d742  pop     rbx
0x18001d743  retn
```
