# ATL::CComCriticalSection::Init(void)

- ea: `0x14000380c`
- end: `0x14000382c`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001010`
- `0x140001060`
- `0x1400010a0`
- `0x1400010d0`
- `0x140003440`
- `0x140003540`
- `0x14000550c`
- `0x140005834`

## callees

- `0x14000380c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x140003810`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x140003810`

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
0x14000380c  sub     rsp, 38h
0x140003810  call    cs:__imp_InitializeCriticalSection
0x140003816  xor     eax, eax
0x140003818  mov     [rsp+38h+var_18], eax
0x14000381c  jmp     short loc_140003827
0x14000381e  mov     eax, 8007000Eh
0x140003823  mov     [rsp+38h+var_18], eax
0x140003827  add     rsp, 38h
0x14000382b  retn
0x14000674e  push    rbp
0x140006750  sub     rsp, 20h
0x140006754  mov     rbp, rdx
0x140006757  mov     rax, [rcx]
0x14000675a  xor     ecx, ecx
0x14000675c  cmp     dword ptr [rax], 0C0000017h
0x140006762  setz    cl
0x140006765  mov     eax, ecx
0x140006767  add     rsp, 20h
0x14000676b  pop     rbp
0x14000676c  retn
```
