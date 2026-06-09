# CUncompressedFormatPlugin::~CUncompressedFormatPlugin(void)

- ea: `0x14003c6c8`
- end: `0x14003c6f1`
- name: `??1CUncompressedFormatPlugin@@QEAA@XZ`
- size: `41`
- prototype: `void __fastcall(CUncompressedFormatPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14003c7e8`

## callees

- `0x14003c6c8`
- `0x140040a70`

## pseudocode

```c
void __fastcall CUncompressedFormatPlugin::~CUncompressedFormatPlugin(CUncompressedFormatPlugin *this)
{
  __int64 v1; // rcx

  *(_QWORD *)this = &CUncompressedFormatPlugin::`vftable';
  v1 = *((_QWORD *)this + 1);
  if ( v1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
}

```

## disassembly

```asm
0x14003c6c8  sub     rsp, 28h
0x14003c6cc  lea     rax, ??_7CUncompressedFormatPlugin@@6B@; const CUncompressedFormatPlugin::`vftable'
0x14003c6d3  mov     [rcx], rax
0x14003c6d6  mov     rcx, [rcx+8]
0x14003c6da  test    rcx, rcx
0x14003c6dd  jz      short loc_14003C6EB
0x14003c6df  mov     rax, [rcx]
0x14003c6e2  mov     rax, [rax+10h]
0x14003c6e6  call    _guard_dispatch_icall
0x14003c6eb  add     rsp, 28h
0x14003c6ef  retn
```
