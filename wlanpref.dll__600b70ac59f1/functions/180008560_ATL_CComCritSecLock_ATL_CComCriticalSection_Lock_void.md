# ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)

- ea: `0x180008560`
- end: `0x18000857e`
- name: `?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ`
- size: `30`
- prototype: ``
- caller_count: `15`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180004aec`
- `0x180004f00`
- `0x180005550`
- `0x180007874`
- `0x180007b3c`
- `0x180009090`
- `0x18000a1c0`
- `0x18000baa0`
- `0x18000dd64`
- `0x18000de44`
- `0x18000df24`
- `0x1800157ec`
- `0x180020030`
- `0x180023fb0`
- `0x1800247f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000856c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000856c`

## pseudocode

```c
__int64 __fastcall ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(__int64 a1)
{
  __int64 result; // rax

  EnterCriticalSection(*(LPCRITICAL_SECTION *)a1);
  result = 0;
  *(_BYTE *)(a1 + 8) = 1;
  return result;
}

```

## disassembly

```asm
0x180008560  push    rbx
0x180008562  sub     rsp, 20h
0x180008566  mov     rbx, rcx
0x180008569  mov     rcx, [rcx]; lpCriticalSection
0x18000856c  call    cs:__imp_EnterCriticalSection
0x180008572  xor     eax, eax
0x180008574  mov     byte ptr [rbx+8], 1
0x180008578  add     rsp, 20h
0x18000857c  pop     rbx
0x18000857d  retn
```
