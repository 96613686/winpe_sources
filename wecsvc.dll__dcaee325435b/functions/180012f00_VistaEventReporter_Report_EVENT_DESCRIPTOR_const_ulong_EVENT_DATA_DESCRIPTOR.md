# VistaEventReporter::Report(_EVENT_DESCRIPTOR const &,ulong,_EVENT_DATA_DESCRIPTOR *)

- ea: `0x180012f00`
- end: `0x180012f18`
- name: `?Report@VistaEventReporter@@UEAAXAEBU_EVENT_DESCRIPTOR@@KPEAU_EVENT_DATA_DESCRIPTOR@@@Z`
- size: `24`
- prototype: `void __fastcall(VistaEventReporter *this, const struct _EVENT_DESCRIPTOR *, ULONG, struct _EVENT_DATA_DESCRIPTOR *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180012f00`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x180012f0d`
- `ADVAPI32!EventWrite` at `0x180012f0d`

## pseudocode

```c
void __fastcall VistaEventReporter::Report(
        VistaEventReporter *this,
        const struct _EVENT_DESCRIPTOR *a2,
        ULONG a3,
        struct _EVENT_DATA_DESCRIPTOR *a4)
{
  REGHANDLE v4; // rcx

  v4 = *((_QWORD *)this + 1);
  if ( v4 )
    EventWrite(v4, a2, a3, a4);
}

```

## disassembly

```asm
0x180012f00  sub     rsp, 28h
0x180012f04  mov     rcx, [rcx+8]; RegHandle
0x180012f08  test    rcx, rcx
0x180012f0b  jz      short loc_180012F13
0x180012f0d  call    cs:__imp_EventWrite
0x180012f13  add     rsp, 28h
0x180012f17  retn
```
