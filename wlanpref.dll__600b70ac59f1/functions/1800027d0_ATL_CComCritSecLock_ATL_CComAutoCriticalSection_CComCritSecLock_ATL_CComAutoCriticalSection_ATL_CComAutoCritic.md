# ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)

- ea: `0x1800027d0`
- end: `0x1800027f6`
- name: `??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z`
- size: `38`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `41`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000347c`
- `0x180003620`
- `0x18000ce08`
- `0x180011ef0`
- `0x180011fe0`
- `0x180012380`
- `0x180012610`
- `0x180013410`
- `0x1800134f4`
- `0x180013ac8`
- `0x180013bb4`
- `0x180013fd4`
- `0x1800140c0`
- `0x1800273d0`
- `0x18002749c`
- `0x180027558`
- `0x180027594`
- `0x180029fc0`
- `0x18002a260`
- `0x18002a2b0`
- `0x18002a2ec`
- `0x18002a340`
- `0x18002a410`
- `0x18002a630`
- `0x18002a690`
- `0x18002a6d0`
- `0x18002a710`
- `0x18002a870`
- `0x18002a980`
- `0x18002aaf0`
- `0x18002ab60`
- `0x18002aba0`
- `0x18002af00`
- `0x18002b320`
- `0x18002b5dc`
- `0x18002b8c0`
- `0x18002bb40`
- `0x18002c010`
- `0x18002c0d0`
- `0x18002c1d0`
- `0x18002c7c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800027e3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800027e3`

## pseudocode

```c
__int64 __fastcall ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
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
0x1800027d0  push    rbx
0x1800027d2  sub     rsp, 20h
0x1800027d6  mov     rbx, rcx
0x1800027d9  mov     [rcx], rdx
0x1800027dc  mov     byte ptr [rcx+8], 0
0x1800027e0  mov     rcx, rdx; lpCriticalSection
0x1800027e3  call    cs:__imp_EnterCriticalSection
0x1800027e9  mov     rax, rbx
0x1800027ec  mov     byte ptr [rbx+8], 1
0x1800027f0  add     rsp, 20h
0x1800027f4  pop     rbx
0x1800027f5  retn
```
