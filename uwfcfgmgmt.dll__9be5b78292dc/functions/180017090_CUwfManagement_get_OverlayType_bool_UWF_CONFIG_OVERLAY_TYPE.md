# CUwfManagement::get_OverlayType(bool,_UWF_CONFIG_OVERLAY_TYPE *)

- ea: `0x180017090`
- end: `0x1800170c5`
- name: `?get_OverlayType@CUwfManagement@@QEAAJ_NPEAW4_UWF_CONFIG_OVERLAY_TYPE@@@Z`
- size: `53`
- prototype: `__int64 __fastcall(CUwfManagement *this, char, enum _UWF_CONFIG_OVERLAY_TYPE *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180018c70`

## callees

- `0x18000afb0`
- `0x180017090`

## pseudocode

```c
__int64 __fastcall CUwfManagement::get_OverlayType(CUwfManagement *this, char a2, enum _UWF_CONFIG_OVERLAY_TYPE *a3)
{
  if ( a3 )
    return CUwfStaticConfiguration::get_OverlayType(
             (CUwfManagement *)((char *)this + (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFD0uLL) + 168),
             a3);
  else
    return 2147500035LL;
}

```

## disassembly

```asm
0x180017090  sub     rsp, 28h
0x180017094  mov     rax, rcx
0x180017097  test    r8, r8
0x18001709a  jnz     short loc_1800170A6
0x18001709c  mov     eax, 80004003h
0x1800170a1  add     rsp, 28h
0x1800170a5  retn
0x1800170a6  neg     dl
0x1800170a8  mov     rdx, r8; enum _UWF_CONFIG_OVERLAY_TYPE *
0x1800170ab  sbb     rcx, rcx
0x1800170ae  add     rax, 0A8h
0x1800170b4  and     rcx, 0FFFFFFFFFFFFFFD0h
0x1800170b8  add     rcx, rax; this
0x1800170bb  call    ?get_OverlayType@CUwfStaticConfiguration@@QEAAJPEAW4_UWF_CONFIG_OVERLAY_TYPE@@@Z; CUwfStaticConfiguration::get_OverlayType(_UWF_CONFIG_OVERLAY_TYPE *)
0x1800170c0  add     rsp, 28h
0x1800170c4  retn
```
