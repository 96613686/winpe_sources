# p9fs::CoroutineIoIssuer::IssueFailed(p9fs::CancelToken &)

- ea: `0x180029488`
- end: `0x1800294e6`
- name: `?IssueFailed@CoroutineIoIssuer@p9fs@@AEAAXAEAVCancelToken@2@@Z`
- size: `94`
- prototype: `void(p9fs::CoroutineIoIssuer *__hidden this, struct p9fs::CancelToken *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180032d47`
- `0x180032d71`

## callees

- `0x180029488`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800294ac`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800294c8`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800294ac`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800294c8`
- `msvcp_win!_Mtx_lock` at `0x18002949d`
- `msvcp_win!_Mtx_lock` at `0x18002949d`
- `msvcp_win!_Mtx_unlock` at `0x1800294df`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180029494`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180029494`

## pseudocode

```c
void __fastcall p9fs::CoroutineIoIssuer::IssueFailed(PTP_IO *this, struct p9fs::CancelToken *a2)
{
  CancelThreadpoolIo(*this);
  if ( _Mtx_lock(a2) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( *((_DWORD *)a2 + 19) == 0x7FFFFFFF )
  {
    *((_DWORD *)a2 + 19) = 2147483646;
    std::_Throw_Cpp_error(6);
    __debugbreak();
  }
  *((_QWORD *)a2 + 10) = 0;
  _Mtx_unlock(a2);
}

```

## disassembly

```asm
0x180029488  push    rbx
0x18002948a  sub     rsp, 20h
0x18002948e  mov     rcx, [rcx]; pio
0x180029491  mov     rbx, rdx
0x180029494  call    cs:__imp_CancelThreadpoolIo
0x18002949a  mov     rcx, rbx; _Mtx_t
0x18002949d  call    cs:__imp__Mtx_lock
0x1800294a3  test    eax, eax
0x1800294a5  jz      short loc_1800294B3
0x1800294a7  mov     ecx, 5
0x1800294ac  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800294b2  int     3; Trap to Debugger
0x1800294b3  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x1800294ba  jnz     short loc_1800294CF
0x1800294bc  mov     ecx, 6
0x1800294c1  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x1800294c8  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800294ce  int     3; Trap to Debugger
0x1800294cf  mov     rcx, rbx
0x1800294d2  mov     qword ptr [rbx+50h], 0
0x1800294da  add     rsp, 20h
0x1800294de  pop     rbx
0x1800294df  jmp     cs:__imp__Mtx_unlock
```
