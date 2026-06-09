# CFrameFormatPlugin::~CFrameFormatPlugin(void)

- ea: `0x14003c5d8`
- end: `0x14003c601`
- name: `??1CFrameFormatPlugin@@QEAA@XZ`
- size: `41`
- prototype: `void __fastcall(CFrameFormatPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14003c720`

## callees

- `0x14003c5d8`
- `0x140040a70`

## pseudocode

```c
void __fastcall CFrameFormatPlugin::~CFrameFormatPlugin(CFrameFormatPlugin *this)
{
  __int64 v1; // rcx

  *(_QWORD *)this = &CFrameFormatPlugin::`vftable';
  v1 = *((_QWORD *)this + 1);
  if ( v1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
}

```

## disassembly

```asm
0x14003c5d8  sub     rsp, 28h
0x14003c5dc  lea     rax, ??_7CFrameFormatPlugin@@6B@; const CFrameFormatPlugin::`vftable'
0x14003c5e3  mov     [rcx], rax
0x14003c5e6  mov     rcx, [rcx+8]
0x14003c5ea  test    rcx, rcx
0x14003c5ed  jz      short loc_14003C5FB
0x14003c5ef  mov     rax, [rcx]
0x14003c5f2  mov     rax, [rax+10h]
0x14003c5f6  call    _guard_dispatch_icall
0x14003c5fb  add     rsp, 28h
0x14003c5ff  retn
```
