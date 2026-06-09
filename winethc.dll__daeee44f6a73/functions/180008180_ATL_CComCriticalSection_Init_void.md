# ATL::CComCriticalSection::Init(void)

- ea: `0x180008180`
- end: `0x1800081a7`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `39`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800010f0`
- `0x180001190`
- `0x1800011d0`
- `0x180001280`
- `0x18000448c`
- `0x1800045b0`
- `0x18000ce24`

## callees

- `0x180008180`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180008184`
- `KERNEL32!InitializeCriticalSection` at `0x180008184`

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
0x180008180  sub     rsp, 38h
0x180008184  call    cs:__imp_InitializeCriticalSection
0x18000818b  nop     dword ptr [rax+rax+00h]
0x180008190  xor     eax, eax
0x180008192  mov     [rsp+38h+var_18], eax
0x180008196  jmp     short loc_1800081A1
0x180008198  mov     eax, 8007000Eh
0x18000819d  mov     [rsp+38h+var_18], eax
0x1800081a1  add     rsp, 38h
0x1800081a5  retn
0x180013196  push    rbp
0x180013198  sub     rsp, 20h
0x18001319c  mov     rbp, rdx
0x18001319f  mov     rax, [rcx]
0x1800131a2  xor     ecx, ecx
0x1800131a4  cmp     dword ptr [rax], 0C0000017h
0x1800131aa  setz    cl
0x1800131ad  mov     eax, ecx
0x1800131af  add     rsp, 20h
0x1800131b3  pop     rbp
0x1800131b4  retn
```
