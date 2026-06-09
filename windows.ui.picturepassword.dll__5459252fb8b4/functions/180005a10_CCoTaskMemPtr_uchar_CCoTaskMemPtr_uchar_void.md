# CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)

- ea: `0x180005a10`
- end: `0x180005a24`
- name: `??1?$CCoTaskMemPtr@E@@QEAA@XZ`
- size: `20`
- prototype: `void __fastcall(void **)`
- caller_count: `13`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006480`
- `0x180006f80`
- `0x1800071c0`
- `0x18000b318`
- `0x18000c438`
- `0x18000c6d4`
- `0x18000e204`
- `0x18000f670`
- `0x1800104d0`
- `0x180012d7c`
- `0x18001d188`
- `0x18001d3f0`
- `0x18001d5ec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005a1d`

## pseudocode

```c
void __fastcall CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(void **a1)
{
  void *v2; // rcx

  v2 = *a1;
  *a1 = 0;
  CoTaskMemFree(v2);
}

```

## disassembly

```asm
0x180005a10  mov     rax, rcx
0x180005a13  mov     rcx, [rcx]
0x180005a16  mov     qword ptr [rax], 0
0x180005a1d  jmp     cs:__imp_CoTaskMemFree
```
