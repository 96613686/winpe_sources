# CWcnAutoArtwork::~CWcnAutoArtwork(void)

- ea: `0x18001cf94`
- end: `0x18001cfc0`
- name: `??1CWcnAutoArtwork@@QEAA@XZ`
- size: `44`
- prototype: `void __fastcall(CWcnAutoArtwork *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f360`
- `0x180017d3c`

## callees

- `0x18001cf94`

## import_xrefs

- `USER32!DestroyIcon` at `0x18001cfb4`
- `USER32!DestroyIcon` at `0x18001cfb4`
- `GDI32!DeleteObject` at `0x18001cfa5`
- `GDI32!DeleteObject` at `0x18001cfa5`

## pseudocode

```c
void __fastcall CWcnAutoArtwork::~CWcnAutoArtwork(CWcnAutoArtwork *this)
{
  void *v2; // rcx
  HICON v3; // rcx

  v2 = *(void **)this;
  if ( v2 )
    DeleteObject(v2);
  v3 = (HICON)*((_QWORD *)this + 1);
  if ( v3 )
    DestroyIcon(v3);
}

```

## disassembly

```asm
0x18001cf94  push    rbx
0x18001cf96  sub     rsp, 20h
0x18001cf9a  mov     rbx, rcx
0x18001cf9d  mov     rcx, [rcx]; ho
0x18001cfa0  test    rcx, rcx
0x18001cfa3  jz      short loc_18001CFAB
0x18001cfa5  call    cs:__imp_DeleteObject
0x18001cfab  mov     rcx, [rbx+8]; hIcon
0x18001cfaf  test    rcx, rcx
0x18001cfb2  jz      short loc_18001CFBA
0x18001cfb4  call    cs:__imp_DestroyIcon
0x18001cfba  add     rsp, 20h
0x18001cfbe  pop     rbx
0x18001cfbf  retn
```
