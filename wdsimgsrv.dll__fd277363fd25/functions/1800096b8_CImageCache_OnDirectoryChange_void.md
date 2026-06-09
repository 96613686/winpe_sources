# CImageCache::OnDirectoryChange(void)

- ea: `0x1800096b8`
- end: `0x1800096e2`
- name: `?OnDirectoryChange@CImageCache@@QEAAKXZ`
- size: `42`
- prototype: `unsigned int __fastcall(CImageCache *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ace0`

## callees

- `0x180009490`

## import_xrefs

- `WDSSRV!WdsPerfCounterAdd` at `0x1800096c9`
- `WDSSRV!WdsPerfCounterAdd` at `0x1800096c9`

## pseudocode

```c
__int64 __fastcall CImageCache::OnDirectoryChange(CImageCache *this)
{
  __int64 v2; // rdx
  int v3; // r8d

  WdsPerfCounterAdd(18);
  return CImageCache::OnChange(this, v2, v3);
}

```

## disassembly

```asm
0x1800096b8  push    rbx
0x1800096ba  sub     rsp, 20h
0x1800096be  mov     edx, 1
0x1800096c3  mov     rbx, rcx
0x1800096c6  lea     ecx, [rdx+11h]
0x1800096c9  call    cs:__imp_WdsPerfCounterAdd
0x1800096d0  nop     dword ptr [rax+rax+00h]
0x1800096d5  mov     rcx, rbx; this
0x1800096d8  add     rsp, 20h
0x1800096dc  pop     rbx
0x1800096dd  jmp     ?OnChange@CImageCache@@QEAAKXZ; CImageCache::OnChange(void)
```
