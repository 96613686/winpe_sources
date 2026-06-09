# CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>(CComAutoCriticalSectionWTry &,bool)

- ea: `0x18000505c`
- end: `0x180005082`
- name: `??0?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@AEAVCComAutoCriticalSectionWTry@@_N@Z`
- size: `38`
- prototype: `__int64 __fastcall(__int64, struct _RTL_CRITICAL_SECTION *)`
- caller_count: `11`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180006410`
- `0x180007b00`
- `0x18000a26c`
- `0x18000a3e8`
- `0x18000a998`
- `0x18000ab84`
- `0x18000aec0`
- `0x18000b5b4`
- `0x18000b700`
- `0x18000bbf8`
- `0x18000bc8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000506f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000506f`

## pseudocode

```c
__int64 __fastcall CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>(
        __int64 a1,
        struct _RTL_CRITICAL_SECTION *a2)
{
  __int64 result; // rax

  *(_QWORD *)a1 = a2;
  *(_BYTE *)(a1 + 8) = 0;
  EnterCriticalSection(a2);
  result = a1;
  *(_BYTE *)(a1 + 8) = 1;
  return result;
}

```

## disassembly

```asm
0x18000505c  push    rbx
0x18000505e  sub     rsp, 20h
0x180005062  mov     rbx, rcx
0x180005065  mov     [rcx], rdx
0x180005068  mov     byte ptr [rcx+8], 0
0x18000506c  mov     rcx, rdx; lpCriticalSection
0x18000506f  call    cs:__imp_EnterCriticalSection
0x180005075  mov     rax, rbx
0x180005078  mov     byte ptr [rbx+8], 1
0x18000507c  add     rsp, 20h
0x180005080  pop     rbx
0x180005081  retn
```
