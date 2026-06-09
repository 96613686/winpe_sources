# CWdsSimpleDeviceQueryResult::~CWdsSimpleDeviceQueryResult(void)

- ea: `0x180006ea8`
- end: `0x180006eeb`
- name: `??1CWdsSimpleDeviceQueryResult@@QEAA@XZ`
- size: `67`
- prototype: `void __fastcall(CWdsSimpleDeviceQueryResult *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006f00`

## callees

- `0x1800058c0`
- `0x180006ea8`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180006eb5`
- `KERNEL32!DeleteCriticalSection` at `0x180006ed8`
- `KERNEL32!DeleteCriticalSection` at `0x180006eb5`
- `KERNEL32!DeleteCriticalSection` at `0x180006ed8`

## pseudocode

```c
void __fastcall CWdsSimpleDeviceQueryResult::~CWdsSimpleDeviceQueryResult(CWdsSimpleDeviceQueryResult *this)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  CDynArray<unsigned short *,CDeallocateString>::Clear((char *)this + 64);
  if ( *((_BYTE *)this + 56) )
  {
    *((_BYTE *)this + 56) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  }
}

```

## disassembly

```asm
0x180006ea8  push    rbx
0x180006eaa  sub     rsp, 20h
0x180006eae  mov     rbx, rcx
0x180006eb1  add     rcx, 68h ; 'h'; lpCriticalSection
0x180006eb5  call    cs:__imp_DeleteCriticalSection
0x180006ebc  nop     dword ptr [rax+rax+00h]
0x180006ec1  lea     rcx, [rbx+40h]
0x180006ec5  call    ?Clear@?$CDynArray@PEAGVCDeallocateString@@@@QEAAXXZ; CDynArray<ushort *,CDeallocateString>::Clear(void)
0x180006eca  lea     rcx, [rbx+10h]; lpCriticalSection
0x180006ece  cmp     byte ptr [rcx+28h], 0
0x180006ed2  jz      short loc_180006EE4
0x180006ed4  mov     byte ptr [rcx+28h], 0
0x180006ed8  call    cs:__imp_DeleteCriticalSection
0x180006edf  nop     dword ptr [rax+rax+00h]
0x180006ee4  add     rsp, 20h
0x180006ee8  pop     rbx
0x180006ee9  retn
```
