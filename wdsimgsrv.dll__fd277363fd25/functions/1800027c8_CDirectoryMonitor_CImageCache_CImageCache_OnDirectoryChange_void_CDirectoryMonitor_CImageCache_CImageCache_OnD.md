# CDirectoryMonitor<CImageCache,&CImageCache::OnDirectoryChange(void)>::~CDirectoryMonitor<CImageCache,&CImageCache::OnDirectoryChange(void)>(void)

- ea: `0x1800027c8`
- end: `0x1800027f3`
- name: `??1?$CDirectoryMonitor@VCImageCache@@$1?OnDirectoryChange@1@QEAAKXZ@@QEAA@XZ`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000af80`

## callees

- `0x180002948`
- `0x180006bf0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800027e7`

## pseudocode

```c
void __fastcall CDirectoryMonitor<CImageCache,&public: unsigned long CImageCache::OnDirectoryChange(void)>::~CDirectoryMonitor<CImageCache,&public: unsigned long CImageCache::OnDirectoryChange(void)>(
        struct _RTL_CRITICAL_SECTION *a1)
{
  CDirectoryMonitor<CImageCache,&public: unsigned long CImageCache::OnDirectoryChange(void)>::Shutdown();
  CTimer<CDirectoryMonitor<CImageCache,&public: unsigned long CImageCache::OnDirectoryChange(void)>>::Delete((__int64)&a1[2].LockCount);
  DeleteCriticalSection(a1);
}

```

## disassembly

```asm
0x1800027c8  push    rbx
0x1800027ca  sub     rsp, 20h
0x1800027ce  mov     rbx, rcx
0x1800027d1  call    ?Shutdown@?$CDirectoryMonitor@VCImageCache@@$1?OnDirectoryChange@1@QEAAKXZ@@QEAAKXZ; CDirectoryMonitor<CImageCache,&CImageCache::OnDirectoryChange(void)>::Shutdown(void)
0x1800027d6  lea     rcx, [rbx+58h]
0x1800027da  call    ?Delete@?$CTimer@V?$CDirectoryMonitor@VCImageCache@@$1?OnDirectoryChange@1@QEAAKXZ@@@@AEAAXXZ; CTimer<CDirectoryMonitor<CImageCache,&CImageCache::OnDirectoryChange(void)>>::Delete(void)
0x1800027df  mov     rcx, rbx
0x1800027e2  add     rsp, 20h
0x1800027e6  pop     rbx
0x1800027e7  jmp     cs:__imp_DeleteCriticalSection
```
