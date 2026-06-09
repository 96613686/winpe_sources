# ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)

- ea: `0x18000597c`
- end: `0x1800059c0`
- name: `??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z`
- size: `68`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800010f0`
- `0x180001660`

## callees

- `0x180002594`
- `0x18000597c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800059a4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800059a4`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(_DWORD *a1)
{
  struct _RTL_CRITICAL_SECTION *v2; // rcx

  a1[2] = -1073741823;
  *(_QWORD *)a1 = &ATL::CComClassFactory::`vftable';
  v2 = (struct _RTL_CRITICAL_SECTION *)(a1 + 4);
  if ( LOBYTE(v2[1].DebugInfo) )
  {
    LOBYTE(v2[1].DebugInfo) = 0;
    DeleteCriticalSection(v2);
  }
  operator delete(a1, 0x48u);
  return a1;
}

```

## disassembly

```asm
0x18000597c  push    rbx
0x18000597e  sub     rsp, 20h
0x180005982  mov     dword ptr [rcx+8], 0C0000001h
0x180005989  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180005990  mov     [rcx], rax
0x180005993  mov     rbx, rcx
0x180005996  add     rcx, 10h; lpCriticalSection
0x18000599a  cmp     byte ptr [rcx+28h], 0
0x18000599e  jz      short loc_1800059AA
0x1800059a0  mov     byte ptr [rcx+28h], 0
0x1800059a4  call    cs:__imp_DeleteCriticalSection
0x1800059aa  mov     edx, 48h ; 'H'; unsigned __int64
0x1800059af  mov     rcx, rbx; void *
0x1800059b2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800059b7  mov     rax, rbx
0x1800059ba  add     rsp, 20h
0x1800059be  pop     rbx
0x1800059bf  retn
```
