# CHost::~CHost(void)

- ea: `0x140008950`
- end: `0x14000898c`
- name: `??1CHost@@QEAA@XZ`
- size: `60`
- prototype: `void __fastcall(CHost *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140001dd8`
- `0x140002310`
- `0x140006c88`

## callees

- `0x140008950`
- `0x140008c70`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140008980`
- `KERNEL32!DeleteCriticalSection` at `0x140008980`

## pseudocode

```c
void __fastcall CHost::~CHost(CHost *this)
{
  *(_QWORD *)this = &CHost::`vftable';
  CHost::Close(this);
  g_pHost = 0;
  if ( *((_BYTE *)this + 737) )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 696));
}

```

## disassembly

```asm
0x140008950  push    rbx
0x140008952  sub     rsp, 20h
0x140008956  lea     rax, ??_7CHost@@6B@; const CHost::`vftable'
0x14000895d  mov     rbx, rcx
0x140008960  mov     [rcx], rax
0x140008963  call    ?Close@CHost@@QEAAXXZ; CHost::Close(void)
0x140008968  lea     rcx, [rbx+2B8h]; lpCriticalSection
0x14000896f  mov     cs:?g_pHost@@3PEAVCHost@@EA, 0; CHost * g_pHost
0x14000897a  cmp     byte ptr [rcx+29h], 0
0x14000897e  jz      short loc_140008986
0x140008980  call    cs:__imp_DeleteCriticalSection
0x140008986  add     rsp, 20h
0x14000898a  pop     rbx
0x14000898b  retn
```
