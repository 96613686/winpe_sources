# ATL::CComCriticalSection::Init(void)

- ea: `0x180003e5c`
- end: `0x180003e7c`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x180001060`
- `0x180001090`
- `0x1800010d0`
- `0x1800039a0`
- `0x180003a90`
- `0x180003b90`
- `0x1800054fc`
- `0x18000581c`

## callees

- `0x180003e5c`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180003e60`
- `KERNEL32!InitializeCriticalSection` at `0x180003e60`

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
0x180003e5c  sub     rsp, 38h
0x180003e60  call    cs:__imp_InitializeCriticalSection
0x180003e66  xor     eax, eax
0x180003e68  mov     [rsp+38h+var_18], eax
0x180003e6c  jmp     short loc_180003E77
0x180003e6e  mov     eax, 8007000Eh
0x180003e73  mov     [rsp+38h+var_18], eax
0x180003e77  add     rsp, 38h
0x180003e7b  retn
0x18001c356  push    rbp
0x18001c358  sub     rsp, 20h
0x18001c35c  mov     rbp, rdx
0x18001c35f  mov     rax, [rcx]
0x18001c362  xor     ecx, ecx
0x18001c364  cmp     dword ptr [rax], 0C0000017h
0x18001c36a  setz    cl
0x18001c36d  mov     eax, ecx
0x18001c36f  add     rsp, 20h
0x18001c373  pop     rbp
0x18001c374  retn
```
