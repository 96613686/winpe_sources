# Microsoft::Windows::Performance::CEventSourceHandler::CAutoDeleteFile::~CAutoDeleteFile(void)

- ea: `0x180024190`
- end: `0x1800241b3`
- name: `??1CAutoDeleteFile@CEventSourceHandler@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `35`
- prototype: `void __fastcall(Microsoft::Windows::Performance::CEventSourceHandler::CAutoDeleteFile *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180033219`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x1800241a0`
- `KERNEL32!DeleteFileW` at `0x1800241a0`

## pseudocode

```c
void __fastcall Microsoft::Windows::Performance::CEventSourceHandler::CAutoDeleteFile::~CAutoDeleteFile(LPCWSTR *this)
{
  DeleteFileW(*this);
}

```

## disassembly

```asm
0x180024190  sub     rsp, 38h
0x180024194  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18002419d  mov     rcx, [rcx]; lpFileName
0x1800241a0  call    cs:__imp_DeleteFileW
0x1800241a7  nop     dword ptr [rax+rax+00h]
0x1800241ac  nop
0x1800241ad  add     rsp, 38h
0x1800241b1  retn
```
