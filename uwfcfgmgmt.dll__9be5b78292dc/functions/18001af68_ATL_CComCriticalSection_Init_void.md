# ATL::CComCriticalSection::Init(void)

- ea: `0x18001af68`
- end: `0x18001af88`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001320`
- `0x180001350`

## callees

- `0x18001af68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001af6c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001af6c`

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
0x18001af68  sub     rsp, 38h
0x18001af6c  call    cs:__imp_InitializeCriticalSection
0x18001af72  xor     eax, eax
0x18001af74  mov     [rsp+38h+var_18], eax
0x18001af78  jmp     short loc_18001AF83
0x18001af7a  mov     eax, 8007000Eh
0x18001af7f  mov     [rsp+38h+var_18], eax
0x18001af83  add     rsp, 38h
0x18001af87  retn
0x18001b486  push    rbp
0x18001b488  sub     rsp, 20h
0x18001b48c  mov     rbp, rdx
0x18001b48f  mov     rax, [rcx]
0x18001b492  xor     ecx, ecx
0x18001b494  cmp     dword ptr [rax], 0C0000017h
0x18001b49a  setz    cl
0x18001b49d  mov     eax, ecx
0x18001b49f  add     rsp, 20h
0x18001b4a3  pop     rbp
0x18001b4a4  retn
```
