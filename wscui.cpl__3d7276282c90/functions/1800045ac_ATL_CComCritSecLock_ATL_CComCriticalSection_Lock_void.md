# ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)

- ea: `0x1800045ac`
- end: `0x1800045ca`
- name: `?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ`
- size: `30`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800043e4`
- `0x180007d24`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800045b8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800045b8`

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
0x1800045ac  push    rbx
0x1800045ae  sub     rsp, 20h
0x1800045b2  mov     rbx, rcx
0x1800045b5  mov     rcx, [rcx]; lpCriticalSection
0x1800045b8  call    cs:__imp_EnterCriticalSection
0x1800045be  xor     eax, eax
0x1800045c0  mov     byte ptr [rbx+8], 1
0x1800045c4  add     rsp, 20h
0x1800045c8  pop     rbx
0x1800045c9  retn
```
