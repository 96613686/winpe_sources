# CDVFormatPlugin::~CDVFormatPlugin(void)

- ea: `0x14003c5a8`
- end: `0x14003c5d1`
- name: `??1CDVFormatPlugin@@QEAA@XZ`
- size: `41`
- prototype: `void __fastcall(CDVFormatPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14003c6f8`

## callees

- `0x14003c5a8`
- `0x140040a70`

## pseudocode

```c
void __fastcall CDVFormatPlugin::~CDVFormatPlugin(CDVFormatPlugin *this)
{
  __int64 v1; // rcx

  *(_QWORD *)this = &CDVFormatPlugin::`vftable';
  v1 = *((_QWORD *)this + 1);
  if ( v1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
}

```

## disassembly

```asm
0x14003c5a8  sub     rsp, 28h
0x14003c5ac  lea     rax, ??_7CDVFormatPlugin@@6B@; const CDVFormatPlugin::`vftable'
0x14003c5b3  mov     [rcx], rax
0x14003c5b6  mov     rcx, [rcx+8]
0x14003c5ba  test    rcx, rcx
0x14003c5bd  jz      short loc_14003C5CB
0x14003c5bf  mov     rax, [rcx]
0x14003c5c2  mov     rax, [rax+10h]
0x14003c5c6  call    _guard_dispatch_icall
0x14003c5cb  add     rsp, 28h
0x14003c5cf  retn
```
