# CTSAutoLock::~CTSAutoLock(void)

- ea: `0x180002c94`
- end: `0x180002cc3`
- name: `??1CTSAutoLock@@QEAA@XZ`
- size: `47`
- prototype: `void __fastcall(CTSAutoLock *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b2d9`
- `0x18000b2eb`
- `0x18000b2fd`

## callees

- `0x180002c94`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180002cb7`
- `KERNEL32!LeaveCriticalSection` at `0x180002cb7`

## pseudocode

```c
void __fastcall CTSAutoLock::~CTSAutoLock(CTSAutoLock *this)
{
  __int64 v1; // rax

  v1 = *(_QWORD *)this;
  if ( *(_QWORD *)this && *(_DWORD *)(v1 + 8) )
  {
    if ( *(_QWORD *)v1 )
      LeaveCriticalSection(*(LPCRITICAL_SECTION *)v1);
  }
}

```

## disassembly

```asm
0x180002c94  sub     rsp, 38h
0x180002c98  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180002ca1  mov     rax, [rcx]
0x180002ca4  test    rax, rax
0x180002ca7  jz      short loc_180002CBE
0x180002ca9  cmp     dword ptr [rax+8], 0
0x180002cad  jz      short loc_180002CBE
0x180002caf  mov     rcx, [rax]; lpCriticalSection
0x180002cb2  test    rcx, rcx
0x180002cb5  jz      short loc_180002CBE
0x180002cb7  call    cs:__imp_LeaveCriticalSection
0x180002cbd  nop
0x180002cbe  add     rsp, 38h
0x180002cc2  retn
```
