# CFileDescriptorEntryArray::~CFileDescriptorEntryArray(void)

- ea: `0x1800230d4`
- end: `0x1800230ff`
- name: `??1CFileDescriptorEntryArray@@AEAA@XZ`
- size: `43`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180023738`

## callees

- `0x1800234d4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800230e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800230e5`

## pseudocode

```c
void __fastcall CFileDescriptorEntryArray::~CFileDescriptorEntryArray(LPVOID *this)
{
  CSxRefArray<CFileDescriptorEntryArray,CFileDescriptorEntry>::DeleteAll();
  CoTaskMemFree(*this);
  *this = 0;
  *((_DWORD *)this + 3) = 0;
}

```

## disassembly

```asm
0x1800230d4  push    rbx
0x1800230d6  sub     rsp, 20h
0x1800230da  mov     rbx, rcx
0x1800230dd  call    ?DeleteAll@?$CSxRefArray@VCFileDescriptorEntryArray@@UCFileDescriptorEntry@@@@QEAAXXZ; CSxRefArray<CFileDescriptorEntryArray,CFileDescriptorEntry>::DeleteAll(void)
0x1800230e2  mov     rcx, [rbx]; pv
0x1800230e5  call    cs:__imp_CoTaskMemFree
0x1800230eb  mov     qword ptr [rbx], 0
0x1800230f2  mov     dword ptr [rbx+0Ch], 0
0x1800230f9  add     rsp, 20h
0x1800230fd  pop     rbx
0x1800230fe  retn
```
