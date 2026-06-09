# ATL::CComCriticalSection::Init(void)

- ea: `0x180010fdc`
- end: `0x180010ffc`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800010a0`
- `0x1800010f0`
- `0x180001120`
- `0x180001160`
- `0x180010d30`

## callees

- `0x180010fdc`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180010fe0`
- `KERNEL32!InitializeCriticalSection` at `0x180010fe0`

## pseudocode

```c
__int64 __fastcall ATL::CComCriticalSection::Init(struct _RTL_CRITICAL_SECTION *this)
{
  InitializeCriticalSection(this);
  return 0;
}

```

## disassembly

```asm
0x180010fdc  sub     rsp, 38h
0x180010fe0  call    cs:__imp_InitializeCriticalSection
0x180010fe6  xor     eax, eax
0x180010fe8  mov     [rsp+38h+var_18], eax
0x180010fec  jmp     short loc_180010FF7
0x180010fee  mov     eax, 8007000Eh
0x180010ff3  mov     [rsp+38h+var_18], eax
0x180010ff7  add     rsp, 38h
0x180010ffb  retn
0x18001467d  push    rbp
0x18001467f  sub     rsp, 20h
0x180014683  mov     rbp, rdx
0x180014686  mov     rax, [rcx]
0x180014689  xor     ecx, ecx
0x18001468b  cmp     dword ptr [rax], 0C0000017h
0x180014691  setz    cl
0x180014694  mov     eax, ecx
0x180014696  add     rsp, 20h
0x18001469a  pop     rbp
0x18001469b  retn
```
