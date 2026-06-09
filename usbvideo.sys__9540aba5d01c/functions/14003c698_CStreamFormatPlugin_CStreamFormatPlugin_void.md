# CStreamFormatPlugin::~CStreamFormatPlugin(void)

- ea: `0x14003c698`
- end: `0x14003c6c1`
- name: `??1CStreamFormatPlugin@@QEAA@XZ`
- size: `41`
- prototype: `void __fastcall(CStreamFormatPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14003c7c0`

## callees

- `0x14003c698`
- `0x140040a70`

## pseudocode

```c
void __fastcall CStreamFormatPlugin::~CStreamFormatPlugin(CStreamFormatPlugin *this)
{
  __int64 v1; // rcx

  *(_QWORD *)this = &CStreamFormatPlugin::`vftable';
  v1 = *((_QWORD *)this + 1);
  if ( v1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
}

```

## disassembly

```asm
0x14003c698  sub     rsp, 28h
0x14003c69c  lea     rax, ??_7CStreamFormatPlugin@@6B@; const CStreamFormatPlugin::`vftable'
0x14003c6a3  mov     [rcx], rax
0x14003c6a6  mov     rcx, [rcx+8]
0x14003c6aa  test    rcx, rcx
0x14003c6ad  jz      short loc_14003C6BB
0x14003c6af  mov     rax, [rcx]
0x14003c6b2  mov     rax, [rax+10h]
0x14003c6b6  call    _guard_dispatch_icall
0x14003c6bb  add     rsp, 28h
0x14003c6bf  retn
```
