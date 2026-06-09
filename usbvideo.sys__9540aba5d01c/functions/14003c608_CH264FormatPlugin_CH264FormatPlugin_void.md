# CH264FormatPlugin::~CH264FormatPlugin(void)

- ea: `0x14003c608`
- end: `0x14003c631`
- name: `??1CH264FormatPlugin@@QEAA@XZ`
- size: `41`
- prototype: `void __fastcall(CH264FormatPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14003c748`

## callees

- `0x14003c608`
- `0x140040a70`

## pseudocode

```c
void __fastcall CH264FormatPlugin::~CH264FormatPlugin(CH264FormatPlugin *this)
{
  __int64 v1; // rcx

  *(_QWORD *)this = &CH264FormatPlugin::`vftable';
  v1 = *((_QWORD *)this + 1);
  if ( v1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
}

```

## disassembly

```asm
0x14003c608  sub     rsp, 28h
0x14003c60c  lea     rax, ??_7CH264FormatPlugin@@6B@; const CH264FormatPlugin::`vftable'
0x14003c613  mov     [rcx], rax
0x14003c616  mov     rcx, [rcx+8]
0x14003c61a  test    rcx, rcx
0x14003c61d  jz      short loc_14003C62B
0x14003c61f  mov     rax, [rcx]
0x14003c622  mov     rax, [rax+10h]
0x14003c626  call    _guard_dispatch_icall
0x14003c62b  add     rsp, 28h
0x14003c62f  retn
```
