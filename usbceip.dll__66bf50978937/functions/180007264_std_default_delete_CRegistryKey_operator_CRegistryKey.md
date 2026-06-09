# std::default_delete<CRegistryKey>::operator()(CRegistryKey *)

- ea: `0x180007264`
- end: `0x18000728c`
- name: `??R?$default_delete@VCRegistryKey@@@std@@QEBAXPEAVCRegistryKey@@@Z`
- size: `40`
- prototype: `void __fastcall(__int64, HKEY *)`
- caller_count: `6`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x180007248`
- `0x180009c50`
- `0x180009d50`
- `0x180009e50`
- `0x18000aa38`
- `0x18000af00`

## callees

- `0x180002434`
- `0x180007264`
- `0x18000bd24`

## pseudocode

```c
void __fastcall std::default_delete<CRegistryKey>::operator()(__int64 a1, HKEY *a2)
{
  if ( a2 )
  {
    CRegistryKey::~CRegistryKey(a2);
    operator delete(a2);
  }
}

```

## disassembly

```asm
0x180007264  test    rdx, rdx
0x180007267  jz      short locret_18000728B
0x180007269  push    rbx
0x18000726a  sub     rsp, 20h
0x18000726e  mov     rcx, rdx; this
0x180007271  mov     rbx, rdx
0x180007274  call    ??1CRegistryKey@@QEAA@XZ; CRegistryKey::~CRegistryKey(void)
0x180007279  mov     edx, 20h ; ' '
0x18000727e  mov     rcx, rbx; Block
0x180007281  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007286  add     rsp, 20h
0x18000728a  pop     rbx
0x18000728b  retn
```
