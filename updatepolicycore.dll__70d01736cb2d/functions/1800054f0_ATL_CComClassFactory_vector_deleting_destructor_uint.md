# ATL::CComClassFactory::`vector deleting destructor'(uint)

- ea: `0x1800054f0`
- end: `0x18000553e`
- name: `??_ECComClassFactory@ATL@@UEAAPEAXI@Z`
- size: `78`
- prototype: `ATL::CComClassFactory *__fastcall(ATL::CComClassFactory *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800054f0`
- `0x18003002c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005517`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005517`

## pseudocode

```c
ATL::CComClassFactory *__fastcall ATL::CComClassFactory::`vector deleting destructor'(
        ATL::CComClassFactory *this,
        char a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rcx

  *(_QWORD *)this = &ATL::CComClassFactory::`vftable';
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  if ( LOBYTE(v4[1].DebugInfo) )
  {
    LOBYTE(v4[1].DebugInfo) = 0;
    DeleteCriticalSection(v4);
  }
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800054f0  mov     [rsp+arg_0], rbx
0x1800054f5  push    rdi
0x1800054f6  sub     rsp, 20h
0x1800054fa  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180005501  mov     rbx, rcx
0x180005504  mov     [rcx], rax
0x180005507  mov     edi, edx
0x180005509  add     rcx, 10h; lpCriticalSection
0x18000550d  cmp     byte ptr [rcx+28h], 0
0x180005511  jz      short loc_18000551D
0x180005513  mov     byte ptr [rcx+28h], 0
0x180005517  call    cs:__imp_DeleteCriticalSection
0x18000551d  test    dil, 1
0x180005521  jz      short loc_180005530
0x180005523  mov     edx, 48h ; 'H'
0x180005528  mov     rcx, rbx; Block
0x18000552b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005530  mov     rax, rbx
0x180005533  mov     rbx, [rsp+28h+arg_0]
0x180005538  add     rsp, 20h
0x18000553c  pop     rdi
0x18000553d  retn
```
