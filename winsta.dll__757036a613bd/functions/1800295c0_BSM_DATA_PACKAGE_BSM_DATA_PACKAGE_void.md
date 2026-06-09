# BSM_DATA_PACKAGE::~BSM_DATA_PACKAGE(void)

- ea: `0x1800295c0`
- end: `0x1800295ee`
- name: `??1BSM_DATA_PACKAGE@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(BSM_DATA_PACKAGE *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800295f4`

## callees

- `0x1800295c0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800295e2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800295e2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800295d3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800295d3`

## pseudocode

```c
void __fastcall BSM_DATA_PACKAGE::~BSM_DATA_PACKAGE(BSM_DATA_PACKAGE *this)
{
  void *v2; // rcx

  if ( *((_DWORD *)this + 16) )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v2 = (void *)*((_QWORD *)this + 9);
  if ( v2 )
    LocalFree(v2);
}

```

## disassembly

```asm
0x1800295c0  push    rbx
0x1800295c2  sub     rsp, 20h
0x1800295c6  cmp     dword ptr [rcx+40h], 0
0x1800295ca  mov     rbx, rcx
0x1800295cd  jz      short loc_1800295D9
0x1800295cf  add     rcx, 58h ; 'X'; lpCriticalSection
0x1800295d3  call    cs:__imp_DeleteCriticalSection
0x1800295d9  mov     rcx, [rbx+48h]; hMem
0x1800295dd  test    rcx, rcx
0x1800295e0  jz      short loc_1800295E8
0x1800295e2  call    cs:__imp_LocalFree
0x1800295e8  add     rsp, 20h
0x1800295ec  pop     rbx
0x1800295ed  retn
```
