# ATL::CComCriticalSection::Init(void)

- ea: `0x180006f08`
- end: `0x180006f28`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180006e20`
- `0x180006e80`

## callees

- `0x180006f08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180006f0c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180006f0c`

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
0x180006f08  sub     rsp, 38h
0x180006f0c  call    cs:__imp_InitializeCriticalSection
0x180006f12  xor     eax, eax
0x180006f14  mov     [rsp+38h+var_18], eax
0x180006f18  jmp     short loc_180006F23
0x180006f1a  mov     eax, 8007000Eh
0x180006f1f  mov     [rsp+38h+var_18], eax
0x180006f23  add     rsp, 38h
0x180006f27  retn
0x18001a9cf  push    rbp
0x18001a9d1  sub     rsp, 20h
0x18001a9d5  mov     rbp, rdx
0x18001a9d8  mov     rax, [rcx]
0x18001a9db  xor     ecx, ecx
0x18001a9dd  cmp     dword ptr [rax], 0C0000017h
0x18001a9e3  setz    cl
0x18001a9e6  mov     eax, ecx
0x18001a9e8  add     rsp, 20h
0x18001a9ec  pop     rbp
0x18001a9ed  retn
```
