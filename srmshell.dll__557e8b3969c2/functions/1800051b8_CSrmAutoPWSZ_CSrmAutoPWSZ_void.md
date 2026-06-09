# CSrmAutoPWSZ::~CSrmAutoPWSZ(void)

- ea: `0x1800051b8`
- end: `0x1800051d7`
- name: `??1CSrmAutoPWSZ@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `11`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018f68`
- `0x1800191ec`
- `0x18001cd46`
- `0x18001dc4a`
- `0x18001eb05`
- `0x18001ebcf`
- `0x18001ed44`
- `0x18001eefd`
- `0x18001ef5f`
- `0x18001ef83`
- `0x18001f05b`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800051c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800051c4`

## pseudocode

```c
void __fastcall CSrmAutoPWSZ::~CSrmAutoPWSZ(LPVOID *this)
{
  CoTaskMemFree(*this);
  *this = 0;
}

```

## disassembly

```asm
0x1800051b8  push    rbx
0x1800051ba  sub     rsp, 20h
0x1800051be  mov     rbx, rcx
0x1800051c1  mov     rcx, [rcx]; pv
0x1800051c4  call    cs:__imp_CoTaskMemFree
0x1800051ca  mov     qword ptr [rbx], 0
0x1800051d1  add     rsp, 20h
0x1800051d5  pop     rbx
0x1800051d6  retn
```
