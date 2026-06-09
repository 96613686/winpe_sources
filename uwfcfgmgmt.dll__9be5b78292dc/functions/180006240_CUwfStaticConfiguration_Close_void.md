# CUwfStaticConfiguration::Close(void)

- ea: `0x180006240`
- end: `0x180006273`
- name: `?Close@CUwfStaticConfiguration@@QEAAXXZ`
- size: `51`
- prototype: `void __fastcall(HKEY *this)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180005a90`
- `0x180006200`
- `0x18000866c`
- `0x180008b3c`
- `0x180017ac4`

## callees

- `0x180006240`
- `0x18000d5f0`

## pseudocode

```c
void __fastcall CUwfStaticConfiguration::Close(HKEY *this)
{
  HKEY v2; // rcx

  CUwfRegKey::Close(this + 2);
  CUwfRegKey::Close(this + 3);
  v2 = this[5];
  if ( v2 )
    CUwfRegKey::Close((HKEY *)v2 + 2);
}

```

## disassembly

```asm
0x180006240  push    rbx
0x180006242  sub     rsp, 20h
0x180006246  mov     rbx, rcx
0x180006249  add     rcx, 10h; this
0x18000624d  call    ?Close@CUwfRegKey@@QEAAJXZ; CUwfRegKey::Close(void)
0x180006252  lea     rcx, [rbx+18h]; this
0x180006256  call    ?Close@CUwfRegKey@@QEAAJXZ; CUwfRegKey::Close(void)
0x18000625b  mov     rcx, [rbx+28h]
0x18000625f  test    rcx, rcx
0x180006262  jz      short loc_18000626D
0x180006264  add     rcx, 10h; this
0x180006268  call    ?Close@CUwfRegKey@@QEAAJXZ; CUwfRegKey::Close(void)
0x18000626d  add     rsp, 20h
0x180006271  pop     rbx
0x180006272  retn
```
