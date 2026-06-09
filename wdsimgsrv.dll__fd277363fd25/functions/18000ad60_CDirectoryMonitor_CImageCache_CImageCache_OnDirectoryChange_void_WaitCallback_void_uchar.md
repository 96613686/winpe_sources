# CDirectoryMonitor<CImageCache,&CImageCache::OnDirectoryChange(void)>::_WaitCallback(void *,uchar)

- ea: `0x18000ad60`
- end: `0x18000ad81`
- name: `?_WaitCallback@?$CDirectoryMonitor@VCImageCache@@$1?OnDirectoryChange@1@QEAAKXZ@@CAXPEAXE@Z`
- size: `33`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000abac`
- `0x18000aeac`

## pseudocode

```c
void __fastcall CDirectoryMonitor<CImageCache,&public: unsigned long CImageCache::OnDirectoryChange(void)>::_WaitCallback(
        PVOID a1)
{
  unsigned int v1; // eax
  __int64 v2; // rdx

  v1 = CDirectoryMonitor<CImageCache,&public: unsigned long CImageCache::OnDirectoryChange(void)>::WaitCallback(a1);
  ElValidateWin32_0(v1, v2, "onecore\\internal\\base\\inc\\private\\eco\\wds\\DirMon.h", 391);
}

```

## disassembly

```asm
0x18000ad60  sub     rsp, 28h
0x18000ad64  call    ?WaitCallback@?$CDirectoryMonitor@VCImageCache@@$1?OnDirectoryChange@1@QEAAKXZ@@AEAAKXZ; CDirectoryMonitor<CImageCache,&CImageCache::OnDirectoryChange(void)>::WaitCallback(void)
0x18000ad69  mov     ecx, eax
0x18000ad6b  lea     r8, aOnecoreInterna_1; "onecore\\internal\\base\\inc\\private\\"...
0x18000ad72  mov     r9d, 187h
0x18000ad78  add     rsp, 28h
0x18000ad7c  jmp     ElValidateWin32_0
```
