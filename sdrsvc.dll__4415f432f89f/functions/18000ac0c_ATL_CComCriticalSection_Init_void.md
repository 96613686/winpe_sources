# ATL::CComCriticalSection::Init(void)

- ea: `0x18000ac0c`
- end: `0x18000ac2c`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001240`
- `0x180001370`
- `0x1800013a0`
- `0x1800013e0`
- `0x18000a590`
- `0x18000a6a0`
- `0x18000d7ec`
- `0x18000db0c`

## callees

- `0x18000ac0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000ac10`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000ac10`

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
0x18000ac0c  sub     rsp, 38h
0x18000ac10  call    cs:__imp_InitializeCriticalSection
0x18000ac16  xor     eax, eax
0x18000ac18  mov     [rsp+38h+var_18], eax
0x18000ac1c  jmp     short loc_18000AC27
0x18000ac1e  mov     eax, 8007000Eh
0x18000ac23  mov     [rsp+38h+var_18], eax
0x18000ac27  add     rsp, 38h
0x18000ac2b  retn
0x180021b4a  push    rbp
0x180021b4c  sub     rsp, 20h
0x180021b50  mov     rbp, rdx
0x180021b53  mov     rax, [rcx]
0x180021b56  xor     ecx, ecx
0x180021b58  cmp     dword ptr [rax], 0C0000017h
0x180021b5e  setz    cl
0x180021b61  mov     eax, ecx
0x180021b63  add     rsp, 20h
0x180021b67  pop     rbp
0x180021b68  retn
```
