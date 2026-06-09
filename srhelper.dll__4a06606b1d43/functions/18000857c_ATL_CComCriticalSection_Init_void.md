# ATL::CComCriticalSection::Init(void)

- ea: `0x18000857c`
- end: `0x18000859c`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x180001060`
- `0x180001090`
- `0x1800010d0`
- `0x1800081c0`
- `0x180009a6c`
- `0x180009d8c`

## callees

- `0x18000857c`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180008580`
- `KERNEL32!InitializeCriticalSection` at `0x180008580`

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
0x18000857c  sub     rsp, 38h
0x180008580  call    cs:__imp_InitializeCriticalSection
0x180008586  xor     eax, eax
0x180008588  mov     [rsp+38h+var_18], eax
0x18000858c  jmp     short loc_180008597
0x18000858e  mov     eax, 8007000Eh
0x180008593  mov     [rsp+38h+var_18], eax
0x180008597  add     rsp, 38h
0x18000859b  retn
0x180015bf8  push    rbp
0x180015bfa  sub     rsp, 20h
0x180015bfe  mov     rbp, rdx
0x180015c01  mov     rax, [rcx]
0x180015c04  xor     ecx, ecx
0x180015c06  cmp     dword ptr [rax], 0C0000017h
0x180015c0c  setz    cl
0x180015c0f  mov     eax, ecx
0x180015c11  add     rsp, 20h
0x180015c15  pop     rbp
0x180015c16  retn
```
