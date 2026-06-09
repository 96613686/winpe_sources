# CUwfConfiguration::CopyTree(CUwfRegKey &,ushort const *,HKEY__ *,bool)

- ea: `0x180006ae0`
- end: `0x180006b12`
- name: `?CopyTree@CUwfConfiguration@@QEAAJAEAVCUwfRegKey@@PEBGPEAUHKEY__@@_N@Z`
- size: `50`
- prototype: `int __fastcall(CUwfConfiguration *this, struct CUwfRegKey *, const unsigned __int16 *, HKEY, bool)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180006a40`
- `0x180007420`
- `0x1800091f0`

## callees

- `0x180006ae0`
- `0x18000d630`
- `0x18000d690`

## pseudocode

```c
int __fastcall CUwfConfiguration::CopyTree(
        CUwfConfiguration *this,
        struct CUwfRegKey *a2,
        const unsigned __int16 *a3,
        HKEY a4,
        bool a5)
{
  void *v6; // r9

  v6 = (void *)*((_QWORD *)this + 1);
  if ( v6 == (void *)-1LL )
    return CUwfRegKey::CopyTree(a2, a4, a3, a5);
  else
    return CUwfRegKey::CopyTreeTransacted(a2, a3, a4, v6, a5);
}

```

## disassembly

```asm
0x180006ae0  push    rbx
0x180006ae2  mov     r10, r9
0x180006ae5  mov     r11, r8
0x180006ae8  mov     r9, [rcx+8]; void *
0x180006aec  mov     rbx, rdx
0x180006aef  mov     rcx, rdx; this
0x180006af2  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x180006af6  jz      short loc_180006B04
0x180006af8  mov     r8, r10; HKEY
0x180006afb  mov     rdx, r11; unsigned __int16 *
0x180006afe  pop     rbx
0x180006aff  jmp     ?CopyTreeTransacted@CUwfRegKey@@QEAAJPEBGPEAUHKEY__@@PEAX_N@Z; CUwfRegKey::CopyTreeTransacted(ushort const *,HKEY__ *,void *,bool)
0x180006b04  mov     r9b, [rsp+8+arg_20]; bool
0x180006b09  mov     rdx, r10; HKEY
0x180006b0c  pop     rbx
0x180006b0d  jmp     ?CopyTree@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBG_N@Z; CUwfRegKey::CopyTree(HKEY__ *,ushort const *,bool)
```
