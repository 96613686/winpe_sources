# CTempFile_Global::~CTempFile_Global(void)

- ea: `0x180029c54`
- end: `0x180029c7a`
- name: `??1CTempFile_Global@@QEAA@XZ`
- size: `38`
- prototype: `void __fastcall(CTempFile_Global *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002a7a0`

## callees

- `0x180029c54`

## import_xrefs

- `ADVAPI32!CryptReleaseContext` at `0x180029c67`
- `ADVAPI32!CryptReleaseContext` at `0x180029c67`

## pseudocode

```c
void __fastcall CTempFile_Global::~CTempFile_Global(HCRYPTPROV *this)
{
  HCRYPTPROV v2; // rcx

  v2 = *this;
  if ( v2 )
    CryptReleaseContext(v2, 0);
  *this = 0;
}

```

## disassembly

```asm
0x180029c54  push    rbx
0x180029c56  sub     rsp, 20h
0x180029c5a  mov     rbx, rcx
0x180029c5d  mov     rcx, [rcx]; hProv
0x180029c60  test    rcx, rcx
0x180029c63  jz      short loc_180029C6D
0x180029c65  xor     edx, edx; dwFlags
0x180029c67  call    cs:__imp_CryptReleaseContext
0x180029c6d  mov     qword ptr [rbx], 0
0x180029c74  add     rsp, 20h
0x180029c78  pop     rbx
0x180029c79  retn
```
