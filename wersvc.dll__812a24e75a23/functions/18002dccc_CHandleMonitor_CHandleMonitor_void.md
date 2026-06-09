# CHandleMonitor::~CHandleMonitor(void)

- ea: `0x18002dccc`
- end: `0x18002dd21`
- name: `??1CHandleMonitor@@QEAA@XZ`
- size: `85`
- prototype: `void __fastcall(CHandleMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180014074`

## callees

- `0x1800029f4`
- `0x18002dc5c`
- `0x18002dccc`
- `0x18002de78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002dd1a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002dce8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002dce8`

## pseudocode

```c
void __fastcall CHandleMonitor::~CHandleMonitor(CHandleMonitor *this)
{
  void *v2; // rcx
  void *v3; // rcx

  CHandleMonitor::Cleanup(this);
  v2 = (void *)*((_QWORD *)this + 15);
  if ( (unsigned __int64)v2 + 1 > 1 )
    CloseHandle(v2);
  v3 = (void *)*((_QWORD *)this + 10);
  if ( v3 != (void *)-1LL )
  {
    *((_QWORD *)this + 11) = v3;
    operator delete(v3, (const struct std::nothrow_t *)&std::nothrow);
  }
  utl::vector<tlx::unique_any<tlx::file_handle_traits>,utl::allocator<tlx::unique_any<tlx::file_handle_traits>>>::~vector<tlx::unique_any<tlx::file_handle_traits>,utl::allocator<tlx::unique_any<tlx::file_handle_traits>>>((char *)this + 56);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x18002dccc  push    rbx
0x18002dcce  sub     rsp, 20h
0x18002dcd2  mov     rbx, rcx
0x18002dcd5  call    ?Cleanup@CHandleMonitor@@QEAAJXZ; CHandleMonitor::Cleanup(void)
0x18002dcda  mov     rcx, [rbx+78h]; hObject
0x18002dcde  lea     rax, [rcx+1]
0x18002dce2  cmp     rax, 1
0x18002dce6  jbe     short loc_18002DCEE
0x18002dce8  call    cs:__imp_CloseHandle
0x18002dcee  mov     rcx, [rbx+50h]; void *
0x18002dcf2  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002dcf6  jz      short loc_18002DD08
0x18002dcf8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002dcff  mov     [rbx+58h], rcx
0x18002dd03  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002dd08  lea     rcx, [rbx+38h]
0x18002dd0c  call    ??1?$vector@V?$unique_any@Ufile_handle_traits@tlx@@@tlx@@V?$allocator@V?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::unique_any<tlx::file_handle_traits>,utl::allocator<tlx::unique_any<tlx::file_handle_traits>>>::~vector<tlx::unique_any<tlx::file_handle_traits>,utl::allocator<tlx::unique_any<tlx::file_handle_traits>>>(void)
0x18002dd11  lea     rcx, [rbx+8]
0x18002dd15  add     rsp, 20h
0x18002dd19  pop     rbx
0x18002dd1a  jmp     cs:__imp_DeleteCriticalSection
```
