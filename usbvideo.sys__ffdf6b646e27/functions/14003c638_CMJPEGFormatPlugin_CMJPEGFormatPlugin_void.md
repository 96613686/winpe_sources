# CMJPEGFormatPlugin::~CMJPEGFormatPlugin(void)

- ea: `0x14003c638`
- end: `0x14003c661`
- name: `??1CMJPEGFormatPlugin@@QEAA@XZ`
- size: `41`
- prototype: `void __fastcall(CMJPEGFormatPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14003c770`

## callees

- `0x14003c638`
- `0x140040a70`

## pseudocode

```c
void __fastcall CMJPEGFormatPlugin::~CMJPEGFormatPlugin(CMJPEGFormatPlugin *this)
{
  __int64 v1; // rcx

  *(_QWORD *)this = &CMJPEGFormatPlugin::`vftable';
  v1 = *((_QWORD *)this + 1);
  if ( v1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
}

```

## disassembly

```asm
0x14003c638  sub     rsp, 28h
0x14003c63c  lea     rax, ??_7CMJPEGFormatPlugin@@6B@; const CMJPEGFormatPlugin::`vftable'
0x14003c643  mov     [rcx], rax
0x14003c646  mov     rcx, [rcx+8]
0x14003c64a  test    rcx, rcx
0x14003c64d  jz      short loc_14003C65B
0x14003c64f  mov     rax, [rcx]
0x14003c652  mov     rax, [rax+10h]
0x14003c656  call    _guard_dispatch_icall
0x14003c65b  add     rsp, 28h
0x14003c65f  retn
```
