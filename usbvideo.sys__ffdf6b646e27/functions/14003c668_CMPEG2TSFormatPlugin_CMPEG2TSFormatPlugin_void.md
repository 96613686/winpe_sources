# CMPEG2TSFormatPlugin::~CMPEG2TSFormatPlugin(void)

- ea: `0x14003c668`
- end: `0x14003c691`
- name: `??1CMPEG2TSFormatPlugin@@QEAA@XZ`
- size: `41`
- prototype: `void __fastcall(CMPEG2TSFormatPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14003c798`

## callees

- `0x14003c668`
- `0x140040a70`

## pseudocode

```c
void __fastcall CMPEG2TSFormatPlugin::~CMPEG2TSFormatPlugin(CMPEG2TSFormatPlugin *this)
{
  __int64 v1; // rcx

  *(_QWORD *)this = &CMPEG2TSFormatPlugin::`vftable';
  v1 = *((_QWORD *)this + 1);
  if ( v1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
}

```

## disassembly

```asm
0x14003c668  sub     rsp, 28h
0x14003c66c  lea     rax, ??_7CMPEG2TSFormatPlugin@@6B@; const CMPEG2TSFormatPlugin::`vftable'
0x14003c673  mov     [rcx], rax
0x14003c676  mov     rcx, [rcx+8]
0x14003c67a  test    rcx, rcx
0x14003c67d  jz      short loc_14003C68B
0x14003c67f  mov     rax, [rcx]
0x14003c682  mov     rax, [rax+10h]
0x14003c686  call    _guard_dispatch_icall
0x14003c68b  add     rsp, 28h
0x14003c68f  retn
```
