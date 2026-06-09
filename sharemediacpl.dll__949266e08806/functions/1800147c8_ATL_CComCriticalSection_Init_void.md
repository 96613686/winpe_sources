# ATL::CComCriticalSection::Init(void)

- ea: `0x1800147c8`
- end: `0x1800147e8`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800016e0`
- `0x1800154d4`

## callees

- `0x1800147c8`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x1800147cc`
- `KERNEL32!InitializeCriticalSection` at `0x1800147cc`

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
0x1800147c8  sub     rsp, 38h
0x1800147cc  call    cs:__imp_InitializeCriticalSection
0x1800147d2  xor     eax, eax
0x1800147d4  mov     [rsp+38h+var_18], eax
0x1800147d8  jmp     short loc_1800147E3
0x1800147da  mov     eax, 8007000Eh
0x1800147df  mov     [rsp+38h+var_18], eax
0x1800147e3  add     rsp, 38h
0x1800147e7  retn
0x18001d406  push    rbp
0x18001d408  sub     rsp, 20h
0x18001d40c  mov     rbp, rdx
0x18001d40f  mov     rax, [rcx]
0x18001d412  xor     ecx, ecx
0x18001d414  cmp     dword ptr [rax], 0C0000017h
0x18001d41a  setz    cl
0x18001d41d  mov     eax, ecx
0x18001d41f  add     rsp, 20h
0x18001d423  pop     rbp
0x18001d424  retn
```
