# ATL::CComClassFactory::~CComClassFactory(void)

- ea: `0x180011f4c`
- end: `0x180011f87`
- name: `??1CComClassFactory@ATL@@QEAA@XZ`
- size: `59`
- prototype: `void __fastcall(ATL::CComClassFactory *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001e7b8`
- `0x18001e7e0`
- `0x18001e8ae`

## callees

- `0x180011f4c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011f7b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011f7b`

## pseudocode

```c
void __fastcall ATL::CComClassFactory::~CComClassFactory(ATL::CComClassFactory *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rcx

  *(_QWORD *)this = &ATL::CComClassFactory::`vftable';
  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  if ( LOBYTE(v1[1].DebugInfo) )
  {
    LOBYTE(v1[1].DebugInfo) = 0;
    DeleteCriticalSection(v1);
  }
}

```

## disassembly

```asm
0x180011f4c  mov     [rsp+arg_0], rcx
0x180011f51  sub     rsp, 28h
0x180011f55  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180011f5c  mov     [rcx], rax
0x180011f5f  lea     rax, [rcx+8]
0x180011f63  mov     [rsp+28h+arg_8], rax
0x180011f68  lea     rcx, [rax+8]; lpCriticalSection
0x180011f6c  mov     [rsp+28h+arg_10], rcx
0x180011f71  cmp     byte ptr [rcx+28h], 0
0x180011f75  jz      short loc_180011F82
0x180011f77  mov     byte ptr [rcx+28h], 0
0x180011f7b  call    cs:__imp_DeleteCriticalSection
0x180011f81  nop
0x180011f82  add     rsp, 28h
0x180011f86  retn
```
