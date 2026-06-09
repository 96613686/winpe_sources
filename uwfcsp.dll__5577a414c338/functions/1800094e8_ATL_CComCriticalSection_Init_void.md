# ATL::CComCriticalSection::Init(void)

- ea: `0x1800094e8`
- end: `0x180009508`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002ba0`
- `0x180002bf0`
- `0x180002c20`
- `0x180008dcc`
- `0x18000bb3c`
- `0x18000be5c`
- `0x18000d1bc`
- `0x18000e8d4`

## callees

- `0x1800094e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800094ec`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800094ec`

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
0x1800094e8  sub     rsp, 38h
0x1800094ec  call    cs:__imp_InitializeCriticalSection
0x1800094f2  xor     eax, eax
0x1800094f4  mov     [rsp+38h+var_18], eax
0x1800094f8  jmp     short loc_180009503
0x1800094fa  mov     eax, 8007000Eh
0x1800094ff  mov     [rsp+38h+var_18], eax
0x180009503  add     rsp, 38h
0x180009507  retn
0x18001a676  push    rbp
0x18001a678  sub     rsp, 20h
0x18001a67c  mov     rbp, rdx
0x18001a67f  mov     rax, [rcx]
0x18001a682  xor     ecx, ecx
0x18001a684  cmp     dword ptr [rax], 0C0000017h
0x18001a68a  setz    cl
0x18001a68d  mov     eax, ecx
0x18001a68f  add     rsp, 20h
0x18001a693  pop     rbp
0x18001a694  retn
```
