# ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)

- ea: `0x180004550`
- end: `0x180004575`
- name: `?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ`
- size: `37`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000367c`
- `0x180006b88`
- `0x180007044`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000455c`
- `KERNEL32!EnterCriticalSection` at `0x18000455c`

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
0x180004550  push    rbx
0x180004552  sub     rsp, 20h
0x180004556  mov     rbx, rcx
0x180004559  mov     rcx, [rcx]; lpCriticalSection
0x18000455c  call    cs:__imp_EnterCriticalSection
0x180004563  nop     dword ptr [rax+rax+00h]
0x180004568  xor     eax, eax
0x18000456a  mov     byte ptr [rbx+8], 1
0x18000456e  add     rsp, 20h
0x180004572  pop     rbx
0x180004573  retn
```
