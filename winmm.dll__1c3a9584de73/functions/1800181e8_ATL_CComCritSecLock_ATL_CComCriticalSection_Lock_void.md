# ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)

- ea: `0x1800181e8`
- end: `0x180018207`
- name: `?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ`
- size: `31`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180016ab4`
- `0x18001795c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800181f4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800181f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(__int64 a1)
{
  EnterCriticalSection(*(LPCRITICAL_SECTION *)a1);
  *(_BYTE *)(a1 + 8) = 1;
  return 0;
}

```

## disassembly

```asm
0x1800181e8  push    rbx
0x1800181ea  sub     rsp, 20h
0x1800181ee  mov     rbx, rcx
0x1800181f1  mov     rcx, [rcx]; lpCriticalSection
0x1800181f4  call    cs:__imp_EnterCriticalSection
0x1800181fa  nop
0x1800181fb  mov     byte ptr [rbx+8], 1
0x1800181ff  xor     eax, eax
0x180018201  add     rsp, 20h
0x180018205  pop     rbx
0x180018206  retn
```
