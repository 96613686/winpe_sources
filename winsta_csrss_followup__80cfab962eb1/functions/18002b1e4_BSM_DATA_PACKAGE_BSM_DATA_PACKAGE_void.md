# BSM_DATA_PACKAGE::~BSM_DATA_PACKAGE(void)

- ea: `0x18002b1e4`
- end: `0x18002b21f`
- name: `??1BSM_DATA_PACKAGE@@QEAA@XZ`
- size: `59`
- prototype: `void __fastcall(BSM_DATA_PACKAGE *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002b228`

## callees

- `0x18002b1e4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b20c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b20c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002b1f7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002b1f7`

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
0x18002b1e4  push    rbx
0x18002b1e6  sub     rsp, 20h
0x18002b1ea  cmp     dword ptr [rcx+40h], 0
0x18002b1ee  mov     rbx, rcx
0x18002b1f1  jz      short loc_18002B203
0x18002b1f3  add     rcx, 58h ; 'X'; lpCriticalSection
0x18002b1f7  call    cs:__imp_DeleteCriticalSection
0x18002b1fe  nop     dword ptr [rax+rax+00h]
0x18002b203  mov     rcx, [rbx+48h]; hMem
0x18002b207  test    rcx, rcx
0x18002b20a  jz      short loc_18002B218
0x18002b20c  call    cs:__imp_LocalFree
0x18002b213  nop     dword ptr [rax+rax+00h]
0x18002b218  add     rsp, 20h
0x18002b21c  pop     rbx
0x18002b21d  retn
```
