# ATL::CComCriticalSection::Init(void)

- ea: `0x180026a50`
- end: `0x180026a77`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `39`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001110`
- `0x180026828`

## callees

- `0x180026a50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180026a54`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180026a54`

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
0x180026a50  sub     rsp, 38h
0x180026a54  call    cs:__imp_InitializeCriticalSection
0x180026a5b  nop     dword ptr [rax+rax+00h]
0x180026a60  xor     eax, eax
0x180026a62  mov     [rsp+38h+var_18], eax
0x180026a66  jmp     short loc_180026A71
0x180026a68  mov     eax, 8007000Eh
0x180026a6d  mov     [rsp+38h+var_18], eax
0x180026a71  add     rsp, 38h
0x180026a75  retn
0x180029853  push    rbp
0x180029855  sub     rsp, 20h
0x180029859  mov     rbp, rdx
0x18002985c  mov     rax, [rcx]
0x18002985f  xor     ecx, ecx
0x180029861  cmp     dword ptr [rax], 0C0000017h
0x180029867  setz    cl
0x18002986a  mov     eax, ecx
0x18002986c  add     rsp, 20h
0x180029870  pop     rbp
0x180029871  retn
```
